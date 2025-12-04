Log Baseline

Objective:
Collect baseline system and authentication logs across the homelab to understand normal user activity and system operations.

Commands Used:

sudo cat /var/log/auth.log | tail -n 25

sudo journalctl -p 3 -xb

sudo less /var/log/syslog


Findings:

Kubuntu showed normal login entries for user bjohnson.

No failed login or suspicious activity recorded.

System logs included service start messages and system updates.

Windows Event Viewer showed standard AD authentication events (IDs 4624, 4634).

Network and DHCP logs in OPNSense showed normal LAN communication.

Summary:
Normal baseline logging behavior established.
Future incidents will be compared against this data to identify anomalies such as brute-force attempts, privilege escalation, or unusual traffic.
