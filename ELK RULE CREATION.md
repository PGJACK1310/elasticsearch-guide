# RULE CREATE IN KIBANA

### Step 1 : match the keyword and identify the relevant SIEM logs.
<img width="1365" height="623" alt="image" src="https://github.com/user-attachments/assets/7b3bec72-20d2-4288-9e96-f25c219c25e5" />

### Step 2 : Navigate to Elastic Security and select the Custom Query rule type to define the SIEM detection logic.
<img width="958" height="567" alt="image" src="https://github.com/user-attachments/assets/77ea387f-a6a9-4412-99e9-28e1018addaf" />

### Step 3 : Configure the custom query by selecting the appropriate data view and defining the keyword-based search condition to detect relevant SIEM events and failed login activities.
<img width="739" height="550" alt="image" src="https://github.com/user-attachments/assets/3bbaf75e-b2e1-4589-a1f3-6649d5160692" />

### Step 4 : Configure the SIEM Rule Details and Alert Classification
- Example : Configure the rule by entering a descriptive rule name, adding a detailed explanation of the Huawei TELNET failed login detection logic, setting the alert severity to High, assigning a Risk Score of 75 to prioritize potential brute-force or unauthorized access attempts, and adding relevant tags such as Huawei, Telnet, Failed-Login, Brute-Force, LOGINFAILED, and Initial-Access to improve alert categorization, threat hunting, and incident investigation within the Elastic Security SIEM platform.
<img width="721" height="513" alt="image" src="https://github.com/user-attachments/assets/42798040-f011-4dea-9f3f-013e0e146cbd" />

### Step 5 : Configure MITRE ATT&CK Mapping, Investigation Fields, and Incident Response Guidance
- Map the detection rule to the appropriate MITRE ATT&CK framework by selecting the tactic Credential Access (TA0006), the technique Brute Force (T1110), and the sub-technique Password Guessing (T1110.001) to accurately classify the attack behavior. Configure custom highlighted fields such as host.ip, src_ip, module, event_name, event_message, and user to provide analysts with critical event information during alert investigation. Additionally, create a detailed investigation guide outlining validation and response procedures, including verifying source IP legitimacy, checking repeated login failures, reviewing TELNET exposure, analyzing authentication logs, blocking malicious IP addresses, recommending SSH instead of TELNET, and escalating incidents if login attempts become successful after multiple failures.
<img width="612" height="506" alt="image" src="https://github.com/user-attachments/assets/f77de9df-53ea-4bb7-a4a3-df9bf955f30c" />

### Step 6 : Configure Rule Scheduling
- Set the rule to run every 1 hour with an additional 30-minute look-back time to ensure continuous monitoring and prevent missed security alerts caused by delayed log ingestion.
<img width="727" height="354" alt="image" src="https://github.com/user-attachments/assets/6980e6ce-26d5-4923-bd1f-c0bb4b88feef" />

### Step 7 : Configure Alert Actions and Enable the Rule
- Select the required alert integration or response action platform such as Email, Slack, Microsoft Teams, Jira, Webhook, or Elastic Defend for automated incident notification and response handling. After reviewing the configuration, click Create & enable rule to activate the SIEM detection rule and begin monitoring Huawei TELNET failed login events in real time.
<img width="698" height="503" alt="image" src="https://github.com/user-attachments/assets/b7eee8f7-52be-434c-8e9c-81a34d643111" />

