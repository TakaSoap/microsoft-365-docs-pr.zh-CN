---
title: 报告 Microsoft Bookings 的信息
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: 了解如何查看Bookings活动的 4 个月视图
ms.openlocfilehash: 191194d112fe231c1a2f64245d33850ecb1266c0
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64714298"
---
# <a name="reporting-info-for-bookings"></a>报告Bookings信息

> [!NOTE]
> 本文可帮助你与最新版本的Microsoft Bookings交互。 以前的版本将在未来几个月内停用。

现在可以在 TSV 文件中查看Bookings日历的四个月视图。 TSV 文件将显示四个月的数据，但一年内可以选择不同的四个月时间段。

此约会级别信息可用于可视化Bookings日历周围的客户活动。 TSV 文件是选项卡分隔的值文件。 可以使用任何文本编辑器或电子表格程序（例如Excel）查看或编辑此类文件。

## <a name="see-four-months-of-booking-activity"></a>查看四个月的预订活动

1. 在Microsoft 365中，选择应用启动器，然后选择 **Bookings**。

1. 在Bookings主页上，选择 **"导出**"。

1. 在" **导出最近的数据** "页上，选择日期范围，然后选择 **"导出**"。

1. 使用新名称保存文件，并指定.xls或 xlsx 格式。

1. 打开文件，查看Bookings日历的四个月视图。

1. 选择报表的日期，然后选择 **"导出**"。

1. 除了现有字段之外，下载的报表还包含一组新的字段。

报表包含以下字段。

 - **日期与时间**
- **客户名称**
- **客户电子邮件**
- **客户电话**
- **客户地址**
- **竖线**
- **服务**
- **Location**
- **持续时间 (分钟)**
- **事件类型**

改进后的报表现在包含以下字段。

- **定价类型**   创建服务时为服务设置默认定价类型。
- **价格**   与所选定价类型相对应的价格。
- **货币**   为企业设置货币类型。
- **Cc 与会者**   接收预订电子邮件通知的收件人。 创建预订时，可以从Teams应用指定此值。
- **注册与会者计数**   有多少客户预订了组预订服务。
- **已启用文本通知**   客户是否可以接收与短信相关的通知。
- **自定义字段**   此字段中将与单个预订相关的所有问题和答案组合在一起。
- **预订 ID**   这有助于识别组服务的相同预订。
