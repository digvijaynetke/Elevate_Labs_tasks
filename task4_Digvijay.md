

# 🧱 **Firewall Configuration and Testing — Kali Linux (UFW)**

**Name:** Digvijay Netke
**System:** ASUS TUF Gaming A17 (Kali Linux 2025.3)
**Date:** *25-10-2025*

---

## **1. Open Firewall Configuration Tool**

**Command Used:**

```bash
sudo apt install ufw -y
sudo ufw enable
sudo ufw status
```

**Description:**
Enabled UFW (Uncomplicated Firewall) on Kali Linux to manage inbound and outbound traffic.

<img width="361" height="105" alt="1" src="https://github.com/user-attachments/assets/3d44a422-dd5d-4db4-8178-b2b1499027ff" />

---

## **2. List Current Firewall Rules**

**Command Used:**

```bash
sudo ufw status numbered
```

**Description:**
Displayed the current list of active firewall rules.

<img width="421" height="169" alt="image" src="https://github.com/user-attachments/assets/d6977b27-9653-4e72-9437-e3c32839c26a" />

```
2.List current firewall rules.
┌──(ryzen㉿kali)-[~]
└─$ sudo iptables -L -v -n
Chain INPUT (policy DROP 0 packets, 0 bytes)
 pkts bytes target     prot opt in     out     source               destination         
   91 10981 ufw-before-logging-input  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
   91 10981 ufw-before-input  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
    0     0 ufw-after-input  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
    0     0 ufw-after-logging-input  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
    0     0 ufw-reject-input  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
    0     0 ufw-track-input  all  --  *      *       0.0.0.0/0            0.0.0.0/0           

Chain FORWARD (policy DROP 0 packets, 0 bytes)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 ufw-before-logging-forward  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
    0     0 ufw-before-forward  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
    0     0 ufw-after-forward  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
    0     0 ufw-after-logging-forward  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
    0     0 ufw-reject-forward  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
    0     0 ufw-track-forward  all  --  *      *       0.0.0.0/0            0.0.0.0/0           

Chain OUTPUT (policy ACCEPT 2 packets, 80 bytes)
 pkts bytes target     prot opt in     out     source               destination         
  103 10664 ufw-before-logging-output  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
  103 10664 ufw-before-output  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
   96  9842 ufw-after-output  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
   96  9842 ufw-after-logging-output  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
   96  9842 ufw-reject-output  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
   96  9842 ufw-track-output  all  --  *      *       0.0.0.0/0            0.0.0.0/0           

Chain ufw-after-forward (1 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-after-input (1 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 ufw-skip-to-policy-input  udp  --  *      *       0.0.0.0/0            0.0.0.0/0            udp dpt:137
    0     0 ufw-skip-to-policy-input  udp  --  *      *       0.0.0.0/0            0.0.0.0/0            udp dpt:138
    0     0 ufw-skip-to-policy-input  tcp  --  *      *       0.0.0.0/0            0.0.0.0/0            tcp dpt:139
    0     0 ufw-skip-to-policy-input  tcp  --  *      *       0.0.0.0/0            0.0.0.0/0            tcp dpt:445
    0     0 ufw-skip-to-policy-input  udp  --  *      *       0.0.0.0/0            0.0.0.0/0            udp dpt:67
    0     0 ufw-skip-to-policy-input  udp  --  *      *       0.0.0.0/0            0.0.0.0/0            udp dpt:68
    0     0 ufw-skip-to-policy-input  all  --  *      *       0.0.0.0/0            0.0.0.0/0            ADDRTYPE match dst-type BROADCAST

Chain ufw-after-logging-forward (1 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 LOG        all  --  *      *       0.0.0.0/0            0.0.0.0/0            limit: avg 3/min burst 10 LOG flags 0 level 4 prefix "[UFW BLOCK] "

Chain ufw-after-logging-input (1 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 LOG        all  --  *      *       0.0.0.0/0            0.0.0.0/0            limit: avg 3/min burst 10 LOG flags 0 level 4 prefix "[UFW BLOCK] "

Chain ufw-after-logging-output (1 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-after-output (1 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-before-forward (1 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 ACCEPT     all  --  *      *       0.0.0.0/0            0.0.0.0/0            ctstate RELATED,ESTABLISHED
    0     0 ACCEPT     icmp --  *      *       0.0.0.0/0            0.0.0.0/0            icmptype 3
    0     0 ACCEPT     icmp --  *      *       0.0.0.0/0            0.0.0.0/0            icmptype 11
    0     0 ACCEPT     icmp --  *      *       0.0.0.0/0            0.0.0.0/0            icmptype 12
    0     0 ACCEPT     icmp --  *      *       0.0.0.0/0            0.0.0.0/0            icmptype 8
    0     0 ufw-user-forward  all  --  *      *       0.0.0.0/0            0.0.0.0/0           

Chain ufw-before-input (1 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 ACCEPT     all  --  lo     *       0.0.0.0/0            0.0.0.0/0           
   86  9784 ACCEPT     all  --  *      *       0.0.0.0/0            0.0.0.0/0            ctstate RELATED,ESTABLISHED
    0     0 ufw-logging-deny  all  --  *      *       0.0.0.0/0            0.0.0.0/0            ctstate INVALID
    0     0 DROP       all  --  *      *       0.0.0.0/0            0.0.0.0/0            ctstate INVALID
    0     0 ACCEPT     icmp --  *      *       0.0.0.0/0            0.0.0.0/0            icmptype 3
    0     0 ACCEPT     icmp --  *      *       0.0.0.0/0            0.0.0.0/0            icmptype 11
    0     0 ACCEPT     icmp --  *      *       0.0.0.0/0            0.0.0.0/0            icmptype 12
    0     0 ACCEPT     icmp --  *      *       0.0.0.0/0            0.0.0.0/0            icmptype 8
    0     0 ACCEPT     udp  --  *      *       0.0.0.0/0            0.0.0.0/0            udp spt:67 dpt:68
    5  1197 ufw-not-local  all  --  *      *       0.0.0.0/0            0.0.0.0/0           
    1   397 ACCEPT     udp  --  *      *       0.0.0.0/0            224.0.0.251          udp dpt:5353
    4   800 ACCEPT     udp  --  *      *       0.0.0.0/0            239.255.255.250      udp dpt:1900
    0     0 ufw-user-input  all  --  *      *       0.0.0.0/0            0.0.0.0/0           

Chain ufw-before-logging-forward (1 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-before-logging-input (1 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-before-logging-output (1 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-before-output (1 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 ACCEPT     all  --  *      lo      0.0.0.0/0            0.0.0.0/0           
    7   822 ACCEPT     all  --  *      *       0.0.0.0/0            0.0.0.0/0            ctstate RELATED,ESTABLISHED
   96  9842 ufw-user-output  all  --  *      *       0.0.0.0/0            0.0.0.0/0           

Chain ufw-logging-allow (0 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 LOG        all  --  *      *       0.0.0.0/0            0.0.0.0/0            limit: avg 3/min burst 10 LOG flags 0 level 4 prefix "[UFW ALLOW] "

Chain ufw-logging-deny (2 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 RETURN     all  --  *      *       0.0.0.0/0            0.0.0.0/0            ctstate INVALID limit: avg 3/min burst 10
    0     0 LOG        all  --  *      *       0.0.0.0/0            0.0.0.0/0            limit: avg 3/min burst 10 LOG flags 0 level 4 prefix "[UFW BLOCK] "

Chain ufw-not-local (1 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 RETURN     all  --  *      *       0.0.0.0/0            0.0.0.0/0            ADDRTYPE match dst-type LOCAL
    5  1197 RETURN     all  --  *      *       0.0.0.0/0            0.0.0.0/0            ADDRTYPE match dst-type MULTICAST
    0     0 RETURN     all  --  *      *       0.0.0.0/0            0.0.0.0/0            ADDRTYPE match dst-type BROADCAST
    0     0 ufw-logging-deny  all  --  *      *       0.0.0.0/0            0.0.0.0/0            limit: avg 3/min burst 10
    0     0 DROP       all  --  *      *       0.0.0.0/0            0.0.0.0/0           

Chain ufw-reject-forward (1 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-reject-input (1 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-reject-output (1 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-skip-to-policy-forward (0 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 DROP       all  --  *      *       0.0.0.0/0            0.0.0.0/0           

Chain ufw-skip-to-policy-input (7 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 DROP       all  --  *      *       0.0.0.0/0            0.0.0.0/0           

Chain ufw-skip-to-policy-output (0 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 ACCEPT     all  --  *      *       0.0.0.0/0            0.0.0.0/0           

Chain ufw-track-forward (1 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-track-input (1 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-track-output (1 references)
 pkts bytes target     prot opt in     out     source               destination         
    2   120 ACCEPT     tcp  --  *      *       0.0.0.0/0            0.0.0.0/0            ctstate NEW
   92  9642 ACCEPT     udp  --  *      *       0.0.0.0/0            0.0.0.0/0            ctstate NEW

Chain ufw-user-forward (1 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-user-input (1 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-user-limit (0 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 LOG        all  --  *      *       0.0.0.0/0            0.0.0.0/0            limit: avg 3/min burst 5 LOG flags 0 level 4 prefix "[UFW LIMIT BLOCK] "
    0     0 REJECT     all  --  *      *       0.0.0.0/0            0.0.0.0/0            reject-with icmp-port-unreachable

Chain ufw-user-limit-accept (0 references)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 ACCEPT     all  --  *      *       0.0.0.0/0            0.0.0.0/0           

Chain ufw-user-logging-forward (0 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-user-logging-input (0 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-user-logging-output (0 references)
 pkts bytes target     prot opt in     out     source               destination         

Chain ufw-user-output (1 references)
 pkts bytes target     prot opt in     out     source               destination         


```
---

