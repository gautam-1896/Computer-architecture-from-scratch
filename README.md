# 🖥️ Computer Architecture From Scratch
### From a Single Transistor to a Fully Working 8-bit Processor Simulator

> **Learn how a computer really works by building one from the ground up.**

This project is a complete educational journey through computer architecture, starting from the fundamental building block—the transistor—and gradually constructing a fully functional 8-bit processor simulator.

Unlike many CPU simulators that begin with logic gates or assembly language, this project starts at the lowest practical level and explains every layer of abstraction until a complete CPU is running machine code.

The goal is not only to build an emulator, but to understand **why every component exists and how modern computers evolved from simple electronic switches.**

---

# Project Goals

- Build every major computer component from scratch
- Understand digital electronics and logic design
- Learn how CPUs actually execute instructions
- Design a complete 8-bit Instruction Set Architecture (ISA)
- Build a programmable processor simulator
- Write assembly programs for the CPU
- Create debugging and visualization tools
- Produce educational documentation suitable for beginners

---

# Learning Roadmap

The project progresses layer by layer.

```
Transistor
      │
      ▼
Logic Gates
      │
      ▼
Boolean Algebra
      │
      ▼
Combinational Circuits
      │
      ▼
Sequential Circuits
      │
      ▼
  Memory
      │
      ▼
 Registers
      │
      ▼
    ALU
      │
      ▼
 Control Unit
      │
      ▼
  Datapath
      │
      ▼
 Instruction Set
      │
      ▼
  Assembler
      │
      ▼
     CPU
      │
      ▼
   Computer
```

---

# Project Features

## Electronics Fundamentals

- Transistor simulation
- MOSFET basics
- Digital voltage levels
- Switching behavior
- Truth tables

---

## Logic Gates

- NOT
- Buffer
- AND
- OR
- XOR
- NAND
- NOR
- XNOR

Each gate includes

- Theory
- Circuit explanation
- Truth table
- Python implementation
- Unit tests

---

## Combinational Logic

- Half Adder
- Full Adder
- Ripple Carry Adder
- Carry Lookahead Concepts
- Multiplexer
- Demultiplexer
- Encoder
- Decoder
- Comparator
- Barrel Shifter

---

## Sequential Logic

- SR Latch
- D Latch
- D Flip-Flop
- JK Flip-Flop
- T Flip-Flop
- Clock simulation

---

## Registers

- 1-bit register
- 8-bit register
- Register file
- Program Counter
- Instruction Register
- Memory Address Register
- Memory Data Register
- Status Register

---

## Memory

- RAM simulation
- ROM simulation
- EEPROM concepts
- Address decoding
- Read/Write cycles

---

## Arithmetic Logic Unit (ALU)

Operations include

- ADD
- SUB
- INC
- DEC
- AND
- OR
- XOR
- NOT
- Shift Left
- Shift Right
- Rotate Left
- Rotate Right
- Compare

Status flags

- Zero
- Carry
- Overflow
- Negative

---

## Bus Architecture

- Address Bus
- Data Bus
- Control Bus

Bus arbitration concepts

---

## Instruction Set Architecture (ISA)

A custom-designed 8-bit ISA including

### Data Movement

- MOV
- LOAD
- STORE
- PUSH
- POP

### Arithmetic

- ADD
- SUB
- MUL (optional)
- DIV (optional)

### Logic

- AND
- OR
- XOR
- NOT

### Shift Operations

- SHL
- SHR
- ROL
- ROR

### Control Flow

- JMP
- JZ
- JNZ
- JC
- CALL
- RET

### Miscellaneous

- NOP
- HALT

---

## CPU Components

- Fetch Unit
- Decode Unit
- Execute Unit
- Control Unit
- ALU
- Register File
- Memory Interface
- Clock

---

## Instruction Cycle

```
Fetch
   │
   ▼
Decode
   │
   ▼
Execute
   │
   ▼
Memory Access
   │
   ▼
Write Back
```

---

## Assembler

Features

- Labels
- Variables
- Constants
- Comments
- Error reporting
- Binary generation

Example

```asm
START:
    LOAD R0, 10
    LOAD R1, 20
    ADD R0, R1
    STORE R0, RESULT
    HALT

RESULT:
    DB 0
```

---

## Machine Code Execution

The simulator can

- Load binary programs
- Execute instructions cycle-by-cycle
- Run continuously
- Pause execution
- Step through instructions
- Reset CPU

---

## Debugger

Features include

- Register view
- Memory viewer
- Stack viewer
- Flag viewer
- Breakpoints
- Instruction trace
- Cycle counter

---

## Visualization

Interactive visualizations for

- Logic gates
- ALU
- Registers
- Datapath
- Control signals
- Memory
- CPU execution

---

# Planned Folder Structure

```
computer-architecture-from-scratch/

│
├── docs/
│
├── src/
│   ├── transistor/
│   ├── logic_gates/
│   ├── combinational/
│   ├── sequential/
│   ├── registers/
│   ├── memory/
│   ├── alu/
│   ├── buses/
│   ├── control_unit/
│   ├── datapath/
│   ├── isa/
│   ├── assembler/
│   ├── cpu/
│   ├── debugger/
│   ├── simulator/
│   └── visualization/
│
├── examples/
│
├── tests/
│
├── assets/
│
├── README.md
├── LICENSE
└── requirements.txt
```

---

# Technologies

- Python 3.12+
- Object-Oriented Design
- Digital Logic Simulation
- Computer Architecture
- Data Structures
- Algorithms
- Optional GUI (Tkinter / PyQt / Pygame)

---

# Future Enhancements

- Pipeline simulation
- Cache memory
- Interrupts
- DMA
- UART simulation
- VGA output
- Keyboard input
- Disk controller
- Microcode engine
- Microprogrammed control unit
- RISC architecture
- CISC architecture
- 16-bit CPU
- 32-bit CPU
- FPGA implementation
- Verilog version
- HDL generation

---

# Educational Objectives

After completing this project, you should understand:

- How transistors implement logic gates
- How logic gates form arithmetic circuits
- How memory stores information
- How registers communicate over buses
- How an ALU performs calculations
- How instructions are decoded
- How a CPU executes programs
- How assembly language maps to machine code
- How an entire computer is built from simple electronic components

---

# Who Is This Project For?

- Computer Science students
- Electronics students
- Embedded systems developers
- FPGA enthusiasts
- Operating Systems learners
- Reverse engineers
- Low-level programmers
- Anyone curious about how computers work

No prior knowledge of computer architecture is required. The project is designed to build understanding from the ground up.

---

# Project Status

🚧 **Work in Progress**

The project is currently under active development. Each module will be implemented, documented, tested, and accompanied by examples before moving on to the next stage.

---

# Contributing

Contributions are welcome!

You can help by:

- Fixing bugs
- Improving documentation
- Adding educational diagrams
- Optimizing simulations
- Writing tests
- Suggesting new features
- Reviewing pull requests

Please open an issue before making major changes.

---

# License

This project is released under the MIT License.

---

# Acknowledgements

Inspired by classic educational projects and books on computer architecture, digital logic, and processor design, with the goal of making these concepts accessible through hands-on implementation.

---

# Star the Project ⭐

If this project helps you understand how computers work, consider giving it a ⭐ on GitHub. It helps others discover the project and motivates future development.

> **"The best way to understand a computer is to build one."**
