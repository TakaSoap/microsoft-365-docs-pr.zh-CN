---
title: 确定事件优先级Microsoft 365 Defender
description: 了解如何筛选来自事件队列中的事件Microsoft 365 Defender
keywords: 事件， 队列， 概述， 设备， 标识， 用户， 邮箱， 电子邮件， 事件， 分析， 响应， 会审
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
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 38bfde92a2988cd8bdbca770402af96a4b9c5134
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321819"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>确定事件优先级Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

Microsoft 365 Defender应用相关分析，将不同产品的相关警报和自动调查聚合到事件中。 Microsoft 365 Defender在产品的整个套件中具有的端到端可见性Microsoft 365 Defender仅可以标识为恶意的活动触发唯一警报。 此视图为安全分析师提供了更广泛的攻击案例，帮助他们更好地了解并处理整个组织的复杂威胁。

**事件队列** 显示跨设备、用户和邮箱创建的事件集合。 它可以帮助你对事件进行排序，以确定优先级并创建明智的网络安全响应决策，这一过程称为事件会审。

在快速启动事件门户时&事件>**事件** 和事件Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">队列</a>。 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件队列的示例。" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

" **最近的事件和警报** "部分显示过去 24 小时内收到的警报数和创建的事件数的图。

默认情况下，事件门户中的事件Microsoft 365 Defender显示过去六个月看到的事件。 最近的事件位于列表顶部，以便你可以先看到它。

事件队列具有可自定义 (选择"选择) 列"，可让你查看事件或受影响实体的不同特征。 这可以帮助您就事件的优先顺序做出明智的决策进行分析。

为了一目了然，自动事件命名根据警报属性（如受影响的终结点数量、受影响的用户数、检测源或类别）生成事件名称。 借助此功能，可以快速了解事件的范围。

例如： *多个源报告的多个终结点上的多阶段事件。*

> [!NOTE]
> 在推出自动事件命名之前已存在的事件不会更改其名称。

事件队列还提供多个筛选选项，在应用这些选项时，您可以对环境中的所有现有事件执行广泛扫描，或决定重点关注特定方案或威胁。 在事件队列中应用筛选器可帮助确定需要立即关注的事件。 

**事件列表** 上方的"筛选器"列表显示当前应用的筛选器。

## <a name="available-filters"></a>可用筛选器

从默认事件队列中，可以选择"筛选器"以查看"筛选器"窗格，您可从该窗格中指定一组已筛选的事件。 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="事件队列的筛选器窗格示例。" lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

您还可以通过在事件 **列表上方** 的"筛选器"列表中选择任何筛选器来查看"筛选器"窗格。

此表列出了可用的筛选器名称。

| 筛选器名称 | 说明 |
|:-------|:-----|
| 状态 | 选择 **"新建**" **、"正在进行"** 或"已 **解决"**。 |
| Severity | 事件的严重性表明它可以对资产产生的影响。 严重性越高，影响越大，通常需要最直接的关注。 选择 **"高**、**中****、低**"或"**信息"**。 |
| 事件分配 | 选择一个或多个分配的用户。 |
| 多个服务源  | 指定筛选器是否适用于多个服务源。 |
| 服务源  | 指定包含警报的事件：应用治理、Microsoft 365 Defender、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Cloud Apps。 |
| 标记 | 从列表中选择一个或多个标记名称。 |
| 多个类别  | 指定筛选器是否适用于多个类别。 |
| 类别 | 选择类别以专注于特定的策略、技术或看到的攻击组件。 |
| 实体 | 指定资源的名称，如用户、设备、邮箱或应用程序名称。 |
| 数据敏感性 | 某些攻击主要针对容易泄露或有价值的数据。 通过应用特定敏感度标签的筛选器，可以快速确定敏感信息是否已被泄露，并确定解决这些事件的优先级。 <br><br> 此筛选器仅在打开Microsoft 信息保护时可用。 |
| 设备组 | 指定 [设备组](/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 名称。 |
| OS 平台 | 指定设备操作系统。 |
| 分类 | 指定相关警报的分类集。 |
| 自动调查状态 | 指定自动调查的状态。  |
| 关联威胁 | 指定命名威胁。  |
| Actors | 指定命名的威胁参与者。  |
|||

默认筛选器显示状态为"新建"和"正在进行"且严重性为 **"低**、中"或"高"的所有警报和 **事件**。 

通过在"筛选器"列表中选择筛选器名称中的 **X** ， **可以快速删除筛选器** 。 

## <a name="save-custom-filters-as-urls"></a>将自定义筛选器另存为 URL

在事件队列中配置了有用的筛选器后，您可以为浏览器选项卡的 URL 添加书签，或者将其另存为网页、Word 文档或您所选择的位置上的链接。 这样，只需单击一下即可访问事件队列的关键视图，例如：

- 新事件
- 高严重性事件
- 未分配事件
- 高严重性、未分配事件
- 分配给我的事件
- 分配给我以及 Microsoft Defender for Endpoint 的事件
- 具有特定标记的事件
- 具有特定威胁类别的事件
- 具有特定关联威胁的事件
- 特定主角的事件

编译有用的筛选器视图列表并存储为 URL 后，就可以使用它来快速处理队列中的事件并设置其优先级，并管理它们以用于后续分配和分析。[](manage-incidents.md)

## <a name="search-for-incidents"></a>搜索事件

在 **事件列表上方的"** 搜索名称或 ID"框中，可以键入事件 ID 或事件名称。 从搜索结果列表中选择事件时，Microsoft 365 Defender门户会打开一个包含事件属性的新选项卡，你可以从该选项卡开始[调查](investigate-incidents.md)。

## <a name="search-for-impacted-assets"></a>搜索受影响的资产

你可以将资源命名&mdash;为用户、设备、邮箱&mdash;或应用程序名称，并查找所有相关事件。 

## <a name="specify-a-time-range"></a>指定时间范围

默认事件列表针对的是过去六个月发生的事件。 通过选择以下选项，可以从日历图标旁边的下拉框中指定新的时间范围：

 - 1 天
 - 3 天
 - 1 周
 - 30 天
 - 30 天
 - 6 个月
 - 可同时指定日期和时间的自定义范围

## <a name="next-steps"></a>后续步骤

确定哪个事件需要最高优先级后，选择它并：

- [管理](manage-incidents.md) 事件的属性，包括标记、分配、误报事件的即时解决和注释。
- 开始 [调查](investigate-incidents.md)。

## <a name="see-also"></a>另请参阅
- [事件概述](incidents-overview.md)
- [管理事件](manage-incidents.md)
- [调查事件](investigate-incidents.md)
