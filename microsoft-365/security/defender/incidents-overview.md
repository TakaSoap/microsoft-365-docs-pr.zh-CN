---
title: Microsoft 365 Defender 中的事件
description: 调查在设备、用户和邮箱中看到的事件。
keywords: 事件, 警报, 调查, 关联, 攻击, 计算机, 设备, 用户, 标识, 标识, 邮箱, 电子邮件, 365, microsoft, m365
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
ms.openlocfilehash: 5b2baa2041a8cffcea212eb449d40b9a9cbfc22a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759482"
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

## <a name="next-step"></a>后续步骤

"事件"页 **中的事件** 队列列出了最近事件。 在这里，你可以：

- 查看应基于严重性 [和](incident-queue.md) 其他因素对哪些事件进行优先排序。 
- 对 [事件](investigate-incidents.md) 进行调查。
- [管理事件](manage-incidents.md)，包括重命名、分配事件、对事件管理工作流进行分类和添加标记。
