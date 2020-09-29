---
title: 首次运行体验 with Autopilot 和注册状态页面
description: 如何部署 ESP 体验、使用的设置以及异常
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 84656e2f0ae9d148c61c27af2a53e157cd44c171
ms.sourcegitcommit: e6283e7c32ba9628fc45e9abc5cd4d21fb3f7ca9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "48299235"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a><span data-ttu-id="41b83-104">首次运行体验 with Autopilot 和注册状态页面</span><span class="sxs-lookup"><span data-stu-id="41b83-104">First-run experience with Autopilot and the Enrollment Status Page</span></span>

<span data-ttu-id="41b83-105">Microsoft 托管桌面使用 [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) 和 Microsoft Intune 的 [注册状态页 (ESP) ](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) 为您的用户提供最佳的首次运行体验。</span><span class="sxs-lookup"><span data-stu-id="41b83-105">Microsoft Managed Desktop uses both [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) and Microsoft Intune's [Enrollment Status Page (ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) to provide the best possible first-run experience to your users.</span></span>

<span data-ttu-id="41b83-106">注册状态页面当前处于公共预览版中。</span><span class="sxs-lookup"><span data-stu-id="41b83-106">The Enrollment Status Page is currently in public preview.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="41b83-107">初始部署</span><span class="sxs-lookup"><span data-stu-id="41b83-107">Initial deployment</span></span>

