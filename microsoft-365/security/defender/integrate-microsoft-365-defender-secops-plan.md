---
title: 步骤 1. 规划Microsoft 365 Defender操作就绪情况
description: 将Microsoft 365 Defender集成到安全操作中时规划Microsoft 365 Defender操作就绪情况的基础知识。
keywords: 事件， 警报， 调查， 关联， 攻击， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击， secops， 安全操作， soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8c69e92390e6ed6515be6f399703124ece99cc39
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664009"
---
# <a name="step-1-plan-for-microsoft-365-defender-operations-readiness"></a>步骤 1. 规划Microsoft 365 Defender操作就绪情况

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

无论安全操作的当前成熟程度如何，与安全运营中心 (SOC) 保持一致都很重要。 虽然没有适合每个组织的单个模型，但某些方面比其他方面更常见。

以下部分介绍 SOC 的核心函数。

## <a name="provide-situational-awareness-of-modern-threats"></a>提供现代威胁的情境感知

SOC 团队准备并搜寻新的和传入的威胁，以便他们能够与组织合作，制定对策和应对措施。 SOC 团队应具有经过现代攻击方法和技术训练有素且了解威胁执行组件的人员。 共享威胁情报和框架（如 [网络终止链](https://www.microsoft.com/security/blog/2016/11/28/disrupting-the-kill-chain/) 或 [MITRE ATT&CK 框架](https://attack.mitre.org/) ）可以为你的员工提供威胁分析师和威胁搜寻人员的能力。

## <a name="provide-first-second-and-potentially-third-level-responses-to-cyber-incidents-and-events"></a>提供对网络事件和事件的第一级、第二级和可能的第三级响应

SOC 是安全事件和事件的防御前线。 当事件、威胁、攻击、策略冲突或审核查找触发警报或行动调用时，SOC 团队会进行评估以进行会审并包含它或将其升级以供调查。 因此，SOC 一线响应者必须对安全事件和指标有广泛的技术知识。

## <a name="centralize-monitoring-and-logging-of-your-organizations-security-sources"></a>集中监视和记录组织的安全源

通常，SOC 团队的核心功能是确保防火墙、入侵防护系统、数据丢失防护系统、危险和漏洞管理系统和标识系统等所有安全设备正常运行并受到监视。 SOC 团队将与标识、DevOps、云、应用程序、数据科学和其他业务团队等更广泛的网络运营协作，以确保安全信息分析得到集中和安全。 此外，SOC 团队负责以可使用和可读格式维护数据的日志，这些格式可能包括分析和规范化不同的格式。

## <a name="establish-red-blue-and-purple-team-operational-readiness"></a>建立红、蓝、紫团队运营准备情况

每个 SOC 团队都应该测试其应对网络事件的准备情况。 测试可以通过训练练习来完成，例如，在 IT、安全性和业务级别，与各个个人一起进行表顶和练习运行。 个别训练练习队是根据代表角色创建的，他们要么扮演一个后卫 (蓝队) ，一个攻击者 (红队) ，要么作为观察者，试图通过在 (紫色队) 中发现的优势和弱点来改进蓝队和红队的方法和技术。

## <a name="next-step"></a>后续步骤

[步骤 2.使用 零信任 框架执行 SOC 集成就绪性评估](integrate-microsoft-365-defender-secops-readiness.md)
