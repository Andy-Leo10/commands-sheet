# Linux commands

- [Linux commands](#linux-commands)
  - [File Operations:](#file-operations)
    - [ls - List directory contents](#ls---list-directory-contents)
    - [cat - Concatenate and display file content](#cat---concatenate-and-display-file-content)
    - [more - View file content page by page](#more---view-file-content-page-by-page)
    - [less - View file content with backward navigation](#less---view-file-content-with-backward-navigation)
    - [head - Display the beginning of a file](#head---display-the-beginning-of-a-file)
    - [tail - Display the end of a file](#tail---display-the-end-of-a-file)
    - [cp - Copy files and directories](#cp---copy-files-and-directories)
    - [mv - Move or rename files and directories](#mv---move-or-rename-files-and-directories)
    - [rm - Remove files and directories](#rm---remove-files-and-directories)
    - [touch - Change file timestamps or create a new file](#touch---change-file-timestamps-or-create-a-new-file)
  - [Directory Operations:](#directory-operations)
    - [pwd - Print working directory](#pwd---print-working-directory)
    - [cd - Change directory](#cd---change-directory)
    - [mkdir - Create a new directory](#mkdir---create-a-new-directory)
    - [rmdir - Remove directory](#rmdir---remove-directory)
  - [Process Management:](#process-management)
    - [top - Display tasks](#top---display-tasks)
    - [htop - Interactive process viewer](#htop---interactive-process-viewer)
    - [bg - Put a process in background](#bg---put-a-process-in-background)
    - [fg - Put a process in foreground](#fg---put-a-process-in-foreground)
    - [kill - Terminate a process](#kill---terminate-a-process)
  - [File Permissions:](#file-permissions)
    - [chmod - Change file permissions](#chmod---change-file-permissions)
    - [chown - Change file owner and group](#chown---change-file-owner-and-group)
    - [chgrp - Change group ownership](#chgrp---change-group-ownership)
  - [Networking:](#networking)
    - [ping - Send ICMP ECHO\_REQUEST to network hosts](#ping---send-icmp-echo_request-to-network-hosts)
    - [ifconfig - Display or configure a network interface](#ifconfig---display-or-configure-a-network-interface)
    - [netstat - Network statistics](#netstat---network-statistics)
    - [ssh - OpenSSH remote login client](#ssh---openssh-remote-login-client)
    - [scp - Secure copy (remote file copy program)](#scp---secure-copy-remote-file-copy-program)
  - [Disk Usage:](#disk-usage)
    - [df - Report file system disk space usage](#df---report-file-system-disk-space-usage)
    - [du - Estimate file and directory space usage](#du---estimate-file-and-directory-space-usage)
  - [Searching:](#searching)
    - [find - Search for files in a directory hierarchy](#find---search-for-files-in-a-directory-hierarchy)
    - [grep - Print lines matching a pattern](#grep---print-lines-matching-a-pattern)
  - [System Information:](#system-information)
    - [uname - Print system information](#uname---print-system-information)
    - [hostname - Show or set the system's host name](#hostname---show-or-set-the-systems-host-name)
    - [dmesg - Print or control the kernel ring buffer](#dmesg---print-or-control-the-kernel-ring-buffer)
  - [Compression/Decompression:](#compressiondecompression)
    - [tar - An archiving utility](#tar---an-archiving-utility)
    - [gzip - Compress or expand files](#gzip---compress-or-expand-files)
    - [gunzip - Compress or expand files](#gunzip---compress-or-expand-files)
    - [zip - Package and compress (archive) files](#zip---package-and-compress-archive-files)
    - [unzip - List, test and extract compressed files in a ZIP archive](#unzip---list-test-and-extract-compressed-files-in-a-zip-archive)
  - [Package Management:](#package-management)
    - [apt-get - APT package handling utility (Debian)](#apt-get---apt-package-handling-utility-debian)
    - [yum - Package manager (RHEL/CentOS)](#yum---package-manager-rhelcentos)
    - [dnf - Next-generation package manager (Fedora)](#dnf---next-generation-package-manager-fedora)
    - [pacman - Package manager (Arch)](#pacman---package-manager-arch)

## File Operations:
### ls - List directory contents
```
ls -l # List directory contents in long format
ls -a # List directory contents including hidden files
ls -lh # List directory contents in long format with human-readable file sizes
```

### cat - Concatenate and display file content
```
cat file1 file2 # Concatenate and display multiple files
cat file1 file2 > newfile # Concatenate and redirect output to a new file
cat file1 >> file2 # Concatenate and append output to an existing file
```

### more - View file content page by page
```
more file # View file content page by page
more +n file # View file content starting from line n
```

### less - View file content with backward navigation
```
less file # View file content with backward navigation
less +n file # View file content starting from line n
```

### head - Display the beginning of a file
```
head file # Display the beginning of a file
head -n 10 file # Display the first 10 lines of a file
```

### tail - Display the end of a file
```
tail file # Display the end of a file
tail -n 10 file # Display the last 10 lines of a file
```

### cp - Copy files and directories
```
cp file1 file2 # Copy file1 to file2
cp -r dir1 dir2 # Copy dir1 to dir2 recursively
cp -i file1 file2 # Copy file1 to file2 interactively
```

### mv - Move or rename files and directories
```
mv file1 file2 # Move or rename file1 to file2
mv -i file1 file2 # Move or rename file1 to file2 interactively
mv dir1 dir2 # Move or rename dir1 to dir2
```

### rm - Remove files and directories
```
rm file # Remove file
rm -r dir # Remove directory and its contents recursively
```

### touch - Change file timestamps or create a new file
```
touch file # Create a new file
```

## Directory Operations:
### pwd - Print working directory
```
pwd # Print the current working directory
```

### cd - Change directory
```
cd /path/to/directory # Change to a specific directory
cd .. # Change to the parent directory
cd ~ # Change to the home directory
```

### mkdir - Create a new directory
```
mkdir directory # Create a new directory
mkdir -p directory/subdirectory # Create nested directories
```

### rmdir - Remove directory
```
rmdir directory # Remove an empty directory
rmdir -p directory/subdirectory # Remove nested directories
```

## Process Management:
```
ps - Report a snapshot of current processes
ps -e # Display all processes
ps -ef # Display all processes with full information
ps -aux # Display all processes with user-oriented format
ps -p PID # Display process information by PID
ps -faux | grep process_name # Display process information by name
```

### top - Display tasks
```
top # Display real-time system information
```

### htop - Interactive process viewer
```
htop # Display interactive process viewer
```

### bg - Put a process in background
```
bg %job_number # Put a job in background by job number
```

### fg - Put a process in foreground
```
fg %job_number # Put a job in foreground by job number
```

### kill - Terminate a process
```
kill PID # Terminate a process by PID
kill -9 PID # Forcefully terminate a process by PID
```

## File Permissions:
### chmod - Change file permissions
```
chmod 755 file # Change file permissions to 755
chmod +x file # Add execute permission to a file
chmod -w file # Remove write permission from a file
```

### chown - Change file owner and group
```
chown user:group file # Change file owner and group
chown user file # Change file owner
```

### chgrp - Change group ownership
```
chgrp group file # Change group ownership
```

## Networking:
### ping - Send ICMP ECHO_REQUEST to network hosts
```
ping host # Ping a host
ping -c 5 host # Ping a host 5 times
```

### ifconfig - Display or configure a network interface
```
ifconfig # Display network interface information
ifconfig eth0 up # Enable a network interface
ifconfig eth0 down # Disable a network interface
```

### netstat - Network statistics
```
netstat -tuln # Display listening ports
netstat -r # Display routing table
```

### ssh - OpenSSH remote login client
```
ssh user@host # Connect to a remote host
ssh -p port user@host # Connect to a remote host on a specific port
```

### scp - Secure copy (remote file copy program)
```
scp file user@host:/path # Copy a file to a remote host
scp user@host:/path/file /local/path # Copy a file from a remote host
for install scp use:
sudo apt-get install openssh-client
```

## Disk Usage:
### df - Report file system disk space usage
```
df -h # Display disk space usage in human-readable format
```

### du - Estimate file and directory space usage
```
du -h # Display file and directory space usage in human-readable format
du -sh * # Display space usage of all files and directories in the current directory
```

## Searching:
### find - Search for files in a directory hierarchy
```
find /path -name filename # Search for a file by name
find /path -type d # Search for directories
find /path -type f # Search for files
```

### grep - Print lines matching a pattern
```
grep pattern file # Print lines matching a pattern in a file
grep -r pattern /path # Recursively search for a pattern in a directory
```

## System Information:
### uname - Print system information
```
uname -a # Print all system information
uname -r # Print kernel release information
uname -m # Print machine hardware name
```

### hostname - Show or set the system's host name
```
hostname # Show the system's host name
hostname newname # Set the system's host name
hostname -I # Display the system's IP address
```

### dmesg - Print or control the kernel ring buffer
```
dmesg # Print kernel messages
dmesg -T # Print kernel messages with human-readable timestamps
```

## Compression/Decompression:
### tar - An archiving utility
```
tar -cvf archive.tar file1 file2 # Create a tar archive
tar -xvf archive.tar # Extract a tar archive
tar -tvf archive.tar # List contents of a tar archive
```

### gzip - Compress or expand files
```
gzip file # Compress a file
gzip -d file.gz # Decompress a file
```

### gunzip - Compress or expand files
```
gunzip file.gz # Decompress a file
```

### zip - Package and compress (archive) files
```
zip archive.zip file1 file2 # Create a zip archive
```

### unzip - List, test and extract compressed files in a ZIP archive
```
unzip archive.zip # Extract a zip archive
```

## Package Management:
### apt-get - APT package handling utility (Debian)
```
apt-get update # Update package lists
apt-get upgrade # Upgrade installed packages
apt-get install package # Install a package
apt-get remove package # Remove a package
apt-get autoremove # Remove unused packages
apt-get clean # Clean up package cache
```

### yum - Package manager (RHEL/CentOS)
```
yum update # Update installed packages
yum install package # Install a package
yum remove package # Remove a package
yum clean all # Clean up package cache
```

### dnf - Next-generation package manager (Fedora)
```
dnf update # Update installed packages
dnf install package # Install a package
dnf remove package # Remove a package
dnf clean all # Clean up package cache
```

### pacman - Package manager (Arch)
```
pacman -Syu # Update installed packages
pacman -S package # Install a package
pacman -R package # Remove a package
pacman -Sc # Clean up package cache
```
