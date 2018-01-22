---
title: "Installing the Insight Agent (deprecated)"
excerpt: ""
---
To begin the installation process, download the Insight Agent and install it on the endpoint. Just remember that you can only install one Insight Agent per machine.
[block:callout]
{
  "type": "info",
  "body": "If you are an existing Insight product customer and already deployed an Insight Agent across your environment, there is nothing else you need to do. The Insight Agent works across all Insight products."
}
[/block]
1. From the _Agent Management_ page, click the **Download agent** button.
2. From the _Download Agent_ page, download the Insight Agent for the appropriate platform. The Insight Agent is packaged in a ZIP file. The necessary license keys and certificates are provided in the downloaded file.
3. Copy the ZIP file to the target system and unzip it. You will find the installer (MSI for Windows, PKG for Mac, a script named *agent_control* for Linux), as well as four security files: client.key, client.crt, config.json, and cafile.pem. Make sure that all supporting files are unzipped to the same folder as the installer.
4. Install the Insight Agent by executing the relevant installer. For the Linux agent, installation commands can be found in the README file packaged with the installer. The Insight Agent is installed as a service, and the security files are automatically installed. The default installation details are:
   * Windows
      * Install location - c:\Program Files\Rapid7\Insight Agent
      * Service name - Rapid7 Insight Agent
   * Mac
      * Install location - /opt/rapid7/ir_agent
      * Service name - com.rapid7.ir_agent
   * Linux
      * Install location - /opt/rapid7/ir_agent
      * Service name - ir_agent

After you install the Insight Agent, it runs automatically. To verify that the agent is running, try the following commands:
* **Windows** - Look in the Task Manager and ensure that "Rapid7's Insight Agent" is running.
* **Mac** - In the terminal, run the following command: ```ps aux | grep ir_agent```
[block:callout]
{
  "type": "info",
  "body": "Multiple “ir_agent” processes will appear in the process list. This means the Insight Agent is running different tasks, it is not an indicator of multiple agents."
}
[/block]
* **Linux** - In the terminal, run the following command: ```ps aux | grep ir_agent```
[block:callout]
{
  "type": "info",
  "body": "Multiple “ir_agent” processes will appear in the process list. This means the Insight Agent is running different tasks, it is not an indicator of multiple agents."
}
[/block]
For more information on installation processes using Software Deployment Tools, see [Installing the Insight Agent Using Patch Management Software](doc:installing-the-insight-agent-using-patch-management-software), [Installing the Insight Agent Using GPOs](doc:installing-the-insight-agent-using-gpos), and [Installing the Insight Agent for McAfee ePO Users](doc:installing-the-insight-agent-for-mcafee-epo-users).
[block:callout]
{
  "type": "info",
  "body": "The Insight Agent will attempt to automatically update via Collector connections, or via other Insight Agents before downloading the update from the Insight platform. Updates do not require a system restart for the new update to take effect."
}
[/block]
###Performing a Silent Installation
[block:callout]
{
  "type": "warning",
  "body": "To perform a silent installation, administrator privileges are required."
}
[/block]
Based on your Operating System, run the appropriate command: 
**Windows:** Run the following for 32-bit Windows:
```msiexec /i agentInstaller-x86.msi /quiet /qn```
Run the following for 64-bit Windows:
```msiexec /i agentInstaller-x64.msi /quiet /qn```

**Mac:** Run the following in the folder of the Agent that you downloaded:
```sudo installer -pkg endpoint_agent.pkg -target /```

**Linux:** The installation for Linux agents are always silent installs.