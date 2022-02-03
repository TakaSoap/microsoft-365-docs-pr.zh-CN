---
title: Microsoft Defender for Endpoint
description: Microsoft Defender for Endpoint 是企业终结点安全性平台，可帮助抵御高级持久性威胁。
keywords: Microsoft Defender for Endpoint 简介，Microsoft Defender for Endpoint 简介，网络安全，高级持久性威胁，企业安全性，计算机行为传感器，云安全性，分析，威胁智能，攻击面减少，下一代保护，自动调查和修复，Microsoft 威胁专家，安全分数，高级搜寻，Microsoft 365 Defender，网络威胁搜寻
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: high
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: intro-overview
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d4bdd474f126eaf6d3cda21b2fcb4a1ffc383abe
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "62322103"
---
# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

Microsoft Defender for Endpoint 是企业终结点安全平台，旨在帮助企业网络阻止、检测、调查和响应高级威胁。

> [!TIP]
> 很快，Microsoft Defender for Endpoint 将在两个计划中提供。 本文介绍 Microsoft Defender for Endpoint 计划 2 中包含的特性和功能。 [了解有关 Microsoft Defender for Endpoint 计划 1 和计划 2 的详细信息](defender-endpoint-plan-1-2.md)。
> 

<p><p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Defender for Endpoint 使用内置于 Windows 10 和 Microsoft 的可靠云服务的以下技术组合：

- **终结点行为传感器**：嵌入在 Windows 10 中，这些传感器从操作系统收集和处理行为信号，并将此传感器数据发送到 Microsoft Defender for Endpoint 专用的独立云实例。

- **云安全分析**：在 Windows 生态系统、企业云产品（如 Office 365）和在线资产中利用大型数据、设备学习和独特的 Microsoft 光学系统，行为信号会转换为对高级威胁的见解、检测和建议响应。

- **威胁情报**：威胁情报由 Microsoft 猎手、安全团队生成并由合作伙伴所提供的威胁情报进行扩充，从而使 Defender for Endpoint 能够标识攻击者的工具、技术和过程，并在收集的传感器数据中观察到上述内容时生成警报。

<center><h2>Microsoft Defender for Endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>威胁和漏洞管理</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>攻击面减少</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>下一代保护</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>终结点检测和响应</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>自动调查和修正</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft 威胁专家</b></a></center></td>
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

<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0]

> [!TIP]
>
> - 了解 Defender for Endpoint 中的最新增强功能：[Microsoft Defender for Endpoint 中的新增功能](whats-new-in-microsoft-defender-endpoint.md)。
> - Microsoft Defender for Endpoint 在最近的 MITRE 评估中演示了业界领先的光学和检测功能。请参阅：[来自基于 MITRE ATT&CK 的评估的见解](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。

<a name="tvm"></a>

**[威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)**

此内置功能使用改变格局的基于风险的方法，以实现对终结点漏洞和错误配置的发现、优先级确定和修复。

<a name="asr"></a>

**[攻击面减少](overview-attack-surface-reduction.md)**

攻击面减少功能集在堆栈中提供第一道防线。 通过确保正确设置了配置设置并应用了攻击缓解技术，这些功能集可抵御攻击和被利用。 此功能集还包括[网络保护](network-protection.md)和 [Web 保护](web-protection-overview.md)，可用于控制对恶意 IP 地址、域和 URL 的访问。

<a name="ngp"></a>

**[下一代保护](next-generation-protection.md)**

为了进一步巩固你的网络的安全外围，Microsoft Defender for Endpoint 使用下一代保护来捕获所有类型的新兴威胁。

<a name="edr"></a>

**[终结点检测和响应](overview-endpoint-detection-response.md)**

可以使用终结点检测和响应功能来检测、调查和响应可能已越过前两个安全通道的高级威胁。 [高级搜寻](advanced-hunting-overview.md)提供了基于查询的威胁搜寻工具，可用于主动发现违规情况并创建自定义检测。

<a name="ai"></a>

**[自动调查和修正](automated-investigations.md)**

能够快速响应高级攻击的同时，Microsoft Defender for Endpoint 提供自动调查和修复功能，可帮助在数分钟内大规模减少警报数量。

<a name="ss"></a>

**[设备的 Microsoft 安全功能分数](tvm-microsoft-secure-score-devices.md)**

Defender for Endpoint 包括面向设备的 Microsoft 安全功能分数，可帮助你动态评估企业网络的安全状态、识别未受保护的系统，并采取建议的措施来提高组织的整体安全性。

<a name="mte"></a>

**[Microsoft 威胁专家](microsoft-threat-experts.md)**

Microsoft Defender for Endpoint 的新托管威胁搜寻服务提供主动搜寻、优先级确定以及其他上下文和见解，从而进一步使安全操作中心 (SOC) 可以快速准确地识别和响应威胁。

> [!IMPORTANT]
> Defender for Endpoint 客户需要申请 Microsoft 威胁专家托管威胁搜寻服务，以获取主动目标攻击通知，并与专家按需服务协作。 专家按需服务是一项附加服务。 在你接受加入 Microsoft 威胁专家托管威胁搜寻服务后，将始终包括目标攻击通知。
>
> 如果你尚未注册但想要体验它的优势，请转到 **设置** \> **常规** \> **高级功能** \> **Microsoft 威胁专家** 进行应用。 接受后，你将获得目标攻击通知的好处，并开始为期 90 天的专家点播试用版。 请联系你的 Microsoft 代表，以获取完整的专家按需服务订阅。

<a name="apis"></a>

**[集中配置和管理，API](management-apis.md)**

将 Microsoft Defender for Endpoint 集成到现有工作流中。

<a name="mtp"></a>

**[与 Microsoft 解决方案集成](threat-protection-integration.md)**

Defender for Endpoint 直接集成了各种 Microsoft 解决方案，包括：

- Microsoft Defender for Cloud
- Microsoft Sentinel
- Intune
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity
- Microsoft Defender for Office
- Skype for Business

**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-365-defende)**

借助 Microsoft 365 Defender，Defender for Endpoint 和各种 Microsoft 安全解决方案构成了统一的违反前/违反后企业防御套件，可跨终结点、标识、电子邮件和应用程序进行本机集成，以检测、阻止、调查和自动响应复杂的攻击。


## <a name="training-for-security-analysts"></a>针对安全分析师的培训

借助Microsoft Learn的学习路径，你可以了解 Defender for Endpoint 及其如何帮助防止、检测、调查和响应组织终结点 – 中的威胁你的设备和系统。

|培训：|使用 Microsoft 365 Defender 检测和响应网络攻击|
|---|---|
|![Microsoft 365 Defender 训练图标。](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Defender for Endpoint 是一种终结点安全解决方案，可在单个统一平台中提供漏洞管理、终结点保护、终结点检测和响应、移动威胁防御和托管服务。<p> 2 小时 25 分钟 - 学习路径 - 9 个模块|

> [!div class="nextstepaction"]
> [开始>](/learn/paths/defender-endpoint-fundamentals/)
