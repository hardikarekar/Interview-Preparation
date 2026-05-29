## Linux Basics

1. What is Linux?
* Linux is an open-source, Unix-like operating system used for servers, networking, cloud computing, and application support. 
* It manages hardware resources and allows multiple users and processes to run efficiently.

2. What is the difference between Linux and Unix?

| Feature          | Linux                             | Unix                              |
| ---------------- | --------------------------------- | --------------------------------- |
| Definition       | Open-source operating system      | Proprietary operating system      |
| Cost             | Mostly free                       | Usually paid/commercial           |
| Source Code      | Openly available                  | Mostly closed source              |
| Developed By     | Community + companies             | AT&T Bell Labs originally         |
| Flexibility      | Highly customizable               | Less customizable                 |
| Usage            | Servers, cloud, desktops, Android | Enterprise systems, large servers |
| Examples         | Ubuntu, Red Hat Enterprise Linux  | AIX, HP-UX, Solaris               |
| Hardware Support | Runs on many hardware platforms   | Often vendor-specific             |
| Licensing        | GPL (General Public License)      | Commercial licenses               |
* Unix is a proprietary operating system developed originally by Bell Labs, while Linux is an open-source Unix-like operating system. 
* Linux is free and highly customizable, whereas Unix systems are mostly commercial and vendor-specific.

3. What is a Linux distribution?
* A Linux distribution is a complete operating system built using the Linux kernel.
* It includes system utilities, package management tools, libraries, and applications that make Linux usable for servers, desktops, or specialized tasks.

4. Name some popular Linux distributions.

| Distribution | Common Usage                          |
| ------------ | ------------------------------------- |
| Ubuntu       | Desktop, servers, cloud               |
| RHEL         | Enterprise Servers                    |
| CentOS       | Server environments                   |
| Debian       | Stable servers and development        |
| Fedora Linux | Latest Linux features and development |
| Kali Linux   | Cybersecurity and penetration testing |
| Arch Linux   | Advanced users and customization      |
| openSUSE     | Enterprise and desktop use            |
| Rocky Linux  | RHEL-compatible servers               |
| Alma Linux   | Enterprise Linux alternative          |

5. What is the Linux kernel?
* The Linux kernel is the core component of the Linux operating system that manages hardware resources such as CPU, memory, devices, and processes. 
* It acts as an interface between software/applications and the hardware.
* Simple Architecture
```txt
Applications
↓
Shell
↓
Linux Kernel
↓
Hardware
```
* When a user runs a command like `ls` the request goes through the kernel, which accesses the file system and returns the output.
* Linux uses a **monolithic kernel**, meaning many core services run inside the kernel space for better performance.

6. What is the difference between CLI and GUI?

| Feature            | CLI                                      | GUI                                 |
| ------------------ | ---------------------------------------- | ----------------------------------- |
| Full Form          | Command Line Interface                   | Graphical User Interface            |
| Interaction Method | Commands typed using keyboard            | Mouse clicks and graphical elements |
| Speed              | Faster for experienced users             | Easier for beginners                |
| Resource Usage     | Uses less memory and CPU                 | Uses more memory and CPU            |
| Automation         | Easy using scripts                       | Limited automation                  |
| Flexibility        | More powerful for administration         | More user friendly                  |
| Usage              | Servers, administration, troubleshooting | Desktop environments                |
| Example            | Bash terminal in linux                   | GNOME, KDE Desktop                  |

7. What is the root user?
* The root user is the superuser or administrator account in Linux that has complete control over the system.
* The root user can:
	* Install or remove software
	* Create and delete user
	* Change system settings
	* Access all files and directories
	* Start or stop services
	* Modify permissions
* Important Characteristics
	* User ID (UID): 0
	* Access Level: Highest privileges
	* Home directory: /root
	* Restrictions: Almost none

