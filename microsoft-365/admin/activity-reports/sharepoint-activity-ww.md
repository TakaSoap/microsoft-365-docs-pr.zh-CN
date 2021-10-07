---
title: Microsoft 365管理中心中的报表 - SharePoint活动
f1.keywords:
- NOCSH
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
description: 获取SharePoint活动使用情况报告，了解每个用户SharePoint的活动、共享的文件数和存储使用率。
ms.openlocfilehash: c1e476ff36fb21150914d08e39aa742bd17493a2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60158906"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Microsoft 365管理中心中的报表 - SharePoint活动

作为Microsoft 365管理员，"报表 **"仪表板将显示** 组织中各种产品的活动概述。 使用该仪表板，能够更深入细致地了解特定于每个产品的活动。 请查看[活动报告中的活动Microsoft 365 管理中心。](activity-reports.md)
  
例如，可通过查看有权使用 SharePoint 的用户与文件之间的交互情况，了解每个用户的活动。用户还可使用它查看共享的文件数，从而了解正在进行的协作的级别。
  
> [!NOTE]
> 您必须是 Microsoft 365 中的全局管理员、全局读取者或报告读者，或者 Exchange、SharePoint、Teams Service、Teams Communications 或 Skype for Business 管理员才能查看报告。 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>如何访问 SharePoint 活动报表？

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击仪表板卡片上的"查看更多SharePoint按钮。
  
## <a name="interpret-the-sharepoint-activity-report"></a>解释SharePoint活动报告

You can view the activities in the SharePoint by choosing the **Activity** tab.<br/>![Microsoft 365报表 - Microsoft SharePoint活动报表。](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

选择 **"选择要在** 报表中添加或删除列的列"。  <br/> ![SharePoint活动报表 - 选择列。](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

您还可以通过选择"导出"链接将报告数据导出到Excel .csv文件。  此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 
  
|项目|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|用户名  <br/> |在活动网站上执行活动的用户SharePoint地址。  <br/> |
|上次活动日期 (UTC)   <br/> |所选日期范围内执行文件活动或访问页面的最近日期。 要查看指定日期发生的活动，请直接在图表中选择该日期。  <br/> |
|查看或编辑的文件  <br/> |用户上载、下载、修改或查看的文件数。   <br/> |
|已同步文件  <br/> |从用户的本地设备同步到网站的文件SharePoint数量。 <br/> |
|在内部共享的文件  <br/> | 已与组织内部用户或组内用户共享的文件 (可能包括外部用户) 。  <br/> |
|在外部共享的文件  <br/> |与组织外部的用户共享的文件数。 <br/>|
|访问的页面  <br/> |用户访问唯一页面。 <br/>|
|Deleted  <br/> | 这表示删除了用户的许可证。  <br/>  **注意：** 已删除用户的活动仍将显示在报告中，只要该用户在所选时间段的某个时间获得许可。 "已删除"列有助于提示你，用户可能不再活跃，但其活动已计入报表数据。  <br/> |
|删除日期  <br/> |删除用户许可证的日期。 <br/>|
|分配的产品  <br/> |Microsoft 365许可给用户的产品。|
|||