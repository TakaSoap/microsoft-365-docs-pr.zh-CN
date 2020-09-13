---
title: Microsoft 365 Apps for enterprise
description: 如何部署 Microsoft 365 应用程序、如何更新和管理设置
keywords: 修订记录
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 767489ba9f9ac63bc1a2d8b4999b6634335b1aef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547742"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="d22f4-104">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="d22f4-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="d22f4-105">初始部署</span><span class="sxs-lookup"><span data-stu-id="d22f4-105">Initial deployment</span></span>

<span data-ttu-id="d22f4-106">Microsoft 托管桌面可确保将 Microsoft 365 应用程序的企业 (64 位) 作为映像的一部分安装在所有 [程序设备](../service-description/device-list.md)上。</span><span class="sxs-lookup"><span data-stu-id="d22f4-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="d22f4-107">在设备提供时，设备上应存在以下所有应用程序：</span><span class="sxs-lookup"><span data-stu-id="d22f4-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="d22f4-108">Word</span><span class="sxs-lookup"><span data-stu-id="d22f4-108">Word</span></span>
- <span data-ttu-id="d22f4-109">Excel</span><span class="sxs-lookup"><span data-stu-id="d22f4-109">Excel</span></span>
- <span data-ttu-id="d22f4-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d22f4-110">PowerPoint</span></span>
- <span data-ttu-id="d22f4-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="d22f4-111">Outlook</span></span>
- <span data-ttu-id="d22f4-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="d22f4-112">Publisher</span></span>
- <span data-ttu-id="d22f4-113">Access</span><span class="sxs-lookup"><span data-stu-id="d22f4-113">Access</span></span>
- <span data-ttu-id="d22f4-114">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d22f4-114">Skype for Business</span></span>
- <span data-ttu-id="d22f4-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="d22f4-115">OneNote</span></span>

<span data-ttu-id="d22f4-116">这种方法可最大限度地降低网络影响，并确保用户在收到其设备后能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="d22f4-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="d22f4-117">然后，将其他策略部署到托管设备，以设置要使用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d22f4-117">We then deploy additional policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="d22f4-118">Microsoft 团队是独立于企业的 Microsoft 365 应用程序部署的，并且不包含在基本映像中。</span><span class="sxs-lookup"><span data-stu-id="d22f4-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="d22f4-119">向用户提供的部署</span><span class="sxs-lookup"><span data-stu-id="d22f4-119">Available deployment to users</span></span>

<span data-ttu-id="d22f4-120">如果用户在其设备上没有 Microsoft 365 应用出于任何原因，则可以使用程序包将设备返回到其预期状态。</span><span class="sxs-lookup"><span data-stu-id="d22f4-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="d22f4-121">将用户添加到 **新式工作区-Office Office365_Install** 组，这些应用程序将在公司门户中提供给他们。</span><span class="sxs-lookup"><span data-stu-id="d22f4-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="d22f4-122">适用于企业版的 Microsoft 365 应用 (32 位) </span><span class="sxs-lookup"><span data-stu-id="d22f4-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="d22f4-123">Microsoft 托管桌面不支持部署适用于企业的 M365 应用程序的32位版本。</span><span class="sxs-lookup"><span data-stu-id="d22f4-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="d22f4-124">Microsoft 365 应用程序的更新</span><span class="sxs-lookup"><span data-stu-id="d22f4-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="d22f4-125">Microsoft 365 应用程序设置为 [每月企业频道](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)更新。</span><span class="sxs-lookup"><span data-stu-id="d22f4-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="d22f4-126">这种做法每个月为用户提供了新的 Office 功能，但每月仅以可预测的发布计划收到一次更新。</span><span class="sxs-lookup"><span data-stu-id="d22f4-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="d22f4-127">更新是在每月的第二个星期二发布的;这些更新可以包括功能、安全性和质量更新。</span><span class="sxs-lookup"><span data-stu-id="d22f4-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="d22f4-128">这些更新会自动进行，并将直接从 Office CDN 为该特定通道提取。</span><span class="sxs-lookup"><span data-stu-id="d22f4-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="d22f4-129">Microsoft 托管桌面 staggers 每个版本，以确定您的环境中的任何潜在问题。</span><span class="sxs-lookup"><span data-stu-id="d22f4-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="d22f4-130">我们在发布后28天完成 Microsoft 365 应用产品组中的首次推出。</span><span class="sxs-lookup"><span data-stu-id="d22f4-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="d22f4-131">Microsoft 托管桌面计划将更新发布到不同的组，以允许验证和测试的时间如下：</span><span class="sxs-lookup"><span data-stu-id="d22f4-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="d22f4-132">测试：0天</span><span class="sxs-lookup"><span data-stu-id="d22f4-132">Test: 0 days</span></span>
- <span data-ttu-id="d22f4-133">第一个：0天</span><span class="sxs-lookup"><span data-stu-id="d22f4-133">First: 0 days</span></span>
- <span data-ttu-id="d22f4-134">Fast：7天</span><span class="sxs-lookup"><span data-stu-id="d22f4-134">Fast: 7 days</span></span>
- <span data-ttu-id="d22f4-135">宽：21天</span><span class="sxs-lookup"><span data-stu-id="d22f4-135">Broad: 21 days</span></span>

