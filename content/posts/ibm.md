+++
title = 'MATLAB goes Quantum'
date = 2025-06-16T22:59:00-04:00
draft = false
+++

I'm the lead developer for MATLAB's quantum computing library. It supports building, simulating, and running gate-based quantum algorithms. It's very easy to run on IBM Quantum hardware
```MATLAB
c = quantumCircuit(hGate(1));
d = quantum.backend.QuantumDeviceIBM('ibm_fez');
job = run(c, d);
```
The quantum circuit is [compiled](https://arxiv.org/pdf/2308.07581) to [OpenQASM](https://arxiv.org/abs/2104.14722) and sent for execution. You can enable options like batch processing, or measurement error mitigation. There are of course other gates and more features too. Other gate-based devices available on AWS are also supported.

IBM hosts an annual quantum conference, and this posts reflects on my experience attending.

### 2024

This year was dubbed the Quantum Developer Conference because it was just for industry partners. The previous years had more marketing aspects. It took place at IBM Research in Yorktown Heights, NY. One key highlight was refactoring their entire runtime from Python to Rust, which was the main performance update for Qiskit 1.0. There were also plans to support more advanced features of OpenQASM 3.0. I also got a tour of their fabrication facility but no photos were allowed.

![](/ibm2024a.png)
![](/ibm2024b.png)

### 2023

This year was hosted at The Shed in Hudson Yards, NYC. The presentations were mostly marketing with some graduate research that felt too technical for a larger audience. They showcased MATLAB along with other quantum SDKs and tools. I gave a talk during a breakout session during the second day.

![](/ibm2023a.png)

### 2022

This was my first year attending. I met with Jay Gambetta and some others after the main presentation. They wanted us on stage next year to highlight MATLAB integration with their runtime service. During this time, the whole library was still internal.

![](/ibm2022a.png)