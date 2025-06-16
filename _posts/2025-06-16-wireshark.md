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

As for Wireshark itself, it is all about learning how to filter data. Understanding source, destination, protocols. Thanks for David Bombal course I saw also that is possible to catch VoiP traffic and play it without leaving Wireshark.

Here are some basic filtering options:

* Source IP: Filter packets originating from a specific IP address. Example: 
```wireshark
ip.src == 10.1.1.254
```
* Destination IP: Filter packets destined for a particular IP address. Example: ip.dst == 192.168.1.1

* Port: Focus on a specific port used in the communication. That's where the list above is useful :) Example: tcp.port == 80 or udp.port == 53

* Connection: Quickly filter all traffic between two nodes by right-clicking on a packet and selecting “Follow TCP Stream” (or similar), or manually using a filter like: Example: (ip.src == 192.168.1.100 and ip.dst == 192.168.1.1) or (ip.src == 192.168.1.1 and ip.dst == 192.168.1.100)

* Protocol: Focus on a certain protocol by simply typing its name. Examples: tcp, udp, icmp (useful for ping requests and responses)

* MAC Address: Filter traffic based on the source or destination hardware (MAC) address. Example: eth.addr == 00:11:22:33:44:55

* VLAN ID: Isolate traffic on a specific VLAN. Example: vlan.id == 100

* TCP Flags: Isolate stages of TCP communication. For instance, to view the packets that initiate a connection (SYN packets), you can use: Example: tcp.flags.syn == 1 and tcp.flags.ack == 0

* Application Protocol Indicators (OSI Layer 7): Sometimes, you may want to filter traffic for a specific application or service: http.request, dns, ftp

<img src="/images/blog/wireshark/babyshark.png" alt="Wireshark" class="responsive-image">