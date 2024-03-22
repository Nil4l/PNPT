### Operating System

What distribution and version is used?

```bash
$ cat /etc/issue
$ cat /etc/*-release
$ cat /etc/lsb-release
$ cat /etc/redhat-release
```

What is the Kernel version? Is it 64-bit?

```bash
$ cat /proc/version   
$ uname -a
$ uname -mrs
$ rpm -q kernel
$ dmesg | grep Linux
```

What can be learned from the environmental variables?

```bash
$ env
$ set
$ cat /etc/profile
$ cat /etc/bashrc
$ cat ~/.bash_profile
$ cat ~/.bashrc
$ cat ~/.bash_logout
$ cat ~/.zshrc
```