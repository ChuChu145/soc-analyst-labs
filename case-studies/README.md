# 📂 SOC Case Studies – Advanced Alert Investigations

## 📌 Overview

This folder contains advanced Security Operations Center (SOC) alert triage case studies conducted using a simulated SIEM environment.

These case studies build upon the foundational alert triage exercises in the main repository and demonstrate a deeper level of investigation, including:

- Log correlation across multiple data sources  
- Threat intelligence validation  
- Phishing and web-based attack analysis  
- Clear incident classification and reporting  

---

## 🎯 Purpose

The goal of these case studies is to simulate real-world SOC analyst workflows by:

- Investigating alerts beyond surface-level indicators  
- Validating threats using supporting evidence  
- Determining impact based on log data  
- Producing structured, professional incident reports  

---

## 🧠 Skills Demonstrated

- SIEM log analysis  
- Phishing detection and investigation  
- Network traffic analysis (IP, ports, protocols)  
- Threat intelligence usage  
- Incident classification (True Positive / False Positive)  
- Risk and impact assessment  

---

## 📁 Case Studies Included

### 1. Malicious URL Connection Attempt (Blocked)
- Investigates an outbound connection to a known malicious URL  
- Demonstrates firewall log analysis and validation of blocked activity  
- Classification: **True Positive – Blocked**

---

### 2. Phishing Email with Malicious Link
- Analyses a phishing email using domain validation and URL investigation  
- Demonstrates correlation between email and network logs  
- Classification: **True Positive – No User Interaction**

---

## 🔍 Methodology

Each case study follows a structured investigation process:

1. Review alert details  
2. Extract key indicators (IP, domain, URL)  
3. Validate indicators using threat intelligence  
4. Correlate logs across data sources (email, proxy, firewall)  
5. Assess impact and determine classification  
6. Recommend appropriate actions  

---

## 📊 Key Concepts Highlighted

- **URL Shorteners** as a phishing technique  
- **Domain Impersonation** (e.g. lookalike domains)  
- **Blocked vs Successful Connections**  
- Importance of **log correlation in determining impact**  

---

## 🚀 Progression from Previous Work

Compared to earlier alert triage exercises in this repository, these case studies demonstrate:

- More detailed analysis and reasoning  
- Improved use of SIEM queries  
- Better structured reporting  
- Stronger focus on real-world attack techniques  

---

## 🧠 Analyst Note

These case studies are designed to reflect real SOC workflows, where identifying threats is only part of the process. Understanding context, validating impact, and clearly communicating findings are equally important in effective security operations.
