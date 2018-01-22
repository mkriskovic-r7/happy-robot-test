---
title: "Using the Agent with InsightIDR"
excerpt: ""
---
Insight Agents are vital tools to monitor assets in your organization, either on the network, or in the hands of remote employees. To help you understand how agents can help you, let’s take a look at some of the benefits of agents while using InsightIDR:
* **Real time monitoring:** Real time monitoring in InsightIDR allows you to see detailed asset information, running process information, authentication information, account impersonation, and local machine detections. In addition to these features, and combined with Window File Access Auditing, the agent collects information about who is accessing what file and from where.
* **Opt-in Honey Credentials:** Honey credentials can be used in your environment to bait hackers with an appealing credential. By enabling Honey Credentials, the agent will inject a fake username and password into the memory of your environment. For example, a popular hacking tool allows hackers to dump credentials from memory and use those credentials to move laterally through networks. If the hacker uses the honey credential found in memory, InsightIDR will alert users about the attempted use of the honey credential, including what machine the attempt originated from, and where the attacker attempted to authenticate to.
* **Advanced detection:** The agent can lookup and detect vulnerabilities that users can’t find otherwise. For example, an agent can easily highlight protocol poisoning. Your environments could be at risk of being infiltrated with an attacker tool that sits in your network and listens for credentials being transmitted over certain multicast protocols. The agent will detect this type of attack, and alert you to it in near-real-time. 
[block:callout]
{
  "type": "info",
  "body": "* **WMI enabled** – In order to collect certain information, the agent uses WMI. In some cases, if WMI is disabled, the agent will start, but some data collection will fail. If WMI has been turned off, but has a startup type of “Automatic” or “Manual”, the agent will attempt to start WMI.\n* **Event Log enabled** – In order to properly monitor windows assets, the Insight Agent requires the Event Log to be running. This will not prevent the agent from starting (except on Windows XP and Windows Server 2003). The event log needs to be started on Windows XP and Windows 2003. Windows 2003 SP1 does not need the event log to be running.\n* **All currently available Insight Agent updates applied** – The agent updates automatically, and information regarding the update is logged in the agent.log file. New data collection capabilities, and detections cannot be used until all agent updates are applied.",
  "title": "Windows systems running the agent using InsightIDR must have:"
}
[/block]
##Data Collected by Insight Agents using InsightIDR
The Insight Agent is continuously running and sending data back to the Insight Platform. The Insight Agent collects the following data for detection purposes: local authentication logs, local process hashes, and local security and event logs.

Generally, collection includes the following types of data:
* Process starts and stops
* Security log event codes
* System event codes
* Protocol poisoning traps
* File audit logs

If you have exposure analytics (EA) entitlement for Threat Exposure Management (TEM), the agent collects vulnerability assessment data when the agent is installed starting from when it last collected data. If the agent is offline when collection was due, it will collect as soon as the agent comes online.