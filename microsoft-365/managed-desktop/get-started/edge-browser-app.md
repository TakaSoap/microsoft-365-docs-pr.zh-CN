---
title: 新版 Microsoft Edge
description: 介绍如何部署和更新新的边缘浏览器
keywords: browser， Microsoft Managed Desktop， Microsoft 365， 服务， 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 42ff665e8ba9c369e29eeeafd27affff04b40966
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841335"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="54e70-104">新的 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="54e70-104">New Microsoft Edge app</span></span>

<span data-ttu-id="54e70-105">新的 [Microsoft Edge](https://www.microsoft.com/edge) 浏览器提供了世界一流的性能，在浏览时具有更多隐私、更高的工作效率和更多价值。</span><span class="sxs-lookup"><span data-stu-id="54e70-105">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="54e70-106">Microsoft 托管桌面提供环境中新边缘浏览器部署的公共预览版。</span><span class="sxs-lookup"><span data-stu-id="54e70-106">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="54e70-107">初始部署</span><span class="sxs-lookup"><span data-stu-id="54e70-107">Initial deployment</span></span>

<span data-ttu-id="54e70-108">若要将 Microsoft 托管桌面设备迁移到新的 Microsoft Edge 浏览器，请通过 Microsoft 托管桌面门户提交 IT 支持票证。</span><span class="sxs-lookup"><span data-stu-id="54e70-108">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="54e70-109">当你提交票证时，我们会将边缘稳定渠道部署到测试组，然后每 24 小时在每个后续部署组中部署它。</span><span class="sxs-lookup"><span data-stu-id="54e70-109">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="54e70-110">若要暂停部署，请提出另一个请求操作保留的票证。</span><span class="sxs-lookup"><span data-stu-id="54e70-110">To pause the deployment, file another ticket asking Operations to hold.</span></span>

<span data-ttu-id="54e70-111">如果 [请求在](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) 组织中进行验证，也可使用 Beta 渠道。</span><span class="sxs-lookup"><span data-stu-id="54e70-111">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is also available upon request for representative validation within your organization.</span></span> <span data-ttu-id="54e70-112">Microsoft 托管桌面将按测试和第一组的要求部署应用程序，以便所有这些用户除了具有稳定渠道之外，还具有 Beta 渠道。</span><span class="sxs-lookup"><span data-stu-id="54e70-112">Microsoft Managed Desktop will deploy the application as required to the Test and First Groups so that all of those users have the Beta Channel in addition to the Stable Channel.</span></span> <span data-ttu-id="54e70-113">对于需要访问 Beta 渠道的其他用户，请将其添加到新式 **工作区 - Edge Beta Users** 组，并让他们从公司门户安装它</span><span class="sxs-lookup"><span data-stu-id="54e70-113">For any other users who need access to the Beta Channel, add them to the **Modern Workplace - Edge Beta Users** group and have them install it from the Company Portal</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="54e70-114">Microsoft Edge 更新</span><span class="sxs-lookup"><span data-stu-id="54e70-114">Updates to Microsoft Edge</span></span>

<span data-ttu-id="54e70-115">Microsoft 托管桌面部署 Microsoft Edge [的 Stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) 渠道，大约每六周自动更新一次。</span><span class="sxs-lookup"><span data-stu-id="54e70-115">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge, which is auto-updated about every six weeks.</span></span> <span data-ttu-id="54e70-116">稳定渠道上的更新由 Microsoft [](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) Edge 产品组逐步推出，以确保为客户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="54e70-116">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> 

<span data-ttu-id="54e70-117">Beta [渠道](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) 将部署到"测试"和"第一组"中的设备，以在组织中进行代表性验证。</span><span class="sxs-lookup"><span data-stu-id="54e70-117">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is deployed to devices in both the Test and First groups for representative validation within the organization.</span></span> <span data-ttu-id="54e70-118">此频道完全受支持，大约每六周自动更新一次新功能。</span><span class="sxs-lookup"><span data-stu-id="54e70-118">This channel is fully supported and is auto-updated with new features approximately every six weeks.</span></span>

<span data-ttu-id="54e70-119">若要确保 Microsoft Edge 正确更新，请不要修改 Microsoft Edge [更新策略](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)。</span><span class="sxs-lookup"><span data-stu-id="54e70-119">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>



## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="54e70-120">由 Microsoft 托管桌面管理的设置</span><span class="sxs-lookup"><span data-stu-id="54e70-120">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="54e70-121">Microsoft 托管桌面为 Microsoft Edge 创建了一组默认策略，用于保护浏览器安全。</span><span class="sxs-lookup"><span data-stu-id="54e70-121">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="54e70-122">默认浏览器设置如下所示：</span><span class="sxs-lookup"><span data-stu-id="54e70-122">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="54e70-123">Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="54e70-123">Microsoft Edge extensions</span></span>

<span data-ttu-id="54e70-124">Microsoft 托管桌面版设备上 Microsoft Edge 的安全基线设置两个策略，以禁用所有 Chrome 扩展和安全用户。</span><span class="sxs-lookup"><span data-stu-id="54e70-124">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure users.</span></span> <span data-ttu-id="54e70-125">若要在环境中启用和部署扩展，请参阅你管理的"设置"。</span><span class="sxs-lookup"><span data-stu-id="54e70-125">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="54e70-126">扩展安装阻止列表</span><span class="sxs-lookup"><span data-stu-id="54e70-126">Extension installation blocklist</span></span>
<span data-ttu-id="54e70-127">**默认值：** 全部</span><span class="sxs-lookup"><span data-stu-id="54e70-127">**Default value:** All</span></span>

<span data-ttu-id="54e70-128">Microsoft 托管桌面设置此策略，以防止在托管终结点上安装 Chrome 扩展。</span><span class="sxs-lookup"><span data-stu-id="54e70-128">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="54e70-129">存在与 Chromium 扩展模型相关的已知风险，包括数据丢失保护、隐私和其他可能会损害设备的风险。</span><span class="sxs-lookup"><span data-stu-id="54e70-129">There are known risks associated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="54e70-130">允许在没有管理员权限的情况下安装 (级本机消息传递) </span><span class="sxs-lookup"><span data-stu-id="54e70-130">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="54e70-131">**默认值：** 已禁用</span><span class="sxs-lookup"><span data-stu-id="54e70-131">**Default value:** Disabled</span></span>

<span data-ttu-id="54e70-132">通过禁用此策略，Microsoft Edge 将仅使用安装在系统级别的本机邮件主机。</span><span class="sxs-lookup"><span data-stu-id="54e70-132">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="54e70-133">本机消息传递主机是 Chrome 扩展的一部分，允许浏览器与用户终结点的其他部分进行交互，从而产生各种安全问题。</span><span class="sxs-lookup"><span data-stu-id="54e70-133">Native messaging hosts are a part of Chrome extensions, which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-tlsssl"></a><span data-ttu-id="54e70-134">TLS/SSL (安全套接字层) </span><span class="sxs-lookup"><span data-stu-id="54e70-134">Secure Sockets Layer (TLS/SSL)</span></span>

#### <a name="minimum-tls-version"></a><span data-ttu-id="54e70-135">最低 TLS 版本</span><span class="sxs-lookup"><span data-stu-id="54e70-135">Minimum TLS version</span></span>

<span data-ttu-id="54e70-136">**默认值：** 支持的最低 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="54e70-136">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="54e70-137">如果要使用安全性不太低的 TLS 1.1，可以提出这样做的请求。</span><span class="sxs-lookup"><span data-stu-id="54e70-137">If you want to use the less secure TLS 1.1, you can file a request to do so.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="54e70-138">允许用户从 SSL 警告页继续</span><span class="sxs-lookup"><span data-stu-id="54e70-138">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="54e70-139">**默认值：** 已禁用</span><span class="sxs-lookup"><span data-stu-id="54e70-139">**Default value:** Disabled</span></span>

<span data-ttu-id="54e70-140">建议不要启用此设置，因为它允许用户访问具有 TSL 错误的网站。</span><span class="sxs-lookup"><span data-stu-id="54e70-140">We don't recommend enabling this setting since it allows users to visit sites with TSL errors.</span></span>

### <a name="microsoft-defender-smartscreen"></a><span data-ttu-id="54e70-141">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="54e70-141">Microsoft Defender SmartScreen</span></span>

#### <a name="configure-windows-defender-smartscreen"></a><span data-ttu-id="54e70-142">配置 Windows Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="54e70-142">Configure Windows Defender SmartScreen</span></span>

<span data-ttu-id="54e70-143">**默认值：** 已启用</span><span class="sxs-lookup"><span data-stu-id="54e70-143">**Default value:** Enabled</span></span>

<span data-ttu-id="54e70-144">默认情况下启用以帮助保护用户。</span><span class="sxs-lookup"><span data-stu-id="54e70-144">Enabled by default to help protect users.</span></span>

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="54e70-145">Windows Defender站点显示 SmartScreen 提示</span><span class="sxs-lookup"><span data-stu-id="54e70-145">Windows Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="54e70-146">**默认值：** 已启用</span><span class="sxs-lookup"><span data-stu-id="54e70-146">**Default value:** Enabled</span></span>

<span data-ttu-id="54e70-147">建议不要禁用此设置，因为这样将允许用户忽略警告，并继续访问潜在恶意站点。</span><span class="sxs-lookup"><span data-stu-id="54e70-147">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="54e70-148">阻止绕过有关Windows Defender的 SmartScreen 警告</span><span class="sxs-lookup"><span data-stu-id="54e70-148">Prevent bypassing of Windows Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="54e70-149">**默认值：** 已启用</span><span class="sxs-lookup"><span data-stu-id="54e70-149">**Default value:** Enabled</span></span>

<span data-ttu-id="54e70-150">建议不要禁用此设置，因为这将允许用户忽略警告并完成未经验证的下载。</span><span class="sxs-lookup"><span data-stu-id="54e70-150">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="54e70-151">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="54e70-151">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="54e70-152">默认 Adobe Flash 设置</span><span class="sxs-lookup"><span data-stu-id="54e70-152">Default Adobe Flash setting</span></span>

<span data-ttu-id="54e70-153">**默认值：** 已禁用</span><span class="sxs-lookup"><span data-stu-id="54e70-153">**Default value:** Disabled</span></span>

<span data-ttu-id="54e70-154">我们不建议使用 Flash，因为存在相关的安全风险。</span><span class="sxs-lookup"><span data-stu-id="54e70-154">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="54e70-155">如果仍有依赖于 Flash 的进程，请设置 **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** 策略，为需要 Flash 的网站启用 Flash。</span><span class="sxs-lookup"><span data-stu-id="54e70-155">If you still have processes that depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites that need it.</span></span> <span data-ttu-id="54e70-156">如果无法维护允许的网站列表以使用 Flash，请提交更改请求以将值更改为"单击播放"，从而允许用户选择何时适合运行 Flash。</span><span class="sxs-lookup"><span data-stu-id="54e70-156">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="54e70-157">密码管理器</span><span class="sxs-lookup"><span data-stu-id="54e70-157">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="54e70-158">允许将密码保存至密码管理器</span><span class="sxs-lookup"><span data-stu-id="54e70-158">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="54e70-159">**默认值：** 已禁用</span><span class="sxs-lookup"><span data-stu-id="54e70-159">**Default value:** Disabled</span></span>

<span data-ttu-id="54e70-160">建议不要允许用户在设备上保存密码。</span><span class="sxs-lookup"><span data-stu-id="54e70-160">We do not recommend allowing users to save passwords on their device.</span></span>

### <a name="internet-explorer-mode-in-microsoft-edge"></a><span data-ttu-id="54e70-161">Internet Explorer Microsoft Edge 中的模式</span><span class="sxs-lookup"><span data-stu-id="54e70-161">Internet Explorer Mode in Microsoft Edge</span></span>
<span data-ttu-id="54e70-162">Microsoft Edge 上的 IE 模式使你能够轻松地在单一浏览器中使用组织所需的所有网站。</span><span class="sxs-lookup"><span data-stu-id="54e70-162">IE mode on Microsoft Edge makes it easy to use all of the sites your organization needs in a single browser.</span></span> <span data-ttu-id="54e70-163">它使用与 Chromium 呈现引擎兼容的网站的集成 Chromium 引擎，并使用 Internet Explorer 11 (IE11) 中的 Trident MSHTML 引擎来访问不依赖于 IE 功能或依赖 IE 功能的网站。</span><span class="sxs-lookup"><span data-stu-id="54e70-163">It uses the integrated Chromium engine for sites that are compatible with the Chromium rendering engine and it uses the Trident MSHTML engine from Internet Explorer 11 (IE11) for sites that aren't or have dependencies on IE functionality.</span></span> <span data-ttu-id="54e70-164">[了解更多] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span><span class="sxs-lookup"><span data-stu-id="54e70-164">[Learn more] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span></span> 

<span data-ttu-id="54e70-165">默认情况下，Microsoft 托管Internet Explorer为设备启用支持模式</span><span class="sxs-lookup"><span data-stu-id="54e70-165">Microsoft Managed Desktop enables Internet Explorer mode for your devices by default</span></span> 

#### <a name="internet-explorer-mode-integration"></a><span data-ttu-id="54e70-166">Internet Explorer模式集成</span><span class="sxs-lookup"><span data-stu-id="54e70-166">Internet Explorer mode integration</span></span>
<span data-ttu-id="54e70-167">**默认值：** Internet Explorer模式</span><span class="sxs-lookup"><span data-stu-id="54e70-167">**Default Value:** Internet Explorer mode</span></span>

<span data-ttu-id="54e70-168">默认情况下，设备设置为使用Internet Explorer模式，但你可以将其设置为改为在独立 Internet Explorer 11 窗口中打开网站。</span><span class="sxs-lookup"><span data-stu-id="54e70-168">By default, devices are set to use Internet Explorer mode, but you can set them to open sites in a standalone Internet Explorer 11 window instead.</span></span> <span data-ttu-id="54e70-169">若要更改此行为，请提交支持请求。</span><span class="sxs-lookup"><span data-stu-id="54e70-169">To change this behavior, file a support request.</span></span>

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a><span data-ttu-id="54e70-170">将站点添加到企业模式站点列表</span><span class="sxs-lookup"><span data-stu-id="54e70-170">Add sites to the Enterprise Mode Site list</span></span>
<span data-ttu-id="54e70-171">若要使站点在Internet Explorer模式打开，必须在企业站点列表中 [包括这些站点](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist)。</span><span class="sxs-lookup"><span data-stu-id="54e70-171">For sites to open in Internet Explorer mode you must include them on the [Enterprise Site list](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist).</span></span> <span data-ttu-id="54e70-172">维护和部署企业站点列表由你负责。</span><span class="sxs-lookup"><span data-stu-id="54e70-172">Maintaining and deploying the Enterprise Site list is your responsibility.</span></span> <span data-ttu-id="54e70-173">有关详细信息，请参阅使用 [配置企业模式站点列表策略进行配置](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span><span class="sxs-lookup"><span data-stu-id="54e70-173">For details, see [Configure using the Configure Enterprise Mode Site List policy](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span></span>

### <a name="other-settings"></a><span data-ttu-id="54e70-174">其他设置</span><span class="sxs-lookup"><span data-stu-id="54e70-174">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="54e70-175">为每个网站启用网站隔离</span><span class="sxs-lookup"><span data-stu-id="54e70-175">Enable site isolation for every site</span></span>

<span data-ttu-id="54e70-176">**默认值：** 已启用</span><span class="sxs-lookup"><span data-stu-id="54e70-176">**Default value:** Enabled</span></span>

<span data-ttu-id="54e70-177">启用此策略后，用户不能选择退出每个网站在其自己的进程中运行的默认行为。</span><span class="sxs-lookup"><span data-stu-id="54e70-177">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="54e70-178">支持的身份验证方案</span><span class="sxs-lookup"><span data-stu-id="54e70-178">Supported authentication schemes</span></span>

<span data-ttu-id="54e70-179">**默认值：** NTLM，协商</span><span class="sxs-lookup"><span data-stu-id="54e70-179">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="54e70-180">Microsoft 托管桌面不支持基本或摘要式身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="54e70-180">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="54e70-181">首次运行时自动导入其他浏览器的数据和设置</span><span class="sxs-lookup"><span data-stu-id="54e70-181">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="54e70-182">**默认值：** 自动从默认浏览器导入所有受支持的数据类型和设置</span><span class="sxs-lookup"><span data-stu-id="54e70-182">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="54e70-183">应用此策略后，首次运行体验将跳过导入部分，从而最大程度地减少用户交互。</span><span class="sxs-lookup"><span data-stu-id="54e70-183">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="54e70-184">来自较早版本的 Microsoft Edge 的浏览器数据将始终在首次运行时以静默方式迁移，无论此设置如何。</span><span class="sxs-lookup"><span data-stu-id="54e70-184">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="54e70-185">你管理的设置</span><span class="sxs-lookup"><span data-stu-id="54e70-185">Settings you manage</span></span>

<span data-ttu-id="54e70-186">可以使用 Microsoft Intune 中的管理模板配置文件部署之前未介绍的任何 Microsoft Edge 设置。</span><span class="sxs-lookup"><span data-stu-id="54e70-186">You can deploy any Microsoft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="54e70-187">有关详细信息，请参阅使用 Microsoft Intune 配置 [Microsoft Edge 策略设置](https://docs.microsoft.com/deployedge/configure-edge-with-intune)。</span><span class="sxs-lookup"><span data-stu-id="54e70-187">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="54e70-188">如果你想要评估当前未包含在 Intune 中的 Microsoft Edge 管理模板中的策略，可以在 Intune 中为 Windows 10 设备使用自定义设置。</span><span class="sxs-lookup"><span data-stu-id="54e70-188">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune, you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="54e70-189">启用特定 Chrome 扩展</span><span class="sxs-lookup"><span data-stu-id="54e70-189">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="54e70-190">管理模板提供了使用 Microsoft Intune 部署特定 Chrome 扩展的设置。</span><span class="sxs-lookup"><span data-stu-id="54e70-190">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="54e70-191">可以在 Microsoft Edge > Extensions > 的计算机配置 **>"允许安装特定扩展"。**</span><span class="sxs-lookup"><span data-stu-id="54e70-191">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="54e70-192">静默安装扩展</span><span class="sxs-lookup"><span data-stu-id="54e70-192">Install extensions silently</span></span>

<span data-ttu-id="54e70-193">您还可以使用管理模板将 Microsoft Edge 设置为安装扩展，而不向用户发出警报。</span><span class="sxs-lookup"><span data-stu-id="54e70-193">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="54e70-194">可以在 Microsoft Edge > 扩展>的计算机配置>控制以静默方式安装的 **扩展**。</span><span class="sxs-lookup"><span data-stu-id="54e70-194">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="microsoft-edge-update-policies"></a><span data-ttu-id="54e70-195">Microsoft Edge 更新策略</span><span class="sxs-lookup"><span data-stu-id="54e70-195">Microsoft Edge update policies</span></span>
<span data-ttu-id="54e70-196">若要确保 Microsoft Edge 正确更新，请不要修改 Microsoft Edge [更新策略](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)。</span><span class="sxs-lookup"><span data-stu-id="54e70-196">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="54e70-197">其他常见企业策略</span><span class="sxs-lookup"><span data-stu-id="54e70-197">Other common enterprise policies</span></span>

<span data-ttu-id="54e70-198">Microsoft Edge 提供了许多其他策略。</span><span class="sxs-lookup"><span data-stu-id="54e70-198">Microsoft Edge offers a great many other policies.</span></span> <span data-ttu-id="54e70-199">这些是一些更常见的方法：</span><span class="sxs-lookup"><span data-stu-id="54e70-199">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="54e70-200">在企业站点列表和 IE 模式下配置站点</span><span class="sxs-lookup"><span data-stu-id="54e70-200">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="54e70-201">配置启动、主页和新选项卡页设置</span><span class="sxs-lookup"><span data-stu-id="54e70-201">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="54e70-202">配置"浏览"游戏设置</span><span class="sxs-lookup"><span data-stu-id="54e70-202">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="54e70-203">配置代理服务器设置</span><span class="sxs-lookup"><span data-stu-id="54e70-203">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

