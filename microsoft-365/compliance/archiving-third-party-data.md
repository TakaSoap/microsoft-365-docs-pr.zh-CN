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
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: 了解如何将第三方数据从社交媒体平台、即时消息平台和文档协作平台导入到 Microsoft 365 邮箱。
ms.openlocfilehash: 18fb9c757652cbebb456da18285444272766167f
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722855"
---
# <a name="archive-third-party-data"></a>存档第三方数据

Microsoft 365 允许管理员使用数据连接器将第三方数据从社交媒体平台、即时消息平台和文档协作平台导入和存档到 Microsoft 365 组织的邮箱。 使用数据连接器在 Microsoft 365 中导入和存档第三方数据的一个主要好处是，可以在导入后对这些数据应用各种 Microsoft 365 合规性解决方案。 这有助于确保组织的非 Microsoft 数据符合影响组织的法规和标准。

## <a name="third-party-data-connectors"></a>第三方数据连接器

下表列出了 Microsoft 365 合规中心中可用的第三方数据连接器。 该表还汇总了在 Microsoft 365 中导入和存档后可应用于第三方数据的合规性解决方案。 请参阅 [下一部分](#overview-of-compliance-solutions-that-support-third-party-data) ，详细了解每个合规性解决方案及其如何受益于第三方数据。

> [!TIP]
> 单击"第 **三** 方数据"列中的链接，转到有关为第三方数据列创建连接器的分步数据类型。

|第三方数据  |诉讼保留|电子数据展示  |保留设置  |记录管理  |通信合规性  |内部风险管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[AT&T Network <sup>1</sup>](archive-att-network-archiver-data.md)     |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Bell Network <sup>1</sup>](archive-bell-network-data.md)     |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Bloomberg 消息](archive-bloomberg-message-data.md)     |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[CellTrust <sup>2</sup>](archive-celltrust-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Cisco Jabber <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[企业 <sup>数字 1</sup>](archive-enterprise-number-data.md)     |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[FX Connect <sup>2</sup>](archive-fxconnect-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[人力资源 (人力资源) ](import-hr-data.md) ||||||![复选标记](../media/checkmark.png)
|[ICE 聊天](archive-icechat-data.md)     |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[即时 Bloomberg](archive-instant-bloomberg-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[领英](archive-linkedin-data.md)   |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[MS SQL Database <sup>2</sup>](archive-mssqldatabaseimporter-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[O2 网络 <sup>1</sup>](archive-o2-network-data.md)     |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[物理保护](import-physical-badging-data.md) ||||||![复选标记](../media/checkmark.png)|
|[透视 <sup>表 2</sup>](archive-pivot-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Redtail Speak <sup>2</sup>](archive-redtailspeak-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[2.0 <sup></sup>](archive-reutersdealing-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Eikon <sup>2</sup>](archive-reuterseikon-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[英国 FX <sup>2</sup>](archive-reutersfx-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Salesforce Chatter <sup>2</sup>](archive-salesforcechatter-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[ServiceNow <sup>2</sup>](archive-servicenow-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[Slack 电子数据展示 <sup>2</sup>](archive-slack-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[云 <sup>2</sup>](archive-symphony-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[TELUS 网络 <sup>1</sup>](archive-telus-network-data.md)    |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[用文本分隔的 <sup>2</sup>](archive-text-delimited-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[Verizon 网络 <sup>1</sup>](archive-verizon-network-data.md)     |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Webex Teams <sup>2</sup>](archive-webexteams-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[网页 <sup>2</sup>](archive-webpagecapture-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[Facebook <sup>2</sup>中的工作区](archive-workplacefromfacebook-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|||
|[Yieldbroker <sup>2</sup>](archive-yieldbroker-data.md)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|[缩放会议 <sup>2</sup>](archive-zoommeetings-data.md)     |![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
||||||||

> [!NOTE]
> <sup>1</sup> 由 TeleMessage 提供的数据连接器。 在 Microsoft 365 中存档数据之前，您必须使用 TeleMessage 为组织设置存档服务。 有关详细信息，请参阅本文的分步说明中的先决条件部分数据类型。<br/><br/>Globanet 提供的<sup>2</sup>个数据连接器。 在 Microsoft 365 中存档数据之前，您必须与 Globanet 一起为组织设置存档服务。 有关详细信息，请参阅本文的分步说明中的先决条件部分数据类型。

上表中列出的第三方数据 (HR 数据和物理密码数据除外，) 导入到用户邮箱中。 支持第三方数据的相应合规性解决方案将应用于存储数据的用户邮箱。

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>支持第三方数据的合规性解决方案概述

以下各节介绍 Microsoft 365 合规性解决方案可帮助你管理上表中列出的第三方数据的一些内容。

### <a name="litigation-hold"></a>诉讼保留

您将用户 [邮箱置于](create-a-litigation-hold.md) 诉讼保留状态以保留第三方数据。 创建保留时，可以指定保留持续时间 (也称为基于时间保留 *)* 以便删除和修改的第三方数据保留指定的时间段，然后从邮箱中永久删除。 或者，您可以无限期保留内容 (称为") 保留"或直到删除诉讼保留。

### <a name="ediscovery"></a>电子数据展示

Microsoft 365 中的三个主要电子数据展示工具是内容搜索、核心电子数据展示和高级电子数据展示。

- **[内容搜索](content-search.md)。** 可以使用内容搜索工具在邮箱中搜索导入的第三方数据。 您可以使用搜索查询和条件来缩小搜索结果范围，并导出搜索结果。

- **[核心电子数据展示](get-started-core-ediscovery.md)。** 此工具基于基本搜索和导出功能构建，它使您可以创建事例，以便控制谁可以访问事例数据、将用户邮箱或与搜索条件相匹配的邮箱内容置于保留状态。 这意味着可以将电子数据展示保留到已导入到用户邮箱的第三方数据上。

- **[高级电子数据展示](overview-ediscovery-20.md)。** 这一强大的工具通过以下方法扩展核心电子数据展示的案例功能：向案例添加保管人、将保管人数据置于保留状态，然后将保管人的第三方数据加载到审阅中，以进一步分析主题和重复检测。 将第三方数据加载到审阅集后，可以查询并筛选为较窄结果集。

   通过核心电子数据展示和高级电子数据展示，您可以管理可能与组织的法律或内部调查相关的第三方数据。

### <a name="retention-settings"></a>保留设置

可以将保留策略应用于 [用户](retention.md) 邮箱，以保留第三方数据， (保留期) 删除其他邮箱内容。 您还可以使用保留策略删除特定期限的第三方数据，或使用保留标签在第[](disposition.md)三方数据的保留期到期时触发处置评审。

### <a name="records-management"></a>记录管理

Microsoft [](records-management.md) 365 中的记录管理功能允许您将第三方数据声明为记录。 这可以通过应用保留标签（将邮箱中第三方数据标记为记录）的用户手动完成。 或者，您可以通过标识第三方数据中的敏感信息、关键字或内容类型来自动应用保留标签。

### <a name="communication-compliance"></a>通信合规性

可以使用通信 [合规性](communication-compliance.md) 来检查第三方数据，以确保数据符合组织的数据标准。 您可以通过检测、捕获和采取针对组织中不当邮件的修正操作来实施此操作。 例如，您可以监视导入的第三方数据，了解冒犯性语言、敏感信息和法规遵从性。

### <a name="insider-risk-management"></a>内部风险管理

内部风险管理解决方案可以使用来自第三方数据（如选择性 HR 数据）[](insider-risk-management.md)的信号，通过让你检测、调查和处理组织中存在风险的活动来最大程度地降低内部风险。 例如，HR 数据连接器导入的数据用作风险指示器，以帮助检测离职的员工数据盗窃。

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>与 Microsoft 合作伙伴合作存档第三方数据

导入和存档第三方数据的另一个选项是供组织与 Microsoft 合作伙伴合作。 如果 Microsoft 合规中心提供的数据连接器不支持第三方 数据类型，你可以与合作伙伴合作，合作伙伴可以提供自定义连接器，该连接器将配置为定期从第三方数据源提取项目，然后通过第三方 API 连接到 Microsoft 云，然后将这些项目导入到 Microsoft 365。 合作伙伴连接器还将项目的内容从第三方数据源转换为电子邮件，然后将它导入到 Microsoft 365 中的邮箱。

有关可以合作的合作伙伴列表以及此方法的分步过程，请参阅"与合作伙伴合作以在 [Microsoft 365](work-with-partner-to-archive-third-party-data.md)中存档第三方数据"。
