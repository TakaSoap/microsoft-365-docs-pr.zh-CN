---
title: Microsoft 365 Apps for enterprise
description: 如何部署 Microsoft 365 应用版、如何更新它们以及如何管理设置
keywords: 修订记录
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 98995084fb7de9ecb434b70b5d38793a20675f19
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840334"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="50d69-104">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="50d69-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="50d69-105">初始部署</span><span class="sxs-lookup"><span data-stu-id="50d69-105">Initial deployment</span></span>

<span data-ttu-id="50d69-106">Microsoft 托管桌面可确保将 Microsoft 365 企业应用版 (64) 作为映像的一部分安装在所有 [程序设备上](../service-description/device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="50d69-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="50d69-107">以下所有应用程序应在交付时存在于设备上：</span><span class="sxs-lookup"><span data-stu-id="50d69-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="50d69-108">Word</span><span class="sxs-lookup"><span data-stu-id="50d69-108">Word</span></span>
- <span data-ttu-id="50d69-109">Excel</span><span class="sxs-lookup"><span data-stu-id="50d69-109">Excel</span></span>
- <span data-ttu-id="50d69-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="50d69-110">PowerPoint</span></span>
- <span data-ttu-id="50d69-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="50d69-111">Outlook</span></span>
- <span data-ttu-id="50d69-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="50d69-112">Publisher</span></span>
- <span data-ttu-id="50d69-113">Access</span><span class="sxs-lookup"><span data-stu-id="50d69-113">Access</span></span>
- <span data-ttu-id="50d69-114">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="50d69-114">Skype for Business</span></span>
- <span data-ttu-id="50d69-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="50d69-115">OneNote</span></span>

<span data-ttu-id="50d69-116">此方法可最大限度地减少网络影响，并确保用户在收到其设备后可高效工作。</span><span class="sxs-lookup"><span data-stu-id="50d69-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="50d69-117">然后，我们将更多策略部署到托管设备，以设置应用程序以使用。</span><span class="sxs-lookup"><span data-stu-id="50d69-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="50d69-118">Microsoft Teams 独立于 Microsoft 365 企业应用版部署，不会包含在基本映像中。</span><span class="sxs-lookup"><span data-stu-id="50d69-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="50d69-119">可供用户使用的部署</span><span class="sxs-lookup"><span data-stu-id="50d69-119">Available deployment to users</span></span>

<span data-ttu-id="50d69-120">如果用户出于任何原因在其设备上没有 Microsoft 365 应用版，可以使用程序包将设备返回到其预期状态。</span><span class="sxs-lookup"><span data-stu-id="50d69-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="50d69-121">将用户添加到 **新式工作区-Office-Office365_Install** 组，应用将在公司门户中提供给他们。</span><span class="sxs-lookup"><span data-stu-id="50d69-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="50d69-122">Microsoft 365 企业应用版 (32 位) </span><span class="sxs-lookup"><span data-stu-id="50d69-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="50d69-123">Microsoft 托管桌面不支持部署 32 位版本的 M365 企业应用版。</span><span class="sxs-lookup"><span data-stu-id="50d69-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="50d69-124">Microsoft 365 应用版更新</span><span class="sxs-lookup"><span data-stu-id="50d69-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="50d69-125">Microsoft 365 应用版已设置为在每月 [企业频道上更新](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)。</span><span class="sxs-lookup"><span data-stu-id="50d69-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="50d69-126">此做法每月向用户提供新的 Office 功能，但他们将按可预测的发布计划每月仅接收一次更新。</span><span class="sxs-lookup"><span data-stu-id="50d69-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="50d69-127">更新在当月的第二个星期二发布;这些更新可能包括功能、安全性和质量更新。</span><span class="sxs-lookup"><span data-stu-id="50d69-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="50d69-128">这些更新会自动发生，并直接从该特定频道的 Office CDN 提取。</span><span class="sxs-lookup"><span data-stu-id="50d69-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="50d69-129">Microsoft 托管桌面会错开每个版本，以确定环境中的任何潜在问题。</span><span class="sxs-lookup"><span data-stu-id="50d69-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="50d69-130">我们在 Microsoft 365 应用产品组发布后的 28 天内完成推出。</span><span class="sxs-lookup"><span data-stu-id="50d69-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="50d69-131">Microsoft 托管桌面计划向不同的组发布更新，以便有时间来进行验证和测试，如下所示：</span><span class="sxs-lookup"><span data-stu-id="50d69-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="50d69-132">测试：零天</span><span class="sxs-lookup"><span data-stu-id="50d69-132">Test: zero days</span></span>
- <span data-ttu-id="50d69-133">第一个：零天</span><span class="sxs-lookup"><span data-stu-id="50d69-133">First: zero days</span></span>
- <span data-ttu-id="50d69-134">快速：7 天</span><span class="sxs-lookup"><span data-stu-id="50d69-134">Fast: 7 days</span></span>
- <span data-ttu-id="50d69-135">广泛：21 天</span><span class="sxs-lookup"><span data-stu-id="50d69-135">Broad: 21 days</span></span>

<span data-ttu-id="50d69-136">Microsoft 托管桌面为设备设置七 [天的更新](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 截止时间。</span><span class="sxs-lookup"><span data-stu-id="50d69-136">Microsoft Managed Desktop sets a seven-day [update deadline](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="50d69-137">更新可用后，必须在七天内安装更新。</span><span class="sxs-lookup"><span data-stu-id="50d69-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="50d69-138">系统会通知 [用户在](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 几个位置需要更新：应用程序在截止时间前 12 小时在系统托盘中，在截止时间之前收到 15 分钟的警告。</span><span class="sxs-lookup"><span data-stu-id="50d69-138">Users are [notified](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="50d69-139">必须关闭所有 Microsoft 365 应用版才能完成更新。</span><span class="sxs-lookup"><span data-stu-id="50d69-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="50d69-140">暂停或回滚更新</span><span class="sxs-lookup"><span data-stu-id="50d69-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="50d69-141">如果出于任何原因需要暂停或回滚 Microsoft 365 应用更新，请通过[](../working-with-managed-desktop/admin-support.md)Microsoft 托管桌面门户提交管理员支持请求。</span><span class="sxs-lookup"><span data-stu-id="50d69-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="50d69-142">在发布期间，Microsoft 托管桌面将监视所有 Microsoft 365 应用版的错误率。</span><span class="sxs-lookup"><span data-stu-id="50d69-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="50d69-143">如果我们注意到新版本及其前置版本之间的质量显著差异，我们可以通过 Microsoft 托管桌面管理门户联系你。</span><span class="sxs-lookup"><span data-stu-id="50d69-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="50d69-144">根据严重性，我们将询问您是否要暂停发布，或通知你我们已采取措施来缓解问题。</span><span class="sxs-lookup"><span data-stu-id="50d69-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="50d69-145">传递优化</span><span class="sxs-lookup"><span data-stu-id="50d69-145">Delivery optimization</span></span>

<span data-ttu-id="50d69-146">传递优化是 Windows 10 中提供的一种对等分发技术。</span><span class="sxs-lookup"><span data-stu-id="50d69-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="50d69-147">它允许设备共享设备通过 Internet 从 Microsoft 下载的内容（如更新）。</span><span class="sxs-lookup"><span data-stu-id="50d69-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="50d69-148">使用它有助于减少网络带宽，因为设备可以从其本地网络上另一台设备获取部分更新，而不必从 Microsoft 完全下载更新。</span><span class="sxs-lookup"><span data-stu-id="50d69-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="50d69-149">[默认情况下，](https://docs.microsoft.com/deployoffice/delivery-optimization) 在运行 Windows 10 企业版或 Windows 10 教育版的设备上启用传递优化。</span><span class="sxs-lookup"><span data-stu-id="50d69-149">[Delivery Optimization](https://docs.microsoft.com/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="50d69-150">由 Microsoft 托管桌面管理的设置</span><span class="sxs-lookup"><span data-stu-id="50d69-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="50d69-151">Microsoft 将一些设置作为服务的一部分管理。</span><span class="sxs-lookup"><span data-stu-id="50d69-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="50d69-152">Microsoft 托管桌面不会管理 Office 安全基线，但可以按照"管理设置"部分中的 [指导操作，自己设置一](#settings-you-manage) 个基线。</span><span class="sxs-lookup"><span data-stu-id="50d69-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="50d69-153">更新设置</span><span class="sxs-lookup"><span data-stu-id="50d69-153">Update settings</span></span>

<span data-ttu-id="50d69-154">Microsoft 托管桌面 [维护托管设备](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 的所有更新设置，应修改这些设置。</span><span class="sxs-lookup"><span data-stu-id="50d69-154">Microsoft Managed Desktop maintains all [update settings](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="50d69-155">设置自动进行的更新</span><span class="sxs-lookup"><span data-stu-id="50d69-155">Set updates to occur automatically</span></span>

<span data-ttu-id="50d69-156">**默认值：** 已启用</span><span class="sxs-lookup"><span data-stu-id="50d69-156">**Default value**: Enabled</span></span>

<span data-ttu-id="50d69-157">配置此策略是为了确保所有 Office 设备都可以从云中保持最新。</span><span class="sxs-lookup"><span data-stu-id="50d69-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="50d69-158">设置必须应用更新的截止时间</span><span class="sxs-lookup"><span data-stu-id="50d69-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="50d69-159">**默认值：7** 天</span><span class="sxs-lookup"><span data-stu-id="50d69-159">**Default value**: 7 days</span></span>

<span data-ttu-id="50d69-160">**UpdateDeadline** 策略用于配置用户在设备上强制执行更新之前具有的宽限期。</span><span class="sxs-lookup"><span data-stu-id="50d69-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="50d69-161">此截止时间策略还会 [向用户](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 触发通知，以通知他们设备上所需的更改。</span><span class="sxs-lookup"><span data-stu-id="50d69-161">This deadline policy also triggers [notifications](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="50d69-162">将设备的更新延迟一段时间</span><span class="sxs-lookup"><span data-stu-id="50d69-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="50d69-163">此策略针对每个更新管理设备组进行不同的配置，并且 Microsoft 托管桌面必须满足其更新目标：</span><span class="sxs-lookup"><span data-stu-id="50d69-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="50d69-164">测试：零天</span><span class="sxs-lookup"><span data-stu-id="50d69-164">Test: zero days</span></span>
- <span data-ttu-id="50d69-165">第一个：零天</span><span class="sxs-lookup"><span data-stu-id="50d69-165">First: zero days</span></span>
- <span data-ttu-id="50d69-166">快速 7 天</span><span class="sxs-lookup"><span data-stu-id="50d69-166">Fast 7 days</span></span>
- <span data-ttu-id="50d69-167">广泛：21 天</span><span class="sxs-lookup"><span data-stu-id="50d69-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="50d69-168">更新通知设置</span><span class="sxs-lookup"><span data-stu-id="50d69-168">Update notifications settings</span></span>

<span data-ttu-id="50d69-169">**默认值：False**</span><span class="sxs-lookup"><span data-stu-id="50d69-169">**Default value**: False</span></span>

<span data-ttu-id="50d69-170">"隐藏更新通知"设置在 Microsoft 托管桌面设备上设置为 **False，** 以便通过通知用户（如果需要更新）为用户提供 [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)最佳更新体验。</span><span class="sxs-lookup"><span data-stu-id="50d69-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="50d69-171">指定用于查找更新的位置</span><span class="sxs-lookup"><span data-stu-id="50d69-171">Specify a location to look for updates</span></span>

<span data-ttu-id="50d69-172">**默认值：** 每月企业频道</span><span class="sxs-lookup"><span data-stu-id="50d69-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="50d69-173">根据需要使用 **UpdatePath** 和 **UpdateChannel** 策略的组合来实现更新计划。</span><span class="sxs-lookup"><span data-stu-id="50d69-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="50d69-174">设置这些策略可确保所有 Office 设备都直接从 CDN 接收每月企业频道的更新。</span><span class="sxs-lookup"><span data-stu-id="50d69-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="50d69-175">指定 Microsoft 365 应用的目标版本</span><span class="sxs-lookup"><span data-stu-id="50d69-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="50d69-176">Microsoft 托管桌面有时使用目标版本策略来回滚或固定特定版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="50d69-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="50d69-177">隐藏启用或禁用 Office 自动更新的选项</span><span class="sxs-lookup"><span data-stu-id="50d69-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="50d69-178">**默认值：** 已启用</span><span class="sxs-lookup"><span data-stu-id="50d69-178">**Default value**: Enabled</span></span>

<span data-ttu-id="50d69-179">若要使 Microsoft 托管桌面满足其 Microsoft 365 应用程序的更新目标，需要此设置。</span><span class="sxs-lookup"><span data-stu-id="50d69-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="50d69-180">首次运行设置</span><span class="sxs-lookup"><span data-stu-id="50d69-180">First run settings</span></span> 

<span data-ttu-id="50d69-181">第一次运行 Office 时，有几个设置会影响行为。</span><span class="sxs-lookup"><span data-stu-id="50d69-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="50d69-182">代表最终用户接受许可条款</span><span class="sxs-lookup"><span data-stu-id="50d69-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="50d69-183">**默认值：** 已禁用</span><span class="sxs-lookup"><span data-stu-id="50d69-183">**Default value**: Disabled</span></span>

<span data-ttu-id="50d69-184">用户首次打开 Microsoft 365 应用时，系统会提示他们接受许可条款。</span><span class="sxs-lookup"><span data-stu-id="50d69-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="50d69-185">如果要代表用户接受许可条款，请向 Microsoft 托管桌面运营团队提出服务请求，要求启用此设置。</span><span class="sxs-lookup"><span data-stu-id="50d69-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="50d69-186">禁止 Outlook 移动复选框</span><span class="sxs-lookup"><span data-stu-id="50d69-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="50d69-187">**默认值：** 已禁用</span><span class="sxs-lookup"><span data-stu-id="50d69-187">**Default value**: Disabled</span></span>

<span data-ttu-id="50d69-188">用户首次打开 Outlook 时，系统会提示他们安装 Outlook Mobile。</span><span class="sxs-lookup"><span data-stu-id="50d69-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="50d69-189">如果不希望用户看到该复选框，请向 Microsoft 托管桌面运营团队提出服务请求，要求为设备启用此设置。</span><span class="sxs-lookup"><span data-stu-id="50d69-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="50d69-190">其他设置</span><span class="sxs-lookup"><span data-stu-id="50d69-190">Other settings</span></span>

<span data-ttu-id="50d69-191">Microsoft 托管桌面还可以代表你配置其他 Microsoft 365 应用设置。</span><span class="sxs-lookup"><span data-stu-id="50d69-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="50d69-192">禁用个人 OneDrive</span><span class="sxs-lookup"><span data-stu-id="50d69-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="50d69-193">**默认值：** 已禁用</span><span class="sxs-lookup"><span data-stu-id="50d69-193">**Default value**: Disabled</span></span>

<span data-ttu-id="50d69-194">一些组织担心用户有权访问其设备上的公司和个人文件。</span><span class="sxs-lookup"><span data-stu-id="50d69-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="50d69-195">你可以向 Microsoft 托管桌面运营团队提出服务请求，要求启用此设置。</span><span class="sxs-lookup"><span data-stu-id="50d69-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="50d69-196">你管理的设置</span><span class="sxs-lookup"><span data-stu-id="50d69-196">Settings you manage</span></span>

<span data-ttu-id="50d69-197">Microsoft 托管桌面尚未将许多其他策略设置为服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="50d69-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="50d69-198">可以使用使用 Office 云策略服务的 Microsoft Intune 配置 [这些](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) 策略。</span><span class="sxs-lookup"><span data-stu-id="50d69-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="50d69-199">若要设置这些策略，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="50d69-199">To set these policies, follow these steps:</span></span>

1.  <span data-ttu-id="50d69-200">登录到 Microsoft Endpoint Manager 管理中心。</span><span class="sxs-lookup"><span data-stu-id="50d69-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="50d69-201">为 **Office > 选择"应用策略">创建**</span><span class="sxs-lookup"><span data-stu-id="50d69-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="50d69-202">在 **"创建策略配置** "页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="50d69-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="50d69-203">输入名称。</span><span class="sxs-lookup"><span data-stu-id="50d69-203">Enter a name.</span></span>
    - <span data-ttu-id="50d69-204">提供可选 (说明) 。</span><span class="sxs-lookup"><span data-stu-id="50d69-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="50d69-205">在 **工作** 分配中，选择此策略是应用于 Microsoft 365 企业应用版所有用户，还是仅适用于使用 Office 网页版匿名访问文档的用户。</span><span class="sxs-lookup"><span data-stu-id="50d69-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="50d69-206">选择分配给策略配置的基于 AAD 的安全组。</span><span class="sxs-lookup"><span data-stu-id="50d69-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="50d69-207">每个策略配置只能分配给一个组，并且只能为每个组分配一个策略配置。</span><span class="sxs-lookup"><span data-stu-id="50d69-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="50d69-208">配置要包含在策略配置中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="50d69-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="50d69-209">可以搜索策略设置名称以查找要配置的策略设置。</span><span class="sxs-lookup"><span data-stu-id="50d69-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="50d69-210">还可以筛选应用程序、策略是否是建议的安全基线以及策略是否已配置。</span><span class="sxs-lookup"><span data-stu-id="50d69-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="50d69-211">平台列指示策略是应用于 Microsoft 365 企业应用版（适用于 Windows 设备、Office 网页版）还是全部应用。</span><span class="sxs-lookup"><span data-stu-id="50d69-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="50d69-212">做出选择后，选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="50d69-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="50d69-213">Office 配置策略仅支持基于用户的部署</span><span class="sxs-lookup"><span data-stu-id="50d69-213">Office Configuration Policies only support user-based deployment</span></span>
