---
title: Microsoft 团队用户活动中的 microsoft 365 报告
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: 了解如何获取 Microsoft 团队用户活动报告，并深入了解组织中的团队活动。
ms.openlocfilehash: 53c3da2d563363c7c463abc62f7cdf4b478ccecc
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353723"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 团队用户活动中的 microsoft 365 报告

Microsoft 365 "**报告**" 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。 在 Microsoft Teams 用户活动报表中，可深入了解组织中的 Microsoft Teams 活动。
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint 或 Skype for Business 管理员的全局管理员、全局读取器或报告阅读器才能查看报告。 
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>如何获取 Microsoft Teams 用户活动报表

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

    
2. 从 "**选择报表**" 下拉下，选择 " **Microsoft 团队** \> **用户活动**"。
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>解读 Microsoft Teams 用户活动报表

可通过查看" **活动**"和" **用户**"图表，了解 Microsoft Teams 用户活动。<br/>![Microsoft 365 报表-Microsoft 团队用户活动。](../../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|||
|:-----|:-----|
|1.  <br/> |可查看" **Microsoft Teams 用户活动**"报表，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您在报告中选择某一天，该表（7）将显示从当前日期起的最长28天的数据（而不是报告生成的日期）。  <br/> |
|2.  <br/> |每个报告中的数据通常最长为过去24到48小时。  <br/> |
|3.  <br/> |" **活动**"视图显示各活动类型的 Microsoft Teams 活动数。活动类型数是指小组聊天消息、私人聊天消息、通话或会议的数量。  <br/> |
|4.  <br/> |" **用户**"视图显示各活动类型的用户数。活动类型数是指小组聊天消息、私人聊天消息、通话或会议的数量。  <br/> |
|5.  <br/> | 在" **活动**"图表上，Y 轴表示特定活动数。  <br/>  在" **文件**"图表上，Y 轴表示参与小组聊天、私人聊天、通话或会议的用户数。  <br/>  图表的 X 轴都表示为此特定报表选定的日期范围。  <br/> |
|6.  <br/> |您可以通过选择图例中的项目来筛选您在图表上看到的系列。 例如，在 "**活动**" 图表中，选择 "**频道消息**"、"**聊天消息**"、"**通话**" 或 "**会议**"，仅查看与每个相关的信息。 更改选择不会更改网格表中的信息。  <br/> ![筛选 Microsoft 团队活动图](../../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|7.  <br/> | 显示的组列表由最大（180 天）报表时间范围内存在的（未删除）所有组确定。活动计数会因日期选择不同而有所变化。  <br/> 注意：在添加之前，可能无法在列中看到以下列表中的所有项。<br/>" **用户名**"是用户的电子邮件地址。 可以显示实际的电子邮件地址或采用匿名字段。  <br/> " **上次活动日期 (UTC)**"表示用户参与 Microsoft Teams 活动的最近日期。  <br/> " **频道消息**"表示指定时间段内，用户在小组聊天中发布的唯一消息数。  <br/> " **聊天消息**"表示指定时间段内，用户在私人聊天中发布的唯一消息数。  <br/> " **通话**"表示指定时间段内，用户参与的通话数。  <br/> " **会议**"表示指定时间段内，用户参与的在线会议数。  <br/> " **其他活动**"表示用户参与的其他团队活动数。  <br/> " **已删除**"指示团队是否已被删除。如果团队被删除，但在报告时段中有活动，则将显示在"已删除"设置为 true 的网格中。  <br/> " **删除日期**"是指删除团队的日期。  <br/> " **分配的产品**"是指分配给用户的一系列产品。  <br/>  如果组织的策略阻止你查看显示了可识别用户信息的报表，可更改所有这些报表的隐私设置。 请查看[Microsoft 365 管理中心的活动报告](activity-reports.md)中的 "**如何隐藏用户级别详细信息？** " 一节。  <br/> |
|8.  <br/> |选择要在报告中添加或删除列的**列**。  <br/> ![Teams user activity report - choose columns](../../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|9.  <br/> |您还可以通过选择 "**导出**" 链接将报告数据导出到 Excel .csv 文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。  <br/> |
|||
   

