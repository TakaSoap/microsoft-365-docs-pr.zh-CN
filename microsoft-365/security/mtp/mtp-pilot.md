---
title: 运行你的试点 Microsoft 365 Defender 项目
description: 在生产中运行试点 Microsoft 365 Defender 项目，以有效确定 Microsoft 365 Defender 的优势和采用情况。
keywords: Microsoft 威胁防护试点，运行试点 Microsoft 威胁防护项目，评估 Microsoft 威胁防护在生产中，Microsoft 威胁防护试点项目，网络安全，高级持久威胁，企业安全性，设备，设备，标识，用户，数据，应用程序，事件，自动化调查和修正，高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 50f334a055a5bd974f9ea1f39c8fa38d44be9c26
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131219"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>运行你的试点 Microsoft 365 Defender 项目 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

若要有效地确定 Microsoft 365 Defender 的优势和采用情况，可以运行试点项目。 在生产环境中启用 Microsoft 365 Defender 并启动用例之前，最好先计划确定要为试点项目完成的任务并设置成功条件。 


## <a name="how-to-use-this-pilot-playbook"></a>如何使用此试点操作手册

本指南概述了 Microsoft 365 Defender 以及有关如何设置试点项目的分步说明。 

Microsoft 365 Defender 是一个统一的前期和后入侵后企业防护套件，它在各个终结点、标识、电子邮件和应用程序中以本地方式协调保护、检测、预防、调查和响应，以提供针对复杂攻击的集成保护。 它通过将以下功能组合并协调为一个安全解决方案来实现此操作：
  - Microsoft defender for Endpoint，Microsoft Defender 高级威胁防护的新名称 (终结点) 
  - Microsoft Defender for Office 365，Office 365 ATP 的新名称 (电子邮件)  
  - Microsoft Defender for Identity，Azure ATP 的新名称 (标识)  
  - Microsoft 云应用安全 (应用程序) 

![Image of_Microsoft 365 Defender 解决方案，适用于用户、Microsoft Defender for a Endpoint for Microsoft Defender for Endpoint、云应用、Microsoft 云应用安全性和数据、Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

使用集成的 Microsoft 365 Defender 解决方案，安全专家可以将威胁信号与 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity 和 Microsoft 云应用安全接收结合在一起，并确定威胁的完整范围和影响、它如何进入环境、受影响的内容以及当前对组织的影响。 Microsoft 365 Defender 执行自动操作以阻止或停止攻击和自我修复受影响的邮箱、终结点和用户身份。 有关详细信息，请参阅 [Microsoft 365 Defender 概述](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 。

![运行 Microsoft 365 Defender 试点的阶段](../../media/pilotphases.png)

下面的示例时间线因您的环境中的资源是否正确而异。 某些检测和工作流可能需要比其他更多的学习时间。

![运行 Microsoft 365 Defender 试点的示例时间线](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>为获得最佳结果，请尽可能仔细地执行试点说明。


### <a name="pilot-playbook-phases"></a>试点行动手册阶段 

在运行 Microsoft 365 Defender 试点中有四个阶段：

|阶段 | 说明 | 
|:-------|:-----|
| [规划](mtp-pilot-plan.md)<br> 约1天| 了解在运行 Microsoft 365 Defender 试点项目之前需要考虑的事项： <br><br>-Scope <br> -用例 <br>- 要求： <br>-测试计划 <br> -成功条件 <br> 记分卡 
| [过程](mtp-evaluation.md) <br>约2天|  访问 Microsoft 365 安全中心以设置你的 Microsoft 365 Defender 试点环境。 你将指导你执行以下操作：<br><br>-确定利益干系人并寻求你的试点的注销 <br> -环境注意事项 <br>-Access <br>-Azure Active Directory 安装程序 <br> -配置顺序 <br> -注册 Microsoft 365 E5 试用版 <br> -配置域 <br>-分配 Microsoft 365 E5 许可证 <br> -完成门户中的安装向导|
| [攻击模拟](mtp-pilot-simulate.md) <br>约2天| 为模拟攻击，您将获得以下指导：<br><br>-验证测试环境要求 <br>-运行模拟 <br>-调查事件 <br>-解决事件 
| [结束和摘要](mtp-pilot-close.md) <br>约1天| 当您到达进程的末尾时，您将被指引到：<br><br>-转到最终输出<br>-向你的利益干系人提供你的输出 <br>-提供反馈 <br>-执行后续步骤 

## <a name="next-step"></a>后续步骤
|[规划阶段](mtp-pilot-plan.md) | 规划 Microsoft 365 Defender 试点项目 
|:-------|:-----|
