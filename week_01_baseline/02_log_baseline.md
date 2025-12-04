# Log Baseline

##  Objective  
Collect baseline system and authentication logs across the homelab to understand normal user activity and system operations.

---

##  Commands Used
```bash
sudo cat /var/log/auth.log | tail -n 25
sudo journalctl -p 3 -xb
sudo less /var/log/syslog
Findings
Kubuntu showed normal login entries for user bjohnson.

No failed login or suspicious activity recorded.

System logs included service start messages and routine updates.

Windows Event Viewer showed standard AD authentication events (IDs 4624, 4634).

Network and DHCP logs in OPNSense showed normal LAN communication and expected device leases.

Summary
Normal baseline logging behavior was established across all systems.
This data serves as a reference for future comparisons during security monitoring and incident response exercises.
Anomalies such as brute-force attempts, privilege escalation, or unauthorized access will be detected by contrasting against this baseline.
