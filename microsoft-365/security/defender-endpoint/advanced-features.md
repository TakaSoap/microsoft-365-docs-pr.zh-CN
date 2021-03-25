---
title: 在 Microsoft Defender for Endpoint 中配置高级功能
description: 启用高级功能，如 Microsoft Defender for Endpoint 中的阻止文件。
keywords: 高级功能， 设置， 阻止文件， 自动调查， 自动解决， skype， microsoft defender for identity， office 365， azure 信息保护， intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 41c97d122362ec1fa945fc012ab7a1da46a43b68
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165581"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a><span data-ttu-id="4c27e-104">在 Defender for Endpoint 中配置高级功能</span><span class="sxs-lookup"><span data-stu-id="4c27e-104">Configure advanced features in Defender for Endpoint</span></span>

<span data-ttu-id="4c27e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4c27e-105">**Applies to:**</span></span>
- [<span data-ttu-id="4c27e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4c27e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4c27e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c27e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> <span data-ttu-id="4c27e-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="4c27e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4c27e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4c27e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="4c27e-110">根据你使用的 Microsoft 安全产品，某些高级功能可能可供你集成 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="4c27e-110">Depending on the Microsoft security products that you use, some advanced features might be available for you to integrate Defender for Endpoint with.</span></span>

## <a name="enable-advanced-features"></a><span data-ttu-id="4c27e-111">启用高级功能</span><span class="sxs-lookup"><span data-stu-id="4c27e-111">Enable advanced features</span></span>

1. <span data-ttu-id="4c27e-112">在导航窗格中，选择 **首选项设置**  >  **高级功能**。</span><span class="sxs-lookup"><span data-stu-id="4c27e-112">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="4c27e-113">选择要配置的高级功能，并切换 **开和\*\*\*\*关之间的设置**。</span><span class="sxs-lookup"><span data-stu-id="4c27e-113">Select the advanced feature you want to configure and toggle the setting between **On** and **Off**.</span></span>
3. <span data-ttu-id="4c27e-114">单击 **保存首选项**。</span><span class="sxs-lookup"><span data-stu-id="4c27e-114">Click **Save preferences**.</span></span>

<span data-ttu-id="4c27e-115">使用以下高级功能可以更好地防范潜在恶意文件，并获取安全调查期间更好的见解。</span><span class="sxs-lookup"><span data-stu-id="4c27e-115">Use the following advanced features to get better protected from potentially malicious files and gain better insight during security investigations.</span></span>

## <a name="automated-investigation"></a><span data-ttu-id="4c27e-116">自动调查</span><span class="sxs-lookup"><span data-stu-id="4c27e-116">Automated investigation</span></span>

<span data-ttu-id="4c27e-117">启用此功能以利用服务的自动调查和修正功能。</span><span class="sxs-lookup"><span data-stu-id="4c27e-117">Turn on this feature to take advantage of the automated investigation and remediation features of the service.</span></span> <span data-ttu-id="4c27e-118">有关详细信息，请参阅自动 [调查](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="4c27e-118">For more information, see [Automated investigation](automated-investigations.md).</span></span>

## <a name="live-response"></a><span data-ttu-id="4c27e-119">实时响应</span><span class="sxs-lookup"><span data-stu-id="4c27e-119">Live response</span></span>

<span data-ttu-id="4c27e-120">启用此功能，以便具有相应权限的用户可以在设备上启动实时响应会话。</span><span class="sxs-lookup"><span data-stu-id="4c27e-120">Turn on this feature so that users with the appropriate permissions can start a live response session on devices.</span></span>

<span data-ttu-id="4c27e-121">有关角色分配详细信息，请参阅创建 [和管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="4c27e-121">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>

## <a name="live-response-for-servers"></a><span data-ttu-id="4c27e-122">服务器实时响应</span><span class="sxs-lookup"><span data-stu-id="4c27e-122">Live response for servers</span></span>
<span data-ttu-id="4c27e-123">启用此功能，以便具有适当权限的用户可以启动服务器上实时响应会话。</span><span class="sxs-lookup"><span data-stu-id="4c27e-123">Turn on this feature so that users with the appropriate permissions can start a live response session on servers.</span></span>

<span data-ttu-id="4c27e-124">有关角色分配详细信息，请参阅创建 [和管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="4c27e-124">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>


## <a name="live-response-unsigned-script-execution"></a><span data-ttu-id="4c27e-125">实时响应未签名脚本执行</span><span class="sxs-lookup"><span data-stu-id="4c27e-125">Live response unsigned script execution</span></span>

<span data-ttu-id="4c27e-126">启用此功能后，您可以在实时响应会话中运行未签名的脚本。</span><span class="sxs-lookup"><span data-stu-id="4c27e-126">Enabling this feature allows you to run unsigned scripts in a live response session.</span></span>

## <a name="autoresolve-remediated-alerts"></a><span data-ttu-id="4c27e-127">Autoresolve 修正警报</span><span class="sxs-lookup"><span data-stu-id="4c27e-127">Autoresolve remediated alerts</span></span>

<span data-ttu-id="4c27e-128">对于在 Windows 10 版本 1809 或之后创建的租户，自动调查和修正功能默认配置为解决自动分析结果状态为"未找到威胁"或"已修正"的警报。</span><span class="sxs-lookup"><span data-stu-id="4c27e-128">For tenants created on or after Windows 10, version 1809, the automated investigation and remediation capability is configured by default to resolve alerts where the automated analysis result status is "No threats found" or "Remediated".</span></span>  <span data-ttu-id="4c27e-129">如果不希望自动解决警报，需要手动关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="4c27e-129">If you don't want to have alerts auto-resolved, you'll need to manually turn off the feature.</span></span>

> [!TIP]
> <span data-ttu-id="4c27e-130">对于在此版本之前创建的租户，你需要从高级功能页面手动 [启用](https://securitycenter.windows.com/preferences2/integration) 此功能。</span><span class="sxs-lookup"><span data-stu-id="4c27e-130">For tenants created prior to that version, you'll need to manually turn this feature on from the [Advanced features](https://securitycenter.windows.com/preferences2/integration) page.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="4c27e-131">自动解决操作的结果可能会影响基于设备上找到的活动警报的设备风险级别计算。</span><span class="sxs-lookup"><span data-stu-id="4c27e-131">The result of the auto-resolve action may influence the Device risk level calculation which is based on the active alerts found on a device.</span></span>
> - <span data-ttu-id="4c27e-132">如果安全操作分析师手动将警报状态设置为"正在进行"或"已解决"，则自动解决功能不会覆盖它。</span><span class="sxs-lookup"><span data-stu-id="4c27e-132">If a security operations analyst manually sets the status of an alert to "In progress" or "Resolved" the auto-resolve capability will not overwrite it.</span></span>

## <a name="allow-or-block-file"></a><span data-ttu-id="4c27e-133">允许或阻止文件</span><span class="sxs-lookup"><span data-stu-id="4c27e-133">Allow or block file</span></span>

<span data-ttu-id="4c27e-134">仅在组织满足以下要求时，阻止才可用：</span><span class="sxs-lookup"><span data-stu-id="4c27e-134">Blocking is only available if your organization fulfills these requirements:</span></span>

- <span data-ttu-id="4c27e-135">使用 Microsoft Defender 防病毒作为活动的反恶意软件解决方案，</span><span class="sxs-lookup"><span data-stu-id="4c27e-135">Uses Microsoft Defender Antivirus as the active antimalware solution and,</span></span>
- <span data-ttu-id="4c27e-136">启用基于云的保护功能</span><span class="sxs-lookup"><span data-stu-id="4c27e-136">The cloud-based protection feature is enabled</span></span>

<span data-ttu-id="4c27e-137">此功能使你能够阻止网络中潜在的恶意文件。</span><span class="sxs-lookup"><span data-stu-id="4c27e-137">This feature enables you to block potentially malicious files in your network.</span></span> <span data-ttu-id="4c27e-138">阻止文件将阻止在组织的设备上读取、写入或执行文件。</span><span class="sxs-lookup"><span data-stu-id="4c27e-138">Blocking a file will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="4c27e-139">若要打开 **"允许"或"阻止** 文件"：：</span><span class="sxs-lookup"><span data-stu-id="4c27e-139">To turn **Allow or block** files on:</span></span>

1. <span data-ttu-id="4c27e-140">在导航窗格中，选择"**设置**  >  **""高级功能**  >  **""允许或阻止文件"。**</span><span class="sxs-lookup"><span data-stu-id="4c27e-140">In the navigation pane, select **Settings** > **Advanced features** > **Allow or block file**.</span></span>

1. <span data-ttu-id="4c27e-141">切换开和 **关\*\*\*\*之间的设置**。</span><span class="sxs-lookup"><span data-stu-id="4c27e-141">Toggle the setting between **On** and **Off**.</span></span>

    ![阻止文件功能的高级设置的图像](images/atp-preferences-setup.png)

1. <span data-ttu-id="4c27e-143">选择 **页面底部的** "保存首选项"。</span><span class="sxs-lookup"><span data-stu-id="4c27e-143">Select **Save preferences** at the bottom of the page.</span></span>

<span data-ttu-id="4c27e-144">启用此功能后，可以通过文件 [配置文件](respond-file-alerts.md#allow-or-block-file) 页上的 **"添加** 指示器"选项卡阻止文件。</span><span class="sxs-lookup"><span data-stu-id="4c27e-144">After turning on this feature, you can [block files](respond-file-alerts.md#allow-or-block-file) via the **Add Indicator** tab on a file's profile page.</span></span>

## <a name="custom-network-indicators"></a><span data-ttu-id="4c27e-145">自定义网络指示器</span><span class="sxs-lookup"><span data-stu-id="4c27e-145">Custom network indicators</span></span>

<span data-ttu-id="4c27e-146">启用此功能后，您可以创建 IP 地址、域或 URL 的指示器，这些指示器根据自定义指示器列表确定是否允许或阻止它们。</span><span class="sxs-lookup"><span data-stu-id="4c27e-146">Turning on this feature allows you to create indicators for IP addresses, domains, or URLs, which determine whether they will be allowed or blocked based on your custom indicator list.</span></span>

<span data-ttu-id="4c27e-147">若要使用此功能，设备必须运行 Windows 10 版本 1709 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="4c27e-147">To use this feature, devices must be running Windows 10 version 1709 or later.</span></span> <span data-ttu-id="4c27e-148">它们还应具有阻止模式和反恶意软件平台版本 4.18.1906.3 或更高版本的网络保护，请参阅[KB 4052623。](https://go.microsoft.com/fwlink/?linkid=2099834)</span><span class="sxs-lookup"><span data-stu-id="4c27e-148">They should also have network protection in block mode and version 4.18.1906.3 or later of the antimalware platform [see KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).</span></span>

<span data-ttu-id="4c27e-149">有关详细信息，请参阅管理 [指示器](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="4c27e-149">For more information, see [Manage indicators](manage-indicators.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4c27e-150">网络保护利用信誉服务，在可能超出你为 Defender for Endpoint 数据选择的位置之外的位置处理请求。</span><span class="sxs-lookup"><span data-stu-id="4c27e-150">Network protection leverages reputation services that process requests in locations that might be outside of the location you have selected for your Defender for Endpoint data.</span></span>

## <a name="show-user-details"></a><span data-ttu-id="4c27e-151">显示用户详细信息</span><span class="sxs-lookup"><span data-stu-id="4c27e-151">Show user details</span></span>

<span data-ttu-id="4c27e-152">启用此功能，以便你可以看到存储在 Azure Active Directory 中的用户详细信息。</span><span class="sxs-lookup"><span data-stu-id="4c27e-152">Turn on this feature so that you can see user details stored in Azure Active Directory.</span></span> <span data-ttu-id="4c27e-153">详细信息包括调查用户帐户实体时的用户图片、姓名、职务和部门信息。</span><span class="sxs-lookup"><span data-stu-id="4c27e-153">Details include a user's picture, name, title, and department information  when investigating user account entities.</span></span> <span data-ttu-id="4c27e-154">您可以在以下视图中找到用户帐户信息：</span><span class="sxs-lookup"><span data-stu-id="4c27e-154">You can find user account information in the following views:</span></span>

- <span data-ttu-id="4c27e-155">安全操作仪表板</span><span class="sxs-lookup"><span data-stu-id="4c27e-155">Security operations dashboard</span></span>
- <span data-ttu-id="4c27e-156">警报队列</span><span class="sxs-lookup"><span data-stu-id="4c27e-156">Alert queue</span></span>
- <span data-ttu-id="4c27e-157">设备详细信息页面</span><span class="sxs-lookup"><span data-stu-id="4c27e-157">Device details page</span></span>

<span data-ttu-id="4c27e-158">有关详细信息，请参阅 [调查用户帐户](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="4c27e-158">For more information, see [Investigate a user account](investigate-user.md).</span></span>

## <a name="skype-for-business-integration"></a><span data-ttu-id="4c27e-159">Skype for Business 集成</span><span class="sxs-lookup"><span data-stu-id="4c27e-159">Skype for Business integration</span></span>

<span data-ttu-id="4c27e-160">启用 Skype for Business 集成后，你能够使用 Skype for Business、电子邮件或电话与用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="4c27e-160">Enabling the Skype for Business integration gives you the ability to communicate with users using Skype for Business, email, or phone.</span></span> <span data-ttu-id="4c27e-161">当你需要与用户通信并降低风险时，这很方便。</span><span class="sxs-lookup"><span data-stu-id="4c27e-161">This can be handy when you need to communicate with the user and mitigate risks.</span></span>

> [!NOTE]
> <span data-ttu-id="4c27e-162">当设备与网络隔离时，有一个弹出窗口，你可以选择启用 Outlook 和 Skype 通信，这将允许用户在断开与网络的连接时与其通信。</span><span class="sxs-lookup"><span data-stu-id="4c27e-162">When a device is being isolated from the network, there's a pop-up where you can choose to enable Outlook and Skype communications which allows communications to the user while they are disconnected from the network.</span></span> <span data-ttu-id="4c27e-163">当设备在隔离模式下时，此设置适用于 Skype 和 Outlook 通信。</span><span class="sxs-lookup"><span data-stu-id="4c27e-163">This setting applies to Skype and Outlook communication when devices are in isolation mode.</span></span>

## <a name="azure-advanced-threat-protection-integration"></a><span data-ttu-id="4c27e-164">Azure 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="4c27e-164">Azure Advanced Threat Protection integration</span></span>

<span data-ttu-id="4c27e-165">与 Azure 高级威胁防护的集成允许你直接透视另一个 Microsoft Identity 安全产品。</span><span class="sxs-lookup"><span data-stu-id="4c27e-165">The integration with Azure Advanced Threat Protection allows you to pivot directly into another Microsoft Identity security product.</span></span> <span data-ttu-id="4c27e-166">Azure 高级威胁防护通过有关可疑遭到入侵的帐户和相关资源的更多见解来扩大调查。</span><span class="sxs-lookup"><span data-stu-id="4c27e-166">Azure Advanced Threat Protection augments an investigation with additional insights about a suspected compromised account and related resources.</span></span> <span data-ttu-id="4c27e-167">通过启用此功能，你将通过从标识的角度透视网络来丰富基于设备的调查功能。</span><span class="sxs-lookup"><span data-stu-id="4c27e-167">By enabling this feature, you'll enrich the device-based investigation capability by pivoting across the network from an identify point of view.</span></span>

> [!NOTE]
> <span data-ttu-id="4c27e-168">你需要具有相应的许可证才能启用此功能。</span><span class="sxs-lookup"><span data-stu-id="4c27e-168">You'll need to have the appropriate license to enable this feature.</span></span>

## <a name="office-365-threat-intelligence-connection"></a><span data-ttu-id="4c27e-169">Office 365 威胁智能连接</span><span class="sxs-lookup"><span data-stu-id="4c27e-169">Office 365 Threat Intelligence connection</span></span>

<span data-ttu-id="4c27e-170">此功能仅在有活动的 Office 365 E5 或威胁智能加载项时可用。</span><span class="sxs-lookup"><span data-stu-id="4c27e-170">This feature is only available if you have an active Office 365 E5 or the Threat Intelligence add-on.</span></span> <span data-ttu-id="4c27e-171">有关详细信息，请参阅 Office 365 企业版 E5 产品页面。</span><span class="sxs-lookup"><span data-stu-id="4c27e-171">For more information, see the Office 365 Enterprise E5 product page.</span></span>

<span data-ttu-id="4c27e-172">启用此功能后，你将能够将 Office 365 高级威胁防护的数据合并到 Microsoft Defender 安全中心，以跨 Office 365 邮箱和 Windows 设备进行全面的安全调查。</span><span class="sxs-lookup"><span data-stu-id="4c27e-172">When you turn this feature on, you'll be able to incorporate data from Office 365 Advanced Threat Protection into Microsoft Defender Security Center to conduct a comprehensive security investigation across Office 365 mailboxes and Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="4c27e-173">你需要具有相应的许可证才能启用此功能。</span><span class="sxs-lookup"><span data-stu-id="4c27e-173">You'll need to have the appropriate license to enable this feature.</span></span>

<span data-ttu-id="4c27e-174">若要在 Office 365 威胁智能中接收上下文设备集成，你需要在安全与合规中心仪表板中启用适用于终结点& Defender。</span><span class="sxs-lookup"><span data-stu-id="4c27e-174">To receive contextual device integration in Office 365 Threat Intelligence, you'll need to enable the Defender for Endpoint settings in the Security & Compliance dashboard.</span></span> <span data-ttu-id="4c27e-175">有关详细信息，请参阅威胁 [调查和响应](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-ti)。</span><span class="sxs-lookup"><span data-stu-id="4c27e-175">For more information, see [Threat investigation and response](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-ti).</span></span>

## <a name="microsoft-threat-experts"></a><span data-ttu-id="4c27e-176">Microsoft 威胁专家</span><span class="sxs-lookup"><span data-stu-id="4c27e-176">Microsoft Threat Experts</span></span>

<span data-ttu-id="4c27e-177">在两个 Microsoft 威胁专家组件中，目标攻击通知一般可用。</span><span class="sxs-lookup"><span data-stu-id="4c27e-177">Out of the two Microsoft Threat Expert components, targeted attack notification is in general availability.</span></span> <span data-ttu-id="4c27e-178">专家按需功能仍处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="4c27e-178">Experts-on-demand capability is still in preview.</span></span> <span data-ttu-id="4c27e-179">只有在应用预览版且应用程序已获得批准后，才能使用专家按需功能。</span><span class="sxs-lookup"><span data-stu-id="4c27e-179">You can only use the experts-on-demand capability if you have applied for preview and your application has been approved.</span></span> <span data-ttu-id="4c27e-180">可以通过适用于终结点门户的 Defender 警报仪表板接收来自 Microsoft 威胁专家的定向攻击通知，如果已配置，可通过电子邮件接收。</span><span class="sxs-lookup"><span data-stu-id="4c27e-180">You can receive targeted attack notifications from Microsoft Threat Experts through your Defender for Endpoint portal's alerts dashboard and via email if you configure it.</span></span>

> [!NOTE]
> <span data-ttu-id="4c27e-181">适用于终结点的 Defender 中的 Microsoft 威胁专家功能随企业移动性 + 安全性 的 E5 许可证 [一起提供](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)。</span><span class="sxs-lookup"><span data-stu-id="4c27e-181">The Microsoft Threat Experts capability in Defender for Endpoint is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="4c27e-182">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4c27e-182">Microsoft Cloud App Security</span></span>

<span data-ttu-id="4c27e-183">启用此设置将 Defender for Endpoint 信号转发到 Microsoft Cloud App Security，以便更深入地了解云应用程序使用情况。</span><span class="sxs-lookup"><span data-stu-id="4c27e-183">Enabling this setting forwards Defender for Endpoint signals to Microsoft Cloud App Security to provide deeper visibility into cloud application usage.</span></span> <span data-ttu-id="4c27e-184">转发的数据存储和处理位置与 Cloud App Security 数据位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="4c27e-184">Forwarded data is stored and processed in the same location as your Cloud App Security data.</span></span>

> [!NOTE]
> <span data-ttu-id="4c27e-185">此功能将在运行 Windows 10 版本 1709 (OS 内部版本 16299.1085（具有[KB4493441](https://support.microsoft.com/help/4493441)版本）的设备上提供企业移动性[+](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)安全性的 E5) ， Windows 10 版本 1803 (OS 内部版本 17134.704（带[KB4493464](https://support.microsoft.com/help/4493464)) 、Windows 10 版本 1809 (操作系统版本 17763.379，KB4489899) 或更高版本 Windows 10 版本）。 [](https://support.microsoft.com/help/4489899)</span><span class="sxs-lookup"><span data-stu-id="4c27e-185">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)), or later Windows 10 versions.</span></span>

## <a name="azure-information-protection"></a><span data-ttu-id="4c27e-186">Azure 信息保护</span><span class="sxs-lookup"><span data-stu-id="4c27e-186">Azure Information Protection</span></span>

<span data-ttu-id="4c27e-187">打开此设置将允许信号转发到 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="4c27e-187">Turning on this setting allows signals to be forwarded to Azure Information Protection.</span></span> <span data-ttu-id="4c27e-188">它使数据所有者和管理员能够查看载入的设备上受保护的数据和设备风险分级。</span><span class="sxs-lookup"><span data-stu-id="4c27e-188">It gives data owners and administrators visibility into protected data on onboarded devices and device risk ratings.</span></span>

## <a name="microsoft-secure-score"></a><span data-ttu-id="4c27e-189">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="4c27e-189">Microsoft Secure Score</span></span>

<span data-ttu-id="4c27e-190">将 Microsoft Defender for Endpoint 信号转发到 Microsoft 365 安全中心中的 Microsoft 安全分数。</span><span class="sxs-lookup"><span data-stu-id="4c27e-190">Forwards Microsoft Defender for Endpoint signals to Microsoft Secure Score in the Microsoft 365 security center.</span></span> <span data-ttu-id="4c27e-191">打开此功能后，Microsoft 安全功能分数可了解设备的安全状态。</span><span class="sxs-lookup"><span data-stu-id="4c27e-191">Turning on this feature gives Microsoft Secure Score visibility into the device's security posture.</span></span> <span data-ttu-id="4c27e-192">转发数据的存储和处理位置与 Microsoft 安全分数数据位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="4c27e-192">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a><span data-ttu-id="4c27e-193">从 Microsoft Defender 标识门户启用适用于终结点的 Microsoft Defender 集成</span><span class="sxs-lookup"><span data-stu-id="4c27e-193">Enable the Microsoft Defender for Endpoint integration from the Microsoft Defender for Identity portal</span></span>

<span data-ttu-id="4c27e-194">若要在 Microsoft Defender for Identity 中接收上下文设备集成，你还需要在 Microsoft Defender 标识门户中启用该功能。</span><span class="sxs-lookup"><span data-stu-id="4c27e-194">To receive contextual device integration in Microsoft Defender for Identity, you'll also need to enable the feature in the Microsoft Defender for Identity portal.</span></span>

1. <span data-ttu-id="4c27e-195">使用全局管理员或安全管理员角色登录到 [Microsoft Defender for Identity](https://portal.atp.azure.com/) 门户。</span><span class="sxs-lookup"><span data-stu-id="4c27e-195">Log in to the [Microsoft Defender for Identity portal](https://portal.atp.azure.com/) with a Global Administrator or Security Administrator role.</span></span>

2. <span data-ttu-id="4c27e-196">单击 **"创建实例"。**</span><span class="sxs-lookup"><span data-stu-id="4c27e-196">Click **Create your instance**.</span></span>

3. <span data-ttu-id="4c27e-197">将"集成"设置切换 **为"打开"，** 然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="4c27e-197">Toggle the Integration setting to **On** and click **Save**.</span></span>

<span data-ttu-id="4c27e-198">在两个门户上完成集成步骤后，你将能够查看设备详细信息或用户详细信息页面中的相关警报。</span><span class="sxs-lookup"><span data-stu-id="4c27e-198">After completing the integration steps on both portals, you'll be able to see relevant alerts in the device details or user details page.</span></span>

## <a name="microsoft-intune-connection"></a><span data-ttu-id="4c27e-199">Microsoft Intune 连接</span><span class="sxs-lookup"><span data-stu-id="4c27e-199">Microsoft Intune connection</span></span>

<span data-ttu-id="4c27e-200">Defender for Endpoint 可以与 [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) 集成 [，以启用基于设备风险的条件访问](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="4c27e-200">Defender for Endpoint can be integrated with [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) to [enable device risk-based conditional access](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span> <span data-ttu-id="4c27e-201">当你 [启用此功能时](configure-conditional-access.md)，你将能够与 Intune 共享 Defender for Endpoint 设备信息，从而增强策略实施。</span><span class="sxs-lookup"><span data-stu-id="4c27e-201">When you [turn on this feature](configure-conditional-access.md), you'll be able to share Defender for Endpoint device information with Intune, enhancing policy enforcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c27e-202">你需要在 Intune 和 Defender for Endpoint 上启用集成才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="4c27e-202">You'll need to enable the integration on both Intune and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="4c27e-203">有关特定步骤详细信息，请参阅在 [Defender for Endpoint 中配置条件访问](configure-conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4c27e-203">For more information on specific steps, see [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).</span></span>

<span data-ttu-id="4c27e-204">此功能仅在具有以下功能时可用：</span><span class="sxs-lookup"><span data-stu-id="4c27e-204">This feature is only available if you have the following:</span></span>

- <span data-ttu-id="4c27e-205">企业移动性 + 安全性 E3、Windows E5 (或 Microsoft 365 企业版 E5) </span><span class="sxs-lookup"><span data-stu-id="4c27e-205">A licensed tenant for Enterprise Mobility + Security E3, and Windows E5 (or Microsoft 365 Enterprise E5)</span></span>
- <span data-ttu-id="4c27e-206">一个活动的 Microsoft Intune 环境，与加入 Azure AD 的 Intune 托管的 Windows 10 [设备一起](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/)。</span><span class="sxs-lookup"><span data-stu-id="4c27e-206">An active Microsoft Intune environment, with Intune-managed Windows 10 devices [Azure AD-joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/).</span></span>

### <a name="conditional-access-policy"></a><span data-ttu-id="4c27e-207">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="4c27e-207">Conditional Access policy</span></span>

<span data-ttu-id="4c27e-208">启用 Intune 集成后，Intune 将自动创建经典条件访问 (CA) 策略。</span><span class="sxs-lookup"><span data-stu-id="4c27e-208">When you enable Intune integration, Intune will automatically create a classic Conditional Access (CA) policy.</span></span> <span data-ttu-id="4c27e-209">此经典 CA 策略是设置到 Intune 的状态报告的先决条件。</span><span class="sxs-lookup"><span data-stu-id="4c27e-209">This classic CA policy is a prerequisite for setting up status reports to Intune.</span></span> <span data-ttu-id="4c27e-210">不应删除它。</span><span class="sxs-lookup"><span data-stu-id="4c27e-210">It should not be deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="4c27e-211">Intune 创建的经典 CA 策略与用于配置[](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/)终结点的新式条件访问策略不同。</span><span class="sxs-lookup"><span data-stu-id="4c27e-211">The classic CA policy created by Intune is distinct from modern [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/), which are used for configuring endpoints.</span></span>

## <a name="preview-features"></a><span data-ttu-id="4c27e-212">预览功能</span><span class="sxs-lookup"><span data-stu-id="4c27e-212">Preview features</span></span>

<span data-ttu-id="4c27e-213">了解 Defender for Endpoint 预览版中的新功能，并首先通过打开预览体验来试用即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="4c27e-213">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="4c27e-214">你将有权访问即将推出的功能，你可以提供反馈，以帮助在功能全面可用之前改进整体体验。</span><span class="sxs-lookup"><span data-stu-id="4c27e-214">You'll have access to upcoming features, which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a><span data-ttu-id="4c27e-215">与 Microsoft 合规中心共享终结点警报</span><span class="sxs-lookup"><span data-stu-id="4c27e-215">Share endpoint alerts with Microsoft Compliance Center</span></span>

<span data-ttu-id="4c27e-216">将终结点安全警报及其会审状态转发到 Microsoft 合规中心，从而通过警报增强内部风险管理策略，并修正内部风险，然后再造成危害。</span><span class="sxs-lookup"><span data-stu-id="4c27e-216">Forwards endpoint security alerts and their triage status to Microsoft Compliance Center, allowing you to enhance insider risk management policies with alerts and remediate internal risks before they cause harm.</span></span> <span data-ttu-id="4c27e-217">转发的数据将处理并存储在与 Office 365 数据相同的位置。</span><span class="sxs-lookup"><span data-stu-id="4c27e-217">Forwarded data is processed and stored in the same location as your Office 365 data.</span></span>

<span data-ttu-id="4c27e-218">在内部风险管理 [设置中](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-settings.md#indicators) 配置安全策略违反指示器后，适用于终结点的 Defender 警报将共享与适用用户的内部风险管理。</span><span class="sxs-lookup"><span data-stu-id="4c27e-218">After configuring the [Security policy violation indicators](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-settings.md#indicators) in the insider risk management settings, Defender for Endpoint alerts will be shared with insider risk management for applicable users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4c27e-219">相关主题</span><span class="sxs-lookup"><span data-stu-id="4c27e-219">Related topics</span></span>

- [<span data-ttu-id="4c27e-220">更新数据保留设置</span><span class="sxs-lookup"><span data-stu-id="4c27e-220">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="4c27e-221">配置警报通知</span><span class="sxs-lookup"><span data-stu-id="4c27e-221">Configure alert notifications</span></span>](configure-email-notifications.md)
