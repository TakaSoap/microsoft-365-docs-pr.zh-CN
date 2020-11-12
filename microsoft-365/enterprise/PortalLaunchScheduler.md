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
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999567"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="e40c7-103">使用门户启动计划程序启动门户</span><span class="sxs-lookup"><span data-stu-id="e40c7-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="e40c7-104">您可以使用门户启动计划程序启动门户，方法是首先验证租户管理员为新门户设置波形的能力。</span><span class="sxs-lookup"><span data-stu-id="e40c7-104">You can launch your portal using the Portal Launch Scheduler by first validating the tenant admin's ability to setup a waves for a new portal.</span></span> <span data-ttu-id="e40c7-105">然后，管理员可以根据主动波中的用户是否存在来验证请求的重定向。</span><span class="sxs-lookup"><span data-stu-id="e40c7-105">Then the admin can validate a redirection of requests, based on the existence of a user in the active waves.</span></span>

<span data-ttu-id="e40c7-106">有关启动成功的门户的详细信息，请遵循 [创建、启动和维护正常门户](https://go.microsoft.com/fwlink/?linkid=2105838)中详细介绍的基本原则、实践和建议。</span><span class="sxs-lookup"><span data-stu-id="e40c7-106">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span></span> 

## <a name="app-setup"></a><span data-ttu-id="e40c7-107">应用程序设置</span><span class="sxs-lookup"><span data-stu-id="e40c7-107">App setup</span></span>
1. <span data-ttu-id="e40c7-108">如果已 `Microsoft.Online.SharePoint.PowerShell` 通过控制面板从计算机中删除现有的，请卸载。</span><span class="sxs-lookup"><span data-stu-id="e40c7-108">Uninstall if there an existing `Microsoft.Online.SharePoint.PowerShell` from your machine through the control panel.</span></span>
2. <span data-ttu-id="e40c7-109">在 PowerShell pass 上 `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` 。</span><span class="sxs-lookup"><span data-stu-id="e40c7-109">On PowerShell pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell`.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="e40c7-110">连接到 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e40c7-110">Connect to SharePoint Online</span></span>
1. <span data-ttu-id="e40c7-111">在 Windows 中打开 [SharePoint Online 命令行管理](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 程序。</span><span class="sxs-lookup"><span data-stu-id="e40c7-111">Open the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span></span>
2. <span data-ttu-id="e40c7-112">以管理员身份连接到你的租户。</span><span class="sxs-lookup"><span data-stu-id="e40c7-112">Connect to your tenant as an admin.</span></span>
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  <span data-ttu-id="e40c7-113">在收到提示时提供你的密码。</span><span class="sxs-lookup"><span data-stu-id="e40c7-113">Supply your password when prompted.</span></span>

## <a name="command-to-get-an-existing-setup"></a><span data-ttu-id="e40c7-114">用于获取现有安装程序的命令</span><span class="sxs-lookup"><span data-stu-id="e40c7-114">Command to get an existing setup</span></span>

<span data-ttu-id="e40c7-115">要查看现有的门户启动配置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e40c7-115">To view existing portal launch configurations:</span></span>

1. <span data-ttu-id="e40c7-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` 。</span><span class="sxs-lookup"><span data-stu-id="e40c7-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite`.</span></span>
2. <span data-ttu-id="e40c7-117">`-DisplayFormat Raw`如果想要查看格式化为原始输入格式的波形集合，请传递其他参数。</span><span class="sxs-lookup"><span data-stu-id="e40c7-117">Pass the additional parameter `-DisplayFormat Raw` if you wish to see the wave collection formatted as a raw input format.</span></span>

## <a name="commands-for-bi-directional-redirection"></a><span data-ttu-id="e40c7-118">双向重定向命令</span><span class="sxs-lookup"><span data-stu-id="e40c7-118">Commands for bi-directional redirection</span></span>

<span data-ttu-id="e40c7-119">若要以暂存方式将旧网站用户迁移到新网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e40c7-119">To migrate old site users to the new site in a staged manner:</span></span>

1. <span data-ttu-id="e40c7-120">创建门户启动波形。</span><span class="sxs-lookup"><span data-stu-id="e40c7-120">Create Portal launch waves.</span></span>
   - <span data-ttu-id="e40c7-121">这仅适用于早期版本的测试阶段。</span><span class="sxs-lookup"><span data-stu-id="e40c7-121">This is only applicable in the early release test phase.</span></span>
   - <span data-ttu-id="e40c7-122">若要立即测试更改的影响，请确保第一个波形 `LaunchDateUtc` 设置为当前日期。</span><span class="sxs-lookup"><span data-stu-id="e40c7-122">To test the impact of the change immediately, make sure the first wave `LaunchDateUtc` is set to the current date.</span></span> <span data-ttu-id="e40c7-123">如果不提供此标志，则会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="e40c7-123">If you do not supply this flag, you get an error message.</span></span> <span data-ttu-id="e40c7-124">发生此错误的原因是，在生产中启动的时间必须至少提前7天。</span><span class="sxs-lookup"><span data-stu-id="e40c7-124">This error happens because launches in production must be scheduled at least 7 days in advance.</span></span>

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="e40c7-125">完整验证。</span><span class="sxs-lookup"><span data-stu-id="e40c7-125">Complete validation.</span></span>
  - <span data-ttu-id="e40c7-126">重定向在整个服务中完成其配置最长可能需要5分钟，因此请等待，然后继续。</span><span class="sxs-lookup"><span data-stu-id="e40c7-126">It can take up to 5 minutes for the redirection to complete its configuration across the service, so please wait before continuing.</span></span>
  - <span data-ttu-id="e40c7-127">如果使用指定的用户登录 `WaveOverrideUsers` ，则不会发生任何更改。</span><span class="sxs-lookup"><span data-stu-id="e40c7-127">If you login with the user specified as `WaveOverrideUsers`, then nothing changes.</span></span> <span data-ttu-id="e40c7-128">您应始终在导航到的网站上进行。</span><span class="sxs-lookup"><span data-stu-id="e40c7-128">You should be staying at the site you navigated to.</span></span>
  - <span data-ttu-id="e40c7-129">使用作为 *查看者 SG1* 一部分的用户登录。</span><span class="sxs-lookup"><span data-stu-id="e40c7-129">Login with a user who is part of *Viewers SG1*.</span></span>
    - <span data-ttu-id="e40c7-130">导航到旧网站，您应重定向到新网站。</span><span class="sxs-lookup"><span data-stu-id="e40c7-130">Navigate to the old site and you should be redirected to the new site.</span></span>
    - <span data-ttu-id="e40c7-131">导航到新网站，您应停留在新网站上。</span><span class="sxs-lookup"><span data-stu-id="e40c7-131">Navigate to the new site and you should be stay on the new site.</span></span>
    - <span data-ttu-id="e40c7-132">在 *查看者 SG2* 中使用用户登录并导航到旧网站并停留在旧网站上。</span><span class="sxs-lookup"><span data-stu-id="e40c7-132">Log with user in *Viewers SG2* and navigate to the old site and stay on the old site.</span></span>
    - <span data-ttu-id="e40c7-133">导航到新网站，并将重定向到旧网站。</span><span class="sxs-lookup"><span data-stu-id="e40c7-133">Navigate to the new site and you should be redirected to the old site.</span></span>

3. <span data-ttu-id="e40c7-134">暂停门户启动。</span><span class="sxs-lookup"><span data-stu-id="e40c7-134">Pause Portal launch.</span></span>
  - <span data-ttu-id="e40c7-135">如果需要暂停启动波形，可以将其暂停为 "x" 天。</span><span class="sxs-lookup"><span data-stu-id="e40c7-135">If you need to pause the launch waves, you can pause them for "x" number of days.</span></span> <span data-ttu-id="e40c7-136">将此 `Status` 标志设置为 pause 可阻止所有即将到来的浪潮 progressions。</span><span class="sxs-lookup"><span data-stu-id="e40c7-136">Setting the `Status` flag to pause prevents all upcoming wave progressions.</span></span> 
  - <span data-ttu-id="e40c7-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="e40c7-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="e40c7-138">这将验证是否已将所有用户重定向到旧网站。</span><span class="sxs-lookup"><span data-stu-id="e40c7-138">This validates that all users are redirected to the old site.</span></span>

4. <span data-ttu-id="e40c7-139">重新启动门户启动进展。</span><span class="sxs-lookup"><span data-stu-id="e40c7-139">Restart the portal launch progression.</span></span> 
  - <span data-ttu-id="e40c7-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="e40c7-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="e40c7-141">验证重定向现在是否已还原。</span><span class="sxs-lookup"><span data-stu-id="e40c7-141">Validate that the redirection is now restored.</span></span>

5. <span data-ttu-id="e40c7-142">删除门户启动安装程序。</span><span class="sxs-lookup"><span data-stu-id="e40c7-142">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="e40c7-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="e40c7-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="e40c7-144">验证是否所有用户都不会进行重定向。</span><span class="sxs-lookup"><span data-stu-id="e40c7-144">Validate that no redirection happens for all users.</span></span>

## <a name="commands-for-redirection-to-temporary-page"></a><span data-ttu-id="e40c7-145">用于重定向到临时页的命令</span><span class="sxs-lookup"><span data-stu-id="e40c7-145">Commands for redirection to temporary page</span></span>

<span data-ttu-id="e40c7-146">如果你没有以前的网站，并且要在新门户页上省略不在 wave 中的用户，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="e40c7-146">Follow these steps if you have no previous site and you want to omit users not in the wave from landing on the new portal page.</span></span>

<span data-ttu-id="e40c7-147">若要在任何网站中创建临时页面，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e40c7-147">To create a temporary page in any of the sites:</span></span>

1. <span data-ttu-id="e40c7-148">创建门户启动浪潮。</span><span class="sxs-lookup"><span data-stu-id="e40c7-148">Create a Portal launch Wave.</span></span>
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="e40c7-149">完整验证。</span><span class="sxs-lookup"><span data-stu-id="e40c7-149">Complete validation.</span></span>

  - <span data-ttu-id="e40c7-150">在继续之前，请等待5分钟，因为该操作最长可能需要五分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="e40c7-150">Wait five minutes before continuing, as the action can take up to five minutes to complete.</span></span>
  - <span data-ttu-id="e40c7-151">使用作为 *查看者 SG1* 的一部分的用户记录日志，并：</span><span class="sxs-lookup"><span data-stu-id="e40c7-151">Log with the user who is part of *Viewers SG1* and:</span></span>
     - <span data-ttu-id="e40c7-152">导航到新网站，您应停留在新网站上。</span><span class="sxs-lookup"><span data-stu-id="e40c7-152">Navigate to the new site, and you should be stay on the new site.</span></span>
     - <span data-ttu-id="e40c7-153">导航到 "temp" 页面，您应停留在 "temp" 页面上。</span><span class="sxs-lookup"><span data-stu-id="e40c7-153">Navigate to the temp page, and you should be stay on the temp page.</span></span>
  - <span data-ttu-id="e40c7-154">使用作为 *查看者 SG2* 的一部分的用户记录日志，并：</span><span class="sxs-lookup"><span data-stu-id="e40c7-154">Log with the user who is part of *Viewers SG2* and:</span></span>
     - <span data-ttu-id="e40c7-155">导航到新网站，您应重定向到 "temp" 页面。</span><span class="sxs-lookup"><span data-stu-id="e40c7-155">Navigate to the new site, and you should be redirected to the temp page.</span></span>
     - <span data-ttu-id="e40c7-156">导航到 "temp" 页面，您应停留在 "temp" 页面上。</span><span class="sxs-lookup"><span data-stu-id="e40c7-156">Navigate to the temp page, and you should stay on the temp page.</span></span>

3. <span data-ttu-id="e40c7-157">删除门户启动安装程序。</span><span class="sxs-lookup"><span data-stu-id="e40c7-157">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="e40c7-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="e40c7-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="e40c7-159">验证是否所有用户都不会进行重定向。</span><span class="sxs-lookup"><span data-stu-id="e40c7-159">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="e40c7-160">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="e40c7-160">Learn more</span></span>
[<span data-ttu-id="e40c7-161">在 SharePoint Online 中规划门户启动滚动计划</span><span class="sxs-lookup"><span data-stu-id="e40c7-161">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)