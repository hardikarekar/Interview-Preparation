## 1. Linux
### Linux Fundamentals
- What is Linux?
	- Linux is a free, open-source, Unix like operating system kernel created by Linus Torvalds in 1991.

- Linux vs Unix
	- Linux: Free, open source and community driven with frequent updates.
	- Unix: Proprietary operating system traditionally licensed for heavy enterprise and workstation use.

- Linux distributions
	- Debian Family
		- Debian based distributions are famous for their reliability and vast software repositories.
		- They primarily use the `.deb` package format and APT package manager.
		- Debian, Ubuntu, Linux Mint, Kali Linux
	- Redhat / Fedora family:
		- Red Hat / Fedora family is standard for corporate environments, web servers and cutting edge software development.
		- It uses on `.rpm` package format and DNF / YUM package manager.
		- Fedora, RHEL, Rocky Linux, AlmaLinux.
	- Arch Family:
		- Arch based linux distros follow a rolling-release model meaning you install the system once and it receives continuous-incremental updates. 
		- It uses the Pacman package manager.
		- Arch Linux, Manjaro.

- Linux kernel
	- The linux kernel is the core foundation software program if a Linux operating system.
	- It acts as a mediator and bridge between computer's hardware and its software applications.
	- Core Responsibilities of the Kernel:
		- The kernel manages four primary jobs to keep a computer running smoothly.
		- Hardware Management:
			- It communicates directly with the physical components like CPU, memory, hard drives and graphic cards using built-in software called device drivers.
		- Memory Management:
			- It tracks how much RAM is being used, decides which application gets access to memory and prevents programs from crashing into or modifying each other's data.
		- Process Scheduling:
			- It decides exactly when and for how long a program gets to use the CPU. 
			- This allows your computer to multitask seamlessly by switching between tasks in milliseconds.
		- File System and Storage Control:
			- It manages how data is saved, organized, read, and deleted on your storage drivers (SSD / HDD).
	- Architecture:
		- The Linux kernel is a monolithic kernel.
		- This means that all major operating system services including device drivers, file system management, memory management, process schedulers - run together inside a single shared memory space called Kernel Space.
	- What is difference between Kernel Space and User Space?
		- Kernel Space is a secure, privileged area of memory reserved exclusively for running the core linux kernel, device drivers and extensions.
		- It has unrestricted access to all hardware.
		- User Space is the restricted memory area where normal user applications (like web browsers, terminal shells, text editors) run.
		- Applications cannot touch hardware directly; they must safely request permission from the kernel.
	- How does a User Space Application talk to the Kernel?
		- Applications use System Calls (SysCalls).
		- System Call is a programmatic request (like open(), read(), write()) sent from an application to the kernel asking it to perform a privileged task such as reading a file from a disk.
	- What is a Kernel Panic and what causes it?
		- Kernel Panic is a safety mechanism triggered by OS when it encounters critical error from which it cannot safely recover.
		- It is equivalent to BSOD (Windows Blue Screen Of Death).
		- Common Causes: Corrupt hard drive sectors, faulty RAM, bug in newly loaded device driver, missing root filesystem during boot.
	- What are the main states a process can be in within the Kernel?
		- Running / Runnable (TASK_RUNNING)
			- Process is either currently executing on CPU or waiting in scheduler queue to run.
		- Interruptible Sleep (TASK_INTERRUPTIBLE)
			- Process is blocked, waiting for event / signal (like user input or disk I/O).
			- It can be woken up by signals.
		- Uninterruptible Sleep (TASK_UNINTERRUPTIBLE)
			- Process is waiting directly on hardware I/O and cannot be interrupted or killed by a signal until hardware responds.
		- Zombie (EXIT_ZOMBIE)
			- Process has finished executing but its entry remains in process table so its parent can read its exit status.
	- What is difference between Hard Link and Soft (Symbolic) Link at the Kernel / inode level?
		- Hard Link
			- Every file has inode that stores its metadata and location on disk. Hard Link points directly to this inode number.
			- If original file deleted, data remains accessible through hard link.
			- Cannot cross filesystems.
			- `ln path_to_original_file path_to_new_hard_link`
		- Soft (Symbolic) Link
			- Special type of file - points to another file/directory by storing its pathname, like a desktop shortcut.
			- It has its own unique inode and distinct permissions separate from target file.
			- Can bridge different partitions, volumes, file systems.
			- If original file deleted soft link breaks.
			- `ln -s [target_path] [link_name]`


