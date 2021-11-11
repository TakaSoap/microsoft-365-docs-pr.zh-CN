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
ms.openlocfilehash: d3dea119e73da7d0b0e8745ea1f96969f4818ac8
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914316"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>确定事件优先级Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

Microsoft 365 Defender相关分析，将不同产品的相关警报和自动调查聚合到事件中。 Microsoft 365 Defender在产品的整个套件中具有的端到端可见性Microsoft 365 Defender仅可以标识为恶意的活动触发唯一警报。 此视图为安全分析师提供了更广泛的攻击案例，帮助他们更好地了解并处理整个组织的复杂威胁。

**事件队列** 显示跨设备、用户和邮箱创建的事件集合。 它可以帮助你对事件进行排序，从而确定优先级并制定明智的网络安全响应决策。 这也称为事件会审。

在 Microsoft 365 Defender (security.microsoft.com) 快速启动时，你可以从事件& **>** 警报和事件Microsoft 365 Defender [队列](https://security.microsoft.com)。 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件队列的示例。" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

" **最近的事件和警报** "部分显示过去 24 小时内收到的警报数和创建的事件数的图。

默认情况下，事件门户中的事件Microsoft 365 Defender显示过去六个月看到的事件。 最近的事件位于列表顶部，以便你可以先看到它。

事件队列具有可自定义 (选择"选择) 列"，可让你查看事件或受影响实体的不同特征。 这可以帮助您就事件的优先顺序做出明智的决策进行分析。

为了一目了然，自动事件命名根据警报属性（如受影响的终结点数量、受影响的用户数、检测源或类别）生成事件名称。 借助此功能，可以快速了解事件的范围。

例如： *多个源报告的多个终结点上的多阶段事件。*

> [!NOTE]
> 在推出自动事件命名之前已存在的事件不会更改其名称。

事件队列还公开了多个筛选选项，在应用这些选项时，您可以对环境中的所有现有事件执行广泛扫描，或决定重点关注特定方案或威胁。 在事件队列中应用筛选器可帮助确定需要立即关注的事件。 

## <a name="available-filters"></a>可用筛选器

从默认事件队列中，可以选择"筛选器"以查看"筛选器"窗格，可以从中查看一组已筛选的事件。 以下是示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="事件队列的筛选器窗格示例。" lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

此表列出了可用的筛选器名称。

| 筛选器名称 | Description |
|:-------|:-----|
| 分配到 | 你可以选择显示分配给你或由自动化处理警报的警报。 |
| 类别 | 选择类别以专注于特定的策略、技术或看到的攻击组件。 |
| 分类 | 根据相关警报的集分类筛选事件。 值包括真警报、假警报或未设置。 |
| 数据敏感性 | 某些攻击主要针对容易泄露或有价值的数据。 通过应用筛选器查看事件中是否涉及敏感数据，可以快速确定敏感信息是否可能已泄露，并优先解决这些事件。 <br><br> 仅适用于已启用 Microsoft 信息保护的情况。|
| 设备组 | 按定义的设备组进行筛选。 |
| 调查状态 | 按自动调查的状态筛选事件。  |
| 多个类别 | 可以选择仅查看映射到多个类别并因此可能导致更多损坏的事件。 |
| 多个服务源  | 筛选以仅查看包含来自不同来源的警报的事件 (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365) 。 |
| OS 平台 | 按操作系统限制事件队列视图。 |
| 服务源 | 通过选择特定来源，可以集中精力处理包含至少一个来自该选定来源的警报的事件。 |
| Severity | 事件的严重性表明它可以对资产产生的影响。 严重性越高，影响越大，通常需要最直接的关注。 |
| 状态 | 可以根据事件的状态选择限制所显示事件的列表，以查看哪些事件处于活动状态/已解决状态。 |
|||

## <a name="save-defined-filters-as-urls"></a>将定义的筛选器另存为 URL

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

编译有用的筛选器视图列表并存储为 URL 后，就可以使用它来快速处理队列中的事件并设置其优先级，并管理它们以用于后续分配和分析。 [](manage-incidents.md)

## <a name="next-steps"></a>后续步骤

确定哪个事件需要最高优先级后，选择它并：

- [管理](manage-incidents.md) 事件的属性，包括标记、分配、误报事件的即时解决和注释。
- 开始 [调查](investigate-incidents.md)。

## <a name="see-also"></a>另请参阅
- [事件概述](incidents-overview.md)
- [管理事件](manage-incidents.md)
- [调查事件](investigate-incidents.md)
