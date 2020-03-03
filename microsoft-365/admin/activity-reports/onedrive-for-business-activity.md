---
title: 管理员中心的 Microsoft 365 报告-OneDrive for Business 活动
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 8bbe4bf8-221b-46d6-99a5-2fb3c8ef9353
description: 获取贵组织的 OneDrive 使用率报告，并了解每个 OneDrive 用户的活动、共享的文件数和存储使用率。
ms.openlocfilehash: b51071fe8c91b0064d6680b628b58df1f370c73d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353583"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>管理员中心的 Microsoft 365 报告-OneDrive for Business 活动

Microsoft 365 "**报告**" 仪表板显示组织中各产品的活动概述。 让用户深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，可通过查看有权使用 OneDrive 的用户与 OneDrive 上文件之间的交互情况，了解每个用户的活动。用户还可使用它查看共享的文件数，从而了解正在进行的协作的级别。
  
> [!NOTE]
> 将逐步引进一些功能。这意味着你可能不会看到此功能，或者此功能可能看起来不同于帮助文章中的描述。不用担心 - 它们即将推出！ 
  
如果想要了解每个 OneDrive 帐户中正在进行的活动量和存储使用情况，可以查看 [OneDrive 使用情况报表](onedrive-for-business-usage.md)
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint 或 Skype for Business 管理员的全局管理员、全局读取器或报告阅读器才能查看报告。 
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>如何获取 OneDrive 活动报表？

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

    
2. 从 "**选择报告**" 下拉下，选择 " **OneDrive** \> **活动**"。
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>解读 OneDrive for Business 活动报表

可通过查看" **文件** "和" **用户** "视图获取有关 OneDrive for Business 活动的信息。 
  
![OneDrive Activity Report](../../media/316b2a03-8e42-447c-aae8-080813eebe84.png)
  
|||
|:-----|:-----|
|1.  <br/> |可查看" **OneDrive for Business 使用情况**"报表以了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您在报告中选择某一天，该表（7）将显示从当前日期起的最长28天的数据（而不是报告生成的日期）。  <br/> |
|2.  <br/> |每个报告中的数据通常最长为过去24到48小时。 <br/>|
|3.  <br/> |" **文件**"视图可帮助了解针对任意 OneDrive 帐户执行了文件交互的已授权用户的唯一编号。  <br/> |
|4.  <br/> |" **用户**"视图可帮助了解活跃 OneDrive 用户数的变化趋势。如果用户在特定期间执行了文件活动（如保存、同步、修改或共享），则视该用户为活跃用户。  <br/> 注意：一个文件活动可能会对单个文件发生多次，但只会计为一个活动文件。 例如，用户可在指定期间多次保存和同步同一文件，但在数据中此文件仅计为一个活跃文件和一个同步文件。           |
|5.  <br/> | 在" **文件**"图表中，Y 轴表示用户保存、同步、修改或共享过的唯一文件数。  <br/>  在" **用户**"图表中，Y 轴表示在任意 OneDrive 帐户上执行文件交互（保存、同步、修改或共享）的唯一用户数。  <br/>  所有图表的 X 轴都表示为此特定报表选定的日期范围。  <br/> |
|6.  <br/> |您可以通过选择图例中的项目来筛选您在图表上看到的系列。 例如，在 "**文件**" 图表上，选择 "**查看或编辑**或**同步**" 以仅查看与每个相关的信息。 更改选择不会更改网格表中的信息。  <br/> |
|7.  <br/> | 下表详细显示了每个用户的数据。 可在表格中添加或删除列。   <br/>  **Username**是 OneDrive 帐户所有者的用户名。  <br/> " **上次活动日期 (UTC)**"表示选定日期范围内在 OneDrive 帐户上最近执行文件活动的日期。若要查看特定日期发生的活动，请直接在图表中选择该日期。  <br/> ![在图表中选择特定日期](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png)  <br/>  此操作将筛选表，以便仅为在特定日期执行活动的用户显示文件活动数据。  <br/> " **已查看或已编辑文件数** "表示用户上传、下载、修改或查看的文件数。  <br/> " **已同步文件数**"表示已从用户本地设备同步到 OneDrive 帐户的文件数。  <br/> **内部共享文件**是指与组织内的用户或组中的用户共享的文件数（可能包含外部用户）。  <br/> " **外部共享文件数**"表示与组织外用户共享的文件数。  <br/> " **已删除**"表示用户许可证已删除。  <br/> 注意：只要已删除用户的活动在所选时间段的某一时刻获得许可，该用户的活动仍将显示在报告中。 " **已删除** "列有助于提示你，用户可能不再活跃，但其活动已计入报表数据。<br/>" **删除日期**"表示用户许可证删除的日期。  <br/> **已分配的产品**是授权给用户的 Microsoft 365 产品。  <br/>  如果组织的策略阻止你查看可识别其中用户信息的报表，你可以更改所有这些报表的隐私设置。 请查看[Microsoft 365 管理中心的活动报告](activity-reports.md)中的 "**如何隐藏用户级别详细信息？** " 一节。  <br/> |
|8.  <br/> |选择 "**管理列**" ![图标管理](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png)列以在报告中添加或删除列。  <br/> |
|9.  <br/> |您还可以通过选择 "**导出**" 链接将报告数据导出到 Excel .csv 文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。  <br/> |
|||
   

