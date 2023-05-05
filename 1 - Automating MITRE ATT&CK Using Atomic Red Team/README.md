# Integrating MITRE ATT&CK

:star: First, we must understand the threat actors TTP (Tatics, Technqiues, & Procedures) in this order. 

![Photo](https://github.com/nguyentimmy/Detection-Engineering/blob/main/1%20-%20Automating%20MITRE%20ATT%26CK%20Using%20Atomic%20Red%20Team/Photos/MITRE.png)

*MITRE ATT&CK® is a globally-accessible knowledge base of adversary tactics and techniques based on real-world observations. The ATT&CK knowledge base is used as a foundation for the development of specific threat models and methodologies in the private sector, in government, and in the cybersecurity product and service community.*

:star: We will create a project to detect well known attacks. You can use any Red Team simulations

## [+] Requirements 
- [Atomic Red Team Installation](https://github.com/redcanaryco/invoke-atomicredteam/wiki/Installing-Invoke-AtomicRedTeam#install-execution-framework-and-atomics-folder)
- Powershell 
- Sentinel or MDE

## [+] Steps
1. Install Atomic Red Team (In this case I am installing ART without the payloads and malware)
```
Install-Module -Name invoke-atomicredteam,powershell-yaml -Scope CurrentUser
```
```
IEX (IWR 'https://raw.githubusercontent.com/redcanaryco/invoke-atomicredteam/master/install-atomicredteam.ps1' -UseBasicParsing);
Install-AtomicRedTeam -getAtomics -Force -noPayloads
```

1. First, we will take the very first tatic on the photo above which is Initial Access. We will name the project, story, or task: 
**"Defend and Detect: Initial Access"**
  > TBA

2. TBA
  > TBA
  - :link: [TBA]():exclamation:

3. TBA
  > TBA
  - :link: [TBA]():exclamation:


## [+] 
- :link: [TBA]():exclamation:
- :link: [TBA]():exclamation:
