# Networks

Networks are simply things connected. For example, a friendship circle: you are all connected because of similar interests, hobbies, skills...

Networks can be found in all walks of life:
- A city's public transportation system
- Infrastructure such as the national power grid for electricity
- Meeting and greeting friends or neighbours
- Postal system

In computing, networking is the same idea, just dispersed to technological devices. A phone, for example, exists to access things.

In computing, a network can be formed by anywhere from 2 devices to billions. These devices include everything from your laptop and phone to security cameras, traffic lights, and even farming equipment. Networks are integrated into our everyday life.

---

## What is the Internet?

The Internet is a giant network that consists of many smaller networks within itself.

The first iteration of the Internet was within the ARPANET project in the late 1960s. This project was funded by the United States Defence Department and was the first documented networking project. However, it wasn't until 1989 when the Internet as we know it was invented by Tim Berners-Lee with the creation of the World Wide Web (WWW).

So, the Internet is just a network that connects other networks.

---

## Identifying Devices on a Network

To communicate and maintain order, devices must be both identifying and identifiable on a network. What use is it if you don't know whom you're talking to?

Devices on a network are very similar to humans in the fact that we have two ways of being identified:
- Our name
- Our fingerprints

We can't change our fingerprints. Every human has an individual set of fingerprints, which means that even if they change their name, there is still an identity behind it.

Devices have the same thing: two means of identification, with one being permeable. These are:
- An **IP Address**
- A **Media Access Control (MAC) Address** (Think of this as being similar to a serial number).

---

### IP Addresses

Briefly, an IP address (or Internet Protocol address) can be used as a way of identifying a host on a network for a period of time. An IP address can then be associated with another device without the IP address changing.

First, let's split up precisely what an IP address is:

```
192.168.1.1

192   octet#1   0-255
168   octet#2   0-255
1     octet#3   0-255
1     octet#4   0-255
```

An IP address is a set of numbers divided into four octets. The value of each octet will summarize to be the IP address of the device on the network. This number is calculated through a technique known as **IP addressing & subnetting**.

### Important Points:
- IP addresses can change from device to device but cannot be active simultaneously more than once within the same network.
- IP addresses follow a set of standards known as **protocols**. These protocols are the backbone of networking and force many devices to communicate in the same language.

Devices can be on both private and public networks. Depending on where they are will determine the type of IP address they have:
- A **public IP address** identifies the device on the Internet.
- A **private IP address** identifies a device amongst other devices.

#### Example:

| Device Name     | IP Address      | IP Address Type |
|-----------------|-----------------|-----------------|
| DESKTOP-KJE57FD | 192.168.1.77   | Private         |
| DESKTOP-KJE57FD | 86.157.52.21   | Public          |
| CMNatic-PC      | 192.168.1.74   | Private         |
| CMNatic-PC      | 86.157.52.21   | Public          |

These two devices will use their private IP addresses to communicate with each other. However, any data sent to the Internet from either of these devices will be identified by the same public IP address. Public IP addresses are given by your Internet Service Provider (ISP) for a monthly fee.

---

### IP Address Versions

As more and more devices become connected, it is becoming increasingly harder to get a public address that isn't already in use. For example, Cisco, an industry giant in the world of networking, estimated that there would be approximately 50 billion devices connected to the Internet by the end of 2021 ([source](https://www.cisco.com/c/dam/en_us/about/ac79/docs/innov/IoT_IBSG_0411FINAL.pdf)).

#### IPv4 vs IPv6:
So far, we have only discussed IPv4, which uses a numbering system of 2^32 IP addresses (4.29 billion). IPv6 is a new iteration of the Internet Protocol addressing scheme to help tackle this issue. It boasts a few benefits:
- Supports up to 2^128 IP addresses (340 trillion+), resolving the issue faced with IPv4.
- More efficient due to new methodologies.

**Comparison of IP Types:**
- IPv6: `2a00:22c4:a531:c500:425f:cce6:c36b:f64d`
- IPv4: `86.157.52.21`

---

### MAC Addresses

Devices on a network will all have a physical network interface, which is a microchip board found on the device's motherboard. The MAC address is a twelve-character hexadecimal number (a base sixteen numbering system used in computing to represent numbers) split into two's and separated by colons.

#### Example:
`a4:c3:f0:85:ac:2d`

- The first six characters represent the company that made the network interface.
- The last six characters are a unique number.

#### Spoofing:
An interesting thing about MAC addresses is that they can be faked or "spoofed" in a process known as **spoofing**. This occurs when a networked device pretends to identify as another using its MAC address. This can often break poorly implemented security designs that assume devices on a network are trustworthy.

#### Example Scenario:
A firewall is configured to allow any communication going to and from the MAC address of the administrator. If a device were to "spoof" this MAC address, the firewall would think it is receiving communication from the administrator when it isn't.

---

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
