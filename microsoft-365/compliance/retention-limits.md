---
title: 保留策略和保留标签策略的限制
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: 了解策略、每个保留策略和保留标签策略项目的最大数量
ms.openlocfilehash: 92647911cfc3435c2d88ce5caa0624a34467a60f
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908097"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="0434a-103">保留策略和保留标签策略的限制</span><span class="sxs-lookup"><span data-stu-id="0434a-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="0434a-104">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="0434a-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="0434a-105">使用“[保留策略和保留](retention.md#retention-policies-and-retention-labels)”来自动保留或删除组织数据时，请注意一些最大数量。</span><span class="sxs-lookup"><span data-stu-id="0434a-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="0434a-106">每个租户策略的最大数</span><span class="sxs-lookup"><span data-stu-id="0434a-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="0434a-107">单个租户最多可有 10,000 个策略（任何配置）。</span><span class="sxs-lookup"><span data-stu-id="0434a-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="0434a-108">此最大数量包括不同的保留策略，以及用于合规性的其他策略，例如 DLP、信息屏障、电子数据展示保留和敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="0434a-108">This maximum number includes the different policies for retention, and other policies for compliance such as policies for DLP, information barriers, eDiscovery holds, and sensitivity labels.</span></span>

<span data-ttu-id="0434a-109">在此 10,000 个策略限制内，每个工作负载的最大保留策略数也有一些限制:</span><span class="sxs-lookup"><span data-stu-id="0434a-109">Within this 10,000 policies limit, there are also some limits on the maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="0434a-110">Exchange Online（任何配置）：1800</span><span class="sxs-lookup"><span data-stu-id="0434a-110">Exchange (any configuration): 1,800</span></span>
- <span data-ttu-id="0434a-111">SharePoint 或 OneDrive：（自动包含所有网站）：13</span><span class="sxs-lookup"><span data-stu-id="0434a-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="0434a-112">SharePoint 或 OneDrive（包含或排除的特定位置）：2,600</span><span class="sxs-lookup"><span data-stu-id="0434a-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

<span data-ttu-id="0434a-113">尽管 Microsoft Teams 和 Yammer 的保留策略使用邮箱来存储数据以用于保留，但 Exchange Online 的最大策略数排除 Teams 和 Yammer 的保留策略。</span><span class="sxs-lookup"><span data-stu-id="0434a-113">Although retention policies for Microsoft Teams and Yammer use mailboxes to store data for retention purposes, the maximum number of policies for Exchange Online exclude retention policies for Teams and Yammer.</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="0434a-114">每个策略的最大项目数</span><span class="sxs-lookup"><span data-stu-id="0434a-114">Maximum number of items per policy</span></span>

<span data-ttu-id="0434a-115">当使用可选配置将保留设置搜索范围缩小到特定用户、特定 Microsoft 365 组或特定网站时，才需要注意每个策略的限制：</span><span class="sxs-lookup"><span data-stu-id="0434a-115">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="0434a-116">每个保留策略的最大项目数：</span><span class="sxs-lookup"><span data-stu-id="0434a-116">Maximum numbers of items per policy for retention:</span></span>

- <span data-ttu-id="0434a-117">Exchange 邮箱：1000</span><span class="sxs-lookup"><span data-stu-id="0434a-117">Exchange mailboxes: 1,000</span></span>
- <span data-ttu-id="0434a-118">Microsoft 365 组：1000</span><span class="sxs-lookup"><span data-stu-id="0434a-118">Microsoft 365 Groups: 1,000</span></span>
- <span data-ttu-id="0434a-119">Teams 频道消息：1000</span><span class="sxs-lookup"><span data-stu-id="0434a-119">Teams channel messages: 1,000</span></span>
- <span data-ttu-id="0434a-120">Teams 聊天：1000</span><span class="sxs-lookup"><span data-stu-id="0434a-120">Teams chats: 1,000</span></span>
- <span data-ttu-id="0434a-121">Yammer 社区消息：1000</span><span class="sxs-lookup"><span data-stu-id="0434a-121">Yammer community messages: 1,000</span></span>
- <span data-ttu-id="0434a-122">Yammer 用户消息：1000</span><span class="sxs-lookup"><span data-stu-id="0434a-122">Yammer user messages: 1,000</span></span>
- <span data-ttu-id="0434a-123">SharePoint 网站：100</span><span class="sxs-lookup"><span data-stu-id="0434a-123">SharePoint sites: 100</span></span>
- <span data-ttu-id="0434a-124">OneDrive 帐户：100</span><span class="sxs-lookup"><span data-stu-id="0434a-124">OneDrive accounts: 100</span></span>

<span data-ttu-id="0434a-125">Skype for Business 仅限于特定用户，且每个策略支持的数量上限是 1000。</span><span class="sxs-lookup"><span data-stu-id="0434a-125">Skype for Business has to be scoped to specific users and the maximum number supported per policy is 1,000.</span></span>

