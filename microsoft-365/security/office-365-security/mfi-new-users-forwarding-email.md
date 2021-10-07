---
title: 新用户转发电子邮件见解
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: ''
description: 管理员可以了解如何使用安全与合规中心中的"新用户转发电子邮件见解&调查其组织中用户何时将邮件转发到新域。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e5ec29849c50f8d012de1886e997b67f1f191ee
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176531"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>新用户在安全与合规中心&电子邮件见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

当组织中新的用户帐户突然开始将电子邮件转发到外部域时，这是可疑的。

安全 **与合规** 中心内 [&](https://protection.office.com) 转发的电子邮件见解的新域在组织中新创建的用户将邮件转发到外部域时通知你。 此条件可能指示已使用遭到入侵的管理员帐户创建新用户。 如果您怀疑帐户已被泄露，请参阅响应遭到入侵 [的电子邮件帐户](responding-to-a-compromised-email-account.md)。

此见解仅在检测到问题时显示，并且显示在"转发 [报告"页上](view-mail-flow-reports.md#forwarding-report) 。

![新用户转发电子邮件见解。](../../media/mfi-new-users-forwarding-email.png)

单击小部件时，将出现一个飞出控件，您可以在其中找到有关转发邮件的更多详细信息，包括指向本文稍后所述的转发修改报告[](#forwarding-modifications-report)的链接。

![详细信息 在单击"新用户转发电子邮件见解"后出现的飞出图。](../../media/mfi-new-users-forwarding-email-details.png)

单击"报告仪表板"或"仪表板"上的"热门见解&建议"区域中的"查看全部"后，选择见解后， (**访问** 此 \>  <https://protection.office.com/insightdashboard> 详细信息) 。

可以单击" **查看与见解关联的** 报告"链接转到"转发修改" **报告，如下** 一节中所述。

## <a name="forwarding-modifications-report"></a>转发修改报告

转发 **修改报告显示** 有关自动转发自组织中发件人的邮件的详细信息：

- 将邮件转发到外部域的新创建的帐户。
- 将邮件转发到组织中其他发件人从未转发给的外部域的帐户。

这些类型的转发邮件可能会带来安全或合规性风险，并可能指示帐户遭到入侵。

该报告包含最多 90 天的数据。 默认情况下，报告显示最近 7 天的数据。

此报告不直接在邮件流仪表板或[报表仪表板](mail-flow-insights-v2.md)[中提供](view-mail-flow-reports.md)。 除了单击"新用户转发电子邮件见解"中的"查看与见解关联的报告"链接，您还可以通过以下操作访问报告：

- 单击 **"正在转发的新** 域"电子邮件见解的详细信息中的 ["转发通知报告"链接](mfi-new-domains-being-forwarded-email.md)。
- 打开 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 。

### <a name="report-view-for-the-forwarding-modifications-report"></a>转发修改报告的报表视图

下表中提供了以下报表视图：

- **显示数据：新转发用户**：

  ![转发修改报告中的新转发用户视图。](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **显示数据：新转发域**：

  ![转发修改报告中的新转发域视图。](../../media/forwarding-modifications-report-new-forwarded-domains.png)

如果 **单击筛选器中的** 报表视图，可以指定开始日期和 **结束日期的日期范围**。 

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>转发修改报告的详细信息表视图

如果单击 **"查看详细信息表**"，显示的信息取决于您所查看的图表：

- **显示数据：新转发用户**：

  - **名称**：发件人的电子邮件地址。
  - **转发类型**
  - **收件人地址**
  - **详细信息**
  - **Count**
  - **第一个转发日期**

- **显示数据：新转发域**：

  - **名称**：发件人的电子邮件域。
  - **转发类型**
  - **收件人地址**
  - **详细信息**
  - **Count**
  - **第一个转发日期**

如果在详细信息 **表** 视图中单击筛选器，可以指定开始日期和 **结束日期的日期范围**。 

如果从表中选择一行，将显示"详细信息"飞出，并包含以下信息：

- 名称：这是发件人的电子邮件地址 ("显示数据：新建转发用户查看) "或发件人的电子邮件域 (from **Show data for： New forwarding domains** view) 。 
- **转发类型**
- **收件人**
- **详细信息**
- **Count**
- **开始日期**
- **建议**：你可以从此处单击链接来管理用户Microsoft 365 管理中心。

!["转发修改"报告中"新建转发用户"视图的详细信息表中的"详细信息"飞出。](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

若要返回到报告视图，请单击"查看 **报告"。**

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。
