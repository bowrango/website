+++
title = 'MATLAB goes Quantum'
date = 2025-06-16T22:59:00-04:00
draft = false
+++

I'm the lead developer for the MATLAB Quantum Computing Library. It supports building, simulating, and running gate-based quantum algorithms. It's very easy to run on IBM Quantum hardware
```MATLAB
c = quantumCircuit(hGate(1));
d = quantum.backend.QuantumDeviceIBM('ibm_fez');
job = run(c, d);
```
The quantum circuit is [compiled](https://arxiv.org/pdf/2308.07581) to [OpenQASM](https://arxiv.org/abs/2104.14722) and sent for execution. You can enable options like batch processing, or measurement error mitigation. There are more gates and features too, and additional gate-based devices available on AWS are also supported.

IBM hosts an annual quantum conference, and this posts reflects on my experience attending.

### 2024

This year was dubbed the Quantum Developer Conference because it was just for industry partners. The previous years had more marketing aspects. It took place at IBM Research in Yorktown Heights, NY. One key highlight was refactoring their entire runtime scheduler from Python to Rust, which was the main performance update for Qiskit 1.0. There were also plans to support more advanced features of OpenQASM 3.0. I also got a tour of their fabrication facility but no photos were allowed. The following two images are from IBM Research, where the most recent System Two was out for display.

![](/ibm2024a.png)
![](/ibm2024b.png)

### 2023

This year was hosted at The Shed in Hudson Yards, NYC. The presentations were mostly marketing with some graduate research that felt too technical for a larger audience. On the first day, they showcased MATLAB along with other quantum SDKs and tools. I worked on integrating QASMTrans into MATLAB to optimize the quantum circuits it sends to hardware.

![](/ibm2023a.png)

On the second day, I gave a talk demonstrating the MATLAB Quantum Computing Library and was featured on their website

![](/ibm-speakers-me.png)

### 2022

This was my first year attending. I met with Jay Gambetta and some others after the main presentation. They wanted us on stage next year to highlight the MATLAB integration with their Qiskit Runtime cloud service. During this time, the library wasn't released (it shipped with R2023a) and I was developing infrastructure to support hardware-agnostic code generation. I should've taken more pictures.

![](/ibm2022a.png)