- Shell and Bash
	- What is shell?
		- Command line interpreter that allows user to interact with operating system.
		- Accepts command from user, interprets them and communicates with Linux kernel to execute those commands.
	- What is bash?
		- Bourne Again Shell.
		- improved version of original bourne shell.

- CLI vs GUI
- Linux boot process
- Linux filesystem hierarchy
- `/etc`, `/var`, `/home`, `/tmp`, `/opt`, `/usr`, `/proc`
- Absolute vs relative paths
### Files and Directories
- `ls`
- `cd`
- `pwd`
- `cp`
- `mv`
- `rm`
- `mkdir`
- `touch`
- `find`
- `locate`
- `file`
- `stat`
### Permissions
- Read/write/execute
- `chmod`
- `chown`
- `chgrp`
- Numeric permissions
- Symbolic permissions
- `umask`
- SUID, SGID, Sticky Bit
### Users and Groups
- `useradd`
- `usermod`
- `userdel`
- `passwd`
- `groupadd`
- `/etc/passwd`
- `/etc/shadow`
- `/etc/group`
- sudo
- Root user
### Processes
- Process vs service
- `ps`
- `top`
- `htop`
- `kill`
- `pkill`
- `killall`
- Background/foreground processes
- `jobs`
- `nohup`
### Services
- `systemctl`
- Start/stop/restart
- Enable/disable
- Service status
- `journalctl`
- systemd
### Disk and Storage
- `df`
- `du`
- `lsblk`
- `mount`
- `umount`
- Disk partitions
- Filesystems
- Inodes
- LVM basics
### Networking in Linux
- `ip`
- `ss`
- `ping`
- `traceroute`
- `nslookup`
- `dig`
- `curl`
- `wget`
- `netstat`
- `/etc/hosts`
- `/etc/resolv.conf`
### Logs and troubleshooting
- `/var/log`
- `journalctl`
- `grep`
- `awk`
- `sed`
- `tail`
- `head`
- `less`
- `cat`
### Package Management
- RPM
- YUM/DNF
- APT
- Installing/updating/removing packages
### SSH
- SSH architecture
- SSH keys
- `ssh`
- `scp`
- `sftp`
- `sshd_config`
- SSH troubleshooting
- Password vs key authentication
#### Must practice linux scenarios
- Server is down — how do you troubleshoot?
- Disk is 100% full.
- CPU utilization is 100%.
- Memory utilization is high.
- Application is not starting.
- Service keeps stopping.
- SSH connection is failing.
- Port is not reachable.
- DNS is not resolving.
- Log file is continuously growing.
- User cannot access a file.
- Permission denied error.

## 2. Windows
### Fundamentals
- Windows Server basics
- Windows client vs server
- Windows services
- Windows Registry
- Event Viewer
- Task Manager
- Computer Management
### Active Directory
- What is Active Directory?
- Domain
- Domain Controller
- Forest
- Tree
- OU
- Users
- Groups
- Group Policy
- LDAP
- Kerberos
- NTLM
- Authentication vs authorization
### DNS and DHCP
- Windows DNS
- DNS records
- A
- AAAA
- CNAME
- MX
- PTR
- DNS troubleshooting
- DHCP
- IP allocation
- Reservations
### Windows troubleshooting
- Event Viewer
- Services
- Task Manager
- Resource Monitor
- Device Manager
- Performance Monitor
- Remote Desktop
### Windows Commands
* ipconfig 
* ping 
* tracert 
* nslookup 
* netstat 
* tasklist 
* taskkill 
* hostname 
* whoami 
* systeminfo 
* sfc
* DISM 
* gpupdate 
* gpresult
### Powershell basics
- What is PowerShell?
- Cmdlets
- `Get-Process`
- `Get-Service`
- `Get-EventLog`
- `Get-ComputerInfo`
- `Test-NetConnection`
- Variables
- Pipes
### Windows Security
- NTFS permissions
- Share permissions
- UAC
- Windows Firewall
- Antivirus/EDR basics
- Local vs domain accounts

