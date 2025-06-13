# Introduction to Verilog RTL Design & Synthesis

Welcome to **Day 1** of the RTL Workshop!  
Today, you'll embark on your journey into digital design by learning Verilog, open-source simulation with **Icarus Verilog (iverilog)**, and the basics of logic synthesis using **Yosys**. This guide will walk you through practical labs, essential concepts, and insightful explanations to help you build a strong foundation in RTL design.

---

##  Table of Contents

1. [Understanding Simulator, Design, and Testbench](#1-Understanding-Simulator-Design-and-Testbench)
2. [Getting Started with Icarus Verilog (iverilog)](#2-getting-started-with-Icarus-verilog-(iverilog))
3. [Lab: Loading design to iverilog](#3-lab-Loading-design-to-iverilog)

## 1. Understanding Simulator, Design, and Testbench
### Simulator
A simulator is a software-based tool used to evaluate the behavior of a digital circuit. It allows you to apply input signals and observe the resulting outputs, helping to verify the logic before it’s implemented on hardware.

### Design
The design refers to the Verilog source code that describes the logic and functionality of the digital system you are building.

### Testbench
A testbench is a simulation wrapper that drives input signals to the design and monitors the outputs. It acts as a virtual testing environment to validate the behavior of your design under various conditions.

<div align="center">
  <img src="https://github.com/user-attachments/assets/93927b96-df80-4da5-b801-284fc2cc6757" alt="Design & Testbench Overview" width="70%">
</div>

## 2. Getting Started with Icarus Verilog (iverilog)
- iverilog is an open-source Verilog simulation tool. Below is a typical workflow:

- Write your design and testbench in Verilog.

- Use iverilog to compile both files into a simulation executable.

- Run the executable to simulate your design. During this process, a .vcd (Value Change Dump) file is generated.

- Open the .vcd file in GTKWave, a waveform viewer, to analyze signal transitions and verify the logic visually.
  
<div align="center">
  <img src="https://github.com/user-attachments/assets/3ca190fb-cfa4-4abb-b9e1-0151b3c4bdba" alt="iverilog Simulation Flow" width="70%">
</div>

## Loading design to iverilog:
Eg : good_mux.v tb_good_mux.v

### Step 1:
> iverilog design name.v testbench-associated.v
eg: > iverilog good_mux.v tb_good_mux.v
- A file will be generated:
a.out (file generated)

### Step 2 : Execute a.out
> ./a.out
- A Vcd file will be generated.
> For this example:
tb_good_mux.vcd will be generated
### Step 3: Load it to simulator
> gtkwave tb_good_mux.vcd
- View the waveform to check then input and output of the design.

<div align="center">
  <img src="https://github.com/user-attachments/assets/701e8189-3101-4a82-8134-e799521b9a8b" alt="GTKWave Example" width="70%">
</div>



