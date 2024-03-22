To know we are, what permissions do we have, what we are capible of.

cat /etc/passwd | cut -d : -f 1

### Confidential Information and Users

Who are you? Who is logged in now? Who has been logged in previously? Who else is there? Who can do what?

```bash
$ id
$ who
$ w
$ last
$ cat /etc/passwd    # List of users
$ cat /etc/sudoers
$ sudo -l
```

What sensitive files can be found?

```bash
$ cat /etc/passwd    # User accounts
$ cat /etc/group     # Groups
$ cat /etc/shadow    # Password hashes
```

Is anything "interesting" in the home directories? Do you have access?

```bash
$ ls -ahlR /root/
$ ls -ahlR /home/
```

Are there any passwords in scripts, databases, configuration files or log files? The specific files to search will depend on the installed programs determined previously...

```bash
$ cat /var/apache2/config.inc
$ cat /var/lib/mysql/mysql/user.MYD
$ cat /root/anaconda-ks.cfg
```

What has the user being doing? Are there any password in plain text? What have they been editing?

```bash
$ cat ~/.bash_history
$ cat ~/.zsh_history
$ cat ~/.nano_history
$ cat ~/.atftp_history
$ cat ~/.mysql_history
$ cat ~/.php_history
```

Are there any private keys accessible?

```bash
cat ~/.ssh/*
# Check other user directories too!
```