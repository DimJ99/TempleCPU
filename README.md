# TempleCPU
This project aims to extend a previously built 8-bit single-cycle CPU into a 32-bit microcontroller-class system-on-chip, developed incrementally alongside coursework in computer architecture and digital design. The goal is not to chase maximum performance, but to deeply understand CPU microarchitecture, memory systems, buses, and peripherals through a realistic open-ended design.

# Phase 0: Architecture Definition
Before implementation, define the architectural boundaries of the system. This phase establishes a shared mental model across the team and prevents major redesigns later. 
GOALS: 
Define a stable 32-bit ISA and programming model
Decide on register file size, instruction format, and memory model
Establish a memory map for RAM, peripherals, and control registers
Choose a target pipeline depth and interrupt model
Document assumptions and non-goals (e.g., no out-of-order execution)

# Phase 1: 32-bit CPU Bring-Up (Single-Cycle)
Create a simple, correct baseline CPU that can execute software reliably.
GOALS:
Extend the existing assembler/toolchain to support 32-bit instructions
Implement a single-cycle 32-bit CPU core
Execute basic assembly programs (loops, branches, memory access)
Provide a clean interface to memory****

# Phase 2: System Bus Integration
Transform the CPU into a system-level component by introducing a standard bus architecture. This enables modular peripherals and future system expansion.
GOALS:
Integrate the CPU as a bus master (AHB)
Attach RAM and peripherals as bus slaves
Establish a consistent memory-mapped I/O model
Lay groundwork for multiple bus masters

# Phase 3: Peripheral Subsystem
Add real microcontroller-style peripherals that interact with software and the external world. Emphasis is on configurability and interrupt generation.
GOALS:
Implement GPIO for basic digital I/O
Add PWM for timing-based output
Integrate an existing USB 1.1 controller design
Introduce interrupt generation from peripherals

# Phase 4: Pipelined CPU Core
Incrementally evolve the single-cycle CPU into an in-order pipelined processor. This phase focuses on understanding instruction overlap, hazards, and control complexity.
GOALS:
Implement a basic in-order pipeline (5 stages)
Handle data hazards through stalling and forwarding
Support control hazards via pipeline flushing
Preserve architectural correctness relative to the single-cycle model

# Phase 5: Interrupt Architecture, DMA, Multi-Master Support
Enable asynchronous hardware events to interact cleanly with the CPU, introduce autonomous data movement and bus arbitration to simulate realistic system-level concurrency.
GOALS:
Implement a centralized interrupt controller
Support interrupt enable/masking
Define a precise interrupt entry and return mechanism
Implement a simple DMA engine as a second bus master
Support basic memory-to-memory transfers
Add bus arbitration logic
Allow CPU and DMA to operate concurrently

# Phase 7: Cache Integration
A primitive L1 direct-mapped cache will be implemented. Further data cache is an option aswell
