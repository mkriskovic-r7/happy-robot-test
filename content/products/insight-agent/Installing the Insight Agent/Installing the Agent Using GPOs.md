---
title: "Installing the Agent Using GPOs"
excerpt: ""
---
1. Download the continuous agent software and unzip it as described in the [Installing the Insight Agent](doc:installation) section.
2. Copy the MSI (s) that you want to use in your environment, along with all the other files in the package, to the network file share that you want to use for this software package. Note that the extra files that are in the package need to be kept in the same folder as the MSI.
3. Create a GPO package to install the Insight Agent. Open the Group Policy Management tool. If you already have an existing group policy then you will need to edit it, you will be using it to install this software.
4. Open Computer Configuration → Policies → Software Settings → Software Installation. Right-click on Software Installation and select New → Package to create a new software install.
5. Select the software you want to install by browsing to the network share where the downloaded agent package was copied. Select the 32-bit or 64-bit MSI, depending on which MSI needs to be run on the endpoints.
The software can be installed using the Assigned deployment method.
6. After setting up the software installation, be sure that the Security for the installation is properly configured. Assets that the package will be installed on need to have at least Read permissions to the installation configuration.

Windows systems which have permissions to the installation and to which the group policy has been applied, should have the software automatically pushed to them.