# Using a Threal Intel Feed

![](https://github.com/nguyentimmy/Detection-Engineering/blob/main/Detect%20Current%20Attack%20Trends%20Using%20Threat%20Intelligence/Photos/MDTI.png)
1. Analyze the relevance of the threat intelligence to your organization's security posture.
  > Is this APT targeting a software company, government agency, or health facilities?
2. Identify the IOCs from the threat intelligence report and you may use them to create custom detection rules. In some cases, your EDR provider should create rules to detect the IOCs. 
   > But by creating detection rules, you can increase visibility and help threat hunters identify potential threats.  Unless, there's an automation on threat intel feed connected to your SIEM or EDR via API.
3. Determine which MITRE ATT&CK techniques are being used by the APT groups and threat actors mentioned in the report. Identify the specific vulnerabilities, devices, or company assets being exploited by these techniques.
  > Learning the TTP the attackers will use can help you proactively be ahead of the game by creating a detection based on their known attack patterns

### 

### 
