---
title: 部署、管理和报告Microsoft Defender 防病毒
description: 可以使用 Intune、Microsoft Endpoint Configuration Manager、组策略、PowerShell 或 WMI 部署和管理 Microsoft Defender 防病毒
keywords: 部署、管理、更新、保护、Microsoft Defender 防病毒
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 3fc0d1e927603a28cd622207cc1690e0ba5e413e
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882352"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>部署、管理和报告Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以通过多种方式部署、管理和Microsoft Defender 防病毒报告应用程序。

由于 Microsoft Defender 防病毒 客户端是作为 Windows 10 和 Windows 11 的核心部分安装的，因此客户端到终结点的传统部署不适用。

但是，在大多数情况下，你仍然需要使用 Microsoft Intune、Microsoft Endpoint Configuration Manager、Azure Defender 或组策略对象在终结点上启用保护服务，如下表所述。

你还将看到以下其他链接：

- 管理Microsoft Defender 防病毒保护，包括管理产品和保护更新
- 报告Microsoft Defender 防病毒保护

> [!IMPORTANT]
> 在大多数情况下，Windows 10或Windows 11如果找到另一个正在运行且最新的防病毒产品Microsoft Defender 防病毒将禁用该防病毒程序。 必须先禁用或卸载第三方防病毒产品，Microsoft Defender 防病毒才能正常运行。 如果重新启用或安装第三方防病毒产品，Windows 10或Windows 11自动禁用Microsoft Defender 防病毒。

工具|部署选项 (<a href="#fn2" id="ref2">2</a>) |管理选项 ([3](#fn3))  (网络范围的配置和策略或) |报告选项
---|---|---|---
Microsoft Intune|[在 Intune 中添加终结点保护设置](/intune/endpoint-protection-configure)|[在 Intune 中配置设备限制设置](/intune/device-restrictions-configure)| [使用 Intune 控制台管理设备](/intune/device-management)
Microsoft Endpoint Manager ([1](#fn1)) |使用 [Endpoint Protection point site system role][] 和 [enable Endpoint Protection with custom client settings][]|具有 [默认和自定义的反恶意软件策略][] 和 [客户端管理][]|具有默认 [Configuration Manager Monitoring workspace][] 和 [email alerts][]
已加入域 (组策略和 Active Directory) |使用组策略对象部署配置更改并确保Microsoft Defender 防病毒配置更改。|使用组策略对象 (GPO) [配置 Microsoft Defender 防病毒][] 和 [配置 Windows Defender 功能][]|终结点报告不适用于组策略。 可以生成 [组策略列表，确定是否未应用任何设置或策略][]
PowerShell|使用组策略、Microsoft Endpoint Configuration Manager或手动在单个终结点上部署。|使用 Defender 模块中提供的 [Set-MpPreference] 和 [Update-MpSignature] cmdlet。|使用相应的 [Defender 模块中可用的 Get- cmdlet][]
Windows Management Instrumentation|使用组策略、Microsoft Endpoint Configuration Manager或手动在单个终结点上部署。|使用 [set 方法的 MSFT_MpPreference class][] 和 [update 方法的 MSFT_MpSignature class][]|在 [MSFT_MpComputerStatus MIV2 Provider][] 中，使用 [Windows Defender MSFT_MpComputerStatus][] 类和关联类的 get 方法
Microsoft Azure|使用 Microsoft Antimalware 配置或 Azure PowerShell [cmdlet](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios)在 Azure 门户中部署 Azure Visual Studio。 还可以在 [Azure Defender 中安装终结点保护*](/azure/security-center/security-center-install-endpoint-protection)|使用[Microsoft Antimalware cmdlet](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)配置虚拟机和云服务Azure PowerShell或使用[代码示例](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|通过[Microsoft Antimalware cmdlet 对虚拟机和云服务Azure PowerShell启用](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)监视。 还可以查看 Azure Active Directory 中的使用情况报告以确定可疑活动，包括[可能感染的设备][]报告，并配置 SIEM 工具以报告 [Microsoft Defender 防病毒 事件][]，并添加该工具作为 AAD 中的应用。

1. <span id="fn1" />某些功能和特性（尤其是与云保护相关）的可用性在 Microsoft Endpoint Manager (Current Branch) 和 System Center 2012 Configuration Manager 之间有所不同。 在此库中，我们专注于 Windows 10、Windows 11、Windows Server 2016 和 Microsoft Endpoint Manager (Current Branch) 。 有关[描述主要](cloud-protection-microsoft-defender-antivirus.md)区别的表，请参阅Microsoft Defender 防病毒 Microsoft 云提供的保护。 [ (返回到表) ](#ref2)

2. <span id="fn2" />在Windows 10和Windows 11中，Microsoft Defender 防病毒是一个无需安装或部署其他客户端或服务即可使用的组件。 当卸载第三方防病毒产品或产品过期时，将自动启用 (产品[，Windows Server 2016) 。](microsoft-defender-antivirus-on-windows-server.md) 因此，不需要传统部署。 此处的部署是指确保Microsoft Defender 防病毒组件在终结点或服务器上可用并启用。 [ (返回到表) ](#ref2)

3. <span id="fn3" />本库中的配置功能和保护（包括配置产品和保护更新[）Microsoft Defender 防病毒功能部分](configure-notifications-microsoft-defender-antivirus.md)进一步介绍。 [ (返回到表) ](#ref2)

## <a name="in-this-section"></a>本节内容

主题 | 说明
---|---
[部署和启用Microsoft Defender 防病毒保护](deploy-microsoft-defender-antivirus.md) | 虽然客户端作为 Windows 10 或 Windows 11 的核心部分安装，但传统部署不适用，但仍需要在终结点上启用具有 Microsoft Endpoint Configuration Manager、Microsoft Intune 或组策略对象的客户端。
[管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md) | 更新客户端有两个部分Microsoft Defender 防病毒：更新终结点上的客户端 (产品更新) ，以及更新安全智能 (保护) 。 可以通过多种方式更新安全智能，Microsoft Endpoint Configuration Manager、组策略、PowerShell 和 WMI。
[监视并报告Microsoft Defender 防病毒保护](report-monitor-microsoft-defender-antivirus.md) | 通过使用 Windows 事件日志) ，可以使用适用于 Microsoft Operations Management Suite 的 Microsoft Intune、Microsoft Endpoint Configuration Manager、Update Compliance 外接程序或第三方 SIEM 产品 (来监视保护状态并创建有关终结点保护的报告。