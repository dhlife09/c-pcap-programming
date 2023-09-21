
# c-pcap-programming
```bash
===========================
[Protocol] TCP

[Ethernet-src mac] 00:00:00:00:00:00
[Ethernet-dst mac] 00:00:17:2C:B3:5B

[IP-src] 10.0.0.20
[IP-dst] 23.246.47.180

[TCP-src port] 48319
[TCP-dst port] 4787

```

**TCP ONLY**
- Ethernet Header: src mac / dst mac
- IP Header: src ip / dst ip
- TCP Header: src port / dst port
- Message (appropriate length)

## Requirement (Ubuntu)
```bash
root@dhlife09: sudo apt install libpcap-dev
```

## Usage
```bash
root@dhlife09: gcc -o main main.c -lpcap
root@dhlife09: ./main
```
- **You must run as root.**
- **You must change your interface name correctly!**

### Change interface name
Enter the `ifconfig` command in the terminal and find the appropriate interface name (e.g., enp0s6), then modify line 136 of the code.
```bash
root@dhlife09: ifconfig
enp0s6: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9000
        inet 10.0.0.20  netmask 255.255.255.0  broadcast 10.0.0.255
        inet6 fe80::17ff:fe00:a25b  prefixlen 64  scopeid 0x20<link>
        ether 00:00:00:00:00:00 txqueuelen 1000  (Ethernet)
        RX packets 1024880  bytes 4372724425 (4.3 GB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 627068  bytes 2456992539 (2.4 GB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 33766  bytes 5221731 (5.2 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 33766  bytes 5221731 (5.2 MB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

### Fix Error(pcap.h: No such file or directory)
- You should install requirement correctly. [(How to?)](https://github.com/dhlife09/c-pcap-programming/main/README.md#requirement-ubuntu)
