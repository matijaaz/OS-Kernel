# RISC-V Operating System Kernel

This repository contains a custom-built, fully functional operating system kernel designed for the RISC-V architecture.

## Overview

The kernel acts as a bridge between the underlying RISC-V hardware and user applications. It is capable of booting, managing hardware interrupts, and providing a stable execution environment for multiple concurrent threads. The primary focus of this project is on multitasking, context switching, and thread synchronization.

## Core Features

* **Thread Management & Scheduling:** Implemented a thread scheduler supporting multiple concurrent execution paths. The scheduler manages Thread Control Blocks (TCBs) and orchestrates execution based on a time-sharing mechanism.
* **Context Switching:** Developed robust context-switching routines in RISC-V Assembly to safely save and restore processor registers during timer interrupts, system calls, or thread yields.
* **Synchronization Mechanisms:** Implemented semaphores (wait and signal operations) to ensure safe access to shared resources, prevent race conditions, and allow threads to block and unblock efficiently.
* **Interrupt & Trap Handling:** Engineered a comprehensive trap handling mechanism to process asynchronous hardware interrupts (like timer ticks) and synchronous software exceptions (system calls/ABI).
* **System Calls (ABI):** Designed an Application Binary Interface to allow user-space applications to safely request kernel services (e.g., thread creation, semaphore manipulation, yielding).

## Technologies & Tools

* **Languages:** C++ (for core kernel logic), RISC-V Assembly (for low-level CPU state manipulation).
* **Architecture:** RISC-V (RV64).
* **Emulator:** QEMU (used for testing and debugging the kernel in a simulated RISC-V environment).
* **Build System:** GNU Make.

## Getting Started

### Prerequisites
To build and run this kernel, you will need the RISC-V GNU Compiler Toolchain and the QEMU emulator installed on your system:
* `qemu-system-riscv64`
* `make`

### Building the Kernel
Clone the repository and run the standard make command to compile the C++ and Assembly source files into a bootable object file:
```bash
make
