---
title: 邮件流仪表板中的未送达报告
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心的邮件流仪表板中的"未送达详细信息"报告来监视未送达报告中最常遇到的错误代码 (也称为来自组织中发件人的NDDR或退回邮件) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: af4beefb8ba15fd7d98b11ec2571eee65a99e4e3
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150155"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>安全与合规中心中的&报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

安全与合规中心的邮件流仪表板[](mail-flow-insights-v2.md)中的未送达报告显示未送达报告（也称为 (报告或退回邮件) 组织中用户遇到次数最多的错误代码。 [&](https://protection.office.com) 此报告显示了 NDR 的详细信息，因此您可以解决电子邮件传递问题。

![安全与合规中心的邮件流仪表板中的"未送达&小组件](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>未送达报告的报告视图

单击" **未送达报告"** 小部件将进入 **未送达报告**。

默认情况下，将显示所有错误代码的活动。 如果单击 **"显示数据"，** 可以从下拉列表中选择特定的错误代码。

如果将鼠标悬停在 (特定) 特定天的错误代码上，则会看到该错误的消息总数。

![非接受域报告中的报告视图](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>未送达报告的详细信息表视图

如果单击 **视图中的"** 查看详细信息报表视图，将显示以下信息：

- "日期"
- **未送达报告代码**
- **Count**
- **示例邮件**：受影响邮件示例的邮件 ID。

如果在 **详细信息表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 

若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"。**

当您在表中选择一行时，将显示一个包含以下信息的飞出图：

- "日期"
- **未送达报告代码**：可以单击链接来查找有关特定错误代码的原因和解决方案的详细信息。
- **Count**
- **示例邮件**：可以单击 **"查看示例邮件** " [以查看受影响邮件](message-trace-scc.md) 示例的邮件跟踪结果。

![在未送达报告中的"详细信息"表视图中选择行后的详细信息飞出](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
