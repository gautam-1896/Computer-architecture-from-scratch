# Instruction Set Architecture (ISA)

> *"Hardware provides the power, but the Instruction Set Architecture provides the language that software uses to control it."*

---

# Introduction

In the previous chapter, we learned how the **datapath** moves data between registers, memory, and the ALU while the **Control Unit** coordinates every operation.

But an important question remains:

> **How does a programmer tell the CPU what to do?**

The answer is through the **Instruction Set Architecture (ISA).**

The ISA is the **interface between software and hardware**.

When you write a program in C, C++, Java, Rust, or Python, it is eventually translated into machine instructions that follow a particular ISA.

The ISA defines:

- What instructions the CPU understands.
- How data is stored.
- How registers are used.
- How memory is accessed.
- How programs communicate with the processor.

Every processor family has an ISA.

For example:

- x86-64
- ARM
- RISC-V
- MIPS

Although processors may have different internal designs, they can run the same software if they implement the same ISA.

---

# Learning Objectives

After completing this lesson, you will be able to:

- Define an Instruction Set Architecture.
- Understand why an ISA is important.
- Learn the components of an ISA.
- Understand instructions, opcodes, and operands.
- Learn common instruction categories.
- Understand addressing modes.
- Compare RISC and CISC architectures.
- Prepare for learning Assembly Language and the Assembler.

---

# Prerequisite Knowledge

Before reading this lesson, you should understand:

- Binary numbers
- Memory
- Registers
- ALU
- Control Unit
- Datapath

---

# What Is an Instruction Set Architecture?

An **Instruction Set Architecture (ISA)** is the specification that defines **how software communicates with a processor**.

It tells programmers and compilers:

- Which instructions are available.
- How instructions are encoded.
- How registers are organized.
- How memory is accessed.
- How interrupts and exceptions behave.

Think of the ISA as the **contract** between software and hardware.

---

# Why Is the ISA Important?

Imagine buying a DVD that only works in one type of DVD player.

Software would face the same problem without a standard instruction set.

The ISA allows software developers to write programs without knowing every detail of the processor's internal hardware.

As long as a CPU implements the same ISA, it can run the same machine code.

---

# ISA vs Microarchitecture

A common source of confusion is the difference between an ISA and a microarchitecture.

| ISA | Microarchitecture |
|------|-------------------|
| Defines what the CPU does | Defines how the CPU does it |
| Visible to programmers | Mostly hidden from programmers |
| Standard specification | Physical hardware implementation |
| Same ISA can have many implementations | Each CPU design is one implementation |

### Example

Two processors may both implement the **RISC-V ISA**.

One may be:

- Small and energy-efficient.
- Single-core.
- Used in embedded systems.

Another may be:

- Multi-core.
- Superscalar.
- Out-of-order.
- Designed for servers.

Although their internal designs differ greatly, both execute the same RISC-V machine instructions.

---

# What Is an Instruction?

An **instruction** is a command given to the CPU.

Examples:

```text
ADD R1, R2

LOAD R1, [1000]

STORE R2, [2000]

JUMP LOOP
```

Each instruction tells the processor to perform one specific task.

---

# Machine Instructions

Inside the computer, instructions are stored as binary numbers.

Example:

```text
ADD R1, R2

↓

10001011 00000010
```

The CPU reads these binary values during the **Fetch–Decode–Execute Cycle**.

---

# Opcode

Every instruction contains an **opcode**.

An **opcode (operation code)** specifies **what operation** the CPU should perform.

Examples:

| Opcode | Meaning |
|---------|----------|
| ADD | Addition |
| SUB | Subtraction |
| LOAD | Read from memory |
| STORE | Write to memory |
| AND | Bitwise AND |
| OR | Bitwise OR |
| JUMP | Branch to another instruction |

---

# Operand

An **operand** specifies the data used by an instruction.

Example:

```text
ADD R1, R2
```

Here:

- **ADD** → Opcode
- **R1** → Operand
- **R2** → Operand

Operands may refer to:

- Registers
- Memory locations
- Constant values (immediate values)

---

# Instruction Format

