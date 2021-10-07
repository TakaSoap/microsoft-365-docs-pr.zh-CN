---
title: '威胁防护 (Windows 10) '
description: Microsoft Defender for Endpoint 是一个统一的平台，可用于预防性保护、入侵后检测、自动调查和响应。
keywords: 威胁防护， 适用于终结点的 Microsoft Defender， 攻击面减少， 下一代保护， 终结点检测和响应， 自动调查和响应， Microsoft 威胁专家， Microsoft 设备安全分数， 高级搜寻， 网络威胁搜寻， Web 威胁防护
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 6ada32650a01f3303a9c3c9011f5465dab5f5184
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206873"
---
# <a name="threat-protection"></a>威胁防护

[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) 是一个统一的平台，可用于预防性保护、入侵后检测、自动调查和响应。 Defender for Endpoint 可保护终结点免受网络威胁，检测高级攻击和数据泄露，自动执行安全事件，并改进安全状况。

> [!TIP]
> 使用户可以轻松访问云服务和本地应用程序，并启用所有设备的新式管理功能。 有关详细信息，请参阅保护 [远程工作人员](/enterprise-mobility-security/remote-work/)。 

<center><h2>Microsoft Defender for Endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><b>威胁& 漏洞管理</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><b>攻击面减少</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <b>下一代保护</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <b>终结点检测和响应</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <b>自动调查和修正</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <b>Microsoft 威胁专家</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>集中配置和管理，API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4obJq]

**[威胁& 漏洞管理](next-gen-threat-and-vuln-mgt.md)**<br>
此内置功能使用改变格局的基于风险的方法，以实现对终结点漏洞和错误配置的发现、优先级确定和修复。

- [威胁& 漏洞管理概述](next-gen-threat-and-vuln-mgt.md)
- [入门](tvm-prerequisites.md)
- [访问安全状态](tvm-dashboard-insights.md)
- [提升安全性并降低风险](tvm-security-recommendation.md)
- [了解设备上的漏洞](tvm-software-inventory.md)

<a name="asr"></a>

**[攻击面减少](overview-attack-surface-reduction.md)**<br>
攻击面减少功能集在堆栈中提供第一道防线。 通过确保正确设置配置设置并应用攻击缓解技术，这些功能集可抵御攻击和利用。

- [基于硬件的隔离](overview-hardware-based-isolation.md)
- [应用程序控制](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [设备控制](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [漏洞保护](exploit-protection.md)
- [网络保护](network-protection.md)[、Web 保护](web-protection-overview.md)
- [受控文件夹访问](controlled-folders.md)
- [网络防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [攻击面减少规则](attack-surface-reduction.md)

<a name="ngp"></a>

**[下一代保护](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
为了进一步巩固你的网络的安全外围，Microsoft Defender for Endpoint 使用下一代保护来捕获所有类型的新兴威胁。

- [行为监视](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [基于云的保护](/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [机器学习](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [URL 保护](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [自动沙盒服务](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

**[终结点检测和响应](overview-endpoint-detection-response.md)**<br>
终结点检测和响应功能已到位，以检测、调查和响应入侵尝试和主动泄露。 借助高级搜寻，你拥有基于查询的威胁搜寻工具，可让你主动发现漏洞并创建自定义检测。

- [警告](alerts-queue.md)
- [历史终结点数据](investigate-machines.md#timeline)
- [响应业务流程](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [取证集合](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [威胁智能](threat-indicator-concepts.md)
- [高级爆炸和分析服务](respond-file-alerts.md#deep-analysis)
- [高级搜寻](advanced-hunting-overview.md)
    - [自定义检测](overview-custom-detections.md)

<a name="ai"></a>

**[自动调查和修正](automated-investigations.md)**<br>
除了快速响应高级攻击之外，Microsoft Defender for Endpoint 还提供自动调查和修正功能，可帮助以分钟数为比例减少警报量。

- [自动调查和修正](automated-investigations.md)
- [查看自动化调查的详细信息和结果](auto-investigation-action-center.md)
- [查看和批准修正操作](manage-auto-investigation.md)

<a name="mte"></a>

**[Microsoft 威胁专家](microsoft-threat-experts.md)**<br>
Microsoft Defender for Endpoint 的新托管威胁搜寻服务提供主动搜寻、优先顺序和其他上下文和见解。 Microsoft 威胁专家使安全操作中心 (SOC) 快速准确地识别和响应威胁。

- [目标攻击通知](microsoft-threat-experts.md)
- [专家按需](microsoft-threat-experts.md)
- [配置你的Microsoft 365 Defender搜寻服务](configure-microsoft-threat-experts.md)

<a name="apis"></a>

**[集中配置和管理，API](management-apis.md)**<br>
将 Microsoft Defender for Endpoint 集成到现有工作流中。
- [载入](onboard-configure.md)
- [API 和 SIEM 集成](configure-siem.md)
- [公开的 API](apis-intro.md)
- [基于角色的访问控制 (RBAC)](rbac.md)
- [报告和趋势](threat-protection-reports.md)

<a name="integration"></a>
**[与 Microsoft 解决方案集成](threat-protection-integration.md)** <br>
 Microsoft Defender for Endpoint 直接与各种 Microsoft 解决方案集成，包括：
- Intune
- Microsoft Defender for Office 365
- Microsoft Defender for Identity
- Azure Defender
- Skype for Business
- Microsoft Cloud App Security

<a name="mtp"></a>
**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**<br>
 借助 Microsoft 365 Defender，Microsoft Defender for Endpoint 和各种 Microsoft 安全解决方案形成统一的攻破前和入侵后企业防御套件，可跨终结点、标识、电子邮件和应用程序进行本机集成，以检测、阻止、调查和自动响应复杂的攻击。
