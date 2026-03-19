# Security Risk Assessment Report

## Incident Summary

A social media organization recently experienced  
a major data breach that compromised customers'  
personal information, including names and addresses.  
Following an inspection of the organization's  
network, four major vulnerabilities were identified  
as the root causes of the incident:  

1. Employees share passwords across the organization  
2. The admin password for the database is set  
   to the default  
3. Firewalls do not have rules in place to filter  
   incoming and outgoing network traffic  
4. Multifactor authentication (MFA) is not used  

If no action is taken to address these  
vulnerabilities, the organization remains at risk  
of experiencing additional data breaches and  
other attacks in the future.  

---

## Part 1: Hardening Tools and Methods Selected  
 
1. **Multi-factor Authentication (MFA)**  
2. **Password Policies**  
3. **Firewall Maintenance**  

---

## Part 2: Recommendations  

### 1. Multi-factor Authentication (MFA)  

MFA requires users to verify their identity through  
two or more methods before gaining access to a  
system, such as a password combined with a one-time  
code sent to a mobile device.  

This measure directly addresses vulnerability 4,  
the absence of MFA in the organization. The recent  
data breach demonstrated that relying solely on  
passwords is insufficient to protect sensitive  
customer data. By implementing MFA, even if an  
attacker obtains valid credentials through methods     
such as phishing or brute force attacks, they would  
still be unable to access the system without the  
second authentication factor. This significantly  
reduces the risk of unauthorized access to   
customers' personal information such as names  
and addresses.

--- 

### 2. Password Policies  

Password policies establish rules that govern how  
passwords are created, used, and managed across    
the organization.  

This measure address two critical vulnerabilities  
identified during the network inspection:  

The first vulnerability is password sharing among   
employees (vulnerability 1). The current practice  
of sharing passwords makes it impossible to track  
individual user activity and increases the risk  
of unauthorized access. Password policies should  
explicitly prohibit sharing credentials between  
employees and require each user to maintain unique,  
individual credentials.  

The second vulnerability is the use of the default  
admin password for the database (vulnerability 2).  
Default passwords are widely known and easily  
exploited by malicious actors, and their use likely  
contributed to the recent data breach. Password  
policies should require all default passwords to  
be changed immediately upon system setup and  
enforce the use of strong passwords that meet  
minimum complexity requirements, such as a   
combination of uppercase and lowercase letters,  
numbers, and special characters.  

--- 

### 3. Firewall Maintenance  

Firewall maintenance involves regularly defining,  
updating, and reviewing the rules that control  
incoming and outgoing network traffic.  

This measure addresses vulnerability 3, the absence  
of traffic filtering rules in the organization's  
firewalls. The lack of firewall rules allowed  
malicious traffic to freely enter and exit the  
network, contributing to the data breach that  
compromised customers' personal information.  

Firewall rules should be configured to allow only  
authorized traffic, block suspicious IP addresses  
and ports, and restrict access to sensitive systems  
such as the customer database. Regular maintenance  
ensures that the rules remain effective as new  
threats emerge and the organization's network  
evolves over time.
