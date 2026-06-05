# Lespion — CyberDefenders Challenge

**Difficulty:** Easy  
**Category:** OSINT / Threat Intelligence  
**Date Completed:** May 30, 2026

## Scenario Summary
Investigate an insider threat by analyzing GitHub repositories for exposed credentials, using OSINT tools to correlate online accounts, and performing image analysis to identify locations.

## Tools Used
- Browser / GitHub / Cyberchef / Kali Linux / Sherlock

## Scenario 
You have been tasked by a client whose network was compromised and brought offline to investigate the incident and determine the attacker's identity.

Incident responders and digital forensic investigators are currently on the scene and have conducted a preliminary investigation. Their findings show that the attack originated from a single user account, probably, an insider. Investigate the incident, find the insider, and uncover the attack actions.

## Why this matters 
Exposed API keys in public repos are a real attack 
vector. Threat actors actively scan GitHub for leaked credentials using 
tools like TruffleHog and GitLeaks.
 
## Investigation Process

### Q1 - [What API key did the insider add to his GitHub repositories?]
**What I did:** Navigated to the GitHub profile linked in the challenge, 
browsed repositories starting with Project-Build---Custom-login-page, 
examined files within the repo and identified an exposed API key.

### Q2 — [What plaintext password did the insider add to his GitHub repositories?]
**What I did:** Scrolled through the same file and saw the password was
encrypted with base64. I opened cyberchef and got the plaintext string.

### Q3 — [What cryptocurrency mining tool did the insider use?]
**What I did:** Went to the repositories to see as I had reached the end
of the file and there was no more important information. The user also had
tools listed per respository so I looked for the descriptions to find the right
one. 

### Q4 — [On which gaming website did the insider have an account?]
**What I did:** On a virtual machine of kali linux I used the tool "sherlock"
while using EMarseille99 as the input paramerter. A couple results showed up but
only one fix the 5 characters and game website description.

### Q5 — [What is the link to the insider Instagram profile?]
**What I did:** I had got this link from the previous question as 
sherlock produced results with many of the users accounts on different platforms.

### Q6 — [Which country did the insider visit on her holiday?]
**What I did:** From going on the users instagram account since it was 
relevant in the last question I was able to find the country.

### Q7 — [Which city does the insider family live in?]
**What I did:** The user had 2 photos listed of the suspected country.
The answer was only also 5 letters long so putting the two togethert I 
was able to suspect where they may live.

### Q8 — [You have been provided with a picture of the building in which the company has an office. Which city is the company located in?]
**What I did:** I had simply went on to google and used the image
in my search and it gave a description of the city and country of orgin.

### Q8 — [With the intel, you have provided, our ground surveillance unit is now overlooking the person of interest suspected address. They saw them leaving their apartment and followed them to the airport. Their plane took off and landed in another country. Our intelligence team spotted the target with this IP camera. Which state is this camera in?]
**What I did:** I had done the same thing as question 8 to find the answer.
