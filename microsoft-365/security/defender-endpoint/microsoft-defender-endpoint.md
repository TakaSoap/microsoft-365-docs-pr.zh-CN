---
title: Microsoft Defender for Endpoint
description: Microsoft Defender for Endpoint 是一个企业终结点安全平台，可帮助抵御高级永久性威胁。
keywords: Microsoft Defender for Endpoint 简介， 适用于终结点的 Microsoft Defender 简介， 网络安全， 高级永久性威胁， 企业安全， 计算机行为传感器， 云安全， 分析， 威胁情报， 攻击面减少， 下一代保护， 自动调查和修正， Microsoft 威胁专家， 安全分数， 高级搜寻， Microsoft 365 Defender， 网络威胁搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 57d4506e32db5defe29f2d0e59f72bd4c1998310
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935925"
---
# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> 有关 Windows 10 企业版 Edition 特性和功能的信息，请参阅 Windows 10 企业版[edition](https://www.microsoft.com/WindowsForBusiness/buy)。

Microsoft Defender for Endpoint 是一个企业终结点安全平台，旨在帮助企业网络预防、检测、调查和响应高级威胁。
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Defender for Endpoint 使用内置于 Windows 10 和 Microsoft 强大的云服务中的以下技术组合：

-   **终结点行为** 传感器：这些传感器嵌入 Windows 10 中，可收集和处理来自操作系统的行为信号，并将此传感器数据发送到 Microsoft Defender for Endpoint 的私有、隔离云实例。


-   云 **安全** 分析：利用 Windows 生态系统中的大数据、设备学习以及独特的 Microsoft 光学系统、企业云产品 (（如 Office 365) ）和在线资产，行为信号将转换为对高级威胁的见解、检测和建议响应。

-   **威胁智能**：威胁智能由 Microsoft 情报人员、安全团队生成，由合作伙伴提供的威胁智能进行增强，使 Defender for Endpoint 能够识别攻击者工具、技术和过程，并可在收集的传感器数据中观察到它们时生成警报。

<center><h2>Microsoft Defender for Endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>威胁&漏洞管理</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>攻击面减少</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>下一代保护</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>终结点检测和响应</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>自动调查和修正</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft 威胁专家</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>集中配置和管理、API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365Defender</a></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - 了解 Defender for Endpoint 中的最新增强功能 [：Microsoft Defender for Endpoint 中的新增功能](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)。
> - Microsoft Defender for Endpoint 在最新的 MITRE 评估中展示了行业领先的光学镜头和检测功能。 阅读 [：MITRE ATT 中的见解&基于 CK 的评估](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。

<a name="tvm"></a>

**[威胁&漏洞管理](next-gen-threat-and-vuln-mgt.md)**<br>
此内置功能使用基于游戏变化风险的方法发现、确定终结点漏洞和错误配置的优先顺序并修正。 

<a name="asr"></a>

**[减少攻击面](overview-attack-surface-reduction.md)**<br>
攻击面减少功能集在堆栈中提供第一道防线。 通过确保正确设置配置设置并应用攻击缓解技术，这些功能可以抵御攻击和利用。 这组功能还包括网络 [保护和](network-protection.md) [Web 保护](web-protection-overview.md)，用于控制对恶意 IP 地址、域和 URL 的访问。 

<a name="ngp"></a>

**[下一代保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
为了进一步强化网络的安全外围，Microsoft Defender for Endpoint 使用旨在捕获所有类型的新兴威胁的下一代保护。

<a name="edr"></a>

**[终结点检测和响应](overview-endpoint-detection-response.md)**<br>
终结点检测和响应功能已到位，以检测、调查和响应可能通过前两个安全支柱的高级威胁。 [高级搜寻](advanced-hunting-overview.md) 提供基于查询的威胁搜寻工具，可让你主动发现漏洞并创建自定义检测。

<a name="ai"></a>

**[自动调查和修正](automated-investigations.md)**<br>
Microsoft Defender for Endpoint 与快速响应高级攻击结合使用，提供自动调查和修正功能，可帮助在数分钟内大规模减少警报量。 

<a name="ss"></a>

**[设备的 Microsoft 安全功能分数](tvm-microsoft-secure-score-devices.md)**<br>

Defender for Endpoint 包括适用于设备的 Microsoft 安全分数，可帮助你动态评估企业网络的安全状态、识别未受保护的系统，以及采取建议的操作来提高组织的整体安全性。

<a name="mte"></a>

**[Microsoft 威胁专家](microsoft-threat-experts.md)**<br>
Microsoft Defender for Endpoint 的新托管威胁搜寻服务提供了主动搜寻、优先顺序和其他上下文和见解，进一步使安全运营中心 (SOC) 可以快速准确地识别和响应威胁。

>[!IMPORTANT]
>Defender for Endpoint 客户需要申请托管威胁Microsoft 威胁专家服务，以获得主动目标攻击通知，并按需与专家协作。 专家按需服务是一项附加服务。 目标攻击通知始终包含在你接受到托管威胁Microsoft 威胁专家服务中。<p>
><p>如果你尚未注册并且希望体验其优势，请转到设置<b></b>> <b>高级常规</b>> <b></b>> <b>Microsoft 威胁专家应用。</b> 接受后，你将受益于定向攻击通知，并开始 90 天的按需专家试用版。 请与 Microsoft 代表联系，获取完整的专家按需订阅。

<a name="apis"></a>

**[集中配置和管理、API](management-apis.md)**<br>
将 Microsoft Defender for Endpoint 集成到现有工作流中。

<a name="mtp"></a>

**[与 Microsoft 解决方案集成](threat-protection-integration.md)** <br>
Defender for Endpoint 直接与各种 Microsoft 解决方案集成，包括：
- Azure Defender
- Azure Sentinel
- Intune
- Microsoft 云应用安全
- Microsoft Defender for Identity
- Microsoft Defender for Office
- Skype for Business

**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**<br>
借助 Microsoft 365 Defender，Defender for Endpoint 和各种 Microsoft 安全解决方案形成统一的攻破前和入侵后企业防御套件，可跨终结点、标识、电子邮件和应用程序进行本机集成，以检测、阻止、调查和自动响应复杂的攻击。


## <a name="related-topic"></a>相关主题
[Microsoft Defender for Endpoint 有助于检测复杂的威胁](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
