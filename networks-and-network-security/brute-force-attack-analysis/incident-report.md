# Security Incident Report

## Section 1: Network Protocol Identified

The network protocol identified in the packet captures
is **HTTP (Hypertext Transfer Protocol)**, operating
at the **Application Layer** of the TCP/IP model.

The tcpdump log confirms HTTP activity through the
following entries:
- `HTTP: GET / HTTP/1.1` → requests to
  yummyrecipesforme.com on port 80
- `HTTP: GET / HTTP/1.1` → requests to
  greatrecipesforme.com on port 80

DNS (Domain Name System) was also identified at the
Application Layer, used to resolve both domains to
their respective IP addresses.

---

## Section 2: Incident Documentation

**Date and Time of Incident:**
The incident occurred between 14:18:32 and 14:25:29,
as recorded in the tcpdump log.

**How the incident was discovered:**
Several customers reported being unable to access
yummyrecipesforme.com and being redirected to an
unknown website. A cybersecurity analyst reproduced
the issue and captured the network traffic using
tcpdump.

**What happened:**
At 14:18:32, the browser sent a DNS request to
dns.google.domain to resolve yummyrecipesforme.com,
which responded with IP address 203.0.113.22.

At 14:18:36, the browser initiated a TCP three-way
handshake with yummyrecipesforme.com on port 80,
followed by an HTTP GET request to the website.

The log shows a large volume of traffic on port 80
following the initial request, indicating the
download of a malicious file from the website.

At 14:20:32, the browser sent a DNS request to
resolve greatrecipesforme.com, which responded with
IP address 192.0.2.17, indicating a redirect caused
by the malware.

At 14:25:29, the browser initiated a TCP three-way
handshake with greatrecipesforme.com on port 80,
followed by an HTTP GET request, confirming the
user was redirected to the malicious website.

**Source of evidence:**
tcpdump traffic log captured during the investigation.

---

## Section 3: Recommendation to Prevent Brute Force Attacks

**Recommended measure: Two-Factor Authentication (2FA)**

Two-factor authentication — autenticação de dois
fatores — requires users to verify their identity
through two separate methods before gaining access
to a system.

This measure is effective because even if a malicious
actor obtains valid credentials through a brute force
attack, they would still be unable to access the
account without the second factor of authentication,
such as a one-time code sent to the user's phone or
email. This significantly reduces the risk of
unauthorized access to sensitive systems and data.
