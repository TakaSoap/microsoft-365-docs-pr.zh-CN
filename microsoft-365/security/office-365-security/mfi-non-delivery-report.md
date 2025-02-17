---
title: 邮件流仪表板中的未送达报告
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心的邮件流仪表板中的"未送达详细信息"报告来监视未送达报告 (也称为"未送达报告"中最常遇到的错误代码或退回组织中发件人的邮件) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bc408f6bb28b11e77c49755b888c44e0ea4d9f57
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473730"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>安全与合规中心&未送达报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

安全与合规中心内"邮件[](mail-flow-insights-v2.md)流"仪表板中的"未送达报告"显示未送达报告 (也称为"未送达报告"或"退回邮件) "中遇到的错误代码（对于组织用户）。 [&](https://protection.office.com) 此报告显示了 NDR 的详细信息，因此您可以解决电子邮件传递问题。

:::image type="content" source="../../media/mfi-non-delivery-report-widget.png" alt-text="安全与合规中心内&quot;邮件流&quot;仪表板中的&quot;未送达&小组件" lightbox="../../media/mfi-non-delivery-report-widget.png":::

## <a name="report-view-for-the-non-delivery-report"></a>未送达报告的报告视图

单击" **未送达报告"** 小部件将进入 **未送达报告**。

默认情况下，将显示所有错误代码的活动。 If you click **Show data for**， you can select a specific error code from the dropdown.

如果将鼠标悬停在图表中 (特定) 显示的错误代码，你将看到该错误的消息总数。

:::image type="content" source="../../media/mfi-non-delivery-report-overview-view.png" alt-text="未接受域报告中的&quot;报告&quot;视图" lightbox="../../media/mfi-non-delivery-report-overview-view.png":::

## <a name="details-table-view-for-the-non-delivery-report"></a>未送达报告的详细信息表视图

如果单击 **视图中的"** 查看详细信息报表视图，将显示以下信息：

- **Date**
- **未送达报告代码**
- **Count**
- **示例邮件**：受影响邮件示例的邮件 ID。

如果在详细信息 **表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。

若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"**。

选择表格中的行时，将显示一个包含以下信息的飞出图：

- **Date**
- **未送达报告代码**：可以单击链接来查找有关特定错误代码的原因和解决方案的详细信息。
- **Count**
- **示例邮件**：可以单击 **"查看示例** 邮件" [以查看受影响邮件](message-trace-scc.md) 示例的邮件跟踪结果。


:::image type="content" source="../../media/mfi-non-delivery-report-details-flyout.png" alt-text="The Details flyout after selecting a row in Details table view in the Non-delivery report" lightbox="../../media/mfi-non-delivery-report-details-flyout.png":::

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。
