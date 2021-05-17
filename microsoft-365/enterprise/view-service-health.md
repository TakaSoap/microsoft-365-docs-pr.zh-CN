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
ms.openlocfilehash: e0ab4eaa1f7a96168839a4abef2f0f254a21d0ad
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644628"
---
# <a name="how-to-check-microsoft-365-service-health"></a><span data-ttu-id="3173c-103">如何检查 Microsoft 365 服务运行状况</span><span class="sxs-lookup"><span data-stu-id="3173c-103">How to check Microsoft 365 service health</span></span>

<span data-ttu-id="3173c-104">[![显示管理中心正在更改且你可在 aka.ms/aboutM365preview 找到更多详细信息的标签。](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="3173c-104">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)</span></span>

<span data-ttu-id="3173c-105">可以在 Office web 版 管理中心的"服务运行状况"页上查看 Microsoft 服务（包括 Office web 版、Yammer、Microsoft Dynamics CRM Microsoft 365 和移动设备管理[云服务）的](https://go.microsoft.com/fwlink/p/?linkid=2024339)运行状况。 </span><span class="sxs-lookup"><span data-stu-id="3173c-105">You can view the health of your Microsoft services, including Office on the web, Yammer, Microsoft Dynamics CRM, and mobile device management cloud services, on the **Service health** page in the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).</span></span> <span data-ttu-id="3173c-106">If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.</span><span class="sxs-lookup"><span data-stu-id="3173c-106">If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.</span></span>

<span data-ttu-id="3173c-107">如果无法登录管理中心，可以使用服务状态页面检查阻止登录租户的已知[](https://status.office365.com)问题。</span><span class="sxs-lookup"><span data-stu-id="3173c-107">If you are unable to sign in to the admin center, you can use the [service status page](https://status.office365.com) to check for known issues preventing you from logging into your tenant.</span></span>  <span data-ttu-id="3173c-108">此外，在 Twitter 上的 [@MSFT365status注册](https://twitter.com/MSFT365Status) 以关注我们，以查看有关特定事件的信息。</span><span class="sxs-lookup"><span data-stu-id="3173c-108">Also sign up to follow us at [@MSFT365status](https://twitter.com/MSFT365Status) on Twitter to see information on certain events.</span></span>

  
### <a name="how-to-check-service-health"></a><span data-ttu-id="3173c-109">如何查看服务运行状况</span><span class="sxs-lookup"><span data-stu-id="3173c-109">How to check service health</span></span>

1. <span data-ttu-id="3173c-110">转到 管理Microsoft 365中心 ， [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) 然后使用管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3173c-110">Go to the Microsoft 365 admin center at [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339), and sign in with an admin account.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3173c-111">分配了全局管理员或服务支持管理员角色的用户可以查看服务运行状况。</span><span class="sxs-lookup"><span data-stu-id="3173c-111">People who are assigned the global admin or service support admin role can view service health.</span></span> <span data-ttu-id="3173c-112">若要允许 Exchange、SharePoint 和 Skype for Business 管理员查看服务运行状况，必须向他们分配服务管理员角色。</span><span class="sxs-lookup"><span data-stu-id="3173c-112">To allow Exchange, SharePoint, and Skype for Business admins to view service health, they must also be assigned the Service admin role.</span></span> <span data-ttu-id="3173c-113">有关可以查看服务运行状况的角色详细信息，请参阅关于 [管理员角色](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)。</span><span class="sxs-lookup"><span data-stu-id="3173c-113">For more information about roles that can view service health, see [About admin roles](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles).</span></span>
  
2. <span data-ttu-id="3173c-114">如果未使用新的管理中心，请在主页上，选择右上角的"试用新的管理中心"切换。</span><span class="sxs-lookup"><span data-stu-id="3173c-114">If you are not using the new admin center, on the **Home** page, select the **Try the new admin center** toggle in the upper-right corner.</span></span>

3. <span data-ttu-id="3173c-115">若要查看服务运行状况，请在管理中心中，转到"运行状况服务运行状况"，或选择"主页"仪表板上的"服务  >  运行状况 **"卡**。 </span><span class="sxs-lookup"><span data-stu-id="3173c-115">To view service health, in the admin center, go to **Health** > **Service health**, or select the **Service health** card on the **Home dashboard**.</span></span> <span data-ttu-id="3173c-116">仪表板卡片指示是否有活动服务问题，以及指向详细"服务运行状况" **页面** 的链接。</span><span class="sxs-lookup"><span data-stu-id="3173c-116">The dashboard card indicates whether there is an active service issue and links to the detailed **Service health** page.</span></span>
  
4. <span data-ttu-id="3173c-117">在 **"服务运行状况** "页上，每个云服务的运行状况以表格格式显示。</span><span class="sxs-lookup"><span data-stu-id="3173c-117">On the **Service health** page, the health state of each cloud service is shown in a table format.</span></span>

   ![View of current issues in service health](../media/service-health-all-services.png)

<span data-ttu-id="3173c-119">" **所有服务** " (默认视图) 显示所有服务及其当前运行状况。</span><span class="sxs-lookup"><span data-stu-id="3173c-119">The **All services** tab (the default view) shows all services and their current health state.</span></span> <span data-ttu-id="3173c-120">图标和" **状态"** 列指示每个服务的状态。</span><span class="sxs-lookup"><span data-stu-id="3173c-120">An icon and the **Status** column indicate the state of each service.</span></span> 

<span data-ttu-id="3173c-121">若要筛选视图以筛选当前遇到事件的服务，请选择页面顶部的"事件"选项卡。</span><span class="sxs-lookup"><span data-stu-id="3173c-121">To filter your view to services currently experiencing an incident, select the **Incidents** tab at the top of the page.</span></span> <span data-ttu-id="3173c-122">选择 **"公告"** 选项卡将只显示当前已发布公告的服务。</span><span class="sxs-lookup"><span data-stu-id="3173c-122">Selecting the **Advisories** tab will show only services that currently have an advisory posted.</span></span> 

<span data-ttu-id="3173c-123">" **历史记录** "选项卡显示已解决的事件和公告的历史记录。</span><span class="sxs-lookup"><span data-stu-id="3173c-123">The **History** tab shows the history of incidents and advisories that have been resolved.</span></span>

<span data-ttu-id="3173c-124">如果您遇到 Microsoft 365 服务问题，并且未在"服务运行状况"页上看到该问题，请通过选择"报告问题"并完成简短表单来告诉我们该问题。 </span><span class="sxs-lookup"><span data-stu-id="3173c-124">If you're experiencing an issue with a Microsoft 365 service and you don’t see it listed on the **Service health** page, tell us about it by selecting **Report an issue**, and completing the short form.</span></span> <span data-ttu-id="3173c-125">我们将查看来自其他组织的个人数据和报告，以查看问题是如何普遍出现，以及问题是否源自于我们的服务。</span><span class="sxs-lookup"><span data-stu-id="3173c-125">We’ll look at related data and reports from other organizations to see how widespread the issue is, and if it originated with our service.</span></span> <span data-ttu-id="3173c-126">如果是这样，我们将在"服务运行状况"页上将其添加为新事件或公告，可在其中跟踪其解决方案。</span><span class="sxs-lookup"><span data-stu-id="3173c-126">If it did, we’ll add it as a new incident or advisory on the **Service health** page, where you can track its resolution.</span></span> <span data-ttu-id="3173c-127">如果你在大约 30 分钟内未在列表中看到它，请考虑联系支持部门以解决该问题。</span><span class="sxs-lookup"><span data-stu-id="3173c-127">If you don’t see it appear on the list within about 30 minutes, consider contacting support to resolve the issue.</span></span>

<span data-ttu-id="3173c-128">若要自定义在仪表板上显示哪些服务的视图，请选择"首选项""自定义视图"，并清除要从服务运行状况仪表板视图中筛选  >  出的服务的复选框。</span><span class="sxs-lookup"><span data-stu-id="3173c-128">To customize your view of which services show up on the dashboard, select **Preferences** > **Custom view**,  and clear the check boxes for the services you want to filter out of your Service health dashboard view.</span></span> <span data-ttu-id="3173c-129">确保选中了要监视的每个服务的复选框。</span><span class="sxs-lookup"><span data-stu-id="3173c-129">Make sure that the check box is selected for each service that you want to monitor.</span></span>    

<span data-ttu-id="3173c-130">若要注册影响活动事件的租户和状态更改的新事件的电子邮件通知，请选择"首选项""电子邮件"，单击"在电子邮件中向我发送服务热度通知"，然后  >  指定： </span><span class="sxs-lookup"><span data-stu-id="3173c-130">To sign up for email notifications of new incidents that affect your tenant and status changes for an active incident, select **Preferences** > **Email**, click **Send me service heath notifications in email**, and then specify:</span></span>

- <span data-ttu-id="3173c-131">最多两个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3173c-131">Up to two email addresses.</span></span>
- <span data-ttu-id="3173c-132">是否需要事件或公告通知</span><span class="sxs-lookup"><span data-stu-id="3173c-132">Whether you want notifications for incidents or advisories</span></span>
- <span data-ttu-id="3173c-133">要通知的服务</span><span class="sxs-lookup"><span data-stu-id="3173c-133">The services for which you want notification</span></span>

> [!NOTE]
> <span data-ttu-id="3173c-134">每个管理员都可以设置其首选项，并且每个管理员帐户具有两个电子邮件地址的上述限制。</span><span class="sxs-lookup"><span data-stu-id="3173c-134">Each admin can have their Preferences set and the above limit of two email address is per admin account.</span></span>

> [!TIP]
> <span data-ttu-id="3173c-135">您还可以使用移动设备上的[Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=627216)管理应用查看服务运行状况，这是使用推送通知保持最新状态很好的方法。</span><span class="sxs-lookup"><span data-stu-id="3173c-135">You can also use the [Microsoft 365 Admin app](https://go.microsoft.com/fwlink/p/?linkid=627216) on your mobile device to view Service health, which is a great way to stay current with push notifications.</span></span> 
  
### <a name="view-details-of-posted-service-health"></a><span data-ttu-id="3173c-136">查看已发布服务的运行状况详细信息</span><span class="sxs-lookup"><span data-stu-id="3173c-136">View details of posted service health</span></span>

<span data-ttu-id="3173c-137">在 **"所有服务** "视图中，选择服务状态将打开公告或事件的摘要视图。</span><span class="sxs-lookup"><span data-stu-id="3173c-137">On the **All services** view, selecting the service status will open a summary view of advisories or incidents.</span></span>
  
<span data-ttu-id="3173c-138">[![显示服务公告的屏幕截图 ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3173c-138">[ ![A screenshot showing the service advisory](../media/service-health-advisory.png) ](../media/service-health-advisory.png#lightbox)</span></span>

<span data-ttu-id="3173c-139">公告或事件摘要提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="3173c-139">The advisory or incident summary provides the following information:</span></span>

- <span data-ttu-id="3173c-140">**标题** - 问题的摘要。</span><span class="sxs-lookup"><span data-stu-id="3173c-140">**Title** - A summary of the problem.</span></span>
- <span data-ttu-id="3173c-141">**服务** - 受影响服务的名称。</span><span class="sxs-lookup"><span data-stu-id="3173c-141">**Service** - The name of the affected service.</span></span>
- <span data-ttu-id="3173c-142">**ID** - 问题的数值标识符。</span><span class="sxs-lookup"><span data-stu-id="3173c-142">**ID** - A numeric identifier for the problem.</span></span>
- <span data-ttu-id="3173c-143">**Status** - 此问题对服务有何影响。</span><span class="sxs-lookup"><span data-stu-id="3173c-143">**Status** - How this problem affects the service.</span></span>
- <span data-ttu-id="3173c-144">**开始时间** - 问题开始的时间。</span><span class="sxs-lookup"><span data-stu-id="3173c-144">**Start time** - The time when the issue started.</span></span>
- <span data-ttu-id="3173c-145">**上次更新** 时间 - 上次更新服务运行状况消息的时间。</span><span class="sxs-lookup"><span data-stu-id="3173c-145">**Last updated** - The last time that the service health message was updated.</span></span> <span data-ttu-id="3173c-146">我们频繁发布消息，告知你在应用解决方案方面的进度。</span><span class="sxs-lookup"><span data-stu-id="3173c-146">We post frequent messages to let you know the progress that we're making in applying a solution.</span></span>

<span data-ttu-id="3173c-147">选择问题标题以查看问题详细信息页面，其中显示有关该问题的详细信息，包括我们在处理解决方案时发布的所有[](#history)消息的历史记录。</span><span class="sxs-lookup"><span data-stu-id="3173c-147">Select the issue title to see the issue detail page, which shows more information about the issue, including the [history](#history) of all messages posted while we work on a solution.</span></span>

![显示问题详细信息的屏幕截图](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a><span data-ttu-id="3173c-149">翻译服务运行状况详细信息</span><span class="sxs-lookup"><span data-stu-id="3173c-149">Translate service health details</span></span>

<span data-ttu-id="3173c-p110">服务运行状况说明是实时发布的，因此这些说明不会自动翻译成你的语言，并且服务事件的详细信息仅以英语形式提供。若要翻译这些说明，请遵循以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3173c-p110">Because service health explanations are posted in real-time, they are not automatically translated to your language and the details of a service event are in English only. To translate the explanation, follow these steps:</span></span>
  
1. <span data-ttu-id="3173c-152">转到[翻译工具](https://www.bing.com/translator/)。</span><span class="sxs-lookup"><span data-stu-id="3173c-152">Go to [Translator](https://www.bing.com/translator/).</span></span>

2. <span data-ttu-id="3173c-p111">在" **服务运行状况**"页上，选择一个事件或公告。在" **显示详细信息**"下，复制关于该问题的文本。</span><span class="sxs-lookup"><span data-stu-id="3173c-p111">On the **Service health** page, select an incident or advisory. Under **Show details**, copy the text about the issue.</span></span>

3. <span data-ttu-id="3173c-155">在"翻译工具"中，粘贴文本，然后选择" **翻译**"。</span><span class="sxs-lookup"><span data-stu-id="3173c-155">In Translator, paste the text and choose **Translate**.</span></span>

### <a name="definitions"></a><span data-ttu-id="3173c-156">定义</span><span class="sxs-lookup"><span data-stu-id="3173c-156">Definitions</span></span>

<span data-ttu-id="3173c-157">大多数情况下，服务显示为正常，没有进一步的信息。</span><span class="sxs-lookup"><span data-stu-id="3173c-157">Most of the time, services will appear as healthy with no further information.</span></span> <span data-ttu-id="3173c-158">服务出现问题时，该问题会标识为公告或事件，并显示当前状态。</span><span class="sxs-lookup"><span data-stu-id="3173c-158">When a service is having a problem, the issue is identified as either an advisory or an incident and shows a current status.</span></span>
  
> [!TIP]
> <span data-ttu-id="3173c-159">服务运行状况中不会显示计划内维护事件。</span><span class="sxs-lookup"><span data-stu-id="3173c-159">Planned maintenance events aren't shown in service health.</span></span> <span data-ttu-id="3173c-160">可以通过" **消息中心**"随时了解最新消息，从而跟踪计划内维护事件。</span><span class="sxs-lookup"><span data-stu-id="3173c-160">You can track planned maintenance events by staying up to date with the **Message center**.</span></span> <span data-ttu-id="3173c-161">筛选出分类为"更改计划"的消息，了解发生更改的时间、其影响以及如何做好相应准备。</span><span class="sxs-lookup"><span data-stu-id="3173c-161">Filter to messages categorized as Plan for change to find out when the change is going to happen, its effect, and how to prepare for it.</span></span> <span data-ttu-id="3173c-162">有关详细信息[，请参阅 Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093)中的消息中心。</span><span class="sxs-lookup"><span data-stu-id="3173c-162">See [Message center in Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) for more details.</span></span>
  
### <a name="incidents-and-advisories"></a><span data-ttu-id="3173c-163">事件和公告</span><span class="sxs-lookup"><span data-stu-id="3173c-163">Incidents and advisories</span></span>

| <span data-ttu-id="3173c-164">Icon</span><span class="sxs-lookup"><span data-stu-id="3173c-164">Icon</span></span> | <span data-ttu-id="3173c-165">说明</span><span class="sxs-lookup"><span data-stu-id="3173c-165">Description</span></span> |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|<span data-ttu-id="3173c-p114">如果服务显示公告，这意味着某问题正在影响一些用户，但该服务仍然可用。公告中通常存在针对该问题的变通方法，并且该问题可能是间歇性的，或其作用范围和对用户的影响有限。</span><span class="sxs-lookup"><span data-stu-id="3173c-p114">If a service has an advisory shown, we are aware of a problem that is affecting some users, but the service is still available. In an advisory, there is often a workaround to the problem and the problem may be intermittent or is limited in scope and user impact.</span></span>  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|<span data-ttu-id="3173c-p115">如果服务显示遇到活动事件，则说明遇到关键问题，且服务或其主要功能目前不可用。例如，用户可能无法发送和接收电子邮件，或无法登录。事件会对用户产生显著影响。对于正在进行的事件，我们会在服务运行状况仪表板中提供有关调查、缓解措施和解决方法确认的更新。</span><span class="sxs-lookup"><span data-stu-id="3173c-p115">If a service has an active incident shown, it's a critical issue and the service or a major function of the service is unavailable. For example, users may be unable to send and receive email or unable to sign-in. Incidents will have noticeable impact to users. When there is an incident in progress, we will provide updates regarding the investigation, mitigation efforts, and confirmation of resolution in the Service health dashboard.</span></span>  <br/> |

### <a name="status-definitions"></a><span data-ttu-id="3173c-174">状态定义</span><span class="sxs-lookup"><span data-stu-id="3173c-174">Status definitions</span></span>

| <span data-ttu-id="3173c-175">状态</span><span class="sxs-lookup"><span data-stu-id="3173c-175">Status</span></span> | <span data-ttu-id="3173c-176">定义</span><span class="sxs-lookup"><span data-stu-id="3173c-176">Definition</span></span> |
|:-----|:-----|
|<span data-ttu-id="3173c-177">**正在调查**</span><span class="sxs-lookup"><span data-stu-id="3173c-177">**Investigating**</span></span> | <span data-ttu-id="3173c-178">我们已发现存在潜在问题，我们正在收集有关情况和影响范围的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3173c-178">We're aware of a potential issue and are gathering more information about what's going on and the scope of impact.</span></span> |
|<span data-ttu-id="3173c-179">**服务降级**</span><span class="sxs-lookup"><span data-stu-id="3173c-179">**Service degradation**</span></span> | <span data-ttu-id="3173c-p116">我们已确认存在可能影响服务或功能使用的问题。例如，如果服务的执行速度比平常慢、存在间歇性中断或某功能运行不正常，则可能看到此状态。</span><span class="sxs-lookup"><span data-stu-id="3173c-p116">We've confirmed that there is an issue that may affect use of a service or feature. You might see this status if a service is performing more slowly than usual, there are intermittent interruptions, or if a feature isn't working, for example.</span></span> |
|<span data-ttu-id="3173c-182">**服务中断**</span><span class="sxs-lookup"><span data-stu-id="3173c-182">**Service interruption**</span></span> | <span data-ttu-id="3173c-p117">如果我们确定某问题影响用户访问服务的能力，则你将看到此状态。在本例中，问题十分重大且可持续重现。</span><span class="sxs-lookup"><span data-stu-id="3173c-p117">You'll see this status if we determine that an issue affects the ability for users to access the service. In this case, the issue is significant and can be reproduced consistently.</span></span> |
|<span data-ttu-id="3173c-185">**正在还原服务**</span><span class="sxs-lookup"><span data-stu-id="3173c-185">**Restoring service**</span></span> | <span data-ttu-id="3173c-186">我们已确定问题成因，知晓需要采取的纠正措施，并正在将服务恢复到正常状态。</span><span class="sxs-lookup"><span data-stu-id="3173c-186">The cause of the issue has been identified, we know what corrective action to take, and are in the process of bringing the service back to a healthy state.</span></span> |
|<span data-ttu-id="3173c-187">**延期恢复**</span><span class="sxs-lookup"><span data-stu-id="3173c-187">**Extended recovery**</span></span> | <span data-ttu-id="3173c-p118">此状态表示正在执行纠正措施，为大多数用户恢复服务，但恢复所有受影响的系统仍需一些时间。如果我们为了减轻影响，而在实施永久解决措施前实施临时措施，你也可能看到此状态。</span><span class="sxs-lookup"><span data-stu-id="3173c-p118">This status indicates that corrective action is in progress to restore service to most users but will take some time to reach all the affected systems. You might also see this status if we've made a temporary fix to reduce impact while we wait to apply a permanent fix.</span></span> |
|<span data-ttu-id="3173c-190">**调查暂停**</span><span class="sxs-lookup"><span data-stu-id="3173c-190">**Investigation suspended**</span></span> | <span data-ttu-id="3173c-p119">如果对潜在问题的详细调查需要请求客户提供其他信息，以便进行进一步的调查，则你将看到此状态。如果我们需要你的参与，我们会告知你所需的数据或日志。</span><span class="sxs-lookup"><span data-stu-id="3173c-p119">If our detailed investigation of a potential issue results in a request for additional information from customers to allow us to investigate further, you'll see this status. If we need you to act, we'll let you know what data or logs we need.</span></span> |
|<span data-ttu-id="3173c-193">**已还原服务**</span><span class="sxs-lookup"><span data-stu-id="3173c-193">**Service restored**</span></span> | <span data-ttu-id="3173c-p120">我们确认纠正措施已解决基础问题，且服务已还原到正常状态。若要了解出了什么问题，请查看问题详细信息。</span><span class="sxs-lookup"><span data-stu-id="3173c-p120">We've confirmed that corrective action has resolved the underlying problem and the service has been restored to a healthy state. To find out what went wrong, view the issue details.</span></span> |
|<span data-ttu-id="3173c-196">**误报**</span><span class="sxs-lookup"><span data-stu-id="3173c-196">**False positive**</span></span> | <span data-ttu-id="3173c-197">经过详细调查后，我们已确认服务运行正常且运行正常。</span><span class="sxs-lookup"><span data-stu-id="3173c-197">After a detailed investigation, we’ve confirmed the service is healthy and operating as designed.</span></span> <span data-ttu-id="3173c-198">未观察到对服务的影响或源自服务外部的事件的原因。</span><span class="sxs-lookup"><span data-stu-id="3173c-198">No impact to the service was observed or the cause of the incident originated outside of the service.</span></span> |
|<span data-ttu-id="3173c-199">**已发布的事件后报告**</span><span class="sxs-lookup"><span data-stu-id="3173c-199">**Post-incident report published**</span></span> | <span data-ttu-id="3173c-200">我们发布了关于特定问题的事后报告，其中包括根本原因信息和确保类似问题不再发生的下一步步骤。</span><span class="sxs-lookup"><span data-stu-id="3173c-200">We’ve published a Post Incident Report for a specific issue that includes root cause information and next steps to ensure a similar issue doesn’t reoccur.</span></span> |

### <a name="history"></a><span data-ttu-id="3173c-201">历史记录</span><span class="sxs-lookup"><span data-stu-id="3173c-201">History</span></span>

<span data-ttu-id="3173c-202">服务运行状况允许你查看当前运行状况，并查看过去 30 天内影响租户的任何服务公告和事件的历史记录。</span><span class="sxs-lookup"><span data-stu-id="3173c-202">Service health lets you look at current health status and view the history of any service advisories and incidents that have affected your tenant in the past 30 days.</span></span> <span data-ttu-id="3173c-203">若要查看所有服务的过去运行状况，请选择问题 **详细信息** 页面上的"查看历史记录"。</span><span class="sxs-lookup"><span data-stu-id="3173c-203">To view the past health of all services, select **View history** on the issue detail page.</span></span>
  
![Show link to health history](../media/service-health-view-history.png)
  
<span data-ttu-id="3173c-205">显示在选定时间范围内发布的所有服务运行状况消息的列表，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3173c-205">A list of all service health messages posted in the selected timeframe is displayed, as shown below:</span></span>
  
![View service health history](../media/service-health-history.png)
  
<span data-ttu-id="3173c-207">展开任意行以查看有关问题的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="3173c-207">Expand any row to view more details about the issue.</span></span>
  
<span data-ttu-id="3173c-208">有关我们对正常运行时间的承诺详细信息，请参阅 Transparent [operations from Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)。</span><span class="sxs-lookup"><span data-stu-id="3173c-208">For more information about our commitment to uptime, see [Transparent operations from Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3173c-209">相关主题</span><span class="sxs-lookup"><span data-stu-id="3173c-209">Related topics</span></span>

<span data-ttu-id="3173c-210">[管理中心Microsoft 365报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
[消息中心首选项](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)</span><span class="sxs-lookup"><span data-stu-id="3173c-210">[Activity Reports in the Microsoft 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
[Message center Preferences](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)</span></span><br/>
[<span data-ttu-id="3173c-211">如何在管理中心Windows发布运行状况</span><span class="sxs-lookup"><span data-stu-id="3173c-211">How to check Windows release health on admin center</span></span>](https://docs.microsoft.com/windows/deployment/update/check-release-health)
