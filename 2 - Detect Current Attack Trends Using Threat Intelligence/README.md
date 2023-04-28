# Using a Threal Intel Feed

**Read the steps by the coresponding numbers on the screenshot for a better understanding.**

![image](https://github.com/nguyentimmy/Detection-Engineering/blob/main/2%20-%20Detect%20Current%20Attack%20Trends%20Using%20Threat%20Intelligence/Photos/MDTI.png)

1. Analyze the relevance of the threat intelligence to your organization's security posture.
  > Is this APT targeting a software company, government agency, or health facilities?
2. Identify the IOCs from the threat intelligence report and you may use them to create custom detection rules. In some cases, your EDR provider should create rules to detect the IOCs. 
  > But by creating detection rules, you can increase visibility and help threat hunters identify potential threats.  Unless, there's an automation on threat intel feed connected to your SIEM or EDR via API.
3. Determine which MITRE ATT&CK techniques are being used by the APT groups and threat actors mentioned in the report. Identify the specific vulnerabilities, devices, or company assets being exploited by these techniques.
  > Learning the TTP the attackers will use can help you proactively be ahead of the game by creating a detection based on their known attack patterns


## [+] Does it Impact your organization?
If the threat intel report is relevant to your organization, here are some steps to be more proactive to detect and mitigate any threats coming your way. If it does, follow the next two methods to harden your defense.

## [+] Detecting IOC 

In this case, I will be use Defender for Endpoint as my EDR solution to create a detection alert and threat hunting query (Which can be beneficial for the threat hunters or SOC).

### I. Using the IOC from your threat intel feed 
Use the list of IOC provided by your threat intel or open source feed. In my case I will use Microsoft Threat Intel for my IOC. 
![Image](https://github.com/nguyentimmy/Detection-Engineering/blob/main/2%20-%20Detect%20Current%20Attack%20Trends%20Using%20Threat%20Intelligence/Photos/IOC-Coinminer.png)

### II.

### III. 
..
## [+] Detection on MITRE ATT&CK Techniques 

### I. Proactive Research on the Techniques
For this quick demo, I will use one of the MITRE ATT&CK techniques used by the threat actor, in this case it will be [T1059.001](https://atomicredteam.io/execution/T1059.001/). Check the screenshot below. 

![Image](https://github.com/nguyentimmy/Detection-Engineering/blob/main/2%20-%20Detect%20Current%20Attack%20Trends%20Using%20Threat%20Intelligence/Photos/T1059-APT.png)

### II. Automating the attack simulation using Atomic Red Teaming
On the list of possible attacks, we will choose an attack the threat actor may most likely use from the threat intel report. Let's say the threat actor is using Bloodhound, we can simulate an attack directly from Atomic Red Team, which is based on the MITRE framework.

![Image](https://github.com/nguyentimmy/Detection-Engineering/blob/main/2%20-%20Detect%20Current%20Attack%20Trends%20Using%20Threat%20Intelligence/Photos/T1059.001-BloodHound.png)

### III. Create a query or policy for Detection
If you want to create a custom detection rule to detect attacks from the threat actor using Bloodhound, [(T1059.001)](https://atomicredteam.io/execution/T1059.001/), here is the KQL to detect the threat. 

```
// Query for any bloodhound related processes and files
let BloodhoundCLI = dynamic([ 'Import-Module Sharphound.ps1' , '-collectionMethod', 'invoke-bloodhound', 'get-bloodhounddata']);
let BloodhoundExe = dynamic(['SharpHound.exe', 'BloodHound.exe', 'Neo4j-Management.exe']);
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has_any(BloodhoundCLI) or ProcessCommandLine has_any(BloodhoundExe) or FileName has_any(BloodhoundExe)
| project Timestamp, DeviceName, DeviceId, AccountName, AccountDomain, ProcessCommandLine, FileName, FolderPath, InitiatingProcessCommandLine, InitiatingProcessFileName, ReportId
```
