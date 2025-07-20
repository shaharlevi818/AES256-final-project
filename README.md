**AES-256 Hardware/Software Co-Design on Xilinx MicroBlaze**
This repository contains the complete project files for a final university project exploring optimal hardware/software partitioning for the AES-256 encryption algorithm on an FPGA. The system is built around a Xilinx MicroBlaze soft-core processor on a Kintex-7 KC705 development board.

**Abstract**
This project presents a performance evaluation of multiple AES-256 encryption and decryption implementations. The core objective was to systematically analyze different hardware/software partitions to find the most efficient design. Efficiency was measured using the Area-Time Product (Clock Cycles * Area Utilization) as the primary optimization metric, balancing performance against resource cost.
Four distinct hardware accelerators were designed in Verilog and benchmarked against a baseline pure software implementation. 

**Key Features**
Algorithm: Implements the full AES-256 standard.
Functionality: Supports both Encryption and Decryption.
Architecture: Hardware/Software co-design using a MicroBlaze soft-core processor and a custom AXI4-Lite peripheral.
Systematic Analysis: Provides a detailed comparison of four different hardware acceleration strategies.
Comprehensive Benchmarking: Measures and analyzes performance (clock cycles), area utilization (LUTs), and power consumption.

**Hardware & Software Environment**
FPGA Board: Xilinx Kintex-7 KC705
Hardware Design Suite: Vivado 2021.1
Software Development Suite: Vitis SDK 2022.2
Processor: Xilinx MicroBlaze 32-bit RISC soft-core
Bus Interface: AXI4-Lite
System Clock: 100MHz

**Implementations Overview**
This project explores four distinct hardware acceleration strategies, plus a baseline software-only implementation.

Implementation 1: Full Hardware (Pipelined)
The entire AES algorithm, including Key Expansion and 14 unrolled rounds, is implemented in hardware. Designed for maximum throughput.

Implementation 2: Full Hardware (Iterative)
The entire AES algorithm is in hardware, but it uses a single, iterative round module. This design reduces area at the cost of latency.

Implementation 3: Partial Hardware (Rounds Only)
The computationally intensive KeyExpansion is moved to software (C code on MicroBlaze). The hardware accelerator only implements the AES round function.

Implementation 4: Minimal Hardware (No SubBytes)
Builds on Implementation #3 by also moving the SubBytes S-Box lookup to software, further reducing the hardware footprint.





This project was completed as a final requirement for the Faculty of Engineering at Tel Aviv University.
