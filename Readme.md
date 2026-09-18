# Log

## Day-1 Thursday 17 September 2026

### BIOS
- BIOS stands for **Basic Input Output System Check**
- POST stands for **Power On Self Test**
- It is the first process that runs when a computer is powered on
- After BIOS succeeds, it hands over control to GRUB

### GRUB
- GRUB stands for **Grand Unified Boot Loader**
- It is an interface used for choosing an operating system
- Dual boot uses GRUB to select between multiple OS options

### Linux Flavours
- Linux is open-source, so there are different **flavours (distributions)** of Linux
- Each flavour serves its own purpose for the user (e.g., Ubuntu for beginners, Kali for security, CentOS for servers)

### Boot Process
- **init** is the first process started by the kernel (PID 1)
- **rmfs** (initial RAM filesystem) is loaded during boot
- If PID 1 is killed, all child processes become **zombie processes** (they are not terminated, but lose their parent)

### Networking
- **NIC (Network Interface Card)** is used to connect a computer to a network

### Basic Linux Commands
| Command | Description |
|---------|-------------|
| `ls` | List directory contents |
| `pwd` | Print working directory |
| `cd` | Change directory |
| `mkdir` | Create a new directory |
| `touch` | Create a new file |
| `rm` | Remove a file |
| `rm -rf` | Remove files/directories recursively and forcefully |
| `man <command>` | Open the manual page for a command |

### Directory Notation
| Symbol | Meaning |
|--------|---------|
| `.` | Current directory |
| `..` | Previous (parent) directory |
