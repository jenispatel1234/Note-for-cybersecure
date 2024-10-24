# Note for cybersecure
Here is an up-to-date list of skills and knowledge that you should have and be comfortable with at this point in the course. If you have gaps in your knowledge, please don't wait to address the issue - either talk to me during class time or send me an Edsby message.

Basic Linux Commands:

Navigating directories (cd, ls)
Creating, reading, updating, and deleting files (touch, nano, rm, mv, cp)
Managing directories (mkdir, rmdir)
Linux Permissions:

Understanding and modifying file permissions (chmod, chown)
Viewing file permissions (ls -l)
Basic Git Usage:

Initializing a Git repository (git init)
Staging changes (git add)
Committing changes (git commit -m)
Pushing changes to GitHub (git push)
Pulling updates from a remote repository (git pull)
Setting Up Git and GitHub:

Installing Git and GitKraken
Creating and managing repositories on GitHub
Collaborating on repositories (adding collaborators)
Basic Terminal Navigation:

Using pwd to check the current directory
Searching for files (find, grep)
Managing Text Files:

Editing text files with nano
Working with Debian VMs:

Installing Debian OS with VMware
Installing software with apt-get
Understanding the basic structure of a Linux filesystem.

#END

# Here is a class notes of bash Scripting, System Manitoring, System Security:-
1. # bash Scripting:-
A Bash script is a plain text file containing a series of commands that are executed sequentially by the Bash shell, which is the default command-line interpreter in most Linux distributions. Bash scripts allow users to automate repetitive tasks, system administration jobs, and software deployments.

