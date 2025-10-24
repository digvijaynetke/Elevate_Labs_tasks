# Vulnerability Assessment using Nessus Essentials

## 1. Install OpenVAS or Nessus Essentials
For this task, I installed **Nessus Essentials**, a widely used vulnerability assessment tool developed by Tenable.  
It helps identify vulnerabilities, misconfigurations, and potential exploits on systems within a network.

**
<img width="1057" height="492" alt="image" src="https://github.com/user-attachments/assets/a5965dc4-788c-451e-8d04-f5e1785cc0ba" />

<img width="586" height="480" alt="1" src="https://github.com/user-attachments/assets/effb0521-408e-4fa8-94a0-f108ae01d6cb" />

**
---

## 2. Set up Scan Target as Local Machine IP or Localhost
The target for the scan was configured as my **local machine IP** (e.g., `192.237.2.3`).  
This ensures that Nessus scans the entire host for open ports, running services, and potential weaknesses.

<img width="1184" height="846" alt="image" src="https://github.com/user-attachments/assets/8c016ed1-70b5-482c-877b-fd60467a4d83" />
<img width="920" height="579" alt="image" src="https://github.com/user-attachments/assets/d0b16d4b-353d-4ad6-b877-32f596784cb0" />


---

## 3. Start a Full Vulnerability Scan
A **Full Scan** policy was launched to perform a comprehensive check across the system.  
This scan analyzed all open ports and checked for vulnerabilities based on the CVSS v3.0 base score.
<img width="1738" height="214" alt="2" src="https://github.com/user-attachments/assets/4c8273cf-0c8a-48ec-8e22-c703cc7acbbd" />


---

## 4. Wait for the Scan to Complete
The scan ran for approximately **30–60 minutes**, depending on the target’s services and system performance.  
Once completed, the scan status showed **"Completed"** with the elapsed time mentioned.

<img width="1639" height="529" alt="image" src="https://github.com/user-attachments/assets/f8e46b07-897a-438e-8efd-9775d3190c28" />

---

## 5. Review the Report for Vulnerabilities and Severity
After completion, Nessus displayed the **summary of discovered vulnerabilities**, categorized into:
- Critical  
- High  
- Medium  
- Low  
- Info  
<img width="1412" height="782" alt="4" src="https://github.com/user-attachments/assets/2e17fa38-6dec-42f9-a789-2f1e1e298c60" />
<img width="1639" height="529" alt="image" src="https://github.com/user-attachments/assets/b4b37447-d80d-4772-aa5c-92a800b38aa4" />


---

## 6. Research Simple Fixes or Mitigations for Found Vulnerabilities
Example:  
- **Vulnerability:** JQuery 1.2 < 3.5.0 Multiple XSS  
  **Fix:** Update JQuery library to version 3.5.0 or later to patch XSS issues.  
- **Vulnerability:** Apache HTTP Server (Multiple Issues)  
  **Fix:** Upgrade to the latest stable version and disable unused modules.

---

## 7. Document the Most Critical Vulnerabilities
The scan identified the following vulnerabilities:
1. **JQuery 1.2 < 3.5.0 Multiple XSS** – Severity: Medium  
   - CVSS Score: 6.1  
   - Impact: Allows attackers to inject malicious scripts via input fields.  
2. **Apache HTTP Server Multiple Issues** – Severity: Info  
   - Impact: Potential information disclosure and misconfiguration.  
<img width="1412" height="782" alt="4" src="https://github.com/user-attachments/assets/ca376033-d85b-4032-ab40-44015d30198f" />

<img width="501" height="393" alt="6" src="https://github.com/user-attachments/assets/e56598a6-bb87-4491-9adb-e100452cf5e0" />

<img width="1054" height="715" alt="7" src="https://github.com/user-attachments/assets/880d25ea-628d-40b5-a8fc-407837371bf6" />

---

## 8. Take Screenshots of the Scan Results
Below are all relevant screenshots captured during the vulnerability assessment process:

1. Host Discovery 

2. Advanced Scan 

3. Vulnerability List  


---

## Conclusion
This vulnerability assessment using **Nessus Essentials** successfully identified multiple issues in the target environment.  
The findings help improve the system’s security posture through regular patching, software updates, and configuration hardening.

---

**Submitted by:**  
**Digvijay Netke**






# interview question


---

### **1. What is vulnerability scanning?**

Vulnerability scanning is an automated process of identifying security weaknesses in systems, networks, or applications. It helps detect outdated software, missing patches, misconfigurations, and known vulnerabilities that attackers could exploit.
It’s usually the first step in assessing an organization’s security posture.

---

### **2. Difference between vulnerability scanning and penetration testing?**

* **Vulnerability Scanning:**

  * Automated process.
  * Detects known weaknesses and misconfigurations.
  * Low risk, non-intrusive.
  * Example: Using tools like Nessus or OpenVAS.

* **Penetration Testing:**

  * Manual or semi-automated process.
  * Exploits vulnerabilities to demonstrate real-world impact.
  * More intrusive and deeper in scope.
  * Example: Ethical hackers actively attempt to break into systems.

In short, vulnerability scanning finds **what could be exploited**, while penetration testing shows **how it can be exploited**.

---

### **3. What are some common vulnerabilities in personal computers?**

Some common vulnerabilities include:

* **Unpatched operating systems or software**
* **Weak or reused passwords**
* **Outdated antivirus or firewall settings**
* **Open or unused ports**
* **Misconfigured services (e.g., file sharing or RDP)**
* **Phishing or social engineering susceptibility**

---

### **4. How do scanners detect vulnerabilities?**

Scanners like **Nessus** or **OpenVAS** use a database of known vulnerabilities and compare it against the system being scanned.
They:

1. Identify open ports and running services.
2. Determine software versions and configurations.
3. Match this information against a vulnerability database (like CVE or NVD).
4. Report potential security issues along with their severity levels.

---

### **5. What is CVSS?**

CVSS stands for **Common Vulnerability Scoring System**.
It provides a standardized way to measure the severity of vulnerabilities on a scale from **0 to 10** —

* **Low (0.1–3.9)**
* **Medium (4.0–6.9)**
* **High (7.0–8.9)**
* **Critical (9.0–10.0)**

This helps security teams prioritize which vulnerabilities to fix first.

---

### **6. How often should vulnerability scans be performed?**

Ideally, vulnerability scans should be performed:

* **Regularly** — at least **monthly** or **quarterly**.
* **After major system updates**, configuration changes, or deployments.
* **Continuously** in high-security environments.

Frequent scanning ensures newly introduced vulnerabilities are detected quickly.

---

### **7. What is a false positive in vulnerability scanning?**

A **false positive** occurs when the scanner reports a vulnerability that doesn’t actually exist or cannot be exploited.
This can happen due to outdated vulnerability databases, incorrect service detection, or environmental factors.
Analysts usually verify such findings manually before reporting.

---

### **8. How do you prioritize vulnerabilities?**

Vulnerabilities are prioritized based on several factors:

1. **Severity (CVSS score)** – Higher severity = higher priority.
2. **Exploitability** – Whether public exploits are available.
3. **Asset value** – Importance of the affected system.
4. **Business impact** – Potential data loss or downtime risk.
5. **Exposure** – Whether the vulnerability is externally accessible.

A good rule: fix **critical and high-risk** issues immediately, then move on to **medium** and **low-risk** ones.

---


