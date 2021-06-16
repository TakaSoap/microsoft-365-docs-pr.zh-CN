---
title: 运行你的试点 Microsoft 365 Defender 项目
description: 在生产中Microsoft 365试点 Defender 项目，以有效确定 Defender Microsoft 365和采用。
keywords: Microsoft 365Defender 试点， 运行试点 Microsoft 365 Defender 项目， 评估生产中的 Microsoft 365 Defender， Microsoft 365 Defender 试点项目， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 3219b329c53c32e02cd29acdd41a48cd93b2e8bb
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930507"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>运行你的试点 Microsoft 365 Defender 项目 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender


本指南通过提供指针来帮助你运行试点项目，以确保你有一个结构良好的计划，指导你完成使用攻击模拟功能，最后结束试点，并提供关键方法，让你反映和记录结果。

![运行 Defender Microsoft 365的阶段](../../media/pilotphases.png)


运行试点有助于有效地确定采用 defender Microsoft 365的好处。 在生产Microsoft 365启用 defender 并启动用例之前，最好先计划确定要为试点项目完成的任务并设置成功条件。 


## <a name="how-to-use-this-pilot-playbook"></a>如何使用此试点手册

本指南概述了 Microsoft 365 Defender 以及如何设置试点项目的分步说明。 

Microsoft 365Defender 是一个统一的攻破前和入侵后企业防御套件，在本机协调跨终结点、标识、电子邮件和应用程序的保护、检测、防护、调查和响应，以提供针对复杂攻击的集成保护。 它通过将以下功能组合并协调到单个安全解决方案中来这样做：
  - Microsoft Defender for Endpoint (终结点) 
  - Microsoft Defender for Office 365 (电子邮件)  
  - Microsoft Defender 标识 (标识)  
  - Microsoft Cloud App Security (应用) 

![适用于of_Microsoft、Microsoft Defender for Identity、终结点 Microsoft Defender for Endpoint、云应用、Microsoft Cloud App Security 和数据、Microsoft Defender for Office 365 的 365 Defender 解决方案的图像](../../media/mtp/m365pillars.png)

借助集成的 Microsoft 365 Defender 解决方案，安全专业人员可以将 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity 和 Microsoft Cloud App Security 接收的威胁信号汇集在一起，并确定威胁的完整范围和影响、威胁进入环境、受影响以及威胁当前对组织的影响。 Microsoft 365Defender 采取自动操作来阻止或停止攻击和自我修复受影响的邮箱、终结点和用户标识。 有关详细信息[，Microsoft 365 Defender](microsoft-365-defender.md)概述。



下面的示例时间线因环境中具有正确的资源而异。 一些检测和工作流可能需要比其他检测和工作流更多的学习时间。

![运行 Defender 试点Microsoft 365时间线示例](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>为了获得最佳结果，请尽可能遵循试点说明。


### <a name="pilot-playbook-phases"></a>试点手册阶段 

运行 Defender 试点有四Microsoft 365阶段：

|阶段 | 说明 | 
|:-------|:-----|
| [规划](m365d-pilot-plan.md)<br> ~ 1 天| 了解在运行 Defender Microsoft 365项目之前需要考虑的问题： <br><br>- 范围 <br> - 用例 <br>- 要求： <br>- 测试计划 <br> - 成功条件 <br> - 记分卡 
| [准备](m365d-evaluation.md) <br>~2 天|  访问Microsoft 365安全中心，以设置Microsoft 365 Defender 试点环境。 将指导你：<br><br>- 确定利益干系人并寻求试点签署 <br> - 环境注意事项 <br>- Access <br>- Azure Active Directory安装程序 <br> - 配置顺序 <br> - 注册Microsoft 365 E5试用版 <br> - 配置域 <br>- 分配Microsoft 365 E5许可证 <br> - 在门户中完成安装向导|
| [攻击模拟](m365d-pilot-simulate.md) <br>~2 天| 要模拟攻击，将指导你：<br><br>- 验证测试环境要求 <br>- 运行模拟 <br>- 调查事件 <br>- 解决事件 
| [结束和摘要](m365d-pilot-close.md) <br>~ 1 天| 完成此过程后，将指导你：<br><br>- 完成最终输出<br>- 将输出呈现给利益干系人 <br>- 提供反馈 <br>- 执行以下步骤 

## <a name="next-step"></a>后续步骤
|[规划阶段](m365d-pilot-plan.md) | 规划 Microsoft 365 Defender 试点项目 
|:-------|:-----|
