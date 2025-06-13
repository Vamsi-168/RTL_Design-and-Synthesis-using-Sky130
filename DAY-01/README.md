# Introduction to Verilog RTL Design & Synthesis

Welcome to Day 1 of the RTL Design Workshop!

Today marks the beginning of your hands-on exploration into the world of digital logic design. You'll start by getting familiar with **Verilog**, dive into **open-source simulation** using **Icarus Verilog (iverilog)**, and take your first steps into **logic synthesis** using **Yosys**.

This session combines essential theory with practical labs to help you understand how real-world RTL design is done. By the end of the day, you’ll have built and simulated your first Verilog design, and synthesized it using a powerful open-source toolchain.

Let’s get started and lay a solid foundation for your RTL design skills!

---

##  DAY-01 Contents

1. [Understanding Simulator, Design, and Testbench](#1-Understanding-Simulator-,-Design-,-and-Testbench)
2. [Getting Started with Icarus Verilog (iverilog)](#2-getting-started-with-Icarus-verilog-(iverilog))
3. [Lab: Loading design to iverilog](#3-lab-Loading-design-to-iverilog)
4. [Yosys - Open Source Verilog Synthesis](#4-Yosys-Open_Source-Verilog-Synthesis)
5. [Synthesis Lab with Yosys](#5-synthesis-lab-with-yosys)

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

## 3. Loading design to iverilog:
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



## 4. Yosys - Open Source Verilog Synthesis

### 🛠️ What is Yosys?

Yosys is an open-source framework for Verilog RTL synthesis. It reads your Verilog design and maps it to a target technology, such as standard-cell libraries or FPGAs. It is widely used in academia, research, and open-source silicon projects.

---

### 📘 Key Features

- Supports most of **Verilog-2005** syntax
- Customizable with support for **technology mapping**
- Can target open-source cell libraries like **Sky130**, **iCE40**, etc.
- Integrates well with tools like **nextpnr**, **ABC**, and **GHDL**

---



## 5. Synthesis Lab with Yosys

Let’s synthesize the `good_mux` design using Yosys!

###  Step-by-Step Yosys Flow

1. **Start Yosys**
    ```shell
    yosys
    ```

2. **Read the liberty library**
    ```shell
    read_liberty -lib /address/to/your/sky130/file/sky130_fd_sc_hd__tt_025C_1v80.lib
    ```

3. **Read the Verilog code**
    ```shell
    read_verilog /home/vsduser/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files/good_mux.v
    ```

4. **Synthesize the design**
    ```shell
    synth -top good_mux
    ```

5. **Technology mapping**
    ```shell
    abc -liberty /address/to/your/sky130/file/sky130_fd_sc_hd__tt_025C_1v80.lib
    ```

6. **Visualize the gate-level netlist**
    ```shell
    show
    ```