<span data-ttu-id="41b83-108">若要提供 ESP 体验，必须在 Microsoft 托管桌面服务中注册设备。</span><span class="sxs-lookup"><span data-stu-id="41b83-108">To provide the ESP experience, you must register devices in the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="41b83-109">有关注册的详细信息，请参阅 [自行注册新设备](../get-started/register-devices-self.md) 或 [合作伙伴的步骤以注册设备](../get-started/register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="41b83-109">For more about registration, see [Register new devices yourself](../get-started/register-devices-self.md) or [Steps for Partners to register devices](../get-started/register-devices-partner.md).</span></span>

<span data-ttu-id="41b83-110">在将设备注册到服务后，可以通过 [管理门户](https://portal.azure.com/)存档支持票证，从而为 Microsoft 托管桌面设备启用 ESP。</span><span class="sxs-lookup"><span data-stu-id="41b83-110">Once your devices are registered with the service, you can enable ESP for your Microsoft Managed Desktop devices by filing a support ticket through the [Admin Portal](https://portal.azure.com/).</span></span> <span data-ttu-id="41b83-111">在您对票证进行文件存档时，我们将最初将 ESP 配置部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="41b83-111">We will initially deploy the ESP configuration to the Test group when you file the ticket.</span></span> <span data-ttu-id="41b83-112">它将部署到其他后续部署组中，每24个小时 (第一个、更快、更广泛的) 。</span><span class="sxs-lookup"><span data-stu-id="41b83-112">It is deployed to the other subsequent deployment groups (First, Fast, and Broad) each 24 hours.</span></span> <span data-ttu-id="41b83-113">若要暂停部署，请文件另一个票证请求操作保留。</span><span class="sxs-lookup"><span data-stu-id="41b83-113">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="41b83-114">Autopilot 配置文件设置</span><span class="sxs-lookup"><span data-stu-id="41b83-114">Autopilot profile settings</span></span>

<span data-ttu-id="41b83-115">Microsoft 托管桌面在用于您的用户设备的 Autopilot 配置文件中使用这些设置：</span><span class="sxs-lookup"><span data-stu-id="41b83-115">Microsoft Managed Desktop uses these settings in the Autopilot profile used for your users' devices:</span></span>


|<span data-ttu-id="41b83-116">设置</span><span class="sxs-lookup"><span data-stu-id="41b83-116">Setting</span></span>  |<span data-ttu-id="41b83-117">值</span><span class="sxs-lookup"><span data-stu-id="41b83-117">Value</span></span>  |
|---------|---------|
|<span data-ttu-id="41b83-118">部署模式</span><span class="sxs-lookup"><span data-stu-id="41b83-118">Deployment mode</span></span> |  <span data-ttu-id="41b83-119">用户驱动</span><span class="sxs-lookup"><span data-stu-id="41b83-119">User Driven</span></span>       |
|<span data-ttu-id="41b83-120">加入 Azure AD as</span><span class="sxs-lookup"><span data-stu-id="41b83-120">Join to Azure AD as</span></span>     |  <span data-ttu-id="41b83-121">Azure AD 已加入</span><span class="sxs-lookup"><span data-stu-id="41b83-121">Azure AD joined</span></span>       |
|<span data-ttu-id="41b83-122">语言 (区域) </span><span class="sxs-lookup"><span data-stu-id="41b83-122">Language (Region)</span></span>     | <span data-ttu-id="41b83-123">操作系统默认值</span><span class="sxs-lookup"><span data-stu-id="41b83-123">Operating system default</span></span>        |
|<span data-ttu-id="41b83-124">自动配置键盘</span><span class="sxs-lookup"><span data-stu-id="41b83-124">Automatically configure keyboard</span></span>     | <span data-ttu-id="41b83-125">否</span><span class="sxs-lookup"><span data-stu-id="41b83-125">No</span></span>        |
|<span data-ttu-id="41b83-126">Microsoft 软件许可条款</span><span class="sxs-lookup"><span data-stu-id="41b83-126">Microsoft Software License Terms</span></span>     |  <span data-ttu-id="41b83-127">隐藏</span><span class="sxs-lookup"><span data-stu-id="41b83-127">Hide</span></span>       |
|<span data-ttu-id="41b83-128">隐私设置</span><span class="sxs-lookup"><span data-stu-id="41b83-128">Privacy settings</span></span>     | <span data-ttu-id="41b83-129">隐藏</span><span class="sxs-lookup"><span data-stu-id="41b83-129">Hide</span></span>        |
|<span data-ttu-id="41b83-130">隐藏更改帐户选项</span><span class="sxs-lookup"><span data-stu-id="41b83-130">Hide change account options</span></span>     | <span data-ttu-id="41b83-131">Show</span><span class="sxs-lookup"><span data-stu-id="41b83-131">Show</span></span>        |
|<span data-ttu-id="41b83-132">用户帐户类型</span><span class="sxs-lookup"><span data-stu-id="41b83-132">User account type</span></span>     |  <span data-ttu-id="41b83-133">标准</span><span class="sxs-lookup"><span data-stu-id="41b83-133">Standard</span></span>       |
|<span data-ttu-id="41b83-134">允许将白色 Glove OOBE</span><span class="sxs-lookup"><span data-stu-id="41b83-134">Allow White Glove OOBE</span></span>     |  <span data-ttu-id="41b83-135">是</span><span class="sxs-lookup"><span data-stu-id="41b83-135">Yes</span></span>       |
|<span data-ttu-id="41b83-136">应用设备名称模板</span><span class="sxs-lookup"><span data-stu-id="41b83-136">Apply device name template</span></span>     | <span data-ttu-id="41b83-137">是</span><span class="sxs-lookup"><span data-stu-id="41b83-137">Yes</span></span>        |
|<span data-ttu-id="41b83-138">输入名称</span><span class="sxs-lookup"><span data-stu-id="41b83-138">Enter a name</span></span>     | <span data-ttu-id="41b83-139">MMD-% RAND：11%</span><span class="sxs-lookup"><span data-stu-id="41b83-139">MMD-%RAND:11%</span></span>        |

> [!NOTE]
> <span data-ttu-id="41b83-140">仅对启用了 ESP 的客户启用 "白色 glove" rovisioning，Microsoft 托管桌面目前不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="41b83-140">While "white glove" rovisioning is only enabled for customers with ESP turned on, it is not currently supported in Microsoft Managed Desktop.</span></span>

## <a name="enrollment-status-page-settings"></a><span data-ttu-id="41b83-141">注册状态页面设置</span><span class="sxs-lookup"><span data-stu-id="41b83-141">Enrollment Status Page settings</span></span>

<span data-ttu-id="41b83-142">Microsoft 托管桌面在注册状态页面体验中使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="41b83-142">Microsoft Managed Desktop uses these settings for the Enrollment Status Page experience:</span></span>


|<span data-ttu-id="41b83-143">设置</span><span class="sxs-lookup"><span data-stu-id="41b83-143">Setting</span></span>  |<span data-ttu-id="41b83-144">值</span><span class="sxs-lookup"><span data-stu-id="41b83-144">Value</span></span>  |
|---------|---------|
|<span data-ttu-id="41b83-145">显示应用和配置文件配置进度</span><span class="sxs-lookup"><span data-stu-id="41b83-145">Show app and profile configuration progress</span></span>     | <span data-ttu-id="41b83-146">是</span><span class="sxs-lookup"><span data-stu-id="41b83-146">Yes</span></span>        |
|<span data-ttu-id="41b83-147">当安装时间超过指定的分钟数时显示一个错误</span><span class="sxs-lookup"><span data-stu-id="41b83-147">Show an error when installation takes longer than specified number of minutes</span></span>     |  <span data-ttu-id="41b83-148">60</span><span class="sxs-lookup"><span data-stu-id="41b83-148">60</span></span>       |
|<span data-ttu-id="41b83-149">出现时间限制错误时显示自定义消息</span><span class="sxs-lookup"><span data-stu-id="41b83-149">Show custom message when time limit error occurs</span></span>     |  <span data-ttu-id="41b83-150">是</span><span class="sxs-lookup"><span data-stu-id="41b83-150">Yes</span></span>       |
|<span data-ttu-id="41b83-151">错误消息</span><span class="sxs-lookup"><span data-stu-id="41b83-151">Error message</span></span>     | <span data-ttu-id="41b83-152">是的，设置你的设备所花时间比预期时间稍长。</span><span class="sxs-lookup"><span data-stu-id="41b83-152">Yes, It's taking a little longer to set up your device than expected.</span></span> <span data-ttu-id="41b83-153">单击下方以开始操作，我们将在后台完成设置</span><span class="sxs-lookup"><span data-stu-id="41b83-153">Click below to get started and we'll finish setting up in the background</span></span>        |
|<span data-ttu-id="41b83-154">允许用户收集有关安装错误的日志</span><span class="sxs-lookup"><span data-stu-id="41b83-154">Allow users to collect logs about installation errors</span></span>     |  <span data-ttu-id="41b83-155">是</span><span class="sxs-lookup"><span data-stu-id="41b83-155">Yes</span></span>       |
|<span data-ttu-id="41b83-156">仅向设备显示由 (OOBE 的现成体验设置的页面) </span><span class="sxs-lookup"><span data-stu-id="41b83-156">Only show page to devices provisioned by out-of-box experience (OOBE)</span></span>     | <span data-ttu-id="41b83-157">是</span><span class="sxs-lookup"><span data-stu-id="41b83-157">Yes</span></span>        |
|<span data-ttu-id="41b83-158">在安装所有应用和配置文件之前阻止设备使用</span><span class="sxs-lookup"><span data-stu-id="41b83-158">Block device use until all apps and profiles are installed</span></span>     |  <span data-ttu-id="41b83-159">是</span><span class="sxs-lookup"><span data-stu-id="41b83-159">Yes</span></span>       |
|<span data-ttu-id="41b83-160">如果出现安装错误，则允许用户重置设备</span><span class="sxs-lookup"><span data-stu-id="41b83-160">Allow users to reset device if installation error occurs</span></span>     |  <span data-ttu-id="41b83-161">是</span><span class="sxs-lookup"><span data-stu-id="41b83-161">Yes</span></span>       |
|<span data-ttu-id="41b83-162">允许用户在发生安装错误时使用设备</span><span class="sxs-lookup"><span data-stu-id="41b83-162">Allow users to use device if installation error occurs</span></span>     |  <span data-ttu-id="41b83-163">是</span><span class="sxs-lookup"><span data-stu-id="41b83-163">Yes</span></span>       |
|<span data-ttu-id="41b83-164">如果这些必需的应用程序已分配给用户/设备，则阻止设备使用</span><span class="sxs-lookup"><span data-stu-id="41b83-164">Block device use until these required apps are installed if they are assigned to the user/device</span></span>     |  <span data-ttu-id="41b83-165">新式工作区-时间更正</span><span class="sxs-lookup"><span data-stu-id="41b83-165">Modern Workplace - Time Correction</span></span>       |



<span data-ttu-id="41b83-166">注册状态页面体验分三个阶段发生。</span><span class="sxs-lookup"><span data-stu-id="41b83-166">The Enrollment Status Page experience occurs in three phases.</span></span> <span data-ttu-id="41b83-167">有关详细信息，请参阅 [注册状态页面跟踪信息](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)。</span><span class="sxs-lookup"><span data-stu-id="41b83-167">For more, see [Enrollment Status Page tracking information](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).</span></span>

<span data-ttu-id="41b83-168">经验如下所示：</span><span class="sxs-lookup"><span data-stu-id="41b83-168">The experience proceeds as follows:</span></span>

1. <span data-ttu-id="41b83-169">Autopilot 体验启动，用户输入他们的凭据。</span><span class="sxs-lookup"><span data-stu-id="41b83-169">The Autopilot experience starts and the user enters their credentials.</span></span>
2. <span data-ttu-id="41b83-170">设备将打开 "注册状态" 页，并继续完成 "设备准备" 和 "设备设置" 阶段。</span><span class="sxs-lookup"><span data-stu-id="41b83-170">The device opens the Enrollment Status Page and proceeds through Device Preparation and Device Setup phases.</span></span> <span data-ttu-id="41b83-171">由于禁用了用户 ESP，因此第三步 (帐户安装) 当前在 Microsoft 托管桌面配置中被 *跳过* 。</span><span class="sxs-lookup"><span data-stu-id="41b83-171">The third step (Account Setup) is *currently skipped* in the Microsoft Managed Desktop configuration because User ESP is disabled.</span></span> <span data-ttu-id="41b83-172">设备将重新启动。</span><span class="sxs-lookup"><span data-stu-id="41b83-172">The device restarts.</span></span>
3. <span data-ttu-id="41b83-173">重新启动后，设备将使用 **其他用户**打开 Windows 登录页。</span><span class="sxs-lookup"><span data-stu-id="41b83-173">After restart, the device opens the Windows sign-in page with **Other user**.</span></span>
4. <span data-ttu-id="41b83-174">用户再次输入其凭据，并打开桌面。</span><span class="sxs-lookup"><span data-stu-id="41b83-174">The users enter their credentials again and the desktop opens.</span></span>

> [!NOTE]
> <span data-ttu-id="41b83-175">如果 Windows 10 版本是1903或更高版本，则仅在 ESP 期间部署 Win32 应用程序。</span><span class="sxs-lookup"><span data-stu-id="41b83-175">Win32 apps are only deployed during ESP if the Windows 10 version is 1903 or later.</span></span>

![Autopilot 安装程序的起始页，显示 "设备准备" 和 "设备安装" 阶段。](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a><span data-ttu-id="41b83-177">白色 glove 设置</span><span class="sxs-lookup"><span data-stu-id="41b83-177">White glove provisioning</span></span>

<span data-ttu-id="41b83-178">Microsoft 托管桌面目前不支持 Windows Autopilot 的 "白色 glove" 功能。</span><span class="sxs-lookup"><span data-stu-id="41b83-178">Microsoft Managed Desktop doesn't currently support the "white glove" feature of Windows Autopilot.</span></span>

## <a name="exceptions"></a><span data-ttu-id="41b83-179">Exceptions</span><span class="sxs-lookup"><span data-stu-id="41b83-179">Exceptions</span></span>

<span data-ttu-id="41b83-180">如果 Microsoft 托管桌面使用的安装程序不能完全满足您的需求，则可以为异常请求文件。</span><span class="sxs-lookup"><span data-stu-id="41b83-180">If the setup used by Microsoft Managed Desktop doesn't exactly match your needs, you can file a request for an exception.</span></span> <span data-ttu-id="41b83-181">若要执行此操作，请参阅 [请求异常](../service-description/customizing.md#request-an-exception)中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="41b83-181">To do this, see details in [Request an exception](../service-description/customizing.md#request-an-exception).</span></span> <span data-ttu-id="41b83-182">下面是可能需要的异常类型的一些示例：</span><span class="sxs-lookup"><span data-stu-id="41b83-182">Here are some examples of the types of exceptions you might need:</span></span>

### <a name="autopilot-exception"></a><span data-ttu-id="41b83-183">Autopilot 异常</span><span class="sxs-lookup"><span data-stu-id="41b83-183">Autopilot exception</span></span>

<span data-ttu-id="41b83-184">您可能需要请求一个不同的设备名称模板。</span><span class="sxs-lookup"><span data-stu-id="41b83-184">You might want to request a different device name template.</span></span> <span data-ttu-id="41b83-185">但是，您不能更改部署模式，将 "加入 Azure" 设置为 "隐私设置" 或 "用户帐户类型"。</span><span class="sxs-lookup"><span data-stu-id="41b83-185">You cannot, however, change Deployment Mode, Join to Azure As, Privacy Settings, or User Account Type.</span></span>

### <a name="enrollment-status-page-exception"></a><span data-ttu-id="41b83-186">注册状态页例外</span><span class="sxs-lookup"><span data-stu-id="41b83-186">Enrollment Status Page exception</span></span>

- <span data-ttu-id="41b83-187">"当安装时间超过指定的分钟数时显示错误" 设置的较长分钟数。</span><span class="sxs-lookup"><span data-stu-id="41b83-187">A longer number of minutes for the "Show an error when installation takes longer than specified number of minutes" setting.</span></span>
- <span data-ttu-id="41b83-188">显示的错误消息</span><span class="sxs-lookup"><span data-stu-id="41b83-188">The error message displayed</span></span>
- <span data-ttu-id="41b83-189">在 "阻止设备使用" 中添加或删除应用程序，直到这些必需的应用程序已被分配给用户/设备 "设置。</span><span class="sxs-lookup"><span data-stu-id="41b83-189">Adding or removing applications in the "Block device use until these required apps are installed if they are assigned to the user/device" setting.</span></span>

## <a name="required-applications"></a><span data-ttu-id="41b83-190">必需的应用程序</span><span class="sxs-lookup"><span data-stu-id="41b83-190">Required applications</span></span>

- <span data-ttu-id="41b83-191">您必须将应用程序定位在新式的工作区 *设备组* 测试、第一次、快速和广泛的应用中。</span><span class="sxs-lookup"><span data-stu-id="41b83-191">You must target applications in the Modern Workplace *device groups* Test, First, Fast, and Broad.</span></span> <span data-ttu-id="41b83-192">应用程序必须安装在 "系统" 上下文中。</span><span class="sxs-lookup"><span data-stu-id="41b83-192">Applications must install in the "System" context.</span></span> <span data-ttu-id="41b83-193">在将测试组中的 ESP 分配给所有组之前，请务必先完成对该测试组中的 ESP 的测试。</span><span class="sxs-lookup"><span data-stu-id="41b83-193">Make sure to complete testing with ESP in the Test group before you assign them to all groups.</span></span>
- <span data-ttu-id="41b83-194">任何应用程序都不需要重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="41b83-194">No applications should require the device to restart.</span></span> <span data-ttu-id="41b83-195">建议在生成应用程序包时，将应用程序设置为 "无任何操作"，如果它们需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="41b83-195">We recommend that applications be set to "Do nothing" when you build the application package if they will require a restart.</span></span>
- <span data-ttu-id="41b83-196">仅在用户登录设备时所需的核心应用程序中限制所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="41b83-196">Limit required applications to only the core applications that a user needs immediately when they sign in to the device.</span></span>
- <span data-ttu-id="41b83-197">将所有应用程序的总大小保持在 1 GB 之下，以避免在应用程序安装阶段超时。</span><span class="sxs-lookup"><span data-stu-id="41b83-197">Keep the total size of all applications collectively under 1 GB to avoid timeouts during the application installation phase.</span></span>
- <span data-ttu-id="41b83-198">理想情况下，应用程序不应具有任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="41b83-198">Ideally, apps should not have any dependencies.</span></span> <span data-ttu-id="41b83-199">如果您有 *必须* 具有依赖项的应用程序，请务必在 ESP 评估中对其进行配置、测试和验证。</span><span class="sxs-lookup"><span data-stu-id="41b83-199">If you have apps that *must* have dependencies, be sure you configure, test, and validate them as part of your ESP evaluation.</span></span>
- <span data-ttu-id="41b83-200">没有需要 "用户" 上下文的应用程序 (例如，团队) 可以包含在 ESP 的公共预览版中。</span><span class="sxs-lookup"><span data-stu-id="41b83-200">No applications that require the "user" context (for example, Teams) can be included in the public preview of ESP.</span></span>
