---
title: 使用 Autopilot 和注册状态页的首次运行体验
description: 如何部署 ESP 体验、使用的设置和配置更改
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ec3758a2c452b5b20deab3b3776d631ebd48eaef
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921938"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a><span data-ttu-id="eac34-104">使用 Autopilot 和注册状态页的首次运行体验</span><span class="sxs-lookup"><span data-stu-id="eac34-104">First-run experience with Autopilot and the Enrollment Status Page</span></span>

<span data-ttu-id="eac34-105">Microsoft 托管桌面使用 [Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot) 和 Microsoft Intune 的注册状态页 [ (ESP) ](/windows/deployment/windows-autopilot/enrollment-status) 为用户提供可能的最佳首次运行体验。</span><span class="sxs-lookup"><span data-stu-id="eac34-105">Microsoft Managed Desktop uses both [Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot) and Microsoft Intune's [Enrollment Status Page (ESP)](/windows/deployment/windows-autopilot/enrollment-status) to provide the best possible first-run experience to your users.</span></span>

<span data-ttu-id="eac34-106">"注册状态"页当前处于公共预览状态。</span><span class="sxs-lookup"><span data-stu-id="eac34-106">The Enrollment Status Page is currently in public preview.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="eac34-107">初始部署</span><span class="sxs-lookup"><span data-stu-id="eac34-107">Initial deployment</span></span>

