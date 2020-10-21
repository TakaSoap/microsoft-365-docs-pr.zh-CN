---
title: 管理员中心的 Microsoft 365 报告-OneDrive for Business 活动
f1.keywords:
- NOCSH
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
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 获取贵组织的 OneDrive 使用率报告，并了解每个 OneDrive 用户的活动、共享的文件数和存储使用率。
ms.openlocfilehash: e83ec835f0aa4a453f14a44d9582edcfd5aa6433
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649742"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>管理员中心的 Microsoft 365 报告-OneDrive for Business 活动

Microsoft 365 " **报告** " 仪表板显示组织中各产品的活动概述。 让用户深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，可通过查看有权使用 OneDrive 的用户与 OneDrive 上文件之间的交互情况，了解每个用户的活动。用户还可使用它查看共享的文件数，从而了解正在进行的协作的级别。
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint、团队服务、团队通信或 Skype for Business 管理员中的全局管理员、全局读取器或报告阅读器才能查看报告。  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>如何获取 OneDrive 活动报表？

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页中，单击 OneDrive 卡上的 " **查看更多** " 按钮。
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>解读 OneDrive for Business 活动报表

您可以通过选择 " **活动** " 选项卡查看 OneDrive 报告中的活动。<br/>![Microsoft 365 报告-Microsoft OneDrive 活动报告。](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

选择 " **选择列** " 可在报告中添加或删除列。  <br/> ![OneDrive 活动报告-选择列](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

您还可以通过选择 " **导出** " 链接将报告数据导出到 Excel .csv 文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 
  
|Item|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|用户名  <br/> |OneDrive 帐户所有者的用户名。  <br/> |
| (UTC) 的上次活动日期  <br/> |最近一次在所选日期范围内对 OneDrive 帐户执行文件活动的日期。 . 要查看指定日期发生的活动，请直接在图表中选择该日期。  <br/> |
|查看或编辑的文件  <br/> |用户上载、下载、修改或查看的文件数。   <br/> |
|已同步文件  <br/> |已从用户本地设备同步到 OneDrive 帐户的文件数。 <br/> |
|内部共享的文件  <br/> | 已与组织内的用户或组中的用户共享的文件数， (可能包括外部用户) 。  <br/> |
|外部共享的文件  <br/> |与组织外部的用户共享的文件数。 <br/>|
|Deleted  <br/> | 这表示用户的许可证已被删除。  <br/> 注意：只要已删除用户的活动在所选时间段的某一时刻获得许可，该用户的活动仍将显示在报告中。 " **已删除** "列有助于提示你，用户可能不再活跃，但其活动已计入报表数据。  <br/> |
|删除日期  <br/> |删除用户许可证的日期。 <br/>|
|已分配产品  <br/> |授权给用户的 Microsoft 365 产品。|
|||