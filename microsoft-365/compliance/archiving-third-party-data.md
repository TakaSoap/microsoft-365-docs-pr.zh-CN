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
ms.openlocfilehash: 6b75d2857fd95d24a90f9245cb299b7558aa3cec
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860707"
---
# <a name="archive-third-party-data"></a>存档第三方数据

Microsoft 365 允许管理员使用数据连接器将第三方数据从社交媒体平台、即时消息平台和文档协作平台导入并存档至 Microsoft 365 组织中的邮箱中。 使用数据连接器在 Microsoft 365 中导入和存档第三方数据的一个主要好处是，你可以在导入后对其应用各种 Microsoft 365 合规性解决方案。 这有助于确保组织的非 Microsoft 数据符合影响你组织的法规和标准。

## <a name="third-party-data-connectors"></a>第三方数据连接器

下表列出了 Microsoft 365 合规中心中可用的第三方数据连接器。 此表还汇总了在 Microsoft 365 中导入和存档后可应用于第三方数据的合规性解决方案。 有关每 [种合规性解决方案](#overview-of-compliance-solutions-that-support-third-party-data) 的更详细说明以及它如何从第三方数据中获得益处，请参阅下一节。

> [!TIP]
> 单击第三方 **数据列中的链接** ，以完成为该数据栏创建连接器的分数据类型。

|第三方数据  |诉讼保留|电子数据展示  |保留策略  |记录管理  |通信合规性  |内部风险管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Bloomberg 消息](archive-bloomberg-message-data.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[HR 数据](import-hr-data.md) ||||||![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|[ICE 聊天](archive-icechat-data.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[即时 Bloomberg](archive-instant-bloomberg-data.md)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[领英](archive-linkedin-data.md)   |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
||||||||

上表中列出的第三方数据 (，HR 数据导入) 用户邮箱除外。 支持第三方数据的相应合规性解决方案将应用于存储该数据的用户邮箱。

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>支持第三方数据的合规性解决方案概述

以下各节介绍了 Microsoft 365 合规性解决方案可以帮助管理上表中列出的第三方数据的一些相关事项。

### <a name="litigation-hold"></a>诉讼保留

将用户 [邮箱置于诉讼](create-a-litigation-hold.md) 保留以保留第三方数据。 创建保留时，你可以指定保留时长 (也称为基于 *时间的* 保留) ，以便将删除和修改的第三方数据保留指定的时间并从邮箱中永久删除。 或者您只需将内容无限期保留 (个名为无限 *期* 保留) ，或者在移除诉讼保留之前。

### <a name="ediscovery"></a>电子数据展示

Microsoft 365 中的三个主要电子数据展示工具包括"内容搜索、核心电子数据展示"和"高级电子数据展示"。

- **[内容搜索](content-search.md)。** 可以使用内容搜索工具搜索邮箱中导入的第三方数据。 您可以使用搜索查询和条件来缩小搜索结果范围和导出搜索结果。

- **[核心电子数据展示](get-started-core-ediscovery.md)。** 此工具基于基本的搜索和导出功能构建，以便你可以创建案例，以便控制哪些人可以访问事例数据、将用户邮箱置于保留状态满足搜索条件的用户邮箱或邮箱内容。 这意味着您可以将电子数据展示保留到导入到用户邮箱的第三方数据。

- **[高级电子数据展示](overview-ediscovery-20.md)。** 此强大的工具可扩展核心电子数据展示的案例功能，方法是允许你向事例添加保护人的数据，将保护人的数据置于保留状态，然后将保护人的第三方数据加载到审查以进行进一步分析（如主题和重复检测）。 将第三方数据加载到审阅集后，可以查询并筛选这些数据以缩小范围结果集。

   核心电子数据展示和高级电子数据展示都允许你管理可能与你的组织法律或内部调查相关的第三方数据。

### <a name="retention-policies"></a>保留策略

可以将保留策略 [应用于用户](retention.md) 邮箱，以保留，然后在保留期 (删除第三) 方 (和其他邮箱内容更新。 还可以使用保留策略删除特定年限的第三方数据，或在保留期到期时触发处置评审。

### <a name="records-management"></a>记录管理

Microsoft [records management](records-management.md) 365 中的记录管理功能使你可以将第三方数据声明为记录。 这可以由应用保留标签（将邮箱中的第三方数据标记为记录）的用户手动完成操作。 或者，可以通过识别第三方数据中的敏感信息、关键字或内容类型来自动应用保留标签。

### <a name="communication-compliance"></a>通信合规性

通过合规性 [，](communication-compliance.md) 您可以检查第三方数据以确保其符合组织的数据标准。 可以通过检测、捕获和对组织中不适当邮件执行修正操作来执行此操作。 例如，您可以监视导入的具有攻击性语言、敏感信息和法规合规性的第三方数据。

### <a name="insider-risk-management"></a>内部风险管理

预览体验成员风险管理解决方案可以使用来自第三方数据（选择性 HR 数据）[Insider risk management](insider-risk-management.md)的信号，通过允许你检测、调查和执行组织中存在的风险活动来最大限度地降低内部风险。 例如，HR 数据连接器导入的数据用作风险指标，以帮助检测分离员工数据被存列。

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>与 Microsoft 合作伙伴进行协作以存档第三方数据

导入和存档第三方数据的另一种选择是由你的组织与 Microsoft 合作伙伴协作。 如果 Microsoft 合规中心提供的数据连接器不支持第三方 数据类型，则可与可以提供自定义连接器的合作伙伴合作，该连接器可定期从第三方数据源中提取项目，然后通过第三方 API 连接到 Microsoft 云，然后将这些项导入到 Microsoft 365。 合作伙伴连接器还将项目的内容从第三方数据源转换为电子邮件，然后将其导入到 Microsoft 365 中的邮箱。

有关你可以使用的合作伙伴列表以及此方法的分步过程，请参阅["与合作伙伴协作在 Microsoft 365 中存档第三方数据"。](work-with-partner-to-archive-third-party-data.md)
