During this investigation,

A windows host alert was investigated using Kibana and the attack was investigated using Sguil in security onion virtual machine.



***//The lab is based on an exercise from the website, malware-traffic-analysis.net which is an excellent resource for learning how to analyse network and host attacks//***

**Part 1: Investigation from Sguil dashboard.**

* The first alert was reviewed in Wireshark and it was a DNS update. The domain shown below.

* The second alert's transcript viewed in capME! showed a GET request to an executable with the hash shown below, just at the beginning of the text.

* The exe file from the second alert was exported to storage and a hash for it was generated.

* Hash was looked up on talosintelligence.com/talos_file_reputation

* Talos reputation report and aliases

* Recmos returned the following

* The second executable in the list of alerts was found and exported and the fingerprint(hash) was generated for it.

* The second file f4.exe had the AMP/CEP detection name below

* All the other three alerts in the GET request for the same f4.exe file in the transcript. Two of the signature IDs are the same but all indicating Trojan activity.




**Part 2: Using Kibana to Investigate Alerts**

* Filtered for the the date and time period of the event

* Filtered out HTTP activity and found 4 downloaded files and four sites 

* Filtered for DNS alerts, tested all domains seen on virustotal for maliciousness

* Filtered for DCE/RPC for information about windows network remote procedures and resources involved and got the following 

* Filtered for Kerberos for information on hostnames and domain names used

* PE for information on portable executables

* SSL and x.509 for information on security certificate and countries that were used

* SMB for more information on the SMB shares on the littletigers network

* Weird for protocol and service anomalies and malformed communications