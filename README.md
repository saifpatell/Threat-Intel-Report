# Threat Intelligence Report: TA505 Cybercrime Group 

## Financial Industry Overview. 

This report delivers an insightful analysis of emerging cyber threats targeting the finance industry, employing the Diamond Model of Intrusion Analysis to examine the tactics of a threat actor which typically operates within the sector. The Mitre ATT&CK framework is used to assess the actors' capabilities, tactics, and common software, generating a heatmap to prioritize techniques and shed light on the constantly evolving cyber threat landscape. Each layer is individually assessed, and the results are combined to generate a heatmap of the prioritized techniques employed by the threat actor in conjunction with the most frequently used software in the industry(See heatmap below). 

![Heatmap](https://github.com/saifpatell/Threat-Intel-Report/blob/main/ATT%26CK%20Heatmap.png)

### Adversary: 

TA505 (Hive0065), a financially driven cybercrime group active since 2014, has played various roles, including ransomware-as-a-service operator, initial access broker, and large botnet operator for financial fraud and phishing attacks. This prolific group, considered one of the largest global phishing and mail spam distributors, has compromised over 3,000 US-based and 8,000 global organizations. TA505 continually adapts its TTPs to stay ahead of cybersecurity developments. Initially focused on info stealing campaigns and targeting the financial sector using Dridex botnets, since 2018, TA505 has shifted to ransomware attacks on universities, hospitals, and manufacturing companies, while also selectively deploying cryptocurrency mining malware. 

### Capabilities:  

TA505's main tools include Locky ransomware and SDBOT RAT as their primary tool, Cl0p ransomware, the FlawedAmmyy RAT (based on leaked source code from the legitimate Ammyy Admin tool), and banking trojans such as Dridex. 

 Outer pipes  Cell padding 
No sorting
| TTPs                                                                                                                                | Use                                                                                                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Technique T1566 – Phishing 

https://attack.mitre.org/techniques/T1566/                                                             | Targeted enterprise employees in Europe with a spear phishing email impersonating One hub, a legitimate, cloud-based file-sharing application for businesses. |
| Tactic - TA011: Command and control 

Technique - T1071: Application layer Protocol 

Sub technique - T1071.001                     | TA505 has used HTTP to communicate with C2 nodes.                                                                                                             |
| Tactic: Native API: ID: T1106                                                                                                       | TA505 has deployed payloads that use Windows API calls on a compromised host                                                                                  |
| Tactic: Ingress Tool Transfer [T1105](https://attack.mitre.org/techniques/T1105)                                                    | TA505 has downloaded additional malware to execute on victim systems                                                                                          |
| Technique [T1562](https://attack.mitre.org/techniques/T1562/): Impair Defenses  

Sub-Techniques T1562.001: Disable or modify Tools | TA505 has used malware to disable Windows Defender                                                                                                            |
| Defensive evasion TA0005: Tactic: T1112: Modify Registry                                                                            | TA505 has used malware to disable Windows Defender through modification of the Registry                                                                       |
| Software Packing                                                                                                                    |                                                                                                                                                               |
| Dynamic link library injection                                                                                                      |                                                                                                                                                               |
| Code Signing                                                                                                                        |                                                                                                                                                               |
| Rundle 32                                                                                                                           |                                                                                                                                                               |
| Deobfuscate/decode files or information                                                                                             |                                                                                                                                                               |
| Command and scripting interpreter – PowerShell and windows command                                                                  |                                                                                                                                                               |

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

Filename

| File name          | SHA1                                     | Description               |
| ------------------ | ---------------------------------------- | ------------------------- |
| main_template.docx | 33094acd614825a916b77df6c5141c088fc3768b | Malicious document        |
| vspub1.dll         | bf0f7abda2228059bb00ec9658ee447fbe84d277 | CobaltStrike similarities |
| vspub2.dll         | d40510da42a478d72e649993208710668a7f6c27 | CobaltStrike similarities |
| xrjkrobuy.dll      | 14f52ae68344e1643b3066c10f7044fdd819db4e | SDBot RAT                 |
| upywloeza.dll      | 0cc7cca16afd632857e3883c06b2f55c057b563e | SDBot RAT                 |
| dtzvlbtxn.dll      | d36e983886a084887f887c6d562d3bc0664587c4 | SDBot RAT                 |
| lvgoywrnxwy.dll    | fea7d944e317c7b2ef1aba57600a8c5310368085 | SDBot RAT                 |
| qcuqqgxmy.dll      | 35423e04e58ab1f2267e19c47e1c69ea5b7041cc | SDBot RAT                 |
| pdxqzmftr.dll      | fd9620c0c295caaee3096423532bb1dbfb7064c5 | SDBot RAT                 |
| lowpro3.13.exe     | cb0b39534d99057b02b090c3650fb1de43d19a02 | Binary                    |
| wsus.exe           | caff1d315a5d87014e5fa62346f58407755d971e | Meterpreter stager        |
| FakeL.exe          | 45c43ec18d15ba7850e6ad2e2e54671636f4d926 | Password Stealer          |

#### Indicators of Compromise (IoCs) - Locky Ransomware 

 

### Victim 

- TA505 conducts targeted attacks across continents, including North America, Asia, Africa, and South America, primarily targeting large financial institutions for valuable data. As of 2019, email attacks remain the most effective malware attack vector. The group's initial phishing attack on a specific financial institution involved targeting a few accounts simultaneously, suggesting prior reconnaissance to identify the best targets. 

- The group's victims span multiple geographical locations, indicating a global focus. 

### Impact Assessment 

- The activities of TA505 have resulted in substantial financial losses, reputational damage, and operational disruptions for the targeted organizations. Their continuous evolution and adaptability make them a persistent and formidable threat to various sectors worldwide. Organizations can expect to see this group continue to target a wide range of industries using social engineering to deliver open-source and custom malware while constantly adjusting TTPs and C&C infrastructure to evade detection. 

### Recommendations and Mitigation Strategies: 

 

 

 

 

 

### Footnotes/References: 

This report is based on publicly available information regarding the TA505 cybercrime group. 


 
