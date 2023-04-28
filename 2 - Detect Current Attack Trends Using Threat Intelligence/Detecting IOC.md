## [+] Detecting IOC 

In this case, I will be use Defender for Endpoint as my EDR solution to create a detection alert and threat hunting query (Which can be beneficial for the threat hunters or SOC).

### I. Using the IOC from your threat intel feed 
Use the list of IOC provided by your threat intel or open source feed. In my case I will use Microsoft Threat Intel for my IOC. 
![Image](https://github.com/nguyentimmy/Detection-Engineering/blob/main/2%20-%20Detect%20Current%20Attack%20Trends%20Using%20Threat%20Intelligence/Photos/IOC-Coinminer.png)

### II. Creating the Query based on your needs
Alternatively, you can use an [IOC parser on SOC Prime](https://tdm.socprime.com/uncoder-cti/) platform to convert into the list IOC to query that fits your SIEM/EDR Solution. It will help speed up the proccess. 

![Image](https://github.com/nguyentimmy/Detection-Engineering/blob/main/2%20-%20Detect%20Current%20Attack%20Trends%20Using%20Threat%20Intelligence/Photos/IOC-Steps.png)

Since I'm using Defender for Endpoint, here is an example of an KQL script that extract IOC's from a link that contains a TXT file. This query will search for any devices connected to any IOC. A detection rule can be created.

```
// This will search for the Indicators of Compromise (IOCs) in the form of SHA256 hashes within the link containing the TXT file.
let EmotetDomain = externaldata(Domain: string)[@"https://raw.githubusercontent.com/Cisco-Talos/IOCs/main/2022/11/Emotet_contacted_domains.txt"] with (format="txt", ignoreFirstRecord=True);
DeviceNetworkEvents
| where RemoteUrl in~ (EmotetDomain)
| project Timestamp, RemoteUrl, RemoteIP, DeviceName, DeviceId, InitiatingProcessCommandLine, InitiatingProcessFileName, InitiatingProcessAccountDomain, InitiatingProcessAccountName, ReportId
```

### III. 
