# Datapath

> *"The Control Unit decides **what** should happen. The Datapath is **where** it happens."*

---

# Introduction

In the previous chapter, we learned about the **Control Unit (CU)**, which coordinates every operation inside the CPU by generating control signals.

However, control signals alone cannot process data.

The CPU also needs a system that can:

- Move data between registers.
- Send operands to the ALU.
- Receive results from the ALU.
- Read data from memory.
- Write data back to memory.

This system is called the **Datapath**.

The datapath is the collection of hardware components and connections that move and process data inside the CPU. It works together with the Control Unit to execute every machine instruction.

Without a datapath, the CPU would know **what** to do, but it would have no way to move or process data.

---

# Learning Objectives

After completing this lesson, you will be able to:

- Define a datapath.
- Understand the components of a datapath.
- Learn how data flows inside a CPU.
- Understand the role of buses and multiplexers.
- Follow data movement during instruction execution.
- Distinguish between the Control Unit and the datapath.
- Prepare for learning about the Instruction Set Architecture (ISA).

---

# Prerequisite Knowledge

Before reading this lesson, you should understand:

- Sequential Circuits
- Registers
- Memory
- Arithmetic Logic Unit (ALU)
- Control Unit
- Fetch–Decode–Execute Cycle

---

# What Is a Datapath?

A **datapath** is the collection of hardware components that **move, store, and process data** inside the CPU.

It includes:

- Registers
- ALU
- Buses
- Multiplexers (MUXes)
- Program Counter (PC)
- Instruction Register (IR)
- Memory interface
- Other supporting hardware

The datapath carries the actual data, while the Control Unit controls how the datapath operates.

---

# Why Is the Datapath Important?

Imagine a factory.

- The **manager** decides what should be built.
- Workers move materials between machines.
- Machines process the materials.
- Conveyor belts transport finished products.

In this analogy:

- **Control Unit** → Factory manager
- **Registers** → Storage shelves
- **ALU** → Processing machine
- **Buses** → Conveyor belts
- **Datapath** → Entire production system

Without the datapath, nothing could move or be processed.

---

# Main Components of a Datapath

A typical datapath contains:

- Registers
- ALU
- Buses
- Multiplexers
- Program Counter
- Instruction Register
- Memory Interface
- Control Signals (from the Control Unit)

Each component has a specific role.

---

# Registers

Registers provide temporary storage for data.

Example:

```text
R1 = 12

R2 = 8
```

The ALU receives operands directly from these registers.

Registers are the fastest storage locations in the CPU.

---

# Arithmetic Logic Unit (ALU)

The ALU performs:

- Addition
- Subtraction
- AND
- OR
- XOR
- Comparisons
- Shift operations

The datapath delivers operands to the ALU and returns the result to a destination register.

---

# Buses

A **bus** is a collection of electrical wires that transfers information between hardware components.

Instead of creating a separate wire between every pair of components, many devices share common buses.

```text
Register A
      │
      │
====== BUS ======
      │
      ▼
     ALU
```

Buses make CPU design simpler and more efficient.

---

# Types of Buses

Three common buses are:

| Bus | Purpose |
|------|---------|
| Data Bus | Transfers data |
| Address Bus | Transfers memory addresses |
| Control Bus | Transfers control signals |

Each bus carries a different type of information.

---

# Data Bus

The **Data Bus** transfers actual data.

Example:

```text
RAM

↓

10101100

↓

CPU
```

The data bus is typically bidirectional, allowing data to move both to and from memory.

---

# Address Bus

The **Address Bus** specifies which memory location the CPU wants to access.

Example:

```text
Address

10010000

↓

RAM
```

The address bus selects *where* to read or write.

---

# Control Bus

The **Control Bus** carries signals such as:

- Read
- Write
- Clock
- Interrupt
- Reset

These signals coordinate communication between the CPU and other hardware.

---

# Multiplexers (MUX)

A **Multiplexer (MUX)** is a digital circuit that selects one of several inputs and forwards it to a single output.

Think of it as a railway switch.

```text
Input A ──┐
          │
Input B ──┼──► MUX ───► Output
          │
Input C ──┘
```

The Control Unit decides which input the MUX selects.

Multiplexers reduce the number of wires needed inside the CPU and allow different data sources to share hardware.

---

# Program Counter (PC)

The Program Counter stores the address of the next instruction.

The datapath transfers this address to memory during the **fetch** stage.

```text
PC

↓

Memory

↓

Instruction
```

---

# Instruction Register (IR)

The Instruction Register stores the current instruction after it has been fetched from memory.

The Control Unit reads the instruction from the IR during the decode stage.

---

# Memory Interface

The datapath connects the CPU to memory.

Typical communication includes:

```text
CPU

↓

Address

↓

Memory

↓

Data

↓

CPU
```

This interface allows the processor to read instructions and access program data.

---

# Data Flow in the Datapath

The datapath continuously moves information between components.

A simplified example is:

```text
Registers

↓

ALU

↓

Registers

↓

Memory

↓

Registers
```

This movement occurs for nearly every instruction executed by the CPU.

---

# Example: ADD Instruction

Consider the instruction:

```text
ADD R1, R2
```

The datapath performs these steps:

1. Read the value from **R1**.
2. Read the value from **R2**.
3. Send both values to the ALU.
4. Perform the addition.
5. Store the result back into a destination register.
6. Update the status flags.

```text
R1 ──┐
      │
      ▼
     ALU
      ▲
      │
R2 ───┘
      │
      ▼
 Result
      │
      ▼
 Register
```

---

# Example: LOAD Instruction

Suppose the CPU executes:

```text
LOAD R1, [1000]
```

