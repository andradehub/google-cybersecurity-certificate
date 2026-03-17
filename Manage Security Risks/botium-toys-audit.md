# Security Audit - Botium Toys

## Scope and Goals
The scope of this audit is the entire security program  
at Botium Toys, including assets, internal network,  
and systems. The goal is to assess existing controls  
and compliance practices to improve the company's 
security posture.

## Risk Assessment Summary
- **Risk score:** 8/10 (high)
- **Main issues:** Inadequate asset management,
missing security controls, and lack of compliance
with U.S. and international regulations and standards,
including PCI DSS, GDPR, and SOC.
- **Potential impact:** High risk of fines and asset loss
due to a lack of compliance.

## Controls Assessment Checklist
| Control | In Place |  
|---|---|  
| Least Privilege | ❌ |  
| Disaster Recovery Plans | ❌ |  
| Password Policies | ❌ |  
| Separation of Duties | ❌ |  
| Firewall | ✅ |  
| Intrusion Detection System (IDS) | ❌ |  
| Backups | ❌ |  
| Antivirus Software | ✅ |  
| Manual Monitoring for Legacy Systems | ✅ |  
| Encryption | ❌ |  
| Password Management System | ❌ |  
| Locks (offices, storefront, warehouse) | ✅ |  
| CCTV Surveillance | ✅ |  
| Fire Detection/Prevention | ✅ |  

## Compliance Checklist

### Payment Card Industry Data Security Standard (PCI DSS)

| Best Practice | In Place |  
|---|---|  
| Only authorized users have access to credit card data | ❌ |  
| Credit card data is stored and transmitted securely | ❌ |  
| Data encryption procedures are implemented | ❌ |  
| Secure password management policies are adopted | ❌ |  

### General Data Protection Regulation (GDPR)

| Best Practice | In Place |  
|---|---|  
| E.U. customers' data is kept private/secured | ❌ |  
| E.U. customers are notified within 72 hours of a breach | ✅ |  
| Data is properly classified and inventoried | ❌ |  
| Privacy policies are enforced | ✅ |  

### System and Organizations Controls (SOC)

| Best Practice | In Place |  
|---|---|  
| User access policies are established | ✅ |  
| Sensitive data (PII/SPII) is confidential/private | ❌ |  
| Data integrity is ensured | ✅ |  
| Data is available to authorized individuals only | ❌ |  

## Recommendations

### Controls
Multiple controls and compliance best practices need  
to be implemented to improve Botium Toys' security  
posture and reduce risk.  

High priority controls that must be implemented immediately include:  
Least Privilege Principle and Separation of Duties to restrict   
unrestricted employee access to sensitive data,  
including cardholder data and customers' PII/SPII, ensuring  
only authorized personnel can access such information;  

Encryption to protect credit card information stored in the  
internal database;  

Disaster Recovery Plans and Backups to ensure   
business continuity in case of an attack; 

Intrusion Detection System (IDS) to identify  
potential threats before they cause damage.

Medium priority controls include:  
Strengthening the Password Policy and implementing a   
Password Management System to reduce vulnerabilities   
from weak credentials;   

Establishing a regular schedule for Legacy Systems  
monitoring and maintenance.

### Compliance

Regarding compliance, Botium Toys must prioritize  
PCI DSS requirements by encrypting credit card data  
and restricting access to authorized users only.  

For GDPR compliance, data must be properly classified  
and inventoried to ensure E.U. customers' data is  
kept private and secure.  

SOC controls must also be strengthened to ensure sensitive  
data confidentiality and proper access management.



