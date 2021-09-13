---
title: Microsoft 365合规性扩展性
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 了解如何使用Microsoft 365数据连接器和 Microsoft Graph API 扩展合规性解决方案。
ms.openlocfilehash: 1fed5ac72c7dbfa4b1be370ec03678e1beecdcd2
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59171071"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365合规性扩展性

Microsoft 365合规性解决方案可帮助组织智能评估其合规性风险、治理和保护敏感数据，并有效响应法规要求。 Microsoft 365扩展性方案非常丰富，使组织能够适应、扩展、集成、加速和支持其合规性解决方案。

合规性扩展性有两个关键构建基块：

- **数据连接器**。 用于导入和存档非 Microsoft 数据，以便Microsoft 365保护和管理功能应用于第三方数据。

- **API**。 允许以编程方式Microsoft 365合规性功能。

## <a name="data-connectors"></a>数据连接器

Microsoft 提供可在服务器中配置的第三方数据Microsoft 365 合规中心。 有关 Microsoft 提供的数据连接器的列表，请参阅第三方 [数据连接器](archiving-third-party-data.md#third-party-data-connectors) 表。 第三方数据连接器表还汇总了在 Microsoft 365 中导入和存档数据后可应用于第三方数据的合规性解决方案，以及指向每个连接器的分步说明的链接。

若要详细了解如何Microsoft 365连接器，请参阅存档[第三方数据](archiving-third-party-data.md)。 如果第三数据类型服务不受 Microsoft 365 合规中心 中提供的数据连接器支持，您可以与可以为您提供自定义连接器的合作伙伴合作。 有关可以合作的合作伙伴列表以及此方法的分步过程，请参阅与合作伙伴协作以存档 [第三方数据](work-with-partner-to-archive-third-party-data.md)。

### <a name="prerequisites-for-data-connectors"></a>数据连接器的先决条件

要导入和存档第三Microsoft 365 合规中心，许多数据连接器都需要您准备并执行第三方数据源中的配置任务。 每个第三方数据连接器都详细记录了这些先决条件。

对于 Microsoft Microsoft 365 合规中心提供的数据连接器，贵组织需要与合作伙伴建立业务关系，然后才能部署连接器。

有关第三方数据连接器的许可要求，Microsoft 365[合规性许可比较](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)文档。

## <a name="apis"></a>API

Microsoft 365合规性 API 在 Microsoft 信息保护 SDK、Microsoft Graph API 和 Office 365 管理活动 API 中提供。 某些合规性 API 是一组新的安全性和合规性 API 的一部分，这些 API 使 Microsoft 365 客户、独立软件供应商、系统集成商和托管安全服务提供商的开发人员能够构建高价值安全性和合规性解决方案。

若要详细了解如何访问 Graph API，请参阅[Microsoft](/graph/overview)Graph 概述。

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft 信息保护 (MIP) SDK

MIP SDK 将标签和保护服务从Microsoft 365安全与合规中心公开到第三方应用程序和服务。 开发人员可以使用 SDK 生成本机支持，以将标签和保护应用于文件。 开发人员可以确定在检测到特定标签时应该采取哪些操作，以及 MIP 加密信息的原因。

高级 MIP SDK 用例包括：

- 在导出时将分类标签应用于文件的业务线应用程序。

- 为 MIP 标签提供本机支持的 CAD/CAM 设计应用程序。

- 可以使用 Azure 信息保护加密数据的云访问安全代理或数据丢失防护解决方案。

若要详细了解 MIP SDK、先决条件、其他方案和示例，请参阅 [MIP SDK 概述](/information-protection/develop/overview)。

### <a name="microsoft-graph-api-for-teams-dlp"></a>Microsoft Graph DLP Teams API

[数据丢失防护 (DLP) ](dlp-microsoft-teams.md)功能在组织中广泛使用Microsoft Teams尤其是在组织转移到远程工作时。 今年较早时，我们宣布公开预览 Microsoft [Graph](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/)中的邮件更改通知 API Teams。 此 API 使开发人员能够构建应用，这些应用可以Microsoft Teams实时侦听邮件，然后为客户和合作伙伴实施 DLP 方案。 此外，Microsoft Graph 修补程序 API 允许您将 DLP 操作应用于Teams邮件。

这两个 API 构成 Microsoft Graph DLP Teams API。 可以通过尝试示例应用 [开始](https://github.com/microsoftgraph/csharp-webhook-with-resource-data)。 有关消息传递 webhook Microsoft Teams，请参阅[文档](/graph/api/subscription-post-subscriptions)。

有关 DLP 的许可要求Teams，请参阅Microsoft 365[安全与合规&指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)。

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>Microsoft Graph API for eDiscovery (preview) 

借助[Advanced eDiscovery，](overview-ediscovery-20.md)组织可以发现它所位于的数据，以及使用智能机器学习和分析功能管理更多端到端电子数据展示工作流，以将数据减少到相关集合 - 所有这一切都在数据保持在 Microsoft 365 安全性和合规性边界内。

Graph适用于 Advanced eDiscovery API 可用于以可扩展且可重复的方式创建和管理事例、审阅集和审阅集查询。 这使客户和合作伙伴能够创建应用和工作流，以自动化常见和重复的过程，例如创建事例和管理保管人和法律保留。

第一组Graph电子数据展示的 API 在公共预览版中可用。 我们计划在日历年结束时添加更多功能。 若要了解有关这些 API 和其他适用于Advanced eDiscovery更新，请参阅此[博客](https://aka.ms/Ignite2020AeDAA)。

有关 Advanced eDiscovery 和 API 的许可要求，请参阅安全与合规Microsoft 365指南中的"电子数据&[部分](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)。

### <a name="microsoft-graph-api-for-teams-export-preview"></a>Microsoft Graph API for Teams Export (preview) 

企业资讯存档 (EIA) for Microsoft Teams 是我们的客户的关键方案，因为它允许客户解决法规要求。 除了我们在 Microsoft Teams 中存档内容的内置功能外，客户和合作伙伴现在可以使用 Teams 导出 API 来解决自定义应用程序和集成方案。 Teams导出 API 支持批量导出 (每秒每个应用/每个租户最多 200 个请求) Teams邮件附件。 此外，API 还可以在删除邮件后的最多 30 天内访问已删除的邮件。 有关导出 API Teams以及如何在应用程序中使用它们，请参阅使用导出 API 导出Microsoft Teams[内容](/microsoftteams/export-teams-content)。

有关使用导出 API 的许可Teams，请参阅Microsoft 365安全与合规[&指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

### <a name="microsoft-graph-connector-apis-preview"></a>Microsoft Graph 连接器 API (预览) 

借助[Microsoft Graph](/microsoftsearch/connectors-overview)连接器，组织可以索引第三方数据，以便数据显示在Microsoft 搜索结果中。 此功能扩展了 Microsoft 365 生产力应用中可搜索的内容源类型以及 Microsoft 更广泛的数据源。 第三方数据可以托管在本地或公有云或私有云中。 从Advanced eDiscovery开始，我们将启用开发人员预览已连接应用的内置合规性Microsoft 365价值。 这使集成到生态系统的应用Microsoft 365，从而为用户提供无缝的合规性体验。 若要了解有关如何在应用视图中合并 Microsoft Graph 连接器 API 的信息，请参阅在 Microsoft 应用视图中创建、更新[和删除Graph。](/graph/search-index-manage-connections)

