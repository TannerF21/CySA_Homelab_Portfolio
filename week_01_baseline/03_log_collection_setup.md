#  Week 1 – Day 3: Log Collection Setup

##  Objective  
Configure centralized log collection in the homelab by forwarding Kubuntu system logs to a central syslog server (Kali) for monitoring and future analysis.

---

##  Commands Used
```bash
# On Kali (Syslog Receiver)
sudo apt update
sudo apt install rsyslog -y
sudo systemctl enable --now rsyslog
```
# Enable UDP listener on port 514
sudo nano /etc/rsyslog.conf
# Uncomment:
 module(load="imudp")
 input(type="imudp" port="514")
sudo systemctl restart rsyslog

# On Kubuntu (Log Forwarder)
sudo nano /etc/rsyslog.d/90-remote.conf
# Add:
# *.* @10.10.10.168:514
sudo systemctl restart rsyslog
Findings
Verified that Kali successfully received Kubuntu system logs via UDP/514.

Live log events (e.g., service restarts, SSH logins) appeared in Kali’s /var/log/syslog.

Log forwarding confirmed network connectivity and real-time monitoring capabilities.

Summary

Centralized logging successfully implemented using rsyslog.
This configuration provides a foundation for security monitoring and future SIEM integration (e.g., ELK or Graylog).
Next steps include parsing logs for events and establishing alert rules for anomalies
