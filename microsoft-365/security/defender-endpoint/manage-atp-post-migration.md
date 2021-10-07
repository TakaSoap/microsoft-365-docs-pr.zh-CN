---
title: 迁移后管理 Microsoft Defender for Endpoint
description: 现在，你已切换到 Microsoft Defender for Endpoint，下一步是管理威胁防护功能
keywords: 迁移后， 管理， 操作， 维护， 利用率， Microsoft Defender for Endpoint， edr
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: conceptual
ms.date: 09/23/2021
ms.reviewer: chventou
ms.openlocfilehash: 1b0dfbb7996cde595fc4d133f1a946e8692d8941
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206895"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>管理 Microsoft Defender for Endpoint，迁移后

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

从以前的终结点保护和防病毒解决方案移动到 Microsoft Defender for Endpoint 后，下一步是管理特性和功能。 我们建议使用[Microsoft Endpoint Manager](/mem/endpoint-manager-overview)（包括 Microsoft Intune[](/mem/intune/fundamentals/what-is-intune)和[Microsoft Endpoint Configuration Manager）](/mem/configmgr/core/understand/introduction)来管理组织的设备和安全设置。 但是，您可以使用其他工具/方法，如域服务中的组[Azure Active Directory对象](/azure/active-directory-domain-services/manage-group-policy)。

下表列出了可以使用的各种工具/方法，以及用于了解更多信息的链接。

<br/><br/>

|工具/方法|说明|
|---|---|
|**[漏洞管理门户中的威胁](/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)**[和Microsoft 365 Defender](https://security.microsoft.com/)仪表板见解|威胁& 漏洞管理仪表板提供了可操作的信息，安全运营团队可以使用这些信息减少曝光并改进组织的安全状况。 <br/><br/> 请参阅[威胁& 漏洞管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)[和威胁Microsoft 365 Defender。](/microsoft-365/security/defender-endpoint/use)|
|**[Microsoft Intune (](/mem/intune/fundamentals/what-is-intune)** 推荐) |Microsoft Intune (Intune) 是[Microsoft Endpoint Manager](/mem/endpoint-manager-overview)的一个组件，它专注于移动设备管理 (MDM) 和移动设备管理 (MAM) 。 通过 Intune，你可以控制组织的设备的使用方式，包括移动电话、平板电脑和笔记本电脑。 还可以配置特定策略以控制应用程序。 <br/><br/> 请参阅[使用 Intune 管理 Microsoft Defender for Endpoint。](manage-atp-post-migration-intune.md)|
|**[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)**|Microsoft Endpoint Manager (Configuration Manager) ，以前称为 System Center Configuration Manager，是 Microsoft Endpoint Manager 的[一Microsoft Endpoint Manager。](/mem/endpoint-manager-overview) Configuration Manager 是管理用户、设备和软件的强大工具。 <br/><br/> 请参阅[使用 Configuration Manager 管理 Microsoft Defender for Endpoint。](manage-atp-post-migration-configuration-manager.md)|
|**[Azure Active Directory域中的组策略对象](/azure/active-directory-domain-services/manage-group-policy)**|[Azure Active Directory域服务](/azure/active-directory-domain-services/overview)包括用户和设备内置的组策略对象。 您可以根据您的环境需要自定义内置组策略对象，并创建自定义组策略对象和组织单位以 (OUS) 。 <br/><br/> 请参阅[使用组策略对象管理 Microsoft Defender for Endpoint。](manage-atp-post-migration-group-policy-objects.md)|
|**[PowerShell、WMI 和 MPCmdRun.exe](manage-atp-post-migration-other-tools.md)**|*我们建议使用 Microsoft Endpoint Manager (包括 Intune 和 Configuration Manager) 来管理组织设备上的威胁防护功能。但是，你可以配置某些设置，例如Microsoft Defender 防病毒 PowerShell、WMI 或 MPCmdRun.exe 工具 (终结点上的) 设置。* <br/><br/> 可以使用 PowerShell 管理Microsoft Defender 防病毒、Exploit Protection 和攻击面减少规则。 请参阅[使用 PowerShell 配置 Microsoft Defender for Endpoint。](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell) <br/><br/> 可以使用 Windows Management Instrumentation (WMI) 来管理Microsoft Defender 防病毒和排除项。 请参阅[使用 WMI 配置 Microsoft Defender for Endpoint。](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) <br/><br/> 您可以使用 Microsoft 恶意软件防护Command-Line实用程序 (MPCmdRun.exe) 管理 Microsoft Defender 防病毒 和排除项，以及验证网络和云之间的连接。 请参阅 [配置 Microsoft Defender for Endpoint with MPCmdRun.exe](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe)。|


## <a name="see-also"></a>另请参阅

- [解决 Microsoft Defender for Endpoint 中的误报/漏报](defender-endpoint-false-positives-negatives.md)