## **3. Add Rule to Block Inbound Traffic on Port 23 (Telnet)**

**Command Used:**

```bash
sudo ufw deny 23
```

**Description:**
Created a rule to block all inbound connections on TCP port 23 (Telnet).

<img width="192" height="78" alt="3" src="https://github.com/user-attachments/assets/524688ed-067f-4190-a99d-dea9d8050f80" />

---

## **4. Test the Rule**

**Command Used:**

```bash
nc -zv localhost 23
```

**Expected Output:**

```
nc: connect to localhost port 23 (tcp) failed: Connection refused
```

<img width="430" height="199" alt="4" src="https://github.com/user-attachments/assets/8b18710e-dcb8-4454-b67b-d362fb67a91f" />

---

## **5. Add Rule to Allow SSH (Port 22)**

**Command Used:**

```bash
sudo ufw allow 22
sudo ufw status numbered
```

**Description:**
Allowed inbound SSH connections on port 22.
<img width="433" height="229" alt="5" src="https://github.com/user-attachments/assets/27a426d1-08ff-4cfd-b50b-7b7f48f7cd4c" />

---

## **6. Remove the Test Block Rule**

**Command Used:**

```bash
sudo ufw status numbered
sudo ufw delete <rule_number>
```

**Description:**
Removed the deny rule for port 23 to restore the firewall’s original state.

