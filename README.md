# RISC_V_32_BIT_AT
# Single-Cycle MIPS Processor in Verilog

This repository contains a complete implementation of a Single-Cycle MIPS Processor using Verilog HDL. The design follows the fundamental principles of the MIPS architecture, where each instruction is executed in a single clock cycle. The processor supports basic R-type and I-type instructions and is structured in a modular way for easy understanding, testing, and extension.

## Project Description

A single-cycle processor executes all steps of the instruction cycle—fetch, decode, execute, memory access, and write-back—within one clock cycle. This project includes all core components required for a functional single-cycle MIPS processor, built and tested in Verilog.

## Major Components

### Program Counter (PC)
- Maintains the address of the current instruction.
- Increments by 4 on each cycle or jumps in case of a branch instruction.

### Instruction Memory
- Stores the 32-bit instructions and provides them based on the current PC value.

### Control Unit
- Generates control signals by decoding the opcode.
- Controls data paths, ALU behavior, memory access, and register operations.

### Register File
- Contains 32 general-purpose registers.
- Supports two simultaneous reads and one write operation per cycle.

### Immediate Generator
- Extracts and sign-extends immediate values from instructions (for I-type and branch operations).

### ALU and ALU Control
- Performs arithmetic and logical operations such as add, subtract, AND, OR, and set-on-less-than.
- ALU Control interprets function codes and control signals to select the appropriate operation.

### Data Memory
- Supports reading and writing for load (`lw`) and store (`sw`) instructions.

### Multiplexers
- Used to select between immediate values and register data, ALU result or memory output, and PC+4 or branch target.

### Adders and Shifters
- Used to calculate PC+4 and branch target addresses.

---

## Supported Instructions

### R-Type Instructions
- add, sub, and, or, slt

### I-Type Instructions
- lw, sw, beq, addi

Additional instructions can be supported with minor updates to the control logic and ALU.

## Simulation and Testing

To run the simulation:

1. Compile the Verilog files using any Verilog simulator (such as Icarus Verilog).
2. Run the testbench to verify functionality.
3. Optionally, view waveform outputs using GTKWave for debugging and visualization.

Example (using Icarus Verilog):


##Future Improvements
1.Support for J-type instructions (e.g., j, jal)
2.Implementation of pipelining for performance enhancement
3.Hazard detection and forwarding unit
4.Extended instruction support (e.g., ori, lui, bne)

##License
This project is open-source and is licensed under the MIT License.

##Credits
This project was created as part of a study on computer architecture and digital design. It is inspired by the MIPS architecture described in standard textbooks such as Computer Organization and Design by Patterson and Hennessy.


