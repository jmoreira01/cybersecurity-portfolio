# DDoS Attack Analysis and NIST CSF Security Plan

## Scenario Summary
A multimedia company offering web design, graphic design, and social media marketing services experienced a DDoS attack that disrupted its internal network for approximately two hours. 
The attack involved a flood of ICMP packets, overwhelming the network and halting normal traffic. The incident management team blocked incoming ICMP packets, shut down non-critical services, and restored critical services to mitigate the impact. 
Investigation revealed that an unconfigured firewall allowed a malicious actor to execute the DDoS attack. 
Post-incident, the network security team implemented measures including a new firewall rule, IP verification, network monitoring software, and an IDS/IPS system.

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
