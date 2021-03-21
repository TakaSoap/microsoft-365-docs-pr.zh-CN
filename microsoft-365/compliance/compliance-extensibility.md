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
# <a name="microsoft-365-compliance-extensibility"></a><span data-ttu-id="481f0-103">Microsoft 365 合规性扩展性</span><span class="sxs-lookup"><span data-stu-id="481f0-103">Microsoft 365 compliance extensibility</span></span>

<span data-ttu-id="481f0-104">Microsoft 365 合规性解决方案可帮助组织智能评估其合规性风险、治理和保护敏感数据，并有效响应法规要求。</span><span class="sxs-lookup"><span data-stu-id="481f0-104">Microsoft 365 compliance solutions help organizations intelligently assess their compliance risks, govern and protect sensitive data, and effectively respond to regulatory requirements.</span></span> <span data-ttu-id="481f0-105">Microsoft 365 合规性具有丰富的扩展性方案，使组织能够适应、扩展、集成、加速和支持其合规性解决方案。</span><span class="sxs-lookup"><span data-stu-id="481f0-105">Microsoft 365 compliance is rich in extensibility scenarios and enables organizations to adapt, extend, integrate, accelerate, and support their compliance solutions.</span></span>

<span data-ttu-id="481f0-106">合规性扩展性有两个关键构建基块：</span><span class="sxs-lookup"><span data-stu-id="481f0-106">There are two key building blocks for compliance extensibility:</span></span>

- <span data-ttu-id="481f0-107">**数据连接器**。</span><span class="sxs-lookup"><span data-stu-id="481f0-107">**Data connectors**.</span></span> <span data-ttu-id="481f0-108">用于导入和存档非 Microsoft 数据，以便你可以将 Microsoft 365 保护和管理功能应用于第三方数据。</span><span class="sxs-lookup"><span data-stu-id="481f0-108">Use to import and archive non-Microsoft data so you can apply Microsoft 365 protection and governance capabilities to third-party data.</span></span>

- <span data-ttu-id="481f0-109">**API**。</span><span class="sxs-lookup"><span data-stu-id="481f0-109">**APIs**.</span></span> <span data-ttu-id="481f0-110">允许以编程方式访问 Microsoft 365 合规性功能。</span><span class="sxs-lookup"><span data-stu-id="481f0-110">Enables programmatic access to Microsoft 365 compliance capabilities.</span></span>

## <a name="data-connectors"></a><span data-ttu-id="481f0-111">数据连接器</span><span class="sxs-lookup"><span data-stu-id="481f0-111">Data connectors</span></span>