Key Components of a Bash Script
Shebang (#!/bin/bash): This is usually the first line in a Bash script, which tells the operating system which interpreter to use to execute the script (in this case, the Bash shell).
Commands: Regular Linux commands (e.g., ls, cp, mv, etc.) that are executed in the order they appear.
Variables: Used to store data and pass information through the script.
Control Structures: Such as if-else, for, while loops, which add decision-making capabilities and iteration.
Functions: Reusable blocks of code defined within the script.
Uses of Bash Scripts in Linux
Automation of Repetitive Tasks:

Routine backups, file transfers, or system updates can be automated using Bash scripts, minimizing manual intervention.
System Administration:

Administrators use Bash scripts to manage users, permissions, log analysis, network configurations, and software installations.
Software Deployment:

Scripts can automate software installation, configuration, and environment setup, especially in DevOps and continuous integration/continuous deployment (CI/CD) pipelines.
Task Scheduling:

Combined with cron jobs, Bash scripts can schedule tasks like database backups, file cleanup, or log rotation to run at specific times.
Batch Processing:

For operations that need to be applied to multiple files or directories, such as renaming, converting formats, or moving files, Bash scripts provide an efficient batch processing mechanism.
Custom Command-Line Utilities:

You can create your own commands by writing Bash scripts to simplify complex command-line tasks.
Example of a Simple Bash Script:

bash
#!/bin/bash
# Script to back up a directory

SRC_DIR="/home/user/documents"
BACKUP_DIR="/backup/$(date +%Y-%m-%d)"

mkdir -p $BACKUP_DIR
cp -r $SRC_DIR/* $BACKUP_DIR

echo "Backup completed for $SRC_DIR"

In this example, the script backs up the /home/user/documents directory to backup folder with the current date as its name.

2. What is system monitoring? Why is it important for maintaining a healthy Linux system?
 # Monitoring:-

 System monitoring refers to the process of continuously observing the performance, resource usage, and health of a computer system, including hardware components (such as CPU, memory, disk, and network), software processes, and system services. In Linux, this involves tracking various system metrics to ensure the system is running smoothly and efficiently.

Key Components of System Monitoring:
CPU Usage: Monitors the percentage of CPU resources being used and helps identify processes that are consuming excessive CPU time.
Memory (RAM) Usage: Keeps track of physical memory usage, swap usage, and how much memory individual processes are consuming.
Disk Usage and I/O: Monitors the space available on hard drives, the rate of reading/writing data to disks, and disk performance metrics.
Network Usage: Monitors the volume of data being transmitted over network interfaces, as well as the speed and errors in network communication.
Process Monitoring: Tracks active processes, their statuses (running, sleeping, etc.), and resources they are using.
System Uptime and Load Average: Checks how long the system has been running and the average number of processes waiting for CPU time, which indicates how busy the system is.
Logs and Alerts: Keeps track of system logs for errors, warnings, and security issues and generates alerts when specific thresholds are exceeded.
Importance of System Monitoring for Maintaining a Healthy Linux System:
Preventing System Overloads:

Monitoring ensures that system resources (CPU, memory, disk, network) are not over-utilized. By identifying resource-hungry processes or services, administrators can prevent system slowdowns or crashes.
Identifying Performance Bottlenecks:

Continuous monitoring helps detect performance issues, such as memory leaks, disk I/O contention, or network congestion, before they become critical. Early detection allows for proactive optimization.
Ensuring High Availability:

For critical systems (e.g., servers hosting websites, databases, or applications), maintaining high availability is essential. Monitoring helps detect failures or service disruptions, allowing for quick remediation and minimizing downtime.
Security:

Monitoring logs and network activity is crucial for detecting suspicious activity or potential security breaches. It helps identify unauthorized access attempts, malware, or configuration issues that could compromise system security.
Optimizing Resource Usage:

Monitoring helps in tuning the system for optimal performance by identifying underutilized or overutilized resources. This can lead to adjustments, such as upgrading hardware, reallocating processes, or adding additional resources to balance the load.
Troubleshooting Issues:

When a system issue arises, monitoring data can provide insights into what caused the problem. Logs and performance metrics allow administrators to diagnose issues and resolve them efficiently.
Capacity Planning:

System monitoring data allows administrators to anticipate when resources (e.g., disk space or RAM) may run out or when a system upgrade will be necessary. It aids in planning for future growth or expansion.
Automating Responses:

System monitoring tools can be configured to take automated actions when certain thresholds are exceeded, such as restarting services, freeing up memory, or notifying administrators of potential issues.
Common System Monitoring Tools in Linux:
top/htop: Real-time monitoring of CPU, memory, and process activity.
vmstat: Provides an overview of system performance including processes, memory, swap, I/O, and CPU activity.
iostat: Monitors CPU usage and input/output statistics for devices and partitions.
netstat/ss: Monitors network connections, routing tables, and network interface statistics.
df/du: Displays disk space usage and availability.
sar: Collects, reports, and saves system activity information.
dstat: Combines the features of iostat, netstat, vmstat, and others to provide a comprehensive overview of system performance.
Nagios, Zabbix, Prometheus: Full-featured monitoring tools that provide extensive logging, alerting, and visualization capabilities for system monitoring across large infrastructures.
Conclusion:
System monitoring is essential for maintaining a stable and secure Linux system. It helps prevent issues before they become critical, optimizes system performance, and ensures the system runs smoothly by giving real-time insights into resource usage and system health.


3. What are basic system security principles on Linux? 
# basic system security:-

Linux is known for its security features, but proper system security depends on following a set of best practices and principles. Below are some basic system security principles for maintaining a secure Linux environment:

1. Least Privilege Principle:
Users and processes should only have the minimum level of access necessary to perform their tasks. This limits the potential damage from security breaches.
Example: Regular users should not have root access unless necessary. Use the sudo command for administrative tasks instead of logging in as root.
2. Strong Authentication and Password Management:
Use strong, complex passwords for all user accounts and administrative users.
Enforce password policies, including password expiration, minimum length, and complexity.
Disable the root account login for SSH access and require users to use sudo for administrative tasks.
Implement multi-factor authentication (MFA) where possible.
3. Regular Software Updates and Patch Management:
Keep the system and all installed software up to date with the latest security patches. This helps close vulnerabilities that attackers may exploit.
Regularly update the Linux kernel and packages using tools like apt, yum, or dnf.
Example:

On Debian-based systems: sudo apt update && sudo apt upgrade
On Red Hat-based systems: sudo yum update
4. User and Group Management:
Create individual user accounts for each user rather than sharing accounts.
Use groups to manage permissions for users with similar needs, assigning only necessary access to each group.
Disable or remove unused user accounts, particularly those with elevated privileges.
Commands:

List users: cat /etc/passwd
Disable user: usermod -L username
Remove user: userdel username
5. File and Directory Permissions:
Use Linux’s built-in file permissions to restrict access to sensitive files. Set correct permissions on critical system files, directories, and user data.
Permissions Model: The Linux file system has three types of permissions for each file or directory: read (r), write (w), and execute (x), which apply to three categories: the owner, the group, and others.
Example: Set a file’s permissions to 755 (rwxr-xr-x) using:

bash
chmod 755 filename
For sensitive files, like system configuration files, restrict access further:

bash
chmod 600 filename
6. Firewall Configuration:
Use a firewall to control incoming and outgoing network traffic. iptables or firewalld are commonly used to configure rules and filter traffic.
Block all unnecessary ports and services, only allowing the traffic essential to system operation.
Example:

bash
sudo ufw enable
sudo ufw allow 22/tcp  # Enable SSH
7. Service Management:
Minimize the number of active services to reduce the attack surface. Disable or uninstall unnecessary services.
Only install and run services that are essential to the server’s role.
Commands:

List running services: systemctl list-units --type=service
Disable unused service: sudo systemctl disable service_name
8. SSH Security:
Disable root login over SSH by setting PermitRootLogin no in /etc/ssh/sshd_config.
Change the default SSH port from 22 to a non-standard port.
Use SSH key authentication instead of passwords for stronger security.
Enable rate-limiting or fail2ban to block repeated failed SSH login attempts.
Example SSH hardening in /etc/ssh/sshd_config:

bash
PermitRootLogin no
Port 2200  # Use a non-standard port
PasswordAuthentication no  # Use key-based authentication
9. Monitoring and Logging:
Enable and monitor system logs for suspicious activities, login attempts, and errors. The logs should be regularly checked or monitored using automated tools.
Tools like syslog, rsyslog, or journalctl can be used to view logs.
Install intrusion detection systems (IDS) such as AIDE or OSSEC to detect changes in system files.
Commands:

View logs: journalctl -xe
Monitor login attempts: sudo lastlog
10. Data Encryption:
Use encryption to protect sensitive data, both at rest and in transit.
Use Full Disk Encryption (FDE) for laptops and sensitive environments (e.g., LUKS on Linux).
Use SSH and SSL/TLS to encrypt network communications.
Example:

Encrypt files using GPG:
bash
gpg -c filename
11. Application Security:
Install software from trusted sources, preferably from official repositories.
Use AppArmor or SELinux to enforce mandatory access controls and limit the capabilities of applications.
Use chroot jails or containers (e.g., Docker) to isolate applications and services.
12. Regular Audits and Vulnerability Scanning:
Periodically audit system configurations, permissions, and access control mechanisms.
Use vulnerability scanning tools like OpenVAS, Nmap, or Lynis to identify potential vulnerabilities in the system.
Command:

Run Lynis security audit: sudo lynis audit system
Conclusion:
Adhering to these basic security principles ensures that your Linux system is hardened against a wide range of potential threats. By applying least privilege, regularly updating the system, controlling access, encrypting data, and monitoring activities, you can significantly enhance the security posture of a Linux system.




##Explanation of the Script Concepts (from Least Complex to Most Complex):

Comments (#):

In the script, anything written after a # symbol is ignored by the computer. It’s called a comment. Comments are used to explain the code to anyone reading it, so they know what each part does. Comments are important to help you understand what you are working on or were trying to do in your code and act as reminders. There is no limit to the amount of comments or their detail you should or could have.


echo:

The echo command is used to display a message on the screen. It's like making the computer "say" something to the user. These are useful for you display prompts, comments or instructions to the user.
The echo command is also a useful tool to test your code. Putting in an echo both inside and outside an if block can help you see what is working in your code or what is broken. echo statements used fir troubleshooting should always be removed when troubleshooting is complete.


Variables:

Variables are like containers that store values. In this script, age_years and age_days are variables.
read -p "Enter your age in years: " age_years takes the user's input and stores it in the age_years variable.
Tip: you can use an echo to display the value of a variable for troubleshooting purposes.


if Statement:

The if statement is used to check if something is true. It helps us control which parts of the script run based on a condition.
For example, we use if to make sure the user’s input is valid.


Regex (^[0-9]+$):

This part is a pattern used to match text. It’s called a "regular expression" (or regex).
^[0-9]+$ means that the input must be made up of digits (0-9), and nothing else. This makes sure the user only types numbers.
^ means "start of input" and $ means "end of input". [0-9] means any digit, and + means "at least one or more".

Resource to learning more about Regex: regexlearn.com/learn/regex101

Tip: Once you have typed or followed the instructions - hit the enter key to progress.


Resource for testing and playing with Regex: regex101.com/


[[ ]] and !~:

[[ ]] is used to test conditions in Bash. It helps make the script safer and easier to write.
!~ means "does not match". In this script, [[ ! $age_years =~ ^[0-9]+$ ]] checks if the input does not match the pattern (meaning it’s not a number).

Tip: Other symbols you may want to explore are ==, |&nbsp;, &nbsp;&gt;&nbsp;, &nbsp;&lt;&nbsp;, -eq, -ne, -gt.

We refer to these symbols as "Conditionals" and there are many more conditionals than what I have listed here.


 Arithmetic Calculation ($(( ))):

$(( )) is used to do math calculations in Bash.
age_days=$((age_years * 365)) calculates how many days are in the given number of years. It multiplies age_years by 365.

Exit Code (exit 1):

exit 1 ends the script. The number 1 is an error code, which means something went wrong.
If the user types something that’s not a valid number, the script stops here.
Tip: use an echo statement to give a clear message to yourself, and your user about what happened.


Attached file: Sample_Script_Control_Structures_Age_Calculator.sh
