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

*
