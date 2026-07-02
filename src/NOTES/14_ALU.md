# Arithmetic Logic Unit (ALU)

> *"The ALU is the calculator of the CPU. Every addition, subtraction, comparison, and logical decision eventually passes through it."*

---

# Introduction

In the previous chapter, we learned about **registers**, which temporarily store the data and instructions that the CPU is currently using.

However, storing data alone is not enough.

A computer must also **process** that data.

For example, it must:

- Add two numbers
- Compare two values
- Perform logical operations
- Shift bits
- Calculate memory addresses

The component responsible for these operations is the **Arithmetic Logic Unit (ALU)**.

The ALU is one of the most important parts of every processor. It performs the mathematical and logical operations that allow computers to solve problems, execute programs, and make decisions.

---

# Learning Objectives

After completing this lesson, you will be able to:

- Define the Arithmetic Logic Unit (ALU).
- Understand where the ALU fits inside the CPU.
- Learn the arithmetic operations performed by the ALU.
- Learn the logical operations performed by the ALU.
- Understand status flags.
- Follow the flow of data through the ALU.
- Recognize how the ALU works with registers and the control unit.

---

# Prerequisite Knowledge

Before reading this lesson, you should understand:

- Binary numbers
- Boolean Algebra
- Logic gates
- Combinational circuits
- Registers

---

# What Is an ALU?

The **Arithmetic Logic Unit (ALU)** is the part of the CPU that performs calculations and logical decisions.

It receives data from registers, performs an operation, and stores the result back into a register.

A simplified view is:

```text
Register A ───┐
              │
              ▼
             ALU
              │
Register B ───┘
              │
              ▼
        Result Register
```

The ALU itself does **not** decide *which* operation to perform. It waits for instructions from the **Control Unit**, which tells it whether to add, subtract, compare, or perform another operation.

---

# Why Is the ALU Important?

Almost every program relies on the ALU.

Examples include:

- Calculating a bill.
- Comparing passwords.
- Sorting numbers.
- Processing images.
- Running video games.
- Executing artificial intelligence algorithms.

Without an ALU, a processor could store data but could never perform calculations.

---

# Main Functions of the ALU

The ALU performs two major categories of operations:

1. Arithmetic Operations
2. Logical Operations

---

# Arithmetic Operations

Arithmetic operations work with numerical values.

Common arithmetic operations include:

| Operation | Description |
|-----------|-------------|
| Addition | Adds two numbers |
| Subtraction | Subtracts one number from another |
| Increment | Adds 1 |
| Decrement | Subtracts 1 |
| Multiplication* | Multiplies numbers |
| Division* | Divides numbers |

\*Many modern CPUs perform multiplication and division using dedicated hardware or specialized execution units rather than the basic ALU.

### Example

```text
Register A = 25

Register B = 17

↓

ALU

↓

25 + 17

↓

42
```

---

# Logical Operations

Logical operations work with binary values.

Common logical operations include:

| Operation | Description |
|-----------|-------------|
| AND | Both bits must be 1 |
| OR | At least one bit is 1 |
| XOR | Bits are different |
| NOT | Inverts every bit |

### Example

```text
1010

AND

1100

=

1000
```

These operations are widely used in:

- Bit masking
- Data manipulation
- Cryptography
- Device control

---

# Bitwise Operations

The ALU operates on individual bits.

Suppose:

```text
A = 1101

B = 1011
```

### AND

```text
1101
1011
----
1001
```

### OR

```text
1101
1011
----
1111
```

### XOR

```text
1101
1011
----
0110
```

---

# Shift Operations

Many ALUs also support **bit shifting**.

### Left Shift

Moves every bit one position to the left.

```text
0011

↓

0110
```

This often multiplies an unsigned binary number by 2.

---

### Right Shift

Moves every bit one position to the right.

```text
1100

↓

0110
```

This often divides an unsigned binary number by 2 (discarding any remainder).

Different CPUs may implement logical and arithmetic right shifts differently.

---

# Comparison Operations

The ALU can compare two values.

For example:

```text
A = 25

B = 17
```

The ALU can determine:

- A > B
- A < B
- A = B

Programs use these comparisons to make decisions, such as executing an `if` statement or repeating a loop.

---

# Status Flags

After every operation, the ALU updates the **Status Register** (also called the **Flags Register**).

These flags describe the result of the operation.

Common flags include:

| Flag | Meaning |
|------|---------|
| Zero (Z) | Result is zero |
| Carry (C) | Carry generated during addition or borrow-related condition in subtraction (architecture-dependent) |
| Sign (S/N) | Result is negative (for signed arithmetic) |
| Overflow (V/O) | Signed arithmetic overflow occurred |

### Example

```text
5 - 5

↓

0

↓

Zero Flag = 1
```

Programs examine these flags to decide what to do next.

---

# Inputs and Outputs of the ALU

The ALU receives:

- Operand 1
- Operand 2
- Operation selection from the Control Unit

