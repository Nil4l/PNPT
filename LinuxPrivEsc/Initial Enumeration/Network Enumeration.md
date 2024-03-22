### Communications and Networking

What NIC(s) does the system have? Is it connected to another network?

```bash
$ ifconfig
$ ip link
$ ip addr
$ /sbin/ifconfig -a
$ cat /etc/network/interfaces
$ cat /etc/sysconfig/network
```

What are the network configuration settings? What can you find out about this network? DHCP server? DNS server? Gateway? Firewall rules?

```bash
$ cat /etc/resolv.conf
$ cat /etc/sysconfig/network
$ cat /etc/networks
$ iptables -L
$ hostname
$ dnsdomainname
```

What other users & hosts are communicating with this system?

```bash
$ lsof -i
$ lsof -i :80
$ netstat -antup
$ netstat -antpx
$ netstat -tulpn
$ chkconfig --list
$ chkconfig --list | grep 3:on
$ last
$ w
```