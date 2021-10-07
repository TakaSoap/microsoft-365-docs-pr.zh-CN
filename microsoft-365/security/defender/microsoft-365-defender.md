---
title: Microsoft 365 Defender
description: Microsoft 365 Defender是一个协调的威胁防护解决方案，旨在保护设备、标识、数据和应用程序
keywords: MMicrosoft 365 Defender 简介， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9061299034371f8ff2175f3c8a04d50068c43811
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60181135"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

> 想要体验 Microsoft 365 Defender？你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。
>

Microsoft 365 Defender 是一款统一的漏洞前和漏洞后企业防御套件，结合检测、预防、调查和应急为一体，可针对终结点、标识、电子邮件和应用程序提供集成的保护，抵御复杂的攻击。

通过集成Microsoft 365 Defender解决方案，安全专业人员可以整合每个产品接收的威胁信号，并确定威胁的完整范围和影响;它如何进入环境、对环境的影响以及它当前对组织的影响。 Microsoft 365 Defender采取自动操作来阻止或停止攻击和自我修复受影响的邮箱、终结点和用户标识。  


<center><h2>Microsoft 365 Defender服务</center></h2>
<table><tr><td><center><b><a href="/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint"><b>Microsoft Defender for Endpoint</b></center></a></td>
<td><center><b><a href="/microsoft-365/security/office-365-security/overview"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="/defender-for-identity/"><b>Microsoft Defender for Identity</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defender交互式指南

在此交互式指南中，你将了解如何使用Microsoft 365 Defender。 你将看到安全Microsoft 365 Defender检测安全风险、调查对组织的攻击以及自动防止有害的活动。

[请查看交互指南](https://aka.ms/M365Defender-InteractiveGuide)



Microsoft 365 Defender 套件保护： 
- **具有 Defender for Endpoint** 的终结点 - Defender for Endpoint 是一个统一的终结点平台，用于预防性保护、攻破后检测、自动调查和响应。 
- **使用 Defender for Office 365** 的电子邮件和协作 - Office 365 Defender 保护你的组织免受电子邮件、链接 (URL 和协作) 造成的恶意威胁。 
- Identity 为 Defender 的标识和 **Azure Active Directory (Azure AD) Identity Protection** - Defender for Identity 使用你的本地 Active Directory 域服务 (AD DS) 信号来识别、检测和调查针对你的组织的高级威胁、泄露的身份和恶意内部操作。 Azure AD Identity Protection 可自动检测和修正基于云的 Azure AD 中基于标识的风险。
- **具有 Microsoft Cloud App 安全性的应用程序** - Microsoft Cloud App security 是一个全面的跨 SaaS 解决方案，为云应用提供深入了解、强数据控制和增强的威胁防护。 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender独特的跨产品层补充了各个套件组件，以：

- 通过信号共享和自动操作帮助抵御攻击，并协调套件中的防御响应。
- 将警报、可疑事件和受影响资产的数据加入"事件"，为安全团队提供跨产品警报、行为和上下文的攻击的完整情景旁白。
- 通过自动修正触发对受影响资产的自我修复，自动响应泄露。
- 使安全团队能够跨终结点和用户数据执行详细Office搜寻。

下面是一个示例，Microsoft 365 Defender如何将产品套件中的所有相关警报关联到单个事件中。

![事件概述页的示例。](../../media/overview-incident.png) <br>

下面是事件的相关警报列表的示例。

![事件警报列表示例](../../media/incident-list.png)<br>

下面是基于查询的搜索（基于电子邮件和终结点原始数据）的示例。

![高级搜寻和查询示例](../../media/advanced-hunting.png)<br>

Microsoft 365 Defender跨产品功能包括： 

- **跨产品单** 一窗格的"列表"- 有关检测、受影响资产、自动操作以及单个队列和单个窗格中的相关证据 [security.microsoft.com。](https://security.microsoft.com) 
- **组合事件队列** - 通过确保完整攻击范围、受影响的资产和自动修正操作组合在一起并及时出现，帮助安全专业人员重点关注关键方面。 
- **威胁自动响应**- 关键威胁信息在 Microsoft 365 Defender 产品之间实时共享，以帮助阻止攻击的进展。 

   例如，如果在受 Defender for Endpoint 保护的终结点上检测到恶意文件，它将指示 defender for Office 365 扫描文件并从所有电子邮件中删除该文件。 整个安全套件都会在看到文件时Microsoft 365文件。
- **对损坏** 的设备、用户标识和邮箱进行自我修复 - Microsoft 365 Defender 使用 AI 支持的自动操作和手册将受影响的资产修正回安全状态。 Microsoft 365 Defender套件产品的自动修正功能，以确保尽可能自动修复与事件相关的所有受影响资产。
- **跨产品威胁搜寻** - 安全团队可以利用其独特的组织知识，通过针对各种保护产品收集的原始数据创建自己的自定义查询来搜寻泄露的迹象。 Microsoft 365 Defender提供对终结点和 Defender 中 30 天的历史原始信号和警报数据的基于查询的访问，以Office 365数据。 

## <a name="get-started"></a>入门

Microsoft 365 Defender许可要求，然后才能在 security.microsoft.com 的 Microsoft 365 Defender 门户中[启用该服务](https://security.microsoft.com)。 有关详细信息，请参阅：

- [许可要求](prerequisites.md#licensing-requirements)
- [打开 Microsoft 365 Defender](m365d-enable.md)

## <a name="training-for-security-analysts"></a>针对安全分析师的培训

通过 Microsoft Learn 的此学习路径，你可以Microsoft 365 Defender它如何帮助识别、控制和修正安全威胁。

|培训：|使用 Microsoft 365 Defender 检测和响应网络攻击|
|---|---|
|![Microsoft 365 Defender 训练图标。](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Microsoft 365 Defender 将跨终结点、标识、电子邮件和应用程序的威胁信号一致，以提供针对复杂网络攻击的集成保护。 Microsoft 365 Defender 是调查和响应事件并主动搜索正在进行的恶意网络安全活动的中心体验。<p> 1 小时 38 分钟 - Learning 路径 - 5 个模块|

> [!div class="nextstepaction"]
> [开始>](/learn/paths/defender-detect-respond/)


## <a name="see-also"></a>另请参阅
- [为 Microsoft 365 租户部署勒索软件保护](/microsoft-365/solutions/ransomware-protection-microsoft-365)
