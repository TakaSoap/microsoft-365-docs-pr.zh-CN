---
title: 管理中心中的 Microsoft 365 报表-SharePoint 网站使用情况
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
description: 获取 SharePoint 网站使用情况报表，了解用户在 SharePoint 网站中存储的文件数、要使用的文件数以及使用的总存储空间。
ms.openlocfilehash: bc9345a5e281f1e7343bf62a2dc6832587d0786e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649745"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>管理中心中的 Microsoft 365 报表-SharePoint 网站使用情况

作为 Microsoft 365 管理员，" **报表** " 仪表板显示组织中各个产品的活动概述。 使用该仪表板，能够更深入细致地了解特定于每个产品的活动。 例如，可以获得有关从 SharePoint 获取的值的高级视图，其中包括用户存储在 SharePoint 网站的总文件数、频繁使用的文件数以及所有这些网站中已使用的存储。 然后，可深入研究 SharePoint 网站使用情况报表，了解所有网站的趋势和其中每个网站的详细信息。 
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint、团队服务、团队通信或 Skype for Business 管理员中的全局管理员、全局读取器或报告阅读器才能查看报告。
在管理中心中，不支持对 GCC 高和 DoD 租户进行 Microsoft 365 报告。
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>如何访问 SharePoint 网站使用情况报表

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页中，单击 SharePoint 卡片上的 " **查看更多** " 按钮。
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>解释 SharePoint 网站使用情况报表

您可以通过选择 " **网站使用情况** " 选项卡在 SharePoint 报表中查看网站使用率。<br/>![Microsoft 365 报告-Microsoft SharePoint 网站使用率报告。](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

选择 " **选择列** " 可在报告中添加或删除列。  <br/> ![SharePoint 网站使用情况报表-选择列](../../media/639f3cfd-6725-4318-a225-6d5c2f01770c.png)

您还可以通过选择 " **导出** " 链接将报告数据导出到 Excel .csv 文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 
  
|Item|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|网站 URL  <br/> |网站的完整 URL。 <br/> |
|Deleted  <br/> |网站的删除状态。 需要至少 7 天时间，网站才会标记为已删除。  <br/> |
|网站所有者  <br/> |网站的主所有者的用户名。   <br/> |
|网站所有者主要名称  <br/> |网站所有者的电子邮件地址。 <br/> |
| (UTC) 的上次活动日期  <br/> | 上次检测到文件活动的日期或在网站上查看页面。  <br/> |
|文件  <br/> |网站上的文件数。 <br/>|
|活动文件  <br/> | 网站上的活动文件数。<br/> 注意：如果在指定的时间段内删除了文件，报告中显示的活动文件数可能大于网站上的当前文件数。  <br/> |
|使用的存储空间 (MB)   <br/> |网站上当前正在使用的存储量。  <br/>|
|存储分配 (MB)   <br/> |为站点分配的最大存储量。  <br/>|
|页面视图  <br/> |在网站上查看页面的次数。  <br/>|
|访问的页面  <br/> |在网站上访问的唯一页面的数量。  <br/>|
|根网站模板  <br/> |用于创建网站的模板。  <br/> 注意：如果要按不同的网站类型筛选数据，则导出数据并使用根 Web 模板列。 |
|||