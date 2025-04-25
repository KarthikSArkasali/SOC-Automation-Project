# SOC Automation: TheHive, Wazuh & Shuffle Integration

## Objective:
This project aims to design and implement a fully automated security monitoring and incident response system within a Security Operations Center (SOC). By integrating TheHive, Wazuh, and Shuffle (SOAR), the objective is to streamline the incident management lifecycle, from detection to response. The system will automate workflows for efficient threat detection, alerting, and incident response, reducing manual workload and enhancing the SOC's capability to swiftly address cyber threats. Through this integration, the system accelerates incident handling, improving the SOC’s overall efficiency, resilience, and response times against emerging threats.

## 🏗️ Step 1: Architecture Design  

![Block Diagram](https://github.com/user-attachments/assets/d437096d-4eb2-4fae-8587-79d986d03bf9)

High‑level block diagram showing data flow from endpoints → Wazuh → TheHive → Shuffle.

## 💻 Step 2: Environment Deployment  
| VM             | Role                         | OS           |
|----------------|------------------------------|--------------|
| Wazuh Server   | Log collection & detection   | Ubuntu 24.04 |
| TheHive Server | Case management              | Ubuntu 24.04 |
| Shuffle Server | SOAR orchestration           | Ubuntu 24.04 |
| Windows Agent  | Event logging (Sysmon)       | Windows 10   |

1. Deployed three Ubuntu 24.04 VMs and one Windows 10 VM  
2. Installed Sysmon on Windows for detailed event logs  

## 🔍 Step 3: Wazuh Configuration  
- Installed Wazuh Manager & Dashboard on Ubuntu

![Opned using web browser](https://github.com/user-attachments/assets/bb541b01-8485-4984-bce8-cfc07c5679de)
  
- Deployed Wazuh agents to Windows and Ubuntu hosts

![New Endpoint Win agent ](https://github.com/user-attachments/assets/400bbdaf-4060-4853-896a-8fce8c65c6e1)

- Verified agent connectivity via Windows Services

![Services](https://github.com/user-attachments/assets/dd1f58f7-e2a2-46ea-a9d9-2d43eaaa471f)

## 🛠️ Step 4: Detection Rule Development  
1. **Telemetry Generation:**  
   - Configured `ossec.conf` to ingest Windows event logs
  
![Log analysis](https://github.com/user-attachments/assets/ae135d10-127a-4d66-a569-3f68af2eaa43)

   - Executed Mimikatz on Windows to generate malicious activity

2. **Rule Creation:**  
   - Custom Wazuh rules to detect Mimikatz (Event ID: 100002)
     
![Rule Creation](https://github.com/user-attachments/assets/8b345c09-4c6e-40f6-a62d-a5ca6efc676f)

3. **Threat Hunting:**  
   - Confirmed detection in Wazuh Dashboard → Alerts  

![Threat hunting](https://github.com/user-attachments/assets/4e3838b9-e9bf-4bef-9de6-eb7e401c6c78)

## 🔄 Step 5: SOAR Workflow in Shuffle  
1. **Shuffle Setup:**  
   - Created organization and users  
   - Built a workflow to ingest Wazuh alerts
  
![Shuffle workflow](https://github.com/user-attachments/assets/c8e1d932-2432-476d-8b16-ae8135769013)

2. **TheHive Integration:**  
   - Alerts from Shuffle automatically open cases in TheHive
  
![Alerts](https://github.com/user-attachments/assets/d0d3abac-7ae6-4f67-bd75-ec3febc8b2d9)

3. **Notification:**  
   - Configured email notifications via Disposable Email SquareX  

![New Email](https://github.com/user-attachments/assets/58ace99c-a5b0-4f07-91b1-6703d41e741c)

## ⚔️ Automated Response Playbook  
Upon Mimikatz detection email:  
1. **Containment:** Firewall‑drop or IP block via Shuffle  
2. **Automated Rules:** Update `ossec.conf` for future auto‑containment  
3. **Team Notification:** Slack/email summary of actions  
4. **Forensic Playbook:** Trigger TheHive playbook for investigation & remediation  

## 🔑 Key Benefits  
- **End‑to‑end automation** cuts mean time to respond (MTTR)  
- **Scalable architecture** with open‑source tooling  
- **Human‑in‑the‑loop** decision points via Shuffle prompts  
- **Comprehensive visibility** from detection through case resolution  

