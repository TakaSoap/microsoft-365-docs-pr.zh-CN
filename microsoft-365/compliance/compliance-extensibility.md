---
title: Microsoft 365 合规性扩展性
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
description: 了解如何使用第三方数据连接器和 Microsoft Graph API 扩展 Microsoft 365 合规性解决方案。
ms.openlocfilehash: 676c0ba41e517dd0c3692fec29a1d4034641b634
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919718"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 合规性扩展性

Microsoft 365 合规性解决方案可帮助组织智能评估其合规性风险、治理和保护敏感数据，并有效响应法规要求。 Microsoft 365 合规性具有丰富的扩展性方案，使组织能够适应、扩展、集成、加速和支持其合规性解决方案。

合规性扩展性有两个关键构建基块：

- **数据连接器**。 用于导入和存档非 Microsoft 数据，以便你可以将 Microsoft 365 保护和管理功能应用于第三方数据。

- **API**。 允许以编程方式访问 Microsoft 365 合规性功能。

## <a name="data-connectors"></a>数据连接器

Microsoft 提供可在 Microsoft 365 合规中心配置的第三方数据连接器。 有关 Microsoft 提供的数据连接器的列表，请参阅第三方 [数据连接器](archiving-third-party-data.md#third-party-data-connectors) 表。 第三方数据连接器表还汇总了在 Microsoft 365 中导入和存档数据后可应用于第三方数据的合规性解决方案，以及指向每个连接器的分步说明的链接。

若要了解有关 Microsoft 365 数据连接器的更多信息，请参阅存档 [第三方数据](archiving-third-party-data.md)。 如果第三数据类型不受 Microsoft 365 合规中心中提供的数据连接器支持，你可以与可以向您提供自定义连接器的合作伙伴合作。 有关可以合作的合作伙伴列表以及此方法的分步过程，请参阅与合作伙伴协作以存档 [第三方数据](work-with-partner-to-archive-third-party-data.md)。

### <a name="prerequisites-for-data-connectors"></a>数据连接器的先决条件

Microsoft 365 合规中心中提供的用于导入和存档第三方数据的许多数据连接器都需要你准备并执行第三方数据源中的配置任务。 每个第三方数据连接器都详细记录了这些先决条件。

对于 Microsoft 365 合规中心内由 Microsoft 的一个合作伙伴提供的数据连接器，你的组织将需要与合作伙伴建立业务关系，然后才能部署连接器。

可以在 [Microsoft 365](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) 合规性许可比较文档中找到第三方数据连接器的许可要求。

## <a name="apis"></a>API

Microsoft 信息保护 SDK、Microsoft Graph API 和 Office 365 管理活动 API 中提供了 Microsoft 365 合规性 API。 某些合规性 API 是一组新的安全性和合规性 API 的一部分，这些 API 使 Microsoft 365 客户、独立软件供应商、系统集成商和托管安全服务提供商的开发人员能够构建高价值安全性和合规性解决方案。

若要详细了解如何访问 Graph API，请参阅 [Microsoft Graph 概述](/graph/overview)。

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft 信息保护 (MIP) SDK

MIP SDK 将 Microsoft 365 安全与合规中心中的标签和保护服务公开到第三方应用程序和服务。 开发人员可以使用 SDK 构建对将标签和保护应用到文件的本机支持。 开发人员可以确定在检测到特定标签时应该采取哪些操作，以及 MIP 加密信息的原因。

高级 MIP SDK 用例包括：

- 在导出时将分类标签应用于文件的业务线应用程序。

- 为 MIP 标签提供本机支持的 CAD/CAM 设计应用程序。

- 云访问安全代理或数据丢失防护解决方案，可以使用 Azure 信息保护对数据进行加密。

若要了解有关 MIP SDK、先决条件、其他方案和示例的更多信息，请参阅 [MIP SDK 概述](/information-protection/develop/overview)。

### <a name="microsoft-graph-api-for-teams-dlp"></a>适用于 Teams DLP 的 Microsoft Graph API

[数据丢失防护 (DLP) ](dlp-microsoft-teams.md) 功能在 Microsoft Teams 中广泛使用，尤其是在组织转移到远程工作时。 今年较早时， [我们宣布](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) 对 Teams 中的邮件公开预览版 Microsoft Graph 更改通知 API。 此 API 使开发人员能够构建能够实时收听 Microsoft Teams 消息的应用，然后为客户和合作伙伴实施 DLP 方案。 此外，Microsoft Graph 修补程序 API 允许你将 DLP 操作应用到 Teams 消息。

这两个 API 构成了适用于 Teams DLP 的 Microsoft Graph API。 可以通过尝试示例应用 [开始](https://github.com/microsoftgraph/csharp-webhook-with-resource-data)。 有关 Microsoft Teams 消息传递 Webhooks 详细信息，请参阅 [文档](/graph/api/subscription-post-subscriptions)。

有关 Teams DLP 的许可要求，请参阅 [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)安全与合规&指南。

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>适用于电子数据展示和预览 (Microsoft Graph API) 

借助[](overview-ediscovery-20.md)高级电子数据展示，组织可以发现它所位于的数据，并管理更多端到端电子数据展示工作流，同时使用智能机器学习和分析功能将数据减少到相关集， 所有这一切都在数据保持在 Microsoft 365 安全性和合规性边界内。

高级电子数据展示的图形 API 可用于以可扩展且可重复的方式创建和管理事例、审阅集和审阅集查询。 这使客户和合作伙伴能够创建应用和工作流，以自动化常见和重复的过程，例如创建事例和管理保管人和法律保留。

第一组适用于电子数据展示的图形 API 在公共预览版中可用。 我们计划在日历年结束时添加更多功能。 若要了解有关这些 API 和其他高级电子数据展示更新的信息，请参阅此 [博客](https://aka.ms/Ignite2020AeDAA)。

有关高级电子数据展示和 API 的许可要求，请参阅 [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)安全与合规许可指南中的"电子数据&部分。

### <a name="microsoft-graph-api-for-teams-export-preview"></a>适用于 Teams 导出和预览 (Microsoft Graph API) 

企业信息 (EIA) For Microsoft Teams 是客户的关键方案，因为它允许客户解决法规要求。 除了我们在 Microsoft Teams 中存档内容的内置功能外，客户和合作伙伴现在可以使用 Teams 导出 API 来解决自定义应用程序和集成方案。 Teams 导出 API 支持批量导出 (每个应用/每个租户每秒最多 200 个请求) Teams 邮件和邮件附件。 此外，API 还可以在删除邮件后的最多 30 天内访问已删除的邮件。 有关这些 Teams 导出 API 以及如何在应用程序中使用它们的信息，请参阅使用 [Microsoft Teams](/microsoftteams/export-teams-content)导出 API 导出内容。

有关使用 Teams 导出 API 的许可要求，请参阅 Microsoft [365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)安全与合规&指南。