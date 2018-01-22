---
title: "Installing the Agent Using Patch Management Software"
excerpt: ""
---
If you have multiple assets in your environment, it can be tedious and time consuming to deploy an agent on each one. To save time, the Insight agent can be pushed out to assets using standard patch management software. To do so, proceed through perform steps 1 and 2 in [Installing the Insight Agent](doc:installation). The unzipped folder can then be pushed out to assets, and you can then run a silent install of the agent, using the normal Microsoft commands for an MSI file:
```msiexec /i agentinstaller-x86_x64.msi /quiet /qn```