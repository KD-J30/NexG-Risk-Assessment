# NexG-Risk-Assessment




# System Description

Microsoft Entra ID is the identity and access management environment used by NexG Services Ltd to authenticate users and manage access to organizational resources.

The environment processes employee identity and access data for **15 employees**.

Microsoft Entra ID is used to authenticate employees and govern the access of the employees of NexG’s ongoing operations.

## Scope

The scope of this risk assessment is focused on identity and access management controls within Microsoft Entra ID, based on the User Access Review control assessment performed for NexG Services Ltd.

The assessment considers whether user access is correct for employees’ current job responsibilities, and whether access is appropriately adjusted when employees change roles or leave the organization.

It is an information-system level risk assessment, not comprehensive of all threats and vulnerabilities to the organization. It is limited to findings and conditions identified during the User Access Review control assessment.

### Items in Scope

- Microsoft Entra ID user accounts
- Authentication
- Security group memberships
- User access permissions
- Department-based access
- Employee role changes
- Employee departures
- Access review activities
- Account deprovisioning
- Least-privilege considerations

**Population: 15 employees**

## Purpose

The purpose of this risk assessment is to identify, evaluate, and prioritize cybersecurity risks affecting user access management at NexG Services Ltd.

The assessment focuses on user accounts, access permissions, security groups, authentication, role changes, and employee departures within Microsoft Entra ID.

It aims to determine whether inappropriate, excessive, or outdated access could result in unauthorized access to NexG’s business resources or information.

---

# Assets

| ID | Asset | Description |
|---|---|---|
| **AS-01** | Employee user accounts | Identities used to authenticate to organizational resources |
| **AS-02** | Security groups | Groups providing department- or role-based access |
| **AS-03** | Business information | Organizational information accessible through business resources |
| **AS-04** | Employee information | Information associated with employees |
| **AS-05** | Business resources | Applications and resources accessed with employee identities |

---

# Risk Scenario: Threat, Vulnerability and Impact

## R-01 — Excessive User Permissions

**Threat:**  
An attacker uses a compromised account to access information.

**Vulnerability:**  
Sarah has Marketing access even though she works in Finance.

**Impact:**

- **Confidentiality:** Unauthorized access to information.
- **Integrity:** Information could be changed without permission.

---

## R-02 — Outdated Permissions

**Threat:**  
An employee uses old access after changing roles.

**Vulnerability:**  
Daniel still has IT access after moving to Sales.

**Impact:**

- **Confidentiality:** Unauthorized access to IT information.
- **Integrity:** Systems or information could be changed without permission.

---

## R-03 — Former Employee Account

**Threat:**  
A former employee or attacker uses an active account.

**Vulnerability:**  
Emma’s account is still active after she resigned.

**Impact:**

- **Confidentiality:** Unauthorized access to company information.
- **Integrity:** Information could be changed or deleted.
- **Availability:** Resources could be disrupted.

---

## R-04 — Compromised Credentials

**Threat:**  
An attacker obtains an employee’s login details.

**Vulnerability:**  
Authentication controls may not adequately protect accounts.

**Impact:**

- **Confidentiality:** Unauthorized access to information.
- **Integrity:** Information could be changed without permission.

---

## R-05 — Malicious Insider

**Threat:**  
An employee intentionally misuses their access.

**Vulnerability:**  
Employees may have more access than they need.

**Impact:**

- **Confidentiality:** Information could be disclosed or stolen.
- **Integrity:** Information could be changed or deleted.

---

# Risk Register

Risks are listed in priority order.

“Target residual risk” is the proposed rating after the recommended treatment is implemented and verified; it is a planning estimate to be confirmed by retesting.

| Risk ID | Risk Scenario | Impact | Likelihood | Risk | Mitigation | NIST CSF 2.0 Mapping |
|---|---|---|---|---|---|---|
| **R-03** | A former employee or attacker uses an active account. | Very High | High | **Very High** | Disable accounts immediately when employees leave and remove their access. Regularly review inactive accounts. | **PR.AA-05** |
| **R-04** | An attacker obtains an employee’s login details. | High | High | **Very High** | Enable MFA and regularly review authentication controls. | **PR.AA-03** |
| **R-01** | An attacker uses a compromised account to access information. | High | Moderate | **High** | Remove unnecessary permissions and regularly review user access based on job responsibilities. | **PR.AA-05** |
| **R-02** | An employee uses old access after changing roles. | High | Moderate | **High** | Review and update user permissions whenever an employee changes roles. | **PR.AA-05** |
| **R-05** | An employee intentionally misuses their access. | High | Moderate | **High** | Apply least privilege, review access regularly, and use monitoring to detect inappropriate access. | **PR.AA-05** |

---

# Risk Matrix

| **Impact / Likelihood** | **Low** | **Moderate** | **High** | **Very High** |
|---|---|---|---|---|
| **Very High** | | | | **R-03** |
| **High** | | | **R-04** | |
| **Moderate** | | | **R-01, R-02, R-05** | |
| **Low** | | | | |

---

# Conclusion

Overall, my assessment is that user access management at NexG Services Ltd presents a **high level of risk**.

All five risks identified fall in the **High or Very High** categories, and in my view none of them should be accepted in their current state.

- **R-03 (former employee account): Very High**
- **R-04 (compromised credentials): Very High**
- **R-01 (excessive user permissions): High**
- **R-02 (outdated permissions): High**
- **R-05 (malicious insider): High**

What stands out is that these are not five isolated issues.

They share a common root cause: access is not consistently governed across the identity lifecycle, from joining and changing roles through to leaving the organization, and authentication may not be strong enough to compensate when that governance fails.

This is reflected in the NIST CSF 2.0 mapping, where four of the five risks fall under **PR.AA-05** and the remaining one under **PR.AA-03**.

Fixing them one by one would be less effective than strengthening the underlying access review and deprovisioning process.

## Risk Treatment Priority

I would prioritize treatment in the following order:

### 1. R-03 — Former Employee Account

An active account belonging to a former employee is the most direct and most avoidable route to unauthorized access, so removing access immediately on departure should be treated as a non-negotiable control.

### 2. R-04 — Compromised Credentials

Enforcing MFA is a relatively low-effort, high-value measure that reduces the impact of stolen credentials across every other scenario.

### 3. R-01 and R-02 — Excessive and Outdated Access

Regular user access reviews and a defined process for updating permissions when roles change would remove excessive and outdated access before it can be abused.

### 4. R-05 — Malicious Insider

Least privilege and monitoring address the insider threat, which is harder to eliminate completely but can be reduced considerably once excess permissions are cleaned up.

