---
title: 管理中心中的 Microsoft 365 报表 - Dynamics 365 客户语音活动
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 了解如何使用 Microsoft 365 管理中心中的 Microsoft 365 报告仪表板获取 Microsoft Dynamics 365 客户语音活动报告。
ms.openlocfilehash: 26d376602caebcb5276b77a3d2c962a14e5fead5
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579646"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>管理中心中的 Microsoft 365 报表 - Dynamics 365 客户语音活动

Microsoft 365 **报表** 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，通过查看每个授权使用 Microsoft Dynamics 365 客户语音的用户与 Dynamics 365 客户语音的交互，可以了解他们的活动。 它还通过查看用户所回复的"专业调查"和"专业调查"数量，帮助您了解进行协作的级别。 
  
> [!NOTE]
> 你必须是 Microsoft 365 中的全局管理员、全局读者或报告读者，或者 Exchange、SharePoint、Teams 服务、Teams 通信或 Skype for Business 管理员才能查看报告。 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>如何访问 Forms Pro 活动报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

    
2. 从"**选择报告"** 下拉列表中，选择 **"Dynamics 365 客户语音** \> **活动"。**

## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>解释 Dynamics 365 客户语音活动报告

通过查看"活动"和"用户"图表，可以查看用户的 Dynamics 365 客户语音活动。 

![表单活动报表](../../media/formsproactivity.png)

|项目|说明|
|:-----|:-----|
|1.  <br/> |可查看 **Dynamics 365 客户语音** 活动报表，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您选择报告中的特定日期，则表 (7) 将显示自当前日期起最多 28 天的数据 (而不是报告生成日期) 。   <br/> |
|2.  <br/> |每个报告中的数据通常与过去 48 小时一样最新。  <br/> |
|3.  <br/> |" **用户** "视图可帮助您了解活动 Dynamics 365 客户语音用户数的趋势。 如果用户已执行特定时间段内围绕专业调查 (创建、编辑、查看等) 活动，则被视为活跃用户。  <br/> |
|4.  <br/> |**"** 活动"视图可帮助您了解活动用户数的趋势。 如果用户在特定期间执行了文件活动（如保存、同步、修改或共享）或访问了页面，则视该用户为活跃用户。<br/> 注意：一个活动对于一个调查可以发生多次，但仅计为一个活动调查。 例如，您可以创建一个专业调查，并指定时段内继续编辑同一调查多次，该调查仅计为一个调查。 <br>|
|5.<br/>|在 **"用户"** 图表上，Y 轴表示唯一用户数。 X 轴是唯一用户处于活动状态的日期。 图例为：<br/><br/>**设计器** 表示用户已创建或编辑了 Dynamics 365 客户语音调查。<br><br>在 **"活动** "图表上，Y 轴表示每个调查的 Dynamics 365 客户语音响应数。 X 轴表示调查或响应活动的发生日期。 图例为：<br/><br/>**创建的调查** 是用户创建的唯一 Dynamics 365 客户语音调查的计数<br>**"** 回复"是收到调查的用户已提交的匿名或非匿名回复的计数。 |
|6.<br/>|通过选择图例中的项目，可以筛选在图表上看到的系列。 例如，在"用户"图表上，选择设计人员、响应者或总计用户，以便仅查看与每个用户有关的信息。 更改此选择不会更改它下面的网格表中的信息。|
|7.<br/>|下表显示了每用户级别的活动细分。 图例为：<br/><br/>**Username** 是在 Microsoft Forms 上执行活动的用户的电子邮件地址。<br/>**上次活动 (UTC)** 表示用户对所选日期范围执行表单活动的最新日期。 要查看指定日期发生的活动，请直接在图表中选择该日期。<br/>这将筛选该表，以仅显示特定天执行活动的用户的文件活动数据。<br/><br/>**创建的调查数** 是用户创建的调查数。<br/> **调查回复数** 是调查分发给的响应者的响应数。|
|8.<br/>|选择" **管理列** "图标以在报表中添加或删除列。|
|9.<br/>|您还可以通过选择"导出"链接将报告数据导出到 Excel .csv **文件中。** 这将导出所有用户的数据，并使您能够执行简单的聚合、排序和筛选以进一步分析。 如果您的用户数少于 100，您可以在报表本身的表中进行排序和筛选。 如果用户数超过 100，则需要导出数据才能进行筛选和排序。|