<span data-ttu-id="eac34-108">若要提供 ESP 体验，必须在 Microsoft 托管桌面服务中注册设备。</span><span class="sxs-lookup"><span data-stu-id="eac34-108">To provide the ESP experience, you must register devices in the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="eac34-109">有关注册的信息，请参阅自己 [注册新设备](../get-started/register-devices-self.md) 或合作伙伴 [注册设备的步骤](../get-started/register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="eac34-109">For more about registration, see [Register new devices yourself](../get-started/register-devices-self.md) or [Steps for Partners to register devices](../get-started/register-devices-partner.md).</span></span>

<span data-ttu-id="eac34-110">向服务注册设备后，可以通过管理门户提交支持票证来为 Microsoft 托管桌面设备 [启用](https://portal.azure.com/)ESP。</span><span class="sxs-lookup"><span data-stu-id="eac34-110">Once your devices are registered with the service, you can enable ESP for your Microsoft Managed Desktop devices by filing a support ticket through the [Admin Portal](https://portal.azure.com/).</span></span> <span data-ttu-id="eac34-111">提交票证时，我们将首先将 ESP 配置部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="eac34-111">We will initially deploy the ESP configuration to the Test group when you file the ticket.</span></span> <span data-ttu-id="eac34-112">它每 24 小时部署到其他后续部署 (、快速和广泛) 部署组。</span><span class="sxs-lookup"><span data-stu-id="eac34-112">It is deployed to the other subsequent deployment groups (First, Fast, and Broad) each 24 hours.</span></span> <span data-ttu-id="eac34-113">若要暂停部署，请提出另一个请求操作保留的票证。</span><span class="sxs-lookup"><span data-stu-id="eac34-113">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="eac34-114">Autopilot 配置文件设置</span><span class="sxs-lookup"><span data-stu-id="eac34-114">Autopilot profile settings</span></span>

<span data-ttu-id="eac34-115">Microsoft 托管桌面在用于用户设备的 Autopilot 配置文件中使用这些设置：</span><span class="sxs-lookup"><span data-stu-id="eac34-115">Microsoft Managed Desktop uses these settings in the Autopilot profile used for your users' devices:</span></span>


|<span data-ttu-id="eac34-116">设置</span><span class="sxs-lookup"><span data-stu-id="eac34-116">Setting</span></span>  |<span data-ttu-id="eac34-117">值</span><span class="sxs-lookup"><span data-stu-id="eac34-117">Value</span></span>  |
|---------|---------|
|<span data-ttu-id="eac34-118">部署模式</span><span class="sxs-lookup"><span data-stu-id="eac34-118">Deployment mode</span></span> |  <span data-ttu-id="eac34-119">用户驱动</span><span class="sxs-lookup"><span data-stu-id="eac34-119">User Driven</span></span>       |
|<span data-ttu-id="eac34-120">作为 加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="eac34-120">Join to Azure AD as</span></span>     |  <span data-ttu-id="eac34-121">已加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="eac34-121">Azure AD joined</span></span>       |
|<span data-ttu-id="eac34-122">语言 (区域) </span><span class="sxs-lookup"><span data-stu-id="eac34-122">Language (Region)</span></span>     | <span data-ttu-id="eac34-123">用户选择</span><span class="sxs-lookup"><span data-stu-id="eac34-123">User Select</span></span>        |
|<span data-ttu-id="eac34-124">自动配置键盘</span><span class="sxs-lookup"><span data-stu-id="eac34-124">Automatically configure keyboard</span></span>     | <span data-ttu-id="eac34-125">否</span><span class="sxs-lookup"><span data-stu-id="eac34-125">No</span></span>        |
|<span data-ttu-id="eac34-126">Microsoft 软件许可条款</span><span class="sxs-lookup"><span data-stu-id="eac34-126">Microsoft Software License Terms</span></span>     |  <span data-ttu-id="eac34-127">隐藏</span><span class="sxs-lookup"><span data-stu-id="eac34-127">Hide</span></span>       |
|<span data-ttu-id="eac34-128">隐私设置</span><span class="sxs-lookup"><span data-stu-id="eac34-128">Privacy settings</span></span>     | <span data-ttu-id="eac34-129">隐藏</span><span class="sxs-lookup"><span data-stu-id="eac34-129">Hide</span></span>        |
|<span data-ttu-id="eac34-130">隐藏更改帐户选项</span><span class="sxs-lookup"><span data-stu-id="eac34-130">Hide change account options</span></span>     | <span data-ttu-id="eac34-131">Show</span><span class="sxs-lookup"><span data-stu-id="eac34-131">Show</span></span>        |
|<span data-ttu-id="eac34-132">用户帐户类型</span><span class="sxs-lookup"><span data-stu-id="eac34-132">User account type</span></span>     |  <span data-ttu-id="eac34-133">标准</span><span class="sxs-lookup"><span data-stu-id="eac34-133">Standard</span></span>       |
|<span data-ttu-id="eac34-134">允许白手套 OOBE</span><span class="sxs-lookup"><span data-stu-id="eac34-134">Allow White Glove OOBE</span></span>     |  <span data-ttu-id="eac34-135">是</span><span class="sxs-lookup"><span data-stu-id="eac34-135">Yes</span></span>       |
|<span data-ttu-id="eac34-136">应用设备名称模板</span><span class="sxs-lookup"><span data-stu-id="eac34-136">Apply device name template</span></span>     | <span data-ttu-id="eac34-137">是</span><span class="sxs-lookup"><span data-stu-id="eac34-137">Yes</span></span>        |
|<span data-ttu-id="eac34-138">输入名称</span><span class="sxs-lookup"><span data-stu-id="eac34-138">Enter a name</span></span>     | <span data-ttu-id="eac34-139">MMD-%RAND：11%</span><span class="sxs-lookup"><span data-stu-id="eac34-139">MMD-%RAND:11%</span></span>        |

## <a name="enrollment-status-page-settings"></a><span data-ttu-id="eac34-140">注册状态页面设置</span><span class="sxs-lookup"><span data-stu-id="eac34-140">Enrollment Status Page settings</span></span>

<span data-ttu-id="eac34-141">Microsoft 托管桌面将这些设置用于注册状态页面体验：</span><span class="sxs-lookup"><span data-stu-id="eac34-141">Microsoft Managed Desktop uses these settings for the Enrollment Status Page experience:</span></span>


|<span data-ttu-id="eac34-142">设置</span><span class="sxs-lookup"><span data-stu-id="eac34-142">Setting</span></span>  |<span data-ttu-id="eac34-143">值</span><span class="sxs-lookup"><span data-stu-id="eac34-143">Value</span></span>  |
|---------|---------|
|<span data-ttu-id="eac34-144">显示应用和配置文件配置进度</span><span class="sxs-lookup"><span data-stu-id="eac34-144">Show app and profile configuration progress</span></span>     | <span data-ttu-id="eac34-145">是</span><span class="sxs-lookup"><span data-stu-id="eac34-145">Yes</span></span>        |
|<span data-ttu-id="eac34-146">当安装时间超过指定分钟数时显示错误</span><span class="sxs-lookup"><span data-stu-id="eac34-146">Show an error when installation takes longer than specified number of minutes</span></span>     |  <span data-ttu-id="eac34-147">60</span><span class="sxs-lookup"><span data-stu-id="eac34-147">60</span></span>       |
|<span data-ttu-id="eac34-148">在出现时间限制错误时显示自定义消息</span><span class="sxs-lookup"><span data-stu-id="eac34-148">Show custom message when time limit error occurs</span></span>     |  <span data-ttu-id="eac34-149">是</span><span class="sxs-lookup"><span data-stu-id="eac34-149">Yes</span></span>       |
|<span data-ttu-id="eac34-150">错误消息</span><span class="sxs-lookup"><span data-stu-id="eac34-150">Error message</span></span>     | <span data-ttu-id="eac34-151">是的，设置设备的时间比预期的要长一些。</span><span class="sxs-lookup"><span data-stu-id="eac34-151">Yes, It's taking a little longer to set up your device than expected.</span></span> <span data-ttu-id="eac34-152">单击下方开始，我们将在后台完成设置</span><span class="sxs-lookup"><span data-stu-id="eac34-152">Click below to get started and we'll finish setting up in the background</span></span>        |
|<span data-ttu-id="eac34-153">允许用户收集有关安装错误的日志</span><span class="sxs-lookup"><span data-stu-id="eac34-153">Allow users to collect logs about installation errors</span></span>     |  <span data-ttu-id="eac34-154">是</span><span class="sxs-lookup"><span data-stu-id="eac34-154">Yes</span></span>       |
|<span data-ttu-id="eac34-155">仅在 OOBE 设备上通过开箱使用体验预配 (页面) </span><span class="sxs-lookup"><span data-stu-id="eac34-155">Only show page to devices provisioned by out-of-box experience (OOBE)</span></span>     | <span data-ttu-id="eac34-156">是</span><span class="sxs-lookup"><span data-stu-id="eac34-156">Yes</span></span>        |
|<span data-ttu-id="eac34-157">在安装所有应用和配置文件之前阻止设备使用</span><span class="sxs-lookup"><span data-stu-id="eac34-157">Block device use until all apps and profiles are installed</span></span>     |  <span data-ttu-id="eac34-158">是</span><span class="sxs-lookup"><span data-stu-id="eac34-158">Yes</span></span>       |
|<span data-ttu-id="eac34-159">允许用户在出现安装错误时重置设备</span><span class="sxs-lookup"><span data-stu-id="eac34-159">Allow users to reset device if installation error occurs</span></span>     |  <span data-ttu-id="eac34-160">是</span><span class="sxs-lookup"><span data-stu-id="eac34-160">Yes</span></span>       |
|<span data-ttu-id="eac34-161">发生安装错误时允许用户使用设备</span><span class="sxs-lookup"><span data-stu-id="eac34-161">Allow users to use device if installation error occurs</span></span>     |  <span data-ttu-id="eac34-162">是</span><span class="sxs-lookup"><span data-stu-id="eac34-162">Yes</span></span>       |
|<span data-ttu-id="eac34-163">阻止设备使用，直到安装这些必需的应用（如果它们已分配给用户/设备）</span><span class="sxs-lookup"><span data-stu-id="eac34-163">Block device use until these required apps are installed if they are assigned to the user/device</span></span>     |  <span data-ttu-id="eac34-164">现代工作场所 - 时间更正</span><span class="sxs-lookup"><span data-stu-id="eac34-164">Modern Workplace - Time Correction</span></span>       |



<span data-ttu-id="eac34-165">注册状态页面体验分三个阶段进行。</span><span class="sxs-lookup"><span data-stu-id="eac34-165">The Enrollment Status Page experience occurs in three phases.</span></span> <span data-ttu-id="eac34-166">有关详细信息，请参阅注册 [状态页面跟踪信息](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)。</span><span class="sxs-lookup"><span data-stu-id="eac34-166">For more, see [Enrollment Status Page tracking information](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).</span></span>

<span data-ttu-id="eac34-167">体验将按如下方式进行：</span><span class="sxs-lookup"><span data-stu-id="eac34-167">The experience proceeds as follows:</span></span>

1. <span data-ttu-id="eac34-168">Autopilot 体验将启动，并且用户输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="eac34-168">The Autopilot experience starts and the user enters their credentials.</span></span>
2. <span data-ttu-id="eac34-169">设备打开注册状态页，然后继续执行设备准备和设备设置阶段。</span><span class="sxs-lookup"><span data-stu-id="eac34-169">The device opens the Enrollment Status Page and proceeds through Device Preparation and Device Setup phases.</span></span> <span data-ttu-id="eac34-170">帐户设置 (第) 步当前在 Microsoft 托管桌面配置中已跳过，因为用户 ESP 已禁用。</span><span class="sxs-lookup"><span data-stu-id="eac34-170">The third step (Account Setup) is *currently skipped* in the Microsoft Managed Desktop configuration because User ESP is disabled.</span></span> <span data-ttu-id="eac34-171">设备重新启动。</span><span class="sxs-lookup"><span data-stu-id="eac34-171">The device restarts.</span></span>
3. <span data-ttu-id="eac34-172">重新启动后，设备将打开其他用户的 Windows **登录页**。</span><span class="sxs-lookup"><span data-stu-id="eac34-172">After restart, the device opens the Windows sign-in page with **Other user**.</span></span>
4. <span data-ttu-id="eac34-173">用户再次输入其凭据，桌面将打开。</span><span class="sxs-lookup"><span data-stu-id="eac34-173">The users enter their credentials again and the desktop opens.</span></span>

> [!NOTE]
> <span data-ttu-id="eac34-174">如果 Windows 10 版本为 1903 或更高版本，则仅在 ESP 期间部署 Win32 应用。</span><span class="sxs-lookup"><span data-stu-id="eac34-174">Win32 apps are only deployed during ESP if the Windows 10 version is 1903 or later.</span></span>

![Autopilot 设置的起始页显示"设备准备"和"设备设置"阶段。](../../media/mmd-autopilot-screenshot.png)

## <a name="autopilot-for-pre-provisioned-deployment"></a><span data-ttu-id="eac34-176">用于预预配部署的 Autopilot</span><span class="sxs-lookup"><span data-stu-id="eac34-176">Autopilot for pre-provisioned deployment</span></span>
> [!NOTE]
> <span data-ttu-id="eac34-177">Microsoft 托管桌面中用于预预配部署的 Autopilot 目前处于公共预览阶段。</span><span class="sxs-lookup"><span data-stu-id="eac34-177">Autopilot for pre-provisioned deployment in Microsoft Managed Desktop is currently in public preview.</span></span>

## <a name="additional-prerequisites-for-autopilot-for-pre-provisioned-deployment"></a><span data-ttu-id="eac34-178">用于预预配部署的 Autopilot 的其他先决条件</span><span class="sxs-lookup"><span data-stu-id="eac34-178">Additional prerequisites for Autopilot for pre-provisioned deployment</span></span>
- <span data-ttu-id="eac34-179">YOU must have Enrollment Status Page (ESP) enabled.</span><span class="sxs-lookup"><span data-stu-id="eac34-179">You must have Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="eac34-180">有关详细信息，请参阅初始 [部署](#initial-deployment)。</span><span class="sxs-lookup"><span data-stu-id="eac34-180">For more information, see [Initial deployment](#initial-deployment).</span></span>
- <span data-ttu-id="eac34-181">设备必须具有有线网络连接。</span><span class="sxs-lookup"><span data-stu-id="eac34-181">Device must have a wired network connection.</span></span>
- <span data-ttu-id="eac34-182">如果你有在 2020 年 8 月之前使用 Microsoft 托管桌面门户注册的设备，请取消注册并再次注册它们。</span><span class="sxs-lookup"><span data-stu-id="eac34-182">If you have devices that were registered using the Microsoft Managed Desktop portal before August 2020, de-register and register them again.</span></span>
- <span data-ttu-id="eac34-183">设备必须具有包含 2020 年 11 月累积更新 [19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3) 或 [20H1 2020.11C](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) 的出厂映像（如果已安装）或必须用最新的 Microsoft 托管桌面映像进行重新映像。</span><span class="sxs-lookup"><span data-stu-id="eac34-183">Devices must must have a factory image that includes the November 2020 cumulative update [19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3) or [20H1 2020.11C](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) as appropriate installed or must be reimaged with the latest Microsoft Managed Desktop image.</span></span>
- <span data-ttu-id="eac34-184">物理设备必须支持 TPM 2.0 和设备证明。</span><span class="sxs-lookup"><span data-stu-id="eac34-184">Physical devices must support TPM 2.0 and device attestation.</span></span> <span data-ttu-id="eac34-185">不支持虚拟机。</span><span class="sxs-lookup"><span data-stu-id="eac34-185">Virtual machines aren't supported.</span></span> <span data-ttu-id="eac34-186">预配过程使用 Windows Autopilot 自部署功能，因此需要 TPM 2.0。</span><span class="sxs-lookup"><span data-stu-id="eac34-186">The pre-provisioning process uses Windows Autopilot self-deploying capabilities, so TPM 2.0 is required.</span></span> <span data-ttu-id="eac34-187">TPM 证明过程还要求访问每个 TPM 提供程序唯一的一组 HTTPS URL。</span><span class="sxs-lookup"><span data-stu-id="eac34-187">The TPM attestation process also requires access to a set of HTTPS URLs that are unique for each TPM provider.</span></span> <span data-ttu-id="eac34-188">有关详细信息，请参阅 Windows Autopilot 网络要求中的 Autopilot 自部署模式和 Autopilot 预预配 [部署条目](https://docs.microsoft.com/mem/autopilot/networking-requirements#tpm)。</span><span class="sxs-lookup"><span data-stu-id="eac34-188">For more information, see the entry for Autopilot self-deploying mode and Autopilot pre-provisioned deployment in [Windows Autopilot networking requirements](https://docs.microsoft.com/mem/autopilot/networking-requirements#tpm).</span></span>

## <a name="sequence-of-events-in-autopilot-for-pre-provisioned-deployment"></a><span data-ttu-id="eac34-189">用于预预配部署的 Autopilot 中的事件序列</span><span class="sxs-lookup"><span data-stu-id="eac34-189">Sequence of events in Autopilot for pre-provisioned deployment</span></span>
1. <span data-ttu-id="eac34-190">IT 管理员根据需要重置设备映像或重置设备。</span><span class="sxs-lookup"><span data-stu-id="eac34-190">IT Admin reimages or resets the device if needed.</span></span>
2. <span data-ttu-id="eac34-191">IT 管理员启动设备，获得开箱即用体验，然后按 Windows 键五次。</span><span class="sxs-lookup"><span data-stu-id="eac34-191">IT Admin boots the device, reaches the out-of-box-experience, and presses the Windows key five times.</span></span>
3. <span data-ttu-id="eac34-192">IT 管理员选择"Windows Autopilot 预配"，然后选择"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="eac34-192">IT Admin selects Windows Autopilot Provisioning and then selects **Continue**.</span></span> <span data-ttu-id="eac34-193">在 Windows Autopilot 配置屏幕上，将显示有关设备的信息。</span><span class="sxs-lookup"><span data-stu-id="eac34-193">On the Windows Autopilot configuration screen, information will be displayed about the device.</span></span>
5. <span data-ttu-id="eac34-194">IT 管理员选择 **预配** 以开始预配过程。</span><span class="sxs-lookup"><span data-stu-id="eac34-194">IT admin selects **Provision** to start the provisioning process.</span></span>
6. <span data-ttu-id="eac34-195">设备启动 ESP 并完成设备准备和设置阶段。</span><span class="sxs-lookup"><span data-stu-id="eac34-195">Device starts ESP and goes through device preparation and setup phases.</span></span> <span data-ttu-id="eac34-196">在设备设置阶段，你将看到显示 x 的应用安装 **x， (** ESP 配置文件设置的准确) 。</span><span class="sxs-lookup"><span data-stu-id="eac34-196">During the device setup phase, you'll see **App installation x of x** displayed (depending on the exact configuration of the ESP profile).</span></span>
7. <span data-ttu-id="eac34-197">帐户设置步骤当前在 Microsoft 托管桌面配置中跳过，因为我们禁用用户 ESP。</span><span class="sxs-lookup"><span data-stu-id="eac34-197">The account setup step is currently skipped in the Microsoft Managed Desktop configuration, since we disable User ESP.</span></span>
8. <span data-ttu-id="eac34-198">设备重新启动。</span><span class="sxs-lookup"><span data-stu-id="eac34-198">The device restarts.</span></span>

<span data-ttu-id="eac34-199">重新启动后，设备将显示绿色状态屏幕，并添加 **"重新封装"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="eac34-199">After it restarts, the device will show the green status screen, with a **Reseal** button.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eac34-200">已知问题：</span><span class="sxs-lookup"><span data-stu-id="eac34-200">Known issues :</span></span> 
> - <span data-ttu-id="eac34-201">ESP 在 Autopilot 用于预预配的部署封装函数之后不会再次运行。</span><span class="sxs-lookup"><span data-stu-id="eac34-201">ESP does not run again after the Autopilot for pre-provisioned deployment reseal function.</span></span>
> - <span data-ttu-id="eac34-202">对于预先预配的部署，Autopilot 不会重命名设备。</span><span class="sxs-lookup"><span data-stu-id="eac34-202">Device are not being renamed by Autopilot for pre-provisioned deployment.</span></span> <span data-ttu-id="eac34-203">设备只有在经过 ESP 用户流后才能重命名。</span><span class="sxs-lookup"><span data-stu-id="eac34-203">The device will only be renamed after going through the ESP user flow.</span></span>


## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a><span data-ttu-id="eac34-204">更改为 Autopilot 和注册状态页面设置</span><span class="sxs-lookup"><span data-stu-id="eac34-204">Change to Autopilot and Enrollment Status Page settings</span></span>

<span data-ttu-id="eac34-205">如果 Microsoft 托管桌面使用的设置不完全匹配你的需求，可以通过管理门户提交 [支持票证](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="eac34-205">If the setup used by Microsoft Managed Desktop doesn't exactly match your needs, you can  file a support ticket through the [Admin Portal](https://portal.azure.com/).</span></span> <span data-ttu-id="eac34-206">下面是您可能需要的配置类型的一些示例：</span><span class="sxs-lookup"><span data-stu-id="eac34-206">Here are some examples of the types of configuration you might need:</span></span>

### <a name="autopilot-settings-change"></a><span data-ttu-id="eac34-207">Autopilot 设置更改</span><span class="sxs-lookup"><span data-stu-id="eac34-207">Autopilot settings change</span></span>

<span data-ttu-id="eac34-208">你可能想要请求其他设备名称模板。</span><span class="sxs-lookup"><span data-stu-id="eac34-208">You might want to request a different device name template.</span></span> <span data-ttu-id="eac34-209">但是，你无法更改部署模式、加入 Azure AD As、隐私设置或用户帐户类型。</span><span class="sxs-lookup"><span data-stu-id="eac34-209">You cannot, however, change Deployment Mode, Join to Azure AD As, Privacy Settings, or User Account Type.</span></span>

### <a name="enrollment-status-page-settings-change"></a><span data-ttu-id="eac34-210">注册状态页面设置更改</span><span class="sxs-lookup"><span data-stu-id="eac34-210">Enrollment Status Page settings change</span></span>

- <span data-ttu-id="eac34-211">"安装所花的时间超过指定分钟数时显示错误"设置的分钟数较长。</span><span class="sxs-lookup"><span data-stu-id="eac34-211">A longer number of minutes for the "Show an error when installation takes longer than specified number of minutes" setting.</span></span>
- <span data-ttu-id="eac34-212">显示的错误消息</span><span class="sxs-lookup"><span data-stu-id="eac34-212">The error message displayed</span></span>
- <span data-ttu-id="eac34-213">在"阻止设备使用，直到安装这些必需的应用（如果它们已分配给用户/设备）"设置中添加或删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="eac34-213">Adding or removing applications in the "Block device use until these required apps are installed if they are assigned to the user/device" setting.</span></span>

## <a name="required-applications"></a><span data-ttu-id="eac34-214">必需的应用程序</span><span class="sxs-lookup"><span data-stu-id="eac34-214">Required applications</span></span>

- <span data-ttu-id="eac34-215">你必须面向新式工作区设备组 Test、First、Fast 和 Broad 中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="eac34-215">You must target applications in the Modern Workplace *device groups* Test, First, Fast, and Broad.</span></span> <span data-ttu-id="eac34-216">应用程序必须安装在"系统"上下文中。</span><span class="sxs-lookup"><span data-stu-id="eac34-216">Applications must install in the "System" context.</span></span> <span data-ttu-id="eac34-217">在将 ESP 分配给所有组之前，请确保使用测试组中 ESP 完成测试。</span><span class="sxs-lookup"><span data-stu-id="eac34-217">Make sure to complete testing with ESP in the Test group before you assign them to all groups.</span></span>
- <span data-ttu-id="eac34-218">任何应用程序都不应要求重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="eac34-218">No applications should require the device to restart.</span></span> <span data-ttu-id="eac34-219">建议在生成应用程序包时将应用程序设置为"不执行任何操作"（如果需要重新启动）。</span><span class="sxs-lookup"><span data-stu-id="eac34-219">We recommend that applications be set to "Do nothing" when you build the application package if they will require a restart.</span></span>
- <span data-ttu-id="eac34-220">将所需应用程序限制为仅在用户登录到设备时立即需要的核心应用程序。</span><span class="sxs-lookup"><span data-stu-id="eac34-220">Limit required applications to only the core applications that a user needs immediately when they sign in to the device.</span></span>
- <span data-ttu-id="eac34-221">将所有应用程序的总大小统一保持在 1 GB 以下，以避免在应用程序安装阶段超时。</span><span class="sxs-lookup"><span data-stu-id="eac34-221">Keep the total size of all applications collectively under 1 GB to avoid timeouts during the application installation phase.</span></span>
- <span data-ttu-id="eac34-222">理想情况下，应用不应有任何依赖关系。</span><span class="sxs-lookup"><span data-stu-id="eac34-222">Ideally, apps should not have any dependencies.</span></span> <span data-ttu-id="eac34-223">如果你有 *必须具有依赖项* 的应用，请确保在 ESP 评估中配置、测试和验证它们。</span><span class="sxs-lookup"><span data-stu-id="eac34-223">If you have apps that *must* have dependencies, be sure you configure, test, and validate them as part of your ESP evaluation.</span></span>
- <span data-ttu-id="eac34-224">例如，不需要"用户"上下文 (例如，Teams) 可包含在 ESP 的公共预览版中。</span><span class="sxs-lookup"><span data-stu-id="eac34-224">No applications that require the "user" context (for example, Teams) can be included in the public preview of ESP.</span></span>