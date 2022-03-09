---
title: Microsoft 365 管理中心应用使用情况报告
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 了解如何使用 Microsoft 365 应用版 中的"报表"仪表板Microsoft 365报表报表Microsoft 365 管理中心。
ms.openlocfilehash: c7a8e5bbf2fec8450b52b3cbe52e110d97061ed3
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2022
ms.locfileid: "63400819"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Microsoft 365中心中的报告 - Microsoft 365 应用版使用情况

"Microsoft 365报表"仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。

 例如，你可以了解每个许可使用 Microsoft 365 应用版 应用的用户的活动，通过查看其跨应用的活动以及如何跨平台使用这些活动。
 
 > [!NOTE]
 > 此报告中不包括共享计算机激活。

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>如何获取Microsoft 365 应用版使用情况报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击"活动 **用户** - 浏览"卡片上的"查看更多Microsoft 365 应用版按钮。

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>解释Microsoft 365 应用版使用情况报告

通过查看用户和平台图表，Microsoft 365 应用版 **用户的活动****。**

> [!div class="mx-imgBorder"]
> ![Microsoft 365 应用版使用情况报告。](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

|Item|说明|
 |:-----|:-----|
 |1. <br/> |可查看 **Microsoft 365 应用版** 使用情况报告，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您选择报告中的某一天，则该表将显示自当前日期起最多 28 天的数据 (而不是报告生成日期) 。 <br/> |
 |2. <br/> |每个报告中的数据通常涵盖最近两天。 每六天，我们将使用次要更新刷新报告，以确保数据质量。 <br/> |
 |3. <br/> |"**用户**"视图显示每个应用的活动用户数（Outlook、Word、Excel、PowerPoint、OneNote 和 Teams）。 "活动用户"是在这些应用中执行任何有意操作的任何用户。 <br/> |
 |4. <br/> |"**平台**"视图显示每个平台的所有应用（如 Windows、Mac、Web 和 Mobile）中活动用户的趋势。 <br/> |
 |5.<br/>|在 **"用户** "图表上，Y 轴表示相应应用的唯一活动用户数。 在 **Platformschart** 上，Y 轴表示各个平台的唯一用户数。 两个图表上的 X 轴都是应用在给定平台上使用的日期。<br/>|
 6.<br/>|通过选择图例中的项目，可以筛选在图表上看到的系列。 例如，在"用户"图表上，选择"Outlook、Word、Excel、PowerPoint、OneDrive 或 Teams"来仅查看与每一个相关的信息。 更改此选择不会更改它下面的网格表中的信息。|
 |7.<br/>|下表详细显示了每个用户的数据。可在表格中添加或删除列。  <br/><br/>**Username** 是在活动上执行活动的用户Microsoft Apps。<br><br/>**上次激活 (UTC)** 是用户在计算机上激活其 Microsoft 365 应用版 订阅或登录共享计算机，然后使用其帐户启动应用的最新日期。 <br/><br/>**UTC (活动)** 是用户执行有意活动的最新日期。 要查看指定日期发生的活动，请直接在图表中选择该日期。<br/><br/>其他列标识用户在该应用的该平台上是否处于活动状态， (在Microsoft 365 应用版) 内处于活动状态。 |
 |8.<br/>|选择" **选择列** "图标以在报表中添加或删除列。|
 |9.<br/>|您还可以通过选择"导出"链接将报告数据导出到Excel .csv文件。 这将导出所有用户的数据，并使您能够执行简单的聚合、排序和筛选以进一步分析。 如果您的用户数少于 100，您可以在报表本身的表中进行排序和筛选。 如果用户数超过 100，则需要导出数据才能进行筛选和排序。|
