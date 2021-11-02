---
title: Microsoft 365管理中心中的报表 - OneDrive for Business活动
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
description: 获取OneDrive使用情况报告，并知道每个用户OneDrive的活动、共享的文件数和存储使用率。
ms.openlocfilehash: 8cfd6dfbcff15c118f9ad54ef29e5cec6cf4d6bf
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60648851"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365管理中心中的报表 - OneDrive for Business活动

the Microsoft 365 Reports dashboard shows you the activity overview across the products in your organization. 让用户深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，可通过查看有权使用 OneDrive 的用户与 OneDrive 上文件之间的交互情况，了解每个用户的活动。用户还可使用它查看共享的文件数，从而了解正在进行的协作的级别。

## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>如何获取 OneDrive 活动报表？

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击仪表板卡片上的"查看更多OneDrive按钮。
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>解读 OneDrive for Business 活动报表

You can view the activities in the OneDrive by choosing the **Activity** tab.<br/>![Microsoft 365报表 - Microsoft OneDrive活动报表。](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

选择 **"选择要在** 报表中添加或删除列的列"。  <br/> ![OneDrive活动报表 - 选择列。](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

您还可以通过选择"导出"链接将报告数据导出到Excel .csv文件。  此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。

可查看" **OneDrive for Business 使用情况**"报表以了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您选择报告中的某一天，则该表将显示自当前日期起最多 28 天的数据 (而不是报告生成日期) 。
  
|Item|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|用户名  <br/> |帐户所有者的用户名OneDrive帐户。  <br/> |
|上次活动日期 (UTC)   <br/> |文件活动在所选日期范围的OneDrive帐户上执行的日期。 . 要查看指定日期发生的活动，请直接在图表中选择该日期。  <br/> |
|查看或编辑的文件  <br/> |用户上载、下载、修改或查看的文件数。   <br/> |
|已同步文件  <br/> |从用户的本地设备同步到用户帐户的文件OneDrive数量。 <br/> |
|在内部共享的文件  <br/> | 已与组织内部用户或组内用户共享的文件 (可能包括外部用户) 。  <br/> |
|在外部共享的文件  <br/> |与组织外部的用户共享的文件数。 <br/>|
|Deleted  <br/> | 这表示删除了用户的许可证。  <br/> 注意：已删除用户的活动仍将显示在报告中，只要该用户在所选时段的某个时间获得许可。 " **已删除** "列有助于提示你，用户可能不再活跃，但其活动已计入报表数据。  <br/> |
|删除日期  <br/> |删除用户许可证的日期。 <br/>|
|分配的产品  <br/> |The Microsoft 365 products that are licensed to the user.|
|||