## 3. Networking
### Fundamentals
- What is a network?
- LAN/WAN
- Client-server architecture
- OSI model
- TCP/IP model
- TCP vs UDP
- MAC vs IP address
- IPv4
- IPv6 basics
### IP Addressing
- Public vs private IP
- Static vs dynamic IP
- Subnet mask
- CIDR
- Default gateway
- Network address
- Broadcast address
- Host address
- Practice subnetting
### Important protocols
* HTTP
* HTTPS
* SSH
* FTP
* SFTP
* DNS
* DHCP
* SMTP
* POP3
* IMAP
* RDP
* SNMP
* ICMP
* LDAP
### Networking Troubleshooting
Learn this flow:
Application → DNS → IP → Route → Firewall → Port → Service → Application
### Scenario Based Questions
- Website isn't opening
- Server cannot connect to another server
- Ping works but application doesn't
- DNS resolution fails
- Port is blocked
- SSH doesn't work
- RDP doesn't work
- Intermittent connectivity
- High latency
- Packet loss
- Firewall blocking traffic
## 4. Database / SQL
### Fundamentals
- What is a database?
- DBMS vs RDBMS
- Table
- Row
- Column
- Primary key
- Foreign key
- Index
- Constraints
- Relationships
### SQL
* SELECT 
* WHERE 
* ORDER BY 
* GROUP BY 
* HAVING 
* DISTINCT 
* LIMIT
### Joins
- INNER JOIN
- LEFT JOIN
- RIGHT JOIN
- FULL JOIN
### CRUD
* SELECT 
* INSERT 
* UPDATE 
* DELETE
### Aggregation
* COUNT() 
* SUM() 
* AVG() 
* MIN() 
* MAX()
### Database Troubleshooting
- Database connection failure
- Authentication failure
- Connection timeout
- High database CPU
- Slow query
- Locking
- Deadlock
- Connection pool
- Database service down
- Disk full
- Transaction basics
- Backup/restore basics
### SQL Server Basics
- SQL Server
- SSMS
- SQL Server services
- Database vs instance
- Tables
- Stored procedures
- SQL Agent
- Logs
- Basic backup/restore concepts
## 5. Application Support
### Application Architecture
Understand:
User 
↓ 
Browser 
↓ 
Web Server 
↓ 
Application Server 
↓ 
Database

Client → Load Balancer → Web Server → Application → Database
### Application Troubleshooting
Learn how to investigate:
- Application down
- HTTP 500
- HTTP 404
- HTTP 401
- HTTP 403
- HTTP 502
- HTTP 503
- Slow application
- Login failure
- Database connection failure
- API failure
- Timeout
- Authentication issue
### Logs
Understand:
- Application logs
- Web server logs
- System logs
- Error logs
- Access logs
Learn how to identify:
Timestamp → Error → Exception → Component → Root cause

## 6. Web Servers
Learn **Nginx + IIS + Apache basics**
### Nginx
- What is Nginx?
- Web server vs reverse proxy
- Configuration files
- Virtual hosts/server blocks
- Ports
- Access/error logs
- Reverse proxy
- SSL/TLS basics
### IIS
- IIS basics
- Application pools
- Websites
- Bindings
- HTTP/HTTPS
- IIS logs
- Application pool failures
- Windows authentication
## 7. APIs / Postman
Learn:
- What is an API?
- REST API
- HTTP methods
- GET
- POST
- PUT
- PATCH
- DELETE
- Headers
- Body
- JSON
- Authentication
- Bearer token
- Basic authentication
- Status codes
Know these:
200, 201, 400, 401, 403, 404, 405, 409, 500, 502, 503, 504

## 8. Git and Github
Learn:
* git clone
* git status
* git add
* git commit
* git push
* git pull
* git fetch
* git branch
* git checkout
* git switch
* git merge
Also understand:
- Repository
- Branch
- Commit
- Merge
- Pull request
- `.gitignore`

## 9. Cloud Basics
### EC2
- What is EC2?
- AMI
- Instance types
- Key pairs
- Security groups
- EBS
- Public/private IP
- Elastic IP
- User data
### Networking
Learn:
- VPC
- Subnet
- Route table
- Internet Gateway
- NAT Gateway
- Security Group
- NACL
### Other Services
- S3
- IAM
- CloudWatch
- RDS
- Load Balancer
- Auto Scaling

## 10. Security Basics
Learn:
- Authentication vs authorization
- IAM
- RBAC
- Least privilege
- MFA
- Encryption
- TLS/SSL
- Certificates
- SSH keys
- Password policies
- Vulnerability vs threat vs risk
- Firewall
- SIEM basics
- Patch management