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
description: 了解如何通过使用第三方数据连接器和 Microsoft Graph Api 扩展 Microsoft 365 合规性解决方案。
ms.openlocfilehash: 284125db8243b10f5c8de7e0a37c1b7284709c28
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204291"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 合规性扩展性

Microsoft 365 合规性解决方案可帮助组织智能化评估合规性风险、管理和保护敏感数据，并有效地响应法规要求。 Microsoft 365 合规性在扩展性方案中非常丰富，使组织能够调整、扩展、集成、加速和支持其合规性解决方案。

有两个用于合规性扩展性的主要构造块：

- **数据连接器**。 用于导入和存档非 Microsoft 数据，以便您可以将 Microsoft 365 保护和治理功能应用于第三方数据。

- **Api**。 启用对 Microsoft 365 合规性功能的编程访问。

## <a name="data-connectors"></a>数据连接器

Microsoft 提供可在 Microsoft 365 合规性中心中配置的第三方数据连接器。 有关由 Microsoft 提供的数据连接器的列表，请参阅 [第三方数据连接器](archiving-third-party-data.md#third-party-data-connectors) 表。 第三方数据连接器表还概述了在 Microsoft 365 中导入和存档数据后，您可以应用于第三方数据的合规性解决方案，并提供了有关每个连接器的分步说明的链接。

若要了解有关 Microsoft 365 数据连接器的详细信息，请参阅 [存档第三方数据](archiving-third-party-data.md)。 如果 Microsoft 365 合规性中心中提供的数据连接器不支持第三方数据类型，则可以与可向您提供自定义连接器的合作伙伴合作。 有关您可以使用的合作伙伴列表和此方法的分步过程，请参阅 [与合作伙伴合作以存档第三方数据](work-with-partner-to-archive-third-party-data.md)。

### <a name="prerequisites-for-data-connectors"></a>数据连接器的先决条件

Microsoft 365 合规中心中提供的许多数据连接器若要导入和存档第三方数据，则需要在第三方数据源中准备并执行配置任务。 对于每个第三方数据连接器，都会详细记录这些必备组件。

对于 Microsoft 合作伙伴之一提供的 Microsoft 365 合规性中心中的数据连接器，贵组织将需要与合作伙伴建立业务关系，然后才能部署连接器。

您可以在 [Microsoft 365 合规性许可比较](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) 文档中找到第三方数据连接器的许可要求。

## <a name="apis"></a>API

Microsoft Information Protection SDK、Microsoft Graph API 和 Office 365 管理活动 API 中提供了 microsoft 365 合规性 Api。 某些合规性 Api 是一组新的安全和合规性 api 的一部分，它使 Microsoft 365 客户、独立软件供应商、系统集成商和托管安全服务提供商的开发人员能够构建高价值的安全性和合规性解决方案。

若要了解有关如何访问 Graph Api 的详细信息，请参阅 [Microsoft Graph 概述](https://docs.microsoft.com/graph/overview)。

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft 信息保护 (MIP) SDK

MIP SDK 向第三方应用程序和服务公开了 Microsoft 365 安全与合规中心的标签和保护服务。 开发人员可以使用 SDK 构建本机支持，以便对文件应用标签和保护。 开发者可以确定在检测到特定标签时应采取的操作，以及有关 MIP 加密信息的原因。

高级别 MIP SDK 使用案例包括：

- 在导出时将分类标签应用于文件的业务线应用程序。

- 提供对 MIP 标记的本机支持的 CAD/CAM 设计应用程序。

- 可以使用 Azure 信息保护对数据进行加密的云访问安全代理或数据丢失防护解决方案。

若要了解有关 MIP SDK、先决条件、其他方案和示例的详细信息，请参阅 [MIP Sdk 概述](https://docs.microsoft.com/information-protection/develop/overview)。

### <a name="microsoft-graph-api-for-teams-dlp"></a>适用于团队 DLP 的 Microsoft Graph API

[数据丢失防护 (DLP) ](dlp-microsoft-teams.md) 功能在 Microsoft 团队中广泛使用，尤其是在组织已移动到远程工作时。 在今年早些时候 [，我们宣布了](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) Microsoft Graph 更改通知 API 的公共预览，用于团队中的邮件。 利用此 API，开发人员可以生成实时收听 Microsoft 团队邮件的应用程序，然后为客户和合作伙伴实施 DLP 方案。 此外，Microsoft Graph 修补程序 API 还允许您将 DLP 操作应用于团队邮件。

这两个 Api 构成了团队 DLP 的 Microsoft Graph API。 您可以通过试用 [示例应用程序](https://github.com/microsoftgraph/csharp-webhook-with-resource-data)开始。 有关 Microsoft 团队邮件 webhook 的详细信息，请参阅 [文档](https://docs.microsoft.com/graph/api/subscription-post-subscriptions)。

有关团队 DLP 的许可要求，请参阅 [适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)。

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>用于电子数据展示 (预览的 Microsoft Graph API) 

使用 [高级电子数据展示](overview-ediscovery-20.md)，组织可以发现其所在的数据，并使用智能机学习和分析功能管理更多端到端的电子数据展示工作流，以将数据减少到相关集-所有数据都保持在 Microsoft 365 安全性和合规性边界内。

用于高级电子数据展示的图形 Api 可用于创建和管理案例、审阅集以及以可缩放且可重复的方式查看集查询。 这使客户和合作伙伴能够创建应用和工作流，以自动执行常见和重复性过程，如创建案例和管理保管人和法律封存。

公共预览版中提供了第一组用于电子数据展示的图形 Api。 我们计划在日历年结束时添加更多的功能。 若要了解有关这些 Api 和适用于高级电子数据展示的其他更新的详细信息，请参阅此 [博客](https://aka.ms/Ignite2020AeDAA)。

有关高级电子数据展示和 API 的许可要求，请参阅 Microsoft 365 许可指南中的 "电子数据展示" 部分，以 [了解安全性 & 合规性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)。

### <a name="microsoft-graph-api-for-teams-export-preview"></a>适用于团队的 Microsoft Graph API 导出 (预览) 

企业信息存档 (EIA) 为 Microsoft 团队是我们客户的关键方案，因为它允许他们解决法规要求。 除了我们在 Microsoft 团队中存档内容的内置功能外，客户和合作伙伴现在还可以使用团队导出 Api 来解决自定义应用程序和集成方案。 团队导出 Api 支持批量导出 (每秒/每个应用程序/每个租户的每秒/每个租户的200请求数) 团队的邮件和邮件附件。 已删除的邮件在被删除后的30天内也会被 API 访问。 有关这些团队导出 Api 以及如何在应用程序中使用它们的详细信息，请参阅 [使用 Microsoft 团队导出 Api 导出内容](https://docs.microsoft.com/microsoftteams/export-teams-content)。

有关使用团队导出 Api 的许可要求，请参阅 [适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。
