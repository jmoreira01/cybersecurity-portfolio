## Scenario

Review the following scenario. Then complete the step-by-step instructions.

You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like.

One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.

You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor.

You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees.

## Step-By-Step Instructions

Follow the instructions and answer the question to complete the activity.

| Time          | Source IP      | Destination IP | Protocol | Info                                                                                     |
|---------------|----------------|-----------------|----------|-------------------------------------------------------------------------------------------|
| 473.144521    | 198.51.100.23  | 192.0.2.1       | TCP      | 42584->443 [SYN] Seq=0 Win=5792 Len=120                                                   |
| 483.195755    | 192.0.2.1      | 198.51.100.23   | TCP      | 443->42584 [SYN, ACK] Seq=0 Win=5792 Len=120                                             |
| 493.246989    | 198.51.100.23  | 192.0.2.1       | TCP      | 42584->443 [ACK] Seq=1 Win=5792 Len=120                                                 |
| 503.298223    | 198.51.100.23  | 192.0.2.1       | HTTP     | GET /sales.html HTTP/1.1                                                               |
| 513.349457    | 192.0.2.1      | 198.51.100.23   | HTTP     | HTTP/1.1 200 OK (text/html)                                                            |
| 523.390692    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 533.441926    | 192.0.2.1      | 203.0.113.0     | TCP      | 443->54770 [SYN, ACK] Seq=0 Win=5792 Len=120                                            |
| 543.493162    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [ACK] Seq=1 Win=5792 Len=0                                                  |
| 553.544394    | 198.51.100.14  | 192.0.2.1       | TCP      | 14785->443 [SYN] Seq=0 Win=5792 Len=120                                                 |
| 563.599628    | 192.0.2.1      | 198.51.100.14   | TCP      | 443->14785 [SYN, ACK] Seq=0 Win=5792 Len=120                                            |
| 573.664863    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 583.730097    | 198.51.100.14  | 192.0.2.1       | TCP      | 14785->443 [ACK] Seq=1 Win=5792 Len=120                                                 |
| 593.795332    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=120                                                 |
| 603.860567    | 198.51.100.14  | 192.0.2.1       | HTTP     | GET /sales.html HTTP/1.1                                                               |
| 613.939499    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=120                                                 |
| 624.018431    | 192.0.2.1      | 198.51.100.14   | HTTP     | HTTP/1.1 200 OK (text/html)                                                            |
| 634.097363    | 198.51.100.5   | 192.0.2.1       | TCP      | 33638->443 [SYN] Seq=0 Win=5792 Len=120                                                 |
| 644.176295    | 192.0.2.1      | 203.0.113.0     | TCP      | 443->54770 [SYN, ACK] Seq=0 Win=5792 Len=120                                            |
| 654.255227    | 192.0.2.1      | 198.51.100.5    | TCP      | 443->33638 [SYN, ACK] Seq=0 Win=5792 Len=120                                            |
| 664.256159    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 675.235091    | 198.51.100.5   | 192.0.2.1       | TCP      | 33638->443 [ACK] Seq=1 Win=5792 Len=120                                                 |
| 685.236023    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 695.236955    | 198.51.100.16  | 192.0.2.1       | TCP      | 32641->443 [SYN] Seq=0 Win=5792 Len=120                                                 |
| 705.237887    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 716.228728    | 198.51.100.5   | 192.0.2.1       | HTTP     | GET /sales.html HTTP/1.1                                                               |
| 726.229638    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 736.230548    | 192.0.2.1      | 198.51.100.16   | TCP      | 443->32641 [RST, ACK] Seq=0 Win=5792 Len=120                                            |
| 746.330539    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 756.330885    | 198.51.100.7   | 192.0.2.1       | TCP      | 42584->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 766.331231    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 777.330577    | 192.0.2.1      | 198.51.100.5    | HTTP     | HTTP/1.1 504 Gateway Time-out (text/html)                                             |
| 787.351323    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 797.360768    | 198.51.100.22  | 192.0.2.1       | TCP      | 6345->443 [SYN] Seq=0 Win=5792 Len=0                                                   |
| 807.380773    | 192.0.2.1      | 198.51.100.7    | TCP      | 443->42584 [RST, ACK] Seq=1 Win=5792 Len=120                                            |
| 817.380878    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 827.383879    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 837.482754    | 192.0.2.1      | 203.0.113.0     | TCP      | 443->54770 [RST, ACK] Seq=1 Win=5792 Len=0                                             |
| 847.581629    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 857.680504    | 192.0.2.1      | 198.51.100.22   | TCP      | 443->6345 [RST, ACK] Seq=1 Win=5792 Len=0                                              |
| 867.709377    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 877.738241    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 887.767105    | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 8913.895969   | 192.0.2.1      | 203.0.113.0     | TCP      | 443->54770 [RST, ACK] Seq=1 Win=5792 Len=0                                             |
| 9013.919832   | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 9113.943695   | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 9213.967558   | 192.0.2.1      | 198.51.100.16   | TCP      | 443->32641 [RST, ACK] Seq=1 Win=5792 Len=120                                            |
| 9313.991421   | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 9414.015245   | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 9514.439072   | 192.0.2.1      | 203.0.113.0     | TCP      | 443->54770 [RST, ACK] Seq=1 Win=5792 Len=0                                             |
| 9614.862899   | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 9714.886727   | 198.51.100.9   | 192.0.2.1       | TCP      | 4631->443 [SYN] Seq=0 Win=5792 Len=0                                                   |
| 9815.310554   | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 9915.734381   | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 10016.158208  | 192.0.2.1      | 203.0.113.0     | TCP      | 443->54770 [RST, ACK] Seq=1 Win=5792 Len=0                                             |
| 10116.582035  | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 10217.005862  | 203.0.113.0    | 192.0.2.1       | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0                                                  |
| 10317.429678  | 192.0.

