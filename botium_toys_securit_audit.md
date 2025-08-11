# Botium Toys: Internal Security Audit

## Scenario Summary
Botium Toys is a small business with a single physical location serving as its office, storefront, and warehouse. With a growing online presence, the IT department faces challenges in maintaining compliance and securing critical assets. The audit scope includes all assets and internal processes, with goals to assess existing assets and complete controls and compliance checklists to improve security posture.

## Current Assets
- Assets managed by the IT Department include: 
- On-premises equipment for in-office business needs  
- Employee equipment: end-user devices (desktops/laptops, smartphones), remote workstations, headsets, cables, keyboards, mice, docking stations, surveillance cameras, etc.
- Storefront products available for retail sale on site and online; stored in the company’s adjoining warehouse
- Management of systems, software, and services: accounting, telecommunication, database, security, ecommerce, and inventory management
- Internet access
- Internal network
- Data retention and storage
- Legacy system maintenance: end-of-life systems that require human monitoring

## Risk Assessment
### Risk Description:
Currently, there is inadequate management of assets. Additionally, Botium Toys does not have all of the proper controls in place and may not be fully compliant with U.S. and international regulations and standards. 

### Control best practices:
The first of the five functions of the NIST CSF is Identify. Botium Toys will need to dedicate resources to identify assets so they can appropriately manage them. Additionally, they will need to classify existing assets and determine the impact of the loss of existing assets, including systems, on business continuity.

### Risk score:
On a scale of 1 to 10, the risk score is 8, which is fairly high. This is due to a lack of controls and adherence to compliance best practices.

### Additional comments:
The potential impact from the loss of an asset is rated as medium, because the IT department does not know which assets would be at risk. The risk to assets or fines from governing bodies is high because Botium Toys does not have all of the necessary controls in place and is not fully adhering to best practices related to compliance regulations that keep critical data private/secure. Review the following bullet points for specific details:

- Currently, all Botium Toys employees have access to internally stored data and may be able to access cardholder data and customers’ PII/SPII.
- Encryption is not currently used to ensure confidentiality of customers’ credit card information that is accepted, processed, transmitted, and stored locally in the company’s internal database. 
- Access controls pertaining to least privilege and separation of duties have not been implemented.
- The IT department has ensured availability and integrated controls to ensure data integrity.
- The IT department has a firewall that blocks traffic based on an appropriately defined set of security rules.
- Antivirus software is installed and monitored regularly by the IT department. 
- The IT department has not installed an intrusion detection system (IDS).
- There are no disaster recovery plans currently in place, and the company does not have backups of critical data. 
- The IT department has established a plan to notify E.U. customers within 72 hours if there is a security breach. Additionally, privacy policies, procedures, and processes have been developed and are enforced among IT department members/other employees, to properly document and maintain data.
- Although a password policy exists, its requirements are nominal and not in line with current minimum password complexity requirements (e.g., at least eight characters, a combination of letters and at least one number; special characters). 
- There is no centralized password management system that enforces the password policy’s minimum requirements, which sometimes affects productivity when employees/vendors submit a ticket to the IT department to recover or reset a password.
- While legacy systems are monitored and maintained, there is no regular schedule in place for these tasks and intervention methods are unclear.
- The store’s physical location, which includes Botium Toys’ main offices, store front, and warehouse of products, has sufficient locks, up-to-date closed-circuit television (CCTV) surveillance, as well as functioning fire detection and prevention systems.

### Key findings from the risk assessment:
- Inadequate asset management and lack of proper controls.
- Non-compliance with U.S. and international regulations (e.g., PCI DSS, GDPR).
- High risk score (8/10) due to missing controls like encryption, IDS, and disaster recovery plans.

## Controls Assessment Checklist
The following table indicates whether Botium Toys currently has each control in place:

| Control | In Place? |
|---------|-----------|
| Least Privilege | No |
| Disaster recovery plans | No |
| Password policies | Yes (but requirements are minimal) | Google says No.
| Separation of duties | No |
| Firewall | Yes |
| Intrusion detection system (IDS) | No |
| Backups | No |
| Antivirus software | Yes |
| Manual monitoring, maintenance, and intervention for legacy systems | Yes (but no regular schedule) | Google says No.
| Encryption | No |
| Password management system | No |
| Locks (offices, storefront, warehouse) | Yes |
| Closed-circuit television (CCTV) surveillance | Yes |
| Fire detection/prevention (fire alarm, sprinkler system, etc.) | Yes |

## Compliance Checklist
The following tables indicate whether Botium Toys adheres to compliance best practices:

### Payment Card Industry Data Security Standard (PCI DSS)
| Best Practice | Adhered To? |
|---------------|-------------|
| Only authorized users have access to customers’ credit card information | No |
| Credit card information is stored, accepted, processed, and transmitted internally, in a secure environment | No |
| Implement data encryption procedures to better secure credit card transaction touchpoints and data | No |
| Adopt secure password management policies | No |

### General Data Protection Regulation (GDPR)
| Best Practice | Adhered To? |
|---------------|-------------|
| E.U. customers’ data is kept private/secured | No |
| There is a plan in place to notify E.U. customers within 72 hours if their data is compromised/there is a breach | Yes |
| Ensure data is properly classified and inventoried | No |
| Enforce privacy policies, procedures, and processes to properly document and maintain data | Yes |

### System and Organizations Controls (SOC type 1, SOC type 2)
| Best Practice | Adhered To? |
|---------------|-------------|
| User access policies are established | No |
| Sensitive data (PII/SPII) is confidential/private | No |
| Data integrity ensures the data is consistent, complete, accurate, and has been validated | Yes |
| Data is available to individuals authorized to access it | Yes (but Principle of Least Privilede not applied) | Google says No.

## Recommendations
To improve Botium Toys’ security posture and reduce risks, I recommend the following:
1. **Implement Least Privilege and Separation of Duties**: Reduce risk and overall impact off malicious insider or compromised accounts (Preventive).
2. **Adopt Encryption**: Provide confidentiality to sensitive information (Deterrent).
3. **Establish Disaster Recovery Plans and Backups**: Develop plans and implement backups to ensure business continuity (Corrective).
4. **Deploy an Intrusion Detection System (IDS)**: Install an IDS to detect and prevent anomalous traffic that matches a signature or rule (Detective).
5. **Enhance Password Policies and Management**: Update password policies to meet current standards and implement a centralized password management system. Reduce likelihood of account compromise through brute fforce or dictionary attack techniques (Preventive).
6. **Improve Account Management Policies**: Managing account lifecycle, reducing attack surface, and limiting overall impact from disgruntled former employees and default account usage (Preventive).

## Reflection
This activity helped me apply the NIST Cybersecurity Framework (CSF) to identify and assess risks in a simulated scenario. The process highlighted the importance of proactive measures like encryption and access controls to protect sensitive data and ensure regulatory compliance.

---
[Back to Cybersecurity Portfolio](README.md)
