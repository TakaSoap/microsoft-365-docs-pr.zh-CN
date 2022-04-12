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
description: 了解如何使用Microsoft 365 管理中心中的Microsoft 365报表仪表板获取使用情况报表的Microsoft 365 应用版。
ms.openlocfilehash: 229797921de2e24754203efc466f63661eb26bc8
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781602"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Microsoft 365管理中心中的报表 - Microsoft 365 应用版用法

Microsoft 365报表仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。

例如，通过查看每个用户跨应用的活动以及如何跨平台使用应用，可以了解每个获得许可使用Microsoft 365 应用版应用的用户的活动。

> [!NOTE]
> 此报表中不包括共享计算机激活。

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>如何访问Microsoft 365 应用版使用情况报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击活动用户上的 **“查看更多**”按钮 - Microsoft 365 应用版卡。

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>解释Microsoft 365 应用版使用情况报告

可以通过查看 **“用户**”和“**平台**”图表来查看用户Microsoft 365 应用版活动。

> [!div class="mx-imgBorder"]
> ![Microsoft 365 应用版使用情况报告。](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

|Item|说明|
|---|---|
|1.|可以查看 **Microsoft 365 应用版使用** 情况报告，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果在报表中选择特定日期，表将显示自当前日期（而不是生成报 (表) 日期）最多 28 天的数据。|
|2.|每个报表中的数据通常最多涵盖过去两天。 每六天，我们将使用次要更新刷新报表，以确保数据质量。|
|3.|“**用户**”视图显示每个应用的活动用户数的趋势 - Outlook、Word、Excel、PowerPoint、OneNote 和Teams。 “活动用户”是在这些应用中执行任何有意操作的任何用户。|
|4.|“**平台**”视图显示每个平台的所有应用（Windows、Mac、Web 和移动）中活动用户的趋势。|
|5.|在 **“用户** ”图表上，Y 轴是相应应用的唯一活动用户数。 在 **平台** 图上，Y 轴是相应平台的唯一用户数。 两个图表上的 X 轴是在给定平台上使用应用的日期。|
 6.|可以通过在图例中选择一个项目来筛选在图表上看到的系列。 例如，在 **“用户**”图表上，选择“Outlook”、“Word”、“Excel”、“PowerPoint”、“OneDrive”或“Teams”，以仅查看与每个信息相关的信息。 更改此选择不会更改下方网格表中的信息。|
|7.|下表详细显示了每个用户的数据。可在表格中添加或删除列。  <br/><br/>**用户名** 是在Microsoft Apps上执行活动的用户的电子邮件地址。<br><br/>**上次激活日期 (UTC)** 是用户在计算机上激活其Microsoft 365 应用版订阅或在共享计算机上登录并使用其帐户启动应用的最新日期。 <br/><br/>**UTC)  (活动日期** 是用户执行有意活动的最新日期。 要查看指定日期发生的活动，请直接在图表中选择该日期。<br/><br/>其他列确定该应用的用户是否在该平台上处于活动状态， (在所选时间段内Microsoft 365 应用版) 。|
|8.|选择 **“选择列”** 图标以添加或删除报表中的列。|
|9.|还可以通过选择“**导** 出”链接将报表数据导出到Excel .csv文件中。 这会为所有用户导出数据，并使你能够进行简单的聚合、排序和筛选以进行进一步分析。 如果用户少于 100，则可以在报表本身的表中进行排序和筛选。 如果用户超过 100 人，若要进行筛选和排序，需要导出数据。|
