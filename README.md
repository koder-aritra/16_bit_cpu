# 16-Bit CPU Design Using Verilog


<img src="16_bit_cpu/layout.png" width="600" >  


## Overview

This project demonstrates the design and implementation of a 16-bit CPU using Verilog. The architecture consists of various components that work together to perform arithmetic, logical, and control operations. Below is a detailed breakdown of the approach, components, instruction set, and operational flow of the CPU.

---

## Approach

The design of the 16-bit CPU involved creating the following components, each serving a specific function in the overall architecture:

- **ALU (Arithmetic Logic Unit)**
- **Arithmetic Unit**
- **Logic Unit**
- **Data Memory**
- **Instruction Memory**
- **Program Counter (PC)**
- **Instruction Register**
- **Multiplexer (MUX)**
- **Controller**
- **CPU (Central Processing Unit)**

These components were individually designed and tested before integration into the complete CPU system.

---

## Instruction Set Architecture (ISA)

The CPU's instruction set determines its operation. The input to the Instruction Memory is a 16-bit instruction, processed by the Instruction Register. The instruction is divided into:

- **[15:12]**: OPCODE (Operation Code) - Defines the operation.
- **[11:0]**: Address or immediate data, depending on the instruction type.

The instruction set supports arithmetic, logical, and control operations, as defined by the OPCODE. Below is a breakdown of the instructions:

### Arithmetic Operations (Mode 0)

- `0000` - ADD
- `0001` - MULTIPLY
- `0010` - SUBTRACT
- `0011` - DIVIDE

### Data Load Operations

- `0100` - LOAD A (Load data into Register A)
- `0105` - LOAD B (Load data into Register B)
- `0110` - LOAD C (Load data into Register C)
- `0111` - JUMP (Jump to immediate address)

### Logical Operations (Mode 1)

- `1000` - AND
- `1001` - OR
- `1010` - NAND
- `1011` - NOR
- `1100` - NOT A
- `1101` - NOT B
- `1110` - XOR
- `1111` - XNOR

The instructions allow the CPU to perform arithmetic, logical, and control operations.

---

## Operational Flow

The CPU follows a state machine approach with three primary states:

1. **Reset State**:
   - Initializes addresses and instruction code to zero.
   - Control signals are reset to zero.
   
2. **Load State**:
   - Loads the Instruction Register with the address and OPCODE, preparing the CPU for execution.
   
3. **Execute State**:
   - Executes the required operation based on the instruction set. 
   - Performs arithmetic/logical operations, manages data movement, and controls program execution.

---

## Components Overview

### ALU (Arithmetic Logic Unit)
Handles all arithmetic and logical operations based on the provided OPCODE.

### Arithmetic Unit
Performs arithmetic functions such as addition, subtraction, multiplication, and division.

### Logic Unit
Performs logical operations like AND, OR, NOT, and XOR.

### Data Memory
Stores data used during program execution.

### Instruction Memory
Holds the instructions that the CPU will execute.

### Program Counter (PC)
Tracks the address of the next instruction to execute.

### Instruction Register
Holds the current instruction being processed by the CPU.

### Multiplexer (MUX)
Selects between different inputs based on control signals.

### Controller
Coordinates the operation of the CPU by managing the ALU, memory accesses, and instruction execution.

---

## Verilog Code

The full Verilog code for the 16-bit CPU design, including all components, is available in the project folder. The design has been tested to ensure correct functionality, with all operations following the defined instruction set.

---

## How to Run

1. Clone the repository.
2. Open the Verilog files in your preferred simulation environment (e.g., ModelSim, Vivado).
3. Compile and simulate the design using the provided testbenches.
4. Verify the output against expected results for various operations.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
