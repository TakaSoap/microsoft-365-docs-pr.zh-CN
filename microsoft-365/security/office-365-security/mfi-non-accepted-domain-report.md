---
title: 邮件流仪表板中的未接受域报告
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心的邮件流仪表板中的"未接受的域"报告监视来自未在 Microsoft 365 中配置发件人域内部部署组织的邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b698600cb3fbc85ec86bed4da542d23fe5eb17e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169463"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>安全与合规中心中的未接受&报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

安全与合规中心内邮件流仪表板[](mail-flow-insights-v2.md)中的"非接受域"报告显示有关来自内部部署电子邮件组织的邮件的信息，其中发件人的域未配置为 Microsoft 365 组织中接受的域。 [&](https://protection.office.com)

Microsoft 365有数据可以证明这些邮件的意图是恶意的，则系统可能会限制这些邮件。 因此，了解发生的情况并解决该问题非常重要。

![安全与合规中心的"邮件流"仪表板中的"非接受&小组件。](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>未接受域报告的报告视图

单击"非接受 **域"小部件上的** 图表将进入 **"未接受域"** 报告。

默认情况下，将显示所有受影响的连接器的活动。 If you click **Show data for**， you can select a specific connector from the dropdown.

如果将鼠标悬停在图表中 () 的数据点上，则会看到连接器的邮件总数。

![未接受域报告中的报告视图。](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>未接受域报告的详细信息表视图

如果单击 **视图中的"** 查看详细信息"报表视图，将显示以下信息：

- **Date**
- **入站连接器名称**
- **发件人域**
- **邮件计数**
- **示例邮件**：受影响邮件示例的邮件 ID。

如果在详细信息 **表** 视图中单击筛选器，可以指定开始日期和 **结束日期的日期范围**。 

若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"。**

选择表格中的行时，将显示一个包含以下信息的飞出图：

- **日期**
- **入站连接器名称**
- **发件人域**
- **邮件计数**
- **示例邮件**：可以单击 **"查看示例** 邮件"以查看 [受影响邮件](message-trace-scc.md) 示例的邮件跟踪结果。

![在"未接受域"报告中的"详细信息"表视图中选择一行后，详细信息飞出。](../../media/mfi-non-accepted-domain-report-details-flyout.png)

若要返回到报告视图，请单击"查看 **报告"。**

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。
