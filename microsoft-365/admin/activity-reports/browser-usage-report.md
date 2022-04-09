---
title: Microsoft 365 管理中心浏览器使用情况报告
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
description: 了解如何在Microsoft 365 管理中心中使用Microsoft 365报表仪表板获取 Microsoft 浏览器使用情况报告。
ms.openlocfilehash: 32f834874e17376bc1b6fb2188c36f2959f504bf
ms.sourcegitcommit: 46e796c6b76a01516c48977335bbf5076ca74a06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2022
ms.locfileid: "64738222"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-browser-usage"></a>Microsoft 365管理中心中的报表 - Microsoft 浏览器使用情况

Microsoft 365报表仪表板显示组织中各产品的活动概述。 它使你能够深入了解各个产品级别报表，以便更精细地了解每个产品中的活动。 请查看[报表概述主题](activity-reports.md)。 在 Microsoft 浏览器使用情况报告中，可以深入了解 Internet Explorer、Microsoft Edge 旧版 和新的Microsoft Edge使用情况。 使用情况报告基于使用 Microsoft 浏览器访问的Microsoft 365 联机服务。

## <a name="how-to-get-to-the-microsoft-browser-usage-report"></a>如何访问 Microsoft 浏览器使用情况报告

1. 在管理中心，转到 **“报表** \> <b><a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a></b> ”页。

2. 在仪表板主页上，单击 Microsoft 浏览器使用卡上的“ **查看更多** ”按钮。

## <a name="how-to-notify-users-to-upgrade-their-browser"></a>如何通知用户升级其浏览器

:::image type="content" alt-text="Microsoft 浏览器使用情况报告操作流。" source="../../media/1ef4eb08-18b8-4dda-aa15-1aad013ecd70.png" lightbox="../../media/1ef4eb08-18b8-4dda-aa15-1aad013ecd70.png":::

全局管理员可以选择向从 Internet Explorer 访问Microsoft 365服务的用户发送消息， (提醒，Internet Explorer 桌面应用程序将于 2022 年 6 月 15 日停用) 。 此目标消息通知用户，这些浏览器的支持将很快结束，并链接到支持文章，其中包含有关切换浏览器的Microsoft Edge和简单步骤的信息。 

如果你的组织在报表上显示 Internet Explorer 使用情况，则可以在 Microsoft 浏览器使用情况报表页上找到此功能 (所需的全局管理员权限) 。 创建消息后，用户将按指定的频率收到通知，直到 2022 年 6 月 15 日。 可以随时打开或关闭此功能。

这是一项受时间限制的功能，目前仅适用于美国的全局管理员，并允许用户在线Excel通知。

## <a name="interpret-the-microsoft-browser-usage-report"></a>解释 Microsoft 浏览器使用情况报告

:::image type="content" alt-text="Microsoft 浏览器使用情况报告。" source="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png" lightbox="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png":::

|Item|说明|
|:-----|:-----|
|1. |可以查看 **Microsoft 浏览器使用** 情况报告，了解过去 7 天、30 天、90 天或 180 天的趋势。 |
|2. |每个报表中的数据通常最多涵盖过去七天。 |
|3. |**每日活动用户** 图表显示用于访问Microsoft 365服务的Microsoft Edge、Microsoft Edge 旧版和 Internet Explorer 的每日用户计数。 |
|4. |“**活动用户**”图表显示在所选时间段内使用Microsoft Edge、Microsoft Edge 旧版和 Internet Explorer 访问Microsoft 365服务的用户总数。 |
|5. |下表详细显示了每个用户的数据。可在表格中添加或删除列。  <br/><br/>**用户名** 是使用 Microsoft 浏览器连接到Microsoft 365服务的用户的电子邮件地址。<br><br/>如果用户使用Microsoft Edge连接到Microsoft 365服务，**则使用Microsoft Edge** 显示刻度线。<br/><br/>如果用户使用Microsoft Edge 旧版连接到Microsoft 365服务，**则使用** Microsoft Edge 旧版显示刻度线。<br/><br/>如果用户使用 Internet Explorer 连接到Microsoft 365服务，**则使用的 Internet Explorer** 会显示刻度线。 |
|6. |选择 **“选择列”** 图标以添加或删除报表中的列。|
|7. |还可以通过选择“**导** 出”链接将报表数据导出到Excel .csv文件中。 这会为所有用户导出数据，并使你能够进行简单的聚合、排序和筛选以进行进一步分析。 如果用户少于 100，则可以在报表本身的表中进行排序和筛选。 如果用户超过 100 人，若要进行筛选和排序，需要导出数据。|
