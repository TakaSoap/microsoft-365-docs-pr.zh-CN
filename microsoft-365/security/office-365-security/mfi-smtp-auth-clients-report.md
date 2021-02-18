---
title: 邮件流仪表板中的 SMTP 身份验证客户端见解和报表
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
description: 管理员可以了解如何使用安全 & 合规中心的邮件流仪表板中的 SMTP 身份验证见解和报表来监视其组织中使用已验证 SMTP (SMTP AUTH) 发送电子邮件的电子邮件发件人。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9050fd2c1bc3863a3bd78190cd5b27fda018479e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287793"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>安全与合规中心中的 SMTP 身份验证客户端见解&报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

安全与合规中心内的邮件流仪表板 [](mail-flow-insights-v2.md)中的 **SMTP 身份验证** 客户端见解和关联的 SMTP &[身份验证](https://protection.office.com)客户端报告重点介绍组织中用户或系统帐户使用 SMTP AUTH 客户端提交协议。 [](#smtp-auth-clients-report) 此旧协议 (终结点smtp.office365.com) 仅提供基本身份验证，并且很容易被受损的帐户用来发送电子邮件。 通过见解和报表，您可以检查 SMTP AUTH 电子邮件提交的异常活动。 它还显示使用 SMTP AUTH 的客户端或设备的 TLS 使用情况数据。

小部件指示过去 7 天内使用 SMTP 身份验证协议的用户或服务帐户的数量。

![安全与合规中心的"邮件流"仪表板中的"SMTP 身份验证&小组件](../../media/mfi-smtp-auth-clients-report-widget.png)

如果单击小部件上的消息数， **则会出现 SMTP 身份验证客户端** 飞出。 该标注提供上一周 TLS 使用情况和卷的聚合视图。

![单击"邮件流"仪表板中的"SMTP 身份验证客户端"小部件后的详细信息飞出](../../media/mfi-smtp-auth-clients-report-details.png)

您可以单击 **SMTP 身份验证客户端报告** 链接以转到 SMTP 身份验证客户端报告，如下一节中所述。

## <a name="smtp-auth-clients-report"></a>SMTP 身份验证客户端报告

### <a name="report-view-for-the-smtp-auth-clients-report"></a>SMTP 身份验证客户端报告的报表视图

默认情况下，报告显示最近 7 天的数据，但最近 90 天的数据可用。

概述部分包含以下图表：

- 查看 **数据者：** 发送量：默认情况下，图表显示从所有域发送的 SMTP 身份验证客户端邮件数 (**显示** 数据：默认情况下，所有发件人域都) 。 可以通过单击"显示数据"，然后从下拉列表中选择发件人域，将结果筛选到特定发件人域。 如果您将特定 (悬停在) ，则会显示消息数。

  ![在安全与合规中心的 SMTP 身份验证客户端报告中&卷视图](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **查看数据者：TLS 使用情况**：图表显示选定时段内所有 SMTP 身份验证客户端邮件的 TLS 使用率百分比。 此图表允许你标识仍在使用较早版本的 TLS 的用户和系统帐户并采取措施。

  ![安全与合规中心内 SMTP 身份验证客户端报告中的 TLS &视图](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

如果 **单击"筛选器**"报表视图，可以指定开始日期和 **结束日期的日期范围**。 

单击 **"** 请求报告"以在电子邮件中接收报告的详细版本。 可以指定接收报告的日期范围和收件人。

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>SMTP 身份验证客户端报告的详细信息表视图

如果单击 **"查看详细信息"表**，则显示的信息取决于您正在查看的图表：

- **查看数据者：发送卷**：下表显示了以下信息：

  - **发件人地址**
  - **邮件计数**

  如果选择一行，则相同的详细信息将显示在一个飞出中。

- **查看数据者：TLS 使用情况**：下表显示了以下信息：

  - **发件人地址**
  - **TLS1.0%**<sup>\*</sup>
  - **TLS1.1%**<sup>\*</sup>
  - **TLS1.2%**<sup>\*</sup>
  - **邮件计数**

  <sup>\*</sup> 此列显示来自发件人的邮件的百分比和数量。

如果在 **详细信息表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 

如果选择行，则类似的详细信息将显示在一个标注中：

![SMTP 身份验证客户端报告中 TLS 使用率视图的详细信息表中的详细信息飞出](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

单击 **"** 请求报告"以在电子邮件中接收报告的详细版本。 可以指定接收报告的日期范围和收件人。

若要返回到报告视图，请单击"**查看报告"。**

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
