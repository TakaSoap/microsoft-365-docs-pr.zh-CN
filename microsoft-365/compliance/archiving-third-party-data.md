---
title: 存档第三方数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: 了解如何从社交媒体平台、即时消息平台和文档协作平台导入和存档第三方数据以Microsoft 365邮箱。
ms.openlocfilehash: 59388d85ba1e768add90461b6905ed5763fcd87d
ms.sourcegitcommit: b1a2b09edbcfcc62ff3f1ecf5bd8adb1afa344c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2021
ms.locfileid: "61586609"
---
# <a name="archive-third-party-data-in-microsoft-365"></a>存档第三方数据Microsoft 365

Microsoft 365管理员可使用数据连接器将第三方数据从社交媒体平台、即时消息平台和文档协作平台导入和存档到组织Microsoft 365邮箱。 使用数据连接器在 Microsoft 365 中导入和存档第三方数据的一个主要好处是，您可以在导入数据后对这些数据应用各种 Microsoft 365 合规性解决方案。 这有助于确保组织的非 Microsoft 数据符合影响组织的法规和标准。

## <a name="third-party-data-connectors"></a>第三方数据连接器

The Microsoft 365 合规中心 provides native third-party data connectors from Microsoft to import data from various data sources， such as LinkedIn， Instant Bloomberg， and Twitter and data connectors that support the Insider risk management solution. 除了这些数据连接器之外，Microsoft 还与以下合作伙伴合作，在 Microsoft 365 合规中心 中提供更多第三方数据Microsoft 365 合规中心。 贵组织与这些合作伙伴一起设置存档服务，然后再在存档服务中创建Microsoft 365 合规中心。