8. What is the home directory in Linux?
* It is the default personal directory assigned to a user where their files, folders, and personal settings are stored.
* When a user logs in, they are usually placed inside their home directory automatically.
* For normal user: `/home/hardik`
* For root user: `/root`
* The home directory stores:
	- Personal files
	- Documents
	- Downloads
	- User-specific configurations
	- Hidden configuration files

9. What are environment variables in Linux?
* Environment variables are dynamic key-value pairs in Linux that store system and user information such as PATH, HOME, and USER. 
* They help configure the behavior of the shell and applications.

| Variable | Purpose                                         |
| -------- | ----------------------------------------------- |
| PATH     | Defines directories where commands are searched |
| HOME     | User's home directory                           |
| USER     | Current logged-in username                      |
| SHELL    | Default shell like bash                         |
| PWD      | Current working directory                       |
* How to view environment variables
	* `printenv`
* How to set a variable
	* `export MYVAR = "Hello Linux"`
* To make it permanent add it in
	* `~/.bashrc`
	* `~/.bash_profile`
	* `/etc/environment`

10. What is the purpose of the PATH variable?
* The PATH variable is an environment variable that tells Linux where to search for executable commands. 
* It allows users to run commands from any directory without specifying their full path.

## File System and Commands

11. What is the Linux file system hierarchy?
* The Linux file system hierarchy is a **standard directory structure** that defines how files and folders are organized in Linux.
* Everything in Linux starts from a single root directory: `/`
* Main directories
	* `/` (Root)
		* The top-level directory of the entire system
		* All files and directories exist under this
	* `/bin`
		* Basic essential commands (used by all users)
		* Example: `ls`, `cp`, `mv`, `cat`
	* `/sbin`
		* System administration commands
		* Used mostly by root user
		* Example: `reboot`, `fdisk`
	* `/etc`
		* Configuration files
		* Example: user settings, network config, service configs
	* `/home`
		* User personal directories
		* Example: `/home/user1` `/home/user2`
	* `/root`
		* Home directory of root user
	* `/var`
		* Variable data (logs, mail, spool files)
		* Example: `/var/log` System logs
	* `/mnt` and `/media`
		* Mount points for external storage
		* USB drives, CDs, external disks

12. What is the difference between absolute and relative paths?
* Absolute path
	* An **absolute path** is the full path starting from the root directory `/`.
	* Example: `/home/user/Documents/file.txt`
	* Key points
		* Always starts with `/`
		- Gives full location from root
		- Works from anywhere in the system
		- Never depends on current directory
- Relative path
	- A **relative path** is the path **relative to your current working directory**.
	- Example
		- If you are in:
			- `/home/user`
		- Then 
			- `Documents/file.txt`
		- Key Points
			- Does NOT start with `/`
			- Depends on current location
			- Shorter and flexible
			- Changes meaning based on where you are

13. Explain the use of pwd command.
* The `pwd` command is used to display the current working directory in Linux. 
* It shows the full path of the directory where the user is currently located.

14. Explain the use of ls command.
* The `ls` command stands for **list**. 
* It is used to **display the contents of a directory** such as files and subdirectories.

15. How do you create a file in Linux?
* Using `touch` command:
	* `touch file.txt`
	* What it does?
		* Creates an empty file if it does not exist.
		* Updates timestamp if already exists.
* Using `cat` command
	* `cat > file.txt`
	* Then type content and press `ctrl + D`
	* What it does
		* Creates a file
		* Allows you to add content immediately
* Using `echo` command
	* `echo "Hello Linux" > file.txt`
	* What it does
		* Creates a file
		* Writes single line content into it
* Using text editors
	* Using nano: `nano file.txt`
	* Using vi/vim: `vi file.txt`
	* What it does
		* Opens file in editor
		* Allows full editing and saving

15. How do you create a directory in Linux?
* A directory in linux is created using `mkdir` command.
* `-p` is used to create nested directories. `mkdir -p parent/child/grandchild`
    
16. What is the difference between cp and mv?
* `cp`
	* `cp` command copies files or directories from one location to another.
	* `cp file1.txt /home/user/Documents`
	* Original file remains, new copy is created.
