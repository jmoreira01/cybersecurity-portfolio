# DDoS Attack Analysis and NIST CSF Security Plan

## Scenario Summary
You are a cybersecurity analyst working for a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. Your organization recently experienced a DDoS attack, which compromised the internal network for two hours until it was resolved.

During the attack, your organization’s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services. 

The company’s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company’s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company’s network through a distributed denial of service (DDoS) attack. 

To address this security event, the network security team implemented: 

- A new firewall rule to limit the rate of incoming ICMP packets

- Source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets

- Network monitoring software to detect abnormal traffic patterns

- An IDS/IPS system to filter out some ICMP traffic based on suspicious characteristics

As a cybersecurity analyst, you are tasked with using this security event to create a plan to improve your company’s network security, following the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF). You will use the CSF to help you navigate through the different steps of analyzing this cybersecurity event and integrate your analysis into a general security strategy. We have broken the analysis into different parts in the template below. You can explore them here:

- Identify security risks through regular audits of internal networks, systems, devices, and access privileges to identify potential gaps in security. 

- Protect internal assets through the implementation of policies, procedures, training and tools that help mitigate cybersecurity threats. 

- Detect potential security incidents and improve monitoring capabilities to increase the speed and efficiency of detections. 

- Respond to contain, neutralize, and analyze security incidents; implement improvements to the security process. 

- Recover affected systems to normal operation and restore systems data and/or assets that have been affected by an incident. 

## Cybersecurity Incident Report and NIST CSF Plan

### 1. Summary
The organization recently suffered a DDoS attack that immobilized the internal network for approximately two hours. 
The incident involved an ICMP flooding attack, where a massive influx of ICMP packets caused network services to become unresponsive. 
The incident management team acted swiftly by blocking incoming ICMP packets, disabling non-critical network services, and restoring critical services. 
A subsequent investigation by the cybersecurity team identified an unconfigured firewall as the vulnerability exploited by a malicious actor to overwhelm the network with a flood of ICMP packets. 
Several security enhancements were implemented post-incident as a response.

### 2. Identify
The cybersecurity team determined that the root cause was an unconfigured firewall, which enabled a malicious actor to exploit this vulnerability. This led to a DDoS attack involving a flood of ICMP packets, overloading the network for nearly two hours.

### 3. Protect
The network security team implemented the following protective measures:
- A new firewall rule to limit the rate of incoming ICMP packets.
- Source IP address verification on the firewall to detect spoofed IPs in ICMP packets.
- Network monitoring software to identify abnormal traffic patterns.
- An IDS/IPS system to filter ICMP traffic based on suspicious characteristics.

### 4. Detect
Enhanced detection capabilities include:
- Deploying IDS/IPS systems to monitor all Internet traffic and detect suspicious patterns.
- Configuring the firewall to identify spoofed IPs in incoming ICMP packets.

### 5. Respond
To halt the attack, the incident management team blocked ICMP packets and related traffic, while taking non-critical network services offline to contain the impact.

### 6. Recover
The recovery process involved restoring critical network services first, followed by non-critical services. 
Additional measures included implementing source IP verification to prevent spoofed IPs in ICMP packets and developing a plan to improve network security in line with NIST CSF guidelines to address future incidents.

## Reflection
This exercise reinforced my understanding of DDoS attacks and the NIST CSF’s structured approach to cybersecurity. 
Analyzing the ICMP flooding incident and applying the Identify, Protect, Detect, Respond, and Recover functions highlighted the importance of proactive firewall configuration and real-time monitoring. 

---
[Back to Cybersecurity Portfolio](README.md)
