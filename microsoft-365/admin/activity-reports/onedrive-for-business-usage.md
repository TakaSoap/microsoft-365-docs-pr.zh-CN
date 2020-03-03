---
title: 管理员中心的 Microsoft 365 报告-OneDrive for business 使用率
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
ms.assetid: 0de3b312-c4e8-4e4b-a02d-32b2f726a680
description: '获取 OneDrive for Business 使用情况报表，了解组织内使用的文件和存储的总数。 '
ms.openlocfilehash: 8bbf904faf1afe28f4a8a83209f681a44eaa932f
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353553"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>管理员中心的 Microsoft 365 报告-OneDrive for business 使用率

Microsoft 365 "**报告**" 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，仪表板上的 OneDrive 卡提供从 OneDrive for Business 中获取的值的高级视图，可显示组织中所有文件总数和所用存储。可深入研究，了解活跃 OneDrive 帐户的趋势、用户与之交互的文件数，以及使用的存储量。它还提供每个用户的 OneDrive 的详细信息。
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint 或 Skype for Business 管理员的全局管理员、全局读取器或报告阅读器才能查看报告。 
 
## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>如何获取 OneDrive 使用情况报表？

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

    
2. 从 "**选择报告**" 下拉下，选择 " **OneDrive** \> **使用情况**"。 
  
## <a name="interpret-the-onedrive-usage-report"></a>OneDrive 使用情况报表说明

可以通过查看" **帐户** "、" **文件** "和" **存储空间** "视图来了解 OneDrive for Business 使用情况。 
  
![OneDrive Usage Report](../../media/49c5b93b-d081-436e-8992-236343a6d46b.png)
  
|||
|:-----|:-----|
|1.  <br/> |" **OneDrive 使用情况**"报表显示过去 7 天、30 天、90 天或 180 天的变化趋势。 但是，如果您在报告中选择某一天，该表（7）将显示从当前日期起的最长28天的数据（而不是报告生成的日期）。  <br/> |
|2.  <br/> |每个报告中的数据通常最长为过去24到48小时。 <br/>|
|3.  <br/> |" **帐户**"视图显示 OneDrive 总帐户和活跃帐户数的变化趋势。"活跃帐户"指其中用户会查看、修改、上传、下载、共享或同步文件。  <br/> |
|4.  <br/> |" **文件**"视图显示总文件数和活跃文件数。在指定时间内，如果存储、同步、修改或共享了文件，则该文件被视为活跃文件。  <br/> 注意：一个文件活动可能会发生多次，但只计为一个活动文件。 例如，用户可在指定期间多次保存和同步同一文件，但在数据中此文件仅计为一个活跃文件和一个同步文件。           |
|5.  <br/> |" **存储空间**"视图将显示使用中的 OneDrive 的存储空间量的变化趋势。  <br/> > 注意：此大小包括与文件关联的任何版本和元数据。           |
|6.  <br/> | 在" **帐户**"图表上，Y 轴表示 OneDrive 帐户数。  <br/>  在" **文件**"图表上，Y 轴表示 OneDrive 中存储的文件数。  <br/>  在" **存储空间**"图表上，Y 轴表示已使用的 OneDrive 存储空间量。  <br/>  所有图表的 X 轴都表示此特定报表的所选日期范围。  <br/> |
|7.  <br/> |您可以通过选择图例中的项目来筛选您在图表上看到的系列。 例如，在 "**文件**" 图表上，选择 "**文件总数**" 或 "**活动文件**数"。 在 "**帐户**" 图表上，选择 "**帐户总数**" 或 "**活动帐户**"。 或在 "**存储**" 图表上，选择 "**使用的存储**"。 更改此选项不会更改表格中的信息。  <br/> |
|8.  <br/> | 该表显示每个用户的 OneDrive 数据细目。如需在表格中显示，需为用户分配包含 OneDrive 的产品许可证，并将 SharePoint Online 设置为开。用户还需登录到 OneDrive 同步客户端，或者使用 web 浏览器访问其 OneDrive。  <br/>  如果 OneDrive 已有文件活动，则该帐户具有执行文件活动的最新日期。表中行根据" **上次活动日期**"排序，因此具有最新文件活动的 OneDrive 会显示在列表顶部。  <br/>  可以添加或删除表中的列。  <br/> ![列选项](../../media/onedriveusage-columns.png)  <br/> **URL**是用户的 OneDrive 的 web 地址。  <br/> " **已删除**"是 OneDrive 的删除状态。需要至少 7 天时间，帐户才会被标记为"已删除"。  <br/> " **所有者**"表示 OneDrive 的主要管理员的用户名。  <br/> **所有者主体名称**是 OneDrive 所有者的电子邮件地址。  <br/> " **上次活动日期 (UTC)**" 表示 OneDrive 中最近执行的文件活动日期。如果 OneDrive 不曾有文件活动，其值将为空。  <br/> " **文件**"表示 OneDrive 中的文件数。  <br/> " **活跃文件**"表示一段时间内的活跃文件数。在选定时间内如果存储、同步、修改或共享了文件，则该文件被视为活跃文件。  <br/> 注意：一个文件活动可能会发生多次，但只计为一个活动文件。 例如，用户可在指定期间多次保存和同步同一文件，但在数据中此文件仅计为一个活跃文件和一个同步文件。 >  如果在指定期间删除了报表上的文件，则报表中显示的活跃文件数可能会超过 OneDrive 中的当前文件数。 >  删除的用户会继续显示在报表中，为期 180 天。<br/>" **已使用的存储 (MB)**"表示 OneDrive 使用的存储量大小，以 MB 计算。 这包括与文件关联的任何版本和元数据。  <br/>  如果组织的策略阻止你查看可识别其中用户信息的报表，你可以更改所有这些报表的隐私设置。 请参阅[Microsoft 365 管理中心预览版中的活动报告](activity-reports.md)中的 "**如何隐藏用户级别详细信息？** " 一节。  <br/> |
|9.  <br/> |选择 "**管理列**" ![图标管理](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png)列以在报告中添加或删除列。  <br/> |
|10.  <br/> |您还可以通过选择 "**导出**" 链接将报告数据导出到 Excel .csv 文件中。 此操作可导出每个 OneDrive 的日期，可方便用户进行简单的排序和筛选，以执行进一步分析。 如果 OneDrive 帐户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果 OneDrive 帐户数量超过 2000，则需要导出数据才能进行筛选和排序。  <br/> 注意：将数据导出到 Excel 文件时，请注意，生成内容报告的日期会反映在 "**数据的**依据" 列中的文件中。  <br/> |
|||
   

