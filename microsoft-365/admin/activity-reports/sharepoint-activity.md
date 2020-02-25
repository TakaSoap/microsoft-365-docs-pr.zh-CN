---
title: "\"管理中心\" 中的 Microsoft 365 报表-SharePoint 活动"
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- SPO160
- BSA160
ms.assetid: a91c958f-1279-499d-9959-12f0de08dc8f
description: 获取 SharePoint 活动使用率报告，以了解每个 SharePoint 用户的活动、共享的文件数以及存储利用率。
ms.openlocfilehash: 0e8195136aa21eda354e685bf4ffe35abdb8bd32
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238215"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>"管理中心" 中的 Microsoft 365 报表-SharePoint 活动

作为 Microsoft 365 管理员，"**报表**" 仪表板显示组织中各个产品的活动概述。 使用该仪表板，能够更深入细致地了解特定于每个产品的活动。 查看[Microsoft 365 管理中心的活动报表](activity-reports.md)。
  
例如，可通过查看有权使用 SharePoint 的用户与文件之间的交互情况，了解每个用户的活动。用户还可使用它查看共享的文件数，从而了解正在进行的协作的级别。
  
> [!NOTE]
> 将逐步引进一些功能。这意味着你可能不会看到此功能，或者此功能可能看起来不同于帮助文章中的描述。但不用担心 - 如果尚未看到这些功能，表示它们即将推出！ 
  
如果想要了解每个 SharePoint 网站中正在进行的活动量和存储使用情况，用户可以查看 [SharePoint 网站使用情况报表](sharepoint-site-usage.md)。
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint 或 Skype for Business 管理员的全局管理员、全局读取器或报告阅读器才能查看报告。 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>如何访问 SharePoint 活动报表？

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

    
2. 从 "**选择报告**" 下拉下，选择 " **SharePoint** \> **活动**"。
  
## <a name="interpreting-the-sharepoint-activity-report"></a>解读 SharePoint 活动报表

可通过查看" **文件**"和" **用户**"视图获取有关 SharePoint 活动的信息。<br/> ![SharePoint Activity Report](../media/96ee85af-f213-499b-9e2b-22912bd0b8c2.png)
  
|||
|:-----|:-----|
|1.  <br/> |可查看" **SharePoint 活动报表**"了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您在报告中选择某一天，该表（7）将显示从当前日期起的最长28天的数据（而不是报告生成的日期）。  <br/> |
|2.  <br/> |每个报告中的数据通常最长为过去24到48小时。  <br/> |
|3.  <br/> |" **文件**"视图可帮助你了解与存储在 SharePoint 网站上的文件进行了文件交互的已授权用户的唯一编号。  <br/> |
|4.  <br/> |" **页面** "视图显示用户访问的独特页面数。  <br/> |
|5.  <br/> |" **用户**"视图可帮助用户了解活跃用户数的变化趋势。如果用户在特定期间执行了文件活动（如保存、同步、修改或共享）或访问了页面，则视该用户为活跃用户。  <br/> 注意：一个文件活动可能会发生多次，但只计为一个活动文件。 例如，用户可在指定期间多次保存和同步同一文件，但在数据中此文件仅计为一个活跃文件和一个同步文件           |
|6.  <br/> | 在" **文件**"图表中，Y 轴表示用户保存、同步、修改或共享过的唯一文件数。  <br/>  在" **用户**"图表中，Y 轴表示在网站上执行文件交互（保存、同步、修改或共享）的唯一用户数。  <br/>  " **页面**"图表中，X 轴表示用户访问的独特页面数。  <br/>  所有图表的 X 轴都表示此特定报表的所选日期范围。  <br/> |
|7.  <br/> |您可以通过选择图例中的项目来筛选您在图表上看到的系列。 例如，在 "**文件**" 图表上，选择 "已**查看" 或**"已**同步**"、"**内部共享**" 或 "在**外部共享**" 以仅查看与每个相关的信息。 更改选择不会更改网格表中的信息。  <br/> |
|8.  <br/> | 下表显示按网站的活动细目。  <br/>  <br/> **Username**是在 SharePoint 网站上执行活动的用户的电子邮件地址。  <br/> " **上次活动日期 (UTC)**"表示选定日期范围内最近执行文件活动或最近访问页面的日期。要查看指定日期发生的活动，请直接在图表中选择该日期。  <br/> ![在图表中选择特定日期](../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png) <br/> 此操作将筛选表，以便仅为在特定日期执行活动的用户显示文件活动数据。  <br/>  " **已查看或已编辑文件数** "表示用户上传、下载、修改或查看的文件数。  <br/>  "已**同步文件**数" 是已从用户本地设备同步到 SharePoint 网站的文件数。  <br/>  **内部共享文件**是指与组织内的用户或组中的用户共享的文件数（可能包含外部用户）。  <br/>  " **外部共享文件数**"表示与组织外用户共享的文件数。  <br/>  **访问的页面**是用户对独特页面的访问。  <br/>  " **已删除**"表示用户许可证已删除。  <br/>  **注意：** 只要已删除用户的活动在所选时间段的某一时刻获得许可，该用户的活动仍将显示在报告中。 "已删除"列有助于提示你，用户可能不再活跃，但其活动已计入报表数据。  <br/> " **删除日期**"表示用户许可证删除的日期。  <br/>  **已分配的产品**是授权给用户的 Microsoft 365 产品。  <br/> |
|9.  <br/> |选择 "**管理列**" ![图标管理](../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png)列以在报告中添加或删除列。  <br/> |
|10.  <br/> |您还可以通过选择 "**导出**" 链接将报告数据导出到 Excel .csv 文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。  <br/> |
|||
   

