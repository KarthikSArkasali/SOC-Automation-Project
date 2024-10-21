# ~ SOC-Automation-Project

This project involves creating an automated security monitoring and incident response system within a SOC by integrating TheHive, Wazuh, and Shuffle (SOAR). It focuses on designing, configuring, and automating detection, alerting, and response workflows for efficient incident management.

# ~ Step-1: Designed a Logical Diagram using draw.io app

![Block Diagram](https://github.com/user-attachments/assets/d437096d-4eb2-4fae-8587-79d986d03bf9)

# ~ Step-2: Installed a Virtual Machines ( 2 Ubuntu Server 24.04 and 1 Win 10)

![Installed Virtual Machines](https://github.com/user-attachments/assets/a99af2a9-8d02-48e0-b8cb-8288edf61411)

# ~ Installed a Sysmon in Win 10 host

![Sysmon](https://github.com/user-attachments/assets/a743f91f-5a35-4137-b88b-a5caf7f87b8a)

# ~ Installed a Wazuh server in Ubuntu 24.04 host

![Installing Wazuh ](https://github.com/user-attachments/assets/997d1f3d-cd05-4e65-ab81-ad4a5d33780d)

# Search with https://<Ipaddress> in web Browser

![Opned using web browser](https://github.com/user-attachments/assets/bb541b01-8485-4984-bce8-cfc07c5679de)

# ~ Step-3: Installed & Configured Thehive Server on ubuntu 24.04

![thehive](https://github.com/user-attachments/assets/5f5d3387-5fbe-4bdf-aedd-c978a6a65959)

# ~ Added & Deployed Windows Agent 

![Endpoint Wazuh](https://github.com/user-attachments/assets/5382e9a0-e38d-4840-921f-14d6cfab16b1)

# ~ Verifying Wazuh Agent is running on Windows 10

![Services](https://github.com/user-attachments/assets/dd1f58f7-e2a2-46ea-a9d9-2d43eaaa471f)

# ~ Step-4: Generate Telemetry & Ingest into Wazuh

   # For ingest data into Wazuh configured Ossec.conf file

![Log analysis](https://github.com/user-attachments/assets/ae135d10-127a-4d66-a569-3f68af2eaa43)

# Downloaded Mimikatz in Windows 10 host

![Mimikatz](https://github.com/user-attachments/assets/30742650-2f2e-4553-9002-ae0908a11e26)

# Created Custom rules for Mimikatz to detected by Wazuh

![Rule Creation](https://github.com/user-attachments/assets/8b345c09-4c6e-40f6-a62d-a5ca6efc676f)

# Mimikatz Detected in Event under Threat Hunting (100002)

![Threat hunting](https://github.com/user-attachments/assets/4e3838b9-e9bf-4bef-9de6-eb7e401c6c78)

# ~ Step-5: Created Shuffle Account & Connect Shuffle SOAR

![Shuffle workflow](https://github.com/user-attachments/assets/c8e1d932-2432-476d-8b16-ae8135769013)

# Created Users under new organization in Thehive

![users](https://github.com/user-attachments/assets/da544eb6-c058-41c5-ab48-b8f5b9b4b6d5)

# Running Workflow & Alert got triggered in Thehive The Disposable Email 

![Alerts](https://github.com/user-attachments/assets/d0d3abac-7ae6-4f67-bd75-ec3febc8b2d9)

# Also in The Disposable Email 

![Email](https://github.com/user-attachments/assets/36099a0c-daec-4ed5-82a5-81070e92c14f)

# After the Alert triggered on both Thehive & Email Soc Analyst Immediately starts Incident Response  
