+++
title = 'Reading'
date = 2024-09-20
draft = false
+++

A list of notable papers I've found interesting (deprecated)

[Variational Quantum Eigensolver Review](https://arxiv.org/abs/2111.05176)
- (2021) Comprehensive review examining VQE algorithm components and methods, identifying key challenges like vanishing gradients and quantum noise mitigation for achieving practical quantum computing advantage

[A variational eigenvalue solver on a quantum processor](https://arxiv.org/pdf/1304.3061)
- (2013) First experimental demonstration of the variational quantum eigensolver for groundstate search

[Best Quantum Compiling Problems](https://arxiv.org/abs/2106.05649)
- (2021) Proposes generic CX units with group Lasso regression to iteratively compress circuits towards a target unitary. They we able to compress QSD 2x towards the lower bound!

[Synthesis of Quantum Logic Circuits](https://arxiv.org/abs/quant-ph/0406176)
- (2006) Presents asymptotically optimal quantum logic circuits requiring significantly less gates than previous methods through novel quantum multiplexors and Shannon decomposition analogies. I implemented these algorithms when developing unitaryGate and emailed Shende about some optimizations. A fascinating puzzle of mine is how to bound the exact error for a desired tolerance.

[Optimization of Quantum Circuit Mapping](https://arxiv.org/pdf/1907.02686)
- (2019) Presents algorithms that improve quantum circuit mapping using gate identities and commutation rules

[Elementary Gates for Quantum Computation](https://arxiv.org/abs/quant-ph/9503016)
- (1995) Establishes that a universal set of quantum gates can implement any unitary transformation on multiple qubits while analyzing gate complexity. This is the canonical work giving explicit circuits for common unitaries.

[Variational Quantum Factoring](https://arxiv.org/pdf/1808.08927.pdf)
- (2018) Introduces a variational quantum factoring algorithm that maps integer factorization to an Ising Hamiltonian as an alternative to Shor's algorithm.

[Quantum Tensor Networks in a Nutshell](https://arxiv.org/abs/1708.00006)
- (2017) Teaches tensor network methods and their graphical language for efficiently representing operations with applications to combinatorial problems

[Tensor Networks for Complex Systems](https://arxiv.org/abs/1812.04011)
- (2019) Comprehensive review exploring tensor network states and their applications across quantum physics

[Optimal Qubit Assignment and Routing via Integer Programming (Qiskit)](https://arxiv.org/abs/2106.06446)
- (2021) Presents an integer linear programming approach to optimally assign and route qubits with limited connectivity, achieving significant reductions in circuit depth and CX gates compared to existing transpilers. It is quite ironic that qubit mapping is already an NP-complete problem.

[CS 269Q Lecture Notes](https://cs269q.stanford.edu/lectures/lecture12.pdf)
- (2019) Notes from Stanford on quantum compilation.

[Graph-Coupled Oscillator Networks](https://arxiv.org/abs/2202.02296)
- (2022) Introduces a novel graph deep learning framework based on discretized oscillator dynamics that addresses oversmoothing while improving gradient stability. I'm curious how the Kuromoto/Adler equations fit into this framework.

[Graph Neural Diffusion](https://arxiv.org/abs/2106.10934)
- (2021) Presents the GRAND framework that formulates GNNs as discretizations of continuous diffusion processes governed by PDEs. This enables deeper GNNs that mitigate oversmoothing and information bottlenecks.

[Quantum Approximate Optimization Algorithm](https://arxiv.org/abs/1411.4028)
- (2014) Introduces a quantum variational algorithm that approximates solutions to combinatorial optimization problems. It's basically a learned version of simulated annealing with a discretized pathway. This is the original QAOA paper.

[Gradients of Parameterized Quantum Gates Using the Parameter-Shift Rule](https://arxiv.org/pdf/1905.13311.pdf)
- (2019) Presents a method to compute quantum circuit gradients by extending the parameter-shift rule to broader classes of quantum gates through decomposition.

[Variational Quantum Algorithms](https://arxiv.org/abs/2012.09265)
- (2021) Review article examining variational quantum algorithms that leverage classical optimizers to train parametrized quantum circuits as the best hope for obtaining near-term quantum advantage.

[Quantum Natural Gradients](https://arxiv.org/abs/1909.02108)
- (2020) Presents a quantum optimization method that applies natural gradient descent to variational quantum circuits using the Fubini-Study metric tensor.

[Quantum Natural Gradient Demo (Pennylane)](https://pennylane.ai/qml/demos/tutorial_quantum_natural_gradient.html)
- (2019) Pennylane is basically PyTorch for quantum computing. I really like their interface.

[Quantum Natural Language Generation on Near-Term Devices](https://arxiv.org/pdf/2211.00727.pdf)
- (2022) Develops a quantum/classical algorithm based on simulated annealing to generates sentences. Probably not the best use of a quantum computer.

[On the Natural Gradient for Variational Quantum Eigensolver](https://arxiv.org/pdf/1909.05074.pdf)
- (2019) Presents case studies demonstrating how the natural gradient improves on standard gradient-based optimization in VQE by leveraging geometric structure of parameter space. Yes, people shouldn't use Adam to optimize quantum circuits.

[The Power of Quantum Neural Networks](https://arxiv.org/pdf/2011.00027.pdf)
- (2021) Show that quantum networks can achieve a significantly better eﬀective dimension than comparable classical networks. They study the trainability of quantum models in connection to the Fisher information spectrum and barren plateaus.

[Liquid Time-Constant Networks](https://arxiv.org/pdf/2006.04439.pdf)
- (2020) Introduces Liquid Time-Constant Networks employing linear first-order dynamical systems modulated via nonlinear interlinked gates for improved stability and expressivity in time-series prediction.

[Closed-Form Continuous-Time Neural Networks](https://www.nature.com/articles/s42256-022-00556-7)
- (2022) Demonstrates closed-form approximation of liquid time-constant networks achieving 1-5 orders of magnitude faster training and inference compared to differential equation-based counterparts.

[Neural Ordinary Differential Equations](https://proceedings.neurips.cc/paper/2018/file/69386f6bb1dfed68692a24c8686939b9-Paper.pdf)
- (2018) Parameterizes the derivative of hidden states using neural networks computed with differential equation solvers, achieving constant memory cost and adaptive evaluation strategies

[Grover Adaptive Search for Constrained Polynomial Binary Optimization](https://arxiv.org/pdf/1912.04088.pdf)
- (2021) Demonstrates efficient quantum oracles for solving constrained polynomial binary optimization problems using Grover's algorithm with quadratic speedup suitable for near-term quantum hardware

[Optimized Compilation of Aggregated Instructions for Realistic Quantum Computers](https://arxiv.org/pdf/1902.01474.pdf)
- (2019) Presents quantum compilation methodology aggregating multiple logical gates into larger units optimized for physical quantum hardware, achieving approximately 5x speedup

[Resource-Efficient Quantum Algorithms for Protein Folding](https://www.nature.com/articles/s41534-021-00368-4)
- (2021) Presents model Hamiltonian with O(N4) scaling and quantum variational algorithm successfully applied to folding 10 amino acid Angiotensin on 22 qubits

[Resource-Efficient Quantum Algorithms for Protein Folding (Sup. Mat.)](https://static-content.springer.com/esm/art%3A10.1038%2Fs41534-021-00368-4/MediaObjects/41534_2021_368_MOESM1_ESM.pdf)

[Gate-Free State Preparation for Fast Variational Quantum Eigensolver Simulations](https://www.nature.com/articles/s41534-021-00493-0)
- (2021) Proposes ctrl-VQE where device-level pulse shapes are variationally optimized for state preparation rather than using quantum circuits, drastically reducing coherence time requirements

[GRAPE: Design of NMR Pulse Sequences by Gradient Ascent Algorithms](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=a7aadf83cb648c3cb2c593e5c7ab7b99b22f2a2b)

[Construction of Energy Functions for Lattice Heteropolymer Models: A Case Study in Constraint Satisfaction Programming and Adiabatic Quantum Optimization](https://arxiv.org/pdf/1211.3422.pdf)
- (2012) Demonstrates reformulation of lattice heteropolymer optimization problems as constraint satisfaction problems and reduces coupling locality for implementation on quantum annealing devices

[Solving Quantum Chemistry Problems with a D-Wave Quantum Annealer](https://arxiv.org/pdf/1811.05256.pdf)
- (2018) Maps quantum chemistry Hamiltonians to Ising spin glass formulations revealing that current D-Wave quantum annealers exhibit exponential scaling limitations requiring new couplers

[t|ket⟩: A Retargetable Compiler for NISQ Devices](https://arxiv.org/pdf/2003.10611.pdf)
- (2020) Introduces quantum compiler platform that generates code for various NISQ devices while optimizing circuits and routing to minimize device errors better than existing competitors

[Structured Cospans](https://arxiv.org/pdf/1911.04630.pdf)
- (2020) Introduces structured cospans as mathematical framework for studying networks with inputs and outputs forming symmetric monoidal categories applicable to electrical circuits and chemical reaction networks

[Approximate Quantum Compiling for Quantum Simulation: A Tensor Network-Based Approach](https://arxiv.org/pdf/2301.08609.pdf)
- (2025) Introduces AQCtensor algorithm generating shallow quantum circuits from matrix product states with constant depth achieving at least order of magnitude circuit depth reduction

[Mathematical Game Theory](https://arxiv.org/pdf/2012.01850.pdf)
- (2020) Presents unified mathematical framework for game theory by modeling games as state sequences encompassing classical games while establishing connections to quantum mechanics through Hilbert space representation

[Foundational Patterns for Efficient Quantum Computing](https://arxiv.org/pdf/1907.11513.pdf)
- (2019) Introduces quantum computing patterns and quantum dictionary framework applying fundamental quantum algorithms to solve NP-hard problems using visual geometric approach

[Thermodynamic AI and the Fluctuation Frontier](https://arxiv.org/pdf/2302.06584.pdf)
- (2023) Proposes unified Thermodynamic AI framework connecting physics-inspired algorithms while introducing specialized hardware using stochastic bits and Maxwell's demon devices to leverage thermal fluctuations as computational resource
- another classic. This one got me into probabilistic bits.

[Thermodynamic Linear Algebra](https://arxiv.org/abs/2308.05660)
- (2023) Establishes connection between thermodynamics and linear algebra proposing that solving linear algebra problems can be accomplished by sampling from thermodynamic equilibrium distribution of coupled harmonic oscillators

[Compiling machine learning programs via high-level tracing](https://cs.stanford.edu/~rfrostig/pubs/jax-mlsys2018.pdf)
- (2018) Introduces JAX domain-specific tracing JIT compiler for generating high-performance accelerator code from pure Python and NumPy machine learning programs using XLA compiler infrastructure

[Thermodynamic Matrix Exponentials and Thermodynamic Parallelism](https://arxiv.org/abs/2311.12759)
- (2023) Introduces thermodynamic algorithm for matrix exponentiation achieving linear speedup by leveraging thermodynamic noise as resource enabling effective parallelization through thermodynamic parallelism

[Invariance and equivariance in brains and machines](https://www.youtube.com/watch?v=xnhhp916JNU&list=LL&index=18)
- (2024) Surveys image processing techniques inspired by the brain. I got quite distracted for a week or and bought an EEG board.

[Disentangling images with Lie group transformations and sparse coding](https://arxiv.org/abs/2012.12071)
- (2020) Combines Lie group mathematics with sparse coding to automatically learn and separate underlying shapes in images from their continuous geometric transformations

[Principles of Neural Design](https://mitpress.mit.edu/9780262534680/principles-of-neural-design/)
- (2017) I very much enjoyed this book and am very interested in biologically plausible learning algorithms.

[Analog Memory and High-Dimensional Computation](http://www.rctn.org/bruno/public/nature-neuromorphic-talk.pdf)
- (Unknown)

[Neuromorphic Visual Scene Understanding with Resonator Networks](https://arxiv.org/pdf/2208.12880)
- (2024) Presents neuromorphic approach using Hierarchical Resonator Networks with Vector Symbolic Architectures to efficiently solve visual scene understanding by factorizing geometric transformations

[Hippocampal memory, cognition, and the role of sleep](https://www.youtube.com/watch?v=c2_rnYdUMiM)
- (2024) 

[Computing with Residue Numbers in High-Dimensional Representation](https://www.researchgate.net/publication/375793530_Computing_with_Residue_Numbers_in_High-Dimensional_Representation)
- (2023) I'm curious about how residue numbers could be used for quantum applications. This or another paper had application for subset-sum but I can't remember.

[Visual scene analysis via factorization of HD vectors](https://redwood.berkeley.edu/wp-content/uploads/2022/11/HDC-scene-analysis-factorization.pdf)
- (2022)

[Classically Estimating Observables of Noiseless Quantum Circuits](https://arxiv.org/pdf/2409.01706)
- (2024) Develops classical algorithm using Pauli propagation demonstrating that estimating observables of random quantum circuits exhibiting chaotic and locally scrambling behavior is classically tractable

[Classical Surrogate Simulation of Quantum Systems with LOWESA](https://arxiv.org/pdf/2308.09109)
- (2023) Introduces LOWESA classical algorithm constructing surrogate expectation landscape to efficiently simulate large quantum systems

[Network Thermodynamics](http://160592857366.free.fr/joe/ebooks/ShareData/NetworkThermo.pdf)
- (Unknown)

[Tensorized Pauli decomposition algorithm](https://arxiv.org/pdf/2310.13421)
- (2024) Introduces faster algorithm for decomposing multi-qubit matrices into Pauli operators employing matrix slicing and addition

[PauliComposer: Compute Tensor Products of Pauli Matrices Efficiently](https://arxiv.org/pdf/2301.00560)
- (2023) Presents simple algorithm for tensor products of Pauli matrices with an optimized approach for Pauli basis decomposition

[Decomposing dense matrices into dense Pauli tensors](https://arxiv.org/pdf/2401.16378)
- (2024) Presents efficient algorithm using Gray code to decompose dense matrices into Pauli tensor sums in O(2^N) time. Achieves 1.5-5x speedups with fixed memory requirements.

[Towards large-scale quantum optimization solvers with few qubits](https://arxiv.org/pdf/2401.09421)
- (2025) Develops variational quantum optimization method solving problems with thousands of binary variables using only small numbers of qubits achieving solutions competitive with state-of-the-art classical solvers

[Variational quantum optimization with multibasis encodings](https://journals.aps.org/prresearch/pdf/10.1103/PhysRevResearch.4.033142)
- (2021) Shows how combinatorial problems can use a more compact encoding.

[Statistical Physics of Self-Replication](https://arxiv.org/abs/1209.1179)
- (2012) Derives that a thermodynamic lower bound for rate of heat production is determined by growth rate, internal entropy, and durability of replicator.

[Transmit LoRa Frames Without a Radio](https://github.com/cnlohr/lolra?tab=readme-ov-file)
- (2024)

[Decomposition Pipeline for Large-Scale Portfolio Optimization with Applications to Near-Term Quantum Computing](https://arxiv.org/pdf/2409.10301)
- (2024) Develops decomposition pipeline breaking large portfolio optimization problems into smaller subproblems using random matrix theory, modified spectral clustering, and risk rebalancing

[Building a simple oscillator based Ising machine for research and education](https://arxiv.org/pdf/2410.00523)
- (2024) Presents straightforward oscillator-based Ising machine designed for educational and research use offering non-traditional computational approach to tackle combinatorial problems

[Geometric Deep Learning Grids, Groups, Graphs, Geodesics, and Gauges](https://arxiv.org/pdf/2104.13478)
- (2021) Provides unified geometric framework for understanding neural network architectures by exposing underlying regularities in data with constructive procedure to incorporate prior physical knowledge

[FABLE: Fast Approximate Quantum Circuits for Block-Encodings](https://arxiv.org/abs/2205.00081)
- (2022) Introduces FABLE method generating approximate quantum circuits for block-encodings of matrices in a fast manner enabling efficient implementations suitable for near-term quantum devices

[Braindrop: A Mixed-Signal Neuromorphic Architecture With a Dynamical Systems-Based Programming Model](https://web.stanford.edu/group/brainsinsilicon/documents/ANeckar2019.pdf)
 - (2019)

[Noise-injected analog Ising machines enable ultrafast statistical sampling and machine learning](https://www.nature.com/articles/s41467-022-33441-3)
- (2022) Introduces universal concept to achieve ultrafast statistical sampling with analog Ising machines by injecting noise demonstrating orders-of-magnitude faster performance than software-based methods.

[Natural gradient and parameter estimation for quantum Boltzmann machines](https://arxiv.org/pdf/2410.24058)
- (2024) Establishes quantum algorithms for computing Fisher-Bures and Kubo-Mori information matrices of thermal states enabling natural gradient descent algorithm for quantum Boltzmann machine learning

[The Purely Functional Software Deployment Model](https://edolstra.github.io/pubs/phd-thesis.pdf)
- The Nix blueprint.

[Tensor Algebra on an Optoelectronic Microchip](https://arxiv.org/pdf/2208.06749)
- (2022) Proposes accelerating tensor algebra computations by offloading operations to optical microchip supported by custom programming language and novel sparse tensor storage method

[Probabilistic Machine Learning: Advanced Topics](https://probml.github.io/pml-book/book2.html)

[The story of PX4 and Pixhawk](https://auterion.com/company/the-history-of-pixhawk/)

[Analog Paradigm](https://analogparadigm.com/index.html)

[Running Markov Chain Monte Carlo on Modern Hardware and Software](https://arxiv.org/pdf/2411.04260)
- (2024) Demonstrates how to leverage modern deep learning hardware and software frameworks to dramatically accelerate Markov Chain Monte Carlo computations traditionally relying on CPU-based approaches

[Oscillator-based Ising Machine](https://arxiv.org/pdf/1709.08102)
- (2017) Demonstrates that Ising machines can be realized using almost any nonlinear self-sustaining oscillators with logic values encoded in phases offering faster and more power-efficient approach
- Tianshi Wang and Jaijeet Roychowdhury (2017)

[OIM: Oscillator-based Ising Machines for Solving Combinatorial Optimisation Problems](https://arxiv.org/pdf/1903.07163)
- (2019) Introduces oscillator-based Ising machines leveraging coupled nonlinear oscillators with sub-harmonic injection locking demonstrating improved performance on benchmark problems for CMOS hardware implementation
- Tianshi Wang and Jaijeet Roychowdhury (2019)

[Solving combinatorial optimisation problems using oscillator based Ising machines](https://jaijeet.github.io/research/PDFs/2021-05-05-Springer-Natural-Computing--Wang-Wu-Nobel-Roychowdhury--OIM--invited.pdf)
- (2021)

[Deep Differentiable Logic Gate Networks](https://arxiv.org/pdf/2210.08277)
- (2022) Introduces differentiable logic gate networks enabling training neural architectures composed of logic gates using gradient descent achieving fast inference speeds beyond million images per second on single CPU core

[Convolutional Differentiable Logic Gate Networks](https://arxiv.org/abs/2411.04732v1)
- (2024) Introduces convolutional logic gate networks achieving competitive accuracy on CIFAR-10 with significantly fewer gates enabling fast efficient inference using only basic hardware operations

[Thermodynamic Natural Gradient Descent](https://arxiv.org/pdf/2405.13817v1)
- (2024) Presents hybrid digital-analog algorithm implementing natural gradient descent with efficiency comparable to first-order methods by exploiting thermodynamic properties of analog system at equilibrium

[Thermodynamic Computing System for AI Applications](https://arxiv.org/pdf/2312.04836)
- (2023) Demonstrates first continuous-variable thermodynamic computer using RLC circuits performing both sampling and linear algebra operations with potential applications in accelerating probabilistic AI workloads

[An Elementary Introduction to Kalman Filtering](https://arxiv.org/pdf/1710.04055)
- (2017) Presents Kalman filtering concepts in accessible way by separating abstract principles from specific applications enabling broader understanding and adoption across computer systems

[The Hardware Lottery](https://arxiv.org/pdf/2009.06489)
- (2020) Introduces concept of hardware lottery describing how research ideas succeed based on compatibility with available hardware rather than inherent superiority

[Coupled-Oscillator Models: State-Space & Dynamics](https://csc.ucdavis.edu/~chaos/courses/poci/Projects2013/Warner/Coupled_Oscillators_NCASO.pdf)

[State Space Approach to Solving RLC circuits](https://web.mit.edu/16.unified/www/FALL/signalssystems/Lecture13.pdf)

[On the State Space Geometry of the Kuramoto–Sivashinsky Flow in a Periodic Domain](https://cns.gatech.edu/~predrag/papers/SCD07.pdf)

[Circuit Synthesis and Electrical Interpretation of Synchronization in the Kuramoto Model](https://ieeexplore.ieee.org/document/8904942)
- (2019) Wave digital model. No hardware experiments

[Generative models of cortical oscillations: neurobiological implications of the Kuramoto model](https://pmc.ncbi.nlm.nih.gov/articles/PMC2995481/pdf/fnhum-04-00190.pdf)

[A Survey of Spiking Neural Network Accelerator on FPGA](https://arxiv.org/pdf/2307.03910)
- (2023) Examines FPGA implementations of spiking neural networks, network architectures, encoding methods, and hardware design approaches.

[Lyapunov function for the Kuramoto model of nonlinearly coupled oscillators](https://link.springer.com/article/10.1007/BF01048044)
- (1993) The original paper.

[Novel Computing Paradigms using Oscillators](https://www2.eecs.berkeley.edu/Pubs/TechRpts/2020/EECS-2020-12.pdf)
- (2020) The paper that got my interested in Kuramoto systems

[Solving combinatorial optimisation problems using oscillator based Ising machines](https://jaijeet.github.io/research/PDFs/2021-05-05-Springer-Natural-Computing--Wang-Wu-Nobel-Roychowdhury--OIM--invited.pdf)

[Use of the CMOS Unbuffered Inverter in Oscillator Circuits](https://www.ti.com/lit/an/szza043/szza043.pdf?ts=1732197694421&ref_url=https%253A%252F%252Fwww.google.com%252F)

[Harmonic Oscillators in CMOS—A Tutorial Overview](https://ieeexplore.ieee.org/document/9530265)
- (2021) Overview of noise models

[Autonomous Probabilistic Coprocessing with Petaflips per Second](https://arxiv.org/pdf/1907.09664)
- (Purdue 2020) Introduces a probabilistic computer architecture using autonomous p-bits. The clockless circuit represents asynchronous parallelism to realize Boltzmann Machines in hardware. No asymptotic guarantees for convergence. they wrote a MATLAB MEX interface to AWS FPGA.

[Hardware-Aware In Situ Learning Based on Stochastic Magnetic Tunnel Junctions](https://journals.aps.org/prapplied/pdf/10.1103/PhysRevApplied.17.014016)

[Roadmap for unconventional computing with nanotechnology](https://iopscience.iop.org/article/10.1088/2399-1984/ad299a/pdf)

[A Reliable and Efficient Procedure for Oscillator PPV Computation, With Phase Noise Macromodeling Applications](https://www.researchgate.net/publication/3224937_A_reliable_and_efficient_procedure_for_oscillator_PPV_computation_with_phase_noise_macromodeling_applications)

[A Modern Primer on Processing in Memory](https://arxiv.org/pdf/2012.03112)
- (2020) Presents comprehensive overview of processing-in-memory technology that aims to reduce or eliminate data movement by placing computation mechanisms inside or near memory chips

[A Simplified Phase Model for Oscillator Based Computing](https://arxiv.org/pdf/1508.00051)
- (2015) Develops computationally efficient phase model that can predict frequency locking behavior with several orders of magnitude speedup for simulating coupled oscillator systems in unconventional computing

[Analysis and design of sub-harmonically injection locked oscillators](https://www.researchgate.net/publication/254023694_Analysis_and_design_of_sub-harmonically_injection_locked_oscillators)
- (2013)

[Synchronization in Complex Networks of Phase Oscillators: A Survey](http://motion.me.ucsb.edu/pdf/2013b-db.pdf)
- (2014)

[Rigorous Q Factor Formulation and Characterization for Nonlinear Oscillators](https://arxiv.org/pdf/1710.02015)
- (2017) Introduces universally applicable Q factor definition for nonlinear oscillators that can be formulated and computed numerically. Extends beyond previous definitions limited to linear systems.

[Methods for Computing Periodic Steady-State - Part II](https://ocw.mit.edu/courses/6-336j-introduction-to-numerical-simulation-sma-5211-fall-2003/fe6022ba6c3ca191675836d3bb5d4fcd_lec16.pdf)

[Notes on Oscillators](https://people.engr.tamu.edu/s-sanchez/665%20Oscillators.pdf)

[An integrated coupled oscillator network to solve optimization problems](https://www.nature.com/articles/s44172-024-00261-w)
- (2024) Presents coupled oscillator network on 4.6mm2 silicon chip with 1440 oscillators and routable connections. Uses MATLAB.

[Analyzing Oscillators using Describing Functions](https://arxiv.org/pdf/1710.02000)
- (2017) Demonstrates that describing functions can be systematically applied to analyze various categories of oscillators including LC, relaxation, and ring oscillators across different physical domains. Includes transfer function analysis of phase perturbation and locking with stability conditions.

[Thermodynamic Algorithms for Quadratic Programming](https://arxiv.org/pdf/2411.14224)
- (2024) Presents novel hybrid digital-analog algorithm solving quadratic programming problems using thermodynamic hardware achieving polynomial asymptotic speedup by incorporating thermodynamic subroutine into interior-point method.

[A coherent Ising machine for 2000-node optimization problems](https://www.researchgate.net/publication/309323862_A_coherent_Ising_machine_for_2000-node_optimization_problems)
- (2016) Reports 2000-spin network with all-to-all coupling using time-multiplexed degenerate optical parametric oscillators

[Dependence of LC VCO Oscillation Frequency on Bias Current](https://web.engr.oregonstate.edu/~moon/research/files/iscas06_lc.pdf)
- (2006) More notes on cross-coupled LC CMOS

[Quantum computing of reacting flows via Hamiltonian simulation](https://arxiv.org/pdf/2312.07893)
- (2024) Develops quantum computing algorithms transforming reactive flow problems into Hamiltonian systems enabling one-shot solutions with potential exponential speedup validated on quantum simulators for combustion applications

[Digitally Synthesized Stochastic Flash ADC Using Only Standard Digital Cells](https://www.benjamin.hershberg.com/wp-content/papercite-data/papers/2011-vlsi-stochastic-adc.pdf)
- (2011) Simple way to use digital gates to perform AD conversion, which usually requires analog components.

[An Ising solver chip based on coupled ring oscillators with a 48-node all-to-all connected array architecture](https://www.nature.com/articles/s41928-023-01021-y)
- (2023) An Ising solver with all-to-all coupling between 48 spins. Local and global connectivity useful for decomposition algorithms that require a wide dynamic range. Supports integer weights with cross-bar arrays.

[BarraCUDA: Bringing Electromagnetic Side Channel Into Play to Steal the Weights of Neural Networks from NVIDIA GPUs](https://arxiv.org/pdf/2312.07783v1)
- (2023) Demonstrates novel electromagnetic side-channel attack extracting parameters of neural networks running on popular Nvidia Jetson Nano device by exploiting physical vulnerabilities in edge GPUs.

[Analog Coupled Oscillator Based Weighted Ising Machine](https://www.nature.com/articles/s41598-019-49699-5)
- (2019) Reports an analog computing system with coupled non-linear oscillators. Funded research from MIT Lincoln Lab.

[Provable bounds for noise-free expectation values computed from noisy samples](https://arxiv.org/abs/2312.00733)
- (2024) Introduces methods to establish provable bounds on noise-free expectation values from noisy samples using Conditional Value at Risk. I talked to IBM about CVaR.

[A Rigorous Graphical Technique for Predicting Sub-harmonic Injection Locking in LC Oscillators](https://jaijeet.github.io/research/PDFs//2014-06-DAC-Bhushan-Graphical-SHIL.pdf)
- (2014) MATLAB analysis.

[Design Issues in CMOS Differential LC Oscillators](http://smirc.stanford.edu/papers/JSSC99MAY-ali.pdf)
- (1999)

[Ising machines: Hardware solvers for combinatorial optimization problems](https://arxiv.org/pdf/2204.00276)
- (2022) Reviews various hardware approaches to building Ising machines comparing their performance using metrics like ground-state success probability and time-to-solution across classical and quantum technologies

[Experimental investigation of performance differences between Co- herent Ising Machines and a quantum annealer](https://arxiv.org/pdf/1805.05217)
- (2019) Demonstrates that coherent Ising machines achieve significantly better performance than quantum annealers on dense optimization problems with exponential advantages in solution time beyond 50 vertices

[Equivalence of coupled parametric oscillator dynamics to Lagrange multiplier primal-dual optimization](https://arxiv.org/pdf/2204.02472)
- (2022) Demonstrates that network of coupled parametric oscillators can solve combinatorial optimization problems by implementing Lagrange multiplier constrained optimization with pump depletion effect naturally enforcing binary constraints. Work by MIT, Sandia National Labs, and UC Berkeley.

[A unifying framework for mean-field theories of asymmetric kinetic Ising systems](https://www.nature.com/articles/s41467-021-20890-5)
- (2021) Proposes unifying framework for mean-field theories of asymmetric kinetic Ising systems from information geometry perspective built on Plefka expansions preserving system correlations.

[Nonequilibrium thermodynamics of the asymmetric Sherrington-Kirkpatrick model](https://www.nature.com/articles/s41467-023-39107-y)
- (2023) Investigates stochastic thermodynamics of asymmetric Sherrington-Kirkpatrick model obtaining exact solutions using path integral method showing entropy production peaks at critical phase transitions.

[Late Breaking Results: New Computational Results and Hardware Prototypes for Oscillator-based Ising Machines](https://arxiv.org/pdf/1904.10211)
- (2019) Develops working hardware prototypes of oscillator-based Ising machines using CMOS electronic oscillators demonstrating effectiveness through both physical implementations and computational simulations. Lots of overlap with other papers but I got more clues.

[QCLAB++: Simulating Quantum Circuits on GPUs](https://arxiv.org/abs/2303.00123)
- (2023) C++ library for state-vector simulation with OpenMP acceleration. It uses clever bitshift masks for efficient indexing.

[Explicit Quantum Circuits for Block Encodings of Certain Sparse Matrices](https://arxiv.org/abs/2203.10236)
- (2022) Provides explicit constructions for quantum circuits that block-encode well-structured sparse matrices. Allows O(poly(n)) elementary quantum gates for n qubits.

[FABLE: Fast Approximate Quantum Circuits for Block-Encodings](https://arxiv.org/abs/2205.00081)
- (2022) I'm curious how this bound can be extended to unitaryGate for general unitary synthesis.

[An algebraic quantum circuit compression algorithm for Hamiltonian simulation](https://arxiv.org/pdf/2108.03283)
- (2021) Presents efficient algorithm for compressing quantum circuits used in Hamiltonian simulation achieving shallow quantum circuits with uncomplicated topologies suited for near-term quantum devices

[QASMTrans: A QASM based Quantum Transpiler Framework for NISQ Devices](https://arxiv.org/abs/2308.07581)
- (2023) High-performance C++ quantum transpiler. Uses SABRE with a modified lookahead heuristic. The code is a mess.

[Stability and decay of Bloch oscillations in presence of time-dependent nonlinearity](https://arxiv.org/pdf/1109.2798)
- (2011) Discovers that when Bose-Einstein condensates undergo Bloch oscillations with time-varying interactions an infinite family of modulations can sustain periodic wave packet evolution

[Recent Advances in Coupled Oscillator Theory](https://arxiv.org/abs/2001.10620)
- (2020) Reviews weakly coupled oscillator theory and extends it by introducing isostable reduction methods to explain behaviors beyond standard weak coupling framework with applications to neuronal systems

[Creating electronic oscillator-based Ising machines without external injection locking](https://www.nature.com/articles/s41598-021-04057-2)
- (2021) Experimentally demonstrates new electronic autaptic oscillator using engineered feedback to eliminate need for external second harmonic signal injection. The engineered feedback generates two decay time constants which effectively generates the 2nd harmonic internally.

[Oscillator-based optimization: design, emulation, and implementation](https://link.springer.com/article/10.1140/epjb/s10051-023-00644-6)
- (2024) Makes parallels between oscillator optimization and wave-digital modelling.

[An Ising Hamiltonian solver based on coupled stochastic phase-transition nano-oscillators](https://www.nature.com/articles/s41928-021-00616-7)
- (2021) Reports Ising solver based on network of electrically coupled phase-transition nano-oscillators with 8-node prototype.

[CMOS-Compatible Ising Machines built using Bistable Latches Coupled through Ferroelectric Transistor Arrays](https://arxiv.org/pdf/2205.14729)
- (2022) Built MATLAB interface to SPICE.

[Spintronic devices as next-generation computation accelerators](https://arxiv.org/pdf/2403.13564v1)
- (2024) Examines spintronics-based Ising machines as hardware accelerators to address computational power demands facing conventional silicon technology benchmarking different platforms and control approaches

[Silicon microring resonators](https://www.photonics.intec.ugent.be/download/pub_3105.pdf)

[On computational capabilities of Ising machines based on nonlinear oscillators](https://arxiv.org/abs/2105.07591)
- (2022) Demonstrates that oscillator networks based on Kuramoto synchronization model can solve NP-hard optimization problems with polynomial time scaling; Proper binary state reconstruction is critical to achieving optimal approximation.
- Kuramoto model that assumes oscillators have same period is the ferromagnetic XY model, which is rank-2 semidefinite programming problem (BZM)
    - Kuramoto systems are identical to BZM so they converge to 0.87 of optimal in polynomial time
    - Rounding problem requires correctly choosing phase direction. The anisotropic state can be destroyed by methods used to stabilize Kuramoto systems (like SHIL!)

[Self-contained relaxation-based dynamical Ising machines](https://arxiv.org/abs/2305.06414)
- (2023) Proposes V2 model to solve Kuramoto rounding problem. No matter which spin orientation it will always be the optimal rounding. Stochastic perturbations will converge to the optimal solution almost surely in superpolynomial time. DIMPLE fits this model!

[Custom CMOS Ising Machine Based on Relaxed Burer-Monteiro-Zhang Heuristic](https://ieeexplore.ieee.org/document/10187692)
- (2023) Focus on computational capability of the dynamical model driving the machine instead of forcing close-to-binary states

[Ising machines as hardware solvers of combinatorial optimization problems](https://arxiv.org/abs/2204.00276)
- (2022)

[Augmenting an electronic Ising machine to effectively solve boolean satisfiability](https://www.nature.com/articles/s41598-023-49966-6.pdf)
-(2023) Uses cross-bar arrays for cubic terms

[100,000-spin coherent Ising machine](https://www.science.org/doi/epdf/10.1126/sciadv.abh0952)
- (2021) Reports CIM with degenerate optical parametric oscillator pulses

[A moment-based approach to the dynamical solution of the Kuramoto model](https://iopscience.iop.org/article/10.1088/0305-4470/30/23/010/pdf)
- (1997)

[Stability diagram for the forced Kuramoto model](https://arxiv.org/pdf/0807.4717)
- (2008) Conducts bifurcation analysis of periodically forced Kuramoto model discovering stability diagram bears striking resemblance to weakly nonlinear forced van der Pol oscillator

[Quantum collective motion of macroscopic mechanical oscillators](https://arxiv.org/pdf/2407.02453)
- (2024) Demonstrates quantum collective motion in six mechanical oscillators coupled through superconducting circuits. First time for macroscopic mechanical oscillators to be put in quantum ground state?

[All-to-all reconfigurability with sparse and higher-order Ising machines](https://arxiv.org/pdf/2312.08748)
- (2024) Demonstrates that probabilistic bit Ising machines can achieve competitive performance on hard optimization problems through a multiplexed architecture emulating an all-to-all network with highly parallelized chromatic Gibbs sampling. Adaptive parallel tempering algorithm

[Electrical and Wave Digital Modeling of CMOS-Based Ring Oscillators](https://www.researchgate.net/profile/Bakr-Al-Beattie/publication/377312212_Electrical_and_Wave_Digital_Modeling_of_CMOS-Based_Ring_Oscillators/links/65a5190ed5ce0e3f94cc5c26/Electrical-and-Wave-Digital-Modeling-of-CMOS-Based-Ring-Oscillators.pdf)
- (2023)

[Deriving Dense Linear Algebra Libraries](https://www.cs.utexas.edu/~flame/pubs/FAC.pdf)
- (Unknown) Triangular Lyapunov examples in MATLAB

[A Performance Study of the 2D Ising Model on GPUs](https://arxiv.org/abs/1906.06297)
- (2019) Demonstrates that GPU implementations of 2D Ising model simulation can outperform specialized hardware using techniques including stencil-based algorithm and multi-spin coding approaches optimized for NVIDIA hardware.

[A mixed-signal oscillatory neural network for scalable analog computations in phase domain](https://iopscience.iop.org/article/10.1088/2634-4386/ace9f5/pdf)
- (2023)

[Non-binary dynamical Ising machines for combinatorial optimization](https://arxiv.org/pdf/2412.08481)
- (2024) Introduces non-binary dynamical Ising machines solving combinatorial optimization problems using continuous systems without requiring conversion to binary states. Explores whether continuous spins need to converge to binary values at all.

[Limits of CMOS and Prospects for Adiabatic/Reversible CMOS](https://www.sandia.gov/app/uploads/sites/210/2023/11/Comet23-slides_SAND.pdf)
- (2023) Michael P Frank from Vaire Computing.

[A 1,968-node coupled ring oscillator circuit for combinatorial optimization problem solving](http://www.ee.umn.edu/groups/VLSIresearch/papers/2022/NatureElectronics22_Ising.pdf)
- (2024)

[A Probabilistic Compute Fabric Based on Coupled Ring Oscillators for Solving Combinatorial Optimization Problems](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9377463)
- (2021)

[Quantum Boltzmann machine learning of ground-state energies](https://arxiv.org/pdf/2410.12935)
- (2024) Develops hybrid quantum-classical algorithm using quantum Boltzmann machines to estimate ground-state energies proving it converges to ε-approximate stationary point with polynomial sample complexity

[A Versatile & Adjustable 400 Node CMOS Oscillator Based Ising Machine to Investigate and Optimize the Internal Computing Principle](https://ieeexplore.ieee.org/document/9908118)
- (2022)

[A 1,968-node coupled ring oscillator circuit for combinatorial optimization problem solving](https://www.nature.com/articles/s41928-022-00749-3)
- (2022) Presents 1,968-node King's graph ring oscillator array with five coupling strength levels achieving up to 95% accuracy for randomly generated combinatorial optimization problems consuming 0.042W average power

[Experimental investigation of the dynamics of coupled oscillators as Ising machines](https://ieeexplore.ieee.org/document/9598867)
- (2021)

[A Novel Oscillator Ising Machine Coupling Scheme for High-Quality Optimization](https://link.springer.com/chapter/10.1007/978-3-031-63742-1_15)
- (2024) The sampling coupler injects a current that depends on the phase diﬀerence between interacting oscillators. Proves analytically that using sampling couplers leads to idealized OIMs, abstracting away the waveforms and innate phase sensitivities of the oscillators.

[Self-contained relaxation-based dynamical Ising machines](https://arxiv.org/pdf/2305.06414)
- (2024) Formulates the V2 model

[On the sample complexity of quantum Boltzmann machine learning](https://www.nature.com/articles/s42005-024-01763-x)
- (2024)

[Design of a 10GHz Clock Distribution Network Using Coupled Standing-Wave Oscillators](https://cecs.uci.edu/~papers/compendium94-03/papers/2003/dac03/pdffiles/40_1.pdf)
- (2003)

[Ising Machines: Theory and Practice](https://www2.eecs.berkeley.edu/Pubs/TechRpts/2023/EECS-2023-138.pdf)
- (2023) Uses cross-bar array for trucated SVD of coupling matrix. Gives novel scheme for positive/negative weights and an MU-MIMO application example based on MATLAB ```scatteringchannelmtx```.

[Power-efficient combinatorial optimization using intrinsic noise in memristor Hopfield neural networks](https://link-springer-com.ezproxy.lib.purdue.edu/content/pdf/10.1038/s41928-020-0436-6)
- (2020)

[A 2×30k-Spin Multichip Scalable Annealing Processor Based on a Processing-In-Memory Approach for Solving Large-Scale Combinatorial Optimization Problems](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8662517)
- (2019)

[A 144Kb Annealing System Composed of 9×16Kb Annealing Processor Chips with Scalable Chip-to-Chip Connections for Large-Scale Combinatorial Optimization Problems](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9365748)
- (2021)

[The Unbearable Slowness of Being: Why do we live at 10 bits/s?](https://arxiv.org/pdf/2408.10234)
- (2024) Investigates fundamental paradox of why human behavior operates at only ~10 bits/s despite sensory systems processing ~10^9 bits/s proposing brain's inner and outer processing modes may explain this dramatic bottleneck

[Frequency tunable CMOS ring oscillator-based Ising machine](https://onlinelibrary.wiley.com/doi/abs/10.1002/cta.4256)
- (2024) Proposes generalized algorithm for monitoring the states of the oscillator network

[Stocastic Simulated Quantum Annealing for Fast Solution of Combinatorial Optimization Problems](https://arxiv.org/pdf/2302.12454)
- (2023) Presents stochastic simulated quantum annealing classical computing method that simulates quantum annealing using multiple replicas of spins achieving dramatically faster convergence speeds and larger problem scalability

[See Through Walls with Wi-Fi!](https://people.csail.mit.edu/fadel/papers/wivi-paper.pdf)
- (2013)

[A Study of Phase Noise in Colpitts and LC-Tank CMOS Oscillators](https://ieeexplore.ieee.org/document/1425718)
- (2005)

[Hyperchaos in coupled Colpitts oscillators](https://www.sciencedirect.com/science/article/abs/pii/S0960077902003739)
- (2003)

[A 350uW 2GHz FBAR transformer coupled Colpitts oscillator with close-in phase noise reduction](https://ieeexplore.ieee.org/abstract/document/7993636)
- (2017)

[Complex Dynamics and Synchronization in a System of Magnetically Coupled Colpitts Oscillators](https://onlinelibrary.wiley.com/doi/10.1155/2017/5483956)
- (2017)

[A Noise-Shifting Differential Colpitts VCO](https://chic.caltech.edu/wp-content/uploads/2013/05/NoiseShifting_JSSC.pdf)
- (2002)

[Phase Drift in Networks of Coupled Colpitts Oscillators](https://www.researchgate.net/publication/350550739_Phase_Drift_in_Networks_of_Coupled_Colpitts_Oscillators)
- (2021)

[Studies on the Dynamics of two Mutually Coupled Colpitts Oscillators](https://ijritcc.org/index.php/ijritcc/article/view/1654/1654)
- (2018)

[An Efficient Analysis of Amplitude and Phase Dynamics in Networked MEMS-Colpitts Oscillators](https://asmedigitalcollection.asme.org/computationalnonlinear/article-abstract/20/1/011002/1207163/An-Efficient-Analysis-of-Amplitude-and-Phase?redirectedFrom=PDF)
- (2025)

[Simulation and implementation of improved chaotic Colpitts circuit for UWB communications](https://ieeexplore.ieee.org/document/5670661)
- (2010)

[A Memristor-Based Colpitts Oscillator Circuit](https://www.mdpi.com/2227-7390/10/24/4820)
- (2022)

[Constructive Proof of Global Lyapunov Function as Potential Function](https://arxiv.org/pdf/1012.2721)
- (2014) Establishes mathematical equivalence between Lyapunov functions from control engineering and potential functions from physics suggesting new approaches to constructing Lyapunov functions by leveraging established physics methods.

[Ising Machine Based on Coupled Spin Torque Oscillators](https://mitcommlabmit.edu/eecs/wp-content/uploads/sites/6/2017/11/Brooke-McGoldrick-thesis-proposal-annotated.pdf)
- (2020)

[Replacing Digital Potentiometers with Precision DACs](https://www.ti.com/lit/ab/slaa906/slaa906.pdf)
- (2019)

[Emulating the coherent Ising machine with a mean-field algorithm](https://arxiv.org/pdf/1806.08422)
- (2018) Demonstrates that classical mean-field algorithm can effectively replicate coherent Ising machine performance achieving comparable results while running roughly 20 times faster in absolute terms