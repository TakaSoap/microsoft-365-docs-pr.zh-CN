---
title: 部署、管理和报告 Microsoft Defender 防病毒
description: 可以使用 Intune、Microsoft Endpoint Configuration Manager、组策略、PowerShell 或 WMI 部署和管理 Microsoft Defender 防病毒
keywords: 部署， 管理， 更新， 保护， Microsoft Defender 防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b44bc529a14d12d2be49854c31a4ea11cdabc7d1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764839"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>部署、管理和报告 Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以通过多种方式部署、管理和报告 Microsoft Defender 防病毒。

由于 Microsoft Defender 防病毒客户端是作为 Windows 10 的核心部分安装的，因此客户端到终结点的传统部署不适用。

但是，在大多数情况下，你仍然需要使用 Microsoft Intune、Microsoft Endpoint Configuration Manager、Azure Defender 或组策略对象在终结点上启用保护服务，如下表所述。

你还将看到以下其他链接：

- 管理 Microsoft Defender 防病毒保护，包括管理产品和保护更新
- Microsoft Defender 防病毒保护报告

> [!IMPORTANT]
> 在大多数情况下，如果 Windows 10 找到另一个正在运行且最新的防病毒产品，它将禁用 Microsoft Defender 防病毒。 必须先禁用或卸载第三方防病毒产品，Microsoft Defender 防病毒才能正常运行。 如果重新启用或安装第三方防病毒产品，Windows 10 将自动禁用 Microsoft Defender 防病毒。

