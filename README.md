# Network Traffic Analysis & Threat Detection

Objective

Analyze network traffic to establish a baseline of normal activity and identify deviations that may indicate malicious behavior. This project focused on practicing packet inspection and IDS alert triage techniques commonly performed by SOC analysts to differentiate benign traffic from potentially actionable security events.

Tools Used

- Wireshark - packet capture, filtering, and protocol analysis
- Snorby (Snort IDS interface) - monitoring and reviewing intrusion detection alerts

Environment

- Traffic captured from a controlled lab environment
- Analysis performed over a defined capture window during normal system activity

Methodology

Traffic Baseline Analysis

- Captured network traffic and applied protocol, IP, and port-based filters in Wireshark
- Identified and documented common baseline traffic patterns, including:
    - DHCP communication
    - Broadcast and ARP traffic
    - Normal TCP/UDP activity associated with routine system operations
- Used protocol statistics and packet inspection to understand expected network behavior

Alert Review & Investigation

- Reviewed IDS alerts generated in Snorby during the capture period
- Examined alert metadata such as:
    - Source and destination IP addresses
    - Ports and protocols involved
    - Signature descriptions and alert priority
- Correlated IDS alerts with packet-level data in Wireshark to evaluate whether alerts aligned with:
    - Legitimate network activity
    - Misconfigurations or noise
    - Potentially suspicious or unauthorized connections

 Analysis & Decision-Making

 - Compared flagged traffic against established baseline behavior
 - Determined which alerts represented false positives versus activity requiring further investigation
 - Practiced analyst judgment by focusing on context rather than alert volume alone

Key Findings

- Established a baseline of normal network activity, including DHCP and routine broadcast communications
- Identified IDS alerts triggered by abnormal traffic patterns and evaluated them to determine whether they represented benign activity or required further investigation
- Differentiated benign alerts from suspicious behavior by correlating IDS data with packet inspection
- Reinforced the importance of context and baseline knowledge when evaluating alerts in a SOC environment

Evidence

<img width="1013" height="708" alt="Screenshot 2025-09-10 135902" src="https://github.com/user-attachments/assets/b9b31a78-f25f-4c28-bed2-00d93c12caac" />

- Wireshark Screenshot: Demonstrates normal network traffic patterns and protocol distribution used to establish baseline behavior.

<img width="992" height="720" alt="SNORBY" src="https://github.com/user-attachments/assets/4f3edb62-3d8a-402d-afad-7c0787fd8dbd" />

- Snorby Screenshot: Highlights IDS alerts reviewed during analysis, including signatures and source/destination details used to evaluate risk

Alert Example

- Signature: Suspicious DHCPv6 Repeat Request Activity
- Trigger: Repeated DHCPv6 solicit messages sent to multicast address ff02::1:2
- Analysis: Packet capture in Wireshark shows multiple DHCPv6 solicit and advertise messages between a local host and the multicast DHCP server. While DHCP traffic is expected, the frequency of requests is higher than typical baseline behavior
- Outcome: Determined to be a false positive due to normal lab activity, not malicious traffic

Skills Demonstrated

- Network traffic analysis and packet inspection
- IDS alert triage and correlation
- Identifying false positives versus potential security incidents
- Understanding baseline network behavior and deviations
- Applying analyst judgment within a SOC-style workflow



