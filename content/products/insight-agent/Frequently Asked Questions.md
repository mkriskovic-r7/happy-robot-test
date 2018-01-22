---
title: "Frequently Asked Questions"
excerpt: "Find answers to Insight Agent related questions on this page."
---
At this point, you should understand the basic concepts around Insight Agents and how to install them.  Here are some answers to questions that you may still have at this point.
[block:api-header]
{
  "title": "What do I need to do if I am an Insight IDR customer and I've already deployed an Insight Agent?"
}
[/block]
If you are an existing InsightIDR customer and have already deployed an Insight Agent across your environment, there is nothing else you need to do. The Insight Agent works with both InsightIDR and Nexpose Now.
[block:api-header]
{
  "title": "What do I need to do in order to get an Insight Agent?"
}
[/block]
If you are currently a Nexpose Enterprise or Nexpose Ultimate user, you just need to opt in to Nexpose Now. After you opt in, you'll need to download and install your agent on the system. Insight Agents will automatically begin to operate after they are installed; no additional configuration is needed.
[block:api-header]
{
  "title": "How do Insight Agents communicate?"
}
[/block]
Insight Agents communicate with the platform either directly or via the Rapid7 Collector.
[block:api-header]
{
  "title": "How is the communication between the agent and platform secured?"
}
[/block]
Communication between the agent and the platform is authenticated by two-way SSL and is secured by TLS v1.2 with a limited list of ciphers. It will fall back to TLSv1.1 for backwards compatibility.
[block:api-header]
{
  "title": "How do I perform a silent install of agents?"
}
[/block]
You can silently install an agent by navigating to the download location for the installer, and running the following commands from the command line:

## Windows

`$ msiexec /i Rapid7EndpointAgent -x64.msi /quiet /qn`

## Mac

`$ installer -pkg ir_agent.pkg -target /`

## Linux

The installations for Linux agents are always silent installs.  Refer to the README file in the agent package for install instructions.
[block:api-header]
{
  "title": "What kind of data does the agent collect?"
}
[/block]
When deployed, an agent collects data from the endpoint, compresses it, and sends it back to Nexpose for analysis. The data it collects includes:

* Basic asset identification information
* Windows registry information
* File version and package information
[block:api-header]
{
  "title": "Does the Insight Agent perform the assessment?"
}
[/block]
No. The agent does not perform the vulnerability assessment. Nexpose automatically performs vulnerability assessments when the latest data is available from the agent on the platform. When Nexpose completes the assessment, the information will become available from your dashboards.
[block:api-header]
{
  "title": "Is any information from the agent logged?"
}
[/block]
Information is logged to a file called `agent.log`. This file also gets rolled into `agent.log.1` and `agent.log.2`. If you ever need support, you will need to provide us with these files so we can help you troubleshoot your issue.
[block:api-header]
{
  "title": "More Questions?"
}
[/block]
If you still have questions about agents or need additional help, please check out our [customer portal](https://www.rapid7.com/for-customers/).