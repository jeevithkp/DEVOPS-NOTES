# Linux Architecture

## Overview
Linux follows a **layered architecture** where each layer communicates with the layer below it to provide a stable, secure, and efficient operating system.

## Architecture Diagram

```text
+------------------------------------------------+
|                  Applications                  |
| (Browsers, Editors, Databases, IDEs, etc.)     |
+------------------------------------------------+
                     │
                     ▼
+------------------------------------------------+
|              System Libraries                  |
| glibc | libpthread | libm | libdl | libstdc++ |
+------------------------------------------------+
                     │
                     ▼
+------------------------------------------------+
|                    Shell                       |
| Bash | Zsh | Fish | Ksh | Csh | Sh            |
+------------------------------------------------+
                     │
                     ▼
+------------------------------------------------+
|                    Kernel                      |
| • Process Management                           |
| • Memory Management                            |
| • Device Drivers                               |
| • File System                                  |
| • Networking                                   |
| • Security                                     |
| • IPC                                          |
+------------------------------------------------+
                     │
                     ▼
+------------------------------------------------+
|                  Hardware                      |
| CPU | RAM | Storage | Network | I/O Devices    |
+------------------------------------------------+
```

---

# Linux Architecture Layers

## 1. Applications
Applications are user-level programs that perform specific tasks.

**Examples**
- Web Browsers
- Text Editors
- Databases
- IDEs
- Office Applications

---

## 2. System Libraries
System libraries provide APIs that allow applications to communicate with the Linux kernel without directly accessing it.

### Common Libraries
- **glibc** – Standard C library
- **libpthread** – POSIX thread support
- **libdl** – Dynamic library loading
- **libm** – Mathematical functions
- **libstdc++** – C++ Standard Library
- **librt** – Real-time extensions
- **libcrypt** – Cryptographic functions

---

## 3. Shell
The shell acts as the interface between users and the kernel. It interprets user commands and passes them to the kernel.

### Popular Linux Shells

| Shell | Description |
|--------|-------------|
| **Bash** | Default shell in most Linux distributions |
| **Zsh** | Highly customizable with plugins and themes |
| **Fish** | Beginner-friendly with syntax highlighting |
| **Ksh** | Enterprise-oriented shell |
| **Csh** | C-like syntax |
| **Sh** | Original Bourne Shell |

---

## 4. Kernel
The kernel is the **core of the Linux operating system**. It manages hardware resources and provides essential services for applications.

### Responsibilities
- Memory Management
- Process Scheduling
- Resource Allocation
- Device Management
- Security Enforcement
- Hardware Communication

---

## Kernel Types

### 1. Monolithic Kernel
- All core services run in kernel space
- High performance
- Less modular

### 2. Microkernel
- Only essential services remain in kernel space
- Better security and modularity
- Slight performance overhead

### 3. Exokernel
- Direct hardware access for applications
- Maximum flexibility and performance
- Increased application complexity

### 4. Hybrid Kernel
- Combination of Monolithic and Microkernel
- Balanced performance and modularity

---

## Kernel Subsystems

### Process Scheduler
- Manages CPU scheduling
- Allocates processor time fairly

### Memory Management
- Allocates RAM
- Handles virtual memory
- Prevents memory conflicts

### Virtual File System (VFS)
- Provides a common interface for different file systems
- Supports multiple storage devices

### Networking Subsystem
- Handles network communication
- Supports routing and protocols

### Inter-Process Communication (IPC)
- Enables communication between running processes
- Provides synchronization mechanisms

---

## 5. Hardware Layer
The hardware layer consists of the physical components of the computer.

### Components
- CPU
- RAM
- Storage Devices
- Network Interface
- Keyboard
- Mouse
- Display
- USB Devices

The kernel communicates with hardware using **device drivers**.

---

## System Utilities
System utilities are command-line tools used to administer and maintain Linux systems.

### Functions
- File Management
- User Management
- Process Monitoring
- Disk Management
- Network Configuration
- Permission Management
- System Monitoring

### Common Commands

| Category | Commands |
|----------|----------|
| File Management | `ls`, `cp`, `mv`, `rm`, `find` |
| Process Management | `ps`, `top`, `htop`, `kill` |
| Disk Management | `df`, `du`, `mount` |
| Networking | `ping`, `ip`, `netstat`, `ss` |
| User Management | `useradd`, `passwd`, `chmod`, `chown` |

---

# Complete Linux Architecture Flow

```text
User
 │
 ▼
Applications
 │
 ▼
System Libraries
 │
 ▼
Shell
 │
 ▼
Kernel
 ├── Process Scheduler
 ├── Memory Management
 ├── Device Drivers
 ├── Virtual File System
 ├── Networking
 ├── Security
 └── IPC
 │
 ▼
Hardware
```

---

# Key Takeaways

- Linux follows a **layered architecture**.
- The **kernel** is the core component managing hardware and system resources.
- **System libraries** provide APIs for applications.
- The **shell** interprets user commands.
- **System utilities** simplify administration and monitoring.
- The **hardware layer** consists of physical components controlled by the kernel through device drivers.
