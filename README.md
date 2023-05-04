# Threat-Intel-Report
# Threat Intelligence Report: TA505 Cybercrime Group 

## Financial Industry Overview. 

This report delivers an insightful analysis of emerging cyber threats targeting the finance industry, employing the Diamond Model of Intrusion Analysis to examine the tactics of a threat actor which typically operates within the sector. The Mitre ATT&CK framework is used to assess the actors' capabilities, tactics, and common software, generating a heatmap to prioritize techniques and shed light on the constantly evolving cyber threat landscape. Each layer is individually assessed, and the results are combined to generate a heatmap of the prioritized techniques employed by the threat actor in conjunction with the most frequently used software in the industry (See Appendix for Heatmap).  

### Adversary: 

TA505 (Hive0065), a financially driven cybercrime group active since 2014, has played various roles, including ransomware-as-a-service operator, initial access broker, and large botnet operator for financial fraud and phishing attacks. This prolific group, considered one of the largest global phishing and mail spam distributors, has compromised over 3,000 US-based and 8,000 global organizations. TA505 continually adapts its TTPs to stay ahead of cybersecurity developments. Initially focused on info stealing campaigns and targeting the financial sector using Dridex botnets, since 2018, TA505 has shifted to ransomware attacks on universities, hospitals, and manufacturing companies, while also selectively deploying cryptocurrency mining malware. 

### Capabilities:  

TA505's main tools include Locky ransomware and SDBOT RAT as their primary tool, Cl0p ransomware, the FlawedAmmyy RAT (based on leaked source code from the legitimate Ammyy Admin tool), and banking trojans such as Dridex. 


### Infrastructure 

- TA505 uses various infrastructure components to support their activities, such as command and control (C2) servers, email servers, and malware distribution networks. 

- The group often leverages compromised email accounts and domains to send out large volumes of phishing emails, increasing the likelihood of success. 

- They employ domain generation algorithms (DGAs) and fast flux techniques to maintain resilient C2 infrastructure and evade takedown attempts. 

Below our IOC’s for their primary tools: 

#### Indicators of Compromise (IoCs) - SDBOT RAT 

C&C IP Addresses 

- 91[.]214[.]124[.]25 

- 91[.]214[.]124[.]20 

- 185[.]176[.]221[.]45 

C&C Domains 

- drm-server-booking[.]com 

- microsoft-live-us[.]com 

- dl1.sync-share[.]com 

URL Redirections 

1)https://eur01.safelinks.protection.outlook[.]com/url=https://clck.ru/JnFFT&data=02|01||bed42450519b40df4d8808d762bd4ff1|d847080b33824b27886012fe4d8edb27|1|0|637086437565223782&sdata=0VDHXIfGUjxrbDC0fnF/VcgoQIGSAD/PBCYcwFodSH4=&reserved=0 

2)https://clck[.]ru/JnFFT 

3)https://sba.yandex[.]net/redirect?url=https%3A%2F%2Fdl1.sync-share.com%3FOr2at&client=clck&sign=2a3f3d25a38344769c6cfb6705a0f918′ 

Final Redirection Hosting Malicious Document 

- https://dl1.sync-share[.]com?Or2at 


#### Indicators of Compromise (IoCs) - Locky Ransomware 

 

### Victim 

- TA505 conducts targeted attacks across continents, including North America, Asia, Africa, and South America, primarily targeting large financial institutions for valuable data. As of 2019, email attacks remain the most effective malware attack vector. The group's initial phishing attack on a specific financial institution involved targeting a few accounts simultaneously, suggesting prior reconnaissance to identify the best targets. 

- The group's victims span multiple geographical locations, indicating a global focus. 

### Impact Assessment 

- The activities of TA505 have resulted in substantial financial losses, reputational damage, and operational disruptions for the targeted organizations. Their continuous evolution and adaptability make them a persistent and formidable threat to various sectors worldwide. Organizations can expect to see this group continue to target a wide range of industries using social engineering to deliver open-source and custom malware while constantly adjusting TTPs and C&C infrastructure to evade detection. 

### Recommendations and Mitigation Strategies: 

 

 

 

 

 

### Footnotes/References: 

This report is based on publicly available information regarding the TA505 cybercrime group. 


 
