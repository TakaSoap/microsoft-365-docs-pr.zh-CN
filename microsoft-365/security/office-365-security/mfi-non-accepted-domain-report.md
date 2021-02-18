---
title: 邮件流仪表板中的未接受域报告
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
description: 管理员可以了解如何使用安全与合规中心的邮件流仪表板中的"未接受的域"报告监视来自未在 Microsoft 365 中配置发件人域内部部署组织的邮件。 &
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6d7355af49c5810a593c5776b70cf7497b43af6b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287861"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>安全与合规中心内&域报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

安全与合规中心的邮件流仪表板中的[](mail-flow-insights-v2.md)"未接受域"报告显示有关来自内部部署电子邮件组织的邮件的信息，其中发件人的域未配置为 Microsoft 365 组织中接受的域。 [&](https://protection.office.com)

如果我们有数据可以证明这些邮件的意图是恶意的，Microsoft 365 可能会限制这些邮件。 因此，了解发生的情况并解决此问题非常重要。

![安全与合规中心中邮件流仪表板中的&小组件](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>非接受域报告的报告视图

单击"非接受域 **"小部件上的** 图表将进入 **非接受域** 报告。

默认情况下，将显示所有受影响的连接器的活动。 如果单击 **"显示数据"，** 可以从下拉列表中选择特定连接器。

如果将鼠标悬停在图表中 () 的数据点上，则会看到连接器的邮件总数。

![非接受域报告中的报告视图](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>非接受域报告的详细信息表视图

如果单击 **视图中的"** 查看详细信息报表视图，将显示以下信息：

- "日期"
- **入站连接器名称**
- **发件人域**
- **邮件计数**
- **示例邮件**：受影响邮件示例的邮件的 ID。

如果在 **详细信息表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 

若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"。**

在表中选择一行时，将出现一个包含以下信息的飞出图：

- "日期"
- **入站连接器名称**
- **发件人域**
- **邮件计数**
- **示例邮件**：可以单击 **"查看示例邮件**"以查看受影响 [](message-trace-scc.md)邮件示例的邮件跟踪结果。

![在"非接受域"报告中的"详细信息"表视图中选择行后的详细信息飞出](../../media/mfi-non-accepted-domain-report-details-flyout.png)

若要返回到报告视图，请单击"**查看报告"。**

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
