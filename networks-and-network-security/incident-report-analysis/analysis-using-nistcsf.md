# Incident Report Analysis  

## Incident Summary  
A multimedia company recently experienced a sudden  
stopping of the organization's network services. The stoppage  
of the services was caused by an incoming flood of ICMP packets. 

## Identify 
The company's cybersecurity team then investigated the security event.  
They found that a malicious actor had sent a flood of ICMP pings  
into the company's network through an unconfigured firewall.  
This vulnerability allowed the malicious attacker to overwhelm  
the company's network through a denial of service (DoS) attack.  

## Protect  
The team implemented basic security policies to protect the internal network,  
and policies implemented are:  
- A new firewall rule to limit the rate of incoming ICMP packets.
- Network monitoring software to detect abnormal traffic patterns.
- An IPS system to filter out some ICMP traffic based on suspicious characteristics.


## Detect
To improve the detection of future network attacks, the security team chose some  
tools to proactively detect an attack, including a source IP address verification   
on the firewall to check for spoofed IP addresses on incoming ICMP packets, and   
an IDS system to monitor all incoming traffic from the internet.
  

## Respond  
The incident management team responded by blocking incoming  
ICMP packets, stopping all non-critical network services,  
and restoring critical network services.

## Recover 
To help the organization recover from the incident, various security processes  
have been implemented to maintain the internal network online and secured,  
including the restoration of all critical network services.
