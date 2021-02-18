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
description: 管理员可以了解如何使用安全与合规中心的邮件流仪表板中的"未送达详细信息"报告来监视未送达报告 (也称为"NDDR"或"从组织发件人退回邮件) 中最常遇到的错误代码。 &
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e31e7dfcbd3c0cacaa6020464ed315f466a849b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287885"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>安全与合规中心中的&报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

安全与合规中心的"邮件流[](mail-flow-insights-v2.md)"仪表板中的"未送达报告"显示未送达报告（也称为 (或退回邮件) 报告）中遇到次数最多的错误代码。 [&](https://protection.office.com) 此报告显示了 NDR 的详细信息，因此您可以解决电子邮件传递问题。

![安全与合规中心的邮件流仪表板中的"未送达&小组件](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>未送达报告的报告视图

单击" **未送达报告"** 小部件将进入 **未送达报告**。

默认情况下，将显示所有错误代码的活动。 如果单击 **"显示数据"，** 可以从下拉列表中选择特定的错误代码。

如果将鼠标悬停在图表中 (特定) 显示的错误代码上，则会看到该错误的消息总数。

![非接受域报告中的报告视图](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>未送达报告的详细信息表视图

如果单击 **视图中的"** 查看详细信息报表视图，将显示以下信息：

- "日期"
- **未送达报告代码**
- **Count**
- **示例邮件**：受影响邮件示例的邮件的 ID。

如果在 **详细信息表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 

若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"。**

选择表格中的行时，将出现一个包含以下信息的飞出图：

- "日期"
- **未送达报告代码**：可以单击链接来查找有关特定错误代码的原因和解决方案的详细信息。
- **Count**
- **示例邮件**：可以单击 **"查看示例邮件**"以查看受影响 [](message-trace-scc.md)邮件示例的邮件跟踪结果。

![在未送达报告中的"详细信息"表视图中选择行后的详细信息飞出](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
