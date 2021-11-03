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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1fb039095df1df5b5fa5890d93b1f5b2462aac2e
ms.sourcegitcommit: 7791c519bd8b68fc23433e13e1ecbdbeaddbebfa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60725679"
---
# <a name="link-query-results-to-an-incident"></a>将查询结果链接到事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

通过指向事件功能的链接，你可以将高级搜寻查询结果添加到调查中的新事件或现有事件。 此功能可帮助你轻松地从高级搜寻活动中捕获记录，以便你可以创建更丰富的时间线或事件上下文，以与事件相关。 

## <a name="link-results-to-new-or-existing-incidents"></a>将结果链接到新事件或现有事件

1. 在高级搜寻查询页面中，首先在提供的查询字段中输入查询，然后选择" **运行查询** "获取结果。

    ![显示查询页的图像](../../media/link-to-incident-1.png)
2. 在"结果"页中，选择与正在处理的新调查或当前调查相关的事件或记录，然后选择"链接到事件 **"。**

    ![显示事件按钮链接的图像](../../media/link-to-incident-1b.png)
3. 在"**链接到** 事件"窗格中找到"警报详细信息"部分，然后选择"创建新事件"以将事件转换为警报，并将其分组为新事件：

 
    ![显示显示创建新事件的事件详细信息的图像](../../media/link-to-incident-3-create-new.png)   
    
    或者， **选择"链接到现有事件** "，将所选记录添加到现有记录。 从现有事件的下拉列表中选择相关事件。 还可以输入事件名称或 ID 的前几个字符以查找现有事件。 

    ![显示显示指向现有链接的事件详细信息的图像](../../media/link-to-incident-3-link-to-existing.png)
4. 对于任一选择，请提供以下详细信息，然后选择"下一 **步"：**
      - **警报标题** - 提供事件响应者可以理解的结果的描述性标题。 这将成为警报标题。
      - **严重性** - 选择适用于警报组的严重性。
      - **类别** - 为警报选择合适的威胁类别。
      - **说明** - 为分组警报提供有用的说明。
      - **建议的操作** - 提供修正操作。

5. 在" **受影响实体"** 部分，选择主要受影响或受影响的实体。 本节中仅显示基于查询结果的适用实体。 在我们的示例中，我们使用了查询来查找与可能的电子邮件过滤事件相关的事件，因此发件人是受到影响的实体。 例如，如果有四个不同的发件人，则创建四个警报，并链接到所选事件。 
     ![显示受影响实体的图像](../../media/link-to-incident-4-impacted-entities.png)   
6. 选择 **下一步**。
7. 查看"摘要"部分 **提供的详细信息** 。
     ![显示摘要的图像](../../media/link-to-incident-5-summary.png) 
8. 选择“**完成**”。

## <a name="view-linked-records-in-the-incident"></a>查看事件中的链接记录

您可以选择事件名称以查看事件链接到的事件。
     ![显示包含链接警报的事件页面的图像](../../media/link-to-incident-6-incident-pg.png) 

在我们的示例中，表示四个选定事件的四个警报已成功链接到新事件。 

在每个警报页面中，您可以在日程表视图或事件（如果可用）中查找 (和查询结果) 事件的完整信息。
     ![显示警报情景的图像](../../media/link-to-incident-7-alert-story.png) 

您还可以选择该事件以打开"检查 **记录"** 窗格。
![显示检查记录的图像](../../media/link-to-incident-7-inspect-record.png) 

## <a name="filter-for-events-added-using-advanced-hunting"></a>筛选使用高级搜寻添加的事件
通过按手动检测源筛选事件队列和警报队列，可以查看从高级搜寻 **生成的** 警报。

![显示显示指向现有链接的事件详细信息的图像](../../media/link-to-incident-8-filter.png) 