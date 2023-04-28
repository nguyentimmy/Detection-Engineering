# Detection Engineering Program: 

Detection engineering is the process of identifying and mitigating security threats by designing, implementing, and continually improving the SIEM and EDR solutions capabilities. 

You can use any security framework to identify security gaps, in this case I will use the MITRE ATT@CK framework to perform deeper analysis. But first thing, let's break things to smaller pieces, we must identify: 
- What do I need to detect?
- What critical assets are in our environment to protect? 
- What threat actors, techniques, tools, can be relevant to us?
- What are the current attack trends and known exploited vulnerabilities? 

In this project, I will use Microsoft Sentinel and M365 Defender as my security solutions to implement Detection Engineering.

## [+] Scope
1. This project aims to enhance the organization's detection and response capabilities through a comprehensive approach that includes MITRE ATT&CK framework and Threat Intelligence.

2. Two main components involve using MITRE ATT&CK and Threat Intelligence 
   > I will perform attack simulations or commands directly from the Atomic Red Team, which is based on the MITRE ATT&CK TTP’s and attack trends, to test capabilities of our EDR/SIEM/SOAR.
 
   > I will integrate Threat Intelligence with detection expertise to keep up with the current attack trends, recent malware, and actively exploited vulnerability.

3. The goal of detection engineering is to design, develop, and implement effective security solutions that can detect and respond to potential threats in a timely and efficient manner. 


## [+] Benefits
1. ***Proactive Security:*** Focuses on identifying and closing gaps in an organization's security posture. 
 
   > By creating and testing detection mechanisms, security teams can better identify and respond to security incidents before they result in a major breach.

2. ***Evaluating Enterprise Endpoint and SIEM Detection:*** Ensure they are detecting and alerting on relevant security events. 
   > This includes setting up alert policies that trigger notifications when certain events occur or attack goes undetected.

3. ***Effective Alert Policies:*** Helps to create more effective alert policies by identifying the most critical events that require immediate attention. 
   > This helps to reduce alert fatigue and improve the efficiency of security teams in responding to security incidents.
 
4. ***Improve Skillsets:*** Helps the Detection Enginner or security team understand the flow of an attack. 
   > Improves the overall skillsets by creating queries, alert policies, and overall response.

5. ***Concised and Refined Incident Response:*** Helps the security team identify threats efficently and identify them before damage can be done. 
   > Help the Security Team be more proactive.

## [+] Procedures
### I. Automating MITRE ATT&CK Using Atomic Red Team

> Please read: :link: [Integrating MITRE ATT&CK](https://github.com/nguyentimmy/Detection-Engineering/tree/main/1%20-%20Automating%20MITRE%20ATT%26CK%20Using%20Atomic%20Red%20Team) :exclamation:

### II. Detect Current Attack Trends Using Threat Intelligence 

> Please read: :link: [Intergrating Threat Intelligence](https://github.com/nguyentimmy/Detection-Engineering/tree/main/2%20-%20Detect%20Current%20Attack%20Trends%20Using%20Threat%20Intelligence) :exclamation:

### III. Continuous Improvement Development 
> In Progress - TBA  :exclamation:
