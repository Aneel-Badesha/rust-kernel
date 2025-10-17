# Rust Kernel

A custom operating system kernel written in Rust, designed to explore low-level systems programming and OS development concepts.

## Overview

This project is an educational and experimental kernel implementation that leverages Rust's memory safety guarantees and zero-cost abstractions for systems programming. The kernel aims to provide a foundation for understanding operating system internals while taking advantage of Rust's modern language features.

## Features (In Development)

- **Memory Safety**: Leveraging Rust's ownership system for safe kernel code
- **No Standard Library**: Bare-metal programming with `#![no_std]`
- **Custom Boot Process**: Low-level bootloader integration
- **Hardware Abstraction**: Direct hardware interaction and device management
- **Interrupt Handling**: System interrupt and exception management
- **Memory Management**: Custom allocators and memory layout control

## Architecture

### Core Components
- **Boot**: Initial system startup and hardware initialization
- **Memory Management**: Physical and virtual memory handling
- **Interrupt System**: IDT (Interrupt Descriptor Table) setup and handlers
- **Hardware Drivers**: Basic device drivers for essential hardware
- **Kernel Services**: Core OS functionality and system calls

### Target Architecture
- **x86_64**: Primary target architecture
- **Bare Metal**: Direct hardware execution without host OS

## Development Environment

### Prerequisites
- **Rust**: Latest stable or nightly compiler
- **cargo**: Rust package manager and build tool
- **QEMU**: For kernel testing and emulation
- **Cross-compilation tools**: For target architecture

### Build Dependencies
```toml
# Key dependencies (typical for OS kernel)
bootloader = "0.9"
volatile = "0.2"
spin = "0.5"
x86_64 = "0.14"
uart_16550 = "0.2"
```

## Getting Started

### Building the Kernel
```bash
# Install Rust nightly
rustup install nightly
rustup default nightly

# Add target for bare metal
rustup target add x86_64-unknown-none

# Build the kernel
cargo build --target x86_64-unknown-none
```

### Running in QEMU
```bash
# Boot the kernel in QEMU emulator
qemu-system-x86_64 -drive format=raw,file=target/x86_64-unknown-none/debug/bootimage-rust-kernel.bin
```

## Development Status

**Current Status**: In Progress

### Completed
- [X] Basic project structure
- [X] Bootloader integration
- [X] VGA text mode output
- [X] Basic panic handler

### In Development
- [ ] Memory management
- [ ] Interrupt handling
- [ ] Keyboard input
- [ ] Hardware abstraction layer

### Planned Features
- [ ] Process management
- [ ] File system support
- [ ] Network stack
- [ ] User space programs

## Learning Objectives

This kernel serves as a learning platform for:
- **Low-level Programming**: Direct hardware interaction
- **Operating System Concepts**: Memory management, scheduling, I/O
- **Rust Systems Programming**: Using Rust for kernel development
- **Computer Architecture**: x86_64 architecture specifics

## Resources

- [The Rust Programming Language](https://doc.rust-lang.org/book/)
- [OSDev Wiki](https://wiki.osdev.org/)
- [Writing an OS in Rust](https://os.phil-opp.com/)

---

**Note**: This is an experimental kernel for educational purposes and is not intended for production use.