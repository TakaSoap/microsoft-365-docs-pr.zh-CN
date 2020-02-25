---
title: Admin center 中的 Office 365 报告-Microsoft 团队设备使用情况
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 917b3e1d-203e-4439-8539-634e80196687
description: 通过从 Office 365 报告中获取 Microsoft 团队应用使用情况报告，深入了解你的组织中使用的 Microsoft 团队应用。
ms.openlocfilehash: 1b337c7e6d7668c708bdd93185e8d0b034a29981
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238232"
---
# <a name="office-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Admin center 中的 Office 365 报告-Microsoft 团队设备使用情况

Office 365**报告**仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。 在 Microsoft Teams 应用使用情况报表中，可深入了解组织中使用的 Microsoft Teams 应用。
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint 或 Skype for Business 管理员的全局管理员、全局读取器或报告阅读器才能查看报告。 
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>如何获取 Microsoft Teams 应用使用情况报表

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

    
2. 从 "**选择报表**" 下拉下，选择 " **Microsoft 团队** \> **设备使用情况**"。
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>解读 Microsoft Teams 应用使用情况报表

通过查看" **用户**"和" **分布**"图表，可了解 Microsoft Teams 应用使用情况。 
  
![Office 365 reports - Microsoft Teams app usage](../media/de35c4de-76b4-4109-a806-66774665499b.png)
  
|||
|:-----|:-----|
|1.  <br/> |可查看" **Microsoft Teams 设备使用情况**"报表，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您在报告中选择某一天，该表（7）将显示从当前日期起的最长28天的数据（而不是报告生成的日期）。  <br/> |
|2.  <br/> |每个报告中的数据通常最长为过去24到48小时。  <br/> |
|3.  <br/> |" **用户**"视图显示各应用的每日不同用户数。  <br/> |
|4.  <br/> |" **分布**"视图显示选定时间段内各应用的不同用户数。  <br/> |
|5.  <br/> | 在" **用户**"图表上，Y 轴表示每个应用的用户数。  <br/>  在" **分布**"图表上，Y 轴表示使用特定应用的用户数。  <br/>  图表的 X 轴都表示为此特定报表选定的日期范围。  <br/> |
|6.  <br/> |您可以通过选择图例中的项目来筛选您在图表上看到的系列。 例如，在 "**用户**" 图表上，选择**Windows**、 **Mac**、**呼叫**、 **Web**、 **Android 手机**或**Windows phone**仅查看与每个相关的信息。 更改选择不会更改网格表中的信息。  <br/> ![您可以通过选择应用程序类型来筛选 Microsoft 团队应用使用情况图表。](../media/64ee1cb1-ca80-4964-8234-7fc671135c3d.png)|
|7.  <br/> | 显示的组列表由最大（180 天）报表时间范围内存在的（未删除）所有组确定。活动计数会因日期选择不同而有所变化。  <br/> 注意：在添加之前，可能无法在列中看到以下列表中的所有项。<br/> " **用户名**"是用户的电子邮件地址。 可以显示实际的电子邮件地址或采用匿名字段。  <br/> " **上次活动日期 (UTC)**"表示用户通过应用参与 Microsoft Teams 活动的最近日期。  <br/> " **已删除**"指示团队是否已被删除。如果团队被删除，但在报告时段中有活动，则将显示在"已删除"设置为 true 的网格中。  <br/> " **删除日期**"是指删除团队的日期。  <br/> " **Windows**"将被选中，前提是指定时间段内用户在 Windows 应用中处于活动状态。  <br/> " **Mac**"将被选中，前提是指定时间段内用户在 Mac 应用中处于活动状态。  <br/> " **Web**"将被选中，前提是指定时间段内用户在 Web 应用中处于活动状态。  <br/> " **iOS**"将被选中，前提是指定时间段内用户在 iOS 应用中处于活动状态。  <br/> " **Android 手机**"将被选中，前提是指定时间段内用户在 Android 手机应用中处于活动状态。  <br/> " **Windows 手机**"将被选中，前提是指定时间段内用户在 Windows Phone 应用中处于活动状态。  <br/>  如果组织的策略阻止你查看显示了可识别用户信息的报表，可更改所有这些报表的隐私设置。 请查看[Microsoft 365 管理中心的活动报告](activity-reports.md)中的 "**如何隐藏用户级别详细信息？** " 一节。  <br/> |
|8.  <br/> |选择要在报告中添加或删除列的**列**。  <br/> ![Teams uapp usage report - choose columns](../media/333f3077-696d-4829-b0a7-1046b3822222.png)|
|9.  <br/> |您还可以通过选择 "**导出**" 链接将报告数据导出到 Excel .csv 文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。  <br/> |
|||
   
  

