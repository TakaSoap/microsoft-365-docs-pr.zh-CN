---
title: Microsoft 365 Defender
description: Microsoft 365 Defender 是一个协调的威胁防护解决方案，旨在保护设备、标识、数据和应用程序
keywords: Microsoft 威胁防护简介、网络安全、高级持久威胁、企业安全性、设备、设备、标识、用户、数据、应用程序、事件、自动调查和修正、高级搜寻
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
ms.openlocfilehash: a8d25ba0b36ad6ba1651ffe19e3e2f6e241548c7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843800"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender



Microsoft 365 Defender 是一个统一的前期和后入侵后企业防护套件，它固有的跨终结点、标识、电子邮件和应用程序协调检测、预防、调查和响应，以提供针对复杂攻击的集成保护。

使用集成的 Microsoft 365 Defender 解决方案，安全专业人员可以将威胁信号与这些产品中的每个产品一起接收并确定威胁的完整作用域和影响，并将它们结合起来。如何进入环境、受影响的内容以及当前对组织的影响。 Microsoft 365 Defender 执行自动操作以阻止或停止攻击和自我修复受影响的邮箱、终结点和用户身份。  


<center><h2>Microsoft 365 Defender 服务</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender for Endpoint</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft 云应用安全</b></a></center></td>
</tr>
</table>
<br>


>[!TIP]
>请参阅本 [Microsoft 365 Defender 互动指南](https://aka.ms/MTP-Interactive-Guide)。


Microsoft 365 Defender suite 保护： 
- **使用 Microsoft defender For endpoint 的终结** 点-microsoft Defender for endpoint 是一个统一的终结点平台，用于预防性保护、入侵后检测、自动调查和响应。 
- **Microsoft defender For office 365 的电子邮件和协作** -office 365 的 defender 保护您的组织免受电子邮件、链接 (url) 和协作工具带来的恶意威胁的侵扰。 
- **带有 Microsoft defender For identity And AZURE AD Identity Protection 的标识** 。 Microsoft Defender for Identity 使用 Active Directory 信号识别、检测和调查组织中的高级威胁、已泄露身份和恶意内幕活动。 
- **Microsoft 云应用安全应用程序** 安全-Microsoft 云应用安全是全面的跨 SaaS 解决方案，为你的云应用提供深入的可见性、强大的数据控制和增强的威胁防护。 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender 独特的跨产品层将各个套件组件扩充为：
- 通过信号共享和自动操作来帮助防止攻击和跨套件协调防御性响应
- 通过将警报上的数据、可疑事件和受影响的资产加入 "事件"，对安全团队的产品警报、行为和上下文中的攻击的完整故事进行旁白
- 通过自动修正触发对受影响资产的自我修复来实现危害的自动化
- 使安全团队能够跨终结点和 Office 数据执行详细和有效的威胁搜寻

![事件概述页面的图像](../../media/overview-incident.png) <br>
跨产品事件 (概述) 

![警报队列的图像](../../media/incident-list.png)<br>
将所有相关的警报全部关联到一起组成一个事件 (警报视图中的套件产品) 

![事件队列的图像](../../media/advanced-hunting.png)<br>
电子邮件和终结点原始数据顶部的基于查询的搜寻


Microsoft 365 Defender 跨产品功能包括： 
- **跨产品单一** 外观视图：用于检测、受影响的资产的所有信息、执行的自动操作以及在 [security.microsoft.com](https://security.microsoft.com)中的单个队列和单个窗格中的相关证据。 
- **组合的事件队列** -以帮助安全专业人员通过确保完整的攻击作用域、受影响的资产和自动修正操作以及时方式进行分组，以帮助安全专业人员重点了解关键因素。 
- **对威胁的自动响应** -在 Microsoft 365 Defender 产品之间实时共享关键威胁信息，以帮助停止攻击的进展。 例如，如果在受 Microsoft Defender for Endpoint 保护的终结点上检测到恶意文件，它将指示 Office 365 的 Defender 扫描并删除所有电子邮件中的文件。 将阻止整个 Microsoft 365 安全套件看到该文件。
- **针对受损设备、用户标识和邮箱的自我修复** -Microsoft 365 Defender 使用采用 AI 的自动操作和行动手册将受影响的资产恢复为安全状态。 Microsoft 365 Defender 利用套件产品的自动修正功能，以确保与事件相关的所有受影响的资产在可能的情况下会自动修正。
- **跨产品威胁搜寻** -安全团队可以通过使用各种保护产品收集的原始数据创建自己的自定义查询，从而利用其独特的组织知识来寻找危害的迹象。 Microsoft 365 Defender 提供了对30天的历史原始信号的基于查询的访问，并在终结点和 Microsoft Defender for Office 365 数据中通知数据。 


## <a name="get-started"></a>入门
必须满足 microsoft 365 Defender 许可要求，然后才能在 [security.microsoft.com](https://security.microsoft.com)中启用 microsoft 365 安全中心中的服务。 有关详细信息，请参阅：
- [授权要求](prerequisites.md#licensing-requirements)
- [启用 Microsoft 365 Defender](mtp-enable.md)
