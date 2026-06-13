# SOC-L1-Alert-Triage-Lab
This repository documents my hands‑on experience performing alert triage and investigation in a simulated SOC environment using TryHackMe.
alert-triage-handson/
├── README.md
├── screenshots/
│   ├── alert_dashboard.png
│   ├── alert_details.png
│   ├── edit_alert.png
│   ├── triage_summary.png
│   └── closing_comments.png
└── notes/
    └── triage_steps.md

The exercise involved analyzing multiple alerts, determining their severity, assigning ownership, investigating indicators, and closing them with appropriate verdicts.

<img width="1235" height="534" alt="soc-dashboard" src="https://github.com/user-attachments/assets/6e963ff0-4bb0-43cd-a7b0-cde8f266d847" />
-----

| Alert Name | Severity | Verdict | Description |
| --- | --- | --- | --- |
| **[Double‑Extension File Creation](ca://s?q=Double_extension_file_creation_alert)** | High | Pending | Detected a suspicious file ``cats2025.mp4.exe`` — typical phishing payload disguised as a media file. |
| **[Potential Data Exfiltration](ca://s?q=Potential_data_exfiltration_alert)** | Critical | Pending | Large outbound data transfer (5.8 GB) to ``*.zoom.us`` flagged for review. |
| **[Download from GitHub Repository](ca://s?q=Download_from_GitHub_repository_alert)** | Low | Pending | Download from GitHub monitored for potential malicious script exposure. |
| **[Unusual VPN Login Location](ca://s?q=Unusual_VPN_login_location_alert)** | Medium | False Positive | User confirmed legitimate login from Japan while on vacation. |
| **[Bruteforce Attack from External](ca://s?q=Bruteforce_attack_alert)** | Medium | True Positive | Multiple failed login attempts detected from external IPs; confirmed malicious. |

**Triage Process**

**Alert Ownership:** 
   
   -> Assigned myself to pending alerts.
   
   -> Changed status from Awaiting Action → In Progress.
   
<img width="457" height="354" alt="ownership" src="https://github.com/user-attachments/assets/767715c4-bbec-4e4f-b247-319b174cad43" />


**Initial Analysis:**

   -> Reviewed alert metadata: source IP, host, user, network, and timestamp.

   -> Checked severity and rule description to prioritize investigation.

<img width="750" height="334" alt="Critical_severity_alert" src="https://github.com/user-attachments/assets/aa73f7a7-29f2-4c67-b76b-a30853c570da" />

   
 <img width="750" height="334" alt="High_severity_alert" src="https://github.com/user-attachments/assets/6b4ed0e8-d3cb-4499-a192-5bdc15bb8754" />

<img width="750" height="334" alt="Medium_severity_alert" src="https://github.com/user-attachments/assets/bc9a162f-dce4-4e20-bd5a-f1b307d79316" />


**Investigation:**
   
   -> Correlated logs and contextual data (VPN, file hashes, URLs).
   
   -> Verified user activity and network behavior.
   
   -> Used threat‑intel lookups for suspicious domains and file hashes.

   <img width="750" height="334" alt="Low_severity_alert" src="https://github.com/user-attachments/assets/a93c9440-4f90-4a9f-a80e-b168ac56d814" />


**Verdict Assignment**
   
   -> Classified alerts as True Positive, False Positive, or Benign.
   
   -> Documented reasoning in analyst comments.

   <img width="656" height="455" alt="Verdict" src="https://github.com/user-attachments/assets/a4310a85-3187-42a0-86fa-e4c48b102de3" />


**Closure**
   
   -> Updated status to Closed.
   -> Added final comments summarizing findings and remediation steps.
   Example closing comments
   1. Alert: Unusual VPN Login Location  
      Verdict: False Positive  
      Comment: User confirmed legitimate access from Japan while on vacation. No compromise detected.
   2. Alert: Bruteforce Attack from External  
      Verdict: True Positive  
      Comment: Multiple failed login attempts from external IPs. Account locked and password reset.

## Skills Demonstrated

- Security Alert Triage
- SIEM Investigation
- Incident Classification
- Threat Intelligence Validation
- Log Analysis
- Security Operations Center (SOC)
- False Positive Analysis
- Incident Documentation

**MITRE ATT&CK Mapping**
| Alert                 | ATT&CK Technique |
| --------------------- | ---------------- |
| Brute Force           | T1110            |
| Data Exfiltration     | T1041            |
| Double Extension File | T1204            |
| VPN Login Anomaly     | T1078            |


## Tools & Platforms

- TryHackMe SOC Simulator
- SIEM Dashboard
- Threat Intelligence Sources
- GitHub

## Key Takeaways

- Learned SOC alert prioritization
- Distinguished true positives from false positives
- Practiced incident documentation
- Improved investigation workflow
- Gained experience with alert ownership and closure

