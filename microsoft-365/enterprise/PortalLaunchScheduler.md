---
title: 使用门户启动计划程序启动门户
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: 本文介绍了如何使用门户启动计划程序启动门户
ms.openlocfilehash: ac55a5b0cc9d252642c890b78ccec1ba720f0957
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730254"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="81d46-103">使用门户启动计划SharePoint启动门户</span><span class="sxs-lookup"><span data-stu-id="81d46-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="81d46-104">门户是 Intranet 上高流量的 SharePoint 通信网站，在几周内拥有 10，000 到 100，000 多个查看者的网站。</span><span class="sxs-lookup"><span data-stu-id="81d46-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="81d46-105">使用门户启动计划程序启动门户，以确保用户在访问新的门户时具有流畅的SharePoint体验。</span><span class="sxs-lookup"><span data-stu-id="81d46-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="81d46-106">门户启动计划程序旨在帮助你遵循分阶段推出方法，方法是分批对查看者进行批处理，并管理新门户的 URL 重定向。</span><span class="sxs-lookup"><span data-stu-id="81d46-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="81d46-107">在每个波的启动过程中，你可以收集用户反馈、监视门户性能，并暂停启动以解决问题，然后再继续下一波。</span><span class="sxs-lookup"><span data-stu-id="81d46-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="81d46-108">详细了解如何在 SharePoint 中[规划门户SharePoint。](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="81d46-108">Learn more about how to [plan a portal launch in SharePoint](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> 

<span data-ttu-id="81d46-109">**有两种类型的重定向：**</span><span class="sxs-lookup"><span data-stu-id="81d46-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="81d46-110">**双向：启动** 新的新式SharePoint门户以替换现有SharePoint或新式门户</span><span class="sxs-lookup"><span data-stu-id="81d46-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="81d46-111">**重定向到临时页面**：启动新的新式SharePoint门户，无现有SharePoint门户</span><span class="sxs-lookup"><span data-stu-id="81d46-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="81d46-112">在启动时，必须独立于波形设置网站权限。</span><span class="sxs-lookup"><span data-stu-id="81d46-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="81d46-113">例如，如果要发布组织范围的门户，可以将权限设置为"除外部用户以外的所有人"，然后使用安全组将用户分为多个组。</span><span class="sxs-lookup"><span data-stu-id="81d46-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="81d46-114">向 Wave 添加安全组不会授予该安全组对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="81d46-114">Adding a security group to a wave does not give that security group access to the site.</span></span> 


> [!NOTE]
> - <span data-ttu-id="81d46-115">从 2021年 5 月开始，面向目标发布客户的 SharePoint 通信网站的主页上的 设置 面板可访问此功能，并将于 2021 年 7 月提供给所有客户</span><span class="sxs-lookup"><span data-stu-id="81d46-115">This feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="81d46-116">此工具的 PowerShell 版本现在可用</span><span class="sxs-lookup"><span data-stu-id="81d46-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="81d46-117">此功能只能在新式通信SharePoint使用</span><span class="sxs-lookup"><span data-stu-id="81d46-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="81d46-118">您必须具有网站的网站所有者权限才能自定义和计划门户的启动</span><span class="sxs-lookup"><span data-stu-id="81d46-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="81d46-119">启动必须至少提前 7 天进行，并且每一波可以持续 1 到 7 天</span><span class="sxs-lookup"><span data-stu-id="81d46-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="81d46-120">所需的波形数由预期用户数自动确定</span><span class="sxs-lookup"><span data-stu-id="81d46-120">The number of waves required is automatically determined by the expected number of users</span></span> 
> - <span data-ttu-id="81d46-121">在计划门户启动[之前](https://aka.ms/perftool)，必须运行 SharePoint 诊断工具，以验证网站的主页是否正常运行</span><span class="sxs-lookup"><span data-stu-id="81d46-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="81d46-122">在启动结束时，具有网站权限的所有用户都将能够访问新网站</span><span class="sxs-lookup"><span data-stu-id="81d46-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="81d46-123">如果组织使用的是[Viva 连接](https://docs.microsoft.com/SharePoint/viva-connections)，则用户可能会看到 Microsoft Teams 应用栏中的组织图标，但在选择图标后，用户将无法访问门户，直到其 Wave 启动</span><span class="sxs-lookup"><span data-stu-id="81d46-123">If your organization is using [Viva Connections](https://docs.microsoft.com/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="81d46-124">此功能不适用于德国Office 365、Office 365由世纪 (中国) 或美国政府Microsoft 365计划</span><span class="sxs-lookup"><span data-stu-id="81d46-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

### <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="81d46-125">了解门户启动计划程序选项之间的差异：</span><span class="sxs-lookup"><span data-stu-id="81d46-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="81d46-126">以前，门户启动只能通过 PowerShell SharePoint计划。</span><span class="sxs-lookup"><span data-stu-id="81d46-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="81d46-127">现在，有两个选项可帮助你计划和管理门户的启动。</span><span class="sxs-lookup"><span data-stu-id="81d46-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="81d46-128">了解这两种工具之间的主要差异：</span><span class="sxs-lookup"><span data-stu-id="81d46-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="81d46-129">**SharePointPowerShell 版本：**</span><span class="sxs-lookup"><span data-stu-id="81d46-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="81d46-130">使用 PowerShell 时需要[SharePoint凭据](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="81d46-130">Admin credentials are required to use [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span></span> 
- <span data-ttu-id="81d46-131">第一波的最低要求</span><span class="sxs-lookup"><span data-stu-id="81d46-131">Minimum requirement of one wave</span></span> 
- <span data-ttu-id="81d46-132">根据协调世界时与 UTC 时区 () 启动</span><span class="sxs-lookup"><span data-stu-id="81d46-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="81d46-133">**产品内版本：**</span><span class="sxs-lookup"><span data-stu-id="81d46-133">**In-product version:**</span></span>

- <span data-ttu-id="81d46-134">需要网站所有者凭据</span><span class="sxs-lookup"><span data-stu-id="81d46-134">Site owner credentials are required</span></span> 
- <span data-ttu-id="81d46-135">两个波形的最低要求</span><span class="sxs-lookup"><span data-stu-id="81d46-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="81d46-136">根据门户的本地时区（如区域设置中指示）计划启动</span><span class="sxs-lookup"><span data-stu-id="81d46-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>



## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="81d46-137">开始使用门户启动计划程序</span><span class="sxs-lookup"><span data-stu-id="81d46-137">Get started using the Portal launch scheduler</span></span>

1.  <span data-ttu-id="81d46-138">使用门户启动计划程序工具之前，将[](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658)需要通过网站权限访问此网站的所有用户添加为网站所有者、网站成员或访问者。</span><span class="sxs-lookup"><span data-stu-id="81d46-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2.  <span data-ttu-id="81d46-139">然后，通过以下两种方式之一访问门户启动计划程序，开始计划门户的启动：</span><span class="sxs-lookup"><span data-stu-id="81d46-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

    <span data-ttu-id="81d46-140">**选项 1：** 您编辑和重新发布对主页所做的更改（或直到主页版本 3.0 之前）的首次操作会提示您使用门户启动计划程序工具。</span><span class="sxs-lookup"><span data-stu-id="81d46-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="81d46-141">选择 **计划启动** 以使用计划前进。</span><span class="sxs-lookup"><span data-stu-id="81d46-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="81d46-142">或者， **选择"重新发布** "以重新发布页面编辑，而不计划启动。</span><span class="sxs-lookup"><span data-stu-id="81d46-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>
    
    ![重新发布主页时使用门户启动计划程序提示的图像](../media/portal-launch-republish-2.png)
    
    <span data-ttu-id="81d46-144">**选项 2：** 你随时都可以导航到 SharePoint 通信网站主页，选择 **"设置"，然后** 计划网站启动以计划门户的启动。</span><span class="sxs-lookup"><span data-stu-id="81d46-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>
    
    ![突出显示了设置网站启动"的"网站启动"窗格的图像](../media/portal-launch-settings-2.png)

3.  <span data-ttu-id="81d46-146">接下来，使用适用于 SharePoint 的页面诊断工具确认门户的运行状况分数，并根据需要对门户进行改进，[直到](https://aka.ms/perftool)门户 **获得正常分数**。</span><span class="sxs-lookup"><span data-stu-id="81d46-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="81d46-147">然后，选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="81d46-147">Then, select **Next**.</span></span>

    ![门户启动计划程序工具的图像](../media/portal-launch-panel-2.png)
       
    > [!NOTE] 
    > <span data-ttu-id="81d46-149">无法从门户启动计划程序编辑网站名称和说明，而可以通过从主页选择"网站 **设置网站信息** 进行更改。 </span><span class="sxs-lookup"><span data-stu-id="81d46-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>
 
4.  <span data-ttu-id="81d46-150">从 **下拉列表中选择** "预期用户数"。</span><span class="sxs-lookup"><span data-stu-id="81d46-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="81d46-151">此图表示最有可能需要访问网站的用户数。</span><span class="sxs-lookup"><span data-stu-id="81d46-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="81d46-152">门户启动计划程序将根据预期用户自动确定理想的波形数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="81d46-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>
    
    - <span data-ttu-id="81d46-153">少于 10，000 个用户：两个波形</span><span class="sxs-lookup"><span data-stu-id="81d46-153">Less than 10k users: Two waves</span></span>
    - <span data-ttu-id="81d46-154">10k 至 30k 用户：三个波形</span><span class="sxs-lookup"><span data-stu-id="81d46-154">10k to 30k users: Three waves</span></span> 
    - <span data-ttu-id="81d46-155">30k+ 到 100，000 个用户：五个波形</span><span class="sxs-lookup"><span data-stu-id="81d46-155">30k+ to 100k users: Five waves</span></span>
    - <span data-ttu-id="81d46-156">超过 100，000 个用户：五个波形，通过启动门户（用户超过 10 万）部分中列出的步骤联系 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="81d46-156">More than 100k users: Five waves and contact your Microsoft via the steps listed in Launch portal with over 100k users section.</span></span> 

5.  <span data-ttu-id="81d46-157">然后，确定 **所需的重定向** 类型：</span><span class="sxs-lookup"><span data-stu-id="81d46-157">Then, determine the **Type of redirect** needed:</span></span>

    <span data-ttu-id="81d46-158">**选项 1：** 将用户发送到现有 SharePoint 页面 (双向) – 在启动新的新式 SharePoint 门户以替换现有 SharePoint 门户时，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="81d46-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="81d46-159">无论用户导航到旧站点还是新站点，活动波中的用户都将重定向到新站点。</span><span class="sxs-lookup"><span data-stu-id="81d46-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="81d46-160">尝试访问新网站的非启动波中的用户将被重定向回旧网站，直到启动其 Wave。</span><span class="sxs-lookup"><span data-stu-id="81d46-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>
    
    > [!NOTE] 
    > <span data-ttu-id="81d46-161">使用双向选项时，计划启动的用户还必须具有对另一个 SharePoint 门户的网站所有者权限。</span><span class="sxs-lookup"><span data-stu-id="81d46-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>
       
    <span data-ttu-id="81d46-162">**选项 2：将** 用户发送到自动生成的临时 (页面重定向) – 当不存在现有页面重定向门户SharePoint使用临时页面重定向。</span><span class="sxs-lookup"><span data-stu-id="81d46-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="81d46-163">用户将被定向到新的新式SharePoint门户，如果用户在尚未启动的波形中，他们将被重定向到临时页面。</span><span class="sxs-lookup"><span data-stu-id="81d46-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>
    
    <span data-ttu-id="81d46-164">**选项 3：将用户** 发送到外部页面 – 在启动用户的波形之前，提供用于临时登陆页面体验的外部 URL。</span><span class="sxs-lookup"><span data-stu-id="81d46-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>
    
6.  <span data-ttu-id="81d46-165">将受众分成一个波波。</span><span class="sxs-lookup"><span data-stu-id="81d46-165">Break up your audience into waves.</span></span> <span data-ttu-id="81d46-166">每波最多添加 20 个安全组。</span><span class="sxs-lookup"><span data-stu-id="81d46-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="81d46-167">可以一直编辑 Wave 详细信息，直到启动每个 Wave。</span><span class="sxs-lookup"><span data-stu-id="81d46-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="81d46-168">每一波可以持续至少一天 (24 小时) 最多七天。</span><span class="sxs-lookup"><span data-stu-id="81d46-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="81d46-169">这使SharePoint和技术环境有机会适应和扩展大量网站用户。</span><span class="sxs-lookup"><span data-stu-id="81d46-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="81d46-170">通过 UI 计划启动时，时区基于网站的区域设置。</span><span class="sxs-lookup"><span data-stu-id="81d46-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span> 

    >[!NOTE] 
    > - <span data-ttu-id="81d46-171">门户启动计划程序将自动默认为至少 2 个波形。</span><span class="sxs-lookup"><span data-stu-id="81d46-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="81d46-172">但是，此工具的 PowerShell 版本将允许使用 1 波。</span><span class="sxs-lookup"><span data-stu-id="81d46-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
    >  - <span data-ttu-id="81d46-173">Microsoft 365版本的门户启动计划程序不支持这些组。</span><span class="sxs-lookup"><span data-stu-id="81d46-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="81d46-174">确定需要马上查看网站的用户，并输入其信息到"免受波形影响的用户 **"** 字段中。</span><span class="sxs-lookup"><span data-stu-id="81d46-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="81d46-175">这些用户被从波形中排除，并且不会在启动之前、期间或之后重定向。</span><span class="sxs-lookup"><span data-stu-id="81d46-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

8.  <span data-ttu-id="81d46-176">确认门户启动详细信息，然后选择 **计划**。</span><span class="sxs-lookup"><span data-stu-id="81d46-176">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="81d46-177">计划启动后，对 SharePoint 门户主页的任何更改都需要在门户启动恢复之前收到正常的诊断结果。</span><span class="sxs-lookup"><span data-stu-id="81d46-177">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>

### <a name="launch-portal-with-over-100k-users"></a><span data-ttu-id="81d46-178">拥有 10 万多个用户的启动门户</span><span class="sxs-lookup"><span data-stu-id="81d46-178">Launch portal with over 100k users</span></span>

<span data-ttu-id="81d46-179">如果计划启动拥有 100，000 多个用户的门户，请按照下面列出的步骤提交支持请求。</span><span class="sxs-lookup"><span data-stu-id="81d46-179">If you are planning to launch a portal with over 100,000 users, please submit a support request following the steps listed below.</span></span> <span data-ttu-id="81d46-180">请确保包含所有请求的信息。</span><span class="sxs-lookup"><span data-stu-id="81d46-180">Make sure to include all requested information.</span></span>

<span data-ttu-id="81d46-181">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="81d46-181">Follow these steps:</span></span>
1. <span data-ttu-id="81d46-182">导航到 https://admin.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="81d46-182">Navigate to https://admin.microsoft.com</span></span>
2. <span data-ttu-id="81d46-183">确保你使用的是新管理中心预览。</span><span class="sxs-lookup"><span data-stu-id="81d46-183">Ensure you are using the new admin center preview.</span></span>
3. <span data-ttu-id="81d46-184">在左侧导航窗格中，选择“支持”，然后选择“新建服务请求”。</span><span class="sxs-lookup"><span data-stu-id="81d46-184">On the left nav pane, select **Support**, and then select **New Service Request**.</span></span> 


   <span data-ttu-id="81d46-185">这将激活屏幕右侧的“**需要帮助?**”窗格。</span><span class="sxs-lookup"><span data-stu-id="81d46-185">This will activate the **Need Help?** pane on the right-hand side of your screen.</span></span>

4.  <span data-ttu-id="81d46-186">In the **Briefly describe your issue** area， enter "launch SharePoint Portal with 100k users".</span><span class="sxs-lookup"><span data-stu-id="81d46-186">In the **Briefly describe your issue** area, enter "Launch SharePoint Portal with 100k users".</span></span></br>
5. <span data-ttu-id="81d46-187">选择“联系支持人员”。</span><span class="sxs-lookup"><span data-stu-id="81d46-187">Select **Contact Support**.</span></span>
6. <span data-ttu-id="81d46-188">在 **"说明**"下，输入"SharePoint 100，000 个用户启动门户"。</span><span class="sxs-lookup"><span data-stu-id="81d46-188">Under **Description**, enter "Launch SharePoint Portal with 100k users".</span></span> 
7. <span data-ttu-id="81d46-189">填写其余信息，然后选择“与我联系”。</span><span class="sxs-lookup"><span data-stu-id="81d46-189">Fill out the remaining info, and select **Contact me**.</span></span>
8. <span data-ttu-id="81d46-190">创建票证后，请确保向支持专员提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="81d46-190">After the ticket has been created, ensure you provide the support agent with the following information:</span></span>
- <span data-ttu-id="81d46-191">启动门户 URL 的</span><span class="sxs-lookup"><span data-stu-id="81d46-191">Launch Portal URL's</span></span> 
- <span data-ttu-id="81d46-192">预期用户数</span><span class="sxs-lookup"><span data-stu-id="81d46-192">Number of users expected</span></span>
- <span data-ttu-id="81d46-193">预计启动时间</span><span class="sxs-lookup"><span data-stu-id="81d46-193">Estimated time of launch</span></span> 

## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="81d46-194">对计划的门户启动进行更改</span><span class="sxs-lookup"><span data-stu-id="81d46-194">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="81d46-195">可以编辑每一波的启动详细信息，直到 Wave 启动日期为止。</span><span class="sxs-lookup"><span data-stu-id="81d46-195">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span> 

1.  <span data-ttu-id="81d46-196">若要编辑门户启动详细信息，请导航到 **"设置，** 然后选择"**计划网站启动"。**</span><span class="sxs-lookup"><span data-stu-id="81d46-196">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2.  <span data-ttu-id="81d46-197">然后，选择"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="81d46-197">Then, select **Edit**.</span></span>
3.  <span data-ttu-id="81d46-198">完成编辑后，选择"更新 **"。**</span><span class="sxs-lookup"><span data-stu-id="81d46-198">When you are finished making your edits, select **Update**.</span></span>


## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="81d46-199">删除计划的门户启动</span><span class="sxs-lookup"><span data-stu-id="81d46-199">Delete a scheduled portal launch</span></span>

<span data-ttu-id="81d46-200">使用门户启动计划程序工具安排的启动可以随时取消或删除，即使已启动某些波形。</span><span class="sxs-lookup"><span data-stu-id="81d46-200">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1.  <span data-ttu-id="81d46-201">若要取消门户的启动，请导航到 **"设置** 计划 **网站启动"。**</span><span class="sxs-lookup"><span data-stu-id="81d46-201">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2.  <span data-ttu-id="81d46-202">然后，选择 **"删除** "，然后在看到下面的邮件时，选择"再次 **删除** "。</span><span class="sxs-lookup"><span data-stu-id="81d46-202">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

    ![门户启动计划程序工具的图像](../media/portal-launch-delete-2.png)


## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="81d46-204">使用 PowerShell 门户启动计划程序</span><span class="sxs-lookup"><span data-stu-id="81d46-204">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="81d46-205">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) and will continue to be supported through PowerShell for customers who prefer this method.</span><span class="sxs-lookup"><span data-stu-id="81d46-205">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="81d46-206">本文开头的相同说明适用于门户启动计划程序这两个版本。</span><span class="sxs-lookup"><span data-stu-id="81d46-206">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span> 

>[!NOTE]
> <span data-ttu-id="81d46-207">您需要管理员权限才能使用 SharePoint PowerShell。</span><span class="sxs-lookup"><span data-stu-id="81d46-207">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="81d46-208">将在 PowerShell 中创建的启动的门户启动详细信息显示，并可在 SharePoint 中新的门户启动计划程序工具中进行管理。</span><span class="sxs-lookup"><span data-stu-id="81d46-208">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>


### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="81d46-209">应用设置和连接到 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="81d46-209">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="81d46-210">[下载最新的SharePoint在线管理壳](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="81d46-210">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="81d46-p117">如果你已安装早期版本的SharePoint Online Management Shell，请进入添加或删除程序并卸载 "SharePoint Online Management Shell"。</span><span class="sxs-lookup"><span data-stu-id="81d46-p117">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="81d46-212">在 "下载中心" 页面上，选择你的语言，然后单击 "下载" 按钮。</span><span class="sxs-lookup"><span data-stu-id="81d46-212">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="81d46-213">系统会要求你下载 x64 和 x86 .msi 文件之间做出选择。</span><span class="sxs-lookup"><span data-stu-id="81d46-213">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="81d46-214">如果你运行的是64位版本的Windows，请下载x64文件，如果你运行的是32位版本，请下载x86文件。</span><span class="sxs-lookup"><span data-stu-id="81d46-214">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="81d46-215">如果你不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)。</span><span class="sxs-lookup"><span data-stu-id="81d46-215">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="81d46-216">下载文件后，运行该文件并按照安装向导中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="81d46-216">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="81d46-217">在Microsoft 365中，以[全局管理员或SharePoint管理员](/sharepoint/sharepoint-admin-role)连接到SharePoint。</span><span class="sxs-lookup"><span data-stu-id="81d46-217">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="81d46-218">若要了解具体操作步骤，请参阅 [SharePoint 在线管理壳入门](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="81d46-218">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="81d46-219">查看任何现有的门户启动设置</span><span class="sxs-lookup"><span data-stu-id="81d46-219">View any existing portal launch setups</span></span>

<span data-ttu-id="81d46-220">查看是否有现有的门户启动配置：</span><span class="sxs-lookup"><span data-stu-id="81d46-220">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="81d46-221">计划站点上的门户启动</span><span class="sxs-lookup"><span data-stu-id="81d46-221">Schedule a portal launch on the site</span></span>

<span data-ttu-id="81d46-222">所需的波形数取决于您预期的启动大小。</span><span class="sxs-lookup"><span data-stu-id="81d46-222">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="81d46-223">少于 10，000 个用户：一波</span><span class="sxs-lookup"><span data-stu-id="81d46-223">Less than 10k users: One wave</span></span>
- <span data-ttu-id="81d46-224">10k 至 30k 用户：三个波形</span><span class="sxs-lookup"><span data-stu-id="81d46-224">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="81d46-225">30k+ 到 100，000 个用户：五个波形</span><span class="sxs-lookup"><span data-stu-id="81d46-225">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="81d46-226">超过 100，000 个用户：五个波形并联系你的 Microsoft 帐户团队</span><span class="sxs-lookup"><span data-stu-id="81d46-226">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="81d46-227">双向重定向的步骤</span><span class="sxs-lookup"><span data-stu-id="81d46-227">Steps for bidirectional redirection</span></span>

<span data-ttu-id="81d46-228">双向重定向涉及启动新的新式 SharePoint Online 门户以替换现有SharePoint或新式门户。</span><span class="sxs-lookup"><span data-stu-id="81d46-228">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="81d46-229">无论用户导航到旧站点还是新站点，活动波中的用户都将重定向到新站点。</span><span class="sxs-lookup"><span data-stu-id="81d46-229">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="81d46-230">尝试访问新网站的非启动波中的用户将被重定向回旧网站，直到启动其 Wave。</span><span class="sxs-lookup"><span data-stu-id="81d46-230">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="81d46-231">我们仅支持在旧网站上的默认主页和新网站上的默认主页之间进行重定向。</span><span class="sxs-lookup"><span data-stu-id="81d46-231">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="81d46-232">如果管理员或所有者需要访问新旧网站而无需重定向，请确保使用 参数列出 `WaveOverrideUsers` 这些管理员或所有者。</span><span class="sxs-lookup"><span data-stu-id="81d46-232">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="81d46-233">以分步方式SharePoint用户从现有SharePoint网站迁移到新网站：</span><span class="sxs-lookup"><span data-stu-id="81d46-233">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="81d46-234">运行以下命令以指定门户启动波。</span><span class="sxs-lookup"><span data-stu-id="81d46-234">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="81d46-235">示例：</span><span class="sxs-lookup"><span data-stu-id="81d46-235">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="81d46-236">完成验证。</span><span class="sxs-lookup"><span data-stu-id="81d46-236">Complete validation.</span></span> <span data-ttu-id="81d46-237">重定向可能需要 5-10 分钟才能完成整个服务的配置。</span><span class="sxs-lookup"><span data-stu-id="81d46-237">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="81d46-238">重定向到临时页面的步骤</span><span class="sxs-lookup"><span data-stu-id="81d46-238">Steps for redirection to temporary page</span></span>

<span data-ttu-id="81d46-239">当不存在现有门户时，应该使用SharePoint重定向。</span><span class="sxs-lookup"><span data-stu-id="81d46-239">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="81d46-240">用户以一种分步SharePoint定向到新的新式联机门户。</span><span class="sxs-lookup"><span data-stu-id="81d46-240">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="81d46-241">如果用户在尚未启动的波形中，他们将被重定向到包含任何 URL (临时) 。</span><span class="sxs-lookup"><span data-stu-id="81d46-241">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="81d46-242">运行以下命令以指定门户启动波。</span><span class="sxs-lookup"><span data-stu-id="81d46-242">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="81d46-243">示例：</span><span class="sxs-lookup"><span data-stu-id="81d46-243">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="81d46-244">完成验证。</span><span class="sxs-lookup"><span data-stu-id="81d46-244">Complete validation.</span></span> <span data-ttu-id="81d46-245">重定向可能需要 5-10 分钟才能完成整个服务的配置。</span><span class="sxs-lookup"><span data-stu-id="81d46-245">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="81d46-246">暂停或重新启动站点上的门户启动</span><span class="sxs-lookup"><span data-stu-id="81d46-246">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="81d46-247">若要暂停正在启动的门户并暂时阻止即将发生的波形进度，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="81d46-247">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="81d46-248">验证所有用户是否都重定向到旧网站。</span><span class="sxs-lookup"><span data-stu-id="81d46-248">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="81d46-249">若要重新启动已暂停的门户启动，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="81d46-249">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="81d46-250">验证重定向现已还原。</span><span class="sxs-lookup"><span data-stu-id="81d46-250">Validate that the redirection is now restored.</span></span> 

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="81d46-251">删除站点上的门户启动</span><span class="sxs-lookup"><span data-stu-id="81d46-251">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="81d46-252">运行以下命令删除已计划或正在进行某个网站的门户启动。</span><span class="sxs-lookup"><span data-stu-id="81d46-252">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="81d46-253">验证所有用户是否未发生重定向。</span><span class="sxs-lookup"><span data-stu-id="81d46-253">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="81d46-254">了解更多</span><span class="sxs-lookup"><span data-stu-id="81d46-254">Learn more</span></span>

[<span data-ttu-id="81d46-255">在 SharePoint Online 中规划门户启动推出计划</span><span class="sxs-lookup"><span data-stu-id="81d46-255">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="81d46-256">规划通信网站</span><span class="sxs-lookup"><span data-stu-id="81d46-256">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
