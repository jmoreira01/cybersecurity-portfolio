# Network Traffic Analysis: YummyRecipesForMe.com Incident

## Scenario Summary
You are a cybersecurity analyst working at a company that specializes in providing IT services for clients. 
Several customers of clients reported that they were not able to access the client company website www.yummyrecipesforme.com, and saw the error “destination port unreachable” after waiting for the page to load. 

You are tasked with analyzing the situation and determining which network protocol was affected during this incident. 
To start, you attempt to visit the website and you also receive the error “destination port unreachable.” 
To troubleshoot the issue, you load your network analyzer tool, tcpdump, and attempt to load the webpage again. To load the webpage, your browser sends a query to a DNS server via the UDP protocol to retrieve the IP address for the website's domain name; this is part of the DNS protocol. Your browser then uses this IP address as the destination IP for sending an HTTPS request to the web server to display the webpage. 
The analyzer shows that when you send UDP packets to the DNS server, you receive ICMP packets containing the error message: “udp port 53 unreachable.”

## Log:
13:24:32.192571 IP 192.51.100.15.52444 > 203.0.113.2.domain: 35884+ A? 
yummyrecipesforme.com. (24)
13:24:36.098564 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2 
udp port 53 unreachable length 254

13:26:32.192571 IP 192.51.100.15.52444 > 203.0.113.2.domain: 35884+ A? 
yummyrecipesforme.com. (24)
13:27:15.934126 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2 
udp port 53 unreachable length 320

13:28:32.192571 IP 192.51.100.15.52444 > 203.0.113.2.domain: 35884+ A? 
yummyrecipesforme.com. (24)
13:28:50.022967 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2 
udp port 53 unreachable length 150

### In the tcpdump log, you find the following information:

1. The first two lines of the log file show the initial outgoing request from your computer to the DNS server requesting the IP address of yummyrecipesforme.com. This request is sent in a UDP packet.

2. The third and fourth lines of the log show the response to your UDP packet. In this case, the ICMP 203.0.113.2 line is the start of the error message indicating that the UDP packet was undeliverable to port 53 of the DNS server.

3. In front of each request and response, you find timestamps that indicate when the incident happened. In the log, this is the first sequence of numbers displayed: 13:24:32.192571. This means the time is 1:24 p.m., 32.192571 seconds.

4. After the timestamps, you will find the source and destination IP addresses. In the first line, where the UDP packet travels from your browser to the DNS server, this information is displayed as: 192.51.100.15 > 203.0.113.2.domain. The IP address to the left of the greater than (>) symbol is the source address, which in this example is your computer’s IP address. The IP address to the right of the greater than (>) symbol is the destination IP address. In this case, it is the IP address for the DNS server: 203.0.113.2.domain. For the ICMP error response, the source address is 203.0.113.2 and the destination is your computers IP address 192.51.100.15.

5. After the source and destination IP addresses, there can be a number of additional details like the protocol, port number of the source, and flags. In the first line of the error log, the query identification number appears as: 35084. The plus sign after the query identification number indicates there are flags associated with the UDP message. The "A?" indicates a flag associated with the DNS request for an A record, where an A record maps a domain name to an IP address. The third line displays the protocol of the response message to the browser: "ICMP," which is followed by an ICMP error message.

6. The error message, "udp port 53 unreachable" is mentioned in the last line. Port 53 is a port for DNS service. The word "unreachable" in the message indicates the UDP message requesting an IP address for the domain "www.yummyrecipesforme.com" did not go through to the DNS server because no service was listening on the receiving DNS port.

7. The remaining lines in the log indicate that ICMP packets were sent two more times, but the same delivery error was received both times. 


Now that you have captured data packets using a network analyzer tool, it is your job to identify which network protocol and service were impacted by this incident. Then, you will need to write a follow-up report. 

As an analyst, you can inspect network traffic and network data to determine what is causing network-related issues during cybersecurity incidents. Later in this course, you will demonstrate how to manage and resolve incidents. For now, you only need to analyze the situation. 

This event, in the meantime, is being handled by security engineers after you and other analysts have reported the issue to your direct supervisor. 


### Part 1: Summary of the Problem Found in the DNS and ICMP Traffic Log

The UDP protocol, as analyzed by the tcpdump tool, reveals "udp port 53 unreachable" when sending UDP packets to the DNS server (IP: 203.0.113.2). This is accompanied by ICMP packets returning an error message indicating that port 53 is unreachable. 
The primary role of port 53 is to facilitate DNS services, serving as the default port for translating domain names (ex, www.yummyrecipesforme.com) into IP addresses. 
The most likely cause of this incident is the DNS server's inability to respond to UDP requests on port 53, potentially due to a service failure or a network block.

### Part 2: Analysis Explanation and Cause of the Incident

The incident began at 1:24 p.m. (13:24), as indicated by the initial timestamp (13:24:32.192571) in the tcpdump log, when multiple customers reported inability to access the website www.yummyrecipesforme.com.
The IT team was notified through reports from several customers who encountered a "destination port unreachable" error while attempting to load the website.
I was tasked with analyzing the issue and initiated an investigation using the tcpdump network protocol analyzer. I attempted to access the website, capturing network traffic to observe the interaction between my system (IP: 192.51.100.15) and the DNS server (IP: 203.0.113.2).
The logs revealed that port 53, designated for DNS services, failed to respond to UDP requests, returning ICMP packets with the error "udp port 53 unreachable." 
The affected protocol is UDP, which could not elicit a response from the DNS server, preventing domain name resolution into IP addresses. This issue persisted across multiple attempts, as noted in the log timestamps (e.g., 13:24:36.098564, 13:27:15.934126).
I conclude that the primary cause is the DNS server's inability to process UDP requests on port 53, likely due to a service failure or a configuration block on the server.
The issue was escalated to my supervisor for further analysis and resolution by the security engineering team.

## Reflection
This exercise helped me to analyze network traffic and identify protocol-related issues. 


---
[Back to Cybersecurity Portfolio](README.md)
