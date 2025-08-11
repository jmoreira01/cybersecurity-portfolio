# Security Risk Assessment – Social Media Organization Data Breach

## 1. Scenario

You are a security analyst working for a social media organization.  
The organization recently experienced a major **data breach**, which compromised the safety of their customers’ personal information, such as **names** and **addresses**.  
Your organization wants to implement strong network hardening practices that can be performed consistently to prevent attacks and breaches in the future.

After inspecting the organization’s network, you discover **four major vulnerabilities**:

1. The organization’s employees share passwords.
2. The admin password for the database is set to the default.
3. The firewalls do not have rules in place to filter traffic coming in and out of the network.
4. Multifactor Authentication (MFA) is not used.

If no action is taken to address these vulnerabilities, the organization is at risk of experiencing another data breach or other attacks in the future.

---

## 2. Recommended Hardening Tools and Methods

The reported incident reveals a **security breach** that compromised customers’ personal data such as names and addresses.  
After analysis, four major vulnerabilities were found.  
I suggest the following recommendations:

Employees share passwords, the database admin password is still set to the default, and MFA is not used for identity verification. 
These three security flaws demonstrate that it is essential to implement a strong password policy and add an additional layer of security with MFA for identity validation.

The firewalls are not properly configured to control ports and inbound/outbound network traffic. It is essential to implement port filtering to limit or block unwanted communications.

High encryption standards should be applied to protect customers’ personal data in the database. This type of sensitive information can cause financial and reputational damage if compromised.

---

## 3. Explanation of Recommendations

Clearly, there is no awareness or training on password policies and access control among the company’s employees.  
The fact that they share passwords shows that human error is one of the biggest vulnerabilities in the company, and it contributed to the success of this attack.  
A strong password policy must be urgently adopted to mitigate the impact of similar attacks.  
Additionally, employee training is critical to raise awareness about the consequences of such behavior.

The company’s customer information is stored in a database protected only by a default password, making access easy for attackers.  
This must be changed to a robust password that follows strong password standards, making it harder to guess during an attack.

Encrypting the database information would be an excellent security enhancement, as it makes the data much harder to compromise.  
This would significantly discourage malicious actors.  
In addition, network segmentation should be implemented, placing the database in an isolated subnet for better protection.

---
