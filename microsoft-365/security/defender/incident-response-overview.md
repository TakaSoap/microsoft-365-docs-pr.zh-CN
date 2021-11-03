---
title: 调查并响应Microsoft 365 Defender
description: 使用事件报告功能调查和响应Microsoft 365 Defender。
keywords: 事件， 警报， 调查， 分析， 响应， 相关， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击
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
ms.openlocfilehash: abd075ae76eefc4a86d3e99471f092b3f4f03b34
ms.sourcegitcommit: cfcdb11cc5d39c6c71a34e09c03e8859cd6708d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60724808"
---
# <a name="investigate-and-respond-with-microsoft-365-defender"></a>调查并响应Microsoft 365 Defender

下面是针对以下项目的主要调查和Microsoft 365 Defender：

- [响应事件](#incident-response)
- [审阅和批准自动修正操作](#automated-investigation-and-remediation)
- [搜索数据中的已知威胁](#proactive-search-for-threats-with-advanced-hunting)
- [了解最新的网络攻击](#get-ahead-of-emerging-threats-with-threat-analytics)
- [获取帮助](#collaborate-with-microsoft-experts)

## <a name="incident-response"></a>事件响应

Microsoft 365 服务和应用将在检测到可疑或恶意事件或活动时创建警报。 单个警报可提供有关已完成或持续攻击的有价值的线索。 但是，攻击通常对不同类型的实体（如设备、用户和邮箱）使用多种技术。 结果是租户中的多个实体将收到多个警报。 由于将单个警报组合在一起以深入了解攻击可能非常困难且耗时，Microsoft 365 Defender 会自动将警报及其相关信息聚合到事件中。

在持续进行的基础上，确定事件队列中的最高优先级事件以进行分析和解决，并为响应做好准备。 此操作包括以下步骤：

- [通过](incident-queue.md) 筛选和事件队列排序来确定最高优先级的事件的会审。
- [通过](manage-incidents.md) 修改事件的标题、将其分配给分析员以及添加标签和注释来管理事件。

对于每个事件，使用事件响应工作流来分析事件及其警报和数据，以包含攻击、消除威胁、从攻击中恢复以及从中学习。 有关[示例，](incidents-overview.md#example-incident-response-workflow-for-microsoft-365-defender)请参阅Microsoft 365 Defender。

## <a name="automated-investigation-and-remediation"></a>自动调查和修复

如果组织正在使用Microsoft 365 Defender，则每当检测到恶意或可疑活动或Microsoft 365 Defender时，安全运营团队都会在安全门户中收到警报。 鉴于可能出现的威胁流永不结束，安全团队经常面临解决大量警报的挑战。 幸运的是，Microsoft 365 Defender包括自动调查和响应 (AIR) 功能，这些功能可帮助安全运营团队更有效地应对威胁。

自动调查完成后，将针对涉及事件的每条证据做出裁定。 根据裁定，确定修正操作。 在某些情况下，将自动执行修正操作;其他情况下，修正操作等待Microsoft 365 Defender审批。 

有关详细信息[，请参阅 Microsoft 365 Defender](m365d-autoir.md)中的自动调查和响应。

## <a name="proactive-search-for-threats-with-advanced-hunting"></a>使用高级搜寻主动搜索威胁

不足以在攻击发生时对攻击做出响应。 对于扩展的、多阶段的攻击（如勒索软件），你必须主动搜索正在进行攻击的证据，并采取措施在攻击完成之前停止攻击。

高级搜寻是 Microsoft 365 Defender 中基于查询的威胁搜寻工具，允许你浏览最多 30 天的原始数据。 你可以主动检查网络中的事件来找到威胁指示器和实体。 这种对数据进行灵活Microsoft 365 Defender可不受约束地搜寻已知威胁和潜在威胁。

你可以使用相同的威胁搜寻查询来构建自定义检测规则。 这些规则将自动运行，以检查并响应可疑的泄露活动、错误配置的计算机和其他发现。

有关详细信息[，请参阅使用高级搜寻在](advanced-hunting-overview.md)Microsoft 365 Defender主动搜寻威胁。

## <a name="get-ahead-of-emerging-threats-with-threat-analytics"></a>通过威胁分析领先于新出现的威胁

威胁分析是威胁情报功能，Microsoft 365 Defender旨在帮助安全团队尽可能高效地应对新出现的威胁。 它包括有关以下项目的详细分析和信息：

- 活动威胁参与者及其活动
- 热门和新的攻击技术
- 关键漏洞
- 常见攻击面
- 流行的恶意软件

威胁分析还包括有关每个已识别威胁的 Microsoft 365 租户中相关事件和受影响资产的信息。

每个已识别的威胁均包括一个分析员报告，这是 Microsoft 安全研究人员编写的威胁的全面分析，这些研究人员处于网络安全检测和分析的最前端，可提供有关攻击在 Microsoft 365 Defender 中如何出现的信息。

有关详细信息，请参阅威胁[分析Microsoft 365 Defender。](threat-analytics.md)

## <a name="collaborate-with-microsoft-experts"></a>与 Microsoft 专家协作

Microsoft 威胁专家 - 目标攻击通知是一项托管威胁搜寻服务。 应用和被接受后，你将收到来自 Microsoft 威胁专家的定向攻击通知，因此不会错过对环境的关键威胁。 这些通知将帮助您保护组织的终结点、电子邮件和标识。 Microsoft 威胁专家 – 按需专家可让你获取有关组织面临的威胁的专家建议，并且你可以就组织面临的威胁寻求帮助。 它作为附加订阅服务提供。

有关详细信息，请参阅Microsoft 威胁专家[中的Microsoft 365概述](/security/mtp/microsoft-threat-experts.md)。
