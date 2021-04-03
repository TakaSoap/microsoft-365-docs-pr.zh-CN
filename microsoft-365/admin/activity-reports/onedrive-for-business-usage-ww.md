---
title: 管理中心中的 Microsoft 365 报表 - OneDrive for Business 使用情况
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: '获取 OneDrive for Business 使用情况报告，了解整个组织使用的文件总数和存储。 '
ms.openlocfilehash: 54a3b1e041ee6155b5ce89d6cd5bc73233d1f69b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579538"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>管理中心中的 Microsoft 365 报表 - OneDrive for Business 使用情况

Microsoft 365 **报表** 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，仪表板上的 OneDrive 卡提供从 OneDrive for Business 中获取的值的高级视图，可显示组织中所有文件总数和所用存储。可深入研究，了解活跃 OneDrive 帐户的趋势、用户与之交互的文件数，以及使用的存储量。它还提供每个用户的 OneDrive 的详细信息。
  
> [!NOTE]
> 你必须是 Microsoft 365 中的全局管理员、全局读者或报告读者，或者 Exchange、SharePoint、Teams 服务、Teams 通信或 Skype for Business 管理员才能查看报告。  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>如何获取 OneDrive 活动报表？

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击 OneDrive **卡上的"** 查看更多"按钮。
  
## <a name="interpret-the-onedrive-usage-report"></a>OneDrive 使用情况报表说明

You can view the usage in the OneDrive report by choosing the **Usage** tab.<br/>![Microsoft 365 报告 - Microsoft OneDrive 使用情况报告。](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

选择 **"选择要在** 报表中添加或删除列的列"。  <br/> ![OneDrive 使用情况报告 - 选择列](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

您还可以通过选择"导出"链接将报告数据导出到 Excel .csv **文件中。** 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 
  
|项目|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|URL  <br/> |用户的 OneDrive 的 Web 地址。 <br/> |
|Deleted  <br/> |OneDrive 的删除状态。 需要至少 7 天时间，帐户才会被标记为"已删除"。  <br/> |
|所有者  <br/> |OneDrive 的主要管理员的用户名。   <br/> |
|所有者主体名称  <br/> |OneDrive 所有者的电子邮件地址。 <br/> |
|上次活动日期 (UTC)   <br/> | 在 OneDrive 中执行文件活动的最新日期。 如果 OneDrive 不曾有文件活动，其值将为空。  <br/> |
|文件  <br/> |OneDrive 中的文件数。 <br/>|
|活动文件  <br/> | 该时段内的活动文件数。<br/> 注意：如果在报告的指定时段内删除了文件，则报告中显示的活动文件数可能大于 OneDrive 中的当前文件数。 >  删除的用户会继续显示在报表中，为期 180 天。  <br/> |
|使用的存储 (MB)   <br/> |OneDrive 使用的存储量（以 MB 为单位）。 |
|||