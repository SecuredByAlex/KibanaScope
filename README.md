# KibanaScope

## Objective

To investigate a potential Command and Control (C2) communication alert flagged by the IDS for a user in the HR department. The goal is to analyze week-long HTTP connection logs ingested into the connection_logs index in Kibana, identify the malicious access pattern THM:{ ________ }, and trace the activity back to its source to assess the scope of compromise.


## Skills Learned

- Kibana Dashboarding: Built visualizations to analyze HTTP traffic patterns.
- Log Analysis: Extracted insights from raw HTTP connection logs using filters, queries, and aggregations.
- Threat Detection: Identified suspicious indicators of C2 communication using IDS alerts and log patterns.
- Elasticsearch Querying (KQL): Used Kibana Query Language to hunt for specific activity (e.g., file access, source IP, URLs).
- SOC Investigation Workflow: Applied practical blue team methodology in log-based threat hunting.
  
## Tools Used

- TryHackMe paltform for accessing the Lab
- Kibana: Open-source SIEM tool
- Kali Linux Terminal: Command-line interface for executing the Tool.
- Virtual Machine (VM): Simulated environment for executing tasks

  
## Scenario

During normal SOC monitoring, Analyst John observed an alert on an IDS solution indicating a potential C2 communication from a user Browne from the HR department. A suspicious file was accessed containing a malicious pattern THM:{ ________ }. A week-long HTTP connection logs have been pulled to investigate. Due to limited resources, only the connection logs could be pulled out and are ingested into the connection_logs index in Kibana.

Our task in this room will be to examine the network connection logs of this user, find the link and the content of the file, and answer the questions.

## Steps Taken

Q1. How many events were returned for the month of March 2022?<br>
Ans : 1482<br>
O/P: <img src="https://github.com/user-attachments/assets/ea98f5ac-388c-45b5-a85a-bd03eb4f7696" /> <br><br>

Q2. What is the IP associated with the suspected user in the logs?<br>
Ans : 192.166.65.54<br>
O/P: <img src="https://github.com/user-attachments/assets/01683cc1-8def-4f05-b648-1cd7cb154000" /> <br><br>

Q3. The user’s machine used a legit windows binary to download a file from the C2 server. What is the name of the binary? <br>
Ans : bitsadmin <br>
O/P: <img src="https://github.com/user-attachments/assets/81968590-e6e1-4abb-ba16-d4d304a42bd1" /> <br><br>

Q4. The infected machine connected with a famous filesharing site in this period, which also acts as a C2 server used by the malware authors to communicate. What is the name of the filesharing site? <br>
Ans : pastebin.com <br>
O/P: <img src="https://github.com/user-attachments/assets/bbffa67e-6538-4f0b-951e-3469975c9594" /> <br><br>

Q5. What is the full URL of the C2 to which the infected host is connected? <br>
Ans : pastebin.com/yTg0Ah6a <br>
O/P: <img src="https://github.com/user-attachments/assets/ddc9adc6-8d55-499c-9a18-29ac849129d0" /> <br><br>

Q6. A file was accessed on the filesharing site. What is the name of the file accessed? <br>
Ans : secret.txt <br>
O/P: <img src="https://github.com/user-attachments/assets/4374f54c-c2bc-45dd-bb19-2e684157f114" /> <br><br>

Q7. The file contains a secret code with the format THM{_____}. <br>
Ans : THM{SECRET__CODE} <br>
O/P: <img src="https://github.com/user-attachments/assets/55d97563-7228-45ff-a79d-ee8519f214e9" /> <br><br>

## Conclusion 

Using Kibana to analyze week-long connection logs proved effective in narrowing down suspicious behavior. The investigation revealed access to a file containing a malicious pattern matching THM{SECRET__CODE}, confirming the IDS alert. This project highlights the importance of proactive log monitoring and the power of visualization tools like Kibana in a SOC environment, especially when resources are limited.

