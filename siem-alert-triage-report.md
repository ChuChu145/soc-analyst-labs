# SIEM Alert Triage Report

## Objective

To investigate and triage multiple SIEM alerts based on severity, context, and potential impact, and determine whether they represent genuine security incidents or false positives.

---

## Scenario

I was presented with a SIEM dashboard containing multiple unassigned alerts with varying severity levels. As part of the triage process, I prioritised alerts based on severity and elapsed time, focusing on those with the highest potential risk.

---

## Summary

* **Total Alerts Investigated:** 3
* **Critical:** 1
* **High:** 1
* **Low:** 1
* **True Positives:** 1
* **False Positives:** 2

---

## Alert 1: Potential Data Exfiltration

### Alert Details

* **Severity:** Critical
* **Trigger Condition:** Data transfer exceeding 5GB

---

### Investigation Steps

* Prioritised the alert due to its severity and elapsed time
* Assigned the alert and began investigation
* Reviewed network traffic details including source, destination, and data volume

---

### Findings

* **Data Sent:** 5.8GB
* **Data Received:** 5.2GB
* **Destination Domain:** *.zoom.us
* **Source Network:** UK04/meetingroom
* **Source IP Address:** Private IP (internal network)

---

### Analysis

The alert was triggered due to high outbound data transfer exceeding the defined threshold. However, several contextual indicators suggest legitimate activity:

* The destination domain (*.zoom.us) is associated with a trusted video conferencing service
* The source network ("meetingroom") indicates a shared business environment
* The private IP address confirms internal origin
* High data transfer is consistent with video conferencing (audio, video, screen sharing)

---

### Risk Consideration

Although the activity appears legitimate, high-volume data transfers can also indicate potential data exfiltration. In a real-world scenario, additional validation would include verifying domain authenticity, reviewing user behaviour, and checking for unusual activity patterns.

---

### Conclusion

This alert was classified as a **false positive**, as the activity aligns with normal business operations.

---

## Alert 2: Double Extension File Creation

### Alert Details

* **Severity:** High
* **Description:** Detection of a file with a double extension

---

### Investigation Steps

* Assigned the alert and updated status to "In Progress"
* Identified the suspicious file and extracted its MD5 hash
* Queried the hash on a Threat Intelligence (TI) platform

---

### Findings

* The MD5 hash was identified as **malicious**

---

### Analysis

Double extension files (e.g. `invoice.pdf.exe`) are commonly used by attackers to disguise malicious executables as legitimate files. This technique relies on users overlooking the true file extension.

The positive match from the TI platform confirms that the file is known to be malicious.

---

### Conclusion

This alert was classified as a **true positive**, indicating a potential malware threat within the environment.

---

## Alert 3: Download from GitHub

### Alert Details

* **Severity:** Low
* **Description:** File downloaded from GitHub

---

### Investigation Steps

* Assigned the alert and updated status to "In Progress"
* Reviewed the accessed URL
* Analysed the source network context

---

### Findings

* **URL Accessed:** https://github.com/facebook/react
* **Source Network:** VPN/DEVELOPERS

---

### Analysis

The URL points to a widely used and legitimate open-source project. The source network suggests expected developer activity.

While GitHub is a trusted platform, it can also host malicious content. However, in this case, the repository accessed is well-known and does not indicate suspicious behaviour.

---

### Conclusion

This alert was classified as a **false positive**, as the activity aligns with normal developer operations.

---

## Overall Outcome

* Successfully triaged and investigated 3 alerts
* Identified 1 true positive (malicious file)
* Reduced noise by correctly identifying 2 false positives

---

## Key Learnings

* High-severity alerts require contextual analysis before escalation
* Threat intelligence is critical for confirming malicious activity
* Understanding normal network behaviour helps reduce false positives
* Context (user role, network, destination) is essential in decision-making

---

## Analyst Reflection

This exercise demonstrates the importance of structured investigation, prioritisation, and critical thinking in a SOC environment. Not all alerts represent real threats, and the ability to distinguish between malicious and legitimate activity is essential for effective security operations.

