---
title: Microsoft 365 管理中心报表 - Microsoft Teams活动
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: 了解如何获取Microsoft Teams活动报告，并深入了解Teams活动。
ms.openlocfilehash: d431a96834a7e7ad69d637cf4009296ca2493211
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60553096"
---
# <a name="microsoft-365-admin-center-reports---microsoft-teams-user-activity"></a>Microsoft 365 管理中心报表 - Microsoft Teams活动

"Microsoft 365 **报表**"仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。 在 Microsoft Teams 用户活动报表中，可深入了解组织中的 Microsoft Teams 活动。
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>如何获取 Microsoft Teams 用户活动报表

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

    
2. 从"**选择报告"** 下拉列表中，选择 **"Microsoft Teams** \> **用户活动"。**
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>解读 Microsoft Teams 用户活动报表

可通过查看" **活动**"和" **用户**"图表，了解 Microsoft Teams 用户活动。<br/>![Microsoft 365报表 - Microsoft Teams活动。](../../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|Item|说明|
|:-----|:-----|
|1.  <br/> |可查看" **Microsoft Teams 用户活动**"报表，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您选择报告中的某一天，则此表将显示自当前日期起最多 28 天的数据 (而不是报告生成日期) 。  <br/> |
|2.  <br/> |每个报告中的数据通常涵盖过去 24 至 48 小时的数据。  <br/> |
|3.  <br/> |为了确保数据质量，我们将对过去五天执行每日数据有效性检查，并且将填补检测到的任何漏洞。 您可能会注意到过程中历史数据的差异。  <br/> |
|4.  <br/> |" **活动**"视图显示各活动类型的 Microsoft Teams 活动数。活动类型数是指小组聊天消息、私人聊天消息、通话或会议的数量。  <br/> |
|5.  <br/> |" **用户**"视图显示各活动类型的用户数。活动类型数是指小组聊天消息、私人聊天消息、通话或会议的数量。  <br/> |
|6.  <br/> | 在 **"活动** "图表上，Y 轴表示指定活动的计数。  <br/>  在 **"文件** "图表上，Y 轴表示参与团队聊天、私人聊天、通话或会议的用户数。  <br/>  图表上的 X 轴是特定报表的选定日期范围。  <br/> |
|7.  <br/> |通过选择图例中的项目，可以筛选在图表上看到的系列。 例如，在"**活动"** 图表上，选择"频道消息"、"聊天消息"、"通话"或"会议"，以仅查看与每个消息有关的信息。   更改选择不会更改网格表中的信息。  <br/> ![筛选Microsoft Teams活动图表。](../../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|8.  <br/> | 显示的组列表由最大（180 天）报表时间范围内存在的（未删除）所有组确定。活动计数会因日期选择不同而有所变化。  <br/> 注意：在添加以下列表中的所有项目之前，可能不会在列中看到这些项目。<br/>" **用户名**"是用户的电子邮件地址。 可以显示实际的电子邮件地址或采用匿名字段。  <br/> " **上次活动日期 (UTC)**"表示用户参与 Microsoft Teams 活动的最近日期。  <br/> " **频道消息**"表示指定时间段内，用户在小组聊天中发布的唯一消息数。  <br/> " **聊天消息**"表示指定时间段内，用户在私人聊天中发布的唯一消息数。  <br/> " **通话**"表示指定时间段内，用户参与的通话数。  <br/> " **会议**"表示指定时间段内，用户参与的在线会议数。  <br/> " **其他活动**"表示用户参与的其他团队活动数。  <br/> " **已删除**"指示团队是否已被删除。如果团队被删除，但在报告时段中有活动，则将显示在"已删除"设置为 true 的网格中。  <br/> " **删除日期**"是指删除团队的日期。  <br/> " **分配的产品**"是指分配给用户的一系列产品。  <br/>  如果组织的策略阻止你查看可识别其中用户信息的报表，你可以更改所有这些报表的隐私设置。 请查看活动报告中的活动报告中 **的** 如何隐藏用户级别 [Microsoft 365 管理中心。](activity-reports.md)  <br/> |
|9.  <br/> |选择 **"列** "以在报表中添加或删除列。  <br/> ![Teams活动报表 - 选择列。](../../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|10.  <br/> |您还可以通过选择"导出"链接将报告数据导出到Excel .csv **文件**。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。  <br/> |
|||
   

