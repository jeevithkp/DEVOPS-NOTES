# Linux File System & File Management for DevOps

> A comprehensive guide to the Linux File System, Filesystem Hierarchy Standard (FHS), navigation, file management, and essential commands every DevOps Engineer should know.

---

# Table of Contents

- Introduction
- Linux File System Architecture
- Characteristics of Linux File Systems
- Advanced File System Features
- Popular Linux File Systems
- ext4 Deep Dive
- Linux Filesystem Hierarchy (FHS)
- Important System Directories
- Types of Linux Files
- Essential System Configuration Files
- Important /proc Files
- Linux Navigation Commands
- File Management Commands
- Absolute vs Relative Paths
- Windows vs Linux File System
- DevOps Best Practices
- Interview Questions

---

# Introduction

Linux stores everything as a file.

This includes:

- Regular files
- Directories
- Devices
- Processes
- Network sockets

Unlike Windows, Linux follows a **single hierarchical directory structure** beginning at the root directory:

```
/
```

Everything exists beneath this root.

---

# Linux File System Architecture

The Linux File System consists of three major layers.

## 1. Logical File System

Responsible for:

- File operations
- Open
- Read
- Write
- Close
- File permissions
- Security

Applications communicate with this layer.

---

## 2. Virtual File System (VFS)

Acts as an abstraction layer.

Purpose:

- Supports multiple file systems simultaneously
- Provides common APIs
- Makes ext4, XFS, FAT32, NTFS work uniformly

---

## 3. Physical File System

Interacts directly with storage devices.

Responsibilities:

- Disk blocks
- Inodes
- Storage allocation
- Disk reads/writes
- Error handling

---

# Characteristics of Linux File Systems

A Linux File System manages:

- Storage allocation
- Directory hierarchy
- Metadata
- Permissions
- File names
- File ownership
- Backup
- Recovery
- Performance

---

# Advanced File System Features

## Journaling

Journaling records filesystem changes before writing them permanently.

Benefits:

- Crash recovery
- Faster reboot
- Reduced corruption

### Modes

### Journal Mode

- Data + Metadata
- Highest protection

### Ordered Mode

- Metadata journaled
- Data written first

(Default in ext4)

### Writeback Mode

- Metadata only
- Fastest
- Less safe

---

## Versioning

Allows restoring previous file versions.

Useful for:

- Snapshots
- Backup
- Recovery

---

## Inodes

Every file has an inode.

Stores:

- Owner
- Permissions
- File size
- Timestamps
- Disk block pointers

Does **NOT** store filename.

---

# Popular Linux File Systems

| File System | Features | Use Case |
|-------------|----------|----------|
| ext | First Linux filesystem | Historical |
| ext2 | No journaling | Flash devices |
| ext3 | Journaling | Legacy systems |
| ext4 | Modern default | General purpose |
| XFS | High-performance | Large files |
| Btrfs | Snapshots, CoW | Enterprise |
| JFS | IBM filesystem | Stable workloads |
| ReiserFS | B+ Trees | Obsolete |
| SquashFS | Read-only compressed | Embedded Linux |
| NTFS | Windows compatibility | Dual boot |
| exFAT | Cross-platform | USB drives |

---

# ext4 Features

ext4 is the default filesystem for most Linux distributions.

Key Features

- Journaling
- Extents
- Delayed Allocation
- Persistent Pre-allocation
- Large File Support
- Metadata Checksums
- Encryption
- HTree Indexing
- Nanosecond timestamps
- Lazy inode initialization

Advantages

- Fast
- Reliable
- Stable
- Backward compatible with ext2/ext3

---

# XFS

Best suited for

- Large storage
- Databases
- Video servers
- Media streaming

Supports

- Online resizing
- Online defragmentation
- Snapshots
- Parallel I/O

Example

```bash
sudo apt install xfsprogs

sudo mkfs.xfs /dev/sda1

sudo mount /dev/sda1 /mnt/data

df -h
```

---

# Linux Filesystem Hierarchy (FHS)

```
/
├── bin
├── boot
├── dev
├── etc
├── home
├── lib
├── media
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin
├── srv
├── sys
├── tmp
├── usr
└── var
```

---

# Important Directories

## /

Root directory.

Everything begins here.

---

## /bin

Essential user commands.

Examples

```
ls
cp
mv
cat
grep
```

---

## /sbin

Administrative commands.

Examples

```
fdisk
iptables
ifconfig
fsck
reboot
```

---

## /boot

Contains

- Linux Kernel
- GRUB
- initramfs

Examples

```
vmlinuz
initrd
grub.cfg
```

---

## /etc

System configuration files.

Examples

```
passwd
hosts
fstab
resolv.conf
crontab
```

---

## /home

User home directories.

Example

```
/home/john
```

---

## /root

Root user's home directory.

---

## /lib

Shared libraries.

Example

```
libc.so
```

---

## /dev

Hardware devices.

Examples

```
/dev/sda
/dev/null
/dev/tty
```

---

## /proc

Virtual filesystem.

Provides runtime system information.

Examples

```
/proc/cpuinfo
/proc/meminfo
/proc/version
```

---

## /var

Variable data.

Contains

- Logs
- Cache
- Mail
- Database files

