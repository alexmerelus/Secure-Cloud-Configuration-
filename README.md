# Part 3: Secure Cloud Configuration

## Implementing Security Measures

### Overview
In this section, we document our security incident response and network security enhancements as part of our commitment to maintaining a robust security posture in our cloud environment.

### Contents

- **Incident Reports**: Two detailed incident reports prepared following the guidelines of the *NIST 800-61* Incident Management Lifecycle.
- **Network Security**: Description of the steps taken to secure the network, aligned with *NIST 800-53* control SC-7 (Boundary Protection) for enhancing our network's defense mechanisms.



![Screenshot 2023-11-06 at 8 05 47 PM](https://github.com/alexmerelus/Secure-Cloud-Configuration-/assets/138509128/12b45ac5-b961-439e-8930-44d531614177)

## 🔐 Incident 1 - Possible Privilege Escalation

## 1. Detection and Analysis:

**Incident Title:** Azure Key Vault Critical Credential Retrieval Attempt.

- **Reporter:** Automated system alert from Microsoft Sentinel.
- **Assigned To:** Owner
- **Status:** Contained
- **Priority Level:** High
- **Incident Detection Date and Time:** 11/3/2023
- **Alert Source:** Microsoft Sentinel detected unusual activity regarding Azure Key Vault.
- **Event ID:** 332
- **Initial Indicators:** 23 access attempts to critical Key Vault secrets, identified as a Privilege Escalation tactic.
- **Affected Key Vault Resources:** Secrets named "Super-Secret-Password1" and "Tenant-Global-Admin-Password".
- **Suspected Source IP:** 73.150.4.213.
- **Systems/Assets Affected:** Azure Key Vault.
- **Potential Impact:** Unauthorized access to sensitive credentials with the possibility of further malicious activity or data breach.
- **Incident Category:** Possible Privilege Escalation / Credential Access Attempt.
- **Response Triggered:** Immediate alert and commencement of investigation. IP block initiated and access controls modified.

## 2. Containment, Eradication, and Recovery:

- **Containment Actions:** Immediate blocking of the suspected IP address. Modification of the associated Network Security Group (NSG) to tighten access controls.
- **Eradication Actions:** Verification that no unauthorized changes were made to the secrets within the Azure Key Vault.
- **Recovery Actions:** 
  - Review and update of Key Vault access policies to ensure adherence to the principle of least privilege.
  - Enhancement of monitoring and alerting rules, including the implementation of machine learning algorithms for improved anomaly detection.
- **Validation of Recovery:** Ongoing monitoring to ensure the integrity of the Key Vault and the security measures implemented.

## 3. Post-Incident Activity:

- **Lessons Learned:** The incident highlighted the need for robust monitoring and rapid response mechanisms. It also underscored the importance of regular reviews of access controls and the potential benefits of using advanced technologies like machine learning for security.
- **Follow-Up Actions:** Ongoing adjustments to access policies, continuous improvement of monitoring systems, and potential security awareness training for staff.
- **Incident Closure Date:** (11/6/2023)


__________________________________________________________________



## 🔐 Incident 2 - Brute Force ATTEMPT - Linux Syslog

## 1. Detection and Analysis:
- **Incident Title:** Brute Force Attempt on Admin Accounts.
- **Initial Indicators:** Repeated login attempts on admin accounts every 10 minutes to bypass lockout policy.
- **Event ID(s):** Incident ID 884.
- **Systems/Assets Affected:** Admin accounts (specific account details should be confidentially recorded).
- **Source of Incident:** IP Address 180.101.88.222.
- **Other Suspicious Activities:** Attempts consistently made around midnight, indicating a possible pattern in the attacker's behavior.

## 2. Containment, Eradication, and Recovery:
- **Containment Actions:** Monitoring of the source IP 180.101.88.222 for further suspicious activity.
- **Eradication Actions:** Password reset initiated for affected accounts.
- **Recovery Actions:** Implementation of Multi-Factor Authentication (MFA) and geolocation restrictions being considered to strengthen security.

## 3. Post-Incident Activity:
- **Lessons Learned:** The need for additional security measures for admin accounts, such as MFA and geolocation-based access control.
- **Follow-Up Actions:** Review and implement MFA for all admin accounts, consider updating the account lockout policy, and potentially block or alert on login attempts from geographically unusual locations.

## Additional Considerations for the Log:
- **Status:** Closed
- **Priority Level:** High (due to targeting of admin accounts).
- **Timeline:** Noted pattern of activity around midnight; ongoing monitoring and additional security measures being implemented.

## Containment and Eradication Process:
- All admin accounts have strong, unique passwords.
- Any unnecessary remote access permissions are revoked.
- Security patches and updates are applied.
- Network and system logs are preserved for further analysis.

## Post-Incident Review:
- Conduct a thorough review to understand the attack vector.
- Update incident response and prevention strategies.


## Conclusion
In this project, a mini honeynet was constructed in Microsoft Azure and log sources were integrated into a Log Analytics workspace. Microsoft Sentinel was employed to trigger alerts and create incidents based on the ingested logs. Additionally, metrics were measured in the insecure environment before security controls were applied, and then again after implementing security measures. It is noteworthy that the number of security events and incidents were drastically reduced after the security controls were applied, demonstrating their effectiveness.

It is worth noting that if the resources within the network were heavily utilized by regular users, it is likely that more security events and alerts may have been generated within the 24-hour period following the implementation of the security controls.
