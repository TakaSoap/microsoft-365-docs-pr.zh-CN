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
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: 了解如何将第三方数据从社交媒体平台、即时消息平台和文档协作平台导入到 Microsoft 365 邮箱。
ms.openlocfilehash: a70747e9268b075f2c46072009b76f8071492fc7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200049"
---
# <a name="archive-third-party-data"></a>存档第三方数据

Microsoft 365 允许管理员使用数据连接器将第三方数据从社交媒体平台、即时消息平台和文档协作平台导入并存档到 Microsoft 365 组织中的邮箱。 使用数据连接器在 Microsoft 365 中导入和存档第三方数据的一个主要好处是，可以在导入后向其应用各种 Microsoft 365 合规性解决方案。 这可帮助您确保您的组织的非 Microsoft 数据符合影响组织的法规和标准。

## <a name="third-party-data-connectors"></a>第三方数据连接器

下表列出了 Microsoft 365 合规性中心提供的第三方数据连接器。 该表还汇总了在 Microsoft 365 中导入和存档后，可应用于第三方数据的合规性解决方案。 有关每个合规性解决方案的更详细说明以及它如何对第三方数据进行有益的详细说明，请参阅 [下一节](#overview-of-compliance-solutions-that-support-third-party-data) 。

> [!TIP]
> 单击 " **第三方数据** " 列中的链接可转到为该数据类型创建连接器的分步说明。

|第三方数据  |诉讼保留|电子数据展示  |保留设置  |记录管理  |通信合规性  |内部风险管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[在&T 网络 <sup>1</sup>](archive-att-network-archiver-data.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[电铃网络 <sup>1</sup>](archive-bell-network-data.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Bloomberg 消息](archive-bloomberg-message-data.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[.EML <sup>2</sup>](archive-eml-data.md)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[企业编号 <sup>1</sup>](archive-enterprise-number-data.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[FX 连接 <sup>2</sup>](archive-fxconnect-data.md)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[人力资源 (人力资源) ](import-hr-data.md) ||||||![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|[ICE 聊天](archive-icechat-data.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[即时 Bloomberg](archive-instant-bloomberg-data.md)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[领英](archive-linkedin-data.md)   |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[O2 网络 <sup>1</sup>](archive-o2-network-data.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[物理徽章](import-physical-badging-data.md) ||||||![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|[Reuters Eikon <sup>2</sup>](archive-reuterseikon-data.md)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[时差 <sup>2</sup>](archive-slack-data.md)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Symphony <sup>2</sup>](archive-symphony-data.md)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[TELUS 网络 <sup>1</sup>](archive-telus-network-data.md)    |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[以文本分隔的 <sup>2</sup>](archive-text-delimited-data.md)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Verizon 网络 <sup>1</sup>](archive-verizon-network-data.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Webex 团队 <sup>2</sup>](archive-webexteams-data.md)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[来自 Facebook <sup>2</sup>的工作区](archive-workplacefromfacebook-data.md)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[缩放会议 <sup>2</sup>](archive-zoommeetings-data.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
||||||||

> [!NOTE]
> <sup>1</sup> 此数据连接器由 TeleMessage 提供。 在 Microsoft 365 中存档数据之前，您必须使用 TeleMessage 为您的组织设置其存档服务。 有关详细信息，请参阅此数据类型的分步说明中的 "先决条件" 部分。<br/><br/><sup>2</sup> 连接器由 Globanet 提供。 在 Microsoft 365 中存档数据之前，您必须使用 Globanet 为您的组织设置其存档服务。 有关详细信息，请参阅此数据类型的分步说明中的 "先决条件" 部分。

上表中列出的第三方数据 (除 HR 数据和物理徽章数据) 将导入到用户邮箱中。 支持第三方数据的相应合规性解决方案将应用于存储数据的用户邮箱。

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>支持第三方数据的合规性解决方案概述

以下各节介绍 Microsoft 365 合规性解决方案可帮助您管理上表中列出的第三方数据的一些内容。

### <a name="litigation-hold"></a>诉讼保留

你将 [诉讼保留](create-a-litigation-hold.md) 置于用户邮箱以保留第三方数据。 创建保留时，可以指定保留期 (也称为 *基于时间的保留*) ，以便在指定时间段内保留已删除和已修改的第三方数据，然后从邮箱中永久删除。 或者，您可以只保留内容 (被称为 *无限保留*) 或在删除诉讼保留之前。

### <a name="ediscovery"></a>电子数据展示

Microsoft 365 中的三个主要电子数据展示工具是内容搜索、核心电子数据展示和高级电子数据展示。

- **[内容搜索](content-search.md)。** 您可以使用内容搜索工具搜索您导入的第三方数据的邮箱。 您可以使用搜索查询和条件来缩小搜索结果范围，并导出搜索结果。

- **[核心电子数据展示](get-started-core-ediscovery.md)。** 此工具基于基本搜索和导出功能构建，使您能够控制可访问事例数据的用户，在与搜索条件相匹配的用户邮箱或邮箱内容上放置保留。 这意味着，您可以在导入到用户邮箱的第三方数据上放置电子数据展示保留。

- **[高级电子数据展示](overview-ediscovery-20.md)。** 此功能强大的工具可以扩展核心电子数据展示的大小写功能，方法是让您向一个案例中添加保管人，将保管人的数据置于保留状态，然后将保管人的第三方数据加载到评审中，以供进一步分析，例如主题和重复检测。 将第三方数据加载到评审集后，可以对其进行查询和筛选以缩小结果集。

   核心电子数据展示和高级电子数据展示使您能够管理可能与您的组织的法律或内部调查相关的第三方数据。

### <a name="retention-settings"></a>保留设置

您可以将 [保留策略](retention.md) 应用于用户邮箱，以便在保留期到期后保留并删除第三方数据 (和其他邮箱内容) 。 您还可以使用保留策略删除特定年龄的第三方数据，或使用保留标签在第三方数据的保留期过期时 [触发处置评审](disposition.md) 。

### <a name="records-management"></a>记录管理

Microsoft 365 中的 [记录管理](records-management.md) 功能允许您将第三方数据声明为记录。 此操作可由应用保留标签（将邮箱中的第三方数据标记为记录）的用户手动完成。 或者，您可以通过识别第三方数据中的敏感信息、关键字或内容类型来自动应用保留标签。

### <a name="communication-compliance"></a>通信合规性

您可以使用 [通信合规性](communication-compliance.md) 检查第三方数据，以确保其符合组织的数据标准。 您可以通过对组织中不适当的邮件进行检测、捕获和采取补救措施来执行此操作。 例如，您可以监视为攻击性语言、敏感信息和法规遵从性而导入的第三方数据。

### <a name="insider-risk-management"></a>内部风险管理

来自第三方数据（如选择性 HR 数据）的信号可由 [内幕风险管理](insider-risk-management.md) 解决方案使用，以通过让您检测、调查和操作组织中的风险活动来最大限度地减少内部风险。 例如，HR 数据连接器导入的数据被用作风险标记，以帮助检测传出的员工数据失窃。

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>与 Microsoft 合作伙伴合作以存档第三方数据

导入和存档第三方数据的另一个选择是让组织与 Microsoft 合作伙伴合作。 如果 Microsoft 合规性中心中提供的数据连接器不支持第三方数据类型，则可以与合作伙伴合作，该合作伙伴可以提供一个自定义连接器，以便定期将其配置为从第三方数据源提取项目，然后通过第三方 API 连接到 Microsoft 云并将这些项目导入到 Microsoft 365。 合作伙伴连接器还将项目的内容从第三方数据源转换为电子邮件，然后将其导入到 Microsoft 365 中的邮箱。

有关您可以使用的合作伙伴列表和此方法的分步过程，请参阅 [在 Microsoft 365 中使用合作伙伴存档第三方数据](work-with-partner-to-archive-third-party-data.md)。
