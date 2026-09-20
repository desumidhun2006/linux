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

---

## Day-2 Friday 18 September 2026

### Course Agenda Overview
- Linux OS, Process Management, File Management, PC Sockets, Threads, Memory Management Server
- Approximately 50 foundational commands across OS and process management

### Basic Navigation Commands
| Command | Description |
|---------|-------------|
| `pwd` | Print working directory (absolute path) |
| `ls` | List files and directories in current directory |
| `cd` | Change directory |
| `mkdir` | Create a new directory |
| `touch` | Create a new file or check file status |
| `rm` | Remove a file |
| `rmdir` | Remove an empty directory |
| `rm -rf` | Remove files/directories recursively and forcefully |
| `cat` | Display entire file contents |
| `head -n <N>` | Print first N lines of a file |
| `tail` | Print last lines of a file |
| `file <filename>` | Identify file type |
| `find <path>` | Search for files in a directory tree |
| `ps` | View active system processes |
| `top` | Real-time system monitoring (CPU, memory, tasks) |
| `whoami` | Display current user identity |
| `man <command>` | Open manual page for a command |

### ls Command Colors
| Color | Meaning |
|-------|---------|
| Blue | Directory |
| Yellow | Regular file |
| Purple/Magenta | Symbolic link or special file |

### File Permission System

#### Permission Characters
| Symbol | Meaning |
|--------|---------|
| `-` | Regular file |
| `d` | Directory |

#### Permission Triplet (rwx)
| Permission | Numeric Value | Description |
|------------|---------------|-------------|
| Read (r) | 4 | View file contents |
| Write (w) | 2 | Modify file contents |
| Execute (x) | 1 | Execute file as program |

#### Common Numeric (Octal) Permissions
| Value | Permissions | Meaning |
|-------|-------------|---------|
| 7 | rwx | Full access |
| 6 | rw- | Read + Write |
| 5 | r-x | Read + Execute |
| 4 | r-- | Read only |
| 0 | --- | No permissions |

#### Permission Categories
- **User/Owner (u)**: The file owner
- **Group (g)**: Users in the file's group
- **Others (o)**: Everyone else

#### Example
```
-rwxr-xr-x 1 user group 4096 Sep 18 10:00 filename
```
- First character `-` = regular file
- `rwx` = owner has read, write, execute
- `r-x` = group has read and execute
- `r-x` = others have read and execute

### ls Command Flags
| Flag | Description |
|------|-------------|
| `-l` | Long listing format (detailed info) |
| `-a` | Show hidden files (starting with .) |
| `-A` | Show all except . and .. |
| `-h` | Human-readable file sizes (KB, MB, GB) |
| `-d` | List directory entries, not contents |
| `-R` | Recursively list subdirectories |
| `-t` | Sort by modification time |
| `-S` | Sort by file size |
| `-1` | Single-column output |
| `-i` | Print inode number |
| `-n` | Display numeric UID/GID |
| `-r` | Reverse sort order |
| `-C` | Columnar listing (default) |
| `-x` | List across by lines |

### mkdir Command
- Creates directories with specified names
- `-p` flag creates missing parent directories automatically
- Without `-p`, fails if parent directory doesn't exist

### rm Command
| Flag | Description |
|------|-------------|
| `-f` | Force, no prompts, ignore nonexistent files |
| `-i` | Prompt before every removal |
| `-I` | Prompt once before removing >3 files or recursive |
| `-r` / `-R` | Recursive removal |
| `-d` | Remove empty directories |
| `-v` | Verbose output |
| `--preserve-root` | Prevents deleting `/` (default) |
| `--no-preserve-root` | Allows deleting `/` (dangerous) |
| `--one-file-system` | Skip directories on different filesystems |

### Recursive Execution
- "Recursive" means processing in a nested, hierarchical manner
- Example: In structure 1→2→3→4, `rm -rf` deletes from deepest child (4) upward to parent (1)
- Uses bottom-up/leaf-to-root traversal

### Path Resolution
| Path Type | Example | Description |
|-----------|---------|-------------|
| Absolute | `/home/user/file` | Starts from root `/` |
| Relative | `home/user/file` | Relative to current directory |

### File Editors

#### vi/vim
- Pre-installed command-line editor
- **Insert Mode**: Press `i` to type text
- **Command Mode**: Press `Escape` to navigate/save
- Commands: `:q` (quit), `:q!` (force quit), `:wq` (save and quit), `dd` (delete line), `yy` (copy line), `p` (paste below), `/` (search)

#### nano
- Beginner-friendly alternative editor
- Simpler interface with on-screen shortcuts

### Output Piping
- `|` (pipe) redirects output of one command as input to another
- Example: `cat file.txt | head -n 5` shows first 5 lines

### Safety Warning
- Commands like `rm -rf` can permanently destroy system files
- Always practice destructive commands in a **virtual machine** environment
- Corrupted VMs can be recovered by reinstalling the virtual disk
