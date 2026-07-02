🛡️ Purple Team Lab – Scenario #1: RDP Brute Force Detection & Log Analysis
📌 Project Overview
This project demonstrates a purple team simulation of a Remote Desktop Protocol (RDP) brute-force attack against a Windows Server in a controlled home lab environment. The objective was to emulate an attacker attempting unauthorized access while validating that Wazuh SIEM successfully collected, correlated, and alerted on failed authentication events.
This exercise highlights the detection and investigation workflow performed by a Security Operations Center (SOC) analyst, including Windows Event Log analysis, authentication monitoring, and incident validation.

🎯 Objectives
🔑 Simulate a failed RDP authentication attempt from Kali Linux
🖥️ Generate Windows Security Event ID 4625 (Failed Logon)
📊 Validate log ingestion into Wazuh SIEM
🚨 Verify Wazuh authentication alerts and rule correlation
🔍 Investigate failed login events using Windows Event Viewer
📝 Document findings and map activity to the MITRE ATT&CK framework

🖥️ Lab Environment
Component
Technology
Attacker Machine
Kali Linux
Target Machine
Windows Server
SIEM
Wazuh
Log Collection
Wazuh Agent
Remote Access
RDP
Attack Framework
MITRE ATT&CK


⚔️ Attack Scenario
🔑 Phase 1 – Initial Access Attempt
Objective
Simulate an attacker attempting to gain unauthorized access to a Windows Server through Remote Desktop Protocol (RDP) using invalid credentials.
Command
<img width="663" height="108" alt="Screenshot 2026-06-28 114123" src="https://github.com/user-attachments/assets/abfdd543-6c95-4b40-b1d0-0e0547dfb7fa" />

Result
Connection attempt initiated from Kali Linux
Authentication failed due to invalid credentials
Windows generated a Failed Logon event
📷 Screenshot
Fake Admin Log

<img width="647" height="862" alt="Screenshot 2026-06-28 091310" src="https://github.com/user-attachments/assets/4bca76df-1a63-435d-9793-80230113953b" />





🖥️ Windows Investigation
Event Viewer
Navigate to:
Windows Logs
└── Security
Search for:
Event ID 4625 – Failed Logon
Information observed:
Username attempted
Source IP Address
Logon Type
Failure Reason
Authentication Package
📷 Screenshot

<img width="1026" height="765" alt="Screenshot 2026-06-28 095450" src="https://github.com/user-attachments/assets/d2ec8ce7-6079-4635-9a48-f731f6d50958" />








<img width="1007" height="726" alt="Screenshot 2026-06-28 095827" src="https://github.com/user-attachments/assets/bfb9f072-3f28-407a-9e96-fd71703776de" />






📊 Wazuh Detection
Detection Summary
Wazuh successfully detected and correlated the failed authentication attempt.
Alerts included:
🚨 Failed Authentication
🔑 Password Guessing Activity
🖥️ Source IP Address
👤 Target Username
📄 Windows Security Event ID 4625
📷 Screenshot


<img width="1906" height="805" alt="Screenshot 2026-06-28 091717" src="https://github.com/user-attachments/assets/0a2e1287-6339-4933-b64b-61e771173910" />





<img width="905" height="626" alt="Screenshot 2026-07-02 151515" src="https://github.com/user-attachments/assets/fae9d369-86f5-4771-82dc-8cb938eae592" />

🔍 Investigation Summary
Step
Observation
Attack Source
Kali Linux
Target
Windows Server
Attack Method
Remote Desktop Protocol (RDP)
Username
FakeAdmin
Result
Authentication Failed
Windows Event
Event ID 4625
Detection Tool
Wazuh SIEM


🎯 MITRE ATT&CK Mapping
Technique
ATT&CK ID
Valid Accounts (Attempt)
T1078
Brute Force
T1110
Remote Services (RDP)
T1021.001


🛡️ Wazuh Detection Summary
✅ Failed Authentication Detection
✅ Windows Security Event Collection
✅ Authentication Log Correlation
✅ Source IP Visibility
✅ Failed Logon Investigation

📚 Skills Demonstrated
🛡️ Security Monitoring
📊 SIEM Analysis
🔎 Threat Hunting
🪟 Windows Event Log Analysis
🐉 Kali Linux
🔐 Remote Desktop Protocol (RDP)
🚨 Authentication Monitoring
🎯 MITRE ATT&CK Mapping
📑 Incident Investigation

📸 Screenshots
📷 Failed RDP Login from Kali Linux
📷 Windows Event Viewer (Event ID 4625)
📷 Wazuh Authentication Alert
📷 Wazuh Dashboard Overview

💡 Lessons Learned
This project demonstrated how a Security Information and Event Management (SIEM) platform can detect and correlate failed authentication attempts in near real time. By generating Windows Security Event ID 4625 through a simulated RDP login attempt, I validated Wazuh's ability to ingest security logs, identify suspicious authentication activity, and support incident investigation. This exercise strengthened my understanding of Windows event logging, authentication monitoring, and SOC investigation workflows.

👩‍💻 Author
Michael Stromer
Aspiring SOC Analyst | Blue Team | Detection Engineering | Threat Hunting