It produces:

- Result
- Status flags

```text
Register A ──┐
             │
Register B ──┼────► ALU
             │
Control Unit ┘
               │
               ▼
         Result + Flags
```

---

# How the ALU Works

Suppose the CPU executes:

```text
ADD R1, R2
```

The sequence is:

1. The Control Unit decodes the instruction.
2. The values in **R1** and **R2** are sent to the ALU.
3. The Control Unit selects the **ADD** operation.
4. The ALU performs the addition.
5. The result is stored back in a register.
6. The status flags are updated.

---

# Building an ALU

An ALU is not a single component.

It is built by combining many smaller circuits.

```text
Transistors
      │
      ▼
Logic Gates
      │
      ▼
Combinational Circuits
      │
      ▼
Adders
Comparators
Shifters
Logic Units
      │
      ▼
Arithmetic Logic Unit
```

The ALU is therefore a complex combinational circuit made from simpler building blocks.

---

# A Simple 4-Bit ALU Example

Suppose:

```text
A = 0101   (5)

B = 0011   (3)
```

If the selected operation is **ADD**:

```text
0101

+

0011

=

1000
```

The ALU outputs:

```text
Result = 1000

Carry = 0
```

If the selected operation is **AND**:

```text
0101

AND

0011

=

0001
```

Only the selected operation's result is sent to the output.

---

# ALU Inside the CPU

A simplified CPU organization is:

```text
          Instructions
                │
                ▼
         Control Unit
                │
      Operation Select
                │
                ▼
Registers ───► ALU ───► Registers
                │
                ▼
          Status Register
```

The Control Unit tells the ALU what to do, the registers supply the data, and the ALU performs the computation.

---

# Real-World Applications

The ALU is used in:

- Desktop CPUs
- Laptop CPUs
- Smartphone processors
- GPUs
- Microcontrollers
- Embedded systems
- Digital signal processors
- AI accelerators
- Robotics
- Network equipment

Every modern processor contains one or more ALUs.

---

# Common Misconceptions

### ❌ The ALU controls the CPU.

✅ The **Control Unit** controls the CPU. The ALU performs the operations it is instructed to execute.

---

### ❌ The ALU stores data permanently.

✅ The ALU processes data. Registers and memory store data.

---

### ❌ The ALU performs only addition.

✅ The ALU performs arithmetic, logical, comparison, and often shift operations.

---

### ❌ Every CPU has only one ALU.

✅ Many modern processors contain multiple ALUs and other specialized execution units so that several operations can be performed in parallel.

---

# Summary

The Arithmetic Logic Unit (ALU) is the computational core of the CPU.

It performs arithmetic operations such as addition and subtraction, logical operations such as AND and OR, comparison operations, and bit-shift operations.

The ALU works closely with:

- Registers
- The Control Unit
- The Status Register

Together, these components allow the CPU to execute instructions and process data efficiently.

---

# Key Takeaways

- The ALU performs arithmetic and logical operations.
- It receives operands from registers.
- The Control Unit selects the operation.
- Results are written back to registers.
- Status flags record information about each result.
- The ALU is built from combinational circuits.
- Modern CPUs often contain multiple ALUs.
- Every program depends on ALU operations.

---

# Review Questions

1. What is the ALU?
2. Why is the ALU important?
3. What are arithmetic operations?
4. What are logical operations?
5. What is the difference between an arithmetic and a logical operation?
6. What are status flags?
7. What is the role of the Control Unit during an ALU operation?
8. How is an ALU built?
9. Why are registers important to the ALU?
10. Give three real-world uses of the ALU.

---

# Mini Quiz

### 1. What does ALU stand for?

A. Automatic Logic Unit

B. Arithmetic Logic Unit

C. Advanced Linear Unit

D. Arithmetic Load Unit

**Answer:** B

---

### 2. Which CPU component tells the ALU which operation to perform?

A. Cache

B. RAM

C. Control Unit

D. SSD

**Answer:** C

---

### 3. Which of the following is a logical operation?

A. Addition

B. Subtraction

C. AND

D. Increment

**Answer:** C

---

### 4. Which flag becomes set when the result of an operation is zero?

A. Carry Flag

B. Overflow Flag

C. Zero Flag

D. Sign Flag

**Answer:** C

---

### 5. Where does the ALU usually get its operands from?

A. SSD

B. Registers

C. ROM

D. Network

**Answer:** B

---

# Further Reading

The ALU can process data, but it cannot decide *which* operation to perform or *when* to perform it.

Another essential CPU component is responsible for coordinating all processor activities.

This component is the **Control Unit (CU)**.

---

# What's Next?

Now that we understand how the CPU performs calculations, the next step is to learn **how those calculations are coordinated**.

In the next chapter, **Control Unit**, we will study how the CPU fetches instructions, decodes them, controls data movement between components, generates control signals, and manages the **Fetch–Decode–Execute Cycle** that drives every computer program.