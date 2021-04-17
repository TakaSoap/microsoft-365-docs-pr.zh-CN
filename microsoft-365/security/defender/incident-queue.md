---
title: 确定 Microsoft 365 Defender 中事件的优先级
description: 了解如何在 Microsoft 365 Defender 中筛选事件队列中的事件
keywords: 事件, 队列, 概述, 设备, 标识, 用户, 邮箱, 电子邮件, 事件
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
ms.openlocfilehash: cd571414512ce876e730199b21bf755e4c4b733f
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876195"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>确定 Microsoft 365 Defender 中事件的优先级

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

Microsoft 365 Defender 应用相关分析，将来自不同产品的相关警报和自动调查聚合到事件中。 在 Microsoft 365 Defender 在整个产品套件中具有端到端可见性时，Microsoft 365 Defender 还会触发有关仅可标识为恶意活动的唯一警报。 此视图为安全分析师提供了更广泛的攻击案例，帮助他们更好地了解并处理整个组织的复杂威胁。

**事件队列** 显示跨设备、用户和邮箱创建的事件集合。 它可以帮助你对事件进行排序，从而确定优先级并制定明智的网络安全响应决策。 

在快速启动 Microsoft 365 安全中心 & 事件>事件和事件，你可以进入事件队列 (security.microsoft.com) 。 [](https://security.microsoft.com)

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件队列示例":::

默认情况下，Microsoft 365 安全中心内的事件队列显示过去六个月看到的事件。 最近的事件位于列表顶部，以便你可以先看到它。

事件队列具有可自定义 (选择"选择) 列"，可让你查看事件或受影响实体的不同特征。 这可以帮助您就事件的优先顺序做出明智的决策进行分析。

为了一目了然，自动事件命名根据警报属性（如受影响的终结点数量、受影响的用户数、检测源或类别）生成事件名称。 这使您可以快速了解事件的范围。

例如： *多个源报告的多个终结点上的多阶段事件。*

> [!NOTE]
> 在推出自动事件命名之前已存在的事件不会更改其名称。

事件队列还公开了多个筛选选项，在应用这些选项时，您可以对环境中的所有现有事件执行广泛扫描，或决定重点关注特定方案或威胁。 在事件队列中应用筛选器可帮助确定需要立即关注的事件。 

## <a name="available-filters"></a>可用筛选器

从默认事件队列中，可以选择"筛选器"以查看"筛选器"窗格，可以从中查看一组已筛选的事件。 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="事件队列的筛选器窗格示例":::

此表列出了可用的筛选器名称。

| 筛选器名称 | 说明 |
|:-------|:-----|
| 分配到 | 你可以选择显示分配给你或由自动化处理警报的警报。 |
| 类别 | 选择类别以专注于特定的策略、技术或看到的攻击组件。 |
| 分类 | 根据相关警报的集分类筛选事件。 值包括真警报、假警报或未设置。 |
| 数据敏感性 | 某些攻击主要针对容易泄露或有价值的数据。 通过应用筛选器查看事件中是否涉及敏感数据，可以快速确定敏感信息是否可能已泄露，并优先解决这些事件。 <br><br> 仅适用于已启用 Microsoft 信息保护的情况。|
| 设备组 | 按定义的设备组进行筛选。 |
| 调查状态 | 按自动调查的状态筛选事件。  |
| 多个类别 | 可以选择仅查看映射到多个类别并因此可能导致更多损坏的事件。 |
| 多个服务源  | 筛选以仅查看包含来自不同来源的警报的事件 (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365) 。 |
| 操作系统平台 | 按操作系统限制事件队列视图。 |
| 服务源 | 通过选择特定来源，可以集中精力处理包含至少一个来自该选定来源的警报的事件。 |
| Severity | 事件的严重性表明它可以对资产产生的影响。 严重性越高，影响越大，通常需要最直接的关注。 |
| 状态 | 可以根据事件的状态选择限制所显示事件的列表，以查看哪些事件处于活动状态/已解决状态。 |
|||

## <a name="incident-response-workflow"></a>事件响应工作流

下面是响应事件的典型工作流：

1. 确定并会审最高优先级的事件，以便进行调查和解决。
2. 对于每个高优先级事件，开始 [调查](investigate-incidents.md)：

   a. 查看事件的摘要，了解事件的范围和严重性以及受影响实体 ("摘要"选项卡) 。 

   b. 开始查看警报以了解警报的来源、范围和严重性 (**警报** 选项卡) 。

   c. 根据需要，在"设备、用户"和"邮箱"选项卡上 (受影响的设备、用户和) 。  

   d. 请参阅 Microsoft 365 Defender 如何自动解决"调查"选项卡 (**警报**) 。
   
   e. 根据需要，使用事件数据集中的信息获取"证据和 (**响应** "选项卡) 。

   调查时，应关注：

   - 包含：减少对租户的任何额外影响。
   - 小安：删除安全威胁。
   - 恢复：将租户资源还原到攻击前的状态。

3. 解决事件后，请花时间：

   - 了解攻击的类型及其影响。
   - 研究安全社区中的攻击，以寻找安全攻击趋势。
   - 重新调用用于解决事件的工作流，并根据需要更新标准工作流和手册。
   - 确定是否需要更改安全状态，并采取措施来实现这些更改。

以下是基本过程的摘要。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="调查事件的基本过程":::

## <a name="next-step"></a>后续步骤

确定哪个事件需要最高优先级后，选择它并开始 [调查](investigate-incidents.md)。

## <a name="see-also"></a>另请参阅
- [事件概述](incidents-overview.md)
- [调查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
