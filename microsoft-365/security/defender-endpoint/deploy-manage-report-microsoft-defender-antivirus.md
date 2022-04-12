---
title: 部署、管理和报告Microsoft Defender 防病毒
description: 可以使用 Intune、Microsoft Endpoint Configuration Manager、组策略、PowerShell 或 WMI 部署和管理Microsoft Defender 防病毒
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
ms.openlocfilehash: 4e0d249f7805c47be55ec42f3362ca1952c20ca3
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788493"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>部署、管理和报告Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒 

**平台**
- Windows

可以通过多种方式部署、管理和报告Microsoft Defender 防病毒。

由于Microsoft Defender 防病毒客户端安装为Windows 10和Windows 11的核心部分，因此不应用将客户端传统部署到终结点。

但是，在大多数情况下，你仍需要在终结点上使用Microsoft Intune、Microsoft Endpoint Configuration Manager、Microsoft Defender for Cloud或组策略对象启用保护服务，如下所述在下表中。

你还将看到以下附加链接：

- 管理Microsoft Defender 防病毒保护，包括管理产品和保护更新
- 有关Microsoft Defender 防病毒保护的报告

> [!IMPORTANT]
> 在大多数情况下，Windows 10或Windows 11会禁用Microsoft Defender 防病毒，如果它发现另一个防病毒产品正在运行和更新。 必须先禁用或卸载第三方防病毒产品，然后Microsoft Defender 防病毒才能正常工作。 如果重新启用或安装第三方防病毒产品，则Windows 10或Windows 11会自动禁用Microsoft Defender 防病毒。

工具|部署选项 (<a href="#fn2" id="ref2">2</a>) |管理选项 (网络范围的配置和策略或基线部署)  ([3](#fn3)) |报告选项
---|---|---|---
Microsoft Intune|[在Intune中添加终结点保护设置](/intune/endpoint-protection-configure)|[在Intune中配置设备限制设置](/intune/device-restrictions-configure)| [使用Intune控制台管理设备](/intune/device-management)
Microsoft Endpoint Manager ([1](#fn1)) |使用 [Endpoint Protection 点站点系统角色][] 和 [使用自定义客户端设置启用Endpoint Protection][]|使用 [默认和自定义的反恶意软件策略][] 和 [客户端管理][]|使用默认 [Configuration Manager 监视工作区][] 和 [电子邮件警报][]
组策略和 Active Directory (已加入域的) |使用组策略对象部署配置更改并确保启用Microsoft Defender 防病毒。|使用组策略对象 (GPO) [配置Microsoft Defender 防病毒的更新选项][] 和 [配置 Windows Defender 功能][]|终结点报告不适用于组策略。 可以生成 [组策略的列表，以确定是否未应用任何设置或策略][]
PowerShell|在单个终结点上使用组策略、Microsoft Endpoint Configuration Manager或手动部署。|使用 Defender 模块中提供的 [Set-MpPreference] 和 [Update-MpSignature] cmdlet。|使用适当的 [Get- cmdlet 在 Defender 模块中可用][]
Windows Management Instrumentation|在单个终结点上使用组策略、Microsoft Endpoint Configuration Manager或手动部署。|使用 [MSFT_MpPreference 类的 Set 方法][] 和 [MSFT_MpSignature 类的更新方法][]|使用 [MSFT_MpComputerStatus][] 类和 [Windows Defender WMIv2 提供程序][] 中关联类的 get 方法
Microsoft Azure|[使用Visual Studio虚拟机配置或使用 Azure PowerShell cmdlet 在Azure 门户中部署适用于 Azure 的Microsoft Antimalware](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios)。 还可以[在 Microsoft Defender for Cloud* 中安装终结点保护](/azure/security-center/security-center-install-endpoint-protection)|使用 [Azure PowerShell cmdlet 为虚拟机和云服务配置Microsoft Antimalware](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)或[使用代码示例](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|将[Microsoft Antimalware用于虚拟机和云服务与Azure PowerShell cmdlet 一起](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)启用监视。 还可以查看Azure Active Directory中的使用情况报告以确定可疑活动，包括[可能受感染的设备][] 报告，并配置 SIEM 工具以报告 [Microsoft Defender 防病毒 事件][]，并将该工具添加为AAD中的应用。

1. <span id="fn1" />Microsoft Endpoint Manager (Current Branch) 和 2012 Configuration Manager System Center，某些函数和功能的可用性（尤其是与云提供的保护相关）的可用性有所不同。 在此库中，我们专注于Windows 10、Windows 11、Windows Server 2016和Microsoft Endpoint Manager (Current Branch) 。 有关描述主要差异的表，请参阅[Microsoft Defender 防病毒使用 Microsoft 云提供的保护](cloud-protection-microsoft-defender-antivirus.md)。 [ (返回表) ](#ref2)

2. <span id="fn2" />在Windows 10和Windows 11中，Microsoft Defender 防病毒是一个无需安装或部署其他客户端或服务即可使用的组件。 当第三方防病毒产品卸载或过期 (时，它将自动启用，但Windows Server 2016) 除外。 因此，不需要传统部署。 此处的部署是指确保Microsoft Defender 防病毒组件在终结点或服务器上可用并启用。 [ (返回表) ](#ref2)

3. <span id="fn3" />此库中的“[配置Microsoft Defender 防病毒功能](configure-notifications-microsoft-defender-antivirus.md)”部分进一步介绍了功能和保护的配置，包括配置产品和保护更新。 [ (返回表) ](#ref2)

## <a name="in-this-section"></a>本节内容

主题 | 说明
---|---
[部署并启用Microsoft Defender 防病毒保护](deploy-microsoft-defender-antivirus.md) | 虽然客户端安装为Windows 10或Windows 11的核心部分，但传统部署不适用，但仍需要在终结点上使用Microsoft Endpoint Configuration Manager、Microsoft Intune或组策略 对象。
[管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md) | 更新Microsoft Defender 防病毒有两个部分：更新终结点上的客户端 (产品更新) ，以及更新安全智能 (保护更新) 。 可以使用Microsoft Endpoint Configuration Manager、组策略、PowerShell 和 WMI 以多种方式更新安全智能。
[监视和报告Microsoft Defender 防病毒保护](report-monitor-microsoft-defender-antivirus.md) | 可以使用Microsoft Intune、Microsoft Endpoint Configuration Manager、Microsoft Operations Management Suite 的更新符合性外接程序或第三方 SIEM 产品 (，使用Windows事件日志) 监视保护状态并创建有关终结点保护的报告。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)
    
