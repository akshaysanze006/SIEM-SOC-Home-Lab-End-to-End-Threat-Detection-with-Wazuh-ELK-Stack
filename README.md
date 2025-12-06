# 🛡️ SIEM/SOC Home Lab: End-to-End Threat Detection with Wazuh & ELK Stack

## 1. Project Overview
This project establishes a fully functional Security Operations Center (SOC) environment using the open-source **Wazuh** platform (SIEM/XDR/HIDS) integrated with the **OpenSearch** (ELK-equivalent) stack. The goal is to demonstrate practical SOC analyst skills across log ingestion, threat detection, and incident response.

## 2. Technical Stack
* **SIEM/HIDS:** Wazuh Manager (for rule processing, correlation, and alerting)
* **Indexer/Data Store:** Wazuh Indexer (OpenSearch)
* **Visualization:** Wazuh Dashboard (OpenSearch Dashboards)
* **Endpoints:** 1x Windows 10 VM, 1x Linux (Ubuntu) VM
* **Virtualization:** VirtualBox/VMware

## 3. Core Use Cases Implemented
| MITRE ATT&CK Tactic | Technique | Wazuh Feature Used |
| :--- | :--- | :--- |
| **T1110** (Credential Access) | Brute Force (SSH/RDP) | Tuned Correlation Rules (`<frequency>/<timeframe>`) |
| **T1078** (Valid Accounts) | Failed Login Triage | Windows Event Log (4625) & Linux Auth Log Analysis |
| **T1562** (Defense Evasion) | File Tampering/Persistence | File Integrity Monitoring (FIM) on critical OS files |

## 4. Implementation Steps (Quick Reference)
1.  **Wazuh Server:** Deploy the All-in-One Wazuh OVA or use the install script on a clean Ubuntu VM.
2.  **Agent Deployment:** Enroll Windows and Linux endpoints using the deployment wizard in the Wazuh UI.
3.  **Detection Configuration:**
    * Validate detection of **Rule ID 5710** by running a **Hydra** attack against the Linux client.
    * Configure **FIM** to monitor changes in `/etc/shadow` on the Linux client.
4.  **Triage & Reporting:** Create a custom dashboard filter in the Wazuh Dashboard to view high-severity alerts (`rule.level >= 10`). Generate a sample PDF report detailing the brute-force incident investigation.

## 5. Demonstrated Skills
* **SOC L1/L2 Alert Triage & Incident Response**
* **Log Management and Normalization** (Wazuh Decoders/Rules)
* **Host-based Intrusion Detection (HIDS)**
* **File Integrity Monitoring (FIM)**
* **MITRE ATT&CK Framework** mapping
* **Linux/Windows Security and Auditing**
