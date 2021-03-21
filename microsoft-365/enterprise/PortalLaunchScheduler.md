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
description: 本文介绍如何使用门户启动计划程序启动门户
ms.openlocfilehash: e39f00dbc63ae7f1dcaf907d9c67df2c1683efc6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926138"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="e812b-103">使用门户启动计划程序启动门户</span><span class="sxs-lookup"><span data-stu-id="e812b-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="e812b-104">门户是 Intranet 上的一个 SharePoint 网站，其中包含大量使用网站内容的网站查看者。</span><span class="sxs-lookup"><span data-stu-id="e812b-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="e812b-105">分波启动门户是确保用户在访问新 SharePoint Online 门户时获得流畅且性能丰富的体验的重要部分。</span><span class="sxs-lookup"><span data-stu-id="e812b-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="e812b-106">分波启动是推出门户的关键方法，如在 SharePoint Online 中规划门户启动 [推出计划中详述](./planportallaunchroll-out.md?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="e812b-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](./planportallaunchroll-out.md?view=o365-worldwide).</span></span> <span data-ttu-id="e812b-107">门户启动计划程序旨在帮助你通过管理新门户的重定向遵循一波/分阶段推出方法。</span><span class="sxs-lookup"><span data-stu-id="e812b-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="e812b-108">在每个阶段中，可以收集用户反馈，并监视每波部署期间的性能。</span><span class="sxs-lookup"><span data-stu-id="e812b-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="e812b-109">这有一个优势：门户的引入速度较慢，让你可以选择暂停并解决问题，然后再继续下一波，并最终确保为用户提供积极的体验。</span><span class="sxs-lookup"><span data-stu-id="e812b-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="e812b-110">有两种类型的重定向：</span><span class="sxs-lookup"><span data-stu-id="e812b-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="e812b-111">双向：启动新的新式 SharePoint Online 门户以替换现有 SharePoint 经典或新式门户</span><span class="sxs-lookup"><span data-stu-id="e812b-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="e812b-112">临时页面重定向：启动没有现有 SharePoint 门户的新新式 SharePoint Online 门户</span><span class="sxs-lookup"><span data-stu-id="e812b-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="e812b-113">门户启动计划程序仅可用于启动新式 SharePoint Online (，即通信网站) 。</span><span class="sxs-lookup"><span data-stu-id="e812b-113">The portal launch scheduler is only available to launch modern SharePoint Online portals (i.e. communication sites).</span></span> <span data-ttu-id="e812b-114">必须至少提前 7 天安排启动。</span><span class="sxs-lookup"><span data-stu-id="e812b-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="e812b-115">所需的波形数由预期用户数决定。</span><span class="sxs-lookup"><span data-stu-id="e812b-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="e812b-116">在计划门户启动之前，必须运行 [SharePoint](./page-diagnostics-for-spo.md) 页面诊断工具，以验证门户上的主页是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="e812b-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](./page-diagnostics-for-spo.md) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="e812b-117">在门户启动结束时，具有网站权限的所有用户都将能够访问新网站。</span><span class="sxs-lookup"><span data-stu-id="e812b-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="e812b-118">有关启动成功门户的详细信息，请遵循创建、启动和维护正常运行的门户中详述的指导原则 [、实践和建议](/sharepoint/portal-health)。</span><span class="sxs-lookup"><span data-stu-id="e812b-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="e812b-119">此功能不适用于 Office 365 Germany、由世纪银行运营的 Office 365 (中国) 或 Microsoft 365 美国政府版计划。</span><span class="sxs-lookup"><span data-stu-id="e812b-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="e812b-120">应用设置和连接到 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e812b-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="e812b-121">[下载最新的SharePoint在线管理壳](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="e812b-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e812b-p104">如果你已安装早期版本的SharePoint Online Management Shell，请进入添加或删除程序并卸载 "SharePoint Online Management Shell"。</span><span class="sxs-lookup"><span data-stu-id="e812b-p104">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="e812b-123">在 "下载中心" 页面上，选择你的语言，然后单击 "下载" 按钮。</span><span class="sxs-lookup"><span data-stu-id="e812b-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="e812b-124">系统会要求你下载 x64 和 x86 .msi 文件之间做出选择。</span><span class="sxs-lookup"><span data-stu-id="e812b-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="e812b-125">如果你运行的是64位版本的Windows，请下载x64文件，如果你运行的是32位版本，请下载x86文件。</span><span class="sxs-lookup"><span data-stu-id="e812b-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="e812b-126">如果你不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)。</span><span class="sxs-lookup"><span data-stu-id="e812b-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="e812b-127">下载文件后，运行该文件并按照安装向导中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="e812b-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="e812b-128">在Microsoft 365中，以[全局管理员或SharePoint管理员](/sharepoint/sharepoint-admin-role)连接到SharePoint。</span><span class="sxs-lookup"><span data-stu-id="e812b-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="e812b-129">若要了解具体操作步骤，请参阅 [SharePoint 在线管理壳入门](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="e812b-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="e812b-130">查看任何现有的门户启动设置</span><span class="sxs-lookup"><span data-stu-id="e812b-130">View any existing portal launch setups</span></span>

<span data-ttu-id="e812b-131">查看是否有现有的门户启动配置：</span><span class="sxs-lookup"><span data-stu-id="e812b-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="e812b-132">计划站点上的门户启动</span><span class="sxs-lookup"><span data-stu-id="e812b-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="e812b-133">所需的波形数取决于您预期的启动大小。</span><span class="sxs-lookup"><span data-stu-id="e812b-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="e812b-134">少于 10，000 个用户：1 波</span><span class="sxs-lookup"><span data-stu-id="e812b-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="e812b-135">10k 至 30k 用户：3 波</span><span class="sxs-lookup"><span data-stu-id="e812b-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="e812b-136">30k+ 到 100，000 个用户：5 个波形</span><span class="sxs-lookup"><span data-stu-id="e812b-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="e812b-137">超过 100，000 个用户：5 次波形并联系你的 Microsoft 帐户团队</span><span class="sxs-lookup"><span data-stu-id="e812b-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="e812b-138">双向重定向的步骤</span><span class="sxs-lookup"><span data-stu-id="e812b-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="e812b-139">双向重定向涉及启动新的新式 SharePoint Online 门户以替换现有 SharePoint 经典或新式门户。</span><span class="sxs-lookup"><span data-stu-id="e812b-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="e812b-140">无论用户导航到旧站点还是新站点，活动波中的用户都将重定向到新站点。</span><span class="sxs-lookup"><span data-stu-id="e812b-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="e812b-141">尝试访问新网站的非启动波中的用户将被重定向回旧网站，直到启动其 Wave。</span><span class="sxs-lookup"><span data-stu-id="e812b-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="e812b-142">我们仅支持在旧网站上的默认主页和新网站上的默认主页之间进行重定向。</span><span class="sxs-lookup"><span data-stu-id="e812b-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="e812b-143">如果管理员或所有者需要访问新旧网站而无需重定向，请确保使用 参数列出 `WaveOverrideUsers` 这些管理员或所有者。</span><span class="sxs-lookup"><span data-stu-id="e812b-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="e812b-144">以分步方式将用户从现有 SharePoint 网站迁移到新的 SharePoint 网站：</span><span class="sxs-lookup"><span data-stu-id="e812b-144">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="e812b-145">运行以下命令以指定门户启动波。</span><span class="sxs-lookup"><span data-stu-id="e812b-145">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="e812b-146">示例：</span><span class="sxs-lookup"><span data-stu-id="e812b-146">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="e812b-147">完成验证。</span><span class="sxs-lookup"><span data-stu-id="e812b-147">Complete validation.</span></span> <span data-ttu-id="e812b-148">重定向可能需要 5-10 分钟才能完成整个服务的配置。</span><span class="sxs-lookup"><span data-stu-id="e812b-148">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="e812b-149">重定向到临时页面的步骤</span><span class="sxs-lookup"><span data-stu-id="e812b-149">Steps for redirection to temporary page</span></span>

<span data-ttu-id="e812b-150">当不存在现有 SharePoint 门户时，应该使用临时页面重定向。</span><span class="sxs-lookup"><span data-stu-id="e812b-150">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="e812b-151">用户以分步方式定向到新的新式 SharePoint Online 门户。</span><span class="sxs-lookup"><span data-stu-id="e812b-151">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="e812b-152">如果用户在尚未启动的波形中，他们将被重定向到包含任何 URL (临时) 。</span><span class="sxs-lookup"><span data-stu-id="e812b-152">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="e812b-153">运行以下命令以指定门户启动波。</span><span class="sxs-lookup"><span data-stu-id="e812b-153">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="e812b-154">示例：</span><span class="sxs-lookup"><span data-stu-id="e812b-154">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="e812b-155">完成验证。</span><span class="sxs-lookup"><span data-stu-id="e812b-155">Complete validation.</span></span> <span data-ttu-id="e812b-156">重定向可能需要 5-10 分钟才能完成整个服务的配置。</span><span class="sxs-lookup"><span data-stu-id="e812b-156">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="e812b-157">暂停或重新启动站点上的门户启动</span><span class="sxs-lookup"><span data-stu-id="e812b-157">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="e812b-158">若要暂停正在启动的门户并暂时阻止即将发生的波形进度，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e812b-158">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="e812b-159">验证所有用户是否都重定向到旧网站。</span><span class="sxs-lookup"><span data-stu-id="e812b-159">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="e812b-160">若要重新启动已暂停的门户启动，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e812b-160">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="e812b-161">验证重定向现已还原。</span><span class="sxs-lookup"><span data-stu-id="e812b-161">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="e812b-162">删除站点上的门户启动</span><span class="sxs-lookup"><span data-stu-id="e812b-162">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="e812b-163">运行以下命令删除已计划或正在进行某个网站的门户启动。</span><span class="sxs-lookup"><span data-stu-id="e812b-163">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="e812b-164">验证所有用户是否未发生重定向。</span><span class="sxs-lookup"><span data-stu-id="e812b-164">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="e812b-165">了解更多</span><span class="sxs-lookup"><span data-stu-id="e812b-165">Learn more</span></span>
[<span data-ttu-id="e812b-166">在 SharePoint Online 中规划门户启动推出计划</span><span class="sxs-lookup"><span data-stu-id="e812b-166">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)