# Security Incident Report – YummyRecipesForMe.com

## 1. Scenario

You are a cybersecurity analyst for **yummyrecipesforme.com**, a website that sells recipes and cookbooks.  
A former employee decided to lure users to a fake website with malware.  

The former employee/hacker executed a brute force attack to gain access to the web host. They repeatedly entered several known default passwords for the administrative account until they correctly guessed the right one.  
After obtaining the login credentials, they were able to access the admin panel and change the website’s source code.  
They embedded a JavaScript function in the source code that prompted visitors to download and run a file upon visiting the website.  
After embedding the malware, the hacker changed the password to the administrative account.  
When customers download the file, they are redirected to a fake version of the website that contains the malware.  

Several hours after the attack, multiple customers emailed **yummyrecipesforme**’s helpdesk.  
They complained that the company’s website had prompted them to download a file to access free recipes. The customers claimed that, after running the file, the address of the website changed and their personal computers began running more slowly.  

In response to this incident, the website owner tries to log in to the admin panel but is unable to, so they reach out to the website hosting provider.  
You and other cybersecurity analysts are tasked with investigating this security event.

To address the incident, you create a sandbox environment to observe the suspicious website behavior.  
You run the network protocol analyzer **tcpdump**, then type in the URL for the website, **yummyrecipesforme.com**.  
As soon as the website loads, you are prompted to download an executable file to update your browser. You accept the download and allow the file to run. You then observe that your browser redirects you to a different URL, **greatrecipesforme.com**, which contains the malware.

The logs show the following process:

- The browser initiates a DNS request: It requests the IP address of the **yummyrecipesforme.com** URL from the DNS server.
- The DNS replies with the correct IP address.
- The browser initiates an HTTP request: It requests the **yummyrecipesforme.com** webpage using the IP address sent by the DNS server.
- The browser initiates the download of the malware.
- The browser initiates a DNS request for **greatrecipesforme.com**.
- The DNS server responds with the IP address for **greatrecipesforme.com**.
- The browser initiates an HTTP request to the IP address for **greatrecipesforme.com**.

A senior analyst confirms that the website was compromised.  
The analyst checks the source code for the website. They notice that JavaScript code had been added to prompt website visitors to download an executable file.  
Analysis of the downloaded file found a script that redirects the visitors’ browsers from **yummyrecipesforme.com** to **greatrecipesforme.com**.  

The cybersecurity team reports that the web server was impacted by a brute force attack. The disgruntled hacker was able to guess the password easily because the admin password was still set to the default password.  
Additionally, there were no controls in place to prevent a brute force attack.

Your job is to document the incident in detail, including identifying the network protocols used to establish the connection between the user and the website.  
You should also recommend a security action to take to prevent brute force attacks in the future.

---

## 2. Identify the network protocol involved in the incident

14:18:32.192571 IP your.machine.52444 > dns.google.domain: 35084+ A? yummyrecipesforme.com. (24)
14:18:32.204388 IP dns.google.domain > your.machine.52444: 35084 1/0/0 A 203.0.113.22 (40)

14:18:36.786501 IP your.machine.36086 > yummyrecipesforme.com.http: Flags [S], seq 2873951608, win 65495, options [mss 65495,sackOK,TS val 3302576859 ecr 0,nop,wscale 7], length 0
14:18:36.786517 IP yummyrecipesforme.com.http > your.machine.36086: Flags [S.], seq 3984334959, ack 2873951609, win 65483, options [mss 65495,sackOK,TS val 3302576859 ecr 3302576859,nop,wscale 7], length 0
14:18:36.786529 IP your.machine.36086 > yummyrecipesforme.com.http: Flags [.], ack 1, win 512, options [nop,nop,TS val 3302576859 ecr 3302576859], length 0
14:18:36.786589 IP your.machine.36086 > yummyrecipesforme.com.http: Flags [P.], seq 1:74, ack 1, win 512, options [nop,nop,TS val 3302576859 ecr 3302576859], length 73: HTTP: GET / HTTP/1.1
14:18:36.786595 IP yummyrecipesforme.com.http > your.machine.36086: Flags [.], ack 74, win 512, options [nop,nop,TS val 3302576859 ecr 3302576859], length 0
…<a lot of traffic on port 80>...

