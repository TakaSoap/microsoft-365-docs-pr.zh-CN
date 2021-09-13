---
title: 使用组策略对象管理 Microsoft Defender for Endpoint
description: 了解如何使用组策略对象管理 Microsoft Defender for Endpoint
keywords: 迁移后， 管理， 操作， 维护， 利用率， PowerShell， Microsoft Defender for Endpoint， edr
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
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: b731dcbeaf49b2c1f6bfbfacde17f7643c8faf4d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59197278"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>使用组策略对象管理 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

> [!NOTE]
> 我们建议使用[Microsoft Endpoint Manager](/mem)管理组织对也称为终结点 (的设备的威胁防护) 。 Endpoint Manager包括[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)和[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)。 **[详细了解Endpoint Manager。](/mem/endpoint-manager-overview)**

可以使用域服务中的组策略Azure Active Directory管理 Microsoft Defender for Endpoint 中的某些设置。

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>使用组策略对象配置 Microsoft Defender for Endpoint

下表列出了可以使用组策略对象配置 Microsoft Defender for Endpoint 时可执行的各种任务。

<br>

****

|任务|了解详细信息的资源|
|---|---|
|**管理用户和计算机对象的设置** <p> *自定义内置组策略对象，或创建自定义组策略对象和组织单位以满足组织需求。*|[管理域服务托管Azure Active Directory中的组策略](/azure/active-directory-domain-services/manage-group-policy)|
|**配置Microsoft Defender 防病毒** <p> *在组织设备上配置&功能，包括策略设置、排除、修正和计划扫描 (也称为终结点) 。*|[使用组策略设置配置和管理Microsoft Defender 防病毒](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <p> [使用组策略启用云保护](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)|
|**管理组织的攻击面减少规则** <p> *自定义攻击面减少规则，&文件夹中的文件，或者向显示在用户设备上的通知警报添加自定义文本。*|[使用组策略对象自定义攻击面减少规则](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders)|
|**管理 Exploit Protection 设置** <p> *你可以自定义 Exploit Protection 设置、导入配置文件，然后使用组策略部署该配置文件。*|[自定义 Exploit Protection 设置](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <p> [导入、导出和部署 Exploit Protection 配置](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml) <p> [使用组策略分发配置](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)|
|**启用网络** 保护以帮助防止员工使用 Internet 上恶意内容的应用 <p> *我们建议在 [测试环境中首先](/microsoft-365/security/defender-endpoint/evaluate-network-protection) 使用审核模式进行网络保护，以查看在推出之前哪些应用将被阻止。*|[使用组策略打开网络保护](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)|
|**配置受控文件夹访问权限** 以防范勒索软件 <p> *[受控文件夹访问权限](/microsoft-365/security/defender-endpoint/controlled-folders) 也称为反反somware保护。*|[使用组策略启用受控文件夹访问权限](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy)|
|**配置Microsoft Defender SmartScreen** 以抵御 Internet 上的恶意站点和文件。|[使用Microsoft Defender SmartScreen策略为 MDM (配置) 组策略和移动设备管理](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)|
|**配置加密和 BitLocker** 以保护组织中运行加密Windows|[BitLocker 组策略设置](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings)|
|**配置 Microsoft Defender Credential Guard** 以防止凭据盗窃攻击|[使用Windows Defender启用 Credential Guard](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy)|
|||

## <a name="configure-your-microsoft-365-defender-portal"></a>配置Microsoft 365 Defender门户

如果尚未配置，请配置 Microsoft 365 Defender 门户以查看警报、配置威胁防护功能，并查看有关组织整体安全状况的详细信息。 请参阅[Microsoft 365 Defender。](microsoft-defender-security-center.md) 还可以配置最终用户是否可以在 web 门户中查看这些功能Microsoft 365 Defender功能。

- [概述Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use)
- [终结点保护：Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>后续步骤

- [获取威胁和漏洞管理的概述](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [访问 Microsoft 365 Defender门户安全操作仪表板](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
- [使用 Intune 管理 Microsoft Defender for Endpoint](manage-atp-post-migration-intune.md)