* `mv`
	* `mv` command moves files/directories or renames them.
	* `mv file1.txt /home/user/Documents`
	* File is removed from original location, file exists only in new location.

16. How do you delete files and directories?
* Delete a file
	* `rm  file1.txt`
* Delete multiple files
	* `rm file1.txt file2t.txt`
* Delete an empty directory
	* `rmdir testdir`
* Delete a directory with contents
	* `rm -r testdir`
		* `-r` means recursive
* Force delete without confirmation
	* `rm -rf testdir`
		* `-r`: recursive, `-f`: force delete

17. What does rm -rf do?
* Used to forcefully and recursively delete files and directories.
* `-r` option removes directories and their contents recursively.
* `-f` forces deletion without confirmation prompts.

18. What is the use of touch command?
* To create an empty file
	* `touch file1.txt`
* To create multiple files
	* `touch file1.txt file2.txt`
* To update file timestamp
	* `touch file1.txt`
		* Updates access time, modification time without changing file content.

19. Explain the cat command.
* `cat` command stands for "concatenate".
* Display file content.
	* `cat file1.txt`
* Create a file using `cat`
	* `cat file1.txt`
		* Then you type content.
	* Press `ctrl+D` to save.
* Append content to a file.
	* `cat >> file1.txt`
		* Add content without overwriting existing data.
* Combine Multiple files
	* `cat file1.txt file2.txt`
	* Displays combined content.
* Create new file from multiple files
	* `cat file1.txt file2.txt > combined.txt`


20. Explain the use of more and less commands.
* `more` command
	* `more file1.txt`
	* Display file one page at a time.
	* Allows forward navigation only
* `less` command
	* `less file1.txt`
	* Allows forward and backward navigation

21. What is the difference between head and tail?
* `head`
	* `head file1.txt`
		* Display beginning of a file.
	* `head -5 file1.txt`
		* Show specific number of lines.
* `tail`
	* `tail file1.txt`
		* Shows last lines of a file.
	* `tail -5 file1.txt`
		* Show specific number of lines.
* Real time monitoring with `tail`
	* `tail -f /var/log/syslog`
		* `-f` means follow the file continuously.
	* Very useful for monitoring logs, troubleshooting services.

22. How do you search for text inside a file?
* Text inside a file is commonly done by using `grep` command.
* `grep "text" file1.txt`
* Common grep options
	* Ignore case
		* `grep -i "text" file1.txt`
	* Show Line Numbers 
		* `grep -n "text" file1.txt`
	* Search recursively in directories
		* `grep -r "error" /var/log`
			* Searches inside all files under `/var/log`

23. What is grep command?
* `grep` command is used to search specific text or patterns inside files.
* Stands for "Global Recursive Expression Print"
* Basic Syntax
	* `grep "pattern" filename`
* Common uses of `grep`
	* Search text in files
	* Find errors in logs
	* Search configuration entries'
	* Filter command outputs
* Important Options
	* Ignore Case
		* `grep -i "text" file1.txt`
	* Show Line Numbers
		* `grep -n "text" file1.txt`
	* Recursive Search
		* `grep -r "error" /var/auth.log`
	* Count Matches
		* `grep -c "text" file1.txt`
* Using grep with pipes
	* `ps -ef | grep ssh`
		* Searches running processes related to SSH
* Why grep is important
	* Troubleshooting
	* Log Analysis
	* Monitoring 
	* Process Filtering

24. What is the use of find command?
* `find` command used to search for files and directories based on
	* Name
	* Type
	* Size
	* Ownership
	* Permissions
	* Time 
* Basic Syntax
	* `find <path> <condition>`
* Common uses 
	* Find file by name
		* `find /home -name file1.txt`
	* Case Insensitive search
		* `find /home -iname file1.txt`
	* Find directories only
		* `find /home -d`
	* Find files only
		* `find /home -type f`
	* Find files by size
		* `find / -size +100M`
	* Find files by permission
		* `find / -perm 777`

25. What is the difference between locate and find?

