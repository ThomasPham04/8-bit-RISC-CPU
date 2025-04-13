# 8-bit RISC CPU Project

## Project Overview

This project involves the design and implementation of an 8-bit RISC (Reduced Instruction Set Computer) CPU, capable of performing basic operations. The CPU is designed to be minimalistic yet functional, emphasizing simplicity and efficiency. The project was completed as a team effort (team size: 5) during September 2024 as part of the Logic Design course (HK241).

### Objectives
- Design and implement major CPU components, including:
  - Program Counter (PC)
  - Address Multiplexer (MUX)
  - Arithmetic Logic Unit (ALU)
  - Controller
  - Memory
  - Registers (including Accumulator)
- Ensure the CPU can handle basic arithmetic and logic operations efficiently.
- Collaborate with team members to integrate components and ensure system functionality.

### Features
- **Instruction Set**: The CPU supports a custom instruction set with 3-bit opcodes and 5-bit operands, including:
  - `HLT`: Halt program execution.
  - `SKZ`: Skip next instruction if ALU result is zero.
  - `ADD`: Add memory value to Accumulator.
  - `AND`: Perform AND operation between Accumulator and memory value.
  - `XOR`: Perform XOR operation between Accumulator and memory value.
  - `LDA`: Load value from memory into Accumulator.
  - `STO`: Store Accumulator value into memory.
  - `JMP`: Unconditional jump to a specified address.
- **Program Counter (PC)**:
  - 5-bit counter with reset, jump, and skip functionality.
  - Synchronized with clock (posedge clk).
- **Address Mux**:
  - Selects between instruction address (from PC) and operand address (from instruction).
  - 5-bit address width, configurable via parameters.
- **ALU**:
  - Performs 8 operations on 8-bit operands.
  - Outputs 8-bit result and 1-bit `is_zero` flag (asynchronous).
- **Memory**:
  - 5-bit address, 8-bit data.
  - Single bidirectional data port (no simultaneous read/write).
- **Controller**:
  - Manages CPU control signals with at least 8 states.
  - Synchronized with clock (posedge clk).

### Repository Structure
- `docs/`: Contains project documentation, including block diagrams and flowcharts.
- `src/`: Source code (Verilog/VHDL) for CPU components.
  - `program_counter.v`: Program Counter implementation.
  - `address_mux.v`: Address Multiplexer implementation.
  - `alu.v`: Arithmetic Logic Unit implementation.
  - `controller.v`: Controller implementation.
  - `memory.v`: Memory implementation.
  - `register.v`: Register (Accumulator) implementation.
- `testbench/`: Testbenches for verifying CPU components.
- `README.md`: Project overview and documentation.
