---
title: "Installing the Insight Agent in Silent Mode"
excerpt: ""
---
Silent installation provides a way for you to distribute the InsightAgent in unattended mode. To perform a silent installation, you must have administrator privileges.

## Windows

Run the following for 32-bit Windows:

```
msiexec /i agentInstaller-x86.msi /quiet /qn
```

Run the following for 64-bit Windows:

```
msiexec /i agentInstaller-x64.msi /quiet /qn
```

## Mac

Run the following in the folder of the Insight Agent that you downloaded:

```
sudo installer -pkg endpoint_agent.pkg -target /
```

## Linux

Linux Insight Agents always use silent installations. Refer to the README file in the agent package for install instructions.