### PING (ICMP)

**Ping** is one of the most fundamental network tools available. It uses ICMP (Internet Control Message Protocol) packets to determine the performance of a connection between devices. The time taken for ICMP packets traveling between devices is measured by ping. This measurement is done using ICMP's echo packet and the echo reply from the target device.

Pings can be performed against devices on a network, such as your home network, or resources like websites.

#### Syntax:
```
ping [IP address or website URL]
```

#### Example:
```
~$ ping 57.144.136.1
PING 57.144.136.1 (57.144.136.1) 56(84) bytes of data.
64 bytes from 57.144.136.1: icmp_seq=1 ttl=55 time=19.2 ms
64 bytes from 57.144.136.1: icmp_seq=2 ttl=55 time=18.9 ms
64 bytes from 57.144.136.1: icmp_seq=3 ttl=55 time=15.9 ms
64 bytes from 57.144.136.1: icmp_seq=4 ttl=55 time=21.0 ms
^C
--- 57.144.136.1 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3004ms
rtt min/avg/max/mdev = 15.863/18.732/20.993/1.842 ms
```

Here we are pinging a device that has the public address `57.144.136.1`. Ping informs us that we have sent four ICMP packets, all of which were received with an average time of 3004 milliseconds.