| **Feature**     | **Find**                                  | **Locate**                |
| --------------- | ----------------------------------------- | ------------------------- |
| Search Method   | Searches filesystem in real time          | Uses prebuilt database    |
| Speed           | Slower                                    | Faster                    |
| Accuracy        | Always up to date                         | May show outdated results |
| Flexibility     | Very powerful and advanced                | Limited search options    |
| Resource Usage  | Higher                                    | Lower                     |
| Search Criteria | Name, size, permission, owner, time, etc. | Mostly filename based     |
* `find` command
	* `find /home -iname file1.txt`
	* Searches actual filesystem
	* Accurate
	* Supports advanced filters
* `locate` command
	* `locate file1.txt`
	* Searches from indexed database
	* Very fast
	* Database may not be updated immediately.
* Why `locate` command can show old results?
	* `locate` uses a database maintained by:
		* `updatedb`
	* If database is outdated
		* New files may not appear
		* Deleted files may still appear

26. How do you count lines, words, and characters in a file?
* `wc` command is used to count lines, words, characters, bytes in a file.
* stands for "word count"
* Basic syntax
	* `wc filename`
* `wc file1.txt`
	* ` 1  2 12 /home/file1.txt`
		* `1`-> lines, `2` -> words, `12` -> characters/bytes
* `-l`, `-w`, `-m` are used for counting lines, words, characters separately.

27. What is the use of awk command?


28. What is the use of sed command?
* stands for "Stream Editor"
* It is used to
	* Search text
	* Replace text
	* Edit files
	* Filter output
	* Modify data automatically 
* Basic syntax
	* `sed 'operation' filename`
		* `s/old/new/`
			* `s` -> substitute; `old` -> text to replace; `new` -> replacement text
* Most common use
	* Search and Replace
		* Suppose a file contains 'Linux is good'
			* `sed 's/Linux/Unix/' file1.txt`
* Without `-i`, `sed` only changes output temporarily.
* Modify file permanently
	* `sed -i 's/Linux/Unix/' file1.txt`

29. What is a symbolic link?
* A symlink or symbolic link is a special file that acts as a pointer or shortcut to another file or directory.
* Instead of containing actual data, it stores the path to its target.
* `ln -s /path/to/original /path/to/symlink`
* Key properties
	* Has its own inode, separate from the target.
	* Contains a path string (relative or absolute) rather than data.
	* Can point to directories not just files.
	* Can point across filesystems and partitions.
	* If target is deleted, symlink becomes broken.

30. What is a hard link?
* A hard link is a directory entry that points to the same inode as another file.
* `ln /path/to/original /path/to/hardlink`
* Key properties:
	* Shares the same inode as the target - they are the same file
	* Changes to one are instantly visible through the other
	* Deleting the original doesn't affect the hard link - data persists
	* Cannot cross filesystems (inodes are filesystem local)
	* Cannot link to directories (to prevent circular filesystem loops)

31. Difference between hard link and soft link?

| Property                    | Hard Link                                             | Soft Link                               |
| --------------------------- | ----------------------------------------------------- | --------------------------------------- |
| Definition                  | A direct reference to the original file's inode       | A shortcut that points to the file path |
| Inode                       | Shares the same inode as the original file            | Has a different inode                   |
| If original file is deleted | Still works because data exists through the hard link | Breaks                                  |


32. What is inode in Linux?
* Index node
* Is a data structure on disk that stores metadata about a file - everything except its name and actual content
* What an inode stores
	* Inode number - Unique ID within the filesystem
	* File Type - Regular file, directory, symlink, etc.
	* Permissions - Read/write/execute for owner, group, others
	* Owner - UID and GID
	* File size - in bytes
	* Timestamps - Created, modified, accessed
	* Hard link count - How many directory entries point to this inode
	* Data block pointers - Where the actual file content lives on disk
*  

## Permissions and Ownership

36. What are file permissions in Linux?
    
37. Explain read, write, and execute permissions.
    
