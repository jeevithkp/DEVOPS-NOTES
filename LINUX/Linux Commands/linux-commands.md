# Basic Linux Commands – Quick Reference

A concise guide to essential Linux commands for beginners, developers, and system administrators.

## Why Learn Linux Commands?

Linux commands allow you to interact with the operating system through the terminal to:

- Navigate the file system
- Create, copy, move, and delete files/directories
- Manage processes and users
- Monitor system resources
- Search files and text
- Automate administrative tasks

---

# File & Directory Commands

| Command | Purpose | Example |
|---------|----------|---------|
| `pwd` | Display current working directory | `pwd` |
| `ls` | List files and directories | `ls -la` |
| `cd` | Change directory | `cd Documents` |
| `mkdir` | Create directory | `mkdir Projects` |
| `mkdir -p` | Create nested directories | `mkdir -p app/src` |
| `rmdir` | Remove empty directory | `rmdir Test` |
| `touch` | Create empty file | `touch file.txt` |
| `cp` | Copy files/directories | `cp file1.txt file2.txt` |
| `mv` | Move or rename files | `mv old.txt new.txt` |
| `rm` | Remove files/directories | `rm file.txt` / `rm -rf folder` |

---

# File Content Commands

| Command | Purpose | Example |
|---------|----------|---------|
| `cat` | Display or concatenate file contents | `cat notes.txt` |
| `head` | Show first few lines | `head file.txt` |
| `tail` | Show last few lines | `tail file.txt` |
| `sort` | Sort file contents | `sort data.txt` |
| `wc` | Count lines, words, and characters | `wc file.txt` |
| `echo` | Print text or write to files | `echo "Hello"` |
| `grep` | Search text patterns | `grep "error" log.txt` |

---

# Search Commands

| Command | Purpose | Example |
|---------|----------|---------|
| `find` | Search files/directories | `find . -name "*.txt"` |
| `locate` | Find files using database | `locate demo.txt` |
| `whereis` | Locate command binaries | `whereis python` |

> **Note:** `locate` requires the `updatedb` database.

---

# System Information Commands

| Command | Purpose | Example |
|---------|----------|---------|
| `uname` | Display system information | `uname -a` |
| `whoami` | Show current logged-in user | `whoami` |
| `cal` | Display calendar | `cal` |
| `df -h` | Show disk usage | `df -h` |
| `du` | Show directory size | `du -sh folder` |
| `free` | Display memory usage | `free -h` |
| `history` | Show command history | `history` |
| `clear` | Clear terminal screen | `clear` |

---

# Process Management

| Command | Purpose | Example |
|---------|----------|---------|
| `ps` | Display running processes | `ps aux` |
| `top` | Monitor processes in real time | `top` |
| `kill` | Terminate a process | `kill 1234` |
| `pidof` | Find process ID | `pidof nginx` |
| `systemctl` | Manage system services | `systemctl status nginx` |

---

# Networking Commands

| Command | Purpose | Example |
|---------|----------|---------|
| `ifconfig` | Display network interfaces (legacy) | `ifconfig` |
| `ip` | Modern network management | `ip addr` |
| `nslookup` | DNS lookup | `nslookup google.com` |
| `wget` | Download files from the internet | `wget https://example.com/file.zip` |
| `curl` | Transfer data from URLs | `curl https://example.com` |
| `curl -o` | Download to a file | `curl -o file.zip URL` |
| `ssh-keygen` | Generate SSH key pairs | `ssh-keygen -t rsa` |

---

# Package Management (Debian/Ubuntu)

| Command | Purpose | Example |
|---------|----------|---------|
| `apt-get update` | Update package list | `sudo apt-get update` |
| `apt-get upgrade` | Upgrade installed packages | `sudo apt-get upgrade` |
| `apt-get install` | Install packages | `sudo apt-get install git` |
| `apt-get remove` | Remove packages | `sudo apt-get remove git` |

---

# User & Group Management

## User Commands

| Command | Purpose |
|---------|----------|
| `useradd` | Create a new user |
| `passwd` | Set/change password |
| `userdel` | Delete a user |
| `su` | Switch user |
| `usermod` | Modify user account |

### Examples

```bash
sudo useradd john
sudo passwd john
su john
sudo userdel john
sudo usermod -l newuser olduser
```

---

## Group Commands

| Command | Purpose |
|---------|----------|
| `groupadd` | Create group |
| `groupdel` | Delete group |
| `usermod -g` | Add user to group |

Example:

```bash
sudo groupadd developers
sudo usermod -g developers john
```

---

# File Permissions

Linux permissions are divided into:

- **Read (r)**
- **Write (w)**
- **Execute (x)**

Permission categories:

- **User (u)**
- **Group (g)**
- **Others (o)**

### Numeric Permissions

| Number | Permission |
|---------|------------|
| 0 | --- |
| 1 | --x |
| 2 | -w- |
| 3 | -wx |
| 4 | r-- |
| 5 | r-x |
| 6 | rw- |
| 7 | rwx |

Example:

```bash
chmod 755 script.sh
chmod 644 file.txt
```

---

# Ownership Commands

| Command | Purpose | Example |
|---------|----------|---------|
| `chmod` | Change file permissions | `chmod 755 script.sh` |
| `chown` | Change owner | `chown user file.txt` |
| `ls -ld` | View directory permissions | `ls -ld folder` |
| `stat` | Display detailed metadata | `stat file.txt` |

---

# Links

| Command | Purpose | Example |
|---------|----------|---------|
| `ln -s` | Create symbolic (soft) link | `ln -s file.txt shortcut.txt` |
| `ln` | Create hard link | `ln file.txt hardlink.txt` |

---

# Most Frequently Used Commands

```bash
pwd                 # Current directory
ls -la              # List files
cd folder           # Change directory
mkdir project       # Create folder
touch app.py        # Create file
cp file1 file2      # Copy file
mv old new          # Rename file
rm file.txt         # Delete file
cat file.txt        # View file
grep "text" file    # Search text
find . -name "*.py" # Find Python files
ps aux              # Running processes
top                 # Process monitor
df -h               # Disk usage
free -h             # Memory usage
whoami              # Current user
uname -a            # System information
wget URL            # Download file
curl URL            # Fetch URL
chmod 755 file      # Change permissions
chown user file     # Change owner
```

---

# Learning Roadmap

### Beginner
- `pwd`
- `ls`
- `cd`
- `mkdir`
- `touch`
- `cp`
- `mv`
- `rm`
- `cat`

### Intermediate
- `grep`
- `find`
- `sort`
- `wc`
- `chmod`
- `chown`
- `ps`
- `top`
- `df`
- `du`

### Advanced
- User management (`useradd`, `usermod`)
- Group management (`groupadd`)
- Service management (`systemctl`)
- Networking (`ip`, `curl`, `wget`, `ssh-keygen`)
- Package management (`apt-get`)

---

# Tips

- Use `man <command>` to open the manual page for any command.
- Use `history` to view previously executed commands.
- Be cautious with `rm -rf`—it permanently deletes files and directories.
- Prefer `ip` over the deprecated `ifconfig`.
- Use `sudo` only when administrative privileges are required.

---

## Summary

Mastering these Linux commands provides a strong foundation for:

- Linux Administration
- DevOps
- Cloud Computing
- System Administration
- Cybersecurity
- Software Development

Learning these core commands will make terminal usage faster, improve productivity, and prepare you for advanced Linux and server management.
