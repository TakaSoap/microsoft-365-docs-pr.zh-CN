---
title: Microsoft 365 Defender
description: Microsoft 365 Defender 是一个协调的威胁防护解决方案，旨在保护设备、标识、数据和应用程序
keywords: Microsoft 威胁防护简介， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f789053e0922ee81155a243bbaa7b3ab5b0f6d87
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055557"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

> 想要体验 Microsoft 365 Defender？ 可以在[实验室环境中评估它或在](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)[生产中运行你的试验项目](m365d-pilot.md?ocid=cx-evalpilot)。
>

Microsoft 365 Defender 是一款统一的漏洞前和漏洞后企业防御套件，结合检测、预防、调查和应急为一体，可针对终结点、标识、电子邮件和应用程序提供集成的保护，抵御复杂的攻击。

借助集成的 Microsoft 365 Defender 解决方案，安全专业人员可以整合每个产品接收的威胁信号，并确定威胁的完整范围和影响;它如何进入环境、对环境的影响以及它当前对组织的影响。 Microsoft 365 Defender 采取自动操作来阻止或停止攻击和自我修复受影响的邮箱、终结点和用户标识。  


<center><h2>Microsoft 365 Defender 服务</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender for Endpoint</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defender 交互式指南

在此交互式指南中，你将了解如何使用 Microsoft 365 Defender 保护你的组织。 你将看到 Microsoft 365 Defender 如何自动帮助检测安全风险、调查组织攻击和防止有害的活动。

> [!VIDEO https://aka.ms/M365Defender-InteractiveGuide]



Microsoft 365 Defender 套件保护： 
- **具有 Microsoft Defender for Endpoint** 的终结点 - Microsoft Defender for Endpoint 是一个统一的终结点平台，用于预防性保护、攻破后检测、自动调查和响应。 
- 使用 **Microsoft Defender for Office 365** 的电子邮件和协作 - 适用于 Office 365 的 Defender 可保护你的组织免受电子邮件、链接 (URL 和协作) 造成的恶意威胁。 
- Identity 为 Microsoft Defender 和 **Azure AD Identity Protection** 的标识 - Microsoft Defender for Identity 使用 Active Directory 信号来标识、检测和调查针对你的组织的高级威胁、遭到入侵的标识和恶意内部行为。 
- **具有 Microsoft Cloud App 安全性的应用程序** - Microsoft Cloud App security 是一个全面的跨 SaaS 解决方案，为云应用提供深入了解、强数据控制和增强的威胁防护。 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender 的独特跨产品层补充了各个套件组件，以：
- 通过信号共享和自动操作帮助抵御攻击，并协调套件中的防御响应
- 通过将警报、可疑事件和受影响资产的数据加入"事件"，为安全团队跨产品警报、行为和上下文进行攻击的完整情景旁白
- 通过自动修正触发受影响资产的自我修复，自动响应泄露
- 使安全团队能够跨终结点和 Office 数据执行详细有效的威胁搜寻

![事件概述页面的图像](../../media/overview-incident.png) <br>
跨产品事件 (概述) 

![警报队列的图像](../../media/incident-list.png)<br>
套件产品中的所有相关警报关联到单个事件 (警报视图) 

![事件队列的图像](../../media/advanced-hunting.png)<br>
基于查询的基于电子邮件和终结点原始数据的搜寻


Microsoft 365 Defender 跨产品功能包括： 
- **跨产品单** 一窗格的"工具"- 集中查看检测、受影响资产、自动操作以及单个队列和单个窗格中的相关证据 [security.microsoft.com。](https://security.microsoft.com) 
- **联合事件队列** - 通过确保完整攻击范围、受影响的资产和自动修正操作组合在一起并及时出现，帮助安全专业人员重点关注关键问题。 
- **自动响应威胁** - 关键威胁信息在 Microsoft 365 Defender 产品之间实时共享，以帮助停止攻击进度。 例如，如果在受 Microsoft Defender for Endpoint 保护的终结点上检测到恶意文件，它将指示 Defender for Office 365 扫描该文件并从所有电子邮件中删除该文件。 整个 Microsoft 365 安全套件将阻止该文件在看到时进行阻止。
- 对损坏的设备、用户标识和邮箱进行自我修复 **-** Microsoft 365 Defender 使用 AI 支持的自动操作和操作手册将受影响的资产修正回安全状态。 Microsoft 365 Defender 利用套件产品的自动修正功能，以确保尽可能自动修复与事件相关的所有受影响资产。
- **跨产品威胁搜寻** - 安全团队可以利用其独特的组织知识，通过针对各种保护产品收集的原始数据创建自己的自定义查询来搜寻泄露的迹象。 Microsoft 365 Defender 提供对终结点和 Microsoft Defender for Office 365 数据之间 30 天的历史原始信号和警报数据的基于查询的访问。 


## <a name="get-started"></a>入门
必须先满足 Microsoft 365 Defender 许可要求，然后才能在 Microsoft 365 安全中心中[](https://security.microsoft.com)启用该服务，security.microsoft.com。 有关详细信息，请阅读：
- [授权要求](prerequisites.md#licensing-requirements)
- [打开 Microsoft 365 Defender](m365d-enable.md)