38. What is chmod command?
    
39. What is chown command?
    
40. What is chgrp command?
    
41. Explain numeric permissions like 755 and 777.
    
42. What is umask?
    
43. What are SUID, SGID, and Sticky Bit?
    
44. How do you check permissions of a file?
    
45. Why is 777 permission considered risky?
    

## Users and Groups

46. How do you create a user in Linux?
    
47. What is the use of useradd command?
    
48. How do you delete a user?
    
49. How do you change a user password?
    
50. How do you create a group?
    
51. What is the /etc/passwd file?
    
52. What is the /etc/shadow file?
    
53. What is sudo?
    
54. Difference between su and sudo?
    
55. How do you check current logged-in users?
    

## Process Management

56. What is a process in Linux?
    
57. How do you view running processes?
    
58. Difference between ps and top?
    
59. What is the kill command?
    
60. What is PID?
    
61. What is a zombie process?
    
62. What is a daemon process?
    
63. What is nice and renice command?
    
64. How do you run a process in the background?
    
65. How do you stop a running process?
    

## Package Management

66. What is package management in Linux?
    
67. Difference between RPM and DEB packages?
    
68. What is yum command?
    
69. What is dnf command?
    
70. What is apt command?
    
71. How do you install a package in Linux?
    
72. How do you update packages?
    
73. How do you remove a package?
    
74. How do you check installed packages?
    
75. What is repository in Linux?
    

## Networking

76. What is an IP address?
    
77. Difference between public and private IP?
    
78. What is DNS?
    
79. What is the use of ping command?
    
80. What is traceroute command?
    
81. What is netstat command?
    
82. What is ss command?
    
83. What is SSH?
    
84. How do you connect to a remote Linux server?
    
85. What is SCP command?
    
86. What is SFTP?
    
87. What is firewall in Linux?
    
88. What is SELinux?
    
89. What is the difference between TCP and UDP?
    
90. How do you check open ports in Linux?
    

## Disk and Storage

91. How do you check disk usage in Linux?
    
92. What is df command?
    
93. What is du command?
    
94. What is mounting in Linux?
    
95. What is the /etc/fstab file?
    
96. What is swap memory?
    
97. Difference between swap and RAM?
    
98. What is LVM in Linux?
    
99. How do you check memory usage in Linux?
    
100. What is the use of free command?
    

---

# Important Practical Linux Commands for Interviews

```bash
pwd
ls -l
cd
mkdir
rm -rf
cp
mv
cat
less
grep
find
chmod
chown
ps -ef
top
kill
systemctl status
systemctl restart
ip a
ping
df -h
du -sh
free -m
```

---

# Frequently Asked Scenario-Based Linux Questions

1. A server is slow. How will you troubleshoot it?
    
2. Disk space is full. What steps will you take?
    
3. A service is not starting. How will you debug it?
    
4. SSH is not working. What will you check?
    
5. A user cannot access a file. How will you troubleshoot permissions?
    
6. CPU usage is very high. Which commands will you use?
    
7. Memory usage is high. How do you identify the issue?
    
8. How do you restart a Linux service?
    
9. How do you check logs in Linux?
    
10. How do you identify which process is using a port?
    

---

# Important Linux Log File Locations

```bash
/var/log/messages
/var/log/secure
/var/log/auth.log
/var/log/syslog
/var/log/dmesg
```

---

# Important Services Commands

```bash
systemctl start service_name
systemctl stop service_name
systemctl restart service_name
systemctl enable service_name
systemctl disable service_name
systemctl status service_name
```

---

# Tips for Linux Interviews

- Practice commands daily on a Linux VM.
    
- Learn troubleshooting commands practically.
    
- Understand permissions and networking clearly.
    
- Be comfortable with SSH and services.
    
- Learn basic shell scripting.
    
- Practice explaining commands with examples.
    
- Focus on real-world troubleshooting scenarios.
    
- Learn differences between Linux distributions.
    
- Practice package management commands.
    
- Revise logs, processes, and file system concepts.