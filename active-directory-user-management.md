# Active Directory User Management & Access Control

## Objective

To perform administrative tasks within an Active Directory environment and understand how user management and access control are handled in a domain setting.

---

## Scenario

In this lab, I worked within a simulated Active Directory environment, performing tasks as a Domain Administrator. The goal was to manage user accounts, delegate permissions, and enforce security policies.

---

## Tools Used

* Active Directory
* PowerShell
* Remote Desktop Protocol (RDP)

---

## Actions Performed

* Connected to a domain-joined machine via RDP
* Delegated password reset permissions within an organisational unit
* Used PowerShell to reset a user’s password
* Configured the account to require a password change at next login

---

## Issue Encountered

While resetting the user’s password, I encountered a password policy restriction.

---

## Resolution

* Adjusted the password to meet domain policy requirements
* Successfully reset the account and enforced password change at next login

---

## Key Learnings

* Active Directory environments enforce strict password policies
* Delegation of permissions must be carefully controlled
* PowerShell is a powerful tool for administrative and security tasks
* Misconfigured permissions could lead to security risks

---

## Analyst Insight

This lab highlights the importance of access control and privilege management in enterprise environments. Improper delegation or weak password policies can introduce security vulnerabilities that may be exploited by attackers.

From a SOC perspective, monitoring account changes, privilege assignments, and authentication behaviour is critical for detecting potential misuse or compromise.

## Evidence

![Active Directory Lab Screenshot](your-image-path.png)