<span data-ttu-id="0434a-126">因为这些限制针对每个策略，因此如果你需要使用会导致超过这些数字的特定包含或排除，则可以创建具有相同保留设置的额外策略。</span><span class="sxs-lookup"><span data-stu-id="0434a-126">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="0434a-127">请参阅下一节，了解为此理由使用多重保留策略的一些 [场景示例和解决方案](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers)。</span><span class="sxs-lookup"><span data-stu-id="0434a-127">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="0434a-128">但是，多重保留策略会产生更高的管理费用，因此要时刻确认自己是否真的需要包含和排除。</span><span class="sxs-lookup"><span data-stu-id="0434a-128">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="0434a-129">请记住，适用于整个位置的默认配置没有任何限制，这种配置选择可能是比创建和维护多重策略更好的解决方案。</span><span class="sxs-lookup"><span data-stu-id="0434a-129">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="0434a-130">如果需要为此方案创建和维护多重策略，请考虑使用 [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) 以实现更高效的配置。</span><span class="sxs-lookup"><span data-stu-id="0434a-130">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="0434a-131">使用多个策略以避免超过最大数量的示例</span><span class="sxs-lookup"><span data-stu-id="0434a-131">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="0434a-132">下面的示例提供了一些设计方案，可在不能仅指定保留策略的位置，并且必须考虑上一节中所述的最大项目数时使用。</span><span class="sxs-lookup"><span data-stu-id="0434a-132">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="0434a-133">Exchange 示例：</span><span class="sxs-lookup"><span data-stu-id="0434a-133">Exchange example:</span></span>

- <span data-ttu-id="0434a-134">**要求**：在具有超过40000个用户邮箱的组织中，大多数用户必须将其电子邮件保留7年，但一部分已确定的用户（425）的电子邮件仅必须保留5年。</span><span class="sxs-lookup"><span data-stu-id="0434a-134">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="0434a-135">**解决方案**：为 Exchange 电子邮件创建一个保留期为7年的保留策略，并排除用户子集。</span><span class="sxs-lookup"><span data-stu-id="0434a-135">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="0434a-136">然后为 Exchange 电子邮件创建保留期为5年的第二个保留策略，其中包括用户子集。</span><span class="sxs-lookup"><span data-stu-id="0434a-136">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="0434a-137">在这两种情况下，包含和排除的数目都低于单个策略的最大指定邮箱数，并且用户的子集必须从第一个策略中明确排除，因为它的[保留期](retention.md#the-principles-of-retention-or-what-takes-precedence)比第二个策略长。</span><span class="sxs-lookup"><span data-stu-id="0434a-137">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="0434a-138">如果用户的子集需要更长的保留策略，则不需要将他们从第一个策略中排除。</span><span class="sxs-lookup"><span data-stu-id="0434a-138">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="0434a-139">使用此解决方案，如果有其他人新加入组织，则其邮箱将自动包含在限期为7年的第一个策略中，并且不会对支持的最大数量产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="0434a-139">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="0434a-140">但是，需要 5 年保留期的新用户将添加到包括和不包括数量中，并且该限制将达到 1000 个。</span><span class="sxs-lookup"><span data-stu-id="0434a-140">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="0434a-141">SharePoint 示例：</span><span class="sxs-lookup"><span data-stu-id="0434a-141">SharePoint example:</span></span>

- <span data-ttu-id="0434a-142">**要求**：一个组织拥有几千个 SharePoint 网站，但只有2000个网站需要10年的保留期，8000个网站要求保留期为4年。</span><span class="sxs-lookup"><span data-stu-id="0434a-142">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="0434a-143">**解决方案**：为 SharePoint 创建20个保留策略，保留期为10年，其中包括100个特定的网站，并为 SharePoint 创建80条保留策略，保留期为4年，其中包括100个特定网站。</span><span class="sxs-lookup"><span data-stu-id="0434a-143">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="0434a-144">由于无需保留所有 SharePoint 网站，因此必须创建指定特定网站的保留策略。</span><span class="sxs-lookup"><span data-stu-id="0434a-144">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="0434a-145">由于一个保留策略不支持超过100个指定网站，因此必须为两个保留期创建多个策略。</span><span class="sxs-lookup"><span data-stu-id="0434a-145">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="0434a-146">这些保留策略中包含的网站数量最多，因此下一个需要保留的新网站需要一个新的保留策略，而不考虑保留期。</span><span class="sxs-lookup"><span data-stu-id="0434a-146">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>

## <a name="maximum-number-of-items-for-disposition"></a><span data-ttu-id="0434a-147">每个处置的最大项目数</span><span class="sxs-lookup"><span data-stu-id="0434a-147">Maximum number of items for disposition</span></span>

<span data-ttu-id="0434a-148">对于[内容处置](disposition.md)，有一些需要注意的限制:</span><span class="sxs-lookup"><span data-stu-id="0434a-148">For the [disposition of content](disposition.md), there are some limits to be aware of:</span></span>

- <span data-ttu-id="0434a-149">每个保留标签在每个阶段最多 1000000 个等待处置的项</span><span class="sxs-lookup"><span data-stu-id="0434a-149">1,000,000 items pending disposition per stage for each retention label</span></span>

- <span data-ttu-id="0434a-150">处置证明在项被处置后至多七年内可用，此期间每个保留标签最多 1000000 个项。</span><span class="sxs-lookup"><span data-stu-id="0434a-150">Proof of disposition for up to seven years after the item was disposed, with a limit of 1,000,000 items per retention label for that period.</span></span> 
    
<span data-ttu-id="0434a-151">如果你需要超过 1000000 个记录项的证明，请联系 [Microsoft 支持](../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="0434a-151">If you need proof of disposition higher than this limit of 1,000,000 for items that are marked as records, contact [Microsoft Support](../business-video/get-help-support.md).</span></span>
