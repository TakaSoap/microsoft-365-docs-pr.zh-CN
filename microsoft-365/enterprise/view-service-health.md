---
title: 如何检查 Microsoft 365 服务运行状况
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: 在致电支持Microsoft 365查看服务运行状况，以查看是否有活动服务中断。
ms.openlocfilehash: 95ab260b4950d261eed1288b8fdf1f59883ff15f
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300401"
---
# <a name="how-to-check-microsoft-365-service-health"></a><span data-ttu-id="beaaf-103">如何检查 Microsoft 365 服务运行状况</span><span class="sxs-lookup"><span data-stu-id="beaaf-103">How to check Microsoft 365 service health</span></span>

<span data-ttu-id="beaaf-104">[![显示管理中心正在更改且你可在 aka.ms/aboutM365preview 找到更多详细信息的标签。](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="beaaf-104">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)</span></span>

<span data-ttu-id="beaaf-105">可以在 Microsoft 365 管理中心 中的"服务运行状况"页上查看 Microsoft 服务 的运行状况，包括 Office web 版、Yammer、Microsoft Dynamics CRM 和移动设备[管理Microsoft 365 管理中心。](https://go.microsoft.com/fwlink/p/?linkid=2024339) </span><span class="sxs-lookup"><span data-stu-id="beaaf-105">You can view the health of your Microsoft services, including Office on the web, Yammer, Microsoft Dynamics CRM, and mobile device management cloud services, on the **Service health** page in the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).</span></span> <span data-ttu-id="beaaf-106">If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.</span><span class="sxs-lookup"><span data-stu-id="beaaf-106">If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.</span></span>

<span data-ttu-id="beaaf-107">如果无法登录管理中心，可以使用服务状态页面检查阻止登录租户的已知[](https://status.office365.com)问题。</span><span class="sxs-lookup"><span data-stu-id="beaaf-107">If you are unable to sign in to the admin center, you can use the [service status page](https://status.office365.com) to check for known issues preventing you from logging into your tenant.</span></span>  <span data-ttu-id="beaaf-108">此外，在 Twitter 上的 [@MSFT365status注册](https://twitter.com/MSFT365Status) 以关注我们，以查看有关特定事件的信息。</span><span class="sxs-lookup"><span data-stu-id="beaaf-108">Also sign up to follow us at [@MSFT365status](https://twitter.com/MSFT365Status) on Twitter to see information on certain events.</span></span>

## <a name="how-to-check-service-health"></a><span data-ttu-id="beaaf-109">如何查看服务运行状况</span><span class="sxs-lookup"><span data-stu-id="beaaf-109">How to check service health</span></span>

1. <span data-ttu-id="beaaf-110">转到 上 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) Microsoft 365 管理中心，然后使用管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="beaaf-110">Go to the Microsoft 365 admin center at [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339), and sign in with an admin account.</span></span>

    > [!NOTE]
    > <span data-ttu-id="beaaf-111">分配了全局管理员或服务支持管理员角色的用户可以查看服务运行状况。</span><span class="sxs-lookup"><span data-stu-id="beaaf-111">People who are assigned the global admin or service support admin role can view service health.</span></span> <span data-ttu-id="beaaf-112">若要允许 Exchange、SharePoint 和 Skype for Business 管理员查看服务运行状况，必须向他们分配服务管理员角色。</span><span class="sxs-lookup"><span data-stu-id="beaaf-112">To allow Exchange, SharePoint, and Skype for Business admins to view service health, they must also be assigned the Service admin role.</span></span> <span data-ttu-id="beaaf-113">有关可以查看服务运行状况的角色详细信息，请参阅关于 [管理员角色](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)。</span><span class="sxs-lookup"><span data-stu-id="beaaf-113">For more information about roles that can view service health, see [About admin roles](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles).</span></span>

2. <span data-ttu-id="beaaf-114">若要查看服务运行状况，请在管理中心中，转到"运行状况服务运行状况"，或选择"主页"仪表板上的"服务  >  运行状况 **"卡**。 </span><span class="sxs-lookup"><span data-stu-id="beaaf-114">To view service health, in the admin center, go to **Health** > **Service health**, or select the **Service health** card on the **Home dashboard**.</span></span> <span data-ttu-id="beaaf-115">仪表板卡片指示是否有活动服务问题，以及指向详细"服务运行状况" **页面** 的链接。</span><span class="sxs-lookup"><span data-stu-id="beaaf-115">The dashboard card indicates whether there is an active service issue and links to the detailed **Service health** page.</span></span>

3. <span data-ttu-id="beaaf-116">在 **"服务运行状况** "页上，每个云服务的运行状况以表格格式显示。</span><span class="sxs-lookup"><span data-stu-id="beaaf-116">On the **Service health** page, the health state of each cloud service is shown in a table format.</span></span>

   ![View of current issues in service health](../media/service-health-all-services.png)

<span data-ttu-id="beaaf-118">" **所有服务** " (默认视图) 显示所有服务、其当前运行状况以及任何活动事件或公告。</span><span class="sxs-lookup"><span data-stu-id="beaaf-118">The **All services** tab (the default view) shows all services, their current health state, and any active incidents or advisories.</span></span> <span data-ttu-id="beaaf-119">"运行状况"列中 **的图标和** 状态指示每个服务的状态。</span><span class="sxs-lookup"><span data-stu-id="beaaf-119">An icon and status in the **Health** column indicate the state of each service.</span></span>

<span data-ttu-id="beaaf-120">如果服务有活动事件或公告，它们将在嵌套表中的服务名称下直接列出。</span><span class="sxs-lookup"><span data-stu-id="beaaf-120">If there is an active incident or advisory for a service they will be listed directly under the service name in a nested table.</span></span> <span data-ttu-id="beaaf-121">通过单击服务名称左侧的 V 形图标，可以折叠嵌套的表以隐藏此视图中的事件或公告。</span><span class="sxs-lookup"><span data-stu-id="beaaf-121">You can collapse the nested table to hide the incidents or advisories in this view by clicking on the chevron icon to the left of the service name.</span></span>   

<span data-ttu-id="beaaf-122">若要筛选视图以只显示所有活动事件，请选择页面顶部的"事件"选项卡。</span><span class="sxs-lookup"><span data-stu-id="beaaf-122">To filter your view to only show all the active incidents, select the **Incidents** tab at the top of the page.</span></span> <span data-ttu-id="beaaf-123">选择 **"公告"** 选项卡将只显示发布的所有活动公告。</span><span class="sxs-lookup"><span data-stu-id="beaaf-123">Selecting the **Advisories** tab will only show all the active advisories posted.</span></span>

<span data-ttu-id="beaaf-124">" **历史记录** "选项卡显示最近七个或 30 天内已解决的所有事件和公告。</span><span class="sxs-lookup"><span data-stu-id="beaaf-124">The **History** tab shows all incidents and advisories that have been resolved within the last seven or 30 days.</span></span>

<span data-ttu-id="beaaf-125">如果您遇到 Microsoft 365 服务问题，并且未在"服务运行状况"页上看到该问题，请通过选择"报告问题"并完成简短表单来告诉我们该问题。 </span><span class="sxs-lookup"><span data-stu-id="beaaf-125">If you're experiencing an issue with a Microsoft 365 service and you don’t see it listed on the **Service health** page, tell us about it by selecting **Report an issue**, and completing the short form.</span></span> <span data-ttu-id="beaaf-126">我们将查看来自其他组织的个人数据和报告，以查看问题是如何普遍出现，以及问题是否源自于我们的服务。</span><span class="sxs-lookup"><span data-stu-id="beaaf-126">We’ll look at related data and reports from other organizations to see how widespread the issue is, and if it originated with our service.</span></span> <span data-ttu-id="beaaf-127">如果是这样，我们将在"服务运行状况"页上将其添加为新事件或公告，可在其中跟踪其解决方案。</span><span class="sxs-lookup"><span data-stu-id="beaaf-127">If it did, we’ll add it as a new incident or advisory on the **Service health** page, where you can track its resolution.</span></span> <span data-ttu-id="beaaf-128">" **报告的问题** "页将显示租户从此表单报告的所有问题以及状态。</span><span class="sxs-lookup"><span data-stu-id="beaaf-128">The **Reported Issues** page will show all issues your tenant has reported from this form and the status.</span></span>

<span data-ttu-id="beaaf-129">若要自定义在仪表板上显示哪些服务的视图，请选择"首选项""自定义视图"，并清除您要从服务运行状况仪表板视图中筛选出的服务  >  的复选框。</span><span class="sxs-lookup"><span data-stu-id="beaaf-129">To customize your view of which services show up on the dashboard, select **Preferences** > **Custom view**,  and clear the checkboxes for the services you want to filter out of your Service health dashboard view.</span></span> <span data-ttu-id="beaaf-130">确保已针对要监视的每个服务选中了复选框。</span><span class="sxs-lookup"><span data-stu-id="beaaf-130">Make sure that the checkbox is selected for each service that you want to monitor.</span></span>

<span data-ttu-id="beaaf-131">若要注册影响活动事件的租户和状态更改的新事件的电子邮件通知，请选择"首选项""电子邮件"，单击"在电子邮件中向我发送服务热度通知"，然后  >  指定： </span><span class="sxs-lookup"><span data-stu-id="beaaf-131">To sign up for email notifications of new incidents that affect your tenant and status changes for an active incident, select **Preferences** > **Email**, click **Send me service heath notifications in email**, and then specify:</span></span>

- <span data-ttu-id="beaaf-132">最多两个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="beaaf-132">Up to two email addresses.</span></span>
- <span data-ttu-id="beaaf-133">是否需要事件或公告通知</span><span class="sxs-lookup"><span data-stu-id="beaaf-133">Whether you want notifications for incidents or advisories</span></span>
- <span data-ttu-id="beaaf-134">要通知的服务</span><span class="sxs-lookup"><span data-stu-id="beaaf-134">The services for which you want notification</span></span>

<span data-ttu-id="beaaf-135">还可以订阅单个事件的电子邮件通知，而不是服务的每一个事件。</span><span class="sxs-lookup"><span data-stu-id="beaaf-135">You can also subscribe to email notifications for individual events instead of every event for a service.</span></span> <span data-ttu-id="beaaf-136">为此，请选择要接收电子邮件通知更新的活动问题，选择"管理此问题的通知"，然后指定：</span><span class="sxs-lookup"><span data-stu-id="beaaf-136">To do so, select the active issue you want to receive email notification updates for, select **Manage notifications for this issue**, and then specify:</span></span> 
- <span data-ttu-id="beaaf-137">最多两个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="beaaf-137">Up to two email addresses.</span></span>

> [!NOTE]
> <span data-ttu-id="beaaf-138">每个管理员都可以设置其首选项，并且每个管理员帐户具有两个电子邮件地址的上述限制。</span><span class="sxs-lookup"><span data-stu-id="beaaf-138">Each admin can have their Preferences set and the above limit of two email address is per admin account.</span></span>

> [!TIP]
> <span data-ttu-id="beaaf-139">您还可以使用移动设备上的[Microsoft 365 管理](https://go.microsoft.com/fwlink/p/?linkid=627216)应用查看服务运行状况，这是使用推送通知保持最新状态很好的方法。</span><span class="sxs-lookup"><span data-stu-id="beaaf-139">You can also use the [Microsoft 365 Admin app](https://go.microsoft.com/fwlink/p/?linkid=627216) on your mobile device to view Service health, which is a great way to stay current with push notifications.</span></span>

### <a name="view-details-of-posted-service-health"></a><span data-ttu-id="beaaf-140">查看已发布服务的运行状况详细信息</span><span class="sxs-lookup"><span data-stu-id="beaaf-140">View details of posted service health</span></span>

<span data-ttu-id="beaaf-141">在 **"所有** 服务"视图中，选择问题标题以查看问题详细信息页面，其中显示有关该问题的详细信息，包括我们在处理解决方案时发布的所有消息的源。</span><span class="sxs-lookup"><span data-stu-id="beaaf-141">On the **All services** view, select the issue title to see the issue detail page, which shows more information about the issue, including a feed of all the messages posted while we work on a solution.</span></span> 

<span data-ttu-id="beaaf-142">[![显示服务公告的屏幕截图 ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="beaaf-142">[ ![A screenshot showing the service advisory](../media/service-health-advisory.png) ](../media/service-health-advisory.png#lightbox)</span></span>

<span data-ttu-id="beaaf-143">公告或事件摘要提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="beaaf-143">The advisory or incident summary provides the following information:</span></span>

- <span data-ttu-id="beaaf-144">**标题** - 问题的摘要。</span><span class="sxs-lookup"><span data-stu-id="beaaf-144">**Title** - A summary of the problem.</span></span>
- <span data-ttu-id="beaaf-145">**ID** - 问题的数值标识符。</span><span class="sxs-lookup"><span data-stu-id="beaaf-145">**ID** - A numeric identifier for the problem.</span></span>
- <span data-ttu-id="beaaf-146">**服务** - 受影响服务的名称。</span><span class="sxs-lookup"><span data-stu-id="beaaf-146">**Service** - The name of the affected service.</span></span>
- <span data-ttu-id="beaaf-147">**上次更新** 时间 - 上次更新服务运行状况消息的时间。</span><span class="sxs-lookup"><span data-stu-id="beaaf-147">**Last updated** - The last time that the service health message was updated.</span></span>
- <span data-ttu-id="beaaf-148">**估计开始时间** - 问题开始时的估计时间。</span><span class="sxs-lookup"><span data-stu-id="beaaf-148">**Estimated Start time** - The estimated time when the issue started.</span></span>
- <span data-ttu-id="beaaf-149">**Status** - 此问题对服务有何影响。</span><span class="sxs-lookup"><span data-stu-id="beaaf-149">**Status** - How this problem affects the service.</span></span>
- <span data-ttu-id="beaaf-150">**用户** 影响 - 此问题对最终用户的影响的简要说明。</span><span class="sxs-lookup"><span data-stu-id="beaaf-150">**User Impact** - A brief description of the impact this issue has on the end user.</span></span>
- <span data-ttu-id="beaaf-151">**所有更新** - 我们频繁发布消息，告知你我们应用解决方案的进度。</span><span class="sxs-lookup"><span data-stu-id="beaaf-151">**All Updates** - We post frequent messages to let you know the progress that we're making in applying a solution.</span></span>

![显示问题详细信息的屏幕截图](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a><span data-ttu-id="beaaf-153">翻译服务运行状况详细信息</span><span class="sxs-lookup"><span data-stu-id="beaaf-153">Translate service health details</span></span>

<span data-ttu-id="beaaf-154">我们使用机器翻译以你的首选语言自动显示消息。</span><span class="sxs-lookup"><span data-stu-id="beaaf-154">We use machine translation to automatically display messages in your preferred language.</span></span> <span data-ttu-id="beaaf-155">阅读 [消息中心帖子的语言](/microsoft-365/admin/manage/language-translation-for-message-center-posts) 翻译，详细了解如何设置语言。</span><span class="sxs-lookup"><span data-stu-id="beaaf-155">Read [Language translation for Message center posts](/microsoft-365/admin/manage/language-translation-for-message-center-posts) for more information on how to set your language.</span></span>

### <a name="definitions"></a><span data-ttu-id="beaaf-156">定义</span><span class="sxs-lookup"><span data-stu-id="beaaf-156">Definitions</span></span>

<span data-ttu-id="beaaf-157">大多数情况下，服务显示为正常，没有进一步的信息。</span><span class="sxs-lookup"><span data-stu-id="beaaf-157">Most of the time, services will appear as healthy with no further information.</span></span> <span data-ttu-id="beaaf-158">服务出现问题时，该问题会标识为公告或事件，并显示当前状态。</span><span class="sxs-lookup"><span data-stu-id="beaaf-158">When a service is having a problem, the issue is identified as either an advisory or an incident and shows a current status.</span></span>

> [!TIP]
> <span data-ttu-id="beaaf-159">服务运行状况中不会显示计划内维护事件。</span><span class="sxs-lookup"><span data-stu-id="beaaf-159">Planned maintenance events aren't shown in service health.</span></span> <span data-ttu-id="beaaf-160">可以通过" **消息中心**"随时了解最新消息，从而跟踪计划内维护事件。</span><span class="sxs-lookup"><span data-stu-id="beaaf-160">You can track planned maintenance events by staying up to date with the **Message center**.</span></span> <span data-ttu-id="beaaf-161">筛选出分类为"更改计划"的消息，了解发生更改的时间、其影响以及如何做好相应准备。</span><span class="sxs-lookup"><span data-stu-id="beaaf-161">Filter to messages categorized as Plan for change to find out when the change is going to happen, its effect, and how to prepare for it.</span></span> <span data-ttu-id="beaaf-162">有关详细信息[，请参阅 Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093)中的消息中心。</span><span class="sxs-lookup"><span data-stu-id="beaaf-162">See [Message center in Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) for more details.</span></span>

### <a name="incidents-and-advisories"></a><span data-ttu-id="beaaf-163">事件和公告</span><span class="sxs-lookup"><span data-stu-id="beaaf-163">Incidents and advisories</span></span>

| <span data-ttu-id="beaaf-164">图标</span><span class="sxs-lookup"><span data-stu-id="beaaf-164">Icon</span></span> | <span data-ttu-id="beaaf-165">说明</span><span class="sxs-lookup"><span data-stu-id="beaaf-165">Description</span></span> |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|<span data-ttu-id="beaaf-p114">如果服务显示公告，这意味着某问题正在影响一些用户，但该服务仍然可用。公告中通常存在针对该问题的变通方法，并且该问题可能是间歇性的，或其作用范围和对用户的影响有限。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p114">If a service has an advisory shown, we are aware of a problem that is affecting some users, but the service is still available. In an advisory, there is often a workaround to the problem and the problem may be intermittent or is limited in scope and user impact.</span></span>  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|<span data-ttu-id="beaaf-p115">如果服务显示遇到活动事件，则说明遇到关键问题，且服务或其主要功能目前不可用。例如，用户可能无法发送和接收电子邮件，或无法登录。事件会对用户产生显著影响。对于正在进行的事件，我们会在服务运行状况仪表板中提供有关调查、缓解措施和解决方法确认的更新。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p115">If a service has an active incident shown, it's a critical issue and the service or a major function of the service is unavailable. For example, users may be unable to send and receive email or unable to sign-in. Incidents will have noticeable impact to users. When there is an incident in progress, we will provide updates regarding the investigation, mitigation efforts, and confirmation of resolution in the Service health dashboard.</span></span>  <br/> |

### <a name="status-definitions"></a><span data-ttu-id="beaaf-174">状态定义</span><span class="sxs-lookup"><span data-stu-id="beaaf-174">Status definitions</span></span>

| <span data-ttu-id="beaaf-175">状态</span><span class="sxs-lookup"><span data-stu-id="beaaf-175">Status</span></span> | <span data-ttu-id="beaaf-176">定义</span><span class="sxs-lookup"><span data-stu-id="beaaf-176">Definition</span></span> |
|:-----|:-----|
|<span data-ttu-id="beaaf-177">**正在调查**</span><span class="sxs-lookup"><span data-stu-id="beaaf-177">**Investigating**</span></span> | <span data-ttu-id="beaaf-178">我们已发现存在潜在问题，我们正在收集有关情况和影响范围的详细信息。</span><span class="sxs-lookup"><span data-stu-id="beaaf-178">We're aware of a potential issue and are gathering more information about what's going on and the scope of impact.</span></span> |
|<span data-ttu-id="beaaf-179">**服务降级**</span><span class="sxs-lookup"><span data-stu-id="beaaf-179">**Service degradation**</span></span> | <span data-ttu-id="beaaf-p116">我们已确认存在可能影响服务或功能使用的问题。例如，如果服务的执行速度比平常慢、存在间歇性中断或某功能运行不正常，则可能看到此状态。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p116">We've confirmed that there is an issue that may affect use of a service or feature. You might see this status if a service is performing more slowly than usual, there are intermittent interruptions, or if a feature isn't working, for example.</span></span> |
|<span data-ttu-id="beaaf-182">**服务中断**</span><span class="sxs-lookup"><span data-stu-id="beaaf-182">**Service interruption**</span></span> | <span data-ttu-id="beaaf-p117">如果我们确定某问题影响用户访问服务的能力，则你将看到此状态。在本例中，问题十分重大且可持续重现。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p117">You'll see this status if we determine that an issue affects the ability for users to access the service. In this case, the issue is significant and can be reproduced consistently.</span></span> |
|<span data-ttu-id="beaaf-185">**正在还原服务**</span><span class="sxs-lookup"><span data-stu-id="beaaf-185">**Restoring service**</span></span> | <span data-ttu-id="beaaf-186">我们已确定问题成因，知晓需要采取的纠正措施，并正在将服务恢复到正常状态。</span><span class="sxs-lookup"><span data-stu-id="beaaf-186">The cause of the issue has been identified, we know what corrective action to take, and are in the process of bringing the service back to a healthy state.</span></span> |
|<span data-ttu-id="beaaf-187">**延期恢复**</span><span class="sxs-lookup"><span data-stu-id="beaaf-187">**Extended recovery**</span></span> | <span data-ttu-id="beaaf-p118">此状态表示正在执行纠正措施，为大多数用户恢复服务，但恢复所有受影响的系统仍需一些时间。如果我们为了减轻影响，而在实施永久解决措施前实施临时措施，你也可能看到此状态。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p118">This status indicates that corrective action is in progress to restore service to most users but will take some time to reach all the affected systems. You might also see this status if we've made a temporary fix to reduce impact while we wait to apply a permanent fix.</span></span> |
|<span data-ttu-id="beaaf-190">**调查暂停**</span><span class="sxs-lookup"><span data-stu-id="beaaf-190">**Investigation suspended**</span></span> | <span data-ttu-id="beaaf-p119">如果对潜在问题的详细调查需要请求客户提供其他信息，以便进行进一步的调查，则你将看到此状态。如果我们需要你的参与，我们会告知你所需的数据或日志。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p119">If our detailed investigation of a potential issue results in a request for additional information from customers to allow us to investigate further, you'll see this status. If we need you to act, we'll let you know what data or logs we need.</span></span> |
|<span data-ttu-id="beaaf-193">**已还原服务**</span><span class="sxs-lookup"><span data-stu-id="beaaf-193">**Service restored**</span></span> | <span data-ttu-id="beaaf-p120">我们确认纠正措施已解决基础问题，且服务已还原到正常状态。若要了解出了什么问题，请查看问题详细信息。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p120">We've confirmed that corrective action has resolved the underlying problem and the service has been restored to a healthy state. To find out what went wrong, view the issue details.</span></span> |
|<span data-ttu-id="beaaf-196">**误报**</span><span class="sxs-lookup"><span data-stu-id="beaaf-196">**False positive**</span></span> | <span data-ttu-id="beaaf-197">经过详细调查后，我们已确认服务运行正常且运行正常。</span><span class="sxs-lookup"><span data-stu-id="beaaf-197">After a detailed investigation, we’ve confirmed the service is healthy and operating as designed.</span></span> <span data-ttu-id="beaaf-198">未观察到对服务的影响或源自服务外部的事件的原因。</span><span class="sxs-lookup"><span data-stu-id="beaaf-198">No impact to the service was observed or the cause of the incident originated outside of the service.</span></span> |
|<span data-ttu-id="beaaf-199">**已发布的事件后报告**</span><span class="sxs-lookup"><span data-stu-id="beaaf-199">**Post-incident report published**</span></span> | <span data-ttu-id="beaaf-200">我们发布了关于特定问题的事后报告，其中包括根本原因信息和确保类似问题不再发生的下一步步骤。</span><span class="sxs-lookup"><span data-stu-id="beaaf-200">We’ve published a Post Incident Report for a specific issue that includes root cause information and next steps to ensure a similar issue doesn’t reoccur.</span></span> |

### <a name="message-post-types"></a><span data-ttu-id="beaaf-201">消息发布类型</span><span class="sxs-lookup"><span data-stu-id="beaaf-201">Message Post Types</span></span>

| <span data-ttu-id="beaaf-202">类型</span><span class="sxs-lookup"><span data-stu-id="beaaf-202">Type</span></span> | <span data-ttu-id="beaaf-203">定义</span><span class="sxs-lookup"><span data-stu-id="beaaf-203">Definition</span></span> |
|:-----|:-----|
|<span data-ttu-id="beaaf-204">**快速更新**</span><span class="sxs-lookup"><span data-stu-id="beaaf-204">**Quick Update**</span></span> | <span data-ttu-id="beaaf-205">针对影响广泛的事件的简短且频繁的增量更新，可供所有客户使用。</span><span class="sxs-lookup"><span data-stu-id="beaaf-205">Short and frequent incremental updates for broadly impacting incidents, available to all customers.</span></span> |
|<span data-ttu-id="beaaf-206">**其他详细信息**</span><span class="sxs-lookup"><span data-stu-id="beaaf-206">**Additional Details**</span></span> | <span data-ttu-id="beaaf-207">这些附加帖子将提供更丰富的技术和解决方案详细信息，以便更深入地了解事件的处理。</span><span class="sxs-lookup"><span data-stu-id="beaaf-207">These additional posts will provide richer technical and resolution details to offer deeper visibility into the handling of incidents.</span></span> <span data-ttu-id="beaaf-208">这适用于满足为监视 、Exchange Online[要求的租户](/microsoft-365/enterprise/microsoft-365-exchange-monitoring?view=o365-worldwide#requirements)。</span><span class="sxs-lookup"><span data-stu-id="beaaf-208">This is available for tenants that meet the same requirements outlined for [Exchange Online monitoring](/microsoft-365/enterprise/microsoft-365-exchange-monitoring?view=o365-worldwide#requirements),</span></span> |

### <a name="history"></a><span data-ttu-id="beaaf-209">历史记录</span><span class="sxs-lookup"><span data-stu-id="beaaf-209">History</span></span>

<span data-ttu-id="beaaf-210">服务运行状况允许你查看当前运行状况，并查看过去 30 天内影响租户的任何服务公告和事件的历史记录。</span><span class="sxs-lookup"><span data-stu-id="beaaf-210">Service health lets you look at your current health status and view the history of any service advisories and incidents that have affected your tenant in the past 30 days.</span></span> <span data-ttu-id="beaaf-211">若要查看所有服务的过去运行状况，请选择" **历史记录视图** "。</span><span class="sxs-lookup"><span data-stu-id="beaaf-211">To view the past health of all services, select **History** view.</span></span>

<span data-ttu-id="beaaf-212">有关我们对正常运行时间的承诺详细信息，请参阅 Transparent [operations from Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)。</span><span class="sxs-lookup"><span data-stu-id="beaaf-212">For more information about our commitment to uptime, see [Transparent operations from Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity).</span></span>

## <a name="related-topics"></a><span data-ttu-id="beaaf-213">相关主题</span><span class="sxs-lookup"><span data-stu-id="beaaf-213">Related topics</span></span>

[<span data-ttu-id="beaaf-214">活动报告中Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="beaaf-214">Activity Reports in the Microsoft 365 admin center</span></span>](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

[<span data-ttu-id="beaaf-215">消息中心首选项</span><span class="sxs-lookup"><span data-stu-id="beaaf-215">Message center Preferences</span></span>](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)

[<span data-ttu-id="beaaf-216">如何在管理中心Windows发布运行状况</span><span class="sxs-lookup"><span data-stu-id="beaaf-216">How to check Windows release health on admin center</span></span>](/windows/deployment/update/check-release-health)
