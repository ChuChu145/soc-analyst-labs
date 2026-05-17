# Phishing Infrastructure Investigation & Credential Harvesting Analysis

## Overview

This project documents a phishing investigation conducted during a SOC Analyst simulation involving a credential harvesting campaign targeting employees of a financial company.

The investigation focused on:
- Identifying the phishing sender
- Investigating malicious attachments
- Decoding obfuscated content
- Identifying attacker infrastructure
- Investigating malicious artifacts
- Malware hash analysis
- Source code analysis
- Identifying adversary credential collection methods

This case study demonstrates practical phishing investigation and threat analysis workflows commonly performed by SOC analysts and incident responders.

---

# Scenario

As an IT team member at a financial company, multiple employees across several departments reported receiving suspicious emails.

Several users identified unusual characteristics within the emails. Unfortunately, some users submitted their credentials through the phishing campaign and subsequently lost access to their accounts, creating the potential for wider organizational compromise.

The incident was escalated for investigation to determine:
- The scope of the attack
- The phishing infrastructure used
- The attacker methodology
- Indicators of compromise (IOCs)

---

# Investigation Process

## 1. Initial Email Investigation

The investigation began by reviewing the suspicious email and identifying the sender email address used in the phishing campaign.

### Objectives
- Identify sender information
- Review email characteristics
- Determine phishing indicators

### Email Investigation Screenshot

![Phishing Email Investigation](images/email-investigation.png)

---

# 2. Attachment Analysis & Decoding

One of the emails contained an encoded attachment.

The attachment was analyzed by viewing the message source

The encoded content was successfully decoded, revealing a redirection URL used within the phishing campaign.

### Root Domain Identified

```plaintext
kennaroads.buzz
```

### CyberChef Decoding Screenshot

![CyberChef Decoding](images/cyberchef-decode.png)

---

# 3. Brand Impersonation Analysis

Further analysis revealed that the phishing campaign was impersonating.
The phishing site attempted to mimic Microsoft branding in order to increase user trust and improve credential theft success rates.

### Microsoft Impersonation Screenshot

![Microsoft Impersonation](images/microsoft-impersonation.png)

---

# 4. Attacker Infrastructure Enumeration

The attacker-controlled website directory structure was explored during investigation.

A suspicious artifact was identified:

```plaintext
/data/update365.zip
```

This file appeared to contain phishing kit components associated with the credential harvesting operation.

### Attacker Directory Screenshot

![Attacker Directory Enumeration](images/directory-enumeration.png)

---

# 5. Malware Hash Analysis

The malicious ZIP file was downloaded and analyzed in a controlled environment.

A SHA256 hash was generated using Linux:

```bash
sha256sum update365.zip
```

### Linux Hashing Screenshot

![Linux SHA256 Hash](images/linux-sha256.png)

---

# 6. VirusTotal Investigation

The generated SHA256 hash was investigated using virus total CTI

The hash returned positive malicious detections from multiple security vendors, confirming the file as malicious.

### VirusTotal Detection Screenshot

![VirusTotal Detection](images/virustotal-detection.png)

---

# 7. Phishing Kit & Source Code Analysis

The ZIP archive was extracted and the contained files were manually investigated.

Particular attention was given to:

```plaintext
submit.php
```

The PHP source code was reviewed to identify:
- Credential handling behavior
- Data exfiltration mechanisms
- Adversary-controlled collection points

During analysis, the email address used by the attacker to collect stolen credentials was identified within the PHP code.

### submit.php Investigation Screenshot

![submit.php Investigation](images/submit-php-analysis.png)

---

# 8. Technical Analysis Observations

Knowledge of programming and web technologies significantly assisted with:
- Navigating phishing kit files
- Understanding PHP code behavior
- Identifying attacker artifacts
- Tracing credential exfiltration methods

This demonstrates the value of coding knowledge within cybersecurity investigations and SOC operations.

---

# Findings

| Investigation Area | Result |
|---|---|
| Phishing sender identified | Yes |
| Encoded attachment analyzed | Yes |
| Redirection domain identified | kennaroads.buzz |
| Brand impersonation detected | Microsoft |
| Malicious ZIP artifact discovered | update365.zip |
| SHA256 hash generated | Yes |
| VirusTotal detections | Malicious |
| Credential collection email identified | Yes |
| PHP phishing kit analyzed | Yes |

---

# Indicators of Compromise (IOCs)

| IOC Type | Value |
|---|---|
| Domain | kennaroads.buzz |
| File | update365.zip |
| Script | submit.php |

---

# Conclusion

The investigation confirmed a credential harvesting phishing campaign targeting employees within the organization.

The adversary used:
- Brand impersonation
- Encoded attachments
- Redirect infrastructure
- Malicious phishing kits
- Credential exfiltration scripts

The phishing kit contained mechanisms for harvesting and transmitting compromised user credentials to attacker-controlled infrastructure.

The investigation successfully identified:
- Malicious infrastructure
- Malware artifacts
- Credential collection mechanisms
- Indicators of compromise

---

# Skills Demonstrated

- Phishing investigation
- Threat hunting
- Email analysis
- URL analysis
- CyberChef decoding
- Malware investigation
- SHA256 hash analysis
- VirusTotal analysis
- Linux command-line usage
- PHP source code analysis
- Web application investigation
- IOC identification
- SOC investigation workflow
- Incident analysis

---

# Tools Used

- :contentReference[oaicite:3]{index=3}
- :contentReference[oaicite:4]{index=4}
- Linux Terminal
- sha256sum
- Browser Developer Investigation
- PHP Source Analysis

---

# MITRE ATT&CK Mapping

| Technique | Description |
|---|---|
| T1566.002 | Phishing: Spearphishing Link |
| T1566.001 | Phishing: Spearphishing Attachment |
| T1059.007 | Command and Scripting Interpreter: JavaScript |
| T1583 | Acquire Infrastructure |
| T1588 | Obtain Capabilities |
| T1056 | Input Capture |
| T1027 | Obfuscated Files or Information |

---

# Lessons Learned

- Brand impersonation remains highly effective in phishing campaigns
- Encoded content can conceal malicious infrastructure
- Directory enumeration may expose attacker artifacts
- Malware hash analysis helps validate malicious files
- Source code analysis can reveal credential exfiltration mechanisms
- Programming knowledge strengthens investigation capabilities

---

# Disclaimer

This project was completed in a controlled lab/simulation environment for cybersecurity training and educational purposes only.
