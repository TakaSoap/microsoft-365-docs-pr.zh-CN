---
title: 新用户转发电子邮件见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解如何使用安全与合规中心内的新用户转发电子邮件见解&调查其组织中用户何时将邮件转发到新域。
ms.openlocfilehash: cf1852169279e19ac00e5e29dd1c26e155936039
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660013"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>新用户在安全与合规中心转发&见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


当组织的新用户帐户突然开始将电子邮件转发到外部域时，这是可疑的。

当 **组织中新** 创建的用户将邮件转发 [到](https://protection.office.com) 外部域时&安全与合规中心中转发的电子邮件见解的新域会通知你。 此条件可能指示已使用遭到入侵的管理员帐户创建新用户。 如果怀疑帐户已被泄露，请参阅"响应遭到入侵[的电子邮件帐户"。](responding-to-a-compromised-email-account.md)

此见解仅在检测到问题时显示，并且显示在"转发 [报告"页上](view-mail-flow-reports.md#forwarding-report) 。

![新用户转发电子邮件见解](../../media/mfi-new-users-forwarding-email.png)

单击小部件时，将出现一个飞出控件，您可以在其中找到有关转发邮件的更多详细信息，包括指向本文稍后介绍的转发修改[](#forwarding-modifications-report)报告的链接。

![单击"新用户"转发电子邮件见解后显示的详细信息飞出](../../media/mfi-new-users-forwarding-email-details.png)

在报表仪表板或仪表板上单击"查看所有热门见解"&建议区域中的见解后，**还可以进入** (\> 页面 <https://protection.office.com/insightdashboard>) 。

可以单击"**查看与见解关联的** 报告"链接，转到下一节中所述的转发修改报告。

## <a name="forwarding-modifications-report"></a>转发修改报告

" **转发修改"报告显示** 有关自动从组织中发件人转发的邮件的详细信息：

- 将邮件转发到外部域的新创建帐户。
- 将邮件转发到组织中其他发件人从未转发到的外部域的帐户。

这些类型的转发邮件可能会带来安全或合规性风险，并可能指示帐户遭到入侵。

该报告包含最多 90 天的数据。 默认情况下，报告显示最近 7 天的数据。

此报告不直接在邮件流仪表板或[报表](mail-flow-insights-v2.md)[仪表板中提供](view-mail-flow-reports.md)。 除了单击"新用户转发电子邮件见解"中的"查看与见解"链接关联的报告外，您还可以通过以下操作访问报告：

- 单击 **正在转发电子邮件见解** 的新域 [的详细信息中的"转发通知报告"链接](mfi-new-domains-being-forwarded-email.md)。
- 打开 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 。

### <a name="report-view-for-the-forwarding-modifications-report"></a>转发修改报告的报告视图

下表中提供了以下报表视图：

- **显示其数据：新转发用户**：

  ![转发修改报告中的新转发用户视图](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **显示其数据：新转发域**：

  ![转发修改报告中新的转发域视图](../../media/forwarding-modifications-report-new-forwarded-domains.png)

如果 **单击"筛选器**"报表视图，可以指定开始日期和 **结束日期的日期范围**。 

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>转发修改报告的详细信息表视图

如果单击 **"查看详细信息"表**，则显示的信息取决于您正在查看的图表：

- **显示其数据：新转发用户**：

  - **名称**：发件人的电子邮件地址。
  - **转发类型**
  - **收件人地址**
  - **Details**
  - **Count**
  - **第一个转发日期**

- **显示其数据：新转发域**：

  - **名称**：发件人的电子邮件域。
  - **转发类型**
  - **收件人地址**
  - **Details**
  - **Count**
  - **第一个转发日期**

如果在 **详细信息表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 

如果从表中选择一行，将显示"详细信息"飞出，并包含以下信息：

- **名称**：这是发件人的电子邮件地址 (显示其数据 **：** 新转发用户查看) 或发件人的电子邮件域 (**从"** 显示数据：新建转发域视图") 。
- **转发类型**
- **收件人**
- **Details**
- **Count**
- **开始日期**
- **建议**：你可以在此处单击链接以在 Microsoft 365 管理中心管理用户。

!["转发修改"报告中"新建转发用户"视图的详细信息表中的详细信息飞出](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

若要返回到报告视图，请单击"**查看报告"。**

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
