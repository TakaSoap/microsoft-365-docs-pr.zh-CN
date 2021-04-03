---
title: 管理中心中的 Microsoft 365 报表 - SharePoint 网站使用情况
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
description: 获取 SharePoint 网站使用率报告，了解用户在 SharePoint 网站中存储的文件数、活跃使用的文件数以及使用的总存储量。
ms.openlocfilehash: cfae7e1fc02d769328af46f75fdafc143467630b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579502"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>管理中心中的 Microsoft 365 报表 - SharePoint 网站使用情况

作为 Microsoft 365 管理员，"报表"仪表板将显示组织中各种产品的活动概述。 使用该仪表板，能够更深入细致地了解特定于每个产品的活动。 例如，可以获得有关从 SharePoint 获取的值的高级视图，其中包括用户存储在 SharePoint 网站的总文件数、频繁使用的文件数以及所有这些网站中已使用的存储。 然后，可深入研究 SharePoint 网站使用情况报表，了解所有网站的趋势和其中每个网站的详细信息。 
  
> [!NOTE]
> 你必须是 Microsoft 365 中的全局管理员、全局读者或报告读者，或者 Exchange、SharePoint、Teams 服务、Teams 通信或 Skype for Business 管理员才能查看报告。
GCC High 和 DoD 租户不支持管理中心中的 Microsoft 365 报告。
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>如何访问 SharePoint 网站使用情况报表

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击 SharePoint **卡片上的"** 查看更多"按钮。
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>解释 SharePoint 网站使用率报告

You can view the site usage in the SharePoint report by choosing the **Site usage** tab.<br/>![Microsoft 365 报告 - Microsoft SharePoint 网站使用情况报告。](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

选择 **"选择要在** 报表中添加或删除列的列"。  <br/> ![SharePoint 网站使用率报告 - 选择列](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

您还可以通过选择"导出"链接将报告数据导出到 Excel .csv **文件中。** 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 
  
|项目|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|网站 URL  <br/> |网站的完整 URL。 <br/> |
|Deleted  <br/> |网站的删除状态。 需要至少 7 天时间，网站才会标记为已删除。  <br/> |
|网站所有者  <br/> |网站的主要所有者的用户名。   <br/> |
|网站所有者主体名称  <br/> |网站所有者的电子邮件地址。 <br/> |
|上次活动日期 (UTC)   <br/> | 上次检测到文件活动或网站上查看页面的日期。  <br/> |
|网站敏感度标签 ID  <br/> | 站点上的敏感度标签。  <br/> |
|外部共享  <br/> | 网站中的外部可共享设置。  <br/> |
|非托管设备策略  <br/> | 非托管设备的站点访问策略。  <br/> |
|地理位置  <br/> | 网站的地理位置。  <br/> |
|文件  <br/> |网站上文件的数量。 <br/>|
|活动文件  <br/> | 网站上活动文件的数量。<br/> 注意：如果在报告的指定时段内删除了文件，则报告中显示的活动文件数可能大于网站上当前的文件数。  <br/> |
|使用的存储 (MB)   <br/> |网站上当前使用的存储量。  <br/>|
|分配了 (MB)   <br/> |为网站分配的最大存储量。  <br/>|
|页面视图  <br/> |在网站中查看页面次数。  <br/>|
|访问的页面  <br/> |访问网站上的唯一页面数。  <br/>|
|匿名链接计数  <br/> |网站上使用"具有链接的任何人"共享文档或文件夹次数。  <br/>|
|公司链接计数  <br/> |网站上使用"组织中的人员及链接"共享文档或文件夹次数。  <br/>|
|来宾计数的安全链接  <br/> |使用网站上"特定人员"共享文档或文件夹次数。  <br/>|
|成员计数的安全链接  <br/> |使用网站上"特定人员"共享文档或文件夹次数。  <br/>|
|根网站模板  <br/> |用于创建网站的模板。  <br/> 注意：如果要按不同的网站类型筛选数据，请导出数据并使用"根 Web 模板"列。 |
|||