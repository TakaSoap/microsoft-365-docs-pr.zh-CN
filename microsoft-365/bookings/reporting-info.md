---
title: 报告 Microsoft Bookings 的信息
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: 了解如何查看 Bookings 活动的 4 个月视图
ms.openlocfilehash: ad0a21454cfe28cec521e545e587105e8f8a7454
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887219"
---
# <a name="reporting-info-for-bookings"></a>Bookings 的报告信息

现在，可以在 TSV 文件中查看 Bookings 日历的四个月视图。 TSV 文件将显示四个月的数据，但您可以选择一年中的四个不同的时间段。

此约会级别信息可用于可视化你的 Bookings 日历周围的客户活动。 TSV 文件是制表符分隔值文件。 可以使用任何文本编辑器或电子表格程序（如文本编辑器或电子表格程序）查看或编辑Excel。

## <a name="see-four-months-of-booking-activity"></a>查看四个月的 Booking 活动

1. 在 Bookings 日历仪表板上，选择 **"将更多数据导出为 TSV"。**

:::image type="content" source="../media/bookings-activities.png" alt-text="Screenshot： 4 months of Bookings activity":::

1. 使用新名称保存文件，并指定.xls xlsx 格式。

1. 打开 文件以查看 Bookings 日历的四个月视图。

1. 选择报告的日期，然后选择"导出 **"。**

:::image type="content" source="../media/bookings-reporting-dates.png" alt-text="Screenshot： Pick a time range and export data to TSV file.":::

1. 除了现有字段之外，下载的报告还包含一组新的字段。

报告包括以下字段。

 - **日期与时间**
- **客户名称**
- **客户电子邮件**
- **客户电话**
- **客户地址**
- **竖线**
- **服务**
- **位置**
- **持续时间 (分钟)**
- **事件类型**

改进的报告现在包含以下字段。

- **定价类型**   创建服务时为服务设置的默认定价类型。
- **价格**   与所选定价类型对应的价格。
- **货币**   为企业设置的货币类型。
- **抄送与会者**   将接收预订电子邮件通知的收件人。 在创建预订时，可以从Teams应用中指定。
- **已注册与会者计数**   有多少客户预订了组预订服务。
- **启用文本通知**  客户是否可以接收短信文本相关的通知。
- **自定义域**   与单个预订相关的所有问题和答案都组合在此字段中。
- **预订 ID**   这有助于确定相同的组服务预订。
