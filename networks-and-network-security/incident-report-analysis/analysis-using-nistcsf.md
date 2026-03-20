# Incident Report Analysis  

## Incident Summary  
A multimedia company recently experienced a suddenly 
stopping of organization's network services. The stoppage  
of the services is because a incoming flood of ICMP packets. 

## Identify 
The company's cybersecurity team then investigated the security event.  
They found that a malicious actor had sent a flood of ICMP pings  
into the company's network through an unconfigured firewall.  
This vulnerability allowed the malicious attacker to overhelm  
the company's network through a deinal of service (DoS) attack.  

## Protect  
The team implemented basics security policies to protect the internal network,  
and policies implemented are:  
- A new firewall rule to limit the rate of incoming ICMP packets.
- Network monitoring sofware to detect abnormal traffic patterns.
- An IPS system to filter out some ICMP traffic based on suspicious characteristics.


## Detect
To improve the detect system of a future network attacks, the security team choose some  
tools to previously detect an attack, including a source IP address verification   
on the firewall to check for spoofed IP addresses on incoming ICMP packets, and   
a IDS system to monitor all incoming traffic from the internet.
  

## Respond  
The incident management team responded by blocking incoming  
ICMP packets, stopping all non-critical network services offline,  
and restoring critical network services.

## Recover 
To organization recover from the incident, diverses security proccess  
have been implemented to maintain the internal network online and secured, 
as the restoring all critical network services.
