---
title: 邮件流仪表板中的 SMTP 身份验证客户端见解和报告
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
description: 管理员可了解如何使用安全 & 合规中心的邮件流仪表板中的 SMTP 身份验证见解和报告，以监视组织中使用经身份验证的 SMTP (SMTP AUTH) 发送电子邮件的电子邮件发件人。
ms.openlocfilehash: 65e5569bcd79caef071ee2103d18a4e985c19dbb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826865"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>安全与合规中心内的 SMTP 身份验证&见解和报告

"**邮件流"仪表板和**关联的[SMTP](#smtp-auth-clients-report) [身份验证](mail-flow-insights-v2.md)客户端报告重点说明了组织中用户或系统帐户使用 SMTP AUTH 客户端提交协议。 此传 (它仅使用端点smtp.office365.com) 仅提供基本身份验证，并容被入入入被入入以供入入用来发送电子邮件的协议。 通过见解和报告，可以检查 SMTP AUTH 电子邮件提交是否有异常活动。 该示例还显示使用 SMTP AUTH 的客户端或设备的 TLS 使用率数据。

小部件指示过去 7 天内使用 SMTP 身份验证协议的用户或服务帐户的数量。

!["安全组合规中心"的"邮件流"仪表板中的"SMTP &小部件"](../../media/mfi-smtp-auth-clients-report-widget.png)

如果您单击小部件上的邮件数量，则会 **出现一个 SMTP 身份验证客户端** 浮出控件。 浮出控件提供上周 TLS 用法和卷的聚合视图。

![在"邮件流"仪表板中单击"SMTP 身份验证客户端"小部件后的详细信息浮出控件](../../media/mfi-smtp-auth-clients-report-details.png)

可以单击 **SMTP 身份验证客户端报告** 链接转到 SMTP 身份验证客户端报告，如下一节所述。

## <a name="smtp-auth-clients-report"></a>SMTP 身份验证客户端报告

### <a name="report-view-for-the-smtp-auth-clients-report"></a>SMTP 身份验证客户端报表的报告视图

默认情况下，报告显示最近 7 天的数据，但数据在最近 90 天内可用。

"概述"部分包含以下图表：

- **查看数据：发送方**：默认情况下，图表显示从所有域发送的 SMTP 身份验证客户端消息 (**显示所有发件人域** 的 SMTP 身份验证客户端消息 (显示所有发件人域在默认情况下) 。 可通过单击"从下拉列表中显示发件人 **域"** 并从下拉列表中选择发件人域，将结果筛选为特定发件人域。 如果您将特定数据点分段并 (数据) ，会显示消息数。

  ![安全与合规中心内"安全"报告中的"SMTP 验证&视图](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **查看数据：TLS 用法**：图表显示所选时间段内所有 SMTP 身份验证客户端消息的 TLS 使用情况百分比。 此图允许你识别仍在使用较旧版本的 TLS 的用户和系统帐户并对它们采取操作。

  ![安全 & 合规中心内 SMTP 身份验证客户端报告中的 TLS 使用情况视图](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

如果单击**筛选器 中的**筛选器报表视图，可以指定具有开始日期和结束**日期的****日期范围**。

单击 **"请求** "报告可在电子邮件中收到报告的更详细版本。 您可以指定日期范围和收件人来接收报告。

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>SMTP 身份验证客户端报表的详细信息表视图

如果您单击 **"查看详细信息**表"，显示的信息取决于正在查看的图表：

- **通过以下方式查看数据**：发送卷：下表中显示了以下信息：

  - **发件人地址**
  - **邮件计数**

  如果选择一行，则在浮出控件中显示相同详细信息。

- **通过以下方式查看数据**：TLS 用法：以下信息显示在表中：

  - **发件人地址**
  - **TLS1.0%**<sup>\*</sup>
  - **TLS1.1%**<sup>\*</sup>
  - **TLS1.2%**<sup>\*</sup>
  - **邮件计数**

  <sup>\*</sup> 此列显示来自发件人的邮件的百分比和数量。

如果在详细信息**表视图中单击**"筛选器"，可以指定具有开始日期和结束**日期的****日期范围**。

如果选择行，类似的详细信息会显示在浮出控件中：

![从 SMTP 身份验证客户端报告中 TLS 使用状况视图的详细信息表明天](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

单击 **"请求** "报告可在电子邮件中收到报告的更详细版本。 您可以指定日期范围和收件人来接收报告。

若要返回报告视图，请单击"查看**报告"。**

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。
