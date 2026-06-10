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
To find this I took the Source and destination IPv4 I had gotten from Q1 and I applied it to the filter. After this I added "&& smb" to the filter to find the source of where the intital contact of the attack. It was likely SMB since we are dealing with PsExec so all I did after that was follow the TCP stream and look through the packet and I found my answer.
 
### Q3 [Knowing the username of the account the attacker used for authentication will give us insights into the extent of the breach. What is the username utilized by the attacker for authentication?]
**What I did:** 
Following of Q2 I scrolled through the results of the filters I added and looked at the SMB2 packets that appeared after following the TCP stream and it listed "NTLMSSP_AUTH, User: \******." 
 
### Q4 [After figuring out how the attacker moved within our network, we need to know what they did on the target machine. What's the name of the service executable the attacker set up on the target?]
**What I did:** 
The same filter as the previous two questions helped me find the answer as the executable was listed with the SMB2 packets under the filter. This was easy to spot because the answer was going to end in ".exe". 

### Q5 [We need to know how the attacker installed the service on the compromised machine to understand the attacker's lateral movement tactics. This can help identify other affected systems. Which network share was used by PsExec to install the service on the target machine?]
**What I did:** 
The same filter was applied and for this question as well as the SMB2 packets shown tell a lot of information. I knew it was looking for a network so under the info section in the SMB2 packets I was looking for something that looked like an IP address followed by something else and that is where I found my answer.

### Q6 [We must identify the network share used to communicate between the two machines. Which network share did PsExec use for communication?]
**What I did:** 
I clicked on the SMB2 packet that had the network information that I had received from the previous question and I followed the TCP stream and looked "$" using the Find search bar at the bottom of the TCP stream since I knew it would be in the answer and within 2 "find next" I was able to find it.

### Q7 [Now that we have a clearer picture of the attacker's activities on the compromised machine, it's important to identify any further lateral movement. What is the hostname of the second machine the attacker targeted to pivot within our network?]
**What I did:** 
For this question all I did was use the "smb" filter to find the answer since NTLMSSP_CHALLENGE were reccomended as a hint to find the answer but they are wrapped inside smb. I couldnt find the packets the way it was reccomended so I thought more out of the box and it worked out. 
