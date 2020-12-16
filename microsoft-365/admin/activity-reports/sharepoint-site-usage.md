---
title: 管理中心中的 Microsoft 365 报告 - SharePoint 网站使用情况
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
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
- SPO160
- BSA160
ms.assetid: 4ecfb843-e5d5-464d-8bf6-7ed512a9b213
description: '获取 SharePoint 网站使用率报告，了解用户存储在 SharePoint 网站中的文件数、活跃使用的文件数和消耗的总存储量。 '
ms.openlocfilehash: 7da72dccb4a90ed204ffa785040b1968ac70feb3
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688201"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>管理中心中的 Microsoft 365 报告 - SharePoint 网站使用情况

作为 Microsoft 365 管理员， **报告仪表板可** 显示组织中各种产品的活动概述。 使用该仪表板，能够更深入细致地了解特定于每个产品的活动。 例如，可以获得有关从 SharePoint 获取的值的高级视图，其中包括用户存储在 SharePoint 网站的总文件数、频繁使用的文件数以及所有这些网站中已使用的存储。 然后，可深入研究 SharePoint 网站使用情况报表，了解所有网站的趋势和其中每个网站的详细信息。 
  
> [!NOTE]
> 你必须是 Microsoft 365 中的全局管理员、全局读者或报告读者，或者 Exchange、SharePoint、Teams 服务、Teams 通信或 Skype for Business 管理员才能查看报告。
GCC High 和 DoD 租户不支持管理中心中的 Microsoft 365 报告。
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>如何访问 SharePoint 网站使用情况报表

1. 在管理中心，转到"**报告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况"。</a>
    
2. 在 **SharePoint 文件下，** 单击 **"查看更多"。** 

3. 在 **SharePoint 活动旁边**，单击向下箭头以打开菜单。

4. 选择 **SharePoint** \> **网站使用情况**。
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>解读 SharePoint 网站使用情况报表

![SharePoint Site Usage Report](../../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|Item|说明|
|:-----|:-----|
|1.  <br/> |可查看" **SharePoint 网站使用情况**"报表，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您选择报告中的某一天，则表 (7) 将显示自当前日期起最多 28 天的数据 (而不是报告生成日期) 。  <br/> |
|2.  <br/> |每个报告中的数据通常涵盖过去 24 到 48 小时。 <br/> |
|3.  <br/> |"网站"图表显示总网站数和活跃网站数，包括用户在报告期间查看、修改、上载、下载、共享或同步文件或查看过页面的任何网站。  <br/> |
|4.  <br/> |" **文件**"图表显示所有网站中的总文件数和活动文件数。总文件数包括用户文件和系统文件。在指定时间内如果存储、同步、修改或共享了文件，则该文件被视为活动文件。  |
|5.  <br/> |" **存储**"图表显示报告时段内分配和使用存储的趋势。  <br/> |
|6.  <br/> |" **页面**"图表显示在所有网站中查看的页面数。  <br/> |
|7.  <br/> |通过选择图例中的项目，可以筛选所看到的图表。 例如，**在"文件**"图表上，选择 **"文件**"或 **"活动文件"。** 在"**站点**"图表上，可以选择"站点 **总数"** 或 **"活动站点"。** 在 **"存储** "图表上，可以选择 **"已分配存储"或** " **已使用存储"。** 更改选择不会更改网格表中的信息。  <br/> |
|8.  <br/> | 下表显示按网站的活动细目。  <br/> ![使用率报告的列选项](../../media/sharepointsite-usage.png)           <br/> " **网站 URL**"表示网站的完整 URL。  <br/> " **已删除**"是网站的删除状态。需要至少 7 天时间，网站才会标记为已删除。  <br/> " **网站所有者**"表示网站主要所有者的用户名。  <br/>**网站所有者主体** 名称是网站所有者的电子邮件地址。  <br/> " **上次活动日期(UTC)**"指上次在网站上检测到文件活动或查看了页面的日期。  <br/> " **文件**"表示网站上的文件数。  <br/> **活动文件** 是网站上活动文件的数量。<br/> 注意：如果在报告的指定时段内删除了文件，则报告中显示的活动文件数可能大于网站上当前的文件数。<br/>" **使用的存储空间 (MB)**"表示当前网站上正在使用的存储空间大小。  <br/> " **分配的存储空间 (MB)**"表示分配给该网站的最大存储空间大小。  <br/> " **页面查看次数**"表示在网站上查看页面的次数。  <br/> " **访问的页数**"表示在网站上访问的独特页面数。  <br/> " **根网站模板**"表示用于创建网站的模板。  <br/> 注意：如果要按不同的网站类型筛选数据，请导出数据并使用根 Web 模板列。 <br/>如果组织的策略阻止你查看可识别其中用户信息的报表，你可以更改所有这些报表的隐私设置。 查看 Microsoft  [365](activity-reports.md)管理中心的活动报告中的"如何隐藏用户级别详细信息？"部分。  <br/> |
|9.  <br/> |选择 **"管理列** ![ 管理列 ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) "以在报表中添加或删除列。    <br/> |
|10.  <br/> |您还可以通过选择"导出导出"链接，将报告数据导出到 Excel  .csv ![ ](../../media/4dc548cc-8061-48d5-9240-6793affca43a.png) 文件中。 此操作可导出所有网站的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果网站数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果网站数超过 2000，则需要导出数据才能进行排序和筛选。  <br/> 注意：将数据导出到 Excel 文件时，请注意，内容报表的生成日期将反映在"数据"列中的"列 **"** 中。      <br/>   |
|||
