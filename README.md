# Linux Commands

Welcome to the Linux Commands Reference repository! This collection is designed to help beginners and experienced users explore and understand essential Linux commands. Whether you're troubleshooting, scripting, or just learning, these commands will help you navigate the Linux ecosystem.

## Contents

The repository includes folders and files grouped by categories of Linux commands:

| # | Category | Description |
|---|----------|-------------|
| 1 | Navigate the file system | Move through the filesystem and view the content of a file |
| 2 | Manage file content in Bash | Commands for creating, deleting, copying, and moving files |
| 3 | Filter content | Find files and content of files, and filter output |
| 4 | Manage users and permissions | Change user permissions and groups |
| 5 | Get help in Linux | Find info about commands |
| 6 | System Monitoring | Tools to monitor system performance, resource usage, and processes |
| 7 | Networking | Basic and advanced commands for managing networks and connections |
| 8 | Permissions | Managing file ownership and access control |
| 9 | Package Management | Installing, removing, and managing software packages |
| 10 | Disk Usage | Commands for analyzing disk space and managing partitions |
| 11 | Scripting Basics | Useful one-liners and examples for bash scripting |

## Learn and Test

- Open the files to view command explanations and examples.
- Run the commands in a Linux terminal to see them in action.

## Folder Structure

```
linux-commands/
├── navigate-the-file-system/
│   ├── pwd     – show the current position in the filesystem
│   ├── ls      – list the files in the current position
│   ├── cat     – print the content of a file in the shell
│   ├── head    – show the first 10 rows of a file
│   └── tail    – show the last 10 rows of a file
│
├── manage-file-content-in-bash/
│   ├── cp      – copy a file or directory
│   ├── mkdir   – create an empty directory
│   ├── mv      – move a file or directory
│   ├── nano    – open or create files in the nano editor
│   ├── rm      – remove a file
│   ├── rmdir   – remove an empty directory
│   └── touch   – create a file
│
├── filter-content/
│   ├── find    – search for directories and files that meet specific criteria
│   ├── grep    – search for a specific string in a file
│   └── |       – (piping) send the standard output of a command as standard input to the next command
│
├── manage-users-and-permissions/
│   ├── chmod     – change permissions on files and directories
│   ├── chown     – change ownership of files and directories
│   ├── groupdel  – delete a group from the system (use with sudo)
│   ├── useradd   – add a user to the system (use with sudo)
│   ├── userdel   – delete a user from the system (use with sudo)
│   └── usermod   – modify an existing user (use with sudo)
│
├── get-help-in-linux/
│   ├── apropos – search man pages for a specific string
│   ├── man     – show a command's full description
│   └── whatis  – show a 1-line command description
│
├── package-management/
│   ├── apt
│   ├── yum
│   └── dnf
│
├── disk-usage/
│   ├── df
│   ├── du
│   └── lsblk
│
├── scripting-basics/
│   ├── bash-loops
│   ├── file-handling
│   └── variables
│
├── system-monitoring/
│   ├── top
│   ├── htop
│   └── ps
│
└── networking/
    ├── ping
    ├── netstat
    └── ssh
```
