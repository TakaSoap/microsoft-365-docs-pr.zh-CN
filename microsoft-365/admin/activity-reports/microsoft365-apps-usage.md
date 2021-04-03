---
title: 管理中心中的 Microsoft 365 报表 - Microsoft 365 应用版使用情况
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
description: 了解如何使用 Microsoft 365 管理中心中的 Microsoft 365 报表仪表板获取 Microsoft 365 应用版使用情况报告。
ms.openlocfilehash: 362697ba8dd40a12107e1b2d9ad6ef1bededda7d
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579574"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>管理中心中的 Microsoft 365 报表 - Microsoft 365 应用版使用情况

Microsoft 365 **报表** 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。

 例如，通过查看每个许可使用 Microsoft 365 应用应用的用户的活动及其跨平台的利用方式，可了解他们的活动。


 > [!NOTE]
 > 你必须是 Microsoft 365 中的全局管理员、全局读者或报告阅读者，或者 Exchange、SharePoint 或 Skype for Business 管理员才能查看报告。

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>如何访问 Microsoft 365 应用版使用情况报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

 2. 从"**选择报告"** 下拉列表中，选择 **"Office 365**   \>  **Microsoft 365 应用使用情况"。**

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>解释 Microsoft 365 应用版使用情况报告

通过查看用户和平台图表，可以查看用户的 Microsoft 365 应用 **活动**。 

![Microsoft 365 应用版使用情况报告](../../media/proplususagenumbers.png)

|项目|说明|
 |:-----|:-----|
 |1. <br/> |可查看 **Microsoft 365** 应用使用情况报告，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您选择报告中的特定日期，则表 (7) 将显示自当前日期起最多 28 天的数据 (而不是报告生成日期) 。 <br/> |
 |2. <br/> |每个报告中的数据通常涵盖最近七天。 <br/> |
 |3. <br/> |" **用户** "视图显示每个应用的活动用户数趋势 -Outlook、Word、Excel、PowerPoint、OneNote 和 Teams。 "活动用户"是在这些应用中执行任何有意操作的任何用户。 <br/> |
 |4. <br/> |" **平台** "视图显示每个平台的所有应用（Windows、Mac、Web 和移动）中活动用户的趋势。 <br/> |
 |5.<br/>|在 **"用户** "图表上，Y 轴表示相应应用的唯一活动用户数。 在 **"平台**   "图表上，Y 轴表示各个平台的唯一用户数。 两个图表上的 X 轴都是应用在给定平台上使用的日期。<br/>|
 6.<br/>|通过选择图例中的项目，可以筛选在图表上看到的系列。 例如，在"用户 **"图表上** ，选择"Outlook、Word、Excel、PowerPoint、OneDrive"或"Teams"，以便仅查看与每一项有关的信息。 更改此选择不会更改它下面的网格表中的信息。|
 |7.<br/>|下表详细显示了每个用户的数据。 可在表格中添加或删除列。 <br/><br/>**Username** 是在 Microsoft 应用上执行活动的用户的电子邮件地址。<br><br/>**上次激活 (UTC)** 是用户激活其 Microsoft 365 应用版订阅的最近日期。<br/><br/>**上次活动 (UTC)** 是用户执行有意活动的最新日期。 要查看指定日期发生的活动，请直接在图表中选择该日期。<br/><br/>以下列对应于每个应用，用于标识用户在所选时段内是否处于活动状态：<br> <br>**Outlook** <br>**Word** <br>**Excel**<br>**PowerPoint** <br>**OneNote**<br><br> 以下各列对应于每个平台，这些平台标识用户在所选时段内是否 (Microsoft 365 应用版) 处于活动状态：<br><br>**Outlook (Windows)**<br>**Outlook (Mac)**<br>**Outlook (Web)** <br>**Outlook (Mobile)**<br> **Word (Windows)**<br> **Word (Mac)**<br> **Word (Web)**<br> **Word (Mobile)**<br> **Excel (Windows)**<br> **Excel (Mac)**<br> **Excel (Web)**<br> **Excel (Mobile)**<br> **PowerPoint (Windows)**<br> **PowerPoint (Mac)**<br>**PowerPoint (Web)**<br> **PowerPoint (Mobile)**<br> **OneNote (Windows)**<br> **OneNote (Mac)**<br> **OneNote (Web)**<br>**OneNote (Mobile)**<br> **Teams (Windows)**<br> **Teams (Mac)**<br> **Teams (Web)**<br>**Teams (Mobile)** |
 |8.<br/>|选择" **管理列** "图标以在报表中添加或删除列。|
 |9.<br/>|您还可以通过选择"导出"链接将报告数据导出到 Excel .csv **文件中。** 这将导出所有用户的数据，并使您能够执行简单的聚合、排序和筛选以进一步分析。 如果您的用户数少于 100，您可以在报表本身的表中进行排序和筛选。 如果用户数超过 100，则需要导出数据才能进行筛选和排序。|
