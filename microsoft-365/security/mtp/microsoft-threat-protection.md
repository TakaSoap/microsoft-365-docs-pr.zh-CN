---
title: Microsoft 365 Defender
description: Microsoft 365 Defender 是一个协调的威胁防护解决方案，旨在保护设备、标识、数据和应用程序
keywords: Microsoft 威胁防护简介， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 1884f0dae87bf068d134430ada78e44d713fd4d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780512"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

> 想要体验 Microsoft 365 Defender？ 可以在[实验室环境中对其进行评估或在](https://aka.ms/mtp-trial-lab)[生产中运行试点项目](https://aka.ms/m365d-pilotplaybook)。
>

Microsoft 365 Defender 是一个统一的攻破前和入侵后企业防御套件，在本机协调跨终结点、标识、电子邮件和应用程序进行检测、预防、调查和响应，以提供针对复杂攻击的集成保护。

借助集成的 Microsoft 365 Defender 解决方案，安全专业人员可以将每个产品接收的威胁信号拼接在一起，并确定威胁的完整范围和影响;它如何进入环境、它的影响以及它当前对组织的影响。 Microsoft 365 Defender 采取自动操作来阻止或停止攻击和自我修复受影响的邮箱、终结点和用户标识。  


<center><h2>Microsoft 365 Defender 服务</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender for Endpoint</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defender 交互式指南

在此交互式指南中，你将了解如何使用 Microsoft 365 Defender 保护你的组织。 你将了解 Microsoft 365 Defender 如何帮助您检测安全风险、调查对组织的攻击以及自动防止有害的活动。

> [!VIDEO https://aka.ms/M365Defender-InteractiveGuide]



Microsoft 365 Defender 套件可保护： 
- **具有 Microsoft Defender for Endpoint** 的终结点 - Microsoft Defender for Endpoint 是一个统一的终结点平台，用于预防性保护、泄露后检测、自动调查和响应。 
- 与 **Microsoft Defender for Office 365** - Office 365 的 Defender 之间的电子邮件和协作可保护你的组织免受电子邮件、链接 (URL) 和协作工具造成的恶意威胁。 
- 具有 Microsoft Defender for Identity 和 **Azure AD Identity Protection** 的标识 - Microsoft Defender for Identity 使用 Active Directory 信号来识别、检测和调查针对组织的高级威胁、遭到入侵的标识和恶意内部操作。 
- **具有 Microsoft Cloud App 安全性** 的应用程序 - Microsoft Cloud App 安全性是一个全面的跨 SaaS 解决方案，为云应用提供深入可见性、强大的数据控制和增强的威胁防护。 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender 的独特跨产品层增强了各个套件组件，以：
- 通过信号共享和自动操作帮助抵御攻击，并在整个套件中协调防御响应
- 通过将警报、可疑事件和受影响资产的数据加入"事件"，为安全团队讲述跨产品警报、行为和上下文的攻击的完整情景
- 通过自动修正触发受影响资产的自我修复，自动响应泄露
- 使安全团队能够跨终结点和 Office 数据执行详细有效的威胁搜寻

![事件概述页面的图像](../../media/overview-incident.png) <br>
跨产品事件 (概述) 

![警报队列的图像](../../media/incident-list.png)<br>
套件产品中的所有相关警报关联到单个事件 (警报视图) 

![事件队列的图像](../../media/advanced-hunting.png)<br>
基于查询的基于电子邮件和终结点原始数据的搜寻


Microsoft 365 Defender 跨产品功能包括： 
- **跨产品单** 一窗格的透明 - 集中查看检测、受影响的资产、自动操作以及单个队列和单个窗格中的相关证据 [security.microsoft.com。](https://security.microsoft.com) 
- **组合事件队列** - 通过确保完整攻击范围、受影响的资产和自动修正操作组合在一起并及时出现，帮助安全专业人员专注于关键问题。 
- **威胁自动响应** - 关键威胁信息在 Microsoft 365 Defender 产品之间实时共享，以帮助停止攻击进度。 例如，如果在受 Microsoft Defender for Endpoint 保护的终结点上检测到恶意文件，它将指示 Defender for Office 365 扫描该文件并从所有电子邮件中删除该文件。 整个 Microsoft 365 安全套件将在看到文件时阻止该文件。
- 对损坏的设备、用户标识和邮箱进行自我修复 **-** Microsoft 365 Defender 使用 AI 支持的自动操作和操作手册将受影响的资产修正回安全状态。 Microsoft 365 Defender 利用套件产品的自动修正功能，以确保尽可能自动修正与事件相关的所有受影响资产。
- **跨产品威胁** 搜寻 - 安全团队可以利用自己独特的组织知识，通过针对各种保护产品收集的原始数据创建自己的自定义查询来搜寻泄露的迹象。 Microsoft 365 Defender 提供对终结点和 Microsoft Defender for Office 365 数据之间 30 天的历史原始信号和警报数据的基于查询的访问。 


## <a name="get-started"></a>入门
必须先满足 Microsoft 365 Defender 许可要求，然后才能在 Microsoft 365 安全中心内启用[security.microsoft.com。](https://security.microsoft.com) 有关详细信息，请阅读：
- [授权要求](prerequisites.md#licensing-requirements)
- [打开 Microsoft 365 Defender](mtp-enable.md)
