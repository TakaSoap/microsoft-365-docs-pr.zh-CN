---
title: Microsoft 365 Defender 中的事件
description: 调查在 Microsoft 365 安全中心内跨设备、用户和邮箱看到的事件。
keywords: 事件， 警报， 调查， 分析， 响应， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: 890e64367c49c24c8c70e2cbda9869a5d0797219
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939574"
---
# <a name="incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

> 希望体验 Microsoft 365 Defender？ 你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。
>

Microsoft 365 Defender 中的事件是关联警报和关联数据的集合，这些警报和关联数据是攻击案例的一部分。 

Microsoft 365 服务和应用在检测到可疑或恶意事件或活动时创建警报。 个别警报提供有关已完成或持续攻击的有价值的线索。 但是，攻击通常对不同类型的实体（如设备、用户和邮箱）使用各种技术。 结果是租户中多个实体收到多个警报。 

由于将各个警报分组在一起以深入了解攻击可能非常困难且耗时，因此 Microsoft 365 Defender 会自动将警报及其相关信息聚合到事件中。

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender 如何将实体中的事件关联到事件中":::

观看此简短概述，了解 Microsoft 365 Defender (4 分钟) 。

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

将相关警报分组到事件可为你提供攻击的全面视图。 例如，可以看到：

- 攻击的开始位置。
- 使用了哪些策略。
- 攻击已进入你的租户多远。
- 攻击范围，如影响的设备、用户和邮箱数量。 
- 与攻击关联的所有数据。

如果 [启用，Microsoft](m365d-enable.md)365 Defender 可以通过自动化和人工智能自动调查和解决警报。 还可以执行其他修正步骤来解决攻击。 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Microsoft 365 安全中心中的事件和警报

在快速启动 Microsoft  365 安全中心&事件>事件或事件管理事件 (security.microsoft.com) 。 [](https://security.microsoft.com) 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 安全中心中的&quot;事件&quot;页面":::

选择事件名称将显示事件摘要，并提供对包含其他信息的选项卡的访问权限。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 安全中心内事件的&quot;摘要&quot;页面示例":::

事件的其他选项卡包括：

- 警报 

  与事件及其信息相关的所有警报。

- 设备

  标识为事件的一部分或与事件相关的所有设备。

- 用户

  标识为事件的一部分或与事件相关的所有用户。

- 邮箱

  已标识为事件的一部分或与事件相关的所有邮箱。

- 调查

  事件警报触发的所有自动调查。

- 证据和响应

  事件警报中支持的所有事件和可疑实体。

下面是 Microsoft 365 安全中心内事件及其数据与事件选项卡之间的关系。

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Microsoft 365 安全中心内事件及其数据与事件选项卡的关系":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Microsoft 365 Defender 事件响应工作流示例

下面是使用 Microsoft 365 安全中心响应 Microsoft 365 中的事件的示例工作流。

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Microsoft 365 的事件响应工作流示例":::

持续确定事件队列中用于分析和解决的最高优先级事件，并使它们做好响应准备。 这是以下两者的组合：

- [通过](incident-queue.md) 筛选和事件队列排序来确定最高优先级事件的会审。
- [通过](manage-incidents.md) 修改事件的标题、将其分配给分析员以及添加标签和注释来管理事件。

1. 对于每个事件，开始 [攻击和警报分析](investigate-incidents.md)：

   a. 查看事件的摘要，了解事件的范围和严重性以及受影响实体 ("摘要"选项卡) 。 

   b. 开始分析警报，了解警报的来源、范围和严重性 (**警报** 选项卡) 。

   c. 根据需要，在"设备、用户"和"邮箱"选项卡上 (受影响的设备、用户和) 。  

   d. 请参阅 Microsoft 365 Defender 如何自动解决"调查"选项卡 (**警报**) 。
   
   e. 根据需要，使用事件数据集中的信息获取"证据和 (**响应** "选项卡) 。

2. 在分析之后或分析过程中，解决抑制问题，以减少攻击和安全威胁的更多影响。

3. 尽可能将租户资源还原到事件发生前的状态，从而从攻击中恢复。

4. [解决](manage-incidents.md#resolve-incident) 事件并花时间了解事件后情况：

   - 了解攻击的类型及其影响。
   - 研究威胁分析 [和安全](threat-analytics.md) 社区中的攻击，以寻找安全攻击趋势。
   - 重新调用用于解决事件的工作流，并根据需要更新标准工作流、流程、策略和操作手册。
   - 确定是否需要更改安全配置，并实施这些更改。

## <a name="example-security-operations-for-microsoft-365-defender"></a>Microsoft 365 Defender 的安全操作示例

下面是 Microsoft 365 Defender 的安全操作示例。

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Micosoft 365 Defender 的安全操作示例":::

日常任务可能包括：

- [管理](manage-incidents.md) 事件
- 查看 [AIR (操作) 调查和 ](m365d-action-center.md) 响应
- 查看最新的 [威胁分析](threat-analytics.md)
- [响应](investigate-incidents.md) 事件

每月任务可能包括：

- 查看 [AIR 设置](m365d-configure-auto-investigation-response.md)
- 查看[安全分数和](microsoft-secure-score-improvement-actions.md)[威胁&漏洞管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- 报告给 IT 安全管理链

季度任务可包括向 CISO (首席信息安全官报告并) 。

年度任务可能包括执行重大事件或泄露练习，以测试员工、系统和流程。 

每日、每月、季度和年度任务可用于更新或优化流程、策略和安全配置。

## <a name="next-steps"></a>后续步骤

"事件"页 **中的事件** 队列列出了最近事件。 在这里，你可以：

- 查看应基于严重性 [和](incident-queue.md) 其他因素对哪些事件进行优先排序。 
- [管理事件](manage-incidents.md)，其中包括重命名、分配、分类以及添加标记和注释以用于事件管理工作流。
- 执行 [事件](investigate-incidents.md) 分析。