14:20:32.192571 IP your.machine.52444 > dns.google.domain: 21899+ A? greatrecipesforme.com. (24)
14:20:32.204388 IP dns.google.domain > your.machine.52444: 21899 1/0/0 A 192.0.2.17 (40)

14:25:29.576493 IP your.machine.56378 > greatrecipesforme.com.http: Flags [S], seq 1020702883, win 65495, options [mss 65495,sackOK,TS val 3302989649 ecr 0,nop,wscale 7], length 0
14:25:29.576510 IP greatrecipesforme.com.http > your.machine.56378: Flags [S.], seq 1993648018, ack 1020702884, win 65483, options [mss 65495,sackOK,TS val 3302989649 ecr 3302989649,nop,wscale 7], length 0
14:25:29.576524 IP your.machine.56378 > greatrecipesforme.com.http: Flags [.], ack 1, win 512, options [nop,nop,TS val 3302989649 ecr 3302989649], length 0
14:25:29.576590 IP your.machine.56378 > greatrecipesforme.com.http: Flags [P.], seq 1:74, ack 1, win 512, options [nop,nop,TS val 3302989649 ecr 3302989649], length 73: HTTP: GET / HTTP/1.1
14:25:29.576597 IP greatrecipesforme.com.http > your.machine.56378: Flags [.], ack 74, win 512, options [nop,nop,TS val 3302989649 ecr 3302989649], length 0
…<a lot of traffic on port 80>...

**Answer:**  
There is more than one protocol involved in the incident: **DNS**, **TCP**, and **HTTP**.  
However, the main one is **HTTP**, because the download of the executable file (malware) occurred via the website access.

---

## 3. Document the incident

**Answer:**  

- **Affected Website:** `yummyrecipesforme.com`
- **Attack Type:** Brute force attack + malware injection
- **Impact:** User devices infected, redirected to malicious domain `greatrecipesforme.com`
- **Detection:** Multiple customer complaints to the helpdesk

The incident occurred on the website **yummyrecipesforme.com**, a website that sells recipes and cookbooks.  
Multiple customers emailed the website helpdesk to report the situation, complaining that the company’s website had prompted them to download a file to access free recipes, but suddenly the website’s address changed and their personal devices began running more slowly.  

The website’s owner tried to log in to the admin panel but could not, so they contacted the website hosting provider.  

Afterwards, I was tasked to investigate the incident, so I created a sandbox environment to observe suspicious activity of the website.  
I ran **tcpdump** with the website’s name, and upon loading the site I was prompted to download an executable file to update the browser, which I accepted.  

The browser then redirected to a different URL, **greatrecipesforme.com**, which contained the malware.  

Through the analysis of the logs, it was revealed that my computer made a [SYN] request to the DNS server via port 52444, targeting `yummyrecipesforme.com`.  
A [SYN/ACK] packet was returned with the IP address `203.0.113.22`.

After this step, my computer requested a connection ([S] flag) via port 36086 directly to the website (`yummyrecipesforme.com.http`), and received a confirmation of my request ([S.] flag).  

Next, the log shows the HTTP code: `GET / HTTP/1.1`, noting that the browser made a request using the HTTP GET method, version 1.1 of the protocol, and where the connection from my machine to the website was signaled with the [P] flag, requesting information.  

At this moment, I recognized that the executable file download could be occurring within this communication.  

After this, there is a ~2-minute gap between logs (based on timestamps).  
After the file download, there is a change in the traffic from my computer to the DNS server, again via port 52444, making a new [SYN] request.  

This time, the DNS server directed to a new IP address (`192.0.2.172`) associated with the URL (`greatrecipesforme.com.http`), as well as a new port (`.56378`), revealing the spoofed website.

---

## 4. Recommend one remediation for brute force attacks

As prevention for similar problems in the future, I recommend the use of **strong password policies**, because one of the major issues in this situation was the ease with which the attacker guessed the password by trying default passwords through trial and error.  

In addition, I suggest adopting **Multi-Factor Authentication (MFA)** to validate identity in two or more authentication processes — for example, a strong password combined with **One-Time Passwords (OTP)**.  
This would add an extra layer of security, helping to mitigate the chance of brute force attacks.

---

## Reflection
The exercise highlights the importance of strong authentication controls and brute force protection mechanisms.

---
[Back to Cybersecurity Portfolio](README.md)
