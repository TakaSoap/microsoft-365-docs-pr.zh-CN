---
title: 管理中心中的 Microsoft 365 报表-Forms Pro 活动
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 了解如何使用 microsoft 365 管理中心中的 Microsoft 365 报告仪表板获取 Microsoft Forms Pro 活动报告。
ms.openlocfilehash: df03f3f0300dcd923f43987ee786981b1653b1ce
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387701"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-pro-activity"></a>管理中心中的 Microsoft 365 报表-Forms Pro 活动

Microsoft 365 "**报告**" 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，您可以通过查看用户与 Forms Pro 的交互来了解使用 Microsoft Forms Pro 的每个用户的活动。 它还可以通过查看创建的 Pro 调查数和用户响应的 Pro 调查，来帮助您了解协作的级别。 
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint、团队服务、团队通信或 Skype for Business 管理员中的全局管理员、全局读取器或报告阅读器才能查看报告。 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>如何获取表单 Pro 活动报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

    
2. 从 "**选择报表**" 下拉下，选择 " **Forms Pro** \> **活动**"。

## <a name="interpret-the-forms-activity-report"></a>解释表单活动报告

您可以通过查看 "**活动**" 和 "**用户**" 图表，获取用户的 Forms Pro 活动的视图。 

![表单活动报告](../../media/formsproactivity.png)

|||
|:-----|:-----|
|1.  <br/> |可以查看 " **Forms Pro**活动" 报表，了解过去7天、30天、90天或180天的趋势。 但是，如果您在报告中选择某一天，该表（7）将显示从当前日期起的最长28天的数据（而不是报告生成的日期）。   <br/> |
|2.  <br/> |每个报告中的数据通常在最近的48小时内。  <br/> |
|3.  <br/> |"**用户**" 视图可帮助您了解活动的 Forms Pro 用户数的趋势。 如果用户已在特定时间段内按照 Pro 调查（创建、编辑、查看等）执行了活动，则认为该用户处于活动状态。  <br/> |
|4.  <br/> |"**活动**" 视图可帮助您了解活动用户数的趋势。 如果用户在特定期间执行了文件活动（如保存、同步、修改或共享）或访问了页面，则视该用户为活跃用户。<br/> 注意：一个活动可以多次发生一次调查，但只计为一个活动调查。 例如，您可以创建一个 Pro 调查，并在指定的时间段内继续多次编辑同一调查，它只计为一个单个调查。 <br>|
|5.<br/>|在 "**用户**" 图表上，Y 轴表示唯一用户数。 X 轴是唯一用户处于活动状态的日期。 图例为：<br/><br/>**设计器**意味着用户已创建或编辑了 Forms Pro 调查。<br><br>在 "**活动**" 图表中，Y 轴表示每个调查的 Forms Pro 响应数。 X 轴表示调查或响应活动发生的日期。 图例为：<br/><br/>所**创建的调查**是用户创建的独特表单专业调查的计数<br>**响应**是接收调查的用户提交的匿名或非匿名响应的计数。 |
|6.<br/>|您可以通过选择图例中的项目来筛选您在图表上看到的系列。 例如，在 "用户" 图表上，选择 "设计器"、"响应者" 或 "总用户"，仅查看与每个用户相关的信息。 更改此选择不会更改下方的网格表中的信息。|
|7.<br/>|该表显示了每个用户级别的活动细目。图例为：<br/><br/>**Username**是在 Microsoft Forms 上执行活动的用户的电子邮件地址。<br/>"**上次活动日期（UTC）** " 是用户在所选日期范围内执行表单活动的最晚日期。 要查看指定日期发生的活动，请直接在图表中选择该日期。<br/>此操作将筛选表，以便仅为在特定日期执行活动的用户显示文件活动数据。<br/><br/>**创建的调查数**是用户创建的调查数。<br/> **调查响应数**是调查向其分发到的响应者的响应数。|
|8.<br/>|选择 "**管理列**" 图标可在报表中添加或删除列。|
|9.<br/>|您还可以通过选择 "**导出**" 链接将报告数据导出到 Excel .csv 文件中。 这将导出所有用户的数据，并使您能够执行简单的聚合、排序和筛选以进行进一步分析。 如果用户少于100，则可以在报表本身的表中对表进行排序和筛选。 如果用户数超过100，则需要导出数据，才能对其进行筛选和排序。|