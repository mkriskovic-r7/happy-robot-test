---
title: "Installing the Agent for McAfee ePO Users"
excerpt: ""
---
Installing the Insight Agent allows McAfee ePO users to deploy and manage the Insight Agent via McAfee ePO software management. 

This process assumes that the McAfee ePolicy Orchestrator is already configured to monitor the Windows systems in your environment, and these target systems have the McAfee Agent installed. 

To begin, download the following: 
* the Rapid7 ePO extension (http://download2.rapid7.com/download/NeXpose-v4/epo-extension/Rapid7Nexpose.zip)
* the Rapid7 Manager plugin (http://download2.rapid7.com/download/NeXpose-v4/epo-extension/R7AgentDeployment_0409.zip)
* the InsightAgent installer from the “Download agent” page in your application. These installer files should be accessible from the ePO server.

Next, install the Rapid7 Extension on the ePO Server, Install the Rapid7 Manager Plugin on Target Systems, and then Install the Insight Agent. 

### Installing the Rapid7 Extension on the ePO Server
You can install the Rapid7 ePO extension by obtaining the installation zip archive from the Rapid7 support. The extension can be installed on ePO using the following steps:
1. From the main menu of ePO, under the _Software_ category, click on **Extensions**.
2. The _Extensions_ screen appears. Click on the **Install Extension** button, and then browse to Rapid7.zip file location. Follow all the steps of the installation process.
3. After the installation is complete, you are returned to the Extensions screen. Ensure that Rapid7 is visible in the list of extensions and the state is _Running_.

### Installing the Rapid7 Manager Plugin on Target Systems
The Rapid7 Manager coordinates communication between the Rapid7 extension and the Insight Agents on the target systems. It is also responsible for enforcing the policies related to Rapid7 on the target systems. The following steps are required for installing the Rapid7 Manager on your systems.

1. From the main menu, under the _Software_ category, click on **Master Repository**.
2. On the Master Repository screen, click the **Check In Package** button, and browse to the R7AgentDeployment zip file.
3. Ensure that the application _Rapid7 Manager_ appears in the package list in the Master Repository screen.
4. From the main menu, under the _Policy_ category, select **Client Task Catalog**. 
5. On the Client Task Catalog screen, select **Product Deployment** as the task type, and then click the **New Task** button.
6. In the client task creation wizard, set the product as **Rapid7 Manager** and the action as **Install**. Complete the rest of the fields in the installation wizard based on your preferences.
7. Now that the installation task is created, you can apply it to the systems in your network. For this, you will have to return to the main menu. Under the _Systems_ category, select **System Tree**.
8. On the System Tree screen, select a system group and open the _Assigned Client Tasks_ tab. From the _Actions_ menu at the bottom of this tab, select **New Client Task Assignment**.
9. In the New Client Task Assignment wizard, select the **Install Rapid7 Manager** task created in the previous step. Based on your selections, the final screen of the wizard looks something like this:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/99dab86-Insight_Agent_installation_6.png",
        "Insight Agent installation_6.png",
        1440,
        860,
        "#5db5d3"
      ]
    }
  ]
}
[/block]
When this Client Task is assigned to your systems, the Rapid7 Manager is installed the next time ePO syncs up with those systems. By default, this sync-up process occurs once every hour.

### Installing the Insight Agent
The Rapid7 Manager is responsible for installing the Insight Agent on your systems. The following steps will help you configure the Agent installation.
 
1. From the main menu, click **Server Settings** under the _Configuration_ category.
2. In the Server Settings screen, select Rapid7 Settings. The right pane will have four text fields for agent-related configuration data - **client.crt**, **config.json**, **client.key** and **cafile.pem**. Complete these fields using the contents of similarly named files in the Insight Agent installation package. The contents of these files can be viewed by opening them in Notepad.
3. Return to the main menu and under the _Policy_ category, click on **Policy Catalog**. The Policy Catalog page will look like this:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a0fa60c-Insight_Agent_installation_8.png",
        "Insight Agent installation_8.png",
        1440,
        381,
        "#5aaac9"
      ]
    }
  ]
}
[/block]
4. On the Policy Catalog page, either duplicate the inbuilt _Default_ (in the case of this screenshot, the Default policy is *nexpose_Default*) policy, or click **New Policy**.
5. On the policy configuration page, select the recommended option - **Don’t reinstall the Rapid7 Insight Agent if already present**. Give this policy a suitable name like ‘install Rapid7 Insight Agent’.
6. Visit the System Tree screen through the main menu. On the System Tree screen, select a system group and open the _Assigned Policies_ tab. From the _Actions_ menu at the bottom of this tab, select **New Policy Assignment**.
7. In the Policy Assignment wizard, select **install Rapid7 Insight Agent** as the policy to assign.

When the Rapid7 Manager on your target system syncs up with the ePO server, it is notified about the new policy assigned to the system. It then downloads the configuration files from the ePO server and the Insight Agent hosted on the Rapid7 cloud platform.
You can confirm the installation of the Insight Agent on your target systems by visiting the path _Program Files > R7Agent_.