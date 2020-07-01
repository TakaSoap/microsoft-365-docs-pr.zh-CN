---
title: 新建 Microsoft Edge
description: ''
keywords: 浏览器、Microsoft 托管桌面、Microsoft 365、服务、文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: d11fd8f29e3232472f9457ba1fc288a5084429e9
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936133"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="23976-103">新建 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="23976-103">New Microsoft Edge app</span></span>

<span data-ttu-id="23976-104">新的[Microsoft Edge 浏览器](https://www.microsoft.com/edge)在浏览过程中提供了世界一流的性能、更高的隐私、更高的工作效率和更多价值。</span><span class="sxs-lookup"><span data-stu-id="23976-104">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="23976-105">Microsoft 托管桌面提供了在您的环境中部署新边缘浏览器的公共预览。</span><span class="sxs-lookup"><span data-stu-id="23976-105">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="23976-106">初始部署</span><span class="sxs-lookup"><span data-stu-id="23976-106">Initial deployment</span></span>

<span data-ttu-id="23976-107">若要将 Microsoft 托管桌面设备迁移到新的 Microsoft Edge 浏览器，请通过 Microsoft 托管桌面门户文件提供 IT 支持票证。</span><span class="sxs-lookup"><span data-stu-id="23976-107">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="23976-108">在您对票证进行存档时，我们会将边缘稳定通道部署到测试组，然后在每个后续的部署组中每隔24小时部署它。</span><span class="sxs-lookup"><span data-stu-id="23976-108">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="23976-109">若要暂停部署，请文件另一个票证请求操作保留。</span><span class="sxs-lookup"><span data-stu-id="23976-109">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="23976-110">Microsoft Edge 的更新</span><span class="sxs-lookup"><span data-stu-id="23976-110">Updates to Microsoft Edge</span></span>

<span data-ttu-id="23976-111">Microsoft 托管桌面部署 Microsoft Edge 的[稳定通道](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel)，每六周自动更新一次。</span><span class="sxs-lookup"><span data-stu-id="23976-111">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge which is auto-updated about every six weeks.</span></span> <span data-ttu-id="23976-112">对稳定通道的更新由 Microsoft Edge 产品组[逐步](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout)进行，以确保为客户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="23976-112">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> <span data-ttu-id="23976-113">Microsoft Edge Beta 通道目前不可用。</span><span class="sxs-lookup"><span data-stu-id="23976-113">The Microsoft Edge Beta channel is not currently available.</span></span>

<span data-ttu-id="23976-114">若要确保 Microsoft Edge 正确更新，请不要修改 Microsoft Edge[更新策略](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)。</span><span class="sxs-lookup"><span data-stu-id="23976-114">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="23976-115">Microsoft 托管桌面管理的设置</span><span class="sxs-lookup"><span data-stu-id="23976-115">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="23976-116">Microsoft 托管桌面已为 Microsoft Edge 创建了一组默认的策略，以保护浏览器的安全。</span><span class="sxs-lookup"><span data-stu-id="23976-116">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="23976-117">默认浏览器设置如下所示：</span><span class="sxs-lookup"><span data-stu-id="23976-117">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="23976-118">Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="23976-118">Microsoft Edge extensions</span></span>

<span data-ttu-id="23976-119">Microsoft 托管桌面设备上 Microsoft Edge 的安全基准设置了两个策略，以禁用所有 Chrome 扩展和安全最终用户。</span><span class="sxs-lookup"><span data-stu-id="23976-119">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure end users.</span></span> <span data-ttu-id="23976-120">若要在环境中启用和部署扩展，请参阅管理的设置。</span><span class="sxs-lookup"><span data-stu-id="23976-120">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="23976-121">扩展安装阻止列表</span><span class="sxs-lookup"><span data-stu-id="23976-121">Extension installation blocklist</span></span>
<span data-ttu-id="23976-122">**默认值：** 各种</span><span class="sxs-lookup"><span data-stu-id="23976-122">**Default value:** All</span></span>

<span data-ttu-id="23976-123">Microsoft 托管桌面设置此策略，以防止在托管终结点上安装 Chrome 扩展。</span><span class="sxs-lookup"><span data-stu-id="23976-123">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="23976-124">存在具有 Chromium 扩展模型的已知 risksassociated，其中包括数据丢失保护、隐私和可能危害设备的其他风险。</span><span class="sxs-lookup"><span data-stu-id="23976-124">There are known risksassociated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="23976-125">允许用户级别的本机邮件主机（无需管理员权限即可安装）</span><span class="sxs-lookup"><span data-stu-id="23976-125">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="23976-126">**默认值：** 禁用</span><span class="sxs-lookup"><span data-stu-id="23976-126">**Default value:** Disabled</span></span>

<span data-ttu-id="23976-127">通过禁用此策略，Microsoft Edge 将仅使用安装在系统级别上的本机邮件主机。</span><span class="sxs-lookup"><span data-stu-id="23976-127">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="23976-128">本机邮件主机是 Chrome 扩展的一部分，它允许浏览器与用户终结点的其他部分进行交互，从而产生各种安全问题。</span><span class="sxs-lookup"><span data-stu-id="23976-128">Native messaging hosts are a part of Chrome extensions which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-ssl"></a><span data-ttu-id="23976-129">安全套接字层 (SSL)</span><span class="sxs-lookup"><span data-stu-id="23976-129">Secure Sockets Layer (SSL)</span></span>

#### <a name="minimum-ssl-version"></a><span data-ttu-id="23976-130">最低 SSL 版本</span><span class="sxs-lookup"><span data-stu-id="23976-130">Minimum SSL version</span></span>

<span data-ttu-id="23976-131">**默认值：** 支持的最低 TLS 1。2</span><span class="sxs-lookup"><span data-stu-id="23976-131">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="23976-132">如果要使用安全性较低的 TLS 1.1，可以请求这样做。</span><span class="sxs-lookup"><span data-stu-id="23976-132">If you want to use the less secure TLS 1.1, you can request this.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="23976-133">允许用户从 "SSL 警告" 页继续</span><span class="sxs-lookup"><span data-stu-id="23976-133">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="23976-134">**默认值：** 禁用</span><span class="sxs-lookup"><span data-stu-id="23976-134">**Default value:** Disabled</span></span>

<span data-ttu-id="23976-135">建议您不要启用此设置，因为它允许用户访问具有 SSL 错误的网站。</span><span class="sxs-lookup"><span data-stu-id="23976-135">We don't recommend enabling this setting since it allows users to visit sites with SSL errors.</span></span>

### <a name="microsoft-defender-smart-screen"></a><span data-ttu-id="23976-136">Microsoft Defender 智能屏幕</span><span class="sxs-lookup"><span data-stu-id="23976-136">Microsoft Defender Smart Screen</span></span>

#### <a name="configure-microsoft-defender-smartscreen"></a><span data-ttu-id="23976-137">配置 Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="23976-137">Configure Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="23976-138">**默认值：** 了</span><span class="sxs-lookup"><span data-stu-id="23976-138">**Default value:** Enabled</span></span>

<span data-ttu-id="23976-139">默认情况下启用以帮助保护最终用户。</span><span class="sxs-lookup"><span data-stu-id="23976-139">Enabled by default to help protect end users.</span></span>

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="23976-140">Microsoft Defender SmartScreen 网站提示</span><span class="sxs-lookup"><span data-stu-id="23976-140">Microsoft Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="23976-141">**默认值：** 了</span><span class="sxs-lookup"><span data-stu-id="23976-141">**Default value:** Enabled</span></span>

<span data-ttu-id="23976-142">建议您不要禁用此设置，因为这将允许用户忽略警告，并继续执行潜在的恶意网站。</span><span class="sxs-lookup"><span data-stu-id="23976-142">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="23976-143">阻止绕过关于下载的 Microsoft Defender SmartScreen 警告</span><span class="sxs-lookup"><span data-stu-id="23976-143">Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="23976-144">**默认值：** 了</span><span class="sxs-lookup"><span data-stu-id="23976-144">**Default value:** Enabled</span></span>

<span data-ttu-id="23976-145">建议不要禁用此设置，因为这将允许用户忽略警告和完成未验证的下载。</span><span class="sxs-lookup"><span data-stu-id="23976-145">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="23976-146">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="23976-146">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="23976-147">默认 Adobe Flash 设置</span><span class="sxs-lookup"><span data-stu-id="23976-147">Default Adobe Flash setting</span></span>

<span data-ttu-id="23976-148">**默认值：** 禁用</span><span class="sxs-lookup"><span data-stu-id="23976-148">**Default value:** Disabled</span></span>

<span data-ttu-id="23976-149">由于相关的安全风险，建议不要使用 Flash。</span><span class="sxs-lookup"><span data-stu-id="23976-149">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="23976-150">如果仍有依赖于 Flash 的进程，请设置**[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** 策略以为需要它的网站启用 Flash。</span><span class="sxs-lookup"><span data-stu-id="23976-150">If you still have processes which depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites which need it.</span></span> <span data-ttu-id="23976-151">如果无法维护允许的网站列表以使用 Flash，请将更改请求更改为**单击以播放**，这样用户就可以选择何时运行 flash。</span><span class="sxs-lookup"><span data-stu-id="23976-151">If can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="23976-152">密码管理器</span><span class="sxs-lookup"><span data-stu-id="23976-152">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="23976-153">启用将密码保存到密码管理器</span><span class="sxs-lookup"><span data-stu-id="23976-153">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="23976-154">**默认值：** 禁用</span><span class="sxs-lookup"><span data-stu-id="23976-154">**Default value:** Disabled</span></span>

<span data-ttu-id="23976-155">建议不要让最终用户在其设备上保存密码。</span><span class="sxs-lookup"><span data-stu-id="23976-155">We do not recommend allowing end users to save passwords on their device.</span></span>

### <a name="other-settings"></a><span data-ttu-id="23976-156">其他设置</span><span class="sxs-lookup"><span data-stu-id="23976-156">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="23976-157">为每个网站启用网站隔离</span><span class="sxs-lookup"><span data-stu-id="23976-157">Enable site isolation for every site</span></span>

<span data-ttu-id="23976-158">**默认值：** 了</span><span class="sxs-lookup"><span data-stu-id="23976-158">**Default value:** Enabled</span></span>

<span data-ttu-id="23976-159">如果启用此策略，则用户将无法退出每个网站在其自己的进程中运行的默认行为。</span><span class="sxs-lookup"><span data-stu-id="23976-159">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="23976-160">支持的身份验证方案</span><span class="sxs-lookup"><span data-stu-id="23976-160">Supported authentication schemes</span></span>

<span data-ttu-id="23976-161">**默认值：** NTLM、协商</span><span class="sxs-lookup"><span data-stu-id="23976-161">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="23976-162">Microsoft 托管桌面不支持基本或摘要式身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="23976-162">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="23976-163">首次运行时自动导入另一个浏览器的数据和设置</span><span class="sxs-lookup"><span data-stu-id="23976-163">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="23976-164">**默认值：** 从默认浏览器自动导入所有受支持的数据类型和设置</span><span class="sxs-lookup"><span data-stu-id="23976-164">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="23976-165">应用此策略后，首次运行体验将跳过 "导入" 部分，最大限度地减少用户交互。</span><span class="sxs-lookup"><span data-stu-id="23976-165">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="23976-166">Microsoft Edge 早期版本中的浏览器数据将始终在首次运行时无提示地迁移，无论此设置如何。</span><span class="sxs-lookup"><span data-stu-id="23976-166">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="23976-167">您管理的设置</span><span class="sxs-lookup"><span data-stu-id="23976-167">Settings you manage</span></span>

<span data-ttu-id="23976-168">您可以使用 Microsoft Intune 中的 "管理模板" 配置文件，部署先前未介绍的任何 Microsoft 边缘设置。</span><span class="sxs-lookup"><span data-stu-id="23976-168">You can deploy any Microsft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="23976-169">有关详细信息，请参阅[Configure Microsoft Edge policy settings With Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)。</span><span class="sxs-lookup"><span data-stu-id="23976-169">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="23976-170">如果要评估当前未包含在 Intune 中的 Microsoft Edge 管理模板中的策略，可以在 Intune 中使用 Windows 10 设备的自定义设置。</span><span class="sxs-lookup"><span data-stu-id="23976-170">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="23976-171">启用特定的部件版式扩展</span><span class="sxs-lookup"><span data-stu-id="23976-171">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="23976-172">管理模板提供了使用 Microsoft Intune 部署特定 Chrome 扩展的设置。</span><span class="sxs-lookup"><span data-stu-id="23976-172">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="23976-173">您可以在 "**计算机配置 > Microsoft Edge > 扩展中找到它，> 允许安装特定的扩展**。</span><span class="sxs-lookup"><span data-stu-id="23976-173">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="23976-174">自动安装扩展</span><span class="sxs-lookup"><span data-stu-id="23976-174">Install extensions silently</span></span>

<span data-ttu-id="23976-175">您还可以使用管理模板设置 Microsoft Edge 以安装分机，而不向用户发出警告。</span><span class="sxs-lookup"><span data-stu-id="23976-175">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="23976-176">您可以在 "**计算机配置" > Microsoft Edge > 扩展中找到它，> 控制自动安装哪些扩展**。</span><span class="sxs-lookup"><span data-stu-id="23976-176">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="23976-177">其他常见的企业策略</span><span class="sxs-lookup"><span data-stu-id="23976-177">Other common enterprise policies</span></span>

<span data-ttu-id="23976-178">Microsoft Edge 提供了很多其他策略。</span><span class="sxs-lookup"><span data-stu-id="23976-178">Microsoft Edge offers a great many additional policies.</span></span> <span data-ttu-id="23976-179">以下是一些比较常见的项：</span><span class="sxs-lookup"><span data-stu-id="23976-179">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="23976-180">在企业网站列表和 IE 模式下配置网站</span><span class="sxs-lookup"><span data-stu-id="23976-180">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="23976-181">配置 "启动"、"主页" 和 "新建选项卡页" 设置</span><span class="sxs-lookup"><span data-stu-id="23976-181">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="23976-182">配置 "冲浪游戏" 设置</span><span class="sxs-lookup"><span data-stu-id="23976-182">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="23976-183">配置代理服务器设置</span><span class="sxs-lookup"><span data-stu-id="23976-183">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

