---
title: 使用 Intune 管理 Microsoft Defender for Endpoint
description: 了解如何使用 Intune 管理 Microsoft Defender for Endpoint
keywords: 迁移后， 管理， 操作， 维护， 利用率， intune， Microsoft Defender for Endpoint， edr
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
ms.topic: article
ms.date: 11/29/2021
ms.reviewer: chventou
ms.openlocfilehash: a8dafd631f8c4ab725003ba2aa5d212abc9de8e3
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2021
ms.locfileid: "61221449"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>使用 Intune 管理 Microsoft Defender for Endpoint

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

我们建议使用[Microsoft Endpoint Manager](/mem)，其中包括 Microsoft Intune (Intune) 来管理组织对也称为终结点 (的设备的威胁防护) 。 [详细了解Endpoint Manager。](/mem/endpoint-manager-overview)

本文介绍了如何在 Intune 中查找适用于终结点的 Microsoft Defender 设置，并列出了可以执行的各种任务。

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>在 Intune 中查找适用于终结点的 Microsoft Defender 设置

> [!IMPORTANT]
> 你必须在 Intune 中分配全局管理员或服务管理员角色，才能配置本文中所述的设置。 若要了解更多信息，请参阅 **[Intune (管理员) 。](/mem/intune/fundamentals/users-add#types-of-administrators)**

1. 转到 Azure 门户 [https://portal.azure.com](https://portal.azure.com) () 并登录。

2. 在 **"Azure 服务"** 下，选择 **"Intune"。**

3. 在左侧的导航窗格中，选择"**设备** 配置"，然后在 **"管理"** 下选择"配置文件 **"。**

4. 选择现有配置文件，或新建一个配置文件。

> [!TIP]
> 需要帮助？ 请参阅 **[将 Microsoft Defender for Endpoint 与 Intune 一同使用](/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**。

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>使用 Intune 配置 Microsoft Defender for Endpoint

下表列出了可以使用 Intune 配置 Microsoft Defender for Endpoint 时可执行的各种任务。 不必一次配置所有内容;选择一个任务，读取相应的资源，然后继续。

<br/><br/>

|任务|了解详细信息的资源|
|---|---|
|**使用 Intune 管理** 组织设备，以保护这些设备和存储于这些设备的数据|[使用 Microsoft Intune 保护设备](/mem/intune/protect/device-protect)|
|**将 Microsoft Defender for Endpoint 与 Intune** 集成为移动威胁防护解决方案 <br/>*(Android 设备或运行 Windows 10 或 Windows 11)*|[使用 Intune 中的条件访问强制执行 Microsoft Defender for Endpoint 的合规性](/mem/intune/protect/advanced-threat-protection)|
|**使用条件访问** 控制可以连接到电子邮件和公司资源的设备和应用|[在 Microsoft Defender for Endpoint 中配置条件访问](/microsoft-365/security/defender-endpoint/configure-conditional-access)|
|**使用Microsoft Defender 防病毒配置** 服务提供程序和策略 CSP ([配置)](/windows/client-management/mdm/policy-configuration-service-provider)|[设备限制：Microsoft Defender 防病毒](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus) <br/><br/> [策略 CSP - Microsoft Defender for Endpoint](/windows/client-management/mdm/policy-csp-defender)|
|**如有必要，请为用户指定Microsoft Defender 防病毒** <br/><br/> *通常，你无需应用排除项。Microsoft Defender 防病毒包括许多基于已知操作系统行为和典型管理文件（如在企业管理、数据库管理和其他企业方案中使用的文件）的自动排除项。*|[病毒扫描建议Enterprise当前支持的版本的病毒扫描的计算机Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers) <br/><br/> [设备限制：Microsoft Defender 防病毒和Windows 10设备Windows 11排除](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/> [在 Microsoft Defender 防病毒 2019 Windows Server 2016 2022 上配置排除项](/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|**配置攻击面减少规则** ，以针对经常被攻击者滥用的软件行为 <br/><br/> *在审核模式下配置攻击面减少 [](/microsoft-365/security/defender-endpoint/audit-windows-defender)规则， (至少一周，最多两) 。可以使用获取模板Power BI ([状态) ，](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)然后在准备就绪后将这些规则设置为活动模式。*|[Microsoft Defender for Endpoint 中的审核模式](/microsoft-365/security/defender-endpoint/audit-windows-defender) <br/><br/> [终结点保护：攻击面减少](/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction) <br/><br/> [详细了解攻击面减少规则](/microsoft-365/security/defender-endpoint/attack-surface-reduction) <br/><br/> [Tech Community博客文章：验证攻击面减少规则 - 第 1 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420)|
|**配置网络筛选** 以阻止从任何应用到 IP 地址或信誉较低的域的出站连接  <br/><br/> *网络筛选也称为网络 [保护](/microsoft-365/security/defender-endpoint/network-protection)。* <br/><br/> *确保Windows 10 Windows 11已安装最新的 [反恶意软件平台](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)更新。*|[终结点保护：网络筛选](/mem/intune/protect/endpoint-protection-windows-10#network-filtering) <br/><br/> [在事件查看器中查看Windows保护事件](/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer)|
|**配置受控文件夹访问权限** 以防范勒索软件 <br/><br/> *[受控文件夹访问权限](/microsoft-365/security/defender-endpoint/controlled-folders) 也称为反反somware保护。*|[终结点保护：受控文件夹访问权限](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/> [在 Intune 中启用受控文件夹访问权限](/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)|
|**配置 Exploit Protection** 以保护组织设备免受使用攻击传播和感染其他设备的恶意软件的攻击 <br/><br/> *[Exploit Protection](/microsoft-365/security/defender-endpoint/exploit-protection) 也称为攻击防护。*|[终结点保护：Microsoft Defender 攻击防护](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/> [在 Intune 中启用 Exploit Protection](/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune)|
|**配置Microsoft Defender SmartScreen** 以抵御 Internet 上的恶意站点和文件。 <br/><br/> *Microsoft Edge应安装在组织的设备上。若要保护 Google Chrome 和 FireFox 浏览器，请配置 Exploit Protection。*|[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/> [设备限制：Microsoft Defender SmartScreen](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen) <br/><br/> [用于管理 Intune 中的 SmartScreen 的策略设置](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)|
|**配置 Microsoft Defender 防火墙** 以阻止未经授权的网络流量流入或流出组织的设备|[终结点保护：Microsoft Defender 防火墙](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [高级安全 Microsoft Defender 防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)|
|**配置加密和 BitLocker** 以保护组织中运行加密Windows|[终结点保护：Windows加密](/mem/intune/protect/endpoint-protection-windows-10#windows-encryption) <br/><br/> [适用于 Windows 10 和 Windows 11 设备的 BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview)|
|**配置 Microsoft Defender Credential Guard** 以防止凭据盗窃攻击|有关 Windows 10、Windows 11、Windows Server 2016 和 Windows Server 2019 以及 Windows Server 2022 的信息，请参阅 Endpoint [protection： Microsoft Defender Credential Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/> 对于 Windows 7 SP1、Windows Server 2008 R2 SP1、Windows 8.1 和 Windows Server 2012 R2，请参阅缓解哈希传递 (PtH) 攻击和其他凭据盗窃（版本 1 和[2）](https://www.microsoft.com/download/details.aspx?id=36036)|
|**配置 Microsoft Defender 应用程序控制** 以选择在组织设备上审核还是信任应用 <br/><br/> *Microsoft Defender 应用程序控制也称为 [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)。*|[使用 Microsoft Defender 应用程序控制策略部署Microsoft Intune](/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune) <br/><br/> [终结点保护：Microsoft Defender 应用程序控制](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control) <br/><br/> [AppLocker CSP](/windows/client-management/mdm/applocker-csp)|
|**配置设备控制和 USB 外围设备访问** 以帮助防止未经授权的外围设备中的威胁损害你的设备|[使用 Microsoft Defender for Endpoint 和 Intune 控制 USB 设备和其他可移动媒体](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)|

## <a name="configure-your-microsoft-365-defender-portal"></a>配置Microsoft 365 Defender门户

如果尚未配置，请配置 Microsoft 365 Defender 门户以查看警报、配置威胁防护功能，并查看有关组织的整体安全状况的详细信息。 请参阅[Microsoft 365 Defender。](microsoft-defender-security-center.md) 还可以配置最终用户是否可以在网站门户中查看这些功能Microsoft 365 Defender功能。

- [概述Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use)
- [终结点保护：Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>后续步骤

- [获取威胁和漏洞管理的概述](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [访问 Microsoft 365 Defender门户安全操作仪表板](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
