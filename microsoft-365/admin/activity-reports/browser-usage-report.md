---
title: Microsoft 365管理中心中的报告 - Microsoft 浏览器使用情况
ms.author: waxiaoyu
author: sarahwxy
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
description: 了解如何使用 Microsoft 365 管理中心 中的"报告"Microsoft 365 Microsoft 浏览器使用情况Microsoft 365 管理中心。
ms.openlocfilehash: f7878ddaef778c3a8a751f0ab1765df26b7c3a58
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156038"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-browser-usage"></a>Microsoft 365管理中心中的报告 - Microsoft 浏览器使用情况

"Microsoft 365 **报表**"仪表板显示组织中各产品的活动概述。 它使您能够深入了解各个产品级别报告，从而更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。 在 Microsoft 浏览器使用情况报告中，可以深入了解Internet Explorer、Microsoft Edge 旧版和新的Microsoft Edge使用情况。 使用率报告基于Microsoft 365 Microsoft 浏览器访问的联机服务。

> [!NOTE]
> 您必须是全局管理员、全局读者或报表的读者Microsoft 365或 Exchange、SharePoint 或 Skype for Business 管理员才能查看报告。

## <a name="how-to-get-to-the-microsoft-browser-usage-report"></a>如何访问 Microsoft 浏览器使用情况报告

1. 在管理中心，转到"报告 **使用情况** \> <b><a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">"</a></b> 页。

2. 在仪表板主页上，单击 Microsoft浏览器使用卡上的"查看更多"按钮。

## <a name="how-to-notify-users-to-upgrade-their-browser"></a>如何通知用户升级其浏览器

:::image type="content" alt-text="Microsoft 浏览器使用情况报告操作流。" source="../../media/1ef4eb08-18b8-4dda-aa15-1aad013ecd70.png" lightbox="../../media/1ef4eb08-18b8-4dda-aa15-1aad013ecd70.png":::

全局管理员可以选择向使用 Edge 旧版 (不支持的 Microsoft 365 服务的用户发送邮件，) Internet Explorer (即将不受支持) 。 此定向消息通知用户，支持这些浏览器的用户将很快发送相关链接，并链接到包含有关 Microsoft Edge 的信息以及切换浏览器要遵循的简单步骤的支持文章。 

您可以在报告页上找到此功能。 创建邮件后，用户将以指定的频率收到通知，直到 2021 年 8 月 17 日。 你随时可以关闭此功能以停止向用户发送通知。 若要再次开始发送通知，请重新启用该功能。

## <a name="interpret-the-microsoft-browser-usage-report"></a>解释 Microsoft 浏览器使用情况报告

:::image type="content" alt-text="Microsoft 浏览器使用情况报告。" source="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png" lightbox="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png":::

|项目|说明|
|:-----|:-----|
|1. |可查看 **Microsoft 浏览器使用情况** 报告，了解过去 7 天、30 天、90 天或 180 天的趋势。 |
|2. |每个报告中的数据通常涵盖最近七天。 |
|3. |"**每日活动用户** 数"图显示用于访问 Microsoft Edge、Microsoft Edge 旧版 Internet Explorer 服务的用户Microsoft 365计数。 |
|4. |"**活动用户**"图显示在选定时段内Microsoft Edge、Microsoft Edge 旧版 和 Internet Explorer 访问 Microsoft 365 服务的用户总数。 |
|5. |下表详细显示了每个用户的数据。可在表格中添加或删除列。  <br/><br/>**Username** 是使用 Microsoft 浏览器连接到 Microsoft 365服务的用户的电子邮件地址。<br><br/>**Used Microsoft Edge** shows a tick mark if the user used Microsoft Edge to connect to Microsoft 365 services.<br/><br/>**Used Microsoft Edge 旧版** 显示一个刻度线（如果用户Microsoft Edge 旧版连接到 Microsoft 365 服务）。<br/><br/>**Used Internet Explorer** user used to connect to Internet Explorer to connect to Microsoft 365 a tick mark. |
|6. |选择" **选择列** "图标以在报表中添加或删除列。|
|7. |您还可以通过选择"导出"链接将报告数据导出到Excel .csv文件。  这将导出所有用户的数据，并使您能够执行简单的聚合、排序和筛选以进一步分析。 如果您的用户数少于 100，您可以在报表本身的表中进行排序和筛选。 如果用户数超过 100，则需要导出数据才能进行筛选和排序。|
