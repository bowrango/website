+++
title = 'Towards optimal unitary synthesis'
date = 2024-09-12T00:15:22-04:00
draft = false
weight = 4
+++


Update (Oct 2026): I finally made progress! See the [preprint on Github](https://github.com/bowrango/lean-unitary/blob/main/submission/decomposition.pdf).

This is my attempt to decompose an arbitrary N-qubit unitary using the minimum number of CX gates. It's been my puzzle since I wrote [unitaryGate](https://www.mathworks.com/help/matlab/ref/unitarygate.html), which implements the best known method that uses twice the lower bound. This work explores my thoughts on improving the algorithm. To my knowledge there is no general algorithm for arbitrary matrices using the minimum number of CX gates.

Quantum circuits are executed using the primitive operations of the quantum computer. The matrices of this primitive set form a basis of the unitary group $U(2^N)$. Any 1 qubit rotation, a unitary matrix in U(2), can be decomposed into 3 rotations like Euler rotations. The figure below shows the smallest circuit for any 2-qubit unitary in the basis {CX,RY,RZ}. The circuit uses 3 2-qubit CX gates and 15 1-qubit rotation gates.

![abc](/circuit.png)

The Quantum Shannon Decomposition (QSD) is the best known general method, using about twice the lower bound. It uses SVD and EIG to recursively factor out single qubit rotations at each step. The 1- and 2-qubit unitary matrices at the leaf nodes are handled using the algorithms above.

![abc](/qsd.png)

The focus will be on the uniform controlled rotation (UCR) gates indicated by $R_Z$ and $R_Y$. The [unitaryGate](https://www.mathworks.com/help/matlab/ref/unitarygate.html) function can remove 1-qubit rotation gates with small angles to allow CX gates to cancel. This gives an informal depth-accuracy tradeoff, and motivates my idea towards a minimum CX gate count and approximate error bound. I'd like to bound the error on an approximate decomposition based on the user provided angle threshold, hoping that leads to an exact decomposition with some insight how to make the angles sparse. Two papers to help solidify this idea:

1. [This](https://arxiv.org/pdf/2106.05649) compresses QSD down to the lower bound using iterative group Lasso regression. Forcing rotation angles to 0 is intuitive but the optimization is expensive. This research is formalized mainly in the language of Lie theory as a recursive sequence of Cartan decompositions. They consider different templates for hardware topology.

2. [This](https://arxiv.org/abs/2205.00081) proves an upper error bound on approximately block encoding a target matrix $A$ using UCR gates. It shows that for common matrices the error is well below the bound.

We learn from (1.) that sparse angles can make QSD optimal through optimization. This hints towards a direct approach as a proof of concept. I apply the main result of (2.) to the UCR gates at each recursive step of QSD.

### Error on a single UCR gate

A UCR gate is block-diagonal over computational basis states of the control qubits:

$$\text{UCR}_Y(\vec{\theta}) = \sum_i |i\rangle\langle i| \otimes R_Y(\theta_i)$$

Setting $\theta_i \to 0$ when $|\theta_i| < \varepsilon$, the spectral norm error is:

$$\Vert\text{UCR}(\vec{\theta}) - \text{UCR}(\tilde{\vec{\theta}})\Vert = \max_{i:\, \text{zeroed}} \Vert R(\theta_i) - I\Vert$$

Since $R_Y(\theta) = e^{-i\theta Y/2}$ has eigenvalues $e^{\pm i\theta/2}$:

$$\Vert R_Y(\theta) - I\Vert = 2|\sin(\theta/4)|$$

So for all zeroed angles ($|\theta_i| < \varepsilon$), each UCR gate introduces error:

$$\delta \leq 2\sin(\varepsilon/4) \leq \varepsilon/2$$

The approximate UCR gate is still exactly unitary — zeroed blocks become identity. This is important for the recursion.

Note that the FABLE compression theorem (2.) bounds the error on the *block-encoded matrix*, where a Walsh-Hadamard transform couples all angles to all matrix elements, giving an $N^3\delta_c$ factor. In QSD, each UCR gate is a direct unitary where each angle independently rotates one basis-state block, so we get the tighter bound above.

### Recursive bound through QSD

At each QSD level, the CSD and two demultiplexing steps decompose an $n$-qubit unitary as:

$$U = (V_1 \otimes I)\; \text{UCR}_Z\; (V_2 \otimes I)\; \text{UCR}_Y\; (V_3 \otimes I)\; \text{UCR}_Z\; (V_4 \otimes I)$$

where $V_1, V_2, V_3, V_4$ are $(n{-}1)$-qubit unitaries. All seven factors and their approximations are exactly unitary, so the standard telescoping bound on the product gives:

$$\Vert U - \tilde{U}\Vert \leq \sum_{i=1}^{4}\Vert V_i - \tilde{V}_i\Vert + 2\Vert\Delta\text{UCR}_Z\Vert + \Vert\Delta\text{UCR}_Y\Vert$$

Let $E(n)$ be the total error for an $n$-qubit unitary. Each $V_i$ contributes $E(n{-}1)$ and each of the 3 UCR gates contributes $\delta$:

$$E(n) = 4\,E(n{-}1) + 3\delta, \qquad E(2) = 0$$

Unrolling gives:

$$\boxed{E(n) = (4^{n-2} - 1)\cdot 2\sin(\varepsilon/4)}$$

For small $\varepsilon$, this simplifies to $E(n) \lesssim (4^{n-2} - 1)\,\varepsilon/2$. The $4^{n-2}$ factor reflects the branching factor of 4 in QSD. Given an error budget $E$, the required angle threshold is:

$$\varepsilon \leq 4\arcsin\!\left(\frac{E}{2(4^{n-2}-1)}\right)$$

This bound is likely loose in practice: the triangle inequality is worst-case, only a fraction of angles at each level fall below $\varepsilon$, and (2.) observes that empirical errors are well below their bound for structured matrices.

### Numerical verification

```matlab
rng(0);
nValues = 3:5;
epsValues = linspace(0, pi, 100);

figure; hold on;
colors = lines(length(nValues));

for k = 1:length(nValues)
    n = nValues(k);
    N = 2^n;

    % Diagonal unitary with known phases
    phi = 2*pi*rand(N, 1);
    U = diag(exp(1i*phi));

    % Compute all circuit-level RZ angles from phases
    angles = diagAngles(phi);

    % Exact decomposition as baseline
    g0 = unitaryGate(1:n, U);
    Ubase = getTransformMatrix(quantumCircuit(g0));

    actual = zeros(size(epsValues));
    tight  = zeros(size(epsValues));
    loose  = zeros(size(epsValues));

    for j = 1:length(epsValues)
        e = epsValues(j);

        g = unitaryGate(1:n, U, RotationThreshold=e);
        Uapprox = getTransformMatrix(quantumCircuit(g));

        actual(j) = norm(Ubase - Uapprox);

        % Tight bound: sum over zeroed rotation gates
        zeroed = abs(angles) < e;
        tight(j) = sum(2 * sin(abs(angles(zeroed)) / 4));

        % Loose bound from recursion
        loose(j) = (4^(n-2) - 1) * 2 * sin(e/4);
    end

    plot(epsValues, actual, '-',  Color=colors(k,:), DisplayName=sprintf('n=%d actual', n));
    plot(epsValues, tight, '--',  Color=colors(k,:), DisplayName=sprintf('n=%d tight', n));
    plot(epsValues, loose, ':',   Color=colors(k,:), DisplayName=sprintf('n=%d loose', n));
end

xlabel('\epsilon (angle threshold)');
ylabel('||U_{exact} - U_{approx}||');
legend(Location='northwest');
title('QSD Approximation Error vs Bound');
grid on;

function a = diagAngles(phi)
% All circuit-level RZ angles for diagonal unitary diag(exp(i*phi)).
% QSD on a diagonal matrix produces only UCR_Z gates. At each level the
% phases split into half-sum (recurse) and half-difference (UCR angles).
    N = length(phi);
    if N == 2
        a = (phi(1) - phi(2)) / 2;
        return;
    end
    top = phi(1:N/2);
    bot = phi(N/2+1:end);
    a = [ucrDecomp((top - bot) / 2); diagAngles((top + bot) / 2)];
end

function a = ucrDecomp(theta)
% Decompose UCR_Z angles into circuit-level RZ angles via the standard
% recursive splitting: sum-half recurses, difference-half becomes RZ gates.
    if isscalar(theta)
        a = theta;
        return;
    end
    top = theta(1:end/2);
    bot = theta(end/2+1:end);
    a = [ucrDecomp((top + bot) / 2); (top - bot) / 2];
end
```

I've omitted my remaining incomplete work and hope to pick this back up soon. Reach out if any of this interests you.
