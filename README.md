# SOC Automation: TheHive, Wazuh & Shuffle Integration

**Objective:**  
Build a fully automated SOC pipeline by integrating Wazuh (threat detection), TheHive (case management), and Shuffle (SOAR). Streamline detection → alerting → response workflows to accelerate incident handling and reduce manual effort.

## 🏗️ Step 1: Architecture Design  
![Architecture Diagram](images/soc-architecture.png)  
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
- Deployed Wazuh agents to Windows and Ubuntu hosts  
- Verified agent connectivity via Wazuh Dashboard  

## 🛠️ Step 4: Detection Rule Development  
1. **Telemetry Generation:**  
   - Configured `ossec.conf` to ingest Windows event logs  
   - Executed Mimikatz on Windows to generate malicious activity  
2. **Rule Creation:**  
   - Custom Wazuh rules to detect Mimikatz (Event ID: 100002)  
3. **Threat Hunting:**  
   - Confirmed detection in Wazuh Dashboard → Alerts  


## 🔄 Step 5: SOAR Workflow in Shuffle  
1. **Shuffle Setup:**  
   - Created organization and users  
   - Built a workflow to ingest Wazuh alerts  
2. **TheHive Integration:**  
   - Alerts from Shuffle automatically open cases in TheHive  
3. **Notification:**  
   - Configured email notifications via Disposable Email SquareX  


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

