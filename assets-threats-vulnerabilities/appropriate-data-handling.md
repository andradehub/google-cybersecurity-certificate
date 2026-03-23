# Data Leak Worksheet

## Incident Summary

A sales manager shared access to a folder of  
internal-only documents with their team during  
a meeting. The folder contained files associated  
with a new product that has not been publicly  
announced. It also included customer analytics  
and promotional materials. After the meeting,  
the manager did not revoke access to the internal  
folder, but warned the team to wait for approval  
before sharing the promotional materials with  
others.  
   
During a video call with a business partner, a  
member of the sales team forgot the warning from  
their manager. The sales representative intended  
to share a link to the promotional materials so  
that the business partner could circulate the  
materials to their customers. However, the sales  
representative accidentally shared a link to the  
internal folder instead. Later, the business  
partner posted the link on their company's social  
media page assuming that it was the promotional  
materials.  

---

## Control
**Least Privilege**  

---

## Issue(s)
What factors contributed to the information leak?  

The first issue is a lack of the principle of least  
privilege, because too many employees had access  
to internal-only documents that were not necessary  
for their functions.  

The second issue is from the manager who did not  
revoke access to the internal folder after the  
meeting.   
   
The third issue is a consequence of all the others  
— the lack of the principle of least privilege  
combined with inattention from the manager directly  
contributed to the data leak.  

---

## Review
What does NIST SP 800-53: AC-6 address?  

AC-6 establishes that employees should only have  
access to information they need for their specific  
functions. This principle was not applied by the  
organization or the manager, which caused the data  
leak through the business partner.  

---

## Recommendation(s)  
How might the principle of least privilege be  
improved at the company?  

The manager should never share a folder of  
internal-only documents in a meeting unless all  
attendees have the appropriate permissions for  
that level of access. Sharing such documents with  
the entire team violates AC-6.  

Additionally, the manager must revoke access to  
shared internal folders immediately after the  
meeting ends, ensuring that sensitive documents  
are only accessible during the authorized period.  

---

## Justification  
How might these improvements address the issues?  

These recommendations are based on NIST SP 800-53  
AC-6 and directly address the mistakes made by the  
manager that led to the entire data leak. By  
restricting access to internal documents only to  
those who need them and revoking access after use,  
the organization significantly reduces the risk of   
accidental or unauthorized data exposure.   