Examples

```
/var/log
```

---

## /tmp

Temporary files.

Usually cleared after reboot.

---

## /usr

Installed applications.

Contains

```
/usr/bin
/usr/lib
/usr/local
```

---

## /media

Auto-mounted removable devices.

USB

DVD

CD

---

## /mnt

Temporary mount point.

---

## /opt

Third-party software.

---

## /srv

Server-specific data.

---

# Linux File Types

## Regular File

Documents

Images

Executables

---

## Directory

Stores files.

---

## Character Device

Keyboard

Mouse

Terminal

---

## Block Device

Hard Disk

SSD

USB

---

## Symbolic Link

Shortcut to another file.

---

## Socket

Inter-process communication.

---

## Named Pipe (FIFO)

Used between processes.

---

# Important Configuration Files

| File | Purpose |
|-------|----------|
| /etc/passwd | User accounts |
| /etc/group | Groups |
| /etc/fstab | Mount information |
| /etc/hosts | Hostname mapping |
| /etc/resolv.conf | DNS |
| /etc/profile | Global environment |
| /etc/bashrc | Bash configuration |
| /etc/crontab | Scheduled jobs |

---

# Useful /proc Files

| File | Purpose |
|-------|----------|
| /proc/cpuinfo | CPU details |
| /proc/meminfo | Memory usage |
| /proc/version | Kernel version |
| /proc/mounts | Mounted filesystems |
| /proc/filesystems | Supported filesystems |
| /proc/stat | System statistics |

---

# Navigation Commands

## pwd

Current directory.

```bash
pwd
```

---

## ls

List files.

```bash
ls
```

Useful options

```bash
ls -l
ls -lh
ls -a
ls -lt
ls -ltr
ls -R
ls -i
ls --color=auto
```

---

## cd

Change directory.

```bash
cd ~

cd ..

cd /

cd /home/user

cd Documents
```

---

## tree

View directory hierarchy.

```bash
tree
```

---

# Directory Management

## mkdir

Create directory.

```bash
mkdir project
```

Options

```bash
mkdir -p app/src/config

mkdir -v project

mkdir -m 755 project
```

---

## rmdir

Remove empty directory.

```bash
rmdir demo
```

Options

```bash
rmdir -p

rmdir -v
```

---

# File Management

## cp

Copy files.

```bash
cp file1 file2

cp -r folder backup

cp -p file backup

cp -i file backup

cp *.txt docs/
```

---

## mv

Move or rename files.

```bash
mv file newfile

mv file /tmp

mv dir newdir
```

Options

```bash
mv -i

mv -f

mv -n

mv -b
```

---

# Path Types

## Absolute Path

Starts from root.

Example

```bash
/home/user/project/file.txt
```

---

## Relative Path

Starts from current directory.

Example

```bash
project/file.txt
```

---

# Special Symbols

| Symbol | Meaning |
|----------|----------|
| / | Root |
| . | Current directory |
| .. | Parent directory |
| ~ | Home directory |

---

# Windows vs Linux

| Windows | Linux |
|-----------|--------|
| Drive letters | Single root |
| NTFS | ext4/XFS/Btrfs |
| Case-insensitive | Case-sensitive |
| Limited permissions | Advanced permissions |
| C:\ | / |

---

# DevOps Best Practices

✔ Always use absolute paths inside scripts.

✔ Store configuration under `/etc`.

✔ Keep application logs in `/var/log`.

✔ Avoid writing files directly under `/`.

✔ Use `/tmp` only for temporary files.

✔ Prefer ext4 for general workloads.

✔ Use XFS for databases and large storage.

✔ Understand inode usage.

✔ Monitor disk usage:

```bash
df -h
du -sh *
```

✔ Check mounts:

```bash
mount

lsblk
```

✔ Monitor filesystem:

```bash
df -Th
```

✔ View permissions:

```bash
ls -l
```

✔ Check inode usage:

```bash
df -i
```

---

# Essential DevOps Commands

```bash
pwd
ls
cd
tree
mkdir
rmdir
cp
mv
find
locate
du
df
mount
umount
stat
file
ln
chmod
chown
```

---

# Interview Questions

### What is the Linux File System?

A hierarchical structure beginning at `/` that organizes and stores all files, directories, and devices.

---

### What is an inode?

A metadata structure containing file information except the filename.

---

### Difference between ext3 and ext4?

- ext4 supports extents
- Better performance
- Larger filesystem support
- Delayed allocation
- Metadata checksum
- Encryption

---

### Difference between Absolute and Relative Path?

Absolute starts from `/`.

Relative starts from current directory.

---

### Why is journaling important?

It protects filesystem consistency during crashes and speeds up recovery.

---

### What does VFS do?

Provides a common interface allowing Linux to support multiple filesystem types.

---

### Which filesystem is best?

- **ext4** → General purpose
- **XFS** → Large files and databases
- **Btrfs** → Snapshots and advanced storage

---

# Conclusion

Understanding the Linux File System is fundamental for DevOps, Cloud, and System Administration. Mastering directory hierarchy, navigation, filesystem types, permissions, and file management commands is essential for efficiently managing Linux servers, automating deployments, troubleshooting issues, and maintaining reliable infrastructure.
