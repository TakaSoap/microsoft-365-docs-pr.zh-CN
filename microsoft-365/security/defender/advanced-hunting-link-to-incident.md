---
title: 将查询结果链接到事件
description: 将查询结果链接到事件
keywords: 高级搜寻， 事件， 透视， 实体， 搜寻， 相关事件， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， Microsoft 365， Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c81b0b0850686242c675629cf99fa2c4b3a18496
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63755489"
---
# <a name="link-query-results-to-an-incident"></a>将查询结果链接到事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

可以使用事件链接功能将高级搜寻查询结果添加到调查中的新事件或现有事件。 此功能可帮助你轻松地从高级搜寻活动中捕获记录，这使你能够创建更丰富的时间线或事件上下文，从而与事件相关。 

## <a name="link-results-to-new-or-existing-incidents"></a>将结果链接到新事件或现有事件

1. 在高级搜寻查询页面中，首先在提供的查询字段中输入查询，然后选择" **运行查询** "获取结果。

    :::image type="content" source="../../media/link-to-incident-1.png" alt-text="Microsoft 365 Defender门户中的&quot;查询&quot;页" lightbox="../../media/link-to-incident-1.png":::

2. 在"结果"页中，选择与正在处理的新调查或当前调查相关的事件或记录，然后选择"链接到事件 **"**。

    :::image type="content" source="../../media/link-to-incident-1b.png" alt-text="门户中&quot;结果&quot;选项卡的&quot;事件Microsoft 365 Defender选项" lightbox="../../media/link-to-incident-1b.png":::

3. 在"**链接到** 事件"窗格中找到"警报详细信息"部分，然后选择"创建新事件"以将事件转换为警报，并将其分组为新事件：

    :::image type="content" source="../../media/link-to-incident-3-create-new.png" alt-text="事件门户中&quot;事件链接&quot;窗格中的&quot;警报Microsoft 365 Defender部分" lightbox="../../media/link-to-incident-3-create-new.png":::
    
    或者， **选择"链接到现有事件** "，将所选记录添加到现有记录。 从现有事件的下拉列表中选择相关事件。 还可以输入事件名称或 ID 的前几个字符以查找现有事件。 

    :::image type="content" source="../../media/link-to-incident-3-link-to-existing.png" alt-text="警报门户中的警报Microsoft 365 Defender部分" lightbox="../../media/link-to-incident-3-link-to-existing.png":::

4. 对于任一选择，请提供以下详细信息，然后选择"下一 **步"**：
      - **警报标题** - 提供事件响应者可以理解的结果的描述性标题。 此描述性标题将成为警报标题。
      - **严重性** - 选择适用于警报组的严重性。
      - **类别** - 为警报选择合适的威胁类别。
      - **说明** - 为分组警报提供有用的说明。
      - **建议的操作** - 提供修正操作。

5. 在" **受影响实体"** 部分，选择主要受影响或受影响的实体。 本节中仅显示基于查询结果的适用实体。 在我们的示例中，我们使用了查询来查找与可能的电子邮件过滤事件相关的事件，因此发件人是受到影响的实体。 例如，如果有四个不同的发件人，则创建四个警报，并链接到所选事件。

     :::image type="content" source="../../media/link-to-incident-4-impacted-entities.png" alt-text="网站门户中&quot;链接到事件&quot;部分Microsoft 365 Defender实体" lightbox="../../media/link-to-incident-4-impacted-entities.png":::

1. 选择 **下一步**。
1. 查看"摘要"部分 **提供的详细信息** 。
   :::image type="content" source="../../media/link-to-incident-5-summary.png" alt-text="事件门户中&quot;事件链接&quot;部分的结果Microsoft 365 Defender页" lightbox="../../media/link-to-incident-5-summary.png":::
     
1. 选择“**完成**”。

## <a name="view-linked-records-in-the-incident"></a>查看事件中的链接记录

您可以选择事件名称以查看事件链接到的事件。
:::image type="content" source="../../media/link-to-incident-6-incident-pg.png" alt-text="活动门户中&quot;摘要&quot;选项卡中的Microsoft 365 Defender屏幕" lightbox="../../media/link-to-incident-6-incident-pg.png":::

在我们的示例中，表示四个选定事件的四个警报已成功链接到新事件。 

在每个警报页面中，可以在时间线视图或事件的完整信息 (（如果可用) 查询结果视图）。
:::image type="content" source="../../media/link-to-incident-7-alert-story.png" alt-text="门户中&quot;日程表&quot;选项卡中的事件Microsoft 365 Defender详细信息" lightbox="../../media/link-to-incident-7-alert-story.png":::

您还可以选择该事件以打开"检查 **记录"** 窗格。
:::image type="content" source="../../media/link-to-incident-7-inspect-record.png" alt-text="检查事件在门户中&quot;日程表&quot;选项卡中的Microsoft 365 Defender详细信息" lightbox="../../media/link-to-incident-7-inspect-record.png":::

## <a name="filter-for-events-added-using-advanced-hunting"></a>筛选使用高级搜寻添加的事件
通过按手动检测源筛选事件队列和警报队列，可以查看从高级搜寻 **生成的** 警报。

:::image type="content" source="../../media/link-to-incident-8-filter.png" alt-text="在安全门户的&quot;筛选器&quot;页中手动筛选Microsoft 365 Defender队列" lightbox="../../media/link-to-incident-8-filter.png":::
