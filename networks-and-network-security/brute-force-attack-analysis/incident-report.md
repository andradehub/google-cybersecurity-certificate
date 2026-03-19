# Security Incident Report

## Section 1: Network Protocol Identified

The network protocol identified in the packet captures
is HTTP (Hypertext Transfer Protocol), operating at
the Application Layer of the TCP/IP model.

The tcpdump log confirms HTTP activity through the
following entries:
- HTTP: GET / HTTP/1.1 → request to
  yummyrecipesforme.com on port 80
- HTTP: GET / HTTP/1.1 → request to
  greatrecipesforme.com on port 80

DNS (Domain Name System) was also identified at the
Application Layer, used to resolve both domains to
their respective IP addresses:
- yummyrecipesforme.com → 203.0.113.22
- greatrecipesforme.com → 192.0.2.17

---

## Section 2: Incident Documentation

**Date and Time of Incident:**
The incident was recorded between 14:18:32 and
14:25:29, as captured in the tcpdump log.

**How the attack started:**
A former employee executed a brute force attack
against the administrative account of
yummyrecipesforme.com, repeatedly entering known
default passwords until the correct credentials
were obtained. After gaining access to the admin
panel, the attacker modified the website's source
code by embedding a malicious JavaScript function
that prompted visitors to download and run an
executable file. The attacker then changed the
administrative account password, locking out the
website owner.

**How the incident was discovered:**
Several hours after the attack, multiple customers
contacted the helpdesk reporting that the website
had prompted them to download a file to access
free recipes. Customers reported that after running
the file, the website address changed and their
computers began running more slowly. The website
owner attempted to log in to the admin panel but
was unable to, and contacted the hosting provider.
Cybersecurity analysts were then tasked with
investigating the incident.

**What the investigation found:**
A sandbox environment was created to safely observe
the suspicious website behavior. Using tcpdump to
capture network traffic, the analyst visited
yummyrecipesforme.com and was prompted to download
an executable file to update the browser.

At 14:18:32, the browser sent a DNS request to
resolve yummyrecipesforme.com, receiving IP address
203.0.113.22 in response.

At 14:18:36, a TCP three-way handshake was completed
with the server, followed by an HTTP GET request.
A large volume of traffic on port 80 was observed,
indicating the download of the malicious file.

At 14:20:32, the browser automatically sent a DNS
request to resolve greatrecipesforme.com, receiving
IP address 192.0.2.17, confirming the malware had
triggered a redirect to the malicious website.

At 14:25:29, the browser completed a TCP three-way
handshake with greatrecipesforme.com and sent an
HTTP GET request, confirming the user had been
redirected to the malicious website.

**Source of evidence:**
tcpdump traffic log captured during sandbox
investigation.

---

## Section 3: Recommendation to Prevent Brute Force Attacks

**Recommended measure: Two-Factor Authentication (2FA)**

Two-factor authentication requires users to verify
their identity through two separate methods before
gaining access to a system. In this incident, the
attacker was able to gain access solely by guessing
the correct password through a brute force attack.

With 2FA in place, even if a malicious actor obtains
valid credentials, they would still be unable to
access the account without the second factor of
authentication, such as a one-time code sent to the
administrator's phone or email. This significantly
reduces the risk of unauthorized access to sensitive
systems, particularly for high-privilege accounts
such as administrative panels.
