# Introduction

> *"Every modern computer—from a simple calculator to the world's fastest supercomputer—is built from billions of tiny electronic switches called transistors."*

Welcome to **Computer Architecture From Scratch**.

This project is a step-by-step journey through the inner workings of a computer. Instead of treating the CPU as a mysterious black box, we'll build one from the ground up, understanding every layer along the way.

By the end of this project, you'll know how a simple electronic switch can eventually become a fully programmable **8-bit processor** capable of executing machine code.

---

# Why This Project?

Many computer architecture courses begin with logic gates, assembly language, or CPU diagrams. While these topics are important, they often skip an essential question:

> **Where do logic gates come from?**

To answer that, we need to go one level deeper.

Logic gates are built from **transistors**.

Transistors are built using **semiconductor physics**.

Understanding these foundations makes the behavior of digital circuits much easier to understand.

This project follows the same path that computer hardware engineers follow when designing real processors.

---

# What Is a Computer?

At its core, a computer is a machine that performs four basic tasks:

1. Accepts input
2. Stores data
3. Processes information
4. Produces output

Whether you're using a smartphone, laptop, gaming console, or server, every computer performs these same fundamental operations.

---

# The Building Blocks of a Computer

Modern computers are built in layers.

```
Software
    │
Operating System
    │
Assembly Language
    │
Machine Code
    │
CPU
    │
Logic Gates
    │
Transistors
    │
Semiconductor Physics
```

In this project, we'll start at the **bottom** and work our way **up**.

---

# Why Start with Transistors?

A transistor is an electronic component that can act as a very fast switch.

It has only two important states:

```
OFF  → 0

ON   → 1
```

These two states form the basis of **binary**, the language used by all digital computers.

By combining millions—or even billions—of transistors, engineers create logic gates, memory, arithmetic units, and eventually complete processors.

---

# A Brief History

## Vacuum Tubes

Before transistors were invented, computers used **vacuum tubes**.

Characteristics:

- Very large
- Consumed a lot of electricity
- Produced significant heat
- Failed frequently
- Expensive to manufacture

Early computers occupied entire rooms and required enormous amounts of power.

---

## The Invention of the Transistor

In **1947**, researchers at **Bell Labs** invented the first transistor.

This breakthrough transformed the electronics industry.

Compared to vacuum tubes, transistors were:

- Smaller
- Faster
- More reliable
- More energy-efficient
- Easier to manufacture

This invention made modern computers possible.

---

## Integrated Circuits

As manufacturing technology improved, engineers began placing multiple transistors onto a single silicon chip.

These chips became known as **Integrated Circuits (ICs)**.

Instead of wiring thousands of individual transistors together, entire circuits could now fit on a single chip.

---

## Modern Processors

Today's CPUs contain **billions of transistors** packed into an area only a few square centimeters in size.

For example:

- Smartphones contain billions of transistors.
- Desktop processors contain tens of billions of transistors.
- High-performance AI chips can contain over one hundred billion transistors.

Despite this incredible scale, every transistor still behaves like a tiny electronic switch.

---

# Moore's Law

In 1965, engineer **Gordon Moore** observed that the number of transistors on integrated circuits was increasing rapidly over time.

This observation became known as **Moore's Law**.

For decades, the number of transistors on computer chips roughly doubled every two years, enabling computers to become:

- Faster
- Smaller
- More powerful
- More energy-efficient
- Less expensive per unit of performance

Although the pace has slowed in recent years, Moore's Law has had a profound influence on the evolution of computing.

---

# From One Transistor to a CPU

This project gradually builds a complete computer by stacking simple concepts.

```
One Transistor
        │
        ▼
Electronic Switch
        │
        ▼
Logic Gates
        │
        ▼
Arithmetic Circuits
        │
        ▼
Registers
        │
        ▼
Memory
        │
        ▼
ALU
        │
        ▼
Control Unit
        │
        ▼
CPU
        │
        ▼
Computer
```

Every chapter builds directly on the previous one.

---

# What You Will Learn

By completing this project, you will understand:

- Basic electricity
- Semiconductors
- Transistors
- Digital logic
- Binary numbers
- Logic gates
- Adders and multiplexers
- Memory systems
- Registers
- Arithmetic Logic Units (ALUs)
- Control units
- Instruction Set Architecture (ISA)
- Assembly language
- CPU execution cycles
- Computer architecture fundamentals

More importantly, you'll understand **how these concepts connect together**.

---

# Project Philosophy

This project follows three guiding principles:

## Learn by Building

Every concept is accompanied by practical implementations and simulations.

---

## Start Simple

Complex systems become easier to understand when broken down into small, manageable pieces.

---

## Understand Every Layer

Rather than memorizing diagrams, you'll build each layer yourself and see how it contributes to the complete system.

---

# Prerequisites

You do **not** need prior knowledge of:

- Electronics
- Computer architecture
- Digital logic
- Assembly language
- Processor design

Basic familiarity with programming (especially Python) is helpful but not required.

---

# What's Next?

Now that you understand the purpose and roadmap of this project, the next chapter introduces the fundamental concepts of electricity.

We'll answer questions such as:

- What is electricity?
- What are electrons?
- How does electric current flow?
- What is voltage?
- Why does electricity move through some materials but not others?

These concepts form the foundation for understanding semiconductors and, ultimately, transistors.

---

## Summary

In this chapter, you learned:

- Why computers are built from transistors.
- Why understanding transistors is important.
- The evolution from vacuum tubes to modern processors.
- The concept of Moore's Law.
- The learning roadmap for this project.
- What you will build by the end of the course.

In the next chapter, we'll begin with the fundamentals of **electricity**, the science that makes every computer possible.

➡️ **Next:** `02_electricity_basics.md`