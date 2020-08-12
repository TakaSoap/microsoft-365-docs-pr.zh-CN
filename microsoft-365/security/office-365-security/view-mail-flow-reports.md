---
title: 查看 "报告" 仪表板中的邮件流报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解安全 & 合规性中心的 "报告" 仪表板中提供的邮件流报告。
ms.custom: ''
ms.openlocfilehash: acf74136fc61d38ea9aac47f36d96aa51a7b9905
ms.sourcegitcommit: 6319e73b3690b4cf1b7932f2b9f51c2c99e70eaa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2020
ms.locfileid: "46635030"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>在安全 & 合规中心中查看 "报告" 仪表板中的邮件流报告

除了安全性 & 合规性中心中的[邮件流仪表板](mail-flow-insights-v2.md)中提供的邮件流报告之外，"报告" 仪表板中还提供了多种其他邮件流报告，可帮助您监视 Microsoft 365 组织。

如果您具有[必要的权限](#what-permissions-are-needed-to-view-these-reports)，则可以转到 "**报告**" 仪表板，在[安全 & 合规中心](https://office.protection.com)中查看这些报告 \> **Dashboard**。 若要直接转到 "报表" 仪表板，请打开 <https://office.protection.office.com/insightdashboard> 。

![Security & 合规中心中的报告仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>连接器报告

**连接器报告**显示为您的组织配置的[入站和出站连接器](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)上的 "邮件流" 活动。

若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 "**连接器报告**"。 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ConnectorReport> 。

!["报告" 仪表板中的连接器报告小部件](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>连接器报告的报告视图

以下图表在报表视图中可用：

- **数据查看依据：邮件流**：此图显示按以下方式组织的入站和出站邮件的数量：

  - **Total**
  - **从不带连接器的 internet**
  - **不带连接器的 internet 连接**
  - 您已配置的特定连接器。
  
  若要隔离图表中的数据，请使用 "**显示数据以供**控制" 选择其中一个选项或**所有邮件流**。

  ![通过邮件流查看连接器报告中的数据](../../media/connector-report-view-data-by-mail-flow.png)

- **查看数据的依据： TLS 用法**：此图显示了邮件流的传输层安全性 (TLS) 版本使用情况的百分比。

  若要隔离图表中的数据，请使用 "**显示数据以供**控制" 选择以下选项之一：

  - **所有邮件流**
  - **从不带连接器的 internet**
  - **不带连接器的 internet 连接**
  - 您已配置的特定连接器。

  ![通过 TLS 使用在连接器报告中查看数据](../../media/connector-report-view-data-by-tls-usage.png)

如果您在报告视图中单击 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。

### <a name="details-table-view-for-the-connector-report"></a>连接器报告的详细信息表格视图

如果您在报告视图中单击 "**查看详细信息表**"，将显示以下信息：

- **Date**
- **连接器方向和名称**
- **连接器类型**
- **强制 TLS？**：值**True**或**False**。
- **没有 TLS** (百分比) 
- **TLS 1.0** (百分比) 
- **TLS 1.1** (百分比) 
- **TLS 1.2** (百分比) 
- **Volume**：邮件数。

如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。

若要返回到报告视图，请单击 "**查看报告**"。

## <a name="exchange-transport-rule-report"></a>Exchange 传输规则报告

**Exchange 传输规则报告**显示邮件流规则的效果 (也称为传输规则) 组织中的传入和传出邮件。

若要查看报告，请打开[安全 & 合规中心](https://protection.office.com)，转到 "**报告** \> **仪表板**"，然后选择 " **Exchange 传输规则**"。 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ETRRuleReport> 。

!["报告" 仪表板中的 Exchange 传输规则小部件](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Exchange 传输规则报告的报告视图

以下图表在报表视图中可用：

- **数据查看依据： Exchange 传输规则** \>**分解方式：方向**：此图显示受传输规则影响的**入站**和**出站**邮件的数量。

- **数据查看依据： Exchange 传输规则** \>**分解方式：严重性**：此图显示**高严重性**和**中低严重性**以及**低严重性**邮件的数量。 将严重性级别设置为规则中的操作 (使用严重级别或_SetAuditSeverity_) **审核此规则**。 有关详细信息，请参阅[Exchange Online 中的邮件流规则操作](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。

- **数据查看依据： DLP Exchange 传输规则** \>**分解方式：方向**：此图显示受数据丢失防护 (DLP) 传输规则影响的**入站**和**出站**邮件的数量。 您可以通过选择以下选项来进一步优化图表：

  - **显示以下项的数据：所有 DLP 传输规则**
  - **显示以下项的数据：已损坏的用户**
  - **显示以下项的数据：检测到的内容量过低美国爱国法案**

- **数据查看依据： DLP Exchange 传输规则** \>**分解方式：方向**：此视图显示**高严重性**和**中严重性**的数目以及受 DLP 传输规则影响的**低严重性**邮件。 您可以通过选择以下选项来进一步优化图表：

  - **显示以下项的数据：所有 DLP 传输规则**
  - **显示以下项的数据：已损坏的用户**
  - **显示以下项的数据：检测到的内容量过低美国爱国法案**

如果您在报告视图中单击 "**筛选器**"，则可以使用以下筛选器修改结果：：

- **开始日期**和**结束日期**
- 方向值
- 严重度值

![Exchange 传输规则报告中的报告视图](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Exchange 传输规则报告的详细信息表格视图

如果您单击 "**查看详细信息表**"，则显示的信息将取决于所查看的图表：

- **数据查看依据： Exchange 传输规则**：

  - **Date**
  - **传输规则**
  - **主题**
  - **发件人地址**
  - **收件人地址**
  - **严重性**
  - **方向**

- **数据查看依据： DLP Exchange 传输规则**：

  - **Date**
  - **DLP 策略**
  - **传输规则**
  - **主题**
  - **发件人地址**
  - **收件人地址**
  - **严重性**
  - **方向**

如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以使用以下筛选器修改结果：

- **开始日期**和**结束日期**
- 方向值
- 严重度值

若要返回到报告视图，请单击 "**查看报告**"。

## <a name="forwarding-report"></a>转发报告

**转发报告**将组织的自动转发的邮件显示为 Exchange Online 邮箱中的外部域。 转发的邮件可能会带来安全或合规性风险，并可能指示已损坏的帐户。

若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 "**转发报告**"。 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=MailFlowForwarding> 。

!["报告" 仪表板中的转发报告构件](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>转发报告的报告视图

报表视图中提供了以下图表：

- 显示以下各项**的数据：转发方法**：显示以下方法：

  - **传输规则**：也称为[邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。
  - **邮箱规则**：也称为[收件箱规则](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。

  ![转发报告中的转发方法视图](../../media/forwarding-report-forwarding-methods.png)

- **显示数据：转发域**：此视图显示作为转发目标的收件人域。

  ![转发报告中的转发域视图](../../media/forwarding-report-forwarding-domains.png)

- **显示以下项的数据：转发器**：显示以下转发器：

  - **传输规则**
  - 包含转发收件箱规则的邮箱。

  ![转发报告中的转发器视图](../../media/forwarding-report-forwarders.png)

如果您在报告视图中单击 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。

### <a name="details-table-view-for-the-forwarding-report"></a>转发报告的详细信息表格视图

如果您在报告视图中单击 "**查看详细信息表**"，将显示以下信息：

- **转发器**：值**传输规则**或包含转发收件箱规则的邮箱。
- **转发类型**：值**邮箱规则**或**传输规则**。
- **收件人名称**
- **收件人域**
- **详细信息**：这是邮件流规则的 GUID 值，或收件箱规则的 RuleIdentity 值。
- **Count**
- **第一次转发日期**

如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。

若要返回到 "报告" 视图，请单击 "**查看报告**"。

## <a name="mailflow-status-report"></a>邮件流状态报告

**邮件流状态报告**类似于[发送和接收的电子邮件报告](#sent-and-received-email-report)，其中包含有关在边缘上允许或阻止的电子邮件的其他信息。 这是唯一包含 edge 保护信息的报告，仅显示在允许 Exchange Online Protection (EOP) 进行评估之前阻止的电子邮件的数量。 请务必注意，如果将邮件发送给5个收件人，我们会将其计数为五个不同的邮件，而不是一封邮件。  
若要查看报表，请打开 "[安全 & 合规中心](https://protection.office.com)"，转到 "**报告**" \> **仪表板**，然后选择 "**邮件流状态报告**"。 若要直接转到 "**邮件流状态" 报告**，请打开 <https://protection.office.com/mailflowStatusReport> 。

!["报告" 仪表板中的邮件流状态报告小部件](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>邮件流状态报告的类型视图

打开报表时，"**类型**" 选项卡在默认情况下处于选中状态。 默认情况下，此视图包含一个使用以下筛选器配置的图表和数据表：

- **日期**：最近7天。
- **方向**：

  - **进货**
  - **出站**
  - **组织内**：此计数用于租户中的邮件，即 发件人 abc@domain.com 从**入站**和**出站**) 分别发送给收件人 xyz@domain.com (计数

- **类型**：

  - **正常邮件**
  - **恶意软件**
  - **垃圾邮件**
  - **边缘保护**
  - **规则消息**
  - **钓鱼电子邮件**

图表按**类型**值进行组织。

您可以通过单击 "**筛选器**" 或单击图表图例中的值来更改这些筛选器。

数据表包含以下信息：

- **方向**
- **类型**
- **24 小时**
- **3 天**
- **7 天**
- **15 天**
- **30 天**

如果单击 "**选择类别" 以了解更多详细信息**，则可以从以下值中进行选择：

- **网络钓鱼电子邮件**：此选择会将您带到[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。
- **电子邮件中的恶意软件**：此选择会将您带到[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。
- **垃圾邮件检测**：选择此选项将转到[垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。
- **边缘阻止的垃圾邮件**：选择此选项将转到[垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。

**导出**：

对于详细信息视图，只能导出一天的数据。 因此，如果要将数据导出7天，则需要执行7个不同的导出操作。

每个导出的 .csv 文件限制为150000行。 如果该天的数据包含的行数超过150000，则会创建多个 .csv 文件。

![邮件流状态报告中的类型视图 ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>邮件流状态报告的方向视图

如果单击 "**方向**" 选项卡，则将使用 "**类型**" 视图中的相同默认筛选器。

图表按**方向**值组织。

您可以通过单击 "**筛选器**" 或通过单击图表图例中的值来更改这些筛选器。 将使用 "**类型**" 视图中的相同筛选器。

数据表包含**类型**视图中的相同信息。

**选择类别以获取更多详细信息**可用的选择和行为与 "**类型**" 视图相同。

**导出**：

对于详细信息视图，只能导出一天的数据。 因此，如果要将数据导出7天，则需要执行7个不同的导出操作。

每个导出的 .csv 文件限制为150000行。 如果该天的数据包含的行数超过150000，则会创建多个 .csv 文件。

![邮件流状态报告中的 "方向" 视图 ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a>发送和接收的电子邮件报告

**已发送和已接收的电子邮件**报告是一个智能报告，显示有关传入和传出电子邮件的信息，包括垃圾邮件检测、恶意软件和标识为 "正常" 的电子邮件。 此报告和[邮件流状态报告](#mailflow-status-report)的区别在于：此报告不包含有关边缘保护阻止的邮件的数据。

报告的聚合视图和详细信息视图允许90天的筛选。

若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 "**已发送和已接收电子邮件**"。 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。

!["报告" 仪表板中的发送和接收电子邮件小部件](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>已发送和已接收电子邮件报告的报告视图

报表视图中提供了以下图表：

- **分解方式：类型**：图表显示所有可用类别：

  - **Total**
  - **正常邮件**
  - **恶意软件 (反恶意软件) ** (EOP) 
  - **垃圾邮件检测**
  - **规则消息**
  -  (Office 365 ATP) 的**高级恶意软件**

  当鼠标悬停在图表中某天 (数据点) 时，可以查看那天的详细信息。

  ![发送和接收的电子邮件报告中的类型视图](../../media/sent-and-received-email-report-type-view.png)

- **分解方式：方向**：图表显示**总计**、**入站**和**出站**数据。 当鼠标悬停在图表中某天 (数据点) 时，可以查看那天的详细信息。

  ![已发送和已接收电子邮件报告中的方向视图](../../media/sent-and-received-email-report-direction-view.png)

- **向下** \> 钻取**恶意软件 (反恶意软件) **：此选择会将您带到[电子邮件报告中的恶意软件检测](view-email-security-reports.md#malware-detections-in-email-report)。

- **向下** \> 钻取**垃圾邮件检测) **：选择此选项将转到[垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。

如果您在报告视图中单击 "**筛选器**"，则可以使用以下筛选器修改结果：

- **开始日期**和**结束日期**
- 方向值
- 类型值

若要返回到报告视图，请单击 "**查看报告**"。

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>已发送和已接收电子邮件报告的详细信息表格视图

如果在 "分解方式" 中单击 "**查看详细信息表** **：方向**" 或 "**分解方式"： "方向**" 视图，将显示以下信息：

- **日期 (UTC) **
- **类型**
- **方向**
- **邮件计数**

如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以使用以下筛选器修改结果：

- **开始日期**和**结束日期**
- 方向值
- 类型值

若要返回到报告视图，请单击 "**查看报告**"。

## <a name="top-senders-and-recipients-report"></a>主要发件人和收件人报告

**最上面的发件人和收件人**报告是显示主要电子邮件发件人和收件人的饼形图。

若要查看报告，请打开 "[安全 & 合规中心](https://protection.office.com)"，转到 "**报告**" \> **仪表板**，然后选择 "**主要发件人和收件人**"。 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。

!["报告" 仪表板中的 "主要发件人和收件人" 小部件](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>主要发件人和收件人报告的报告视图

报表视图中提供了以下图表：

- **显示 \> 主要邮件发件人的数据**
- **显示 \> 主要邮件收件人的数据**
- **显示 \> 排名靠前的垃圾邮件收件人的数据**
- **显示数据 \>主要的恶意软件收件人** (EOP) 
- **显示数据 \>主要的恶意软件收件人 (ATP) ** (Office 365 ATP) 

饼图的复合根据这些选择的变化而变化。

当您将鼠标指针悬停在饼图中时，您可以看到发送或接收的邮件数。

如果您在报告视图中单击 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。

!["热门发件人和收件人" 报告中报告视图中的饼形图](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>主要发件人和收件人报告的详细信息表格视图

如果您单击 "**查看详细信息表**"，则显示的信息将取决于所查看的图表：

- **显示 \> 主要邮件发件人的数据**

  - **主要邮件发件人**
  - **Count**

- **显示 \> 主要邮件收件人的数据**

  - **主要邮件收件人**
  - **Count**

- **显示 \> 排名靠前的垃圾邮件收件人的数据**

  - **主要垃圾邮件收件人**
  - **Count**

- **显示数据 \>主要的恶意软件收件人** (EOP) 

  - **主要恶意软件收件人**
  - **Count**

- **显示数据 \>主要的恶意软件收件人 (ATP) ** (Office 365 ATP) 

  - ** (ATP) 的主要恶意软件收件人**
  - **Count**

如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。

若要返回到报告视图，请单击 "**查看报告**"。

## <a name="what-permissions-are-needed-to-view-these-reports"></a>查看这些报告所需的权限是什么？

若要查看和使用报告，您必须是安全 & 合规性中心**和**Exchange Online 中指定角色组的成员。

- 在安全 & 合规性中心中，您必须是下列角色组之一的成员：

  -组织管理-安全管理员 (你也可以在[Azure Active Directory 管理中心](https://aad.portal.azure.com)中执行此操作-安全读者

  有关详细信息，请参阅[安全与合规中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。

- 在 Exchange Online 中，您必须是下列角色组之一的成员：

  -组织管理-仅查看组织管理-仅查看收件人-合规性管理

有关详细信息，请参阅[Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo)中的权限和[管理 exchange online 中的角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

## <a name="related-topics"></a>相关主题

[安全与合规中心内的智能报告和见解](reports-and-insights-in-security-and-compliance.md)

[安全与合规中心内的邮件流见解](mail-flow-insights-v2.md)

[查看安全与合规中心内的电子邮件安全报告](view-email-security-reports.md)

[查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)
