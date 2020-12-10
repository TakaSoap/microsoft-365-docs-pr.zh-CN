---
title: Microsoft 365 组-管理中心中的 microsoft 365 报告
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: 获取 Microsoft 365 组报告以了解有关组及其活动的信息。
ms.openlocfilehash: 4a89f09f89e399905d0cb6927eca76c1242dfc62
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611878"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Microsoft 365 组-管理中心中的 microsoft 365 报告

Microsoft 365 " **报告** " 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。 在 Microsoft 365 组报告中，您可以深入了解组织中的组活动，并查看创建和使用的组数。
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint、团队服务、团队通信或 Skype for Business 管理员中的全局管理员、全局读取器或报告阅读器才能查看报告。  
  
## <a name="how-to-get-to-the-groups-report"></a>如何访问组报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页中，单击 "活动用户-Microsoft 365 应用" 或 "活动用户-Microsoft 365 服务卡片" 上的 " **查看更多** " 按钮，以转到 "Office 365 报告" 页。
  
## <a name="interpret-the-groups-report"></a>解释组报告

您可以通过选择 "组" " **活动** " 选项卡，在 "Office 365 报告" 中查看激活。<br/>![Microsoft 365 报表-Microsoft Office 365 组活动。](../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png)

选择 " **选择列** " 可在报告中添加或删除列。  <br/> ![Office 365 组活动报告-选择列](../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png)

您还可以通过选择 " **导出** " 链接将报告数据导出到 Excel .csv 文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 

|项目|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|组名称  <br/> |组的名称。  <br/> |
|Deleted  <br/> |已删除的组的数量。 如果该组被删除，但在报告时间段中有活动，它将显示在网格中，并显示设置为 true 的标记。  <br/> |
|组所有者  <br/> |组所有者的名称。  <br/> |
| (UTC) 的上次活动日期  <br/> |组接收到邮件的最新日期。 -这是活动在电子邮件对话、Yammer 或网站中发生的最新日期。  <br/> |
|类型  <br/> |组的类型。 可以是私有组，也可以是公用组。  <br/> |
|Exchange 中接收的电子邮件  <br/> |组接收到的邮件数。|
|Exchange 中的电子邮件 (总数)   <br/> |组邮箱中的总项目数。  <br/> |
|用于 Exchange (MB 的邮箱存储)   <br/> |组的邮箱使用的存储。 <br/>|
|SharePoint 文件 (总数)   <br/> |存储在 SharePoint 组网站中的文件数。  <br/> |
|SharePoint 文件 (活动)   <br/> |在报告期间 (查看或修改、同步、在内部或外部共享) 的 SharePoint 组网站中的文件数。  <br/> |
|用于 SharePoint (MB 的网站总存储空间)   <br/> |报告期间使用的存储量（以 MB 为单位）。  <br/> |
|Yammer 中的邮件 (发布)   <br/> |在报告时段内，在 Yammer 组中发布的邮件数。  <br/> |
|Yammer 中的邮件 (阅读)   <br/> |在报告时间段内 Yammer 组中读取的对话数。  <br/> |
|Yammer 中的邮件 (赞)   <br/> |报告期间，Yammer 组中的已赞邮件数。  <br/> |
|Members  <br/> |组中的成员数。  <br/> |
|外部成员 |组中的外部用户数。|
|||