- [百里达](#veritas-data-connectors)

- [TeleMessage](#telemessage-data-connectors)

- [17a-4 LLC](#17a-4-data-connectors)

- [CellTrust](#celltrust-data-connectors)

以下各节中列出的第三方数据 (除用于 Microsoft 365 预览体验成员风险管理解决方案) 的 HR 数据和物理密码数据外）将导入到用户邮箱中。 支持Microsoft 365数据的合规性解决方案将应用于存储数据的用户邮箱。

### <a name="microsoft-data-connectors"></a>Microsoft 数据连接器

下表列出了本机第三方数据连接器，这些连接器可用于Microsoft 365 合规中心。 该表还汇总了在导入并存档第三方数据之后可应用Microsoft 365。 有关 [每个合规性解决方案](#overview-of-compliance-solutions-that-support-third-party-data) 及其如何支持第三方数据的详细说明，请参阅支持第三方数据的合规性解决方案概述部分。

单击"第 **三方数据** "列中的链接，转到有关为第三方数据列创建连接器的数据类型。

|第三方数据  |诉讼保留|电子数据展示  |保留设置  |记录管理  |通信合规性  |内部风险管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Bloomberg 消息](archive-bloomberg-message-data.md)     |![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)||
|[发展 EHR 医疗保健](import-epic-data.md) ||||||![复选标记](../media/checkmark.png)|
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[通用 EHR 医疗保健](import-healthcare-data.md) ||||||![复选标记](../media/checkmark.png)|
|[人力资源 (HR) ](import-hr-data.md) ||||||![复选标记](../media/checkmark.png)|
|[ICE 聊天](archive-icechat-data.md)     |![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[领英](archive-linkedin-data.md)   |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[物理保护](import-physical-badging-data.md) ||||||![复选标记](../media/checkmark.png)|
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
||||||||

### <a name="veritas-data-connectors"></a>Veritas 数据连接器

本节中的表列出了与它合作提供的第三方数据连接器。 该表还汇总了在导入第三方数据后可应用于第三方数据的合规性Microsoft 365。 有关 [每个合规性解决方案](#overview-of-compliance-solutions-that-support-third-party-data) 及其如何支持第三方数据的详细说明，请参阅支持第三方数据的合规性解决方案概述部分。

在您将第三方数据存档到 Microsoft 365 中之前，您必须与用户一起为组织设置名为 *Merge1* (的存档服务) 。 有关详细信息，请单击"第三方数据"列中的链接，转到创建该连接器的分步说明数据类型。

|第三方数据  |诉讼保留|电子数据展示  |保留设置  |记录管理  |通信合规性  |内部风险管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust](archive-celltrust-data.md)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[MS SQL 上的 Cisco Jabber](archive-ciscojabberonmssql-data.md)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Oracle 上的 Cisco Jabber](archive-ciscojabberonoracle-data.md)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[PostgreSQL 上的 Cisco Jabber](archive-ciscojabberonpostgresql-data.md)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[EML](archive-eml-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[FX 连接](archive-fxconnect-data.md)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Jive](archive-jive-data.md)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[MS SQL 数据库](archive-mssqldatabaseimporter-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[透视](archive-pivot-data.md)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Redtail Speak](archive-redtailspeak-data.md)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Reuters Dealing](archive-reutersdealing-data.md)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Reuters Eikon](archive-reuterseikon-data.md)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Reuters FX](archive-reutersfx-data.md)|![复选标记。](../media/checkmark.png)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[RingCentral](archive-ringcentral-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Salesforce Chatter](archive-salesforcechatter-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[ServiceNow](archive-servicenow-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[Skype for Business](archive-skypeforbusiness-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[可宽延时间电子数据展示](archive-slack-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Symphony](archive-symphony-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[文本分隔](archive-text-delimited-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[Twitter](archive-veritas-twitter-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[Webex Teams](archive-webexteams-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[网页](archive-webpagecapture-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[Workplace from Facebook](archive-workplacefromfacebook-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[XIP](archive-xip-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[XSLT/XML](archive-xslt-xml-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[Yieldbroker](archive-yieldbroker-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Twitter](archive-youtube-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[Zoom 会议](archive-zoommeetings-data.md)     |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
||||||||

### <a name="telemessage-data-connectors"></a>TeleMessage 数据连接器

本节中的表列出了与 TeleMessage 合作提供的第三方数据连接器。 该表还汇总了在导入第三方数据后可应用于第三方数据的合规性Microsoft 365。 有关 [每个合规性解决方案](#overview-of-compliance-solutions-that-support-third-party-data) 及其如何支持第三方数据的详细说明，请参阅支持第三方数据的合规性解决方案概述部分。

您必须使用 TeleMessage 为组织设置存档服务，然后才能在 Microsoft 365 中存档第三方数据。 有关详细信息，请单击"第三方数据"列中的链接，转到创建该连接器的分步说明数据类型。

TeleMessage 数据连接器还可用于美国政府云GCC环境中Microsoft 365环境。 有关详细信息，请参阅本文 [中的](#data-connectors-in-the-us-government-cloud) 美国政府云数据连接器部分。

|第三方数据  |诉讼保留|电子数据展示  |保留设置  |记录管理  |通信合规性  |内部风险管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android](archive-android-archiver-data.md)     |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[AT&T 网络](archive-att-network-archiver-data.md)     |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Bell 网络](archive-bell-network-data.md)     |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[企业编号](archive-enterprise-number-data.md)     |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[O2 网络](archive-o2-network-data.md)     |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[都斯网络](archive-rogers-network-archiver-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[信号](archive-signal-archiver-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[百年](archive-telegram-archiver-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[TELUS 网络](archive-telus-network-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Verizon 网络](archive-verizon-network-data.md)     |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[微信](archive-wechat-data.md)|![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[WhatsApp](archive-whatsapp-data.md)     |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
||||||||

### <a name="17a-4-data-connectors"></a>17a-4 数据连接器

本节中的表列出了与 17a-4 LLC 合作提供的第三方数据连接器。 该表还汇总了在导入第三方数据后可应用于第三方数据的合规性Microsoft 365。 有关 [每个合规性解决方案](#overview-of-compliance-solutions-that-support-third-party-data) 及其如何支持第三方数据的详细说明，请参阅支持第三方数据的合规性解决方案概述部分。

在 Microsoft 365 中存档第三方数据之前，您必须使用 17a-4 LLC 为组织设置其 (称为 *DataParser*) 。 有关详细信息，请单击"第三方数据"列中的链接，转到创建该连接器的分步说明数据类型。

17a-4 数据连接器还可用于美国政府GCC云中的Microsoft 365环境中。 有关详细信息，请参阅本文 [中的](#data-connectors-in-the-us-government-cloud) 美国政府云数据连接器部分。

|第三方数据  |诉讼保留|电子数据展示  |保留设置  |记录管理  |通信合规性  |内部风险管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[BlackBerry](archive-17a-4-blackberry-data.md)     |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Bloomberg](archive-17a-4-bloomberg-data.md)     |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Cisco Jabber](archive-17a-4-cisco-jabber-data.md)   |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Cisco Webex](archive-17a-4-webex-teams-data.md)   |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[FactSet](archive-17a-4-factset-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Fuze](archive-17a-4-fuze-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[FX 连接](archive-17a-4-fxconnect-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[ICE 聊天](archive-17a-4-ice-im-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[InvestEdge](archive-17a-4-investedge-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[LivePerson 对话云](archive-17a-4-liveperson-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Quip](archive-17a-4-quip-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Refinitiv Eikon Messenger](archive-17a-4-refinitiv-messenger-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[ServiceNow](archive-17a-4-servicenow-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
[Skype for Business Server](archive-17a-4-skype-for-business-server-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[可宽延时间](archive-17a-4-slack-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[SQL](archive-17a-4-sql-database-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Symphony](archive-17a-4-symphony-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[缩放](archive-17a-4-zoom-data.md)    |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
||||||||

### <a name="celltrust-data-connectors"></a>CellTrust 数据连接器

本节中的表列出了与 CellTrust 合作提供的第三方数据连接器。 该表还汇总了在导入第三方数据后可应用于第三方数据的合规性Microsoft 365。 有关 [每个合规性解决方案](#overview-of-compliance-solutions-that-support-third-party-data) 及其如何支持第三方数据的详细说明，请参阅支持第三方数据的合规性解决方案概述部分。

在将第三方数据存档到 Microsoft 365 中之前，您必须使用 CellTrust 为组织设置 (*CellTrust SL2*) 存档服务。 有关详细信息，请单击"第三方数据"列中的链接，转到创建 CellTrust SL2 连接器的分步说明。

|第三方数据  |诉讼保留|电子数据展示  |保留设置  |记录管理  |通信合规性  |内部风险管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust SL2](archive-data-from-celltrustsl2.md)     |![复选标记。](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
||||||||

CellTrust SL2 数据连接器还可用于美国政府GCC环境中Microsoft 365环境。 有关详细信息，请参阅本文 [中的](#data-connectors-in-the-us-government-cloud) 美国政府云数据连接器部分。

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>支持第三方数据的合规性解决方案概述

以下各节介绍一些Microsoft 365合规性解决方案可以帮助您管理上表中列出的第三方数据。

### <a name="litigation-hold"></a>诉讼保留

将用户 [邮箱置于](create-a-litigation-hold.md) 诉讼保留以保留第三方数据。 创建保留时，您可以指定保留持续时间 (也称为基于时间的保留 *) 以便* 已删除和修改的第三方数据将保留一段指定时间，然后从邮箱中永久删除。 或者，您可以无限期地保留 (称为"无限期 *保留")* 或删除诉讼保留。

### <a name="ediscovery"></a>电子数据展示

网站中的三个主要电子数据展示Microsoft 365内容搜索、核心电子数据展示和Advanced eDiscovery。

- **[内容搜索](content-search.md)。** 您可以使用内容搜索工具在邮箱中搜索您导入的第三方数据。 您可以使用搜索查询和条件来缩小搜索结果范围，并导出搜索结果。

- **[核心电子数据展示](get-started-core-ediscovery.md)。** 此工具基于基本搜索和导出功能构建，通过创建案例，您可以控制谁可以访问事例数据、将用户邮箱或与搜索条件匹配的邮箱内容置于保留状态。 这意味着您可以将电子数据展示保留置于导入到用户邮箱的第三方数据上。

- **[Advanced eDiscovery](overview-ediscovery-20.md)。** 这一强大的工具通过让您向案例添加保管人、将保管人的数据置于保留状态，然后将保管人的第三方数据加载到审阅中以进一步分析（如主题和重复检测）来扩展核心电子数据展示的案例功能。 将第三方数据加载到审阅集后，可以查询并筛选到较窄结果集。

   核心电子数据展示Advanced eDiscovery可让你管理可能与组织的法律或内部调查相关的第三方数据。

### <a name="retention-settings"></a>保留设置

可以将保留策略应用于 [用户](retention.md) 邮箱以保留，然后在保留期到期 (删除第三) 内容。 您还可以使用保留策略删除特定期限的第三方数据，或使用保留标签在第[](disposition.md)三方数据的保留期到期时触发处置评审。

### <a name="records-management"></a>记录管理

通过[记录](records-management.md)管理Microsoft 365，您可将第三方数据声明为记录。 这可以通过应用保留标签（将邮箱中第三方数据标记为记录）的用户手动完成。 或者，您可以通过标识第三方数据中的敏感信息、关键字或内容类型来自动应用保留标签。

### <a name="communication-compliance"></a>通信合规性

可以使用通信 [合规性](communication-compliance.md) 检查第三方数据，以确保数据符合组织的数据标准。 您可以通过检测、捕获组织中不适当的邮件并采取修正操作来这样做。 例如，您可以监视为冒犯性语言、敏感信息和法规合规性而导入的第三方数据。

### <a name="insider-risk-management"></a>内部风险管理

预览体验成员风险管理解决方案可以使用来自第三方数据的信号（如选择性 HR[](insider-risk-management.md)数据）来最大程度地降低内部风险，让你可以检测、调查和处理组织中存在风险的活动。 例如，HR 数据连接器导入的数据用作风险指示器，以帮助检测离职的员工数据盗窃。

## <a name="using-ediscovery-tools-to-search-for-third-party-data"></a>使用电子数据展示工具搜索第三方数据

使用数据连接器导入和存档用户邮箱中的第三方数据后，Microsoft 365电子数据展示工具搜索第三方数据。 您还可以使用电子数据展示工具创建与核心电子数据展示相关联的基于查询的保留，Advanced eDiscovery事例以保留第三方数据。 有关电子数据展示工具的更多信息，请参阅 Microsoft 365 中的[电子数据展示解决方案](ediscovery.md)。

若要 (或保留) 使用数据连接器导入到用户邮箱的任何类型的第三方数据，可以使用以下搜索查询。 请确保将搜索范围确定为用户邮箱。

```powershell
kind:externaldata
```

可以在"关键字"框中使用此查询进行内容搜索、与核心电子数据展示案例关联的搜索或 Advanced eDiscovery。

![查询以搜索第三方数据。](..\media\SearchThirdPartyData1.png)

您还可以使用 `kind:externaldata` property：value 对将搜索范围缩小到第三方数据。 例如，若要搜索从导入项目的 **Subject** 属性中包含 *单词 contoso* 的任何第三方数据源导入的项目，请使用"**关键字**"框中的以下查询：

```powershell
subject:contoso AND kind:externaldata
```

或者，您可以使用 Message **kind** 条件配置相同的查询。

![使用邮件类型条件将搜索范围缩小到第三方数据。](..\media\SearchThirdPartyData2.png)

若要搜索特定类型的存档第三方数据，请使用搜索查询中的 **itemclass** 邮箱属性。 使用以下 property：value 格式：

```powershell
itemclass:ipm.externaldata.<third-party data type>
```

第三方数据连接器导入的每一项都包括 **itemclass** 属性，其值对应于第三方数据数据类型。 例如，若要在导入项目的 **Subject** 属性中搜索包含 *单词 contoso* 的 Facebook 数据，请使用以下查询：

```powershell
subject:contoso AND itemclass:ipm.externaldata.facebook*
```

下面是适用于不同类型的第三方数据的 **itemclass** 值的一些示例。

| **第三方数据类型** | **itemclass 属性的值**   |
|---------------------------|-------------------------------------|
| Bloomberg 消息         | ipm.externaldata.bloombergmessage* |
| CellTrust                 | ipm.externaldata.celltrust*        |
| Pivot                     | ipm.externaldata.pivot*            |
| WhatsApp 存档器         | ipm.externaldata.whatsapparchiver* |
|||

*itemclass 属性的值* 不区分大小写。 通常，使用第三方名称（数据类型 (空格）后) 通配符 * ( * ) 字符。

有关创建电子数据展示搜索查询的信息，请参阅关键字查询和电子数据展示 [的搜索条件](keyword-queries-and-search-conditions.md)。

## <a name="data-connectors-in-the-us-government-cloud"></a>美国政府云中的数据连接器

某些数据连接器在美国政府云中可用。 以下各节指示支持第三方数据连接器的特定政府环境。 有关美国政府云详细信息，请参阅美国政府[Microsoft 365 云](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy)。

### <a name="telemessage-data-connectors"></a>Telemessage 数据连接器

|数据连接器  |GCC  |GCC 高  |DoD  |
|:---------|:---------|:---------|:---------|
|Android 存档器 | 是 | 否 | 否 |
|AT&T 短信/彩信网络存档程序 | 是 | 否 | 否 |
|铃声短信/彩信网络存档程序 | 是 | 否 | 否 |
|企业编号存档器 | 是 | 否 | 否 |
|O2 SMS 和语音网络存档器 | 是         | 否 | 否 |
|集成网络存档器 | 是         | 否 | 否 |
|信号存档程序 | 是 | 否 | 否 |
|Telegram 存档程序 | 是 | 否 | 否 |
|TELUS SMS 网络存档器 | 是 | 否 | 否 |
|Verizon 短信/彩信网络存档程序 | 是 | 否 | 否 |
|微信存档器 | 是 | 否 | 否 |
|WhatsApp 存档器 | 是 | 否 | 否 |
|||||

### <a name="celltrust-data-connectors"></a>CellTrust 数据连接器

|数据连接器  |GCC  |GCC 高  |DoD  |
|:---------|:---------|:---------|:---------|
|CellTrust SL2 | 是 | 否 | 否 |
|||||

### <a name="17a-4-data-connectors"></a>17a-4 数据连接器

|数据连接器  |GCC  |GCC 高  |DoD  |
|:---------|:---------|:---------|:---------|
|BlackBerry DataParser | 是 | 否 | 否 |
|Bloomberg DataParser  | 是 | 否 | 否 |
|Cisco Jabber DataParser  | 是 | 否 | 否 |
|Cisco Webex DataParser  | 是 | 否 | 否 |
|FactSet DataParser  | 是 | 否 | 否 |
|Fuze DataParser  | 是 | 否 | 否 |
|FX Connect DataParser  | 是 | 否 | 否 |
|ICE DataParser  | 是 | 否 | 否 |
|InvestEdge DataParser  | 是 | 否 | 否 |
|LivePerson 对话云 DataParser  | 是 | 否 | 否 |
|Quip DataParser  | 是 | 否 | 否 |
|Refinitiv Eikon Messenger DataParser  | 是 | 否 | 否 |
|ServiceNow DataParser  | 是 | 否 | 否 |
|Skype for Business Server DataParser | 是 | 否 | 否 |
|Slack DataParser | 是 | 否 | 否 |
|SQL DataParser  | 是 | 否 | 否 |
|Symphony DataParser | 是 | 否 | 否 |
|Zoom DataParser | 是 | 否 | 否 |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>与 Microsoft 合作伙伴合作存档第三方数据

导入和存档第三方数据的另一个选项是让组织与 Microsoft 合作伙伴合作。 如果 Microsoft 合规中心内提供的数据连接器不支持第三方 数据类型，你可以与合作伙伴合作，该合作伙伴可以提供一个自定义连接器，该连接器将配置为定期提取第三方数据源中的项目，然后通过第三方 API 连接到 Microsoft 云，然后将这些项目导入 Microsoft 365。 合作伙伴连接器还将项目的内容从第三方数据源转换为电子邮件，然后将它导入到 Microsoft 365 中的邮箱。

有关可以合作的合作伙伴列表以及此方法的分步过程，请参阅与合作伙伴协作以在 Microsoft 365[中存档第三方数据](work-with-partner-to-archive-third-party-data.md)。
