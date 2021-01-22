---
title: 规划试点 Microsoft 365 Defender 项目
description: 与利益干系人一起规划试点 Microsoft 365 Defender 项目，以管理预期并确保成功。
keywords: Microsoft 威胁防护试点， 规划 Microsoft 威胁防护试点项目， 评估生产中的 Microsoft 威胁防护， Microsoft 威胁防护试点项目， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8037b71fc41fb7fb0bdbfc829bad2ece1de6849b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930170"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>规划试点 Microsoft 365 Defender 项目 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

|![规划](../../media/phase-diagrams/1-planning.png)<br/>规划|[![准备](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[准备](prepare-mtpeval.md) | [![模拟攻击](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)<br/>[模拟攻击](mtp-pilot-simulate.md) | [![结束和汇总](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[结束和汇总](mtp-pilot-close.md)|
|--|--|--|--|
|*你在这里！*| | | |

您当前处于规划阶段。

若要确保您的试点项目成功，一开始就与利益干系人进行全面规划并获得批准至关重要。 规划要素包括确定范围、用例、要求和成功条件。

本指南将指导你完成如何规划试点项目。 

>[!IMPORTANT]
>为了获得最佳结果，请尽可能遵循试点说明。


## <a name="scope"></a>范围

试点的范围将根据您的环境和可接受的测试方法确定测试的范围。 下面是要考虑的一些范围示例：
- 包括终结点、服务器、域控制器的开发或测试环境。
- 使用 Microsoft 365、Azure、Active Directory 服务、终结点和服务器的生产环境

>[!NOTE]
>如果你还没有完整许可证，你可以获取试用许可证来评估 [Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) - 计划、准备、设置、配置和运行你的试点项目。 利益干系人将在帮助促进从头到完的过程方面起到重要作用。

还应根据组织构成定义要评估的操作系统的类型。 这可能包括以下各项[：Mac 终结点](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements)[、Linux 服务器](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements)[、Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)终结点[、Windows Server 2016。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)

## <a name="use-cases"></a>用例

用例表示有关要测试的工具如何供其预期用户使用的声明。 可以从特定人物（如 SOC 分析员）的角度将这些事件视为用户情景。 例如：
- 作为 SOC 分析师，我需要查看、关联、评估和管理网络中跨设备、用户和邮箱的警报和事件。 [事件管理]
- 作为 SOC 分析员，我必须具有自动调查和响应网络中恶意事件的工具和流程。 [Auto IR]
- 作为 SOC 分析师，我必须从环境中搜索数据，以查找已知和潜在的威胁以及可疑活动。 [高级搜寻]

请记住，应在定义的作用域的参数内创建这些用例。 例如，如果测试范围不包括对 Microsoft Cloud App Security 等工具的评估，则不应创建依赖它作为数据源的用例。

## <a name="requirements"></a>要求

从用例列表中，您可以开始创建要求。 要求包括工具必须满足用例的功能。 这些要求可以分为配置和维护、对集成的支持以及特定于功能的要求（如搜寻能力）和生成自定义警报的能力等类别。

## <a name="test-plan"></a>测试计划

根据要求，可能采用不同的测试方法。 例如，如果要求是评估自动修正的完成情况，测试计划需要包括生成行为的步骤 () 在 Microsoft 365 Defender 中触发自动修正操作。 如果要求是检测特定行为或攻击，则测试可能涉及更多步骤。 重点就是制定计划，根据你的要求进行精确测试。

## <a name="success-criteria"></a>成功条件

成功条件最终是设置用于衡量所测试结果的条形图。 无论你是测试 Microsoft 365 Defender (还是针对这一点) 其他技术，都必须有一些可量化的条件来确定该工具提供的价值。 根据范围、要求和测试计划，成功条件将确定如何为测试评分。 这应该不会通过或失败，而应基于你的需求进行更多的加权评分。 例如，要成功，工具可能需要在确定的某些关键方面得分超过 80%。

## <a name="scorecard"></a>记分卡

将计划的所有元素汇集在一起的方法之一是创建记分卡。 请参阅下面的记分卡示例：

| 用例 | 要求 | 配置要求 | 测试计划 | 预期结果 | 测试状态 | 得分 | 注释 |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|事件管理|- Microsoft 365 Defender  </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender for Endpoint </br></br>- Microsoft Cloud App Security (可选) |有关详细信息 [，请参阅](https://aka.ms/mtp-trial-lab) 准备、设置和配置的先决条件 |[模拟攻击](mtp-pilot-simulate.md) <br></br>[调查事件](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |调查人员可以了解事件的范围和影响并管理事件||||
|AutoIR|- Microsoft 365 Defender </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender for Endpoint |有关详细信息 [，请参阅](https://aka.ms/mtp-trial-lab) 准备、设置和配置的先决条件 <br>启用 AutoIR  |[模拟攻击](mtp-pilot-simulate.md) <br></br>[自动调查](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#automated-investigation-and-remediation) |Microsoft 365 Defender 会自动修正警报和事件||||
|高级搜寻|- Microsoft 365 Defender </br></br>- Microsoft Defender for Endpoint </br></br>-Microsoft Defender for Office 365 |有关详细信息 [，请参阅](https://aka.ms/mtp-trial-lab) 准备、设置和配置的先决条件|[高级搜寻方案](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#advanced-hunting-scenario) |调查人员可以通过高级搜寻、透视受影响实体和创建自定义检测来查找数据||||



## <a name="next-step"></a>后续步骤
|![准备阶段](../../media/mtp/prep.png) <br>[准备阶段](prepare-mtpeval.md) | 准备 Microsoft 365 Defender 试点环境
|:-------|:-----|
