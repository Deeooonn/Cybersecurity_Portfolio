The first part of the activity involves using kibana to investigate an SQL injection attack.

The second activity used Kibana to investigate an a DNS exfiltration incident...


**Part 1** HTTP (SQL injection)

* Before starting, in kibana, the timeframe of the data displayed was first changed to display a time period sufficient enough to capture data from multiple dates including the events to be investigated—June 2020.

* The status of services was checked using 
        
               sudo so-status

* Filtered for http traffic under the Zeek (Bro) Hunting heading.

* Scrolled to view event info of events

* Pivoted to capMe! in the ID field in the event info by clicking on the hyperlinked id

* Found the query used in performing SQL injection for authentication bypass

* Found exposed user records

**Part 2** DNS Exfiltration