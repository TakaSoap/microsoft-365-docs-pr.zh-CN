---
title: 邮件流仪表板中的未送达报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在安全 & 合规性中心中使用邮件流仪表板中的 "未送达详细信息" 报告来监视未送达报告中最常遇到的错误代码 (也称为 "Ndr" 或 "退回邮件") 来自组织中的发件人的邮件。
ms.openlocfilehash: bc530cce54b3d4fd9f414920a8fb58f4322f6b5c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195960"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>安全 & 合规中心中的未送达报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Security & 合规性中心](https://protection.office.com)的[邮件流仪表板](mail-flow-insights-v2.md)中的**未送达报告**显示在未送达报告中遇到的最大错误代码 (也称为 "ndr" 或 "退回邮件") 组织中的用户。 此报告显示 Ndr 的详细信息，以便您可以解决电子邮件传递问题。

![Security & 合规性中心的邮件流仪表板中的未送达报告小部件](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>未送达报告的报告视图

单击 **未送达报告** 小部件将转到 **未送达报告**。

默认情况下，显示所有错误代码的活动。 如果单击 " **显示数据**"，则可以从下拉列表中选择特定的错误代码。

如果将鼠标悬停在特定颜色 (在图表中特定日期) 的错误代码，您将看到错误的邮件总数。

![不接受的域报告中的报告视图](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>未送达报告的详细信息表格视图

如果您在报告视图中单击 " **查看详细信息表** "，将显示以下信息：

- **Date**
- **未送达报告代码**
- **Count**
- **示例邮件**：受影响邮件的示例的邮件 id。

如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。

若要通过电子邮件将特定日期范围的报告发送给一个或多个收件人，请单击 " **请求下载**"。

当您在表中选择一行时，将显示一个包含以下信息的浮出控件：

- **Date**
- **未送达报告代码**：您可以单击链接以查找有关特定错误代码的原因和解决方案的详细信息。
- **Count**
- **示例邮件**：您可以单击 " **查看示例邮件** "，查看有关受影响邮件的示例的 [邮件跟踪](message-trace-scc.md) 结果。

![在未送达报告的 "详细信息表" 视图中选择行后的详细信息浮出控件](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。
