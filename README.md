# Incident Response Report: ByteBistro.com SYN Flood Attack (Oct 31, 2025)

## Overview
On **October 31, 2025**, while working as a **Security Operations Center (SOC) Analyst** at **Byte Bistro Ltd**, I responded to a critical outage of the company's public web server, **ByteBistro.com**. The incident was caused by a **SYN flood attack**, where a high volume of incomplete TCP connections overwhelmed the server, resulting in service unavailability and HTTP 502/503 errors for customers.  

This project demonstrates the detection, analysis, and mitigation of a network-level denial-of-service (DoS) attack, providing a realistic example of professional cybersecurity operations.


## Actions Taken / Mitigation
To restore service and prevent further disruption, the following mitigation measures were implemented:

1. **SYN Cookies Enabled**  
   - Activated on the web server to protect against resource exhaustion caused by half-open TCP connections.  
   - Ensured legitimate traffic continued to be processed during the attack.

2. **Firewall IP Filtering**  
   - Blocked identified malicious IP addresses directly at the firewall:  
     - 203.0.113.45  
     - 198.51.100.200  
     - 198.51.100.71  
   - Prevented attack traffic from reaching the server and consuming resources.

3. **Temporary SYN Rate Limiting**  
   - Restricted the number of new connections per IP per second to mitigate additional attacks from unknown sources.  
   - Ongoing monitoring ensured that legitimate users were not impacted.

Following these measures, the web server **resumed normal functionality** and remained stable, with no further signs of SYN flood activity.


## Skills Practiced
During this incident, I applied and developed key SOC skills, including:  
- **Network Traffic Analysis:** Capturing and analyzing packet-level data using **Wireshark**.  
- **IDS and SIEM Log Correlation:** Interpreting alerts and logs to identify attack patterns.  
- **Incident Mitigation:** Implementing SYN cookies, firewall rules, and rate limiting.  
- **Log Analysis:** Reviewing kernel and system logs to confirm attack scope.  
- **Incident Documentation:** Writing professional reports and mitigation summaries.  
- **Threat Assessment & Future Planning:** Recommending stress testing and TCP timeout adjustments for long-term resilience.


## Supporting Documents
The following artifacts are included in the repository for reference:  
- **Packet Capture:** `snippet_oct31_0948.pcap` – live traffic during the attack.  
- **SIEM Log Analysis:** Documentation correlating IDS and kernel logs.  
- **Mitigation Report:** Summary of actions taken and post-incident status.


## Future Recommendations
- Conduct **regular stress and penetration testing** to simulate SYN flood scenarios.  


## Notes
**Disclaimer:** This is a simulated incident created solely for educational and training purposes. All data, IP addresses, and events are fictional.

