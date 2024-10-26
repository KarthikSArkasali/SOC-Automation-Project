# ~ SOC Automation Project Utilizing TheHive, Wazuh, and Shuffle for Enhanced Incident Response

* This project focuses on developing an automated security monitoring and incident response system within a Security Operations Center (SOC) by integrating TheHive, Wazuh, and Shuffle (SOAR). The objective is to design, configure, and automate workflows for efficient incident detection, alerting, and response, streamlining the entire incident management lifecycle. By leveraging these integrated tools, the system enables rapid threat detection and response, reducing manual workload and enhancing the SOC’s overall efficiency and resilience against cyber threats.

# ~ Step-1: Designed a logical architecture diagram using the draw.io application.

![Block Diagram](https://github.com/user-attachments/assets/d437096d-4eb2-4fae-8587-79d986d03bf9)

# ~ Step 2: Set up virtual machines, including two Ubuntu Server 24.04 instances and one Windows 10 instance.

![Installed Virtual Machines](https://github.com/user-attachments/assets/a99af2a9-8d02-48e0-b8cb-8288edf61411)

# Installed Sysmon on the Windows 10 host for enhanced event monitoring and logging

![Sysmon](https://github.com/user-attachments/assets/a743f91f-5a35-4137-b88b-a5caf7f87b8a)

# Installed and configured a Wazuh server on an Ubuntu 24.04 host for comprehensive threat detection and monitoring

![Installing Wazuh ](https://github.com/user-attachments/assets/997d1f3d-cd05-4e65-ab81-ad4a5d33780d)

# Accessed the Wazuh dashboard GUI through a web browser by entering https://<IP-Address> of the Ubuntu host where the Wazuh server is installed

![Opned using web browser](https://github.com/user-attachments/assets/bb541b01-8485-4984-bce8-cfc07c5679de)

# ~ Step 3: Installed and configured TheHive server on Ubuntu 24.04.

![thehive](https://github.com/user-attachments/assets/5f5d3387-5fbe-4bdf-aedd-c978a6a65959)

# Added an agent in the Wazuh dashboard GUI and deployed the Windows agent by executing PowerShell commands to facilitate enhanced monitoring and management

![New Endpoint Win agent ](https://github.com/user-attachments/assets/400bbdaf-4060-4853-896a-8fce8c65c6e1)

# Added an agent in the Wazuh dashboard GUI and deployed the Ubuntu agent to facilitate enhanced monitoring and management

![Endpoint ubuntu agent](https://github.com/user-attachments/assets/d67fd1be-1ea4-4eb1-9191-1e770bde8aec)

# Verified that the Wazuh agent is running on Windows 10 by checking the Services application

![Services](https://github.com/user-attachments/assets/dd1f58f7-e2a2-46ea-a9d9-2d43eaaa471f)

# ~ Step-4: Generated telemetry data and ingested it into Wazuh for analysis.

   # Configured the ossec.conf file to ingest data into Wazuh

![Log analysis](https://github.com/user-attachments/assets/ae135d10-127a-4d66-a569-3f68af2eaa43)

# Downloaded Mimikatz on the Windows 10 host for credential extraction and security testing

![Mimikatz](https://github.com/user-attachments/assets/30742650-2f2e-4553-9002-ae0908a11e26)

# Created custom rules in Wazuh to detect Mimikatz activity

![Rule Creation](https://github.com/user-attachments/assets/8b345c09-4c6e-40f6-a62d-a5ca6efc676f)

# Mimikatz activity was detected in the event logs under Threat Hunting (Event ID: 100002)

![Threat hunting](https://github.com/user-attachments/assets/4e3838b9-e9bf-4bef-9de6-eb7e401c6c78)

# ~ Step-5: Created a Shuffle account and developed a new workflow.

![Shuffle workflow](https://github.com/user-attachments/assets/c8e1d932-2432-476d-8b16-ae8135769013)

# Created user accounts under the new organization in TheHive

![users](https://github.com/user-attachments/assets/da544eb6-c058-41c5-ab48-b8f5b9b4b6d5)

# Executed the workflow, which triggered and generated an alert in TheHive

![Alerts](https://github.com/user-attachments/assets/d0d3abac-7ae6-4f67-bd75-ec3febc8b2d9)

# A description of the alert that was generated. 

![New Cases thehive](https://github.com/user-attachments/assets/09a40196-f5f4-4916-9a9b-97229c7cdf0c)

# Executed the workflow, resulting in an alert being triggered and sent to the Disposable Email SquareX app 

![New Email](https://github.com/user-attachments/assets/58ace99c-a5b0-4f07-91b1-6703d41e741c)

# Upon receiving an email alert indicating Mimikatz usage, the SOC analyst performs the following steps:

# 1. Containment Actions
  * Initiates firewall-drop or IP blocking to isolate the compromised endpoint.
  * Executes containment either via SOAR automation or manual intervention, based on organizational protocols.
# 2. Automated Response Configuration
  * Configures automated response rules in ossec.conf to enable rapid containment actions on future detections.
# 3. SOC Notification
  * Sends notifications to the SOC team, providing details of the detection, containment actions taken, and the current status of the affected endpoints.
# 4. Incident Response Playbook Activation
  * Activates an incident response playbook to systematically investigate, remediate, and conduct forensic analysis on the compromised endpoint.

# This structured response approach strengthens network security and mitigates further risks.

