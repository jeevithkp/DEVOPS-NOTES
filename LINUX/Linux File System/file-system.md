# Linux File System & Directory Management

## Overview

This repository provides comprehensive notes on the Linux File System,
Filesystem Hierarchy Standard (FHS), Linux storage architecture,
filesystem implementations, directory structure, and essential Linux
file management commands. It is intended for DevOps Engineers, System
Administrators, Cloud Engineers, and Linux learners.

## Objectives

-   Understand Linux filesystem architecture.
-   Learn the Linux directory hierarchy (FHS).
-   Explore ext4, XFS, Btrfs and other filesystems.
-   Master navigation and file management commands.
-   Build practical Linux administration skills.

## Linux File System Architecture

### Logical File System

-   File APIs (open, read, write, close)
-   Permissions and access control

### Virtual File System (VFS)

-   Common interface for multiple filesystems
-   Supports ext4, XFS, FAT32, NTFS, Btrfs

### Physical File System

-   Disk interaction
-   Block allocation
-   Storage management

## Filesystem Features

-   Journaling
-   Inodes
-   Versioning
-   Metadata
-   Space management
-   Permissions

## Filesystem Implementations

  Filesystem   Highlights
  ------------ -----------------------------------------------------------
  ext4         Default Linux filesystem, journaling, extents, encryption
  XFS          High-performance, large files, parallel I/O
  Btrfs        Snapshots, compression, self-healing
  JFS          Stable enterprise filesystem
  SquashFS     Compressed read-only
  NTFS/exFAT   Cross-platform compatibility

## Linux Directory Structure

  Directory   Purpose
  ----------- -------------------------
  /           Root
  /bin        Essential binaries
  /boot       Bootloader & kernel
  /dev        Device files
  /etc        Configuration
  /home       User data
  /lib        Libraries
  /media      Removable media
  /mnt        Temporary mounts
  /opt        Optional software
  /proc       Process information
  /sbin       Administrative binaries
  /srv        Service data
  /tmp        Temporary files
  /usr        User applications
  /var        Logs and variable data

## Important Configuration Files

-   /etc/passwd
-   /etc/group
-   /etc/fstab
-   /etc/hosts
-   /etc/resolv.conf
-   /proc/cpuinfo
-   /proc/meminfo
-   /var/log

## Essential Linux Commands

### Navigation

``` bash
pwd
ls -la
cd
```

### Directory Management

``` bash
mkdir -p project/src
rmdir emptydir
```

### File Management

``` bash
cp -r source backup
mv file.txt archive/
```

## Absolute vs Relative Paths

-   Absolute paths begin with `/`.
-   Relative paths depend on the current working directory.
-   Special symbols: `.`, `..`, `~`.

## DevOps Relevance

This guide covers core Linux knowledge required for: - Server
administration - Cloud infrastructure - Storage management - Automation
and shell scripting - Troubleshooting - Log management - Production
operations

## Suggested Images

1.  Linux Filesystem Hierarchy
2.  Linux Filesystem Architecture (Logical → VFS → Physical)
3.  ext4 vs XFS vs Btrfs comparison
4.  Linux directory tree

## Conclusion

This repository serves as a practical reference for Linux filesystem
concepts, directory hierarchy, filesystem implementations, and
command-line operations. It provides the foundational knowledge required
for DevOps, cloud engineering, and Linux system administration.