Every ISA defines how instructions are arranged in binary.

A simple instruction format might look like:

```text
┌────────┬──────────┬──────────┐
│ Opcode │ Operand1 │ Operand2 │
└────────┴──────────┴──────────┘
```

Different ISAs use different instruction formats.

Some use fixed-length instructions, while others allow variable-length instructions.

---

# Categories of Instructions

Most processors provide instructions in several categories.

---

## 1. Data Transfer Instructions

Move data between registers and memory.

Examples:

```text
LOAD

STORE

MOVE
```

---

## 2. Arithmetic Instructions

Perform mathematical calculations.

Examples:

```text
ADD

SUB

INC

DEC
```

---

## 3. Logical Instructions

Perform Boolean operations.

Examples:

```text
AND

OR

XOR

NOT
```

---

## 4. Shift and Rotate Instructions

Move bits left or right.

Examples:

```text
SHIFT LEFT

SHIFT RIGHT

ROTATE LEFT

ROTATE RIGHT
```

---

## 5. Comparison Instructions

Compare two values.

Example:

```text
CMP R1, R2
```

These instructions often update status flags without storing an arithmetic result.

---

## 6. Branch Instructions

Change the normal sequence of execution.

Examples:

```text
JUMP

CALL

RETURN

BEQ

BNE
```

Branch instructions make loops, conditions, and function calls possible.

---

# Addressing Modes

The CPU must know **where to find operands**.

Different methods are called **addressing modes**.

---

## Immediate Addressing

The value is included directly in the instruction.

Example:

```text
ADD R1, #5
```

The number **5** is part of the instruction itself.

---

## Register Addressing

Operands are stored in registers.

Example:

```text
ADD R1, R2
```

Both operands are inside CPU registers.

---

## Direct Addressing

The instruction specifies a memory address.

Example:

```text
LOAD R1, [1000]
```

The CPU reads data from memory address **1000**.

---

## Indirect Addressing

A register contains the memory address.

Example:

```text
LOAD R1, [R2]
```

Here, **R2** stores the address of the data.

---

# Example Instruction Execution

Suppose the instruction is:

```text
ADD R1, R2
```

The CPU performs:

```text
Fetch

↓

Decode

↓

Read R1

↓

Read R2

↓

ALU Adds Values

↓

Store Result

↓

Update Flags
```

This entire process follows the ISA specification.

---

# Fixed-Length vs Variable-Length Instructions

Different ISAs encode instructions differently.

| Fixed-Length | Variable-Length |
|---------------|-----------------|
| Every instruction has the same size | Instruction size can vary |
| Simpler decoding | More complex decoding |
| Often used by RISC processors | Common in x86 processors |

---

# RISC and CISC

The two major ISA design philosophies are:

- RISC
- CISC

---

## RISC (Reduced Instruction Set Computer)

Characteristics:

- Smaller instruction set.
- Simple instructions.
- Usually fixed-length instructions.
- Easier to pipeline.
- Often requires more instructions to complete a complex task.

Examples:

- RISC-V
- ARM (modern implementations primarily follow RISC principles)
- MIPS

---

## CISC (Complex Instruction Set Computer)

Characteristics:

- Larger instruction set.
- More complex instructions.
- Often variable-length instructions.
- A single instruction may perform several operations.

Example:

- x86-64

---

# RISC vs CISC

| Feature | RISC | CISC |
|----------|------|-------|
| Instruction Set | Smaller | Larger |
| Instruction Complexity | Simple | Complex |
| Instruction Length | Usually fixed | Often variable |
| Hardware Complexity | Lower | Higher |
| Code Size | Usually larger | Usually smaller |

Both approaches are successful and continue to evolve in modern processors.

---

# Popular Instruction Set Architectures

| ISA | Common Uses |
|------|-------------|
| x86-64 | Desktop and server computers |
| ARM | Smartphones, tablets, embedded systems |
| RISC-V | Education, research, embedded systems, growing commercial use |
| MIPS | Education, networking equipment, embedded systems |

Each ISA has strengths for different applications.

---

# How the ISA Fits into Computer Architecture

