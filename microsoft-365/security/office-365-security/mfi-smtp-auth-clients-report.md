---
title: SMTP 身份验证客户端在邮件流仪表板中了解和报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规性中心中的邮件流仪表板中的 SMTP 身份验证了解和报告来监视组织中的电子邮件发件人，这些发件人使用经过身份验证的 SMTP (SMTP AUTH) 发送电子邮件。
ms.openlocfilehash: afdcf01260dd6dfcaf6b53d107e5addd007b1fb3
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577203"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>SMTP 身份验证客户端在安全 & 合规中心中了解和报告

**Smtp 身份验证客户端**在[邮件流仪表板](mail-flow-insights-v2.md)和关联的[SMTP auth 客户端](#smtp-auth-clients-report)中的洞察力报告突出显示了组织中的用户或系统帐户对 SMTP 身份验证客户端提交协议的使用。 此旧版协议 (使用终结点 smtp.office365.com) 仅提供基本身份验证，并且容易被受攻击帐户用来发送电子邮件。 通过真知灼见和报告，可以检查 SMTP 身份验证电子邮件提交是否有异常活动。 它还显示了使用 SMTP 身份验证的客户端或设备的 TLS 使用数据。

该小部件指示最近7天内已使用 SMTP 身份验证协议的用户或服务帐户的数量。

![Security & 合规性中心的邮件流仪表板中的 SMTP 身份验证客户端小部件](../../media/mfi-smtp-auth-clients-report-widget.png)

如果单击小组件上的邮件数，则将显示**SMTP Auth 客户端**弹出。 浮出控件提供了上一周的 TLS 使用和卷的聚合视图。

![单击邮件流仪表板中的 "SMTP 身份验证客户端" 小部件后的详细信息浮出控件](../../media/mfi-smtp-auth-clients-report-details.png)

您可以单击 " **Smtp auth 客户端报告**" 链接以转到 smtp auth 客户端报告，如下一节中所述。

## <a name="smtp-auth-clients-report"></a>SMTP 身份验证客户端报告

### <a name="report-view-for-the-smtp-auth-clients-report"></a>SMTP Auth 客户端报告的报告视图

默认情况下，此报告显示过去7天的数据，但数据可用于过去的90天。

"概述" 部分包含以下图表：

- **数据查看依据：发送卷**：默认情况下，图表显示从所有域发送的 SMTP 身份验证客户端邮件的数量 (显示其数据：默认情况下，**所有发件人域**都处于选中状态) 。 您可以通过单击下拉列表中的 "**显示数据**" 并选择 "发件人域"，将结果筛选为特定发件人域。 如果将特定数据点悬停 (天) ，则显示邮件数。

  ![在 SMTP Auth 客户端的 "安全 & 合规中心" 报告中发送卷视图](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **查看数据的依据： TLS 用法**：图表显示选定时间段内所有 SMTP 身份验证客户端邮件的 TLS 使用百分比。 此图允许你识别仍在使用旧版 TLS 的用户和系统帐户，并对其执行操作。

  ![SMTP Auth 客户端中的 TLS 使用情况视图报告中的安全性 & 合规性中心](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

如果您在报告视图中单击 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。

单击 "**请求报告**" 可在电子邮件中接收更详细的报告版本。 您可以指定日期范围和接收报告的收件人。

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>SMTP Auth 客户端报告的详细信息表格视图

如果您单击 "**查看详细信息表**"，则显示的信息将取决于所查看的图表：

- **数据查看方式：发送卷**：表中显示以下信息：

  - **发件人地址**
  - **邮件计数**

  如果选择了行，则会在浮出控件中显示相同的详细信息。

- **数据查看依据： TLS 用法**：表中显示了以下信息：

  - **发件人地址**
  - **TLS 1.0%**<sup>\*</sup>
  - **TLS 1.1%**<sup>\*</sup>
  - **TLS 1.2%**<sup>\*</sup>
  - **邮件计数**

  <sup>\*</sup>此列显示发件人的邮件的百分比和数量。

如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。

如果选择行，则在浮出控件中显示类似的详细信息：

![来自 SMTP Auth 客户端报告中的 TLS 使用状况视图的详细信息表中的详细信息的浮出控件](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

单击 "**请求报告**" 可在电子邮件中接收更详细的报告版本。 您可以指定日期范围和接收报告的收件人。

若要返回到 "报告" 视图，请单击 "**查看报告**"。

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中的其他见解的信息，请参阅[Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。