<span data-ttu-id="481f0-112">Microsoft 提供可在 Microsoft 365 合规中心配置的第三方数据连接器。</span><span class="sxs-lookup"><span data-stu-id="481f0-112">Microsoft provides third-party data connectors that can be configured in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="481f0-113">有关 Microsoft 提供的数据连接器的列表，请参阅第三方 [数据连接器](archiving-third-party-data.md#third-party-data-connectors) 表。</span><span class="sxs-lookup"><span data-stu-id="481f0-113">For a list of data connectors provided by Microsoft, see the [Third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) table.</span></span> <span data-ttu-id="481f0-114">第三方数据连接器表还汇总了在 Microsoft 365 中导入和存档数据后可应用于第三方数据的合规性解决方案，以及指向每个连接器的分步说明的链接。</span><span class="sxs-lookup"><span data-stu-id="481f0-114">The table of third-party data connectors also summarizes the compliance solutions that you can apply to third-party data after you import and archive data in Microsoft 365, and links to the step-by-step instructions for each connector.</span></span>

<span data-ttu-id="481f0-115">若要了解有关 Microsoft 365 数据连接器的更多信息，请参阅存档 [第三方数据](archiving-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="481f0-115">To learn more about Microsoft 365 data connectors, see [Archiving third-party data](archiving-third-party-data.md).</span></span> <span data-ttu-id="481f0-116">如果第三数据类型不受 Microsoft 365 合规中心中提供的数据连接器支持，你可以与可以向您提供自定义连接器的合作伙伴合作。</span><span class="sxs-lookup"><span data-stu-id="481f0-116">If a third-party data type isn't supported by the data connectors available in the Microsoft 365 compliance center, you can work with a partner who can provide you with a custom connector.</span></span> <span data-ttu-id="481f0-117">有关可以合作的合作伙伴列表以及此方法的分步过程，请参阅与合作伙伴协作以存档 [第三方数据](work-with-partner-to-archive-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="481f0-117">For a list of partners you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data](work-with-partner-to-archive-third-party-data.md).</span></span>

### <a name="prerequisites-for-data-connectors"></a><span data-ttu-id="481f0-118">数据连接器的先决条件</span><span class="sxs-lookup"><span data-stu-id="481f0-118">Prerequisites for data connectors</span></span>

<span data-ttu-id="481f0-119">Microsoft 365 合规中心中提供的用于导入和存档第三方数据的许多数据连接器都需要你准备并执行第三方数据源中的配置任务。</span><span class="sxs-lookup"><span data-stu-id="481f0-119">Many of the data connectors available in the Microsoft 365 compliance center to import and archive third-party data require that you prepare and perform configuration tasks in the third-party data source.</span></span> <span data-ttu-id="481f0-120">每个第三方数据连接器都详细记录了这些先决条件。</span><span class="sxs-lookup"><span data-stu-id="481f0-120">These prerequisites are documented in detail for each third-party data connector.</span></span>

<span data-ttu-id="481f0-121">对于 Microsoft 365 合规中心内由 Microsoft 的一个合作伙伴提供的数据连接器，你的组织将需要与合作伙伴建立业务关系，然后才能部署连接器。</span><span class="sxs-lookup"><span data-stu-id="481f0-121">For data connectors in the Microsoft 365 compliance center provided by one of Microsoft's partners, your organization will need a business relationship with the partner before you can deploy a connector.</span></span>

<span data-ttu-id="481f0-122">可以在 [Microsoft 365](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) 合规性许可比较文档中找到第三方数据连接器的许可要求。</span><span class="sxs-lookup"><span data-stu-id="481f0-122">You can find licensing requirements for third-party data connectors in the [Microsoft 365 Compliance Licensing Comparison](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) document.</span></span>

## <a name="apis"></a><span data-ttu-id="481f0-123">API</span><span class="sxs-lookup"><span data-stu-id="481f0-123">APIs</span></span>

<span data-ttu-id="481f0-124">Microsoft 信息保护 SDK、Microsoft Graph API 和 Office 365 管理活动 API 中提供了 Microsoft 365 合规性 API。</span><span class="sxs-lookup"><span data-stu-id="481f0-124">Microsoft 365 compliance APIs are available in the Microsoft Information Protection SDK, Microsoft Graph API, and the Office 365 Management Activity API.</span></span> <span data-ttu-id="481f0-125">某些合规性 API 是一组新的安全性和合规性 API 的一部分，这些 API 使 Microsoft 365 客户、独立软件供应商、系统集成商和托管安全服务提供商的开发人员能够构建高价值安全性和合规性解决方案。</span><span class="sxs-lookup"><span data-stu-id="481f0-125">Some compliance APIs are part of a new set of security and compliance APIs that enable developers for Microsoft 365 customers, independent software vendors, system integrators, and managed security service providers to build high-value security and compliance solutions.</span></span>

<span data-ttu-id="481f0-126">若要详细了解如何访问 Graph API，请参阅 [Microsoft Graph 概述](/graph/overview)。</span><span class="sxs-lookup"><span data-stu-id="481f0-126">To learn more about how to access Graph APIs, see [Overview of Microsoft Graph](/graph/overview).</span></span>

### <a name="microsoft-information-protection-mip-sdk"></a><span data-ttu-id="481f0-127">Microsoft 信息保护 (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="481f0-127">Microsoft Information Protection (MIP) SDK</span></span>

<span data-ttu-id="481f0-128">MIP SDK 将 Microsoft 365 安全与合规中心中的标签和保护服务公开到第三方应用程序和服务。</span><span class="sxs-lookup"><span data-stu-id="481f0-128">The MIP SDK exposes the labeling and protection services from Microsoft 365 security and compliance centers to third-party applications and services.</span></span> <span data-ttu-id="481f0-129">开发人员可以使用 SDK 构建对将标签和保护应用到文件的本机支持。</span><span class="sxs-lookup"><span data-stu-id="481f0-129">Developers can use the SDK to build native support for applying labels and protection to files.</span></span> <span data-ttu-id="481f0-130">开发人员可以确定在检测到特定标签时应该采取哪些操作，以及 MIP 加密信息的原因。</span><span class="sxs-lookup"><span data-stu-id="481f0-130">Developers can determine which actions should be taken when specific labels are detected, and reason over MIP-encrypted information.</span></span>

<span data-ttu-id="481f0-131">高级 MIP SDK 用例包括：</span><span class="sxs-lookup"><span data-stu-id="481f0-131">High-level MIP SDK use cases include:</span></span>

- <span data-ttu-id="481f0-132">在导出时将分类标签应用于文件的业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="481f0-132">A line-of-business application that applies classification labels to files on export.</span></span>

- <span data-ttu-id="481f0-133">为 MIP 标签提供本机支持的 CAD/CAM 设计应用程序。</span><span class="sxs-lookup"><span data-stu-id="481f0-133">A CAD/CAM design application that provides native support for MIP labeling.</span></span>

- <span data-ttu-id="481f0-134">云访问安全代理或数据丢失防护解决方案，可以使用 Azure 信息保护对数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="481f0-134">A cloud access security broker or data loss prevention solution that can encrypt data with Azure Information Protection.</span></span>

<span data-ttu-id="481f0-135">若要了解有关 MIP SDK、先决条件、其他方案和示例的更多信息，请参阅 [MIP SDK 概述](/information-protection/develop/overview)。</span><span class="sxs-lookup"><span data-stu-id="481f0-135">To learn more about the MIP SDK, prerequisites, additional scenarios, and samples, see [MIP SDK Overview](/information-protection/develop/overview).</span></span>

### <a name="microsoft-graph-api-for-teams-dlp"></a><span data-ttu-id="481f0-136">适用于 Teams DLP 的 Microsoft Graph API</span><span class="sxs-lookup"><span data-stu-id="481f0-136">Microsoft Graph API for Teams DLP</span></span>

<span data-ttu-id="481f0-137">[数据丢失防护 (DLP) ](dlp-microsoft-teams.md) 功能在 Microsoft Teams 中广泛使用，尤其是在组织转移到远程工作时。</span><span class="sxs-lookup"><span data-stu-id="481f0-137">[Data loss prevention (DLP)](dlp-microsoft-teams.md) capabilities are widely used in Microsoft Teams particularly as organizations have shifted to remote work.</span></span> <span data-ttu-id="481f0-138">今年较早时， [我们宣布](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) 对 Teams 中的邮件公开预览版 Microsoft Graph 更改通知 API。</span><span class="sxs-lookup"><span data-stu-id="481f0-138">Earlier this year we [announced the public preview](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) of the Microsoft Graph Change Notification API for messages in Teams.</span></span> <span data-ttu-id="481f0-139">此 API 使开发人员能够构建能够实时收听 Microsoft Teams 消息的应用，然后为客户和合作伙伴实施 DLP 方案。</span><span class="sxs-lookup"><span data-stu-id="481f0-139">This API enables developers to build apps that can listen to Microsoft Teams messages in near-real time and then implement DLP scenarios for both customers and partners.</span></span> <span data-ttu-id="481f0-140">此外，Microsoft Graph 修补程序 API 允许你将 DLP 操作应用到 Teams 消息。</span><span class="sxs-lookup"><span data-stu-id="481f0-140">Additionally, Microsoft Graph Patch API lets you apply DLP actions to Teams messages.</span></span>

<span data-ttu-id="481f0-141">这两个 API 构成了适用于 Teams DLP 的 Microsoft Graph API。</span><span class="sxs-lookup"><span data-stu-id="481f0-141">These two APIs form the Microsoft Graph API for Teams DLP.</span></span> <span data-ttu-id="481f0-142">可以通过尝试示例应用 [开始](https://github.com/microsoftgraph/csharp-webhook-with-resource-data)。</span><span class="sxs-lookup"><span data-stu-id="481f0-142">You can get started by trying out the [sample app](https://github.com/microsoftgraph/csharp-webhook-with-resource-data).</span></span> <span data-ttu-id="481f0-143">有关 Microsoft Teams 消息传递 Webhooks 详细信息，请参阅 [文档](/graph/api/subscription-post-subscriptions)。</span><span class="sxs-lookup"><span data-stu-id="481f0-143">For more information about Microsoft Teams messaging webhooks, see the [documentation](/graph/api/subscription-post-subscriptions).</span></span>

<span data-ttu-id="481f0-144">有关 Teams DLP 的许可要求，请参阅 [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)安全与合规&指南。</span><span class="sxs-lookup"><span data-stu-id="481f0-144">For the licensing requirements for Teams DLP, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams).</span></span>

### <a name="microsoft-graph-api-for-ediscovery-preview"></a><span data-ttu-id="481f0-145">适用于电子数据展示和预览 (Microsoft Graph API) </span><span class="sxs-lookup"><span data-stu-id="481f0-145">Microsoft Graph API for eDiscovery (preview)</span></span>

<span data-ttu-id="481f0-146">借助[](overview-ediscovery-20.md)高级电子数据展示，组织可以发现它所位于的数据，并管理更多端到端电子数据展示工作流，同时使用智能机器学习和分析功能将数据减少到相关集， 所有这一切都在数据保持在 Microsoft 365 安全性和合规性边界内。</span><span class="sxs-lookup"><span data-stu-id="481f0-146">With [Advanced eDiscovery](overview-ediscovery-20.md), organizations can discover data where it lives, and manage more end-to-end eDiscovery workflows with intelligent machine-learning and analytics capabilities to reduce data to the relevant set – all while the data stays within the Microsoft 365 security and compliance boundary.</span></span>

<span data-ttu-id="481f0-147">高级电子数据展示的图形 API 可用于以可扩展且可重复的方式创建和管理事例、审阅集和审阅集查询。</span><span class="sxs-lookup"><span data-stu-id="481f0-147">Graph APIs for Advanced eDiscovery can be used to create and manage cases, review sets, and review set queries in a scalable and repeatable manner.</span></span> <span data-ttu-id="481f0-148">这使客户和合作伙伴能够创建应用和工作流，以自动化常见和重复的过程，例如创建事例和管理保管人和法律保留。</span><span class="sxs-lookup"><span data-stu-id="481f0-148">This enables customers and partners to create apps and workflows to automate common and repetitive processes such as creating cases and managing custodians and legal holds.</span></span>

<span data-ttu-id="481f0-149">第一组适用于电子数据展示的图形 API 在公共预览版中可用。</span><span class="sxs-lookup"><span data-stu-id="481f0-149">The first set of Graph APIs for eDiscovery are available in public preview.</span></span> <span data-ttu-id="481f0-150">我们计划在日历年结束时添加更多功能。</span><span class="sxs-lookup"><span data-stu-id="481f0-150">We plan to add more capabilities by the end of the calendar year.</span></span> <span data-ttu-id="481f0-151">若要了解有关这些 API 和其他高级电子数据展示更新的信息，请参阅此 [博客](https://aka.ms/Ignite2020AeDAA)。</span><span class="sxs-lookup"><span data-stu-id="481f0-151">To learn more about these APIs and other updates for Advanced eDiscovery, see this [blog](https://aka.ms/Ignite2020AeDAA).</span></span>

<span data-ttu-id="481f0-152">有关高级电子数据展示和 API 的许可要求，请参阅 [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)安全与合规许可指南中的"电子数据&部分。</span><span class="sxs-lookup"><span data-stu-id="481f0-152">For the licensing requirements for Advanced eDiscovery and the API, see the "eDiscovery" section in the [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery).</span></span>

### <a name="microsoft-graph-api-for-teams-export-preview"></a><span data-ttu-id="481f0-153">适用于 Teams 导出和预览 (Microsoft Graph API) </span><span class="sxs-lookup"><span data-stu-id="481f0-153">Microsoft Graph API for Teams Export (preview)</span></span>

<span data-ttu-id="481f0-154">企业信息 (EIA) For Microsoft Teams 是客户的关键方案，因为它允许客户解决法规要求。</span><span class="sxs-lookup"><span data-stu-id="481f0-154">Enterprise Information Archiving (EIA) for Microsoft Teams is a key scenario for our customers as it allows them to solve for regulatory requirements.</span></span> <span data-ttu-id="481f0-155">除了我们在 Microsoft Teams 中存档内容的内置功能外，客户和合作伙伴现在可以使用 Teams 导出 API 来解决自定义应用程序和集成方案。</span><span class="sxs-lookup"><span data-stu-id="481f0-155">In addition to our built-in capabilities for archiving content in Microsoft Teams, customers and partners can now use Teams Export APIs to solve for custom application and integration scenarios.</span></span> <span data-ttu-id="481f0-156">Teams 导出 API 支持批量导出 (每个应用/每个租户每秒最多 200 个请求) Teams 邮件和邮件附件。</span><span class="sxs-lookup"><span data-stu-id="481f0-156">The Teams Export APIs support bulk-export (up to 200 requests per second/per app/per tenant) of Teams messages and message attachments.</span></span> <span data-ttu-id="481f0-157">此外，API 还可以在删除邮件后的最多 30 天内访问已删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="481f0-157">Deleted messages are also accessible by the API for up to 30 days after they are deleted.</span></span> <span data-ttu-id="481f0-158">有关这些 Teams 导出 API 以及如何在应用程序中使用它们的信息，请参阅使用 [Microsoft Teams](/microsoftteams/export-teams-content)导出 API 导出内容。</span><span class="sxs-lookup"><span data-stu-id="481f0-158">For more information about these Teams Export APIs and how to use them in your applications, see [Export content with the Microsoft Teams Export APIs](/microsoftteams/export-teams-content).</span></span>

<span data-ttu-id="481f0-159">有关使用 Teams 导出 API 的许可要求，请参阅 Microsoft [365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)安全与合规&指南。</span><span class="sxs-lookup"><span data-stu-id="481f0-159">For the licensing requirements for the use of the Teams Export APIs, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>