工具|部署选项 (<a href="#fn2" id="ref2">2</a>) |管理选项 ([3](#fn3))  (网络范围的配置和策略或) |报告选项  
---|---|---|---  
Microsoft Intune|[在 Intune 中添加终结点保护设置](/intune/endpoint-protection-configure)|[在 Intune 中配置设备限制设置](/intune/device-restrictions-configure)| [使用 Intune 控制台管理设备](/intune/device-management)  
Microsoft Endpoint Manager ([1](#fn1)) |使用[Endpoint Protection 点站点系统角色，][][并使用自定义客户端设置启用 Endpoint Protection][]|使用 [默认和自定义的反恶意软件策略][] 和 [客户端管理][]|使用默认的[Configuration Manager 监视工作区][][和电子邮件警报][]  
已加入域 (组策略和 Active Directory) |使用组策略对象部署配置更改并确保已启用 Microsoft Defender 防病毒。|使用 GPO (组策略) [配置 Microsoft Defender][] 防病毒的更新选项和配置 Windows Defender [功能][]|终结点报告不适用于组策略。 可以生成组策略 [列表，以确定是否未应用任何设置或策略][]
PowerShell|使用组策略、Microsoft Endpoint Configuration Manager 或手动在个别终结点上部署。|使用 [Defender 模块中提供的 Set-MpPreference] 和 [Update-MpSignature] cmdlet。|使用 Defender [模块中可用的相应 Get- cmdlet][]
Windows Management Instrumentation|使用组策略、Microsoft Endpoint Configuration Manager 或手动在个别终结点上部署。|使用 [MSFT_MpPreference 的 Set][] 方法和 MSFT_MpSignature [类的 Update 方法][]|使用[MSFT_MpComputerStatus][] [WMIv2][]提供程序中的关联类的 Windows Defender 和 get 方法
Microsoft Azure|在 Azure 门户中部署适用于 Azure 的 Microsoft 反恶意软件，Visual Studio[虚拟机配置或 Azure PowerShell cmdlet。](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios) 还可以在 [Azure Defender 中安装终结点保护*](/azure/security-center/security-center-install-endpoint-protection)|使用 [Azure PowerShell cmdlet](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) 为虚拟机和云服务配置 Microsoft 反恶意软件或使用 [代码示例](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|使用 [Microsoft Antimalware for Virtual Machines and Cloud Services 和 Azure PowerShell cmdlet 启用](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) 监视。 还可以查看 Azure Active Directory 中的使用情况报告以确定可疑活动，包括[][]可能受感染的设备报告，并配置 SIEM 工具以报告[Microsoft Defender][]防病毒事件，将该工具添加为 AAD 中的应用。

1. <span id="fn1" />Microsoft Endpoint Manager (Current Branch) 和 System Center 2012 Configuration Manager 之间的某些功能和功能的可用性不同，尤其是与云保护相关。 在此库中，我们侧重于 Windows 10、Windows Server 2016 和 Microsoft Endpoint Manager (Current Branch) 。 有关 [描述主要差异的](cloud-protection-microsoft-defender-antivirus.md) 表，请参阅在 Microsoft Defender 防病毒中使用 Microsoft 云提供的保护。 [ (返回到表) ](#ref2)
  
2.  <span id="fn2" />在 Windows 10 中，Microsoft Defender 防病毒是一个无需安装或部署其他客户端或服务即可使用的组件。 当卸载第三方防病毒产品或产品过期时，将自动启用 ([Windows Server 2016](microsoft-defender-antivirus-on-windows-server.md)) 。 因此，不需要传统部署。 此处的部署是指确保 Microsoft Defender 防病毒组件在终结点或服务器上可用并启用。 [ (返回到表) ](#ref2)

3. <span id="fn3" />本库中的配置 [Microsoft Defender](configure-notifications-microsoft-defender-antivirus.md) 防病毒功能部分进一步介绍了功能和保护的配置，包括配置产品和保护更新。 [ (返回到表) ](#ref2)

[终结点保护点站点系统角色]: /configmgr/protect/deploy-use/endpoint-protection-site-role
[默认和自定义的反恶意软件策略]:  /configmgr/protect/deploy-use/endpoint-antimalware-policies
[客户端管理]:  /configmgr/core/clients/manage/manage-clients
[使用自定义客户端设置启用 Endpoint Protection]:  /configmgr/protect/deploy-use/endpoint-protection-configure-client
[Configuration Manager 监视工作区]:  /configmgr/protect/deploy-use/monitor-endpoint-protection
[电子邮件警报]:  /configmgr/protect/deploy-use/endpoint-configure-alerts
[Deploy the Microsoft Intune client to endpoints]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune
[custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection
 [custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection 
[manage tasks]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#choose-management-tasks-for-endpoint-protection
[Monitor endpoint protection in the Microsoft Intune administration console]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#monitor-endpoint-protection
[类的 set 方法MSFT_MpPreference类]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[MSFT_MpSignature 的 Update 方法]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[MSFT_MpComputerStatus]:  /previous-versions/windows/desktop/defender/msft-mpcomputerstatus
[Windows Defender WMIv2 提供程序]: /previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal
[Set-MpPreference]:  https://technet.microsoft.com/itpro/powershell/windows/defender/set-mppreference.md
[Update-MpSignature]: /powershell/module/defender/update-mpsignature
[Get- Defender 模块中可用的 cmdlet]: /powershell/module/defender/
[配置 Microsoft Defender 防病毒的更新选项]: manage-updates-baselines-microsoft-defender-antivirus.md
[配置Windows Defender功能]: configure-microsoft-defender-antivirus-features.md
[用于确定是否未应用任何设置或策略的组策略]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[可能受感染的设备]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[Microsoft Defender 防病毒事件]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>本节内容

主题 | 说明
---|---
[部署和启用 Microsoft Defender 防病毒保护](deploy-microsoft-defender-antivirus.md) | 虽然客户端是作为 Windows 10 的核心部分安装的，但传统部署不适用，你仍然需要使用 Microsoft Endpoint Configuration Manager、Microsoft Intune 或组策略对象在终结点上启用客户端。 
[管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md) | 更新 Microsoft Defender 防病毒有两个部分：更新终结点上的客户端 (产品更新) ，以及更新安全智能 (保护) 。 可以使用 Microsoft Endpoint Configuration Manager、组策略、PowerShell 和 WMI 以多种方式更新安全智能。
[监视并报告 Microsoft Defender 防病毒保护](report-monitor-microsoft-defender-antivirus.md) | 通过使用 Windows 事件日志) ，可以使用 Microsoft Intune、Microsoft Endpoint Configuration Manager、Microsoft Operations Management Suite 的更新合规性外接程序或第三方 SIEM 产品 (来监视保护状态并创建有关终结点保护的报告。