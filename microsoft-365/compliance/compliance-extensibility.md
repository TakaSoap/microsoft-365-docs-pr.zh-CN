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
ms.openlocfilehash: 8eeb83013ec412ed82973b37c4c10e2250f5eaf8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285738"
---
# <a name="microsoft-365-compliance-extensibility"></a><span data-ttu-id="a8406-103">Microsoft 365 合规性扩展性</span><span class="sxs-lookup"><span data-stu-id="a8406-103">Microsoft 365 compliance extensibility</span></span>

<span data-ttu-id="a8406-104">Microsoft 365 合规性解决方案可帮助组织智能化评估合规性风险、管理和保护敏感数据，并有效地响应法规要求。</span><span class="sxs-lookup"><span data-stu-id="a8406-104">Microsoft 365 compliance solutions help organizations intelligently assess their compliance risks, govern and protect sensitive data, and effectively respond to regulatory requirements.</span></span> <span data-ttu-id="a8406-105">Microsoft 365 合规性在扩展性方案中非常丰富，使组织能够调整、扩展、集成、加速和支持其合规性解决方案。</span><span class="sxs-lookup"><span data-stu-id="a8406-105">Microsoft 365 compliance is rich in extensibility scenarios and enables organizations to adapt, extend, integrate, accelerate, and support their compliance solutions.</span></span>

<span data-ttu-id="a8406-106">有两个用于合规性扩展性的主要构造块：</span><span class="sxs-lookup"><span data-stu-id="a8406-106">There are two key building blocks for compliance extensibility:</span></span>

- <span data-ttu-id="a8406-107">**数据连接器**。</span><span class="sxs-lookup"><span data-stu-id="a8406-107">**Data connectors**.</span></span> <span data-ttu-id="a8406-108">用于导入和存档非 Microsoft 数据，以便您可以将 Microsoft 365 保护和治理功能应用于第三方数据。</span><span class="sxs-lookup"><span data-stu-id="a8406-108">Use to import and archive non-Microsoft data so you can apply Microsoft 365 protection and governance capabilities to third-party data.</span></span>

- <span data-ttu-id="a8406-109">**Api**。</span><span class="sxs-lookup"><span data-stu-id="a8406-109">**APIs**.</span></span> <span data-ttu-id="a8406-110">启用对 Microsoft 365 合规性功能的编程访问。</span><span class="sxs-lookup"><span data-stu-id="a8406-110">Enables programmatic access to Microsoft 365 compliance capabilities.</span></span>

## <a name="data-connectors"></a><span data-ttu-id="a8406-111">数据连接器</span><span class="sxs-lookup"><span data-stu-id="a8406-111">Data connectors</span></span>

<span data-ttu-id="a8406-112">Microsoft 提供可在 Microsoft 365 合规性中心中配置的第三方数据连接器。</span><span class="sxs-lookup"><span data-stu-id="a8406-112">Microsoft provides third-party data connectors that can be configured in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a8406-113">有关由 Microsoft 提供的数据连接器的列表，请参阅 [第三方数据连接器](archiving-third-party-data.md#third-party-data-connectors) 表。</span><span class="sxs-lookup"><span data-stu-id="a8406-113">For a list of data connectors provided by Microsoft, see the [Third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) table.</span></span> <span data-ttu-id="a8406-114">第三方数据连接器表还概述了在 Microsoft 365 中导入和存档数据后，您可以应用于第三方数据的合规性解决方案，并提供了有关每个连接器的分步说明的链接。</span><span class="sxs-lookup"><span data-stu-id="a8406-114">The table of third-party data connectors also summarizes the compliance solutions that you can apply to third-party data after you import and archive data in Microsoft 365, and links to the step-by-step instructions for each connector.</span></span>

