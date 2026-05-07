# VULNERABILITY ANALYSIS
# File Analysis Scanning Result
Detailed analysis of network traffic, vulnerability scanning, and OS fingerprinting.

---

### 🔍 Question 1: ICMP Hidden Data (Base64)
**Goal:** Find the hidden flag in `packet1.pcap`.
* **Discovery:** Identified Packet No. 37 due to an unusual length anomaly.
* **Extraction:** Found a Base64 string in the ICMP data field: `U1VDVEYyMDIze2FpX2lzX2Nvb2x9`.
* **Flag:** `SUCTF2023{ai_is_cool}`

**Screenshots:**
(Drag and drop your images here)

---

### 🕵️ Question 2: ICMP Steganography (Evil Bit)
**Goal:** Extract a flag hidden in the IPv4 Reserved Bit (Evil Bit) of `packet2.pcap`.
* **Method:** 1. Isolated the `ip.flags.rb` field in Wireshark.
  2. Exported bit values to Excel and used `=IF(A2="0x02",1,0)` to rebuild the binary string.
  3. Decoded the binary via CyberChef.
* **Flag:** `SUCTF2023{bit_by_bit_it_comes}`

**Screenshots:**
(Drag and drop your images here)

---

### 🛡️ Question 3: Nmap Scan Interpretation
**Goal:** Identify risks and fixes for a target machine.
* **Critical Finding:** Port 445 (SMB) is vulnerable to **EternalBlue (MS17-010)**.
* **Other Risks:** FTP (vsftpd 2.3.4 backdoor), HTTP (Apache 2.2.8 vulnerabilities).
* **Fixes:** Patch MS17-010, disable unused services, and upgrade OS from Windows 7 to a supported version.

**Screenshots:**
(Drag and drop your images here)

---

### 🐧 Question 4: OS Fingerprinting (TTL)
**Goal:** Identify OS types based on Time To Live values.
* **Linux:** TTL = 64.
* **Windows:** TTL = 128.

**Screenshots:**
(Drag and drop your images here)

---

### 🐱 Question 5: Nessus Analysis (Ghostcat)
**Goal:** Analyze the Ghostcat vulnerability found in a Nessus scan.
* **Vulnerability:** CVE-2020-1938 (Ghostcat).
* **Details:** Affects port 8009 (AJP protocol) on Apache Tomcat.
* **Risk Score:** 9.8 (Critical).

**Screenshots:**
(Drag and drop your images here)

---

## 🛠️ Tools Used
- **Wireshark** (Packet Analysis)
- **CyberChef** (Decoding)
- **Nmap** (Scanning)
- **Nessus** (Vulnerability Assessment)

**Author:** Nur Alia Maisarah Binti Abd Rahaman  
**ID:** 52215125613 (L01-B05)
