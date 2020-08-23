---
title: Extensions and virtual machine agent minimum version support
description: Describes the minimum version support for Linux and Windows virtual machine agents in Azure.
ms.date: 07/21/2020
ms.prod-support-area-path: 
ms.reviewer: 
---
# Minimum version support for virtual machine agents in Azure

This article describes the minimum version support for Linux and Windows virtual machine agents in Azure.

_Original product version:_ &nbsp; Virtual Machine running Linux, Virtual Machine running Windows  
_Original KB number:_ &nbsp; 4049215

## Minimum supported version of Linux VM Agent

To get support for Linux Agent and extensions in Azure, the [Linux Agent](https://github.com/Azure/WALinuxAgent) version on the Linux virtual machine (VM) must be later than or equal to 2.2.10. 

**Starting in July 2020**, the minimum supported version will be 2.2.41 for the Linux Agent.

- If the Linux Agent version is earlier than 2.2.10, you must update the VM by using the distribution package manager and by enabling auto-update. 
- If the distribution vendor does not have the minimum Linux Agent version in the package repositories, the system is still in support. If the Linux Agent version is later than 2.1.7, you must enable the Agent auto-update feature. This will retrieve the latest version of code for extension handling. 
- If the Linux Agent version is earlier than 2.2.10, or if the Linux system is out-of-support, we may require you to update the agent before we can offer support. 
- If the Linux Agent version is customized by the publisher, Microsoft may direct you to the publisher of the image for support agent or extension specific support due to the customization.
 To upgrade the Linux Agent, see [How to update the Azure Linux Agent on a VM](https://docs.microsoft.com/azure/virtual-machines/linux/update-agent). 

### How to check your Linux Agent Version?

To check your Linux Agent Version, run:

```
waagent --version
```

For example, if you are running this command on Ubuntu 18.04, you'll see the output as:WALinuxAgent - 2.2.45 Python - 3.6.9 Goal State Agent - 2.2.48.1

```
WALinuxAgent – 2.2.45
Python – 3.6.9
Goal State Agent – 2.2.48.1
```

Refer to [https://github.com/Azure/WALinuxAgent/wiki/FAQ](https://github.com/Azure/WALinuxAgent/wiki/FAQ) for more information about the agent.

## Minimum supported version of Windows VM Agent

To get support for Windows Agent and extensions in Azure, the Windows Agent on the Windows VM must be later than or equal to 2.7.1198.781.

**Starting in June of 2020**, the minimum supported version will be 2.7.41491.911 for the Windows agent. 

- If the Windows Agent is earlier than 2.7.1198.781, or if the Windows system is out-of-support, we may require you to update the agent before we can offer support. 
 To upgrade the Windows Agent, see [About the virtual machine agent and extensions for Windows VMs](https://docs.microsoft.com/azure/virtual-machines/extensions/agent-windows). 

## Frequently asked questions

**What is the Azure Linux Agent?**
  
The Microsoft Azure Linux Agent (waagent) manages both Linux & FreeBSD provisioning, and virtual machine (VM) interaction with the Azure Fabric Controller. In addition to the Linux Agent providing provisioning functionality, Azure also provides the option of using cloud-init for some Linux OSes. To know more about the functionality, visit the [Linux VM Agent page](https://docs.microsoft.com/azure/virtual-machines/extensions/agent-linux).

**What is changing on Azure Linux Agent version requirements after July 31, 2020?**
  
After July 31, 2020, any Azure Linux Agent version below 2.2.41 will not be supported for published images. This means that any Linux VM images published to Azure Marketplace need to have 2.2.41 version or later installed in them.

**Do I need to take any action?**
  
Yes, any Linux VM images should be updated to 2.2.41 or higher versions to continue to be part of the support.

**Why is this change happening?**
  
Azure Linux Agent 2.2.41 will reach it's scheduled end-of-life. More recent versions of Azure Linux Agent have many improvements and bug fixes over version 2.2.41, and provides more stability.
  
**Will any existing VM images published in the Marketplace be affected?**
  
There is no impact to existing images at the moment, but eventually all existing images will need to be updated with newer versions. Current best practice is to allow the agent to auto-update the version,  unless it's disabled for any specific reason.

**Are Windows VM publishers affected?**
  
No. This change only affects Linux VM publishers.

**How do I install or update the VM with Linux agent?**
  
- For information on how to install Azure VM agent with Linux, follow steps in [this article](https://docs.microsoft.com/azure/virtual-machines/extensions/agent-linux#installation).
- For more information on updating the Azure Linux Agent on a VM, follow steps in [this article](https://docs.microsoft.com/azure/virtual-machines/extensions/update-linux-agent).

## More information

For more information about the support policy for running Microsoft server software in the Microsoft Azure virtual machine environment, see [Microsoft server software support for Microsoft Azure virtual machines](https://support.microsoft.com/help/2721672).