<span data-ttu-id="a8406-115">若要了解有关 Microsoft 365 数据连接器的详细信息，请参阅 [存档第三方数据](archiving-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="a8406-115">To learn more about Microsoft 365 data connectors, see [Archiving third-party data](archiving-third-party-data.md).</span></span> <span data-ttu-id="a8406-116">如果 Microsoft 365 合规性中心中提供的数据连接器不支持第三方数据类型，则可以与可向您提供自定义连接器的合作伙伴合作。</span><span class="sxs-lookup"><span data-stu-id="a8406-116">If a third-party data type isn't supported by the data connectors available in the Microsoft 365 compliance center, you can work with a partner who can provide you with a custom connector.</span></span> <span data-ttu-id="a8406-117">有关您可以使用的合作伙伴列表和此方法的分步过程，请参阅 [与合作伙伴合作以存档第三方数据](work-with-partner-to-archive-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="a8406-117">For a list of partners you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data](work-with-partner-to-archive-third-party-data.md).</span></span>

### <a name="prerequisites-for-data-connectors"></a><span data-ttu-id="a8406-118">数据连接器的先决条件</span><span class="sxs-lookup"><span data-stu-id="a8406-118">Prerequisites for data connectors</span></span>

<span data-ttu-id="a8406-119">Microsoft 365 合规中心中提供的许多数据连接器若要导入和存档第三方数据，则需要在第三方数据源中准备并执行配置任务。</span><span class="sxs-lookup"><span data-stu-id="a8406-119">Many of the data connectors available in the Microsoft 365 compliance center to import and archive third-party data require that you prepare and perform configuration tasks in the third-party data source.</span></span> <span data-ttu-id="a8406-120">对于每个第三方数据连接器，都会详细记录这些必备组件。</span><span class="sxs-lookup"><span data-stu-id="a8406-120">These prerequisites are documented in detail for each third-party data connector.</span></span>

<span data-ttu-id="a8406-121">对于 Microsoft 合作伙伴之一提供的 Microsoft 365 合规性中心中的数据连接器，贵组织将需要与合作伙伴建立业务关系，然后才能部署连接器。</span><span class="sxs-lookup"><span data-stu-id="a8406-121">For data connectors in the Microsoft 365 compliance center provided by one of Microsoft's partners, your organization will need a business relationship with the partner before you can deploy a connector.</span></span>

<span data-ttu-id="a8406-122">您可以在 [Microsoft 365 合规性许可比较](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) 文档中找到第三方数据连接器的许可要求。</span><span class="sxs-lookup"><span data-stu-id="a8406-122">You can find licensing requirements for third-party data connectors in the [Microsoft 365 Compliance Licensing Comparison](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) document.</span></span>

## <a name="apis"></a><span data-ttu-id="a8406-123">API</span><span class="sxs-lookup"><span data-stu-id="a8406-123">APIs</span></span>

<span data-ttu-id="a8406-124">Microsoft Information Protection SDK、Microsoft Graph API 和 Office 365 管理活动 API 中提供了 microsoft 365 合规性 Api。</span><span class="sxs-lookup"><span data-stu-id="a8406-124">Microsoft 365 compliance APIs are available in the Microsoft Information Protection SDK, Microsoft Graph API, and the Office 365 Management Activity API.</span></span> <span data-ttu-id="a8406-125">某些合规性 Api 是一组新的安全和合规性 api 的一部分，它使 Microsoft 365 客户、独立软件供应商、系统集成商和托管安全服务提供商的开发人员能够构建高价值的安全性和合规性解决方案。</span><span class="sxs-lookup"><span data-stu-id="a8406-125">Some compliance APIs are part of a new set of security and compliance APIs that enable developers for Microsoft 365 customers, independent software vendors, system integrators, and managed security service providers to build high-value security and compliance solutions.</span></span>

<span data-ttu-id="a8406-126">若要了解有关如何访问 Graph Api 的详细信息，请参阅 [Microsoft Graph 概述](https://docs.microsoft.com/graph/overview)。</span><span class="sxs-lookup"><span data-stu-id="a8406-126">To learn more about how to access Graph APIs, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

### <a name="microsoft-information-protection-mip-sdk"></a><span data-ttu-id="a8406-127">Microsoft 信息保护 (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="a8406-127">Microsoft Information Protection (MIP) SDK</span></span>

<span data-ttu-id="a8406-128">MIP SDK 向第三方应用程序和服务公开了 Microsoft 365 安全与合规中心的标签和保护服务。</span><span class="sxs-lookup"><span data-stu-id="a8406-128">The MIP SDK exposes the labeling and protection services from Microsoft 365 security and compliance centers to third-party applications and services.</span></span> <span data-ttu-id="a8406-129">开发人员可以使用 SDK 构建本机支持，以便对文件应用标签和保护。</span><span class="sxs-lookup"><span data-stu-id="a8406-129">Developers can use the SDK to build native support for applying labels and protection to files.</span></span> <span data-ttu-id="a8406-130">开发者可以确定在检测到特定标签时应采取的操作，以及有关 MIP 加密信息的原因。</span><span class="sxs-lookup"><span data-stu-id="a8406-130">Developers can determine which actions should be taken when specific labels are detected, and reason over MIP-encrypted information.</span></span>

<span data-ttu-id="a8406-131">高级别 MIP SDK 使用案例包括：</span><span class="sxs-lookup"><span data-stu-id="a8406-131">High-level MIP SDK use cases include:</span></span>

- <span data-ttu-id="a8406-132">在导出时将分类标签应用于文件的业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="a8406-132">A line-of-business application that applies classification labels to files on export.</span></span>

- <span data-ttu-id="a8406-133">提供对 MIP 标记的本机支持的 CAD/CAM 设计应用程序。</span><span class="sxs-lookup"><span data-stu-id="a8406-133">A CAD/CAM design application that provides native support for MIP labeling.</span></span>

- <span data-ttu-id="a8406-134">可以使用 Azure 信息保护对数据进行加密的云访问安全代理或数据丢失防护解决方案。</span><span class="sxs-lookup"><span data-stu-id="a8406-134">A cloud access security broker or data loss prevention solution that can encrypt data with Azure Information Protection.</span></span>

<span data-ttu-id="a8406-135">若要了解有关 MIP SDK、先决条件、其他方案和示例的详细信息，请参阅 [MIP Sdk 概述](https://docs.microsoft.com/information-protection/develop/overview)。</span><span class="sxs-lookup"><span data-stu-id="a8406-135">To learn more about the MIP SDK, prerequisites, additional scenarios, and samples, see [MIP SDK Overview](https://docs.microsoft.com/information-protection/develop/overview).</span></span>

### <a name="microsoft-graph-api-for-teams-dlp"></a><span data-ttu-id="a8406-136">适用于团队 DLP 的 Microsoft Graph API</span><span class="sxs-lookup"><span data-stu-id="a8406-136">Microsoft Graph API for Teams DLP</span></span>

<span data-ttu-id="a8406-137">[数据丢失防护 (DLP) ](dlp-microsoft-teams.md) 功能在 Microsoft 团队中广泛使用，尤其是在组织已移动到远程工作时。</span><span class="sxs-lookup"><span data-stu-id="a8406-137">[Data loss prevention (DLP)](dlp-microsoft-teams.md) capabilities are widely used in Microsoft Teams particularly as organizations have shifted to remote work.</span></span> <span data-ttu-id="a8406-138">在今年早些时候 [，我们宣布了](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) Microsoft Graph 更改通知 API 的公共预览，用于团队中的邮件。</span><span class="sxs-lookup"><span data-stu-id="a8406-138">Earlier this year we [announced the public preview](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) of the Microsoft Graph Change Notification API for messages in Teams.</span></span> <span data-ttu-id="a8406-139">利用此 API，开发人员可以生成实时收听 Microsoft 团队邮件的应用程序，然后为客户和合作伙伴实施 DLP 方案。</span><span class="sxs-lookup"><span data-stu-id="a8406-139">This API enables developers to build apps that can listen to Microsoft Teams messages in near-real time and then implement DLP scenarios for both customers and partners.</span></span> <span data-ttu-id="a8406-140">此外，Microsoft Graph 修补程序 API 还允许您将 DLP 操作应用于团队邮件。</span><span class="sxs-lookup"><span data-stu-id="a8406-140">Additionally, Microsoft Graph Patch API lets you apply DLP actions to Teams messages.</span></span>

<span data-ttu-id="a8406-141">这两个 Api 构成了团队 DLP 的 Microsoft Graph API。</span><span class="sxs-lookup"><span data-stu-id="a8406-141">These two APIs form the Microsoft Graph API for Teams DLP.</span></span> <span data-ttu-id="a8406-142">您可以通过试用 [示例应用程序](https://github.com/microsoftgraph/csharp-webhook-with-resource-data)开始。</span><span class="sxs-lookup"><span data-stu-id="a8406-142">You can get started by trying out the [sample app](https://github.com/microsoftgraph/csharp-webhook-with-resource-data).</span></span> <span data-ttu-id="a8406-143">有关 Microsoft 团队邮件 webhook 的详细信息，请参阅 [文档](https://docs.microsoft.com/graph/api/subscription-post-subscriptions)。</span><span class="sxs-lookup"><span data-stu-id="a8406-143">For more information about Microsoft Teams messaging webhooks, see the [documentation](https://docs.microsoft.com/graph/api/subscription-post-subscriptions).</span></span>

<span data-ttu-id="a8406-144">有关团队 DLP 的许可要求，请参阅 [适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)。</span><span class="sxs-lookup"><span data-stu-id="a8406-144">For the licensing requirements for Teams DLP, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams).</span></span>

### <a name="microsoft-graph-api-for-ediscovery-preview"></a><span data-ttu-id="a8406-145">用于电子数据展示 (预览的 Microsoft Graph API) </span><span class="sxs-lookup"><span data-stu-id="a8406-145">Microsoft Graph API for eDiscovery (preview)</span></span>

<span data-ttu-id="a8406-146">使用 [高级电子数据展示](overview-ediscovery-20.md)，组织可以发现其所在的数据，并使用智能机学习和分析功能管理更多端到端的电子数据展示工作流，以将数据减少到相关集-所有数据都保持在 Microsoft 365 安全性和合规性边界内。</span><span class="sxs-lookup"><span data-stu-id="a8406-146">With [Advanced eDiscovery](overview-ediscovery-20.md), organizations can discover data where it lives, and manage more end-to-end eDiscovery workflows with intelligent machine-learning and analytics capabilities to reduce data to the relevant set – all while the data stays within the Microsoft 365 security and compliance boundary.</span></span>

<span data-ttu-id="a8406-147">用于高级电子数据展示的图形 Api 可用于创建和管理案例、审阅集以及以可缩放且可重复的方式查看集查询。</span><span class="sxs-lookup"><span data-stu-id="a8406-147">Graph APIs for Advanced eDiscovery can be used to create and manage cases, review sets, and review set queries in a scalable and repeatable manner.</span></span> <span data-ttu-id="a8406-148">这使客户和合作伙伴能够创建应用和工作流，以自动执行常见和重复性过程，如创建案例和管理保管人和法律封存。</span><span class="sxs-lookup"><span data-stu-id="a8406-148">This enables customers and partners to create apps and workflows to automate common and repetitive processes such as creating cases and managing custodians and legal holds.</span></span>

<span data-ttu-id="a8406-149">公共预览版中提供了第一组用于电子数据展示的图形 Api。</span><span class="sxs-lookup"><span data-stu-id="a8406-149">The first set of Graph APIs for eDiscovery are available in public preview.</span></span> <span data-ttu-id="a8406-150">我们计划在日历年结束时添加更多的功能。</span><span class="sxs-lookup"><span data-stu-id="a8406-150">We plan to add more capabilities by the end of the calendar year.</span></span> <span data-ttu-id="a8406-151">若要了解有关这些 Api 和适用于高级电子数据展示的其他更新的详细信息，请参阅此 [博客](https://aka.ms/Ignite2020AeDAA)。</span><span class="sxs-lookup"><span data-stu-id="a8406-151">To learn more about these APIs and other updates for Advanced eDiscovery, see this [blog](https://aka.ms/Ignite2020AeDAA).</span></span>

<span data-ttu-id="a8406-152">有关高级电子数据展示和 API 的许可要求，请参阅 Microsoft 365 许可指南中的 "电子数据展示" 部分，以 [了解安全性 & 合规性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="a8406-152">For the licensing requirements for Advanced eDiscovery and the API, see the "eDiscovery" section in the [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery).</span></span>

### <a name="microsoft-graph-api-for-teams-export-preview"></a><span data-ttu-id="a8406-153">适用于团队的 Microsoft Graph API 导出 (预览) </span><span class="sxs-lookup"><span data-stu-id="a8406-153">Microsoft Graph API for Teams Export (preview)</span></span>

<span data-ttu-id="a8406-154">企业信息存档 (EIA) 为 Microsoft 团队是我们客户的关键方案，因为它允许他们解决法规要求。</span><span class="sxs-lookup"><span data-stu-id="a8406-154">Enterprise Information Archiving (EIA) for Microsoft Teams is a key scenario for our customers as it allows them to solve for regulatory requirements.</span></span> <span data-ttu-id="a8406-155">除了我们在 Microsoft 团队中存档内容的内置功能外，客户和合作伙伴现在还可以使用团队导出 Api 来解决自定义应用程序和集成方案。</span><span class="sxs-lookup"><span data-stu-id="a8406-155">In addition to our built-in capabilities for archiving content in Microsoft Teams, customers and partners can now use Teams Export APIs to solve for custom application and integration scenarios.</span></span> <span data-ttu-id="a8406-156">团队导出 Api 支持批量导出 (每秒/每个应用程序/每个租户的每秒/每个租户的200请求数) 团队的邮件和邮件附件。</span><span class="sxs-lookup"><span data-stu-id="a8406-156">The Teams Export APIs support bulk-export (up to 200 requests per second/per app/per tenant) of Teams messages and message attachments.</span></span> <span data-ttu-id="a8406-157">已删除的邮件在被删除后的30天内也会被 API 访问。</span><span class="sxs-lookup"><span data-stu-id="a8406-157">Deleted messages are also accessible by the API for up to 30 days after they are deleted.</span></span> <span data-ttu-id="a8406-158">有关这些团队导出 Api 以及如何在应用程序中使用它们的详细信息，请参阅 [使用 Microsoft 团队导出 Api 导出内容](https://docs.microsoft.com/microsoftteams/export-teams-content)。</span><span class="sxs-lookup"><span data-stu-id="a8406-158">For more information about these Teams Export APIs and how to use them in your applications, see [Export content with the Microsoft Teams Export APIs](https://docs.microsoft.com/microsoftteams/export-teams-content).</span></span>

<span data-ttu-id="a8406-159">有关使用团队导出 Api 的许可要求，请参阅 [适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="a8406-159">For the licensing requirements for the use of the Teams Export APIs, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>
