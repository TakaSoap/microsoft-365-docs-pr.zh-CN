---
title: Microsoft 365 多地理位置
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: 在本文中，您将了解如何使用 Microsoft 365 多地理位置将 Microsoft 365 的状态扩展到多个地理区域。
ms.openlocfilehash: 10f941549fd4899d5b3a14c97e6f301339702722
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171322"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="8c491-103">Microsoft 365 多地理位置</span><span class="sxs-lookup"><span data-stu-id="8c491-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="8c491-104">利用 Microsoft 365 多地理位置，你的组织可将其 Microsoft 365 触及范围扩展到你的现有租户内的多个地理区域和/或国家或地区。</span><span class="sxs-lookup"><span data-stu-id="8c491-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="8c491-105">请联系 Microsoft 帐户团队，为 Microsoft 365 多地理位置注册你的跨国公司。</span><span class="sxs-lookup"><span data-stu-id="8c491-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="8c491-106">通过 Microsoft 365 多地理位置，你可以在选择的地理位置中预配和存储静态数据，以满足数据驻留要求，与此同时，开启面向员工的现代生产力体验的全球推广。</span><span class="sxs-lookup"><span data-stu-id="8c491-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

<span data-ttu-id="8c491-107">有关 Microsoft 365 多地理位置的视频简介，请参阅 [SharePoint Online 和 OneDrive 多地理位置，以控制数据所在的位置](https://www.youtube.com/watch?v=Do9U3JuROhk)。</span><span class="sxs-lookup"><span data-stu-id="8c491-107">For a video introduction to Microsoft 365 Multi-Geo, see [SharePoint Online and OneDrive Multi-Geo to control where your data resides](https://www.youtube.com/watch?v=Do9U3JuROhk).</span></span>

## <a name="multi-geo-architecture"></a><span data-ttu-id="8c491-108">多地理位置体系结构</span><span class="sxs-lookup"><span data-stu-id="8c491-108">Multi-Geo architecture</span></span>

<span data-ttu-id="8c491-109">在多地理位置环境中，Microsoft 365 租户由（最初在其中设置了 Microsoft 365 订阅）的中心位置以及一个或多个附属位置组成。</span><span class="sxs-lookup"><span data-stu-id="8c491-109">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="8c491-110">在多地理位置租户中，有关地理位置、组和用户信息的信息是在 Azure Active Directory (Azure AD) 中进行管控。</span><span class="sxs-lookup"><span data-stu-id="8c491-110">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="8c491-111">由于系统会集中管理你的租户信息并同步到每个地理位置中，因此共享操作以及涉及到公司中任何人的体验均包含全局意识。</span><span class="sxs-lookup"><span data-stu-id="8c491-111">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![SharePoint 管理中心中多地理位置地图的屏幕截图](../media/multi-geo-world-map.png)

<span data-ttu-id="8c491-113">请注意，Microsoft 365 多地理位置旨在满足数据驻留需求，而不是优化性能。</span><span class="sxs-lookup"><span data-stu-id="8c491-113">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="8c491-114">若要了解 Microsoft 365 性能优化，请参阅 [Microsoft 365 的网络计划和性能调整](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848)，或与支持群组联系。</span><span class="sxs-lookup"><span data-stu-id="8c491-114">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="8c491-115">术语</span><span class="sxs-lookup"><span data-stu-id="8c491-115">Terminology</span></span>

<span data-ttu-id="8c491-116">下面是用于描述 Microsoft 365 多地理位置的关键术语：</span><span class="sxs-lookup"><span data-stu-id="8c491-116">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="8c491-117">**中心位置** - 最初在其中设置你的租户的地理位置。</span><span class="sxs-lookup"><span data-stu-id="8c491-117">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="8c491-118">**地理位置管理员** - 可管理一个或多个指定附属位置的管理员。</span><span class="sxs-lookup"><span data-stu-id="8c491-118">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="8c491-119">**地理位置代码** - 给定地理位置的三个字母的代码。</span><span class="sxs-lookup"><span data-stu-id="8c491-119">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="8c491-120">**地理位置** - 可在多地理位置租户中用于托管数据的地理位置，包括 Exchange 邮箱以及 OneDrive 和 SharePoint 站点。</span><span class="sxs-lookup"><span data-stu-id="8c491-120">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="8c491-121">**首选数据位置 (PDL)** - 管理员设置的一个用户属性，指明应在其中设置 Exchange 邮箱和 OneDrive 的地理位置。</span><span class="sxs-lookup"><span data-stu-id="8c491-121">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="8c491-122">PDL 还确定在何处设置用户创建的 SharePoint 站点。</span><span class="sxs-lookup"><span data-stu-id="8c491-122">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="8c491-123">**附属位置** – 多地理位置租户中在其中启用地理位置感知 Microsoft 365 工作负载（SharePoint、OneDrive 和 Exchange）的地理位置。</span><span class="sxs-lookup"><span data-stu-id="8c491-123">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="8c491-124">**租户** - 组织在 Microsoft 365 中的表示形式，通常有一个或多个关联域（例如，contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="8c491-124">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="8c491-125">许可</span><span class="sxs-lookup"><span data-stu-id="8c491-125">Licensing</span></span>

<span data-ttu-id="8c491-126">将 Microsoft 365 多地理位置作为以下 Microsoft 365 订阅计划的附加功能，向其租户中最少有 250 个 Microsoft 365 席位并且这些席位中至少有 5% 使用多地理位置的 EA 客户提供。</span><span class="sxs-lookup"><span data-stu-id="8c491-126">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for EA customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="8c491-127">有关详细信息，请与 Microsoft 帐户团队联系。</span><span class="sxs-lookup"><span data-stu-id="8c491-127">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="8c491-128">Microsoft 365 F1、E1、E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="8c491-128">Microsoft 365 F1, E1, E3, or E5</span></span>
- <span data-ttu-id="8c491-129">Exchange Online 计划 1 或计划 2</span><span class="sxs-lookup"><span data-stu-id="8c491-129">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="8c491-130">OneDrive for Business 计划 1 或计划 2</span><span class="sxs-lookup"><span data-stu-id="8c491-130">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="8c491-131">SharePoint Online 计划 1 或计划 2</span><span class="sxs-lookup"><span data-stu-id="8c491-131">SharePoint Online Plan 1 or Plan 2</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="8c491-132">Microsoft 365 多地理位置可用性</span><span class="sxs-lookup"><span data-stu-id="8c491-132">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="8c491-133">Microsoft 365 多地理位置当前在以下国家和地区提供：</span><span class="sxs-lookup"><span data-stu-id="8c491-133">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="8c491-134">入门</span><span class="sxs-lookup"><span data-stu-id="8c491-134">Getting started</span></span>

<span data-ttu-id="8c491-135">请按照以下步骤开始使用多地理位置：</span><span class="sxs-lookup"><span data-stu-id="8c491-135">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="8c491-136">与你的帐户团队协作，_在 Microsoft 365 服务计划中添加多地理位置功能_。</span><span class="sxs-lookup"><span data-stu-id="8c491-136">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="8c491-137">他们将指导你添加需要的许可证数量。</span><span class="sxs-lookup"><span data-stu-id="8c491-137">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="8c491-138">Microsoft 365 订阅数至少为 250 个的 EA 客户可以使用多地理位置功能。</span><span class="sxs-lookup"><span data-stu-id="8c491-138">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="8c491-139">Microsoft 需要为多地理位置支持配置你的 Exchange Online 租户，然后你才能开始使用 Microsoft 365 多地理位置。</span><span class="sxs-lookup"><span data-stu-id="8c491-139">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="8c491-140">这个一次性配置流程在你订购“*Microsoft 365 中的多地理位置功能*”服务计划之后触发，并且许可证将显示在你的租户中。</span><span class="sxs-lookup"><span data-stu-id="8c491-140">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="8c491-141">在租户完成每个工作负荷的配置过程之后，您将在 [microsoft 365 消息中心](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) 收到工作负荷特定的通知，然后您可以开始配置和使用 Microsoft 365 多地理位置功能。</span><span class="sxs-lookup"><span data-stu-id="8c491-141">You will receive workload specific notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your tenant has completed the configuration process for each workload, and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span> <span data-ttu-id="8c491-142">为多地理位置配置租户所需的时间因租户而异，但大多数租户在收到功能许可证后的一个月内完成。</span><span class="sxs-lookup"><span data-stu-id="8c491-142">The time required to configure a tenant for Multi-Geo support varies from tenant to tenant, but most tenants finish within a month after receipt of the feature licenses.</span></span> <span data-ttu-id="8c491-143">较大或更复杂的租户可能需要更多时间来完成配置过程。</span><span class="sxs-lookup"><span data-stu-id="8c491-143">Larger or more complex tenants may require more time to complete the configuration process.</span></span> <span data-ttu-id="8c491-144">有关你需要的具体租户的详细信息，请与你的帐户团队联系。</span><span class="sxs-lookup"><span data-stu-id="8c491-144">Please contact your account team for details on your specific tenant should you require it.</span></span>

2. <span data-ttu-id="8c491-145">阅读[规划多地理位置环境](plan-for-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="8c491-145">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="8c491-146">了解[管理多地理位置环境](administering-a-multi-geo-environment.md)和[你的用户将对环境有怎样的体验](multi-geo-user-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="8c491-146">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="8c491-147">准备好设置 Microsoft 365 多地理位置时，请[为多地理位置配置你的租户](multi-geo-tenant-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="8c491-147">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="8c491-148">[设置搜索](configure-search-for-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="8c491-148">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c491-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c491-149">See also</span></span>

[<span data-ttu-id="8c491-150">Exchange Online 和 OneDrive 中的多地理位置功能</span><span class="sxs-lookup"><span data-stu-id="8c491-150">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="8c491-151">OneDrive 和 SharePoint Online 中的多地理位置功能</span><span class="sxs-lookup"><span data-stu-id="8c491-151">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="8c491-152">Exchange Online 中的多地理位置功能</span><span class="sxs-lookup"><span data-stu-id="8c491-152">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="8c491-153">多地理位置环境中的 Teams 体验</span><span class="sxs-lookup"><span data-stu-id="8c491-153">Teams experience in a multi-geo environment</span></span>](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)
