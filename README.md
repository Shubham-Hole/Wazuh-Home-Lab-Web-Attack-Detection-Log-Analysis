# 🔐 Wazuh Home Lab – Web Attack Detection & Log Analysis

## 📌 Project Overview
This project demonstrates the design and implementation of a **SOC-focused home lab** using **Wazuh SIEM and Suricata IDS** to detect and analyze **web-based attacks**. A deliberately vulnerable web application (DVWA) was used to simulate attacks, while Apache web logs and IDS alerts were ingested into Wazuh for investigation and threat analysis.

---

## 🎯 Objectives
- Build an end-to-end SIEM + IDS home lab
- Detect web-based attacks using IDS and log analysis
- Analyze Apache web logs for malicious activity
- Practice SOC alert triage and investigation workflows
- Understand SIEM troubleshooting and IDS tuning

---

## 🧱 Lab Architecture

| Machine       | Role                                                          |
| ------------- | ------------------------------------------------------------- |
| Ubuntu Server | Victim system hosting DVWA, Apache, Suricata IDS, Wazuh Agent |
| Parrot OS     | Centralized SIEM server running Wazuh Manager                 |
| Kali Linux    | Attacker machine for web and network attacks                  |


### 🔹 Network Design

* All VMs connected via **NAT Network**
* Allows **VM-to-VM communication**
* Isolated from host LAN (safe lab environment)

---

## 🛠 Tools & Technologies

* **Wazuh** – Log collection, correlation, threat hunting
* **Suricata** – Network traffic monitoring and IDS
* **DVWA** – Web attack simulation
* Apache Web Server – Web log generation
* MariaDB – Backend database
* Kali Linux – Attack simulation platform

---
## 🔄 Project Workflow

```
Attacker (Kali)
      ↓
Victim (DVWA + Apache + Suricata)
      ↓
Wazuh Agent (Log Forwarding)
      ↓
Wazuh Manager (SIEM Analysis)
      ↓
SOC Investigation (Threat Hunting)
```
## 🔴 Attack Scenarios Performed

### 1️⃣ Web Application Attack – SQL Injection

**Target:** DVWA SQL Injection module
**Payload Used:**

```
' OR '1'='1
```

**Outcome:**

* Apache access logs recorded malicious URL parameters
* Logs confirmed attack execution
* Evidence available for SOC analysis

---

### 2️⃣ Brute Force Attack – Web Login

**Target:** DVWA Brute Force module
**Method:**

* Repeated incorrect login attempts (manual + automated)
* Same source IP, same endpoint, short time interval

**Outcome:**

* Apache logs showed repeated authentication attempts
* Pattern consistent with brute-force behavior

---

### 3️⃣ Network Reconnaissance (Explored)

**Tool:** Nmap
**Observation:**
**Payload Used:**

```
sudo nmap -sS <vitcim ip>
```

* Suricata traffic capture verified
* Custom IDS rules attempted
* Detection logic and rule debugging documented

---

## 📸 Evidence & Screenshots
Included evidence:
- Wazuh dashboard security events
- Suricata IDS alerts
- Apache log entries showing attacks 
- DVWA exploitation attempts

(Add screenshots in `/screenshots` directory)






