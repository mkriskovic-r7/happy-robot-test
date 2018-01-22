---
title: "Deploying Insight Agent to Azure"
excerpt: ""
---
The Rapid7 Insight Agent connects your Azure virtual machines to solutions on the Rapid7 Insight platform.

To get started, download the agent configuration/installation package from the agent download page in InsightVM.

# Installing the Insight Agent extension

To add the Rapid7 Insight Agent extension to a virtual machine, follow these steps:

1. Download the configuration zip from your Insight Platform solution.
2. Apply the extension to the virtual machine through either the azure portal or command line.

## Using Azure Portal

In the Azure portal, navigate to:

* **Virtual Machines** > \[VMname\] > **Extensions** > **Add** button > **Rapid7 Insight Agent** extension

## Using Command Line
[block:callout]
{
  "type": "info",
  "body": "Get the latest available extension version with the Azure CLI."
}
[/block]
1. Set up the [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest) to [access the extension details](https://docs.microsoft.com/en-us/cli/azure/vm/extension?view=azure-cli-latest).
2. Log in with `az login`.
3. Browse Rapid7 extension versions with:

```
az vm extension image list --publisher "Rapid7.InsightPlatform"
[{
    "name": "InsightAgentLinux",
    "publisher": "Rapid7.InsightPlatform",
    "version": "2.0.0.2"
},
{
    "name": "InsightAgentWindows",
    "publisher": "Rapid7.InsightPlatform",
    "version": "2.0.0.2"
},
...
```

### PowerShell

To add the Rapid7 Insight Agent extension to a virtual machine using PowerShell, first make sure you have the [latest version](https://github.com/Azure/azure-powershell#installation) of PowerShell installed.
[block:callout]
{
  "type": "warning",
  "title": "NOTE",
  "body": "Switching between classic and resource manager in the same PowerShell  window frequently results in an error:\n\n`Missing type map configuration or unsupported mapping`\n\nWhen using both types, it is recommended to use separate PowerShell windows."
}
[/block]
1. Base64 encode the configuration zip file:


```
$filepath = C:\tmp\config.zip
$binary = Get-Content -Path $filepath -Encoding Byte
$base64 = [Convert]::ToBase64String($binary)
```


2. Apply extension:

**Classic**:
Login: `Add-AzureAccount`
List VMs: `Get-AzureVM`
```
$params = "{`"configzip`": `"$base64`" }"
$vmobj = Get-AzureVM -ServiceName {your_vm_service_name} \
-Name {your_vm_name}
$vmobj | Set-AzureVMExtension -ExtensionName
'InsightAgentWindows' \
-Publisher 'Rapid7.InsightPlatform' \
-Version 2.0 \
-PrivateConfiguration $params
$vmobj | Update-AzureVM   # This applies the extension
$vmobj | Get-AzureVMExtension
```

**Resource Manager**:
Login: `Login-AzureRmAccount`
List VMs: `Get-AzureRmVM`
```
$params = @{"configzip" = "$base64"; };
Set-AzureRmVMExtension -Publisher Rapid7.InsightPlatform \
-ExtensionName InsightAgentWindows \
-ExtensionType InsightAgentWindows \
-Version 2.0 \
-ProtectedSettings $params \
-VMName {your_vm} \
-Location {your_location} \
-ResourceGroupName {your_resource_group}
```

### Azure 2.0 CLI

To add the Rapid7 Insight Agent extension to a **resource manager** virtual machine using the Azure CLI, first make sure you have the latest version of the [Azure 2.x CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest) installed.

```
az login
base64=$(base64 ~/config.zip)
az vm extension set --protected-settings "{\"configzip\":\"$base64\"}" --vm-name
{your_windows_vm} --name InsightAgentWindows --publisher Rapid7.InsightPlatform
--resource-group {vm-resource-group} --version 2.0
```

### Azure 1.0 CLI

To add the Rapid7 Insight Agent extension to a **classic** virtual machine using the Azure CLI, first make sure you have the latest version of the [Azure 1.x CLI](https://docs.microsoft.com/en-us/azure/cli-install-nodejs) installed.

```
azure login
azure config mode asm
base64=$(base64 ~/config.zip)
azure vm extension set -t "{\"configzip\":\"$base64\"}" "{your_windows_vm}"
InsightAgentWindows Rapid7.InsightPlatform 2.0
```