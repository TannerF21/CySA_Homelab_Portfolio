Hostname	     IP Address	    OS/Role	                   Purpose
OPNSense	     10.10.10.1	    Firewall	             DHCP & Gateway
DC01	         10.10.10.160	  Windows Server 2022  	Domain Controller
Kali	         10.10.10.168	  Kali Linux	           Attacker VM
Kubuntu 	     10.10.10.184 	Linux Client	     Domain-Joined Workstation
Metasploitable 10.10.10.200	  Linux	                 Vulnerable Target



Commands used:
ip a
sudo nmap -sn 10.10.10.0/24
sudo nmap -sn -R 10.10.10.0/24
