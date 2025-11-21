# Task 8 Capture Network Traffic with Wireshark
File: wireshark_capture.pcap
**Task: Capture and analyze local network traffic using Wireshark.**

# 📌 Objective
This task demonstrates the use of **Wireshark** to capture network packets, apply filters, and analyze HTTP traffic.
The included **.pcap** file contain a short capture of local network activity including **ARP, DNS, TCP,** and **HTTP packets**.

# 🛠️ Tools Used
- Wireshark
- Kali linux (Virtual Machine)
- Local machine network interface (Bridged adapter)

# 📥 Capture Process
1. Installed Wireshark.
2. Selected the primary network interface.
3. Started a live packet capture.
4. Generated some HTTP traffic by visiting a website (http://testphp.vulnweb.com/login.php)
5. Stopped the capture and saved it as wireshark_capture.pcap.

# 📊 Packet Analysis Summary

**1. ARP (Address Resolution Protocol)**
- Used to map IP addresses to MAC addresses.
- present as broadcasts:
     - **who has 192.168.x.x ? Tell 192.168.x.x**
- Shows local device discovery and communication with the gateway/router.
  
**2. DNS (Domain Name System) Queries**
- Before any HTTP session begins, the client performs DNS lookups.
  
**3. TCP Handshake**
Before HTTP data transfer:
- **SYN**: client initiates connection
- **SYN, ACK**: server responds
- **ACK**: client acknowledges
This creates the TCP session used for HTTP.

**4. HTTP Traffic (Filtered using: http)**
The capture includes HTTP packets such as:
- **GET requests**
- **HTTP responses**
These packets show the structure of application-layer communication.

# 🔍 How to Reproduce the Filter
- Use this Wireshark display filter:
http
- Alternative helpul filters:
tcp.port == 80
dns
arp
ip

# Conclusion
This task demonstrated the fundamental process of capturing and analyzing network traffic using Wireshark on a Kali Linux virtual machine. By reviewing ARP, DNS, TCP, and HTTP packets, we gained insight into how devices communicate on a network and how application-layer data flows through the lower layers. The included capture file (wireshark_capture.pcap) showcases real examples of packet exchanges, making it a useful reference for learning network analysis. Overall, this exercise strengthens understanding of network fundamentals and provides practical  experience with one of the most essential tools used in cybersecurity and network diagnostics.