```text
High-Level Language
        │
        ▼
Compiler
        │
        ▼
Assembly Language
        │
        ▼
Assembler
        │
        ▼
Machine Code
        │
        ▼
Instruction Set Architecture
        │
        ▼
CPU
```

The ISA is the bridge between software and hardware.

---

# Real-World Example

Suppose a programmer writes:

```c
a = b + c;
```

A compiler might generate:

```text
LOAD R1, b

LOAD R2, c

ADD R1, R2

STORE R1, a
```

The CPU understands these instructions because they follow its ISA.

---

# Real-World Applications

Every processor uses an ISA, including:

- Desktop computers
- Laptops
- Smartphones
- Servers
- Embedded systems
- Automotive controllers
- Industrial automation
- Network devices
- Spacecraft
- Robotics

Software cannot run unless it is compatible with the processor's ISA.

---

# Common Misconceptions

### ❌ ISA and CPU are the same thing.

✅ The ISA is a specification. The CPU is a hardware implementation of that specification.

---

### ❌ All CPUs use the same ISA.

✅ Different processors implement different instruction set architectures.

---

### ❌ Programs written in C or Python are executed directly by the CPU.

✅ They are first translated into machine instructions that follow the processor's ISA.

---

### ❌ RISC is always faster than CISC.

✅ Performance depends on many factors, including microarchitecture, compiler quality, cache design, clock speed, and workload—not only the ISA.

---

# Summary

The **Instruction Set Architecture (ISA)** defines how software communicates with hardware.

It specifies:

- Instructions
- Registers
- Memory operations
- Instruction formats
- Addressing modes
- Program execution behavior

The ISA serves as the bridge between programs and the processor, allowing compilers, assemblers, operating systems, and application software to work with the hardware in a standardized way.

---

# Key Takeaways

- The ISA is the interface between software and hardware.
- Instructions are commands executed by the CPU.
- Every instruction contains an opcode and, in most cases, one or more operands.
- Different instruction categories perform different tasks.
- Addressing modes specify where operands are located.
- RISC and CISC are two major ISA design philosophies.
- Multiple CPUs can implement the same ISA using different internal designs.
- Programs must be translated into machine code that follows the processor's ISA.

---

# Review Questions

1. What is an Instruction Set Architecture?
2. Why is the ISA important?
3. What is the difference between an ISA and a microarchitecture?
4. What is an instruction?
5. What is an opcode?
6. What is an operand?
7. Name four categories of CPU instructions.
8. What are addressing modes?
9. Compare RISC and CISC architectures.
10. Why can different processors run the same software if they implement the same ISA?

---

# Mini Quiz

### 1. What does ISA stand for?

A. Integrated System Architecture

B. Instruction Set Architecture

C. Internal Storage Array

D. Intelligent System Adapter

**Answer:** B

---

### 2. What part of an instruction specifies the operation to perform?

A. Operand

B. Address

C. Opcode

D. Register

**Answer:** C

---

### 3. Which instruction category changes the flow of program execution?

A. Arithmetic

B. Logical

C. Branch

D. Shift

**Answer:** C

---

### 4. Which addressing mode stores the value directly inside the instruction?

A. Register Addressing

B. Immediate Addressing

C. Direct Addressing

D. Indirect Addressing

**Answer:** B

---

### 5. Which of the following is an example of a RISC ISA?

A. x86-64

B. RISC-V

C. 8051 Machine Code

D. BIOS

**Answer:** B

---

# Further Reading

Now that we understand the language understood by the CPU, the next step is to learn a human-readable representation of that language.

Instead of writing binary machine code directly, programmers often use **Assembly Language**, where short mnemonic names such as `ADD`, `LOAD`, and `JUMP` represent machine instructions.

---

# What's Next?

In the next chapter, **Assembler and Assembly Language**, we will explore how **assembly language is written, how an assembler converts it into machine code, labels, directives, symbols, and how simple assembly programs are created and executed**.


➡️ **Next:** [18 Assembler](18_Assembler.md)

This chapter will bridge the gap between **high-level programming languages** and the binary instructions executed by the CPU, completing our understanding of how software communicates with hardware.