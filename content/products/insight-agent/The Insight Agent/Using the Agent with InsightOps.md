---
title: "Using the Agent with InsightOps"
excerpt: ""
---
Insight Agents are vital tools to monitor assets in your organization, either on the network, or in the hands of remote employees. To help you understand how agents can help you, let’s take a look at some of the benefits of agents while using InsightOps:
* **Log following:** The agent can send the contents of logs on the host machine to InsightOps using the Endpoint Interrogator, allowing you to monitor the current health and status of your devices. For example, if a System Administrator wants to send the syslog of a Linux host to InsightOps in real time, the agent makes this possible. 
* **Track remote assets:** Some assets owned by your organization may be off the organization’s network for long periods of time, the agent is still able to still track these assets for you. For example, a laptop used by an employee who works remotely, may not be on the company network. Using InsightOps, you can place an agent on this asset and easily monitor it. 
* **Monitor assets that have credential restrictions:** Use InsightOps to work with assets that have distinct or frequently changing administrative credentials, and then deploy an agent to the asset rather than continually updating credentials in the Insight Platform collector. 

##Data Collected by Insight Agents using InsightOps
When deployed, an agent collects data from the endpoint, compresses it, and sends it back to InsightOps for analysis. The data it collects includes:
* Basic asset identification information
* Windows registry information
* File version and package information
[block:callout]
{
  "type": "info",
  "body": "For configuring the agent with InsightOps on Windows, see https://insightops.help.rapid7.com/docs/insight-agent-on-windows\nFor configuring the agent with InsightOps on Mac, see https://insightops.help.rapid7.com/docs/insight-agent-on-mac-osx\nFor configuring the agent with InsightOps on Linux, see https://insightops.help.rapid7.com/docs/insight-agent-on-linux"
}
[/block]