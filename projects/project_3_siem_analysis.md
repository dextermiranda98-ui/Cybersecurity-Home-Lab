Project 3: Centralized Log Analysis with Wazuh
💡 Objective
The objective of this project was to deploy and configure Wazuh, an open-source security platform, to centralize security event logs and perform host intrusion detection (HIDS). I focused on demonstrating my ability to install agents, monitor host integrity, analyze security events, and create custom alerting rules.

🛠️ Tools & Environment
Virtualization: VirtualBox

Logical Topology: An isolated network with a Windows 10 client and a Windows Server 2016 machine sending logs to a dedicated Ubuntu Server running the Wazuh Manager.

Operating Systems: Windows Server 2022, Windows 11, Ubuntu Server

Key Tools:

Wazuh Manager: The core server for collecting, analyzing, and storing data from agents.

Wazuh Agents: Installed on the Windows machines to forward security events and perform HIDS.

Wazuh API & Dashboard: The web-based interface for managing agents, viewing alerts, and creating visualizations.

Nmap: Used to generate log data for analysis.

⚙️ Step-by-Step Process
1. Wazuh Manager Deployment
I began by deploying the Wazuh Manager on a dedicated Ubuntu virtual machine. I followed the official Wazuh installation guide, which provided a streamlined process for setting up the server, its API, and the web dashboard. I ensured all components were correctly configured and accessible.

2. Agent Deployment & Enrollment
Next, I installed the Wazuh Agent on both the Windows 10 client and the Windows Server 2016 machine. From the Wazuh Dashboard, I enrolled each agent, which established a secure communication channel between the agent and the manager. This step was crucial for enabling log forwarding and HIDS capabilities.

3. Host Intrusion Detection (HIDS)
With the agents active, I demonstrated Wazuh's HIDS capabilities. I intentionally modified a critical system file on the Windows Server to simulate a common attack vector. Wazuh immediately detected the file integrity change and logged an alert. This validated the system's ability to monitor for suspicious activity at the host level.

4. Log Analysis & Dashboarding
Wazuh automatically collected logs from the Windows Event Logs and forwarded them to the manager. I used the Wazuh Dashboard to explore the collected data, creating a custom visualization to show failed logon attempts from different IP addresses. This process demonstrated my ability to navigate and use a SIEM for security monitoring.

5. Rule Creation & Alerting
To prove a deeper understanding of the system, I created a custom rule to alert on a specific event. I developed a rule that would trigger an alert for more than 3 failed logon attempts from the same source IP within a short time frame. I then simulated a brute-force attack from my Kali Linux machine, which successfully triggered the custom alert, proving my ability to proactively configure the SIEM for threat detection.

🧠 Challenges & Lessons Learned
Agent Enrollment: A key challenge was ensuring a stable connection between the Wazuh Manager and the agents. Firewall rules on the host and guest VMs had to be carefully configured to allow communication, which reinforced the importance of network segmentation and access control lists.

Integrated vs. Standalone: This project provided a valuable contrast to my earlier project with Suricata. I learned that while Suricata is a powerful IDS/IPS, Wazuh offers a more comprehensive, integrated solution that includes HIDS and centralized log management, providing a broader view of security events across the network.

Conclusion

This project provided me with a fundamental understanding of integrated security platforms. By deploying and using Wazuh, I gained practical skills in log management, HIDS, and real-time security alerting. I am now capable of setting up a monitoring pipeline and using a SIEM to identify and respond to security incidents. This experience is a crucial step toward a career in security operations and incident response.
