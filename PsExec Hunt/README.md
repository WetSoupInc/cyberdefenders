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
I first wanted to check out IP addresses that had the most traffic so I navigated to Wiresharks Statistics tab at the top and then clicked on conversations. I then knew that it would be under the IPv4 or the IPv6 Since it was an IP address that I was looking for. There was no IPv6 so I checked all the IPv4 and found the one IPv4 with the most traffic and because this is a PsExec lab I figured high traffic would be involved in the findings. 

### Q2 [To fully understand the extent of the breach, can you determine the machine's hostname to which the attacker first pivoted?]
**What I did:** 

 
### Q3 [Knowing the username of the account the attacker used for authentication will give us insights into the extent of the breach. What is the username utilized by the attacker for authentication?]
**What I did:** 

 
### Q4 [After figuring out how the attacker moved within our network, we need to know what they did on the target machine. What's the name of the service executable the attacker set up on the target?]
**What I did:** 


### Q5 [We need to know how the attacker installed the service on the compromised machine to understand the attacker's lateral movement tactics. This can help identify other affected systems. Which network share was used by PsExec to install the service on the target machine?]
**What I did:** 


### Q6 [We must identify the network share used to communicate between the two machines. Which network share did PsExec use for communication?]
**What I did:** 


### Q7 [Now that we have a clearer picture of the attacker's activities on the compromised machine, it's important to identify any further lateral movement. What is the hostname of the second machine the attacker targeted to pivot within our network?]
**What I did:** 
