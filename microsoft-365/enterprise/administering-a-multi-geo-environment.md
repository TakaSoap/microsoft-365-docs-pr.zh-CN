---
title: 管理多地理位置环境
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: 管理员可以了解如何在多地理位置SharePoint OneDrive和启用服务。
ms.openlocfilehash: 4c5215b855b8ca1840035b39fcfbddde419c13d8
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362314"
---
# <a name="administering-a-multi-geo-environment"></a><span data-ttu-id="4451a-103">管理多地理位置环境</span><span class="sxs-lookup"><span data-stu-id="4451a-103">Administering a multi-geo environment</span></span>

<span data-ttu-id="4451a-104">下文描述了 Microsoft 365 服务在多地理位置环境中的工作方式。</span><span class="sxs-lookup"><span data-stu-id="4451a-104">Here's a look at how Microsoft 365 services work in a multi-geo environment.</span></span>

## <a name="administrator-experience"></a><span data-ttu-id="4451a-105">管理员体验</span><span class="sxs-lookup"><span data-stu-id="4451a-105">Administrator experience</span></span>

<span data-ttu-id="4451a-106">管理[SharePoint中心](https://admin.microsoft.com/sharepoint)左侧导航中具有"地理位置"选项卡，其中具有地理位置地图，可在其中查看和管理地理位置。</span><span class="sxs-lookup"><span data-stu-id="4451a-106">The [SharePoint admin center](https://admin.microsoft.com/sharepoint) has a **Geo locations** tab in the left navigation which features a geo locations map where you can view and manage your geo locations.</span></span> <span data-ttu-id="4451a-107">使用此页面添加或删除租户的地理位置。</span><span class="sxs-lookup"><span data-stu-id="4451a-107">Use this page to add or delete geo locations for your tenant.</span></span>

## <a name="audit-log-search"></a><span data-ttu-id="4451a-108">审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="4451a-108">Audit log search</span></span>

<span data-ttu-id="4451a-109">可以从 Microsoft 365 审核日志搜索页中找到所有附属位置的统一[审核日志](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)。</span><span class="sxs-lookup"><span data-stu-id="4451a-109">A unified [Audit log](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) for all your satellite locations is available from the Microsoft 365 audit log search page.</span></span> <span data-ttu-id="4451a-110">你可以查看跨地理位置的所有审核日志条目，例如，NAM 和 EUR 用户的活动将显示在一个组织视图中，然后你可以应用现有筛选器，查看特定用户的活动。</span><span class="sxs-lookup"><span data-stu-id="4451a-110">You can see all the audit log entries from across geo locations, for example, NAM & EUR users' activities will show up in one org view and then you can apply existing filters to see specific user's activities.</span></span>

## <a name="bcs-secure-store-apps"></a><span data-ttu-id="4451a-111">BCS、安全存储、应用</span><span class="sxs-lookup"><span data-stu-id="4451a-111">BCS, Secure Store, Apps</span></span>

<span data-ttu-id="4451a-112">BCS、安全存储和应用在每个附属位置都具有单独的实例，因此，SharePoint Online 管理员应从每个附属位置单独管理和配置这些服务。</span><span class="sxs-lookup"><span data-stu-id="4451a-112">BCS, Secure Store, and Apps all have separate instances in each satellite location, therefore the SharePoint Online administrator should manage and configure these services separately from each satellite location.</span></span>

## <a name="compliance-admin-center"></a><span data-ttu-id="4451a-113">合规性管理中心</span><span class="sxs-lookup"><span data-stu-id="4451a-113">Compliance admin center</span></span>

<span data-ttu-id="4451a-114">多地理位置租户有一个中央合规中心：Microsoft 365[合规性管理中心。](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="4451a-114">There is one central compliance center for a multi-geo tenant: [Microsoft 365 Compliance admin center](https://compliance.microsoft.com/).</span></span>

## <a name="ediscovery"></a><span data-ttu-id="4451a-115">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="4451a-115">eDiscovery</span></span>

<span data-ttu-id="4451a-116">默认情况下，电子数据展示管理员或多地理位置租户的管理员将只能在该租户的中心位置执行电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="4451a-116">By default, an eDiscovery Manager or Administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="4451a-117">Office 365 全局管理员必须分配电子数据展示管理者权限，以允许其他人员执行电子数据展示，并在其适用的合规性安全筛选器中分配“Region”参数，以便将要进行电子数据展示的区域指定为附属位置，否则，不会对该附属位置执行任何电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="4451a-117">The Office 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span> <span data-ttu-id="4451a-118">若要针对区域配置合规性安全筛选器，请参阅[配置 Office 365 多地理位置电子数据展示](multi-geo-ediscovery-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="4451a-118">To configure the Compliance Security Filter for a Region, see [Configure Office 365 Multi-Geo eDiscovery](multi-geo-ediscovery-configuration.md).</span></span>

## <a name="exchange-mailboxes"></a><span data-ttu-id="4451a-119">Exchange 邮箱</span><span class="sxs-lookup"><span data-stu-id="4451a-119">Exchange mailboxes</span></span>

<span data-ttu-id="4451a-120">如果更改了用户的 PDL，则会自动转移用户的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="4451a-120">Users' Exchange mailboxes are moved automatically if their PDL is changed.</span></span> <span data-ttu-id="4451a-121">创建新邮箱时，如果没有为用户的 PDL 设置值，则会将新邮箱预配到用户的 PDL 或中心位置。</span><span class="sxs-lookup"><span data-stu-id="4451a-121">When a new mailbox is created, it is provisioned to the user's PDL or to the central location if no value has been set for the user's PDL.</span></span>

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a><span data-ttu-id="4451a-122">信息保护 (DLP) 策略 (IP) 数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="4451a-122">Information Protection (IP) Data Loss Prevention (DLP) policy</span></span>

<span data-ttu-id="4451a-123">可以在“安全性和合规性”中心内为 OneDrive for Business、SharePoint 和 Exchange 设置 IP DLP 策略，并根据需要将策略的适用范围设置为整个租户或适用的用户。</span><span class="sxs-lookup"><span data-stu-id="4451a-123">You can set your IP DLP policies for OneDrive for Business, SharePoint, and Exchange in the Security and Compliance center, scoping policies as needed to the whole tenant or to applicable users.</span></span> <span data-ttu-id="4451a-124">例如：如果你希望为附属位置中的某个用户选择策略，请选择将策略应用于特定 OneDrive，并输入用户的 OneDrive url。</span><span class="sxs-lookup"><span data-stu-id="4451a-124">For example: If you wish to select a policy for a user in a satellite location, select to apply the policy to a specific OneDrive and enter the user's OneDrive url.</span></span> <span data-ttu-id="4451a-125">有关创建 DLP 的一般指南，请参阅[数据丢失防护策略概述](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)。</span><span class="sxs-lookup"><span data-stu-id="4451a-125">See [Overview of data loss prevention policies](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) for general guidance in creating DLP policies.</span></span>

<span data-ttu-id="4451a-126">DLP 策略将基于每个地理位置的适用性自动同步。</span><span class="sxs-lookup"><span data-stu-id="4451a-126">The DLP policies are automatically synchronized based on their applicability to each geo location.</span></span>

<span data-ttu-id="4451a-127">在 UI 中，无法为地理位置中的所有用户实施信息保护和数据丢失防护策略，你必须为策略选择适用的帐户，或将策略全局应用于所有帐户。</span><span class="sxs-lookup"><span data-stu-id="4451a-127">Implementing Information Protection and Data Loss prevention policies to all users in a geo location is not an option available in the UI, instead you must select the applicable accounts for the policy or apply the policy globally to all accounts.</span></span>

## <a name="microsoft-powerapps"></a><span data-ttu-id="4451a-128">Microsoft PowerApps</span><span class="sxs-lookup"><span data-stu-id="4451a-128">Microsoft PowerApps</span></span>

<span data-ttu-id="4451a-129">为附属位置创建的 PowerApp 将使用位于租户的中心位置中的终结点。</span><span class="sxs-lookup"><span data-stu-id="4451a-129">PowerApps created for the satellite location will use the end point located in the central location for the tenant.</span></span> <span data-ttu-id="4451a-130">Microsoft PowerApps 不是多地理位置服务。</span><span class="sxs-lookup"><span data-stu-id="4451a-130">Microsoft PowerApps is not a Multi-Geo service.</span></span> 

## <a name="power-automate"></a><span data-ttu-id="4451a-131">Power Automate</span><span class="sxs-lookup"><span data-stu-id="4451a-131">Power Automate</span></span>

<span data-ttu-id="4451a-132">为附属位置创建的流程将使用位于租户的默认地理位置中的终结点。</span><span class="sxs-lookup"><span data-stu-id="4451a-132">Flows created for the satellite location will use the end point located in the default geo location for the tenant.</span></span>  <span data-ttu-id="4451a-133">Power Automate不是多地理位置服务。</span><span class="sxs-lookup"><span data-stu-id="4451a-133">Power Automate is not a Multi-Geo service.</span></span> 

## <a name="sharepoint-storage-quota"></a><span data-ttu-id="4451a-134">SharePoint 存储配额</span><span class="sxs-lookup"><span data-stu-id="4451a-134">SharePoint storage quota</span></span>

<span data-ttu-id="4451a-135">默认情况下，多地理位置环境中的所有地理位置具有相同的可用租户存储配额。</span><span class="sxs-lookup"><span data-stu-id="4451a-135">By default, all geo locations of a multi-geo environment share the available tenant storage quota.</span></span>  <span data-ttu-id="4451a-136">也可通过为特定地理位置分配特定配额来管理存储配额。</span><span class="sxs-lookup"><span data-stu-id="4451a-136">You can also manage the storage quota by allocating a specific quota for a particular geo location.</span></span> <span data-ttu-id="4451a-137">有关详细信息，请参阅 [多地理位置环境中的 SharePoint 存储配额](sharepoint-multi-geo-storage-quota.md)。</span><span class="sxs-lookup"><span data-stu-id="4451a-137">For more information, see [SharePoint storage quotas in multi-geo environments](sharepoint-multi-geo-storage-quota.md).</span></span>

## <a name="sharing"></a><span data-ttu-id="4451a-138">共享</span><span class="sxs-lookup"><span data-stu-id="4451a-138">Sharing</span></span>

<span data-ttu-id="4451a-139">管理员可以为他们的每个位置设置和管理共享策略。</span><span class="sxs-lookup"><span data-stu-id="4451a-139">Administrators can set and manage sharing policies for each of their locations.</span></span> <span data-ttu-id="4451a-140">每个地理位置中的 OneDrive 和 SharePoint 站点将只遵循对应的地理位置特定共享设置。</span><span class="sxs-lookup"><span data-stu-id="4451a-140">The OneDrive and SharePoint sites in each geo location will honor only the corresponding geo specific sharing settings.</span></span> <span data-ttu-id="4451a-141">（例如，你可以为中心位置允许[外部共享](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85)，但不能为附属位置允许外部共享，反之亦然。）请注意，共享设置不允许配置地理位置之间的共享限制。</span><span class="sxs-lookup"><span data-stu-id="4451a-141">(For example, you can allow [external sharing](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) for your central location, but not for your satellite location or vice versa.) Note that the sharing settings do not allow configuring sharing limitations between geo locations.</span></span>

## <a name="stream"></a><span data-ttu-id="4451a-142">Stream</span><span class="sxs-lookup"><span data-stu-id="4451a-142">Stream</span></span>

<span data-ttu-id="4451a-143">上传到 Stream 的视频存储在上传OneDrive的视频中。</span><span class="sxs-lookup"><span data-stu-id="4451a-143">Videos uploaded to Stream are stored in the OneDrive of the person uploading.</span></span> <span data-ttu-id="4451a-144">会议录制存储在每个OneDrive与会者的会议室中。</span><span class="sxs-lookup"><span data-stu-id="4451a-144">Meeting recordings are stored in the OneDrive of each attendee who records the meeting.</span></span>

## <a name="taxonomy"></a><span data-ttu-id="4451a-145">分类</span><span class="sxs-lookup"><span data-stu-id="4451a-145">Taxonomy</span></span>

<span data-ttu-id="4451a-146">我们支持跨地理位置为企业托管的元数据使用统一[分类](/sharepoint/managed-metadata)，并将主分类托管在公司的中心位置中。</span><span class="sxs-lookup"><span data-stu-id="4451a-146">We support a unified [taxonomy](/sharepoint/managed-metadata) for enterprise managed metadata across geo locations, with the master being hosted in the central location for your company.</span></span> <span data-ttu-id="4451a-147">我们建议你通过中心位置管理全局分类，并仅向附属位置分类中添加特定于位置的术语。</span><span class="sxs-lookup"><span data-stu-id="4451a-147">We recommend that you manage your global taxonomy from the central location and only add location-specific terms to the satellite location's Taxonomy.</span></span> <span data-ttu-id="4451a-148">全局分类术语将同步到附属位置。</span><span class="sxs-lookup"><span data-stu-id="4451a-148">Global taxonomy terms will synchronize to the satellite locations.</span></span>

<span data-ttu-id="4451a-149">有关附加详细信息及开发人员指南，请参阅[管理多地理位置租户中的元数据](/sharepoint/dev/solution-guidance/multigeo-managedmetadata)。</span><span class="sxs-lookup"><span data-stu-id="4451a-149">See [Manage metadata in a multi-geo tenant](/sharepoint/dev/solution-guidance/multigeo-managedmetadata) for additional details and for developer guidance.</span></span>

## <a name="user-profile-application"></a><span data-ttu-id="4451a-150">用户配置文件应用程序</span><span class="sxs-lookup"><span data-stu-id="4451a-150">User Profile Application</span></span>

<span data-ttu-id="4451a-151">每个地理位置都有一个[用户配置文件应用程序](/sharepoint/manage-user-profiles)。</span><span class="sxs-lookup"><span data-stu-id="4451a-151">There is a [user profile application](/sharepoint/manage-user-profiles) in each geo location.</span></span> <span data-ttu-id="4451a-152">每个用户的配置文件信息都托管在其地理位置中，并可供该地理位置的管理员使用。</span><span class="sxs-lookup"><span data-stu-id="4451a-152">Each user's profile information is hosted in their geo location and available to the administrator for that geo location.</span></span>

<span data-ttu-id="4451a-153">如果你有自定义配置文件属性，建议跨地区使用同一配置文件架构并在所有地理位置或所需的位置填充自定义配置文件属性。</span><span class="sxs-lookup"><span data-stu-id="4451a-153">If you have custom profile properties, then we recommend that you use the same profile schema across geographies and populate your custom profile properties either in all geo locations or where needed.</span></span> <span data-ttu-id="4451a-154">有关如何以编程方式填充用户配置文件数据的指导，请参阅[批量用户配置文件更新 API](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="4451a-154">For guidance regarding how to populate user profile data programmatically, please refer to the [Bulk User Profile Update API](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).</span></span>

<span data-ttu-id="4451a-155">有关附加信息及开发人员指南，请参阅[在多地理位置租户中使用用户配置文件](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience)。</span><span class="sxs-lookup"><span data-stu-id="4451a-155">See [Work with user profiles in a multi-geo tenant](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) for additional details and for developer guidance.</span></span>

## <a name="yammer"></a><span data-ttu-id="4451a-156">Yammer</span><span class="sxs-lookup"><span data-stu-id="4451a-156">Yammer</span></span>

<span data-ttu-id="4451a-157">Yammer不是多地理位置工作负载。</span><span class="sxs-lookup"><span data-stu-id="4451a-157">Yammer is not a Multi-Geo workload.</span></span> <span data-ttu-id="4451a-158">Yammer中存储Yammer线程将放置在租户的中心位置。</span><span class="sxs-lookup"><span data-stu-id="4451a-158">Yammer threads stored in Yammer will be placed in the tenant’s central location.</span></span> <span data-ttu-id="4451a-159">Yammer推出文件存储更改，将在Yammer存储SharePoint。</span><span class="sxs-lookup"><span data-stu-id="4451a-159">Yammer is rolling out a file storage change which will store Yammer files within SharePoint.</span></span> <span data-ttu-id="4451a-160">Yammer中存储SharePoint文件将SharePoint组关联的Yammer网站。</span><span class="sxs-lookup"><span data-stu-id="4451a-160">Yammer files stored in SharePoint will be placed the SharePoint site associated with the Yammer group.</span></span> <span data-ttu-id="4451a-161">SharePoint组网站基于 PDL 逻辑，如SharePoint[和组所述](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups)。</span><span class="sxs-lookup"><span data-stu-id="4451a-161">SharePoint group sites are based on PDL logic as outlined in [SharePoint Sites and Groups](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups).</span></span>