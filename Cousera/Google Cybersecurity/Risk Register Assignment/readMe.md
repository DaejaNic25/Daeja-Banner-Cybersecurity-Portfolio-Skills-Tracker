# Risk Register & Risk Assessment

This project was completed as part of the Google Cybersecurity Certificate on Coursera.

## Objective
Identify, analyze, and prioritize security risks affecting a financial institution using a structured risk register.

## Operational Environment
- Coastal bank with low crime rate
- 100 on-site employees, 20 remote employees
- 2,000 individual accounts, 200 commercial accounts
- Subject to financial regulations and compliance requirements

:contentReference[oaicite:1]{index=1}

## Risk Assessment Methodology
Each risk was evaluated using:
- **Likelihood (1–3)** → Probability of occurrence  
- **Severity (1–3)** → Impact on the organization  
- **Priority Score = Likelihood × Severity**

## Identified Risks

### 1. Business Email Compromise (BEC)
- **Likelihood:** 3 (High)
- **Severity:** 3 (High)
- **Priority:** 9  
- **Description:** Employee tricked into sharing sensitive information via phishing

### 2. Compromised User Database
- **Likelihood:** 2 (Moderate)
- **Severity:** 3 (High)
- **Priority:** 6  
- **Description:** Weak encryption exposing customer data

### 3. Financial Records Leak
- **Likelihood:** 2 (Moderate)
- **Severity:** 3 (High)
- **Priority:** 6  
- **Description:** Misconfigured database exposed publicly

### 4. Physical Theft (Safe Left Unlocked)
- **Likelihood:** 1 (Low)
- **Severity:** 2 (Moderate)
- **Priority:** 2  
- **Description:** Physical security failure leading to theft

### 5. Supply Chain Disruption
- **Likelihood:** 1 (Low)
- **Severity:** 2 (Moderate)
- **Priority:** 2  
- **Description:** Natural disasters impacting deliveries

## Key Insights
- Human-related threats (phishing) present the highest risk
- Data protection failures can lead to regulatory violations
- Misconfigurations are a major cause of data exposure
- Physical and environmental risks, while lower priority, still require controls

## Risk Prioritization Strategy
- Focus on high-priority risks first (score 6–9)
- Implement controls such as:
  - Email security awareness training
  - Strong encryption practices
  - Access control and monitoring
  - Secure configuration management

## Skills Demonstrated
- Risk Identification & Analysis
- Risk Scoring & Prioritization
- Security Control Evaluation
- Understanding of Regulatory Impact
- Threat Modeling Fundamentals
