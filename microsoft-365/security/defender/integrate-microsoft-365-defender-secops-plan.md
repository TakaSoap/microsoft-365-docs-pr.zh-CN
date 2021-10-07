---
title: 步骤 1. 规划Microsoft 365 Defender准备情况
description: 将安全操作集成到Microsoft 365 Defender操作准备情况Microsoft 365 Defender规划基础知识。
keywords: 事件， 警报， 调查， 关联， 攻击， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击， secops， 安全操作， soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: db4b5b7518f3a79a37222764c0b7d627078aba5f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197997"
---
# <a name="step-1-plan-for-microsoft-365-defender-operations-readiness"></a>步骤 1. 规划Microsoft 365 Defender准备情况

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

无论安全操作的当前成熟度如何，与 SOC 安全运营中心 (一) 。 尽管没有适合每个组织的单一模型，但有些方面比其他方面更常见。 

以下各节介绍 SOC 的核心功能。

## <a name="provide-situational-awareness-of-modern-threats"></a>提供现代威胁的情境感知

SOC 团队准备并搜寻新的和传入的威胁，以便他们可以与组织合作以建立对策和响应。 你的 SOC 团队应具有在新式攻击方法和技术方面经过高度培训并且了解威胁参与者的人员。 共享威胁情报和框架（如 [网络](https://www.microsoft.com/security/blog/2016/11/28/disrupting-the-kill-chain/) 击杀链或 [MITRE ATT&CK](https://attack.mitre.org/) 框架）可增强威胁分析员和威胁情报人员的员工。

## <a name="provide-first-second-and-potentially-third-level-responses-to-cyber-incidents-and-events"></a>提供对网络事件和事件的一级、二级和可能的三级响应

SOC 是安全事件和事件的防护线。 当事件、威胁、攻击、策略违反或审核查找触发警报或行动号召时，SOC 团队会进行评估以会审并包含它或上报它进行调查。 因此，SOC 第一线响应者必须具有安全事件和指示器的广泛技术知识。

## <a name="centralize-monitoring-and-logging-of-your-organizations-security-sources"></a>集中监视和记录组织的安全源 

通常，SOC 团队的核心功能是确保所有安全设备（如防火墙、入侵防护系统、数据丢失防护系统、危险和漏洞管理 系统和标识系统）正常运行并受到监视。 SOC 团队将处理更广泛的网络操作，如标识、DevOps、云、应用程序、数据科学和其他业务团队，以确保集中和安全的安全信息分析。 此外，SOC 团队还负责以可用和可读格式维护数据日志，其中可能包括解析和规范化不同的格式。

## <a name="establish-red-blue-and-purple-team-operational-readiness"></a>建立红色、蓝色和紫色团队操作准备情况

每个 SOC 团队都应在响应网络事件时测试其准备情况。 可通过培训练习完成测试，例如与 IT、安全性和业务级别的不同人员一起运行的表格和做法。 个人培训练习团队基于代表性角色创建，并扮演防御者 (蓝队) 、攻击者 (红队) 的角色，或者作为寻求通过练习 (紫色团队) 中发现的优势和弱点来改进蓝队和红队的方法和技术的人。

## <a name="next-step"></a>后续步骤

[步骤 2.使用零信任框架执行 SOC 集成准备情况评估](integrate-microsoft-365-defender-secops-readiness.md)



