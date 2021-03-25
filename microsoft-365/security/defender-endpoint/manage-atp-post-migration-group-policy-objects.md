---
title: 使用组策略对象管理 Microsoft Defender for Endpoint
description: 了解如何使用组策略对象管理 Microsoft Defender for Endpoint
keywords: 迁移后， 管理， 操作， 维护， 利用率， PowerShell， windows defender 高级威胁防护， atp， edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 6d10bd932d9414f1460076d3fe7ca8dbed8041a6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185647"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>使用组策略对象管理 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> 我们建议使用 [Microsoft Endpoint Manager](https://docs.microsoft.com/mem) 来管理组织针对设备的威胁防护功能 (也称为终结点) 。 Endpoint Manager 包括[Microsoft Intune 和](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) [Microsoft Endpoint Configuration Manager。](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) **[了解有关 Endpoint Manager 的更多信息](https://docs.microsoft.com/mem/endpoint-manager-overview)**。 

可以使用 Azure Active Directory 域服务中的组策略对象来管理 Microsoft Defender for Endpoint 中的某些设置。

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>使用组策略对象配置 Microsoft Defender for Endpoint

下表列出了可以使用组策略对象配置 Microsoft Defender for Endpoint 时可执行的各种任务。

|任务  |了解详细信息的资源  |
|---------|---------|
|**管理用户和计算机对象的设置** <br/><br/>*自定义内置组策略对象，或创建自定义组策略对象和组织单位以满足组织需求。*     |[管理 Azure Active Directory 域服务托管域中的组策略](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)   |
|**配置 Microsoft Defender 防病毒** <br/><br/>*在组织设备上配置&功能，包括策略设置、排除、修正和计划扫描 (也称为终结点) 。*   |[使用组策略设置配置和管理 Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[使用组策略启用云保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**管理组织的攻击面减少规则** <br/><br/>*自定义攻击面减少规则，&文件夹中的文件，或者向显示在用户设备上的通知警报添加自定义文本。* |[使用组策略对象自定义攻击面减少规则](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**管理 Exploit Protection 设置**<br/><br/>*你可以自定义 Exploit Protection 设置、导入配置文件，然后使用组策略部署该配置文件。*  |[自定义 Exploit Protection 设置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[导入、导出和部署 Exploit Protection 配置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[使用组策略分发配置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**启用网络** 保护以帮助防止员工使用 Internet 上恶意内容的应用 <br/><br/>*我们建议在 [测试环境中首先](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) 使用审核模式进行网络保护，以查看在推出之前哪些应用将被阻止。* |[使用组策略打开网络保护](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**配置受控文件夹访问权限** 以防范勒索软件 <br/><br/>*[受控文件夹访问权限](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) 也称为反反somware保护。*  |[使用组策略启用受控文件夹访问权限](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**配置 Microsoft Defender SmartScreen** 以防范 Internet 上的恶意站点和文件。  |[使用组策略配置 Microsoft Defender SmartScreen 组策略和移动设备 (MDM) 设置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**配置加密和 BitLocker** 以保护运行 Windows 的组织设备上的信息 |[BitLocker 组策略设置](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**配置 Microsoft Defender Credential Guard** 以防止凭据盗窃攻击 |[使用Windows Defender启用 Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>配置 Microsoft Defender 安全中心

如果尚未配置，请配置 Microsoft **Defender** 安全中心 () 以查看警报、配置威胁防护功能以及查看有关组织整体安全状况 [https://securitycenter.windows.com](https://securitycenter.windows.com) 的详细信息。 

还可以配置最终用户是否可以在 Microsoft Defender 安全中心看到的功能以及这些功能。

- [Microsoft Defender 安全中心概述](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [终结点保护：Microsoft Defender 安全中心](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>后续步骤

- [获取威胁和漏洞管理的概述](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [访问 Microsoft Defender 安全中心安全操作仪表板](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [使用 Intune 管理 Microsoft Defender for Endpoint](manage-atp-post-migration-intune.md)
