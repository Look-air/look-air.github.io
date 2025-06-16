---
title: "(Wire)shark not so scary"
date: 2025-06-16
image: /images/blog/wireshark/babyshark.png
excerpt: "During my preparation for Network+ and now for CCNA using Wireshark is an essential part of the process. Wireshark and Cisco Packet Tracer are must-haves for quality, hands-on learning. Capturing and filtering traffic is really what it’s all about."
layout: blog
---
<img src="/images/blog/wireshark/wireshark.png" alt="Wireshark" class="responsive-image">
<h1 style="margin-bottom: 5px;">{{ page.title }}</h1>
<p style="font-size: 0.9em; color: #666; margin-top: 0;">{{ page.date | date: "%B %d, %Y" }}</p>
During my preparation for Network+ and now for CCNA using Wireshark is an essential part of the process. Wireshark and Cisco Packet Tracer are must-haves for quality, hands-on learning. Capturing and filtering traffic is really what it’s all about.

If you're looking to grasp the basics of [**Wireshark**](https://www.wireshark.org/), I highly recommend checking out the Wireshark room on [**TryHackMe**](https://tryhackme.com/room/wiresharkfilters). I just finished it, and it was a great hands-on experience! That room is free to access, and Wireshark itself is free and open-source. This is, of course, just the start. For a more thorough guide, I recommend David Bombal and his course on Udemy, which is very detailed and dives into CCNA topics while teaching Wireshark.
One tip before diving in: make sure you understand TCP, UDP, and the most common ports. Wireshark is, after all, a tool for analyzing network traffic.

### Port numbers
Here is a short list of the most useful ports I used while preparing for CompTIA Network+:

* 20, 21 TCP - **FTP**: File Transfer Protocol
* 22 TCP - **SFTP**: SSH File Transfer Protocol
* 22 TCP - **SSH**: Secure Shell
* 23 TCP - **Telnet**: Telnet Protocol
* 25 TCP - **SMTP**: Simple Mail Transfer Protocol
* 53 UDP - **DNS**: Domain Name System
* 67, 68 UDP - **DHCP**: Dynamic Host Configuration Protocol
* 69 UDP - **TFTP**: Trivial File Transfer Protocol
* 80 TCP - **HTTP**: HyperText Transfer Protocol
* 110 TCP - **POP3**: Post Office Protocol version 3
* 123 UDP - **NTP**: Network Time Protocol
* 137, 139 UDP/TCP - **NetBIOS**: Network Basic Input/Output System
* 143 TCP - **IMAP**: Internet Message Access Protocol
* 161, 162 UDP - **SNMP**: Simple Network Management Protocol
* 389 TCP - **LDAP**: Lightweight Directory Access Protocol
* 443 TCP - **HTTPS**: HyperText Transfer Protocol Secure
* 445 TCP - **SMB**: Server Message Block
* 514 TCP - **Syslog**: System Logging Protocol
* 587 TCP - **SMTPS**: Secure Simple Mail Transfer Protocol
* 636 TCP - **LDAPS**: Secure Lightweight Directory Access Protocol
* 993 TCP - **IMAPS**: Internet Message Access Protocol Secure
* 995 TCP - **POP3S**: Post Office Protocol 3 Secure
* 1433 TCP - **SQL**: Microsoft SQL Server
* 3306 TCP - **MySQL**: MySQL Database Protocol
* 3389 TCP - **RDP**: Remote Desktop Protocol
* 4460 TCP - **NTS**: Network Time Security
* 5060, 5061 UDP/TCP - **SIP**: Session Initiation Protocol

### Basic filtering
As for Wireshark itself, it is all about learning how to filter data. Understanding source, destination, protocols. Thanks for David Bombal course I saw also that is possible to catch VoiP traffic and play it without leaving Wireshark.

Here are some basic filtering options:

* **IP address**: Filter packets based on IP address, or you can specify the source or destination addresss. This is layer 3 in OSI model.

```wireshark
ip.addr == 192.168.1.1
ip.src == 192.168.1.1
ip.dst == 192.168.1.1
```
* **MAC Address**: Filter traffic based on the hardware (MAC) address, or you can specify the source or destination address. This is layer 2 in OSI model.

```wireshark
eth.addr == 00:11:22:33:44:55
eth.src == 00:11:22:33:44:55
eth.dst == 00:11:22:33:44:55
```
* **Port**: Focus on a specific port used in communication. This is where the list above becomes useful :) You can recognize traffic just by looking at port being used.

```wireshark
tcp.port == 80
```
* **Connection**: Quickly filter all traffic between two nodes by right-clicking on a packet and selecting “Conversation Filter". Ethernet - Layer 2, IPv4/6 - Layer 3.

<img src="/images/blog/wireshark/conversation.png" alt="Conversation filter" class="responsive-image">

* **Protocol**: Focus on a certain protocol by simply typing its name.

```wireshark
tcp
udp
icmp
```
* **VLAN ID**: Isolate traffic on a specific VLAN.

```wireshark
vlan.id == 100
```
* **TCP Flags**: Isolate stages of TCP communication. For instance, to view the packets that initiate a connection (SYN packets).

```wireshark
tcp.flags.syn == 1
tcp.flags.ack == 1
tcp.flags.fin == 1
tcp.flags.reset == 1
```
* **Application Protocol Indicators** (OSI Layer 7): Sometimes, you may want to filter traffic for a specific application or service.

```wireshark
http
dns
ftp
imap
smtp
```
* **Drag and Drop**: You can drag and drop parameters directly from the Packet Details window to filter by specific attributes.

<img src="/images/blog/wireshark/dragdrop.gif" alt="Wireshark" class="responsive-image">

### Logical operators
Wireshark's filtering language also allows you to combine expressions using logical operators, making your searches even more precise. You can use the NOT operator (!) to exclude specific traffic.
For example: !tcp filters out all TCP packets. The AND operator (either as && or the word and) lets you narrow the filter further, such as ip.src == 192.168.1.1 && tcp.port == 80, which selects only packets from that source with a destination port of 80. 
The OR operator (either || or or) can broaden your filter to catch multiple conditions at once. For example: tcp.port == 80 || tcp.port == 443 displays packets on either common web ports.

```wireshark
!(NOT)
&&(AND)
||(OR)
```
### Don't stop
Don't be afraid to experiment with different scenarios. Try capturing unsecure connections in your homelab, like monitoring FTP sessions to see passwords transmitted in clear text. For even more advanced practice, set up a virtual network using GNS3, which even integrates Wireshark for seamless packet analysis. The key is to learn by doing, so challenge yourself with real-world setups and discover the power of hands-on network analysis.

<img src="/images/blog/wireshark/babyshark.png" alt="Wireshark" class="responsive-image">