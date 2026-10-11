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

### Items in Scope

- Microsoft Entra ID user accounts
- Security group memberships
- User access permissions
- Employee role changes
- Employee departures
- Account deactivation
- Excessive or unnecessary access


**Population: 15 employees**

## Purpose

The purpose of this risk assessment is to identify, evaluate and prioritize cybersecurity risks affecting user access management at NexG Services Ltd.

The assessment focuses on user accounts, access permissions, security groups, role changes and employee departures within Microsoft Entra ID.



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

## R-03 — Former Employee Active Account

**Threat:**  
A former employee or attacker uses an active account.

**Vulnerability:**  
Emma’s account is still active after she resigned.

**Impact:**

- **Confidentiality:** Unauthorized access to company information.
- **Integrity:** Information could be changed or deleted.
- **Availability:** Resources could be disrupted.



# Risk Register


| Risk ID | Risk Scenario | Impact | Likelihood | Risk | Mitigation | NIST CSF 2.0 Mapping |
|---|---|---|---|---|---|---|
| **R-03** | A former employee or attacker uses an active account. | Very High | High | **Very High** | Disable accounts immediately when employees leave and remove their access. Regularly review inactive accounts. | **PR.AA-05** |
| **R-01** | An attacker uses a compromised account to access information. | High | Moderate | **High** | Remove unnecessary permissions and regularly review user access based on job responsibilities. | **PR.AA-05** |
| **R-02** | An employee uses old access after changing roles. | High | Moderate | **High** | Review and update user permissions whenever an employee changes roles. | **PR.AA-05** |

For priority of the risk refer to ( https://github.com/KD-J30/NexG-Risk-Assessment/raw/main/nexG%20risk%20assessment/Screenshot%202026-10-11%20230331.png) for the risk score
# Risk Matrix
![Risk Matrix](https://github.com/KD-J30/NexG-Risk-Assessment/blob/main/nexG%20risk%20assessment/Screenshot%202026-10-11%20233414.png)

---
# Conclusion
The assessment indicates that user access management at NexG Services Ltd presents a high level of risk, with all 3 identified risks classified as High or Very High. These findings highlight weaknesses in managing excessive permissions, role changes and employee departures . The NIST CSF 2.0 mapping further reflects these concerns. Recommendations to mitigate these risks are : implementing quarterly access recertification by department manager; mandatory access reviews following role changes and automated deprovisioning to ensure that access is revoked when an employee leaves the organisation.  

