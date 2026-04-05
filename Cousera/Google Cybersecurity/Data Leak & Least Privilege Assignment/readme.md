# Data Leak Analysis & Least Privilege Implementation

This project was completed as part of the Google Cybersecurity Certificate on Coursera.

## Objective
Analyze a real-world data leak scenario and apply the principle of least privilege (NIST SP 800-53: AC-6) to identify security gaps and recommend improvements.

## Scenario Summary
A sales manager granted team-wide access to a folder containing sensitive internal documents, including:
- Unreleased product information
- Customer analytics
- Promotional materials

Access was not revoked after the meeting. A sales employee mistakenly shared the internal folder with a business partner, who later posted it publicly on social media.

:contentReference[oaicite:0]{index=0}

## Key Security Issue
Failure to enforce the **principle of least privilege**, resulting in:
- Excessive access permissions
- Lack of access control enforcement
- No restriction on external sharing

## Control Applied
**NIST SP 800-53 – AC-6 (Least Privilege)**  
Ensures users only have the minimum level of access required to perform their job functions.

## Root Causes
- Access not revoked after use
- Over-permissioned shared folder
- Lack of separation between internal and external content
- Human error (employee forgot instructions)

## Recommendations
- Implement time-based access controls (temporary permissions)
- Use Role-Based Access Control (RBAC)
- Separate internal vs. shareable content into different folders
- Restrict link sharing (internal-only permissions)
- Require approval workflows before external sharing
- Enable logging and auditing of access activity

## Impact of Improvements
- Reduces risk of accidental data exposure
- Prevents unauthorized external sharing
- Improves accountability and monitoring
- Strengthens data confidentiality controls

## Security Framework Mapping
- **Function:** Protect  
- **Category:** PR.DS (Data Security)  
- **Subcategory:** PR.DS-5 (Protection against data leaks)  
- **Reference:** NIST SP 800-53 AC-6  

## Skills Demonstrated
- Incident Analysis
- Access Control Evaluation
- NIST Framework Application
- Risk Mitigation Strategy
- Security Policy Recommendations
