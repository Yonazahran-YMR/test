# SOC Analyst

# SOC Analyst Study Notes 🛡️

Alright, time to actually write down what a Security Operations Center (SOC) analyst does so I don't forget it by tomorrow. Ngl, this whole field felt overwhelming at first, but once I broke it down, it actually makes a lot of sense. 

## What even is a SOC?

Basically, it's the mission control room for an organization's cybersecurity. 
* It's where people sit (or work remotely) staring at screens, waiting for bad stuff to happen.
* The main goal? Find threats, stop them, and figure out how the bad guys got in before they mess everything up.
* It’s a 24/7/365 thing because hackers apparently don't sleep, which means shift work. Fun.

## The Tier System (How we grow up)

This clicked for me because it's basically customer support, but for getting hacked instead of broken printers. 

* **Tier 1 (Triage / The Front Lines):** 
  * This is usually the entry-level spot. 
  * You're basically staring at alerts all day, figuring out what's real and what's just a false positive. 
  * If it looks sketchy, you escalate it. If it's nothing, you close it. Easy enough, but volume is crazy high.
* **Tier 2 (Incident Responders):** 
  * When Tier 1 finds something actually legit, it gets kicked up here.
  * These folks do the deep-dive investigation. They figure out the scope of the breach and how to contain it so it doesn't spread.
* **Tier 3 (Threat Hunters / Deep Analysis):** 
  * The senior hackers (the good guys). 
  * They aren't just waiting for alerts—they're actively hunting around the network to find hidden threats that automated tools missed. 

## The Tools We Use

Don't panic about memorizing all of these yet, but these are the big ones:

* **SIEM (Security Information and Event Management):** 
  * *This is basically the brain.* It sucks in logs from everywhere—firewalls, servers, user logins—and squawks when something looks weird. Splunk and Microsoft Sentinel are huge here.
* **EDR (Endpoint Detection and Response):** 
  * Watches individual laptops, servers, and phones (the endpoints). If a laptop starts doing weird crypto-mining or downloading sketchy stuff, EDR steps in to isolate it.
* **Ticketing Systems:** 
  * ServiceNow or Jira. Not glamorous, but everything we do has to be documented. If you didn't document it, it didn't happen.

## A Typical Workflow (What I'd actually be doing)

1. **Alert pops up:** SIEM flags a weird login from halfway across the world.
2. **Investigation:** I check it out. Is this employee just on a VPN? Or did their password actually get stolen?
3. **Triage:** Decide if it's a false alarm or a real incident.
4. **Action:** If it's real, I might disable the user account, block the IP, and write up a report for Tier 2. 

*Note to self: Remember that speed is important, but accuracy matters more. Don't just close alerts to clear your inbox or you'll get fired lol.*