* To lock a account
	* `passwd -L username`
* To check status of account
	* `passwd -S username`
* To unlock account
	* `passwd -U username`

* Administered Linux servers in production and non-production environments, including user management, permissions, backups, monitoring, and troubleshooting.
* Managed Linux user accounts, groups, sudo privileges, password policies, account lock/unlock operations, and user access audits.
- Implemented and managed file and directory ownerships and permissions.
	* Administered linux servers in production and non-production environments.
	* Managed user by adding and removing accounts 
		* Add 
			* `adduser username`
		* Delete
			* `userdel username`
		* Delete forcefully
			* `userdel -r username`
	* Managed Groups
		* Add
			* `groupadd groupname`
		* Delete
			* `groupdel groupname`
	* User lock
		* `passwd -l username`
	* User unlock
		* `passwd -u username`
	* Check password status
		* `passwd -S username`
	* Password set
		* `passwd username`
	* User permission
		* `chmod`
	* User ownership
		* `chown`
	* User related configuration file
		* `/etc/passwd` file
	* User password related configuration file
		* `/etc/shadow`
	* User home directory
		* `/home` file
	* To check password expiry of user
		* `chage -l username`
	* To set password expiry days for users
		* `chage -M 90 username`
	* To switch between users
		* `su - username`
	* To provide sudo access for users
		* `vi sudo`
	* To check group related details
		* `/etc/group` file
	* To check os version
		* `cat /etc/redhat-release`

* Performed OS and middleware patching activities across Production, UAT, and DR environments with validation and rollback support
	* Types of patching
		* Security vulnerability
		* Bugs/Issue
		* Performance problems
		* System stability issues
	* Update package
		* `yum update package_name`
	* Patching tool
		* yum
			* `yum install package_name`
			* `yum update package_name`
		* rpm
	* To check available updates in patch
		* `yum check -update`
	* To apply patch 
		* `yum update -y`
		* `yum update package_name`
	* To check os-version
		* `uname -r`
		* `cat /etc/redhat-release`
	* Prechecks before patching
		*  Check rollback plan
			* Take snapshot
		* Check diskspace
			* `df -h`
		* Check memory
			* `free -m`
		* Check pending security patch
			* `yum updateinfo list security all`
		
		* Verify application dependency
		* Inform stakeholder
		* Schedule maintenance window (downtime)

* Difference between rpm and yum

| yum                              | rpm                    |
| -------------------------------- | ---------------------- |
| Resolve dependency automatically | Install single package |
| High level package manager       | Low level tool         |
* How to verify install package
	* yum
		* `yum install installed`
	* rpm 
		* `-qa`

* Kernel patching
	* Security fix
	* Hardware support
	* Performance improve
	* Check version of kernel
		* `uname -r`
	* Reboot is required after patching

* Cron tab (Job Scheduling)
	* To check cron service
		* `systemctl status crond`
	* Stop cron service
		* `systemctl stop crond`
	* Start 
		* `systemctl start crond`
	* Check cron log file
		* `tail -f /var/spool/cron`
		* `tail -f /var/log/cron`
	* Check cron related details
		* `cat /etc/crontab`
	* Disable/allow cron access for user config file
		* `/etc/cron.allow`
		* `/etc/cron.deny`
	* Five stars 
		* `* * * * *`
	* To edit cron
		* `crontab -e`
	* To remove cron
		* `crontab -r`

* Backup and restoration
	* Backup is the process of copying important data and file for recovery during below:
		* Server crash
		* Data corruption
		* Accidental deletion
		* Disaster Recovery
	* Commands for backup
		* `tar (archive) (backup_file)`
			* Eg: `tar -cvf backup.tar`
		* `cp`
		* `scp`
		* `gzip` to compress file
		* `gunzip` decompress file
		* `zip` `unzip`
		* `dd`
		* `mysqldump `-u username -p password > 
		* Create compress backup
			* `tar -czvf`
		* Extract 
			* `tar -xvf`
		* To extract `.tar` and `.gz` file
			* `tar -xzvf`
		* SCP backup
			* `scp -r  bkp_folder_name  username@server-ip:/backup`