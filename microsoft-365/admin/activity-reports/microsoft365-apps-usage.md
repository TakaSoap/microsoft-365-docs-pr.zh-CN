---
title: Microsoft 365 专业增强版中的报告管理中心-使用情况
ms.author: sirkkuw
author: sirkkuw
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
- MET150
- MOE150
- GEA150
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: 了解如何使用 Microsoft 365 管理中心中的 Microsoft 365 报告仪表板获取使用情况报告的专业增强版。
ms.openlocfilehash: f697b6bcf0ae53c028ce2f13a97b1e11134a6112
ms.sourcegitcommit: 8a88b7526e6a3a907f33a8567e0d25b74fe60d80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43204074"
---
# <a name="microsoft-365-reports-in-the-admin-center---proplus-usage"></a>Microsoft 365 专业增强版中的报告管理中心-使用情况

Microsoft 365 "**报告**" 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，您可以通过查看各个应用程序的活动并在多个平台中使用这些应用程序的活动，了解每个用户使用专业增强版应用程序获得的活动。  
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint 或 Skype for Business 管理员的全局管理员、全局读取器或报告阅读器才能查看报告。 

## <a name="how-to-get-to-the-proplus-usage-report"></a>如何获取专业增强版使用情况报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

    
2. 从 "**选择报表**" 下拉下，选择 " **Office 365** \> **专业增强版使用情况**"。

## <a name="interpret-the-proplus-usage-report"></a>解释专业增强版使用情况报告

您可以通过查看 "**用户**" 和 "**平台**" 图表，获取用户的专业增强版活动的视图。 

![专业增强版使用情况报告](../../media/proplususagenumbers.png)

|||
|:-----|:-----|
|1.  <br/> |可以查看 "**专业增强版使用率**" 报表，了解过去7天、30天、90天或180天的趋势。 但是，如果您在报告中选择某一天，该表（7）将显示从当前日期起的最长28天的数据（而不是报告生成的日期）。  <br/> |
|2.  <br/> |每个报告中的数据通常最长为过去24到48小时。  <br/> |
|3.  <br/> |**Users** view iew 显示了每个应用程序（Outlook、Word、Excel、PowerPoint、OneNote 和团队）的活动用户数的趋势。 "活动用户" 是在这些应用程序中执行任何故意操作的任何人。  <br/> |
|4.  <br/> |"**平台**" 视图显示每个平台（Windows、Mac、Web 和移动设备）上的每个应用程序的活动用户的趋势。 <br/> |
|5.<br/>|在 "**用户**" 图表上，Y 轴表示各个应用程序的唯一活动用户数。 在 " **平台** " 图表中，Y 轴表示各个平台的唯一用户数。 这两个图表的 X 轴都是在给定平台上使用应用程序的日期。<br/>|
|6.<br/>|您可以通过选择图例中的项目来筛选您在图表上看到的系列。 例如，在 "**用户**" 图表上，选择 "Outlook"、"Word"、"Excel"、"PowerPoint"、"OneDrive" 或 "团队"，仅查看与每个相关的信息。 更改此选择不会更改下方的网格表中的信息。|
|7.<br/>|下表详细显示了每个用户的数据。 可在表格中添加或删除列。 <br/><br/>**Username**是在 Microsoft 应用上执行活动的用户的电子邮件地址。<br><br/>"**上次激活日期（UTC）** " 是用户激活其专业增强版订阅的最晚日期。<br/><br/>"**上次活动日期（UTC）** " 是用户有意执行的活动的最晚日期。 要查看指定日期发生的活动，请直接在图表中选择该日期。<br/><br/>与每个应用程序对应的以下各列，这些应用程序标识用户是否在选定时间段内处于活动状态的应用程序：<br> <br>**Outlook** <br>**Word** <br>**Excel**<br>**PowerPoint** <br>**OneNote**<br><br> 与每个平台对应的以下各列，这些列确定用户是否在所选时间段内的任何应用程序（专业增强版中的任何应用程序）上都处于活动状态：<br><br>**Outlook （Windows）**<br>**Outlook （Mac）**<br>**Outlook （Web）** <br>**Outlook （移动版）**<br> **Word （Windows）**<br> **Word （Mac）**<br> **Word （Web）**<br> **Word （移动版）**<br> **Excel （Windows）**<br> **Excel （Mac）**<br> **Excel （Web）**<br> **Excel （移动）**<br> **PowerPoint （Windows）**<br> **PowerPoint （Mac）**<br>**PowerPoint （Web）**<br> **PowerPoint （移动版）**<br> **OneNote （Windows）**<br> **OneNote （Mac）**<br> **OneNote （Web）**<br>**OneNote （移动）**<br> **团队（Windows）**<br> **团队（Mac）**<br> **团队（Web）**<br>**团队（移动）** |
|8.<br/>|选择 "**管理列**" 图标可在报表中添加或删除列。|
|9.<br/>|您还可以通过选择 "**导出**" 链接将报告数据导出到 Excel .csv 文件中。 这将导出所有用户的数据，并使您能够执行简单的聚合、排序和筛选以进行进一步分析。 如果用户少于100，则可以在报表本身的表中对表进行排序和筛选。 如果用户数超过100，则需要导出数据，才能对其进行筛选和排序。|