### 1. Identify the type of attack causing this network interruption

Reflect on the types of network intrusion attacks that you have learned about in this course so far. 
As a security analyst, identifying the type of network attack based on the incident is the first step to managing the attack and preventing similar attacks in the future.

Here are some questions to consider when determining what type of attack occurred:

- What do you currently understand about network attacks?
- Which type of attack would likely result in the symptoms described in the scenario?
- What is the difference between a denial of service (DoS) and distributed denial of service (DDoS)?
- Why is the website taking a long time to load and reporting a connection timeout error?

#### Answers:

- **What do you currently understand about network attacks?**

  Network attacks are typically carried out by malicious agents seeking some form of benefit, creating a disruptive effect on networks, devices, and operations of an organization/entity.
  Common attacks are often made via Malware, Spoofing, Packet Sniffing, and Packet Flooding, which can lead to the extraction of confidential and valuable information, damage to reputation, and financial loss.
  Examples of attacks used include DoS, DDoS, SYN, or ICMP Flooding, and Ping of Death.

- **Which type of attack would likely result in the symptoms described in the scenario?**

  Analyzing the exercise, I noticed that after using a packet sniffer to analyze the data packets, a large number of TCP SYN requests were revealed coming from an unknown IP address. Therefore, the likelihood of it being a Direct DoS SYN Flood Attack is very high and is the most probable cause.

- **What is the difference between a denial of service (DoS) and distributed denial of service (DDoS)?**

  In a DoS situation, a single source is used for attacking a target, whereas in a DDoS situation, multiple sources are used to attack a target.

- **Why is the website taking a long time to load and reporting a connection timeout error?**

  Since SYN packets are sent very frequently, multiplying several connection requests, the server becomes overwhelmed because the number of SYN requests exceeds the number of open ports to handle so many requests.
  The HTTP/1.1 504 Gateway Time-out (text/html) error is sent because the server takes too long to respond, and the [RST, ACK] packet is sent if the [SYN, ACK] request does not happen, canceling that request.

### Section 1: Identify the type of attack that may have caused this network interruption

**One potential explanation for the website's connection timeout error message is:**

As the attacker sends a large number of SYN Packets to the target, the server that receives them tries to respond to each request, leaving the port open for receiving the response. 
Since it cannot respond to all, the port remains open in standby waiting for the [ACK] packet, which will never arrive. 
The server is disrupted by its inability to respond, sending timeout errors.

**The logs show that:**

The logs show that initially the [SYN] request is successfully responded to, but progressively the attacker starts a process of flooding with SYN requests, and the server becomes unable to operate normally.

**This event could be:**

Since only a single IP Address is revealed in the attack on the server, there is a high probability that it is a Direct DoS SYN Flood Attack.

### Section 2: Explain how the attack is causing the website to malfunction

**When website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol. Explain the three steps of the handshake:**

1. The client sends a SYN Packet to the server to request a connection.
2. The server responds with a SYN/ACK packet as acknowledgment of the communication.
3. The client receives the SYN/ACK packet and sends an ACK packet as acknowledgment of receipt. When this process is successful, the TCP connection is open and is in compliance to send and receive information.

**Explain what happens when a malicious actor sends a large number of SYN packets all at once:**

When a large number of SYN packets are sent, the server tries to respond to all of them with a SYN/ACK packet, leaving the port open. Since there is never an ACK response to finalize each request, the server becomes incapacitated, continuously receives new SYN packet requests, and sends timeout error messages because it cannot respond adequately.

**Explain what the logs indicate and how that affects the server:**

The logs show that initially the [SYN] request is successfully responded to, but progressively the attacker starts a process of flooding with SYN requests, and the server becomes unable to operate normally because it waits for the ACK response from the client, continues to receive new SYN packet requests, and cannot respond to all requests, sending timeout errors.

**Observations:** 
Attacks like these on the network cause service interruptions, rendering affected servers inoperable. They can lead to loss of clients or even the business itself, damage to reputation due to inability to maintain normal operation of activities and operations, and raise legal issues.

As forms of prevention against the attack, temporarily shutting down the server helps in recovering the machine to its normal operation, and configuring the firewall to block the IP address that was causing the SYN flood attack, although it may only be effective until the attacker can spoof another IP Address.

---
[Back to Cybersecurity Portfolio](README.md)