The datapath performs:

```text
Program Counter

↓

Instruction Memory

↓

Instruction Register

↓

Address = 1000

↓

RAM

↓

Data

↓

Register R1
```

The data travels through the datapath from memory to the register.

---

# Example: STORE Instruction

Suppose the instruction is:

```text
STORE R1, [1000]
```

The datapath performs:

```text
Register R1

↓

Data Bus

↓

Memory

↓

Address 1000
```

The value stored in R1 is written into memory.

---

# Datapath During the Fetch–Decode–Execute Cycle

The datapath participates in every stage.

### Fetch

```text
PC

↓

Memory

↓

Instruction Register
```

### Decode

```text
Instruction Register

↓

Control Unit
```

### Execute

```text
Registers

↓

ALU

↓

Registers
```

The Control Unit and datapath work together throughout the cycle.

---

# Datapath vs Control Unit

| Feature | Datapath | Control Unit |
|----------|----------|--------------|
| Purpose | Moves and processes data | Controls operations |
| Includes | ALU, Registers, Buses, MUXes | Instruction decoder and control logic |
| Handles | Data | Control signals |
| Performs Calculations | Yes (through the ALU) | No |
| Stores Temporary Data | Yes (through registers) | No |

Together, they form the functional core of the CPU.

---

# Single-Cycle and Multi-Cycle Datapaths

CPU designers organize datapaths in different ways.

### Single-Cycle Datapath

- Each instruction completes in one clock cycle.
- Simpler design.
- The clock period must be long enough for the slowest instruction.

### Multi-Cycle Datapath

- Instructions are divided into several stages.
- Different instructions may require different numbers of clock cycles.
- More efficient use of hardware.

Modern processors often use even more advanced techniques such as **pipelining**, which will be studied later.

---

# Real-World Example

Imagine delivering a package.

- **Warehouse** → Memory
- **Delivery Vehicle** → Bus
- **Sorting Center** → Registers
- **Processing Machine** → ALU
- **Dispatcher** → Control Unit
- **Entire Delivery Network** → Datapath

The dispatcher gives instructions, while the delivery network moves and processes the packages.

---

# Real-World Applications

Every modern processor contains a datapath, including:

- Desktop CPUs
- Laptop CPUs
- Smartphone processors
- Microcontrollers
- GPUs
- AI processors
- Automotive controllers
- Industrial control systems
- Networking equipment

Whether the processor is simple or highly advanced, it must have a datapath to move and process information.

---

# Common Misconceptions

### ❌ The datapath is a single hardware component.

✅ The datapath is a collection of interconnected hardware components.

---

### ❌ The Control Unit is part of the datapath.

✅ The Control Unit works closely with the datapath but is usually treated as a separate functional unit that controls it.

---

### ❌ Buses only transfer data.

✅ Different buses carry data, addresses, and control signals.

---

### ❌ The ALU can access memory directly.

✅ The datapath moves data between memory, registers, and the ALU. The ALU typically operates on values already loaded into registers.

---

# Summary

The datapath is the hardware system that moves and processes information inside the CPU.

It includes registers, the ALU, buses, multiplexers, and the memory interface. The Control Unit coordinates these components by generating control signals.

Together, the datapath and the Control Unit enable the CPU to fetch instructions, execute operations, and store results efficiently.

---

# Key Takeaways

- The datapath moves and processes data inside the CPU.
- It includes registers, the ALU, buses, multiplexers, and memory interfaces.
- The Control Unit controls the datapath using control signals.
- Buses transfer data, addresses, and control information.
- Multiplexers select one input from multiple sources.
- The datapath is active during every instruction execution.
- Modern CPUs may use single-cycle, multi-cycle, or pipelined datapaths.

---

# Review Questions

1. What is a datapath?
2. Why is the datapath important?
3. Which components make up a datapath?
4. What is the purpose of a bus?
5. What are the three main types of buses?
6. What is the function of a multiplexer?
7. How does the datapath help execute an ADD instruction?
8. What is the difference between the datapath and the Control Unit?
9. What is the role of the Program Counter in the datapath?
10. What is the difference between a single-cycle and a multi-cycle datapath?

---

# Mini Quiz

### 1. What is the primary purpose of the datapath?

A. Display graphics

B. Move and process data

C. Store files permanently

D. Manage network traffic

**Answer:** B

---

### 2. Which component performs arithmetic operations within the datapath?

A. Program Counter

B. ALU

C. Cache

D. ROM

**Answer:** B

---

### 3. Which bus carries memory addresses?

A. Data Bus

B. Address Bus

C. Control Bus

D. System Bus

**Answer:** B

---

### 4. What is the purpose of a multiplexer (MUX)?

A. Increase memory size

B. Select one input from multiple inputs

C. Store instructions

D. Generate clock signals

**Answer:** B

---

### 5. Which CPU component controls the datapath?

A. ALU

B. RAM

C. Control Unit

D. SSD

**Answer:** C

---

# Further Reading

So far, we have explored **how the CPU is built** and **how data moves inside it**.

However, software must communicate with the CPU using a well-defined language that specifies available instructions, registers, memory addressing methods, and data formats.

This interface is called the **Instruction Set Architecture (ISA)**.

---

# What's Next?

Now that we understand how the CPU physically moves and processes data, the next step is to learn **how software communicates with the hardware**.

In the next chapter, **Instruction Set Architecture (ISA)**, we will explore **machine instructions, instruction formats, opcodes, operands, addressing modes, and how programmers and compilers use the ISA to control the processor**.


➡️ **Next:** [17 Instruction Set Architecture](17_Instruction Set Architecture.md)