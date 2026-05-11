# RULE CREATE IN KIBANA

### Step 1 : match the keyword and identify the relevant SIEM logs.
<img width="1365" height="623" alt="image" src="https://github.com/user-attachments/assets/7b3bec72-20d2-4288-9e96-f25c219c25e5" />

### Step 2 : Navigate to Elastic Security and select the Custom Query rule type to define the SIEM detection logic.
<img width="958" height="567" alt="image" src="https://github.com/user-attachments/assets/77ea387f-a6a9-4412-99e9-28e1018addaf" />

### Step 3 : Configure the custom query by selecting the appropriate data view and defining the keyword-based search condition to detect relevant SIEM events and failed login activities.
<img width="739" height="550" alt="image" src="https://github.com/user-attachments/assets/3bbaf75e-b2e1-4589-a1f3-6649d5160692" />

### Step 4 : Configure the SIEM Rule Details and Alert Classification
- Configure the rule by entering a descriptive rule name, adding a detailed explanation of the Huawei TELNET failed login detection logic, setting the alert severity to High, assigning a Risk Score of 75 to prioritize potential brute-force or unauthorized access attempts, and adding relevant tags such as Huawei, Telnet, Failed-Login, Brute-Force, LOGINFAILED, and Initial-Access to improve alert categorization, threat hunting, and incident investigation within the Elastic Security SIEM platform.
<img width="721" height="513" alt="image" src="https://github.com/user-attachments/assets/42798040-f011-4dea-9f3f-013e0e146cbd" />
