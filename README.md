# Automated deploy of elasticstack using Ansible

### Two main ideas:
1. [Pastehunter](https://github.com/kevthehermit/PasteHunter) project for monitoring sources like pastebin, github, etc.
ELK-Stack is configured with 3 data and 1 master nodes, HAProxy for load balancing and proper data ingestion, PasteHunter as data scrapping tool.
3. Analysis of fdns data from Rapid7 [sonar](https://opendata.rapid7.com/sonar.fdns_v2/) project
Download files from rapid7 website and use filebeat for data ingestion. The project was used as recon source during engagments. Now it's better to use Amazon AWS services like it is described [here](https://blog.rapid7.com/2018/10/16/how-to-conduct-dns-reconnaissance-for-02-using-rapid7-open-data-and-aws/)

### Configuration:
1. Please configure ansible according to your environment
2. Set variable for elastic in group vars
3. Don't forget about "split brain" situation, configure total number of master nodes / 2 + 1

### Todo:
1. Automaticaly deploy elastic with [Security Requirements](https://www.elastic.co/guide/en/elasticsearch/reference/current/configuring-security.html)
2. Make elasticsearch roles
3. Autoconfigure system data storage with lvm of various sizes
