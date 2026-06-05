# PsExec Hunt — CyberDefenders Challenge

**Difficulty:** Easy  
**Category:** Network Forensics  
**Date Completed:** N/A

## Scenario Summary
Analyze SMB traffic in a PCAP file using Wireshark to identify PsExec lateral movement, compromised systems, user credentials, and administrative shares.

## Tools Used
- Browser / GitHub / Linux / Wireshark 

## Tactics Used
- Execution / Defense Evasion / Discovery / Lateral Movement

## Scenario
An alert from the Intrusion Detection System (IDS) flagged suspicious lateral movement activity involving PsExec. This indicates potential unauthorized access and movement across the network. As a SOC Analyst, your task is to investigate the provided PCAP file to trace the attacker’s activities. Identify their entry point, the machines targeted, the extent of the breach, and any critical indicators that reveal their tactics and objectives within the compromised environment.

## Why this matters 
This challenge matters because PsExec is a common tool used for lateral movement, allowing attackers to execute commands remotely and expand their control across systems. Detecting and understanding this activity helps SOC analysts recognize real-world intrusion patterns and strengthen defenses against privilege escalation and network compromise.

## Investigation Process

### Q1 [To effectively trace the attacker's activities within our network, can you identify the IP address of the machine from which the attacker initially gained access?]
**What I did:** 