*<img width="470" height="996" alt="6" src="https://github.com/user-attachments/assets/a67317a2-b0b3-4403-a5cb-3b61f41f0b33" />
*

---

## **7. Commands Used Summary**

```bash
sudo apt install ufw -y
sudo ufw enable
sudo ufw status numbered
sudo ufw deny 23
nc -zv localhost 23
sudo ufw allow 22
sudo ufw delete <rule_number>
```

---

## **8. Summary: How Firewall Filters Traffic**

> A firewall filters traffic based on defined security rules.
> It monitors packets entering or leaving the system and compares them against allow/deny policies.
> If a packet matches a deny rule, it’s dropped; if it matches an allow rule, it’s permitted.
> UFW provides a simple interface for managing these rules, ensuring only trusted communication occurs between the system and the network.

---






# Interview Questions


---

### **1️⃣ What is a firewall?**

A **firewall** is a network security device or software that monitors and controls incoming and outgoing network traffic based on predefined rules.
Its main purpose is to create a barrier between a trusted internal network and untrusted external networks (like the Internet) to block malicious or unauthorized access.

---

### **2️⃣ Difference between stateful and stateless firewall**

| Feature                | Stateful Firewall                                             | Stateless Firewall                                   |
| ---------------------- | ------------------------------------------------------------- | ---------------------------------------------------- |
| **Traffic Monitoring** | Tracks the *state* of active connections (e.g., TCP sessions) | Evaluates each packet independently                  |
| **Context Awareness**  | Aware of connection context — can identify legitimate packets | No connection awareness — treats every packet as new |
| **Security Level**     | More secure (intelligent filtering)                           | Less secure (simple rule-based filtering)            |
| **Performance**        | Slightly slower due to tracking                               | Faster but less accurate                             |
| **Example**            | UFW / iptables (stateful)                                     | Basic ACL-based routers (stateless)                  |

---

### **3️⃣ What are inbound and outbound rules?**

* **Inbound rules:** Control traffic **entering** your system or network (e.g., allow SSH or block Telnet).
* **Outbound rules:** Control traffic **leaving** your system (e.g., prevent apps from sending data to unknown IPs).

In short:

* Inbound → what can come **in**
* Outbound → what can go **out**

---

### **4️⃣ How does UFW simplify firewall management?**

UFW (**Uncomplicated Firewall**) provides an **easy-to-use interface** for managing `iptables` (which can be complex).

* Uses **simple commands** like `ufw allow 22` or `ufw deny 80`.
* Automatically handles low-level configurations.
* Supports profiles (like SSH, HTTP).
* Displays readable status lists with `ufw status numbered`.

In essence, it makes Linux firewall management beginner-friendly.

---

### **5️⃣ Why block port 23 (Telnet)?**

Port **23** is used by **Telnet**, an **unsecured** protocol that transmits data (including passwords) in plain text.
Attackers can easily intercept or sniff credentials.
Hence, it’s considered insecure and replaced by **SSH (port 22)**, which encrypts communication.

---

### **6️⃣ What are common firewall mistakes?**

1. Allowing **too many open ports** unnecessarily.
2. Forgetting to block **outbound connections** from untrusted apps.
3. Not updating rules after network or service changes.
4. Misconfiguring **default policies** (e.g., default allow instead of deny).
5. Not logging or monitoring firewall activity.
6. Disabling the firewall temporarily and forgetting to re-enable it.

---

### **7️⃣ How does a firewall improve network security?**

* **Blocks unauthorized access** to internal systems.
* **Filters malicious traffic** before it reaches devices.
* **Restricts communication** to trusted sources and services.
* **Prevents data exfiltration** (outbound protection).
* **Logs activity**, helping detect intrusion attempts.

Overall, it enforces a security boundary and reduces the system’s attack surface.

---

### **8️⃣ What is NAT in firewalls?**

**NAT (Network Address Translation)** allows multiple devices on a local network to share a single public IP address.
In firewall context, NAT:

* **Masks internal IPs**, hiding network structure from outsiders.
* Helps with **IP conservation** and **security**.
* Common types:

  * **SNAT (Source NAT):** Changes source IP (used for outgoing traffic).
  * **DNAT (Destination NAT):** Changes destination IP (used for port forwarding).

---

