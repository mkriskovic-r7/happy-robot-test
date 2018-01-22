---
title: "Installing the Insight Agent"
excerpt: ""
---
To begin the installation process, download the Insight Agent and install it on the endpoint. Please note that you can only install one Insight Agent per machine.
[block:callout]
{
  "type": "info",
  "body": "If you are an existing Insight product customer and have already deployed an Insight Agent across your environment, there is nothing else you need to do. The Insight Agent works across all Insight products.",
  "title": "Note"
}
[/block]

[block:api-header]
{
  "title": "Step1: Download the Insight Agent"
}
[/block]
1. From the _Agent Management_ page, click the **Download agent** button.
2. From the _Download Agent_ page, download the Insight Agent for the appropriate platform. The Insight Agent is packaged in a ZIP file. The necessary license keys and certificates are provided in the downloaded file.
[block:api-header]
{
  "title": "Step 2: Install the Insight Agent"
}
[/block]
You can install the Insight Agent on [Windows](https://insightagent.help.rapid7.com/v1.0/docs/installation#section-windows), [Mac](https://insightagent.help.rapid7.com/v1.0/docs/installation#section-mac), and [Linux](https://insightagent.help.rapid7.com/v1.0/docs/installation#section-linux) systems. Follow the instructions for your operating system below.

## Windows

1.  Copy the ZIP file to the target system and unzip it.  You will find the MSI installer as well as the following security files: client.key, client.crt, config.json, and cafile.pem.
2.  Make sure that all supporting files are unzipped to the same folder as the installer.
3.  Install the agent by executing the MSI installer.  The agent will be installed as a service, and the security files will also be automatically installed.  The default installation details are:
    *  **Install Location** - C:\Program Files (x86)\Rapid7\Insight Agent\ for 32-bit systems and C:\Program Files\Rapid7\Insight Agent\ for 64-bit systems
    *  **Service Name** - Rapid7 Insight Agent

### Silent Installation

Run the following for 32-bit Windows:

`msiexec /i agentInstaller-x86.msi /quiet /qn`

Run the following for 64-bit Windows:

`msiexec /i agentInstaller-x64.msi /quiet /qn`

## Mac

1. Copy the ZIP file to the target system and unzip it.  You will find the PKG installer as well as the following security files: client.key, client.crt, config.json, and cafile.pem.
2. Make sure that all supporting files are unzipped to the same folder as the installer.
3. Install the agent by executing the PKG installer.  The agent will be installed as a service, and the security files will also be automatically installed.  The default installation details are:
    * **Install Location** - /opt/rapid7/ir_agent
    * **Service Name** - com.rapid7.ir_agent

### Silent Installation

Run the following in the folder of the Insight Agent that you downloaded:

`sudo installer -pkg endpoint_agent.pkg -target /`

## Linux

1. Copy the ZIP file to the target system and unzip it.  You will find a script named *agent_control* as well as the following security files: client.key, client.crt, config.json, and cafile.pem.
2.  Make sure that all supporting files are unzipped to the same folder as the installer.
3.  Install the Insight Agent by executing the *agent_control* script.  Installation commands can be found in the README file packaged with the script itself. The Insight Agent is installed as a service, and the security files are automatically installed. The default installation details are:
    *  **Install Location** - /opt/rapid7/ir_agent
    *  **Service Name** - ir_agent

### Silent Installation

Linux Insight Agents always use silent installations. Refer to the README file in the agent package for install instructions.

For more information on installation processes using Software Deployment Tools, see [Installing the Insight Agent Using Patch Management Software](doc:installing-the-insight-agent-using-patch-management-software), [Installing the Insight Agent Using GPOs](doc:installing-the-insight-agent-using-gpos), and [Installing the Insight Agent for McAfee ePO Users](doc:installing-the-insight-agent-for-mcafee-epo-users).
[block:callout]
{
  "type": "info",
  "body": "The Insight Agent will attempt to automatically update via Collector connections or via other agents before downloading the update from the Insight platform. Updates do not require a system restart for the new update to take effect.",
  "title": "Note"
}
[/block]

[block:api-header]
{
  "title": "Step 3: Verify the Insight Agent Is Running"
}
[/block]
The InsightAgent automatically runs after it is installed. To verify that it is up and running, you can run 
`ps aux | grep ir_agent` on Mac and Linux systems or check the Task Manager for "Rapid7's Insight Agent" on Windows systems.
[block:callout]
{
  "type": "info",
  "body": "For Insight Agents on Mac and Linux systems, multiple “ir_agent” processes will appear in the process list. This means the Insight Agent is running different tasks; it is not an indicator of multiple agents.",
  "title": "Note"
}
[/block]