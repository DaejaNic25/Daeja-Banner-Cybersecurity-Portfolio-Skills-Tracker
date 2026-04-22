# 🔑 Lab: Improve Authentication, Authorization & Accounting for a Small Business

**Course:** Google Cybersecurity Certificate — Coursera  
**Domain:** Identity & Access Management (IAM) | Access Controls | Incident Analysis  
**Frameworks Referenced:** NIST AAA Model, Role-Based Access Control (RBAC)

---

## Overview

Authentication, Authorization, and Accounting (AAA) are three foundational pillars of access control in any security program. When these controls break down — through expired accounts, excessive permissions, or missing audit trails — organizations become vulnerable to insider threats and unauthorized access.

In this activity, I analyzed a real-world-style access control incident at a small business, identified the authentication and authorization failures that led to it, and recommended technical and operational controls to prevent recurrence.

---

## Scenario

A security event was flagged involving unauthorized access to sensitive financial systems. Using an access controls worksheet, I investigated the incident across three dimensions: **observations**, **identified issues**, and **recommendations**.

---

## Access Controls Worksheet

### 🗒️ Notes — Identifying the Threat

| Field | Details |
|---|---|
| **Who caused the incident?** | A user within the **legal department** attempted to access financial/banking systems |
| **Event Code** | Windows Event Code `1227` |
| **When did it occur?** | October 3, 2023 at **8:29:57 AM** |
| **IP Address** | `157.207.255.255` |
| **Device Name** | `Up2-NoGud` |

---

### ⚠️ Issues — Authorization & Authentication Failures

**1. Excessive Privilege / Improper Access Level**  
User **Robert Taylor Jr.** held admin-level access and was able to reach payroll/financial systems — despite belonging to the legal department, which has no business need for that data. This violates the **principle of least privilege**.

**2. Stale / Orphaned Account**  
Robert Taylor Jr.'s contract ended in **2019**, yet his account remained active and was used to access payroll systems in **2023** — a gap of over four years. This is a critical identity lifecycle management failure.

---

### ✅ Recommendations — Preventive Controls

**1. Implement Role-Based Access Control (RBAC)**  
Access to financial and payroll systems should be scoped strictly to roles that require it (e.g., Finance, HR). Legal department accounts should have no pathway to sensitive financial data. RBAC enforces this at the system level, not just policy.

**2. Enforce Multi-Factor Authentication (MFA) on All Admin Accounts**  
MFA requires users to present something they *know* (password), something they *have* (authenticator app/token), or something they *are* (biometric). Even if credentials are compromised, an attacker without the second factor cannot authenticate — significantly reducing the blast radius of credential-based attacks.

**3. Establish an Account Expiration & Offboarding Policy**  
User accounts should be automatically disabled within **30 days** of contract end or role change. A formal offboarding checklist should include immediate access revocation, account deactivation, and audit log review. This prevents orphaned accounts from becoming long-lived attack vectors.

**4. Enforce Access Control Policies with Periodic Review**  
Documented policies should define who qualifies for admin access, what approval process is required, and when access must be revoked. Quarterly access reviews (recertification campaigns) ensure permissions stay aligned with current roles.

---

## Key Takeaways

| Concept | Details |
|---|---|
| **Authentication** | Verifying *who* the user is (credentials, MFA) |
| **Authorization** | Defining *what* the user is allowed to access (RBAC, least privilege) |
| **Accounting** | Logging and auditing *what* the user did (event logs, SIEM alerts) |
| **Least Privilege** | Users should only have the minimum access needed for their role |
| **Account Lifecycle** | Accounts must be deprovisioned promptly when no longer needed |
| **Windows Event Code 1227** | Flags access control policy violations — a key indicator for IAM-related incidents |

---

## Real-World Application

This type of incident maps directly to SOC workflows:

- **SIEM Alerting** — Event code 1227 would surface in a tool like Splunk or QRadar, triggering an IAM-related alert
- **Insider Threat Detection** — Behavioral baselines would flag a legal user querying financial data as anomalous
- **Incident Response** — The account would be immediately disabled and the access event preserved for forensic review
- **Identity Governance** — Findings like this drive access recertification initiatives and orphaned account cleanup projects

---

*Completed as part of the Google Cybersecurity Certificate on Coursera.*
