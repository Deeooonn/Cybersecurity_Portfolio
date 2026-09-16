In this activity, a review was done after an attack and a compromised host was isolated.

Legitimate users no longer had access to a file confidential.txt and logs were reviewed to understand how it was compromised.

Security Onion VM was used for this activity
 Sguil was used to review alerts
 Wireshark was used to view and analyse packet captures
 Kibana was pivoted to for interactive dashboard and visualization

* Alert was reviewed in sguil to indicate that attacker gained root access
* "Show packet data" and "show rule" boxes were checked to show the alert in more detail
* ID of the alert was right clicked to view transcript that displayed commands executed on the
  target by the attacker including the below to view passwords.
               
              cat /etc/shadow

* Pivoting to Wireshark by right clicking on alert ID, we could read all packets assembled in the TCP conversation by selecting follow > TCP stream

* Pivoting to kibana by right clicking on the src/dest ip showed the associated alerts and then filtering for the files showed files transmitted during the conversation. 

* Clicking on the conversation id displayed the capME! view of the stolen fle content.

**The attacker had been reading user and password data which surely gave him root privileges
  to seize the file and deny eligible users availability**


**5 tuple usage**

Wireshark and sguil showed and used source and destination addresses and ports
Kibana used source address but could have used either 
Wireshark indicated the kind of protocol.








**It's advised that users change their passwords and comply with the security policies especially as it may be in a production environment.**