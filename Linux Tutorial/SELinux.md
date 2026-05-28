## What is Selinux?
* Security Enhanced Linux
* A Linux Kernel Security Module
* Provides additional layer of access control and Mandatory Access Control (MAC) to enhance security.

## DAC Vs MAC
DAC
* Discretionary Access Control (DAC)
* An identity based security model where owner of a resource dictates who can access it and what permissions (read, write, execute) they have.
MAC
* Mandatory Access Control
* Is a highly secure, centrally enforced system where OS restricts access to resources based on predefined security labels.
## SELinux Options
* Enforcing (by default enabled in Redhat)
* Permissive (disabled but logs the activity)
* Disable
## How to check SELinux status?
`getenforce or sestatus`
## Change SELinux settings
* `setenforce 0` 
	* Permissive / Disable
* `setenforce 1`
	* Enable
## Change SELinux settings permanent
* `/etc/selinux/config` file
* Make changes in config file
	* `SELINUX=enforcing/disabled/permissive`
* It's a good practice to take snapshot of your system before making changes to SELinux
## Two Main Concepts of SELinux
* Labeling
	* It is an invisible "security tag" attached to every file, folder, process, and network port.
	* Just like an employee ID badge, these tags tell SELinux exactly who you are, what you are allowed to touch, and what you are blocked from doing.
* Type Enforcement