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
ms.openlocfilehash: 7e488caba5e4df47bb3f51f195e093891565d95c
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367197"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="033f8-103">使用门户启动计划程序启动门户</span><span class="sxs-lookup"><span data-stu-id="033f8-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="033f8-104">门户是 Intranet 上的一个 SharePoint 网站，其中包含大量使用网站内容的网站查看者。</span><span class="sxs-lookup"><span data-stu-id="033f8-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="033f8-105">以波形的顺序启动门户是确保用户具有访问新 SharePoint Online 门户的流畅且能力丰富的体验的重要部分。</span><span class="sxs-lookup"><span data-stu-id="033f8-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="033f8-106">以波形方式启动是一种用于滚动门户的关键方式，在 [SharePoint Online 中规划门户启动回滚计划中](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)有详细介绍。</span><span class="sxs-lookup"><span data-stu-id="033f8-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> <span data-ttu-id="033f8-107">门户启动计划程序旨在帮助您通过管理新门户的重定向来帮助您遵循波形/分阶段的滚动方法。</span><span class="sxs-lookup"><span data-stu-id="033f8-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="033f8-108">在每个波形过程中，可以在每次部署浪潮期间收集用户反馈并监视性能。</span><span class="sxs-lookup"><span data-stu-id="033f8-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="033f8-109">这样做的优势在于门户的速度缓慢，让您可以选择在继续下一次浪潮之前暂停和解决问题，并最终确保用户获得良好的体验。</span><span class="sxs-lookup"><span data-stu-id="033f8-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="033f8-110">有两种类型的重定向：</span><span class="sxs-lookup"><span data-stu-id="033f8-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="033f8-111">双向：启动新的新式 SharePoint Online 门户以替换现有 SharePoint 经典或新式门户</span><span class="sxs-lookup"><span data-stu-id="033f8-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="033f8-112">临时页面重定向：启动新的新式 SharePoint Online 门户（没有现有 SharePoint 门户）</span><span class="sxs-lookup"><span data-stu-id="033f8-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="033f8-113">门户启动计划程序仅适用于启动新式 SharePoint Online 门户，即通信网站和新式团队网站。</span><span class="sxs-lookup"><span data-stu-id="033f8-113">The portal launch scheduler is only available to launch modern SharePoint Online portals, i.e. communication sites and modern team sites.</span></span> <span data-ttu-id="033f8-114">必须提前安排启动时间至少7天。</span><span class="sxs-lookup"><span data-stu-id="033f8-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="033f8-115">所需的波浪数由预期的用户数决定。</span><span class="sxs-lookup"><span data-stu-id="033f8-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="033f8-116">在计划门户启动之前，必须运行 [SharePoint 工具的页面诊断程序](https://aka.ms/perftool) 以验证门户上的主页是否运行正常。</span><span class="sxs-lookup"><span data-stu-id="033f8-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="033f8-117">在门户启动结束时，具有网站权限的所有用户都将能够访问新网站。</span><span class="sxs-lookup"><span data-stu-id="033f8-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="033f8-118">有关启动成功的门户的详细信息，请遵循 [创建、启动和维护正常门户](https://docs.microsoft.com/sharepoint/portal-health)中详细介绍的基本原则、实践和建议。</span><span class="sxs-lookup"><span data-stu-id="033f8-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](https://docs.microsoft.com/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="033f8-119">此功能不适用于 Office 365 德国、由世纪互联运营的 Office 365 (中国) 或 Microsoft 365 美国政府版计划。</span><span class="sxs-lookup"><span data-stu-id="033f8-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="033f8-120">应用程序设置和连接到 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="033f8-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="033f8-121">[下载最新的SharePoint在线管理壳](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="033f8-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="033f8-p104">如果你已安装早期版本的SharePoint Online Management Shell，请进入添加或删除程序并卸载 "SharePoint Online Management Shell"。</span><span class="sxs-lookup"><span data-stu-id="033f8-p104">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="033f8-123">在 "下载中心" 页面上，选择你的语言，然后单击 "下载" 按钮。</span><span class="sxs-lookup"><span data-stu-id="033f8-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="033f8-124">系统会要求你下载 x64 和 x86 .msi 文件之间做出选择。</span><span class="sxs-lookup"><span data-stu-id="033f8-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="033f8-125">如果你运行的是64位版本的Windows，请下载x64文件，如果你运行的是32位版本，请下载x86文件。</span><span class="sxs-lookup"><span data-stu-id="033f8-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="033f8-126">如果你不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)。</span><span class="sxs-lookup"><span data-stu-id="033f8-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="033f8-127">下载文件后，运行该文件并按照安装向导中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="033f8-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="033f8-128">在Microsoft 365中，以[全局管理员或SharePoint管理员](/sharepoint/sharepoint-admin-role)连接到SharePoint。</span><span class="sxs-lookup"><span data-stu-id="033f8-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="033f8-129">若要了解具体操作步骤，请参阅 [SharePoint 在线管理壳入门](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="033f8-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="033f8-130">查看任何现有的门户启动设置</span><span class="sxs-lookup"><span data-stu-id="033f8-130">View any existing portal launch setups</span></span>

<span data-ttu-id="033f8-131">若要查看是否存在现有门户启动配置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="033f8-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="033f8-132">在网站上安排门户启动</span><span class="sxs-lookup"><span data-stu-id="033f8-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="033f8-133">所需的波浪数取决于所需的启动大小。</span><span class="sxs-lookup"><span data-stu-id="033f8-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="033f8-134">少于10k 用户：1波</span><span class="sxs-lookup"><span data-stu-id="033f8-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="033f8-135">10k 到30k 用户：3波</span><span class="sxs-lookup"><span data-stu-id="033f8-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="033f8-136">30k + 到100k 用户：5波</span><span class="sxs-lookup"><span data-stu-id="033f8-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="033f8-137">超过100k 的用户：5个波，并联系你的 Microsoft 帐户团队</span><span class="sxs-lookup"><span data-stu-id="033f8-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="033f8-138">双向重定向步骤</span><span class="sxs-lookup"><span data-stu-id="033f8-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="033f8-139">双向重定向包括启动新的新式 SharePoint Online 门户以替换现有的 SharePoint 经典或新式门户。</span><span class="sxs-lookup"><span data-stu-id="033f8-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="033f8-140">Active 无线电波中的用户将被重定向到新网站，无论它们是导航到旧网站还是新网站。</span><span class="sxs-lookup"><span data-stu-id="033f8-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="033f8-141">尝试访问新网站的非启动浪潮中的用户将被重定向回旧网站，直到其波形启动。</span><span class="sxs-lookup"><span data-stu-id="033f8-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="033f8-142">仅支持旧网站上的默认主页和新网站上的默认主页之间的重定向。</span><span class="sxs-lookup"><span data-stu-id="033f8-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="033f8-143">如果您有需要访问旧网站和新网站的管理员或所有者而不进行重定向，请确保使用参数列出这些网站 `WaveOverrideUsers` 。</span><span class="sxs-lookup"><span data-stu-id="033f8-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span> <span data-ttu-id="033f8-144">如果您有需要访问旧网站和新网站的管理员或所有者而不进行重定向，请确保使用参数列出这些网站 `WaveOverrideUsers` 。</span><span class="sxs-lookup"><span data-stu-id="033f8-144">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span> <span data-ttu-id="033f8-145">仅支持旧网站上的默认主页和新网站上的默认主页之间的重定向。</span><span class="sxs-lookup"><span data-stu-id="033f8-145">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span>

<span data-ttu-id="033f8-146">若要以暂存方式将用户从现有 SharePoint 网站迁移到新的 SharePoint 网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="033f8-146">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="033f8-147">运行以下命令以指定门户启动波形。</span><span class="sxs-lookup"><span data-stu-id="033f8-147">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="033f8-148">示例：</span><span class="sxs-lookup"><span data-stu-id="033f8-148">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="033f8-149">完整验证。</span><span class="sxs-lookup"><span data-stu-id="033f8-149">Complete validation.</span></span> <span data-ttu-id="033f8-150">重定向可能需要5-10 分钟才能在服务中完成其配置。</span><span class="sxs-lookup"><span data-stu-id="033f8-150">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="033f8-151">重定向到临时页面的步骤</span><span class="sxs-lookup"><span data-stu-id="033f8-151">Steps for redirection to temporary page</span></span>

<span data-ttu-id="033f8-152">如果不存在任何现有 SharePoint 门户，则应使用临时页面重定向。</span><span class="sxs-lookup"><span data-stu-id="033f8-152">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="033f8-153">以暂存方式将用户定向到新新式 SharePoint Online 门户。</span><span class="sxs-lookup"><span data-stu-id="033f8-153">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="033f8-154">如果用户处于尚未启动的浪潮中，则会将它们重定向到 (任何 URL) 的临时页面。</span><span class="sxs-lookup"><span data-stu-id="033f8-154">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="033f8-155">运行以下命令以指定门户启动波形。</span><span class="sxs-lookup"><span data-stu-id="033f8-155">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="033f8-156">示例：</span><span class="sxs-lookup"><span data-stu-id="033f8-156">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="033f8-157">完整验证。</span><span class="sxs-lookup"><span data-stu-id="033f8-157">Complete validation.</span></span> <span data-ttu-id="033f8-158">重定向可能需要5-10 分钟才能在服务中完成其配置。</span><span class="sxs-lookup"><span data-stu-id="033f8-158">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="033f8-159">在网站上暂停或重新启动门户启动</span><span class="sxs-lookup"><span data-stu-id="033f8-159">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="033f8-160">若要暂停正在进行的门户启动，并暂时阻止即将发生的声波 progressions，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="033f8-160">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="033f8-161">验证是否已将所有用户重定向到旧网站。</span><span class="sxs-lookup"><span data-stu-id="033f8-161">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="033f8-162">若要重新启动已暂停的门户启动，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="033f8-162">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="033f8-163">验证重定向现在是否已还原。</span><span class="sxs-lookup"><span data-stu-id="033f8-163">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="033f8-164">在网站上删除门户启动</span><span class="sxs-lookup"><span data-stu-id="033f8-164">Delete a portal launch on the site</span></span>
1. <span data-ttu-id="033f8-165">创建门户启动浪潮。</span><span class="sxs-lookup"><span data-stu-id="033f8-165">Create a Portal launch Wave.</span></span>
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="033f8-166">运行以下命令以删除已计划或正在进行的网站的门户启动。</span><span class="sxs-lookup"><span data-stu-id="033f8-166">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. <span data-ttu-id="033f8-167">验证是否所有用户都不会进行重定向。</span><span class="sxs-lookup"><span data-stu-id="033f8-167">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="033f8-168">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="033f8-168">Learn more</span></span>
[<span data-ttu-id="033f8-169">在 SharePoint Online 中规划门户启动滚动计划</span><span class="sxs-lookup"><span data-stu-id="033f8-169">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
