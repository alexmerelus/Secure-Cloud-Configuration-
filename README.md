# Part 3: Secure Cloud Configuration

## 🔐 Incident Response Log for Possible Privilege Escalation

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