<span data-ttu-id="d22f4-136">Microsoft 托管桌面为设备设置为期七天的 [更新期限](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 。</span><span class="sxs-lookup"><span data-stu-id="d22f4-136">Microsoft Managed Desktop sets a seven-day [update deadline](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="d22f4-137">更新可用后，必须在七天内安装。</span><span class="sxs-lookup"><span data-stu-id="d22f4-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="d22f4-138">[通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)用户多个位置需要进行更新：应用程序，在最后期限之前的系统托盘12小时内，他们会在最后期限前收到15分钟警告。</span><span class="sxs-lookup"><span data-stu-id="d22f4-138">Users are [notified](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="d22f4-139">必须关闭所有 Microsoft 365 应用才能完成更新。</span><span class="sxs-lookup"><span data-stu-id="d22f4-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="d22f4-140">暂停或回退更新</span><span class="sxs-lookup"><span data-stu-id="d22f4-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="d22f4-141">如果出于任何原因需要暂停或回滚 Microsoft 365 应用程序更新，请通过 Microsoft 托管桌面门户文件获取 [管理员支持请求](../working-with-managed-desktop/admin-support.md) 。</span><span class="sxs-lookup"><span data-stu-id="d22f4-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="d22f4-142">在发布过程中，Microsoft 托管桌面会监视所有 Microsoft 365 应用的错误率。</span><span class="sxs-lookup"><span data-stu-id="d22f4-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="d22f4-143">如果我们注意到新版本与其早期版本之间的质量有显著差异，我们可能会通过 Microsoft 托管桌面管理门户与您联系。</span><span class="sxs-lookup"><span data-stu-id="d22f4-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="d22f4-144">根据严重性，我们将询问您是要暂停发布还是要通知您我们已采取措施来缓解问题。</span><span class="sxs-lookup"><span data-stu-id="d22f4-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="d22f4-145">传递优化</span><span class="sxs-lookup"><span data-stu-id="d22f4-145">Delivery optimization</span></span>

<span data-ttu-id="d22f4-146">传递优化是 Windows 10 中提供的对等分发技术。</span><span class="sxs-lookup"><span data-stu-id="d22f4-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="d22f4-147">它允许设备共享设备已从 Microsoft 下载的来自 internet 的内容（如更新）。</span><span class="sxs-lookup"><span data-stu-id="d22f4-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="d22f4-148">这有助于减少网络带宽，因为设备可以从其本地网络上的其他设备中获取更新的某些部分，而无需完全从 Microsoft 下载更新。</span><span class="sxs-lookup"><span data-stu-id="d22f4-148">This can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="d22f4-149">默认情况下，在运行 Windows 10 企业版或 Windows 10 教育版的设备上启用[传递优化](https://docs.microsoft.com/deployoffice/delivery-optimization)。</span><span class="sxs-lookup"><span data-stu-id="d22f4-149">[Delivery Optimization](https://docs.microsoft.com/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="d22f4-150">Microsoft 托管桌面管理的设置</span><span class="sxs-lookup"><span data-stu-id="d22f4-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="d22f4-151">Microsoft 将某些设置作为服务的一部分进行管理。</span><span class="sxs-lookup"><span data-stu-id="d22f4-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="d22f4-152">Microsoft 托管桌面不会管理 Office 安全基准，但可以按照 " [管理设置](#settings-you-manage) " 部分中的指导进行设置。</span><span class="sxs-lookup"><span data-stu-id="d22f4-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="d22f4-153">更新设置</span><span class="sxs-lookup"><span data-stu-id="d22f4-153">Update settings</span></span>

<span data-ttu-id="d22f4-154">Microsoft 托管桌面维护托管设备的所有 [更新设置](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) ，您应修改这些设置。</span><span class="sxs-lookup"><span data-stu-id="d22f4-154">Microsoft Managed Desktop maintains all [update settings](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="d22f4-155">设置自动进行的更新</span><span class="sxs-lookup"><span data-stu-id="d22f4-155">Set updates to occur automatically</span></span>

<span data-ttu-id="d22f4-156">**默认值**： Enabled</span><span class="sxs-lookup"><span data-stu-id="d22f4-156">**Default value**: Enabled</span></span>

<span data-ttu-id="d22f4-157">配置此策略是为了确保所有 Office 设备都可以从云保持最新。</span><span class="sxs-lookup"><span data-stu-id="d22f4-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="d22f4-158">设置必须应用更新的截止时间</span><span class="sxs-lookup"><span data-stu-id="d22f4-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="d22f4-159">**默认值**：7天</span><span class="sxs-lookup"><span data-stu-id="d22f4-159">**Default value**: 7 days</span></span>

<span data-ttu-id="d22f4-160">**UpdateDeadline**策略用于配置用户在设备上实施更新前的宽限期。</span><span class="sxs-lookup"><span data-stu-id="d22f4-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="d22f4-161">此截止时间策略还会触发 [通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 给用户，以通知其设备上所需的更改。</span><span class="sxs-lookup"><span data-stu-id="d22f4-161">This deadline policy also triggers [notifications](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="d22f4-162">推迟一段时间内设备上的更新</span><span class="sxs-lookup"><span data-stu-id="d22f4-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="d22f4-163">对于每个更新管理设备组，此策略的配置方式各不相同，Microsoft 托管桌面需要此策略来满足更新目标：</span><span class="sxs-lookup"><span data-stu-id="d22f4-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="d22f4-164">测试：0天</span><span class="sxs-lookup"><span data-stu-id="d22f4-164">Test: 0 days</span></span>
- <span data-ttu-id="d22f4-165">第一个：0天</span><span class="sxs-lookup"><span data-stu-id="d22f4-165">First: 0 days</span></span>
- <span data-ttu-id="d22f4-166">7天</span><span class="sxs-lookup"><span data-stu-id="d22f4-166">Fast 7 days</span></span>
- <span data-ttu-id="d22f4-167">宽：21天</span><span class="sxs-lookup"><span data-stu-id="d22f4-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="d22f4-168">更新通知设置</span><span class="sxs-lookup"><span data-stu-id="d22f4-168">Update notifications settings</span></span>

<span data-ttu-id="d22f4-169">**默认值**： False</span><span class="sxs-lookup"><span data-stu-id="d22f4-169">**Default value**: False</span></span>

<span data-ttu-id="d22f4-170">Microsoft 托管桌面设备上的 "隐藏更新通知" 设置为 **False** ，以便在需要更新时向用户提供 [最佳的更新](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 体验。</span><span class="sxs-lookup"><span data-stu-id="d22f4-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="d22f4-171">指定用于查找更新的位置</span><span class="sxs-lookup"><span data-stu-id="d22f4-171">Specify a location to look for updates</span></span>

<span data-ttu-id="d22f4-172">**默认值**：每月企业频道</span><span class="sxs-lookup"><span data-stu-id="d22f4-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="d22f4-173">**UpdatePath**和**UpdateChannel**策略的组合将根据需要使用，以实现更新计划。</span><span class="sxs-lookup"><span data-stu-id="d22f4-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="d22f4-174">设置这些策略可确保所有 Office 设备都直接从 CDN 接收更新，以用于每月企业频道。</span><span class="sxs-lookup"><span data-stu-id="d22f4-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="d22f4-175">指定 Microsoft 365 应用的目标版本</span><span class="sxs-lookup"><span data-stu-id="d22f4-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="d22f4-176">Microsoft 托管桌面有时使用目标版本策略，以便回滚或固定特定版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="d22f4-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="d22f4-177">隐藏用于启用或禁用 Office 自动更新的选项</span><span class="sxs-lookup"><span data-stu-id="d22f4-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="d22f4-178">**默认值**： Enabled</span><span class="sxs-lookup"><span data-stu-id="d22f4-178">**Default value**: Enabled</span></span>

<span data-ttu-id="d22f4-179">Microsoft 托管桌面需要此设置以满足 Microsoft 365 应用程序的更新目标。</span><span class="sxs-lookup"><span data-stu-id="d22f4-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="d22f4-180">首次运行设置</span><span class="sxs-lookup"><span data-stu-id="d22f4-180">First run settings</span></span> 

<span data-ttu-id="d22f4-181">有几种设置会影响首次运行 Office 时的行为。</span><span class="sxs-lookup"><span data-stu-id="d22f4-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="d22f4-182">代表最终用户接受许可条款</span><span class="sxs-lookup"><span data-stu-id="d22f4-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="d22f4-183">**默认值**： Disabled</span><span class="sxs-lookup"><span data-stu-id="d22f4-183">**Default value**: Disabled</span></span>

<span data-ttu-id="d22f4-184">当用户首次打开 Microsoft 365 应用时，系统会提示他们接受许可条款。</span><span class="sxs-lookup"><span data-stu-id="d22f4-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="d22f4-185">如果要代表用户接受许可条款，请向 Microsoft 托管桌面操作团队咨询服务请求，以确保启用此设置。</span><span class="sxs-lookup"><span data-stu-id="d22f4-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="d22f4-186">"取消 Outlook mobile" 复选框</span><span class="sxs-lookup"><span data-stu-id="d22f4-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="d22f4-187">**默认值**： Disabled</span><span class="sxs-lookup"><span data-stu-id="d22f4-187">**Default value**: Disabled</span></span>

<span data-ttu-id="d22f4-188">用户首次打开 Outlook 时，系统会提示安装 Outlook Mobile。</span><span class="sxs-lookup"><span data-stu-id="d22f4-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="d22f4-189">如果您不希望您的用户看到该复选框，请向 Microsoft 托管桌面操作团队提供服务请求，要求为您的设备启用此设置。</span><span class="sxs-lookup"><span data-stu-id="d22f4-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="d22f4-190">其他设置</span><span class="sxs-lookup"><span data-stu-id="d22f4-190">Other settings</span></span>

<span data-ttu-id="d22f4-191">Microsoft 托管桌面可以选择代表你配置其他 Microsoft 365 应用设置。</span><span class="sxs-lookup"><span data-stu-id="d22f4-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="d22f4-192">禁用个人 OneDrive</span><span class="sxs-lookup"><span data-stu-id="d22f4-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="d22f4-193">**默认值**： Disabled</span><span class="sxs-lookup"><span data-stu-id="d22f4-193">**Default value**: Disabled</span></span>

<span data-ttu-id="d22f4-194">有些组织担心用户有权访问其设备上的企业和个人文件。</span><span class="sxs-lookup"><span data-stu-id="d22f4-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="d22f4-195">您可以通过 Microsoft 托管桌面操作团队为服务请求提供请求，以启用此设置。</span><span class="sxs-lookup"><span data-stu-id="d22f4-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="d22f4-196">您管理的设置</span><span class="sxs-lookup"><span data-stu-id="d22f4-196">Settings you manage</span></span>

<span data-ttu-id="d22f4-197">还有许多其他策略，Microsoft 托管桌面尚未将其设置为我们的服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="d22f4-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="d22f4-198">您可以使用 Microsoft Intune （它使用 [Office 云策略](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) 服务）对这些配置进行配置。</span><span class="sxs-lookup"><span data-stu-id="d22f4-198">You can configure these by using Microsoft Intune, which uses the [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="d22f4-199">为此，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d22f4-199">To do this, follow these steps:</span></span>

1.  <span data-ttu-id="d22f4-200">登录到 Microsoft 终结点管理器管理中心。</span><span class="sxs-lookup"><span data-stu-id="d22f4-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="d22f4-201">选择 " **应用程序" > Office 应用程序 > 创建策略**</span><span class="sxs-lookup"><span data-stu-id="d22f4-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="d22f4-202">在 " **创建策略** 配置" 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d22f4-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="d22f4-203">输入名称。</span><span class="sxs-lookup"><span data-stu-id="d22f4-203">Enter a name.</span></span>
    - <span data-ttu-id="d22f4-204">提供 (可选) 的说明。</span><span class="sxs-lookup"><span data-stu-id="d22f4-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="d22f4-205">在 " **分配**" 中，选择此策略是应用于适用于企业的 Microsoft 365 应用程序的所有用户，还是仅适用于使用 web Office 匿名访问文档的用户。</span><span class="sxs-lookup"><span data-stu-id="d22f4-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="d22f4-206">选择分配给策略配置的基于 AAD 的安全组。</span><span class="sxs-lookup"><span data-stu-id="d22f4-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="d22f4-207">每个策略配置仅可分配给一个组，并且每个组只能分配一个策略配置。</span><span class="sxs-lookup"><span data-stu-id="d22f4-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="d22f4-208">将策略设置配置为包含在策略配置中。</span><span class="sxs-lookup"><span data-stu-id="d22f4-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="d22f4-209">您可以搜索策略设置名称以查找要配置的策略设置。</span><span class="sxs-lookup"><span data-stu-id="d22f4-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="d22f4-210">您还可以在应用程序上进行筛选，这取决于策略是否为建议的安全基准，以及策略是否已配置。</span><span class="sxs-lookup"><span data-stu-id="d22f4-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="d22f4-211">"平台" 列指示是否将策略应用于适用于 Windows 的 Microsoft 365 应用程序、Office for web 或全部。</span><span class="sxs-lookup"><span data-stu-id="d22f4-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="d22f4-212">做出选择后，选择 " **创建**"。</span><span class="sxs-lookup"><span data-stu-id="d22f4-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="d22f4-213">Office 配置策略仅支持基于用户的部署</span><span class="sxs-lookup"><span data-stu-id="d22f4-213">Office Configuration Policies only support user-based deployment</span></span>
