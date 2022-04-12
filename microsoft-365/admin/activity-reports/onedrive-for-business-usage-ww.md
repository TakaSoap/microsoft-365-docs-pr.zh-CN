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
description: '获取OneDrive for Business使用情况报告，了解整个组织中使用的文件和存储的总数。 '
ms.openlocfilehash: f212a29a5fb41aae9ecb0daeae0638d7af1e5dd1
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781539"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365管理中心中的报表 - OneDrive for Business用法

Microsoft 365报表仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，仪表板上的 OneDrive 卡提供从 OneDrive for Business 中获取的值的高级视图，可显示组织中所有文件总数和所用存储。可深入研究，了解活跃 OneDrive 帐户的趋势、用户与之交互的文件数，以及使用的存储量。它还提供每个用户的 OneDrive 的详细信息。

## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>如何实现获取OneDrive使用情况报告？

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击OneDrive卡上的 **“查看更多**”按钮。
  
## <a name="interpret-the-onedrive-usage-report"></a>OneDrive 使用情况报表说明

可以通过选择“使用情况”选项卡来查看OneDrive报表中的 **使用** 情况。<br/>![Microsoft 365报表 - Microsoft OneDrive使用情况报告。](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

选择 **要** 从报表中添加或删除列的列。  <br/> ![OneDrive使用情况报告 - 选择列。](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

还可以通过选择“**导** 出”链接将报表数据导出到Excel .csv文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 

可以查看 **OneDrive for Business使用** 情况报告，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果在报表中选择特定日期，表将显示自当前日期（而不是生成报 (表) 日期）最多 28 天的数据。
  
|Item|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|URL  <br/> |用户OneDrive的 Web 地址。 <br/> |
|Deleted  <br/> |OneDrive的删除状态。 需要至少 7 天时间，帐户才会被标记为"已删除"。  <br/> |
|所有者  <br/> |OneDrive的主要管理员的用户名。   <br/> |
|所有者主体名称  <br/> |OneDrive所有者的电子邮件地址。 <br/> |
|上次活动日期 (UTC)   <br/> | 文件活动在OneDrive中执行的最新日期。 如果 OneDrive 不曾有文件活动，其值将为空。  <br/> |
|文件  <br/> |OneDrive中的文件数。 <br/>|
|活动文件  <br/> | 时间段内的活动文件数。<br/> 注意：如果在报表的指定时间段内删除了文件，则报表中显示的活动文件数可能大于OneDrive中的当前文件数。 >  删除的用户会继续显示在报表中，为期 180 天。  <br/> |
|存储使用的 MB (MB)   <br/> |OneDrive使用 MB 的存储量。 |
|||
   
> [!NOTE]
> 报表仅包括具有有效OneDrive for Business许可证的用户。
