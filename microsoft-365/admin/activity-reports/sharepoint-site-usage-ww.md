---
title: Microsoft 365 管理中心 SharePoint网站使用情况报告
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
description: 获取SharePoint网站使用情况报告，了解用户在SharePoint站点中存储的文件数、主动使用的文件数以及消耗的总存储量。
ms.openlocfilehash: afcaa6cd087948c635604dbadeb9d56c6d48c1a9
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781492"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365管理中心中的报表 - SharePoint网站使用情况

作为Microsoft 365管理员，“报表”仪表板显示组织中各种产品的活动概述。 使用该仪表板，能够更深入细致地了解特定于每个产品的活动。 例如，可以从SharePoint获取的值的高级别视图，包括用户在SharePoint站点中存储的文件总数、正在积极使用的文件数以及所有这些站点中使用的存储。 然后，你可以向下钻取 SharePoint 网站使用情况报告，了解所有网站的趋势和每个网站级别的详细信息。 

## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>如何访问 SharePoint 网站使用情况报表

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击SharePoint卡上的 **“查看更多**”按钮。

## <a name="show-user-details-in-the-reports"></a>显示报表中的用户详细信息

报告提供有关组织的使用情况数据的信息。 默认情况下，报告显示包含用户、组和网站可识别名称的信息。 从 2021 年 9 月 1 开始，我们将默认隐藏所有报告的用户信息，以持续致力于帮助公司支持其本地隐私法律。
  
你的用户列表将如下所示：
  
![报告 - 匿名用户列表。](../../media/2ed99bce-4978-4ee3-9ea2-4a8db26eef02.png)
  
全局管理员可以恢复租户的此更改，并显示可识别的用户信息（如果其组织的隐私实践允许）。 可以按照以下步骤在 Microsoft 365 管理中心中实现此目标：
  
1. 在管理中心，转到“**设置**”\>“**组织设置**” \>“**服务**”页面。

2. 选择“**报表**”。 
  
3. 取消选中 **在所有报表中，显示用户、组和网站的已取消标识的名称**，然后保存所做的更改。 
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>解释SharePoint网站使用情况报告

可以通过选择“网站使用情况”选项卡来查看SharePoint报表中的 **网站使用情况**。

:::image type="content" alt-text="Microsoft 365报表 - Microsoft SharePoint站点使用情况报告。" source="../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png" lightbox="../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png":::

选择 **要** 从报表中添加或删除列的列。

:::image type="content" alt-text="SharePoint网站使用情况报告 - 选择列。" source="../../media/71ac3195-c494-40c1-9346-a858125ef6df.png":::

还可以通过选择“**导** 出”链接将报表数据导出到Excel .csv文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 

可以查看 **SharePoint网站使用** 情况报告，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果在报表中选择特定日期，表将显示自当前日期（而不是生成报 (表) 日期）最多 28 天的数据。
  
|跃点数|Description|
|:-----|:-----|
|网站 URL  |网站的完整 URL。 |
|Deleted  |网站的删除状态。 需要至少 7 天时间，网站才会标记为已删除。  |
|网站所有者  |网站主所有者的用户名。   |
|网站所有者主体名称  |网站所有者的电子邮件地址。 |
|上次活动日期 (UTC)   | 检测到最后一次文件活动的日期或在网站上查看页面的日期。  |
|网站敏感度标签 ID  | 网站上的敏感度标签。  |
|外部共享  | 网站上的外部可共享设置。  |
|非托管设备策略  | 非托管设备的站点访问策略。  |
|地理位置  | 站点的地理位置。  |
|文件  |网站上的文件数。 |
|活动文件  | 网站上的活动文件数。 如果文件在指定时间段内被保存、同步、修改或共享，则视为活跃文件。<br/> 注意：如果在报表的指定时间段内删除了文件，则报表中显示的活动文件数可能大于站点上的当前文件数。  |
|存储使用的 MB (MB)   |当前在站点上使用的存储量。  |
|存储分配的 MB (MB)   |为站点分配的最大存储量。  |
|页面视图  |在网站上查看页面的次数。  |
|访问过的页面  |网站上访问的唯一页面数。  |
|匿名链接计数  |使用网站上的“包含链接的任何人”共享文档或文件夹的次数。  |
|公司链接计数  |使用网站上的“组织中的人与链接”共享文档或文件夹的次数。  |
|来宾计数的安全链接  |使用网站上的“特定人员”共享文档或文件夹的次数。  |
|成员计数的安全链接  |使用网站上的“特定人员”共享文档或文件夹的次数。  |
|根网站模板  |用于创建网站的模板。  <br/> 注意：如果要按不同的网站类型筛选数据，请导出数据并使用根 Web 模板列。 |

