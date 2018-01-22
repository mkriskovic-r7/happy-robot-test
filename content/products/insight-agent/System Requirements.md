---
title: "System Requirements"
excerpt: ""
---
Currently, Insight Agents are officially supported on the following systems:
* **Windows** – All versions Windows XP onwards.
[block:callout]
{
  "type": "info",
  "body": "Windows XP (including SP2 and SP3) and Windows 2003 (including SP1) requires WMI service to be set to **Automatic** or **Manual**."
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Windows systems running the agent must have **all currently available Insight Agent updates applied**. The agent updates automatically, and information regarding the update is logged in the agent.log file. New jobs cannot be launched until all agent updates are applied.\n\nPlease note that if you are using InsightIDR, your system must also have:\n* **WMI enabled** – In order to collect certain information, the agent uses the WMI module in several jobs,. in particular, the ui_realtime job. In some cases, if WMI is disabled, the agent will start, but some data collection will fail. If WMI has been turned off, but has a startup type of “Automatic” or “Manual”, the agent will attempt to start WMI.\n* **Event Log enabled** – In order to properly monitor windows assets, the Insight Agent requires the Event Log to be running. This will not prevent the agent from starting (except on Windows XP and Windows Server 2003). The event log needs to be started on Windows XP and Windows 2003. Windows 2003 SP1 does not need the event log to be running."
}
[/block]
* **Mac** – All versions OS X Yosemite (version 10.10) onwards.
* **Linux** – all distributions and versions listed below:
   * Debian 7.0 – 8.2
   * CentOS 5.2 – 7.3
   * Oracle Enterprise Linux (OEL) 5.2 – 7.3
   * Red Hat Enterprise Linux (RHEL) 5.2 – 7.3
      * Red Hat Enterprise Linux (RHEL) Client 5.2 – 7.3
      * Red Hat Enterprise Linux (RHEL) Server 5.2 – 7.3
      * Red Hat Enterprise Linux (RHEL) Workstation 5.2 – 7.3
   * Ubuntu 11.04 – 17.04
   * Fedora 17-25
   * SUSE Linux Enterprise Server (SLES) 11 – 12
   * SUSE Linux Enterprise Desktop (SLED) 11 – 12
   * openSUSE LEAP (42.1 – 42.2)
   * Amazon Linux
[block:callout]
{
  "type": "warning",
  "body": "Administrator privileges for the target systems are required for installation."
}
[/block]