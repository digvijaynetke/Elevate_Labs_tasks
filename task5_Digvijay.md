# Wireshark Packet Capture and Analysis

## 1. Install Wireshark
I installed **Wireshark**, a network protocol analyzer used to capture and inspect packets flowing through a network interface.
<img width="952" height="813" alt="image" src="https://github.com/user-attachments/assets/d712e4c9-3aaf-407a-9712-0b3c53bf7af9" />

---

## 2. Start Capturing on Active Network Interface
After launching Wireshark, I selected my **active network interface** (Wi-Fi / Ethernet) and started the capture to record real-time network traffic.
> capturing started
<img width="1898" height="969" alt="image" src="https://github.com/user-attachments/assets/87404198-a364-491d-9c85-ba707a2d5515" />

---

## 3. Browse a Website or Ping a Server to Generate Traffic
To generate traffic, I opened a few websites and used the command `ping google.com` in the terminal.  
This helped capture various packets including **DNS**, **ICMP**, and **TCP/HTTP** traffic.

<img width="1878" height="937" alt="image" src="https://github.com/user-attachments/assets/e3e1e6e8-1adc-45a1-b801-4752ef7eefe1" />


---

## 4. Stop Capture After a Minute
After about a minute of monitoring, I stopped the capture to analyze the recorded data.

---

## 5. Filter Captured Packets by Protocol (HTTP, DNS, TCP)
Using Wireshark’s filter bar, I applied protocol-based filters such as:  
- `http` – to view web requests and responses.
<img width="927" height="295" alt="image" src="https://github.com/user-attachments/assets/73b3f7c8-bc1e-4857-a650-84cbdef3f8bf" />
- `dns` – to view domain resolution queries.
<img width="941" height="760" alt="image" src="https://github.com/user-attachments/assets/1287981c-9d61-4e80-bf2b-95019ee26dc3" />
- `tcp` – to analyze transmission control packets.
<img width="911" height="916" alt="image" src="https://github.com/user-attachments/assets/14f79063-5a05-4369-a9b2-0c29e46da956" />

---

## 6. Identify at Least 3 Different Protocols in the Capture
In my capture, I identified the following protocols:
1. **DNS (Domain Name System)** – Resolves domain names to IP addresses.  
<img width="923" height="615" alt="image" src="https://github.com/user-attachments/assets/0321357d-0831-4dd3-a355-9e0ac4f7afa9" />

2. **TCP (Transmission Control Protocol)** – Ensures reliable delivery of data packets.  
<img width="928" height="397" alt="image" src="https://github.com/user-attachments/assets/f274984d-dc4e-490b-a7d8-fe75c50c17ed" />

3. **HTTP (HyperText Transfer Protocol)** – Handles communication between browser and web servers.
<img width="900" height="451" alt="image" src="https://github.com/user-attachments/assets/d2b877c2-a88c-427c-aba8-744f2c8272d1" />


---

## 7. Export the Capture as a .pcap File
The entire capture session was exported as a `.pcap` file for documentation and further analysis.
<img width="641" height="36" alt="image" src="https://github.com/user-attachments/assets/9051dd40-e9d5-4ff5-9af8-97e8297c1b8a" />

https://github.com/digvijaynetke/Elevate_Labs_tasks/blob/main/files/task5.pcapng

---

## 8. Summarize Findings and Packet Details
From the captured packets:
- I observed DNS queries being sent to resolve website names.  
- TCP handshakes (SYN, SYN-ACK, ACK) occurred before HTTP requests.  
- HTTP packets showed GET and response headers between client and server.  
This exercise helped me understand **how data travels across different layers of the OSI model** and improved my **protocol analysis skills**.

---



# Interview Questions and Answers

### **1. What is Wireshark used for?**  
Wireshark is used to capture, analyze, and troubleshoot network traffic in real time. It helps in understanding protocols, detecting issues, and identifying malicious activity.

---

### **2. What is a packet?**  
A packet is a small unit of data transmitted over a network. It contains both **header information** (source, destination, protocol, etc.) and **payload data** (the actual message).

---

### **3. How to filter packets in Wireshark?**  
Wireshark provides a **filter bar** where filters like `ip.addr == 8.8.8.8`, `http`, or `tcp.port == 80` can be used to isolate specific traffic for analysis.

---

### **4. What is the difference between TCP and UDP?**  
| Feature | TCP | UDP |
|----------|-----|-----|
| Reliability | Reliable (uses acknowledgments) | Unreliable |
| Connection | Connection-oriented | Connectionless |
| Speed | Slower | Faster |
| Use Case | Web browsing, email | Streaming, gaming |

---

### **5. What is a DNS query packet?**  
A DNS query packet is a request sent by a client to a DNS server to resolve a domain name (e.g., `www.google.com`) into its corresponding IP address.

---

### **6. How can packet capture help in troubleshooting?**  
Packet capture allows network administrators to:
- Detect connection issues (timeouts, retransmissions).  
- Identify network congestion or misconfigurations.  
- Verify data flow and protocol performance.  
- Spot suspicious or unauthorized activity.

---

### **7. What is a protocol?**  
A protocol is a set of rules that define how data is formatted, transmitted, and received across a network.  
Examples include **HTTP**, **TCP/IP**, **DNS**, and **FTP**.

---

### **8. Can Wireshark decrypt encrypted traffic?**  
Wireshark can decrypt **some encrypted traffic** like SSL/TLS **only if the appropriate encryption keys** (such as session keys or certificates) are provided.  
However, it cannot decrypt traffic without the necessary keys, keeping user privacy intact.

---

**Submitted by:**  
**Digvijay Netke**  
