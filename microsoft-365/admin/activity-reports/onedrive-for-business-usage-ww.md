---
title: Microsoft 365 OneDrive for Business使用情况报告
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: '获取OneDrive for Business使用情况报告，了解整个组织使用的文件和存储的总数。 '
ms.openlocfilehash: d3b884f374cf3dde572bd67ad905fc308a1701d1
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2022
ms.locfileid: "63400777"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365中心中的报告 - OneDrive for Business使用情况

"Microsoft 365报表"仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，仪表板上的 OneDrive 卡提供从 OneDrive for Business 中获取的值的高级视图，可显示组织中所有文件总数和所用存储。可深入研究，了解活跃 OneDrive 帐户的趋势、用户与之交互的文件数，以及使用的存储量。它还提供每个用户的 OneDrive 的详细信息。

## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>如何访问使用率OneDrive报告？

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击仪表板卡片上的"查看更多OneDrive按钮。
  
## <a name="interpret-the-onedrive-usage-report"></a>OneDrive 使用情况报表说明

You can view the usage in the OneDrive by choosing the **Usage** tab.<br/>![Microsoft 365报告 - Microsoft OneDrive使用情况报告。](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

选择 **"选择要在** 报表中添加或删除列的列"。  <br/> ![OneDrive使用情况报表 - 选择列。](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

您还可以通过选择"导出"链接将报告数据导出到Excel .csv文件。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 

可查看 **OneDrive for Business** 使用情况报告，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您选择报告中的某一天，则该表将显示自当前日期起最多 28 天的数据 (而不是报告生成日期) 。
  
|Item|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|URL  <br/> |用户地址的 web OneDrive。 <br/> |
|Deleted  <br/> |文件的删除OneDrive。 需要至少 7 天时间，帐户才会被标记为"已删除"。  <br/> |
|所有者  <br/> |网站的主要管理员的OneDrive。   <br/> |
|所有者主体名称  <br/> |所有者的电子邮件地址OneDrive。 <br/> |
|上次活动日期 (UTC)   <br/> | 文件活动在文件中执行的最新OneDrive。 如果 OneDrive 不曾有文件活动，其值将为空。  <br/> |
|文件  <br/> |文件中文件OneDrive。 <br/>|
|活动文件  <br/> | 该时段内的活动文件数。<br/> 注意：如果在报告的指定时段内删除了文件，则报告中显示的活动文件数可能大于当前报告OneDrive。 >  删除的用户会继续显示在报表中，为期 180 天。  <br/> |
|存储已 (MB)   <br/> |应用程序使用OneDrive MB 的数量。 |
|||
   
> [!NOTE]
> 该报告仅包括具有有效许可证OneDrive for Business用户。
