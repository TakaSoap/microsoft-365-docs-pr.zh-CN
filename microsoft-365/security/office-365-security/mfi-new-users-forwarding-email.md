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
description: 管理员可以了解如何使用安全 & 合规中心中的新用户转发电子邮件，以调查组织中的用户何时将邮件转发到新域。
ms.openlocfilehash: 22bbd762b221fae151a489aa1e9485dfc7baf06a
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357269"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>新用户在安全 & 合规中心转发电子邮件洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


当组织中的新用户帐户突然开始将电子邮件转发到外部域时，这是可疑的。

当组织中新创建的用户将邮件转发到外部域时，将在 [安全 & 合规中心](https://protection.office.com)中 **转发的新域** 将向您发出通知。 这种情况可能表示使用了已损坏的管理员帐户来创建新用户。 如果您怀疑帐户已损坏，请参阅 [响应已泄露的电子邮件帐户](responding-to-a-compromised-email-account.md)。

此洞察力仅在检测到问题时显示，并显示在 " [转发报告](view-mail-flow-reports.md#forwarding-report) " 页上。

![新用户转发电子邮件见解](../../media/mfi-new-users-forwarding-email.png)

当您单击小组件时，将显示一个弹出对话框，可在其中找到有关转发邮件的更多详细信息，包括指向本主题后面所述的 [转发修改报告](#forwarding-modifications-report) 的链接。

![单击新用户转发电子邮件洞察力后显示的详细信息浮出控件](../../media/mfi-new-users-forwarding-email-details.png)

当您在 (**报告** 仪表板 "或") 上的 "**热门见解 & 建议**" 区域中单击 "**查看全部**" 后，您还可以转到此详细信息页面 \> **Dashboard** <https://protection.office.com/insightdashboard> 。

您可以单击 " **查看与洞察力相关的报告** " 链接以转到 " **转发修改" 报告** ，如下一节中所述。

## <a name="forwarding-modifications-report"></a>转发修改报告

" **转发修改" 报告** 显示有关自动从组织中的发件人转发的邮件的详细信息：

- 将邮件转发到外部域的新创建的帐户。
- 将邮件转发到组织中的其他发件人从未转发给外部域的帐户。

这些转发邮件类型可能会带来安全或合规性风险，并可能指示已泄露的帐户。

此报告包含最长为90天的数据。 默认情况下，此报告显示过去7天的数据。

此报告不能直接在 [邮件流仪表板](mail-flow-insights-v2.md) 或 [报表仪表板](view-mail-flow-reports.md)中使用。 除了单击 **新用户发送电子邮件** 见解中的 "**查看与洞察力相关的查看报告**" 链接之外，您还可以通过以下方式获取报告：

- 在要转发的新域的详细信息中单击 " **转发通知报告** " 链接， [了解如何理解电子邮件](mfi-new-domains-being-forwarded-email.md)。
- 打开 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 。

### <a name="report-view-for-the-forwarding-modifications-report"></a>"转发修改" 报告的报告视图

报表视图中提供了以下图表：

- **显示以下项的数据：新的转发用户**：

  ![转发修改报告中的新转发用户视图](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **显示以下项的数据：新的转发域**：

  ![转发修改报告中的新的转发域视图](../../media/forwarding-modifications-report-new-forwarded-domains.png)

如果您在报告视图中单击 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>转发修改报告的详细信息表格视图

如果您单击 " **查看详细信息表**"，则显示的信息将取决于所查看的图表：

- **显示以下项的数据：新的转发用户**：

  - **名称**：发件人的电子邮件地址。
  - **转发类型**
  - **收件人地址**
  - **Details**
  - **Count**
  - **第一次转发日期**

- **显示以下项的数据：新的转发域**：

  - **名称**：发件人的电子邮件域。
  - **转发类型**
  - **收件人地址**
  - **Details**
  - **Count**
  - **第一次转发日期**

如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。

如果从表中选择行，则会显示 **详细** 信息弹出项，其中包含以下信息：

- **名称**：这是发件人的电子邮件地址 (来自 **显示以下项的数据：新的转发用户** 查看) 或发件人的电子邮件域 (来自 **显示以下项的数据：新的转发域** 视图) 。
- **转发类型**
- **收件人**
- **Details**
- **Count**
- **开始日期**
- **建议**：在此，可以单击 "Microsoft 365 管理中心" 中的 "管理用户" 的链接。

!["转发修改报告" 中 "新转发用户" 视图的 "详细信息" 表格中的详细信息表格](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

若要返回到 "报告" 视图，请单击 " **查看报告**"。

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。
