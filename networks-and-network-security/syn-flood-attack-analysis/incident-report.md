# Cybersecurity Incident Report

## Section 1: Identify the type of attack that may have caused this network interruption  

**One potential explanation for the website's connection timeout error message is:**  
A SYN Flood attack performed by a malicious actor, exhausting the server's     
resources and making it unavailable to legitimate users.    
 
**The logs show that:**    
The IP address 203.0.113.0 continuously sent SYN packets to the server  
(192.0.2.1) on port 443, without completing the TCP three-way handshake.  
The server attempted to respond with SYN-ACK packets but never received  
the final ACK, causing its connection table to fill up. As a result,  
legitimate users began receiving RST, ACK responses and 504 Gateway  
Timeout errors.  

**This event could be:**  
A DoS (Denial of Service) attack originating from a single source —  
IP address 203.0.113.0 — using the SYN Flood technique to overwhelm  
the server and deny service to legitimate users.  

---

## Section 2: Explain how the attack is causing the website to malfunction  

**When website visitors try to establish a connection with the web server,  
a three-way handshake occurs using the TCP protocol:**  

1. **SYN** — The client sends a SYN packet to the server requesting  
a connection.  

2. **SYN-ACK** — The server responds with a SYN-ACK packet,  
acknowledging the request and reserving resources while waiting  
for confirmation.  

3. **ACK** — The client sends an ACK packet confirming the connection,  
completing the handshake and establishing communication.  

**Explain what happens when a malicious actor sends a large number  
of SYN packets all at once:**  
The attacker sends a flood of SYN packets without ever completing  
the handshake with the final ACK. The server reserves resources for  
each incomplete connection, waiting for confirmations that never arrive.  
This rapidly exhausts the server's connection table, leaving no  
resources available to handle legitimate connection requests.  

**Explain what the logs indicate and how that affects the server:**  
The logs show that starting at timestamp 3.390692, IP 203.0.113.0  
began sending continuous SYN packets to port 443 of the server  
(192.0.2.1). The server responded with SYN-ACK packets but never  
received the final ACK. As the attack progressed, the server began  
sending RST, ACK packets to legitimate users such as 198.51.100.16  
and 198.51.100.7, indicating it could no longer accept new connections.  
By timestamp 7.330577, the server was returning HTTP 504 Gateway  
Timeout errors, confirming that the SYN Flood had rendered the  
service unavailable.  
