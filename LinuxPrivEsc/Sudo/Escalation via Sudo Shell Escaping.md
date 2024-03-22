## Resource
- gtfobins
- 
Linux PrivEsc Playground - [https://tryhackme.com/room/privescplayground](https://tryhackme.com/room/privescplayground)


Escalating privileges via sudo shell escaping involves exploiting a vulnerability in a command executed with sudo permissions to run arbitrary commands as root. Here's a detailed explanation of how this type of privilege escalation works:

1. **Identifying sudo Permissions**: In Linux, the `sudo` command allows users to execute commands with the privileges of another user, typically the root user. To escalate privileges, you need to identify a command or script on the system that is executed with sudo permissions.
    
2. **Finding a Shell Escape**: Once you've identified a command executed with sudo permissions, you need to find a way to escape out of the executed command's context to gain access to a shell. This typically involves exploiting a vulnerability in how the command handles user input or command execution.
    
    For example, if a command executed with sudo permissions does not properly sanitize user input, you may be able to inject special characters or commands to break out of the command's execution and gain access to a shell.
    
3. **Executing Arbitrary Commands**: After escaping the command's context and gaining access to a shell, you can execute arbitrary commands with root privileges, effectively escalating your privileges on the system.
    
    Once you have a shell, you can perform various actions, such as accessing sensitive files, modifying system configurations, or installing malware.
    

1. In command prompt type: **sudo -l**

2. From the output, notice the list of programs that can run via sudo.