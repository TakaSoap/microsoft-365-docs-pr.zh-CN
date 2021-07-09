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
ms.openlocfilehash: 2448b95e5c5c5da25a916b659f6b49d04ba8f0c1
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339570"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a><span data-ttu-id="ab533-104">在 Defender for Endpoint 中配置高级功能</span><span class="sxs-lookup"><span data-stu-id="ab533-104">Configure advanced features in Defender for Endpoint</span></span>

<span data-ttu-id="ab533-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ab533-105">**Applies to:**</span></span>
- [<span data-ttu-id="ab533-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ab533-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ab533-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab533-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> <span data-ttu-id="ab533-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="ab533-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ab533-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ab533-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="ab533-110">根据你使用的 Microsoft 安全产品，某些高级功能可能可供你集成 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="ab533-110">Depending on the Microsoft security products that you use, some advanced features might be available for you to integrate Defender for Endpoint with.</span></span>

## <a name="enable-advanced-features"></a><span data-ttu-id="ab533-111">启用高级功能</span><span class="sxs-lookup"><span data-stu-id="ab533-111">Enable advanced features</span></span>

1. <span data-ttu-id="ab533-112">在导航窗格中，选择 **首选项设置**  >  **高级功能**。</span><span class="sxs-lookup"><span data-stu-id="ab533-112">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="ab533-113">选择要配置的高级功能，并切换 **开和\*\*\*\*关之间的设置**。</span><span class="sxs-lookup"><span data-stu-id="ab533-113">Select the advanced feature you want to configure and toggle the setting between **On** and **Off**.</span></span>
3. <span data-ttu-id="ab533-114">单击 **保存首选项**。</span><span class="sxs-lookup"><span data-stu-id="ab533-114">Click **Save preferences**.</span></span>

<span data-ttu-id="ab533-115">使用以下高级功能可以更好地防范潜在恶意文件，并获取安全调查期间更好的见解。</span><span class="sxs-lookup"><span data-stu-id="ab533-115">Use the following advanced features to get better protected from potentially malicious files and gain better insight during security investigations.</span></span>

## <a name="automated-investigation"></a><span data-ttu-id="ab533-116">自动调查</span><span class="sxs-lookup"><span data-stu-id="ab533-116">Automated investigation</span></span>

<span data-ttu-id="ab533-117">启用此功能以利用服务的自动调查和修正功能。</span><span class="sxs-lookup"><span data-stu-id="ab533-117">Turn on this feature to take advantage of the automated investigation and remediation features of the service.</span></span> <span data-ttu-id="ab533-118">有关详细信息，请参阅自动 [调查](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="ab533-118">For more information, see [Automated investigation](automated-investigations.md).</span></span>

## <a name="live-response"></a><span data-ttu-id="ab533-119">实时响应</span><span class="sxs-lookup"><span data-stu-id="ab533-119">Live response</span></span>

<span data-ttu-id="ab533-120">启用此功能，以便具有相应权限的用户可以在设备上启动实时响应会话。</span><span class="sxs-lookup"><span data-stu-id="ab533-120">Turn on this feature so that users with the appropriate permissions can start a live response session on devices.</span></span>

<span data-ttu-id="ab533-121">有关角色分配详细信息，请参阅创建 [和管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ab533-121">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>

## <a name="live-response-for-servers"></a><span data-ttu-id="ab533-122">服务器实时响应</span><span class="sxs-lookup"><span data-stu-id="ab533-122">Live response for servers</span></span>
<span data-ttu-id="ab533-123">启用此功能，以便具有适当权限的用户可以启动服务器上实时响应会话。</span><span class="sxs-lookup"><span data-stu-id="ab533-123">Turn on this feature so that users with the appropriate permissions can start a live response session on servers.</span></span>

<span data-ttu-id="ab533-124">有关角色分配详细信息，请参阅创建 [和管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ab533-124">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>


## <a name="live-response-unsigned-script-execution"></a><span data-ttu-id="ab533-125">实时响应未签名脚本执行</span><span class="sxs-lookup"><span data-stu-id="ab533-125">Live response unsigned script execution</span></span>

<span data-ttu-id="ab533-126">启用此功能后，您可以在实时响应会话中运行未签名的脚本。</span><span class="sxs-lookup"><span data-stu-id="ab533-126">Enabling this feature allows you to run unsigned scripts in a live response session.</span></span>

## <a name="always-remediate-pua"></a><span data-ttu-id="ab533-127">始终修正 PUA</span><span class="sxs-lookup"><span data-stu-id="ab533-127">Always remediate PUA</span></span>
<span data-ttu-id="ab533-128">可能不需要的应用程序 （PUA） 是一类软件，会导致计算机运行缓慢、显示意外广告或最糟情况，安装其他可能意外或不需要的软件。</span><span class="sxs-lookup"><span data-stu-id="ab533-128">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software which might be unexpected or unwanted.</span></span> 

<span data-ttu-id="ab533-129">启用此功能，以便 (PUA) 在租户的所有设备上修正可能不需要的应用程序，即使未在设备上配置 PUA 保护。</span><span class="sxs-lookup"><span data-stu-id="ab533-129">Turn on this feature so that potentially unwanted applications (PUA) are remediated on all devices in your tenant even if PUA protection is not configured on the devices.</span></span> <span data-ttu-id="ab533-130">这有助于防止用户无意中在设备上安装不需要的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ab533-130">This will help protect users from inadvertently installing unwanted applications on their device.</span></span> <span data-ttu-id="ab533-131">关闭后，修正取决于设备配置。</span><span class="sxs-lookup"><span data-stu-id="ab533-131">When turned off, remediation is dependent on the device configuration.</span></span> 


## <a name="restrict-correlation-to-within-scoped-device-groups"></a><span data-ttu-id="ab533-132">限制与作用域内设备组之间的关联</span><span class="sxs-lookup"><span data-stu-id="ab533-132">Restrict correlation to within scoped device groups</span></span>
<span data-ttu-id="ab533-133">此配置可用于本地 SOC 操作希望仅将警报关联限制为可以访问的设备组的方案。</span><span class="sxs-lookup"><span data-stu-id="ab533-133">This configuration can be used for scenarios where local SOC operations would like to limit alert correlations only to device groups that they can access.</span></span> <span data-ttu-id="ab533-134">打开此设置后，由跨设备组的警报组成的事件将不再被视为单个事件。</span><span class="sxs-lookup"><span data-stu-id="ab533-134">By turning this setting on, an incident composed of alerts that cross device groups will no longer be considered a single incident.</span></span> <span data-ttu-id="ab533-135">然后，本地 SOC 可以针对事件采取措施，因为他们可以访问涉及的设备组之一。</span><span class="sxs-lookup"><span data-stu-id="ab533-135">The local SOC can then take action on the incident because they have access to one of the device groups involved.</span></span> <span data-ttu-id="ab533-136">但是，全局 SOC 将按设备组而不是一个事件查看多个不同的事件。</span><span class="sxs-lookup"><span data-stu-id="ab533-136">However, global SOC will see several different incidents by device group instead of one incident.</span></span> <span data-ttu-id="ab533-137">建议不要打开此设置，除非这样做超出了整个组织中事件相关性的好处</span><span class="sxs-lookup"><span data-stu-id="ab533-137">We do not recommend turning this setting on unless doing so outweighs the benefits of incident correlation across the entire organization</span></span>
>[!NOTE]
><span data-ttu-id="ab533-138">更改此设置仅影响未来的警报关联。</span><span class="sxs-lookup"><span data-stu-id="ab533-138">Changing this setting impacts future alert correlations only.</span></span>

## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="ab533-139">启用EDR阻止模式</span><span class="sxs-lookup"><span data-stu-id="ab533-139">Enable EDR in block mode</span></span>
<span data-ttu-id="ab533-140">终结点检测和响应 (EDR) 在阻止模式下提供对恶意项目的保护，即使 Microsoft Defender 防病毒处于被动模式时。</span><span class="sxs-lookup"><span data-stu-id="ab533-140">Endpoint detection and response (EDR) in block mode provides protection from malicious artifacts, even when Microsoft Defender Antivirus is running in passive mode.</span></span> <span data-ttu-id="ab533-141">打开后，EDR模式阻止在设备上检测到的恶意项目或行为。</span><span class="sxs-lookup"><span data-stu-id="ab533-141">When turned on, EDR in block mode blocks malicious artifacts or behaviors that are detected on a device.</span></span> <span data-ttu-id="ab533-142">EDR阻止模式在后台工作，以修正在泄露后检测到的恶意项目。</span><span class="sxs-lookup"><span data-stu-id="ab533-142">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post breach.</span></span>


## <a name="autoresolve-remediated-alerts"></a><span data-ttu-id="ab533-143">Autoresolve 修正警报</span><span class="sxs-lookup"><span data-stu-id="ab533-143">Autoresolve remediated alerts</span></span>

<span data-ttu-id="ab533-144">对于在 Windows 10 版本 1809 或之后创建的租户，自动调查和修正功能默认配置为解决自动分析结果状态为"未找到威胁"或"已修正"的警报。</span><span class="sxs-lookup"><span data-stu-id="ab533-144">For tenants created on or after Windows 10, version 1809, the automated investigation and remediation capability is configured by default to resolve alerts where the automated analysis result status is "No threats found" or "Remediated".</span></span>  <span data-ttu-id="ab533-145">如果不希望自动解决警报，需要手动关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="ab533-145">If you don't want to have alerts auto-resolved, you'll need to manually turn off the feature.</span></span>

> [!TIP]
> <span data-ttu-id="ab533-146">对于在此版本之前创建的租户，你需要从高级功能页面手动 [启用](https://securitycenter.windows.com/preferences2/integration) 此功能。</span><span class="sxs-lookup"><span data-stu-id="ab533-146">For tenants created prior to that version, you'll need to manually turn this feature on from the [Advanced features](https://securitycenter.windows.com/preferences2/integration) page.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="ab533-147">自动解决操作的结果可能会影响基于设备上找到的活动警报的设备风险级别计算。</span><span class="sxs-lookup"><span data-stu-id="ab533-147">The result of the auto-resolve action may influence the Device risk level calculation which is based on the active alerts found on a device.</span></span>
> - <span data-ttu-id="ab533-148">如果安全操作分析师手动将警报状态设置为"正在进行"或"已解决"，则自动解决功能不会覆盖它。</span><span class="sxs-lookup"><span data-stu-id="ab533-148">If a security operations analyst manually sets the status of an alert to "In progress" or "Resolved" the auto-resolve capability will not overwrite it.</span></span>

## <a name="allow-or-block-file"></a><span data-ttu-id="ab533-149">允许或阻止文件</span><span class="sxs-lookup"><span data-stu-id="ab533-149">Allow or block file</span></span>

<span data-ttu-id="ab533-150">仅在组织满足以下要求时，阻止才可用：</span><span class="sxs-lookup"><span data-stu-id="ab533-150">Blocking is only available if your organization fulfills these requirements:</span></span>

- <span data-ttu-id="ab533-151">使用 Microsoft Defender 防病毒 作为活动的反恶意软件解决方案，</span><span class="sxs-lookup"><span data-stu-id="ab533-151">Uses Microsoft Defender Antivirus as the active antimalware solution and,</span></span>
- <span data-ttu-id="ab533-152">启用基于云的保护功能</span><span class="sxs-lookup"><span data-stu-id="ab533-152">The cloud-based protection feature is enabled</span></span>

<span data-ttu-id="ab533-153">此功能使你能够阻止网络中潜在的恶意文件。</span><span class="sxs-lookup"><span data-stu-id="ab533-153">This feature enables you to block potentially malicious files in your network.</span></span> <span data-ttu-id="ab533-154">阻止文件将阻止在组织的设备上读取、写入或执行文件。</span><span class="sxs-lookup"><span data-stu-id="ab533-154">Blocking a file will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="ab533-155">若要打开 **"允许"或"阻止** 文件"：：</span><span class="sxs-lookup"><span data-stu-id="ab533-155">To turn **Allow or block** files on:</span></span>

1. <span data-ttu-id="ab533-156">在导航窗格中，选择"设置  >    >  **终结点常规**  >  **高级功能**  >  **允许或阻止文件"。**</span><span class="sxs-lookup"><span data-stu-id="ab533-156">In the navigation pane, select **Settings** > **Endpoints** > **General** > **Advanced features** > **Allow or block file**.</span></span>

1. <span data-ttu-id="ab533-157">切换开和 **关\*\*\*\*之间的设置**。</span><span class="sxs-lookup"><span data-stu-id="ab533-157">Toggle the setting between **On** and **Off**.</span></span>

    ![阻止文件功能的高级设置的图像](images/atp-preferences-setup.png)

1. <span data-ttu-id="ab533-159">选择 **页面底部的** "保存首选项"。</span><span class="sxs-lookup"><span data-stu-id="ab533-159">Select **Save preferences** at the bottom of the page.</span></span>

<span data-ttu-id="ab533-160">启用此功能后，可以通过文件 [配置文件](respond-file-alerts.md#allow-or-block-file) 页上的 **"添加** 指示器"选项卡阻止文件。</span><span class="sxs-lookup"><span data-stu-id="ab533-160">After turning on this feature, you can [block files](respond-file-alerts.md#allow-or-block-file) via the **Add Indicator** tab on a file's profile page.</span></span>

## <a name="custom-network-indicators"></a><span data-ttu-id="ab533-161">自定义网络指示器</span><span class="sxs-lookup"><span data-stu-id="ab533-161">Custom network indicators</span></span>

<span data-ttu-id="ab533-162">启用此功能后，您可以创建 IP 地址、域或 URL 的指示器，这些指示器根据自定义指示器列表确定是否允许或阻止它们。</span><span class="sxs-lookup"><span data-stu-id="ab533-162">Turning on this feature allows you to create indicators for IP addresses, domains, or URLs, which determine whether they will be allowed or blocked based on your custom indicator list.</span></span>

<span data-ttu-id="ab533-163">若要使用此功能，设备必须运行Windows 10版本 1709 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ab533-163">To use this feature, devices must be running Windows 10 version 1709 or later.</span></span> <span data-ttu-id="ab533-164">它们还应具有阻止模式和反恶意软件平台版本 4.18.1906.3 或更高版本的网络保护，请参阅[KB 4052623。](https://go.microsoft.com/fwlink/?linkid=2099834)</span><span class="sxs-lookup"><span data-stu-id="ab533-164">They should also have network protection in block mode and version 4.18.1906.3 or later of the antimalware platform [see KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).</span></span>

<span data-ttu-id="ab533-165">有关详细信息，请参阅管理 [指示器](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="ab533-165">For more information, see [Manage indicators](manage-indicators.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ab533-166">网络保护利用信誉服务，在可能超出你为 Defender for Endpoint 数据选择的位置之外的位置处理请求。</span><span class="sxs-lookup"><span data-stu-id="ab533-166">Network protection leverages reputation services that process requests in locations that might be outside of the location you have selected for your Defender for Endpoint data.</span></span>

## <a name="tamper-protection"></a><span data-ttu-id="ab533-167">防篡改保护</span><span class="sxs-lookup"><span data-stu-id="ab533-167">Tamper protection</span></span>
<span data-ttu-id="ab533-168">在某些类型的网络攻击期间，不良参与者会尝试在你的计算机上禁用安全功能，如防病毒保护。</span><span class="sxs-lookup"><span data-stu-id="ab533-168">During some kinds of cyber attacks, bad actors try to disable security features, such as anti-virus protection, on your machines.</span></span> <span data-ttu-id="ab533-169">不良操作者希望禁用安全功能，以便更轻松地访问数据、安装恶意软件，或者以其他方式利用你的数据、标识和设备。</span><span class="sxs-lookup"><span data-stu-id="ab533-169">Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.</span></span>

<span data-ttu-id="ab533-170">防篡改保护实质上Microsoft Defender 防病毒并阻止通过应用和方法更改安全设置。</span><span class="sxs-lookup"><span data-stu-id="ab533-170">Tamper protection essentially locks Microsoft Defender Antivirus and prevents your security settings from being changed through apps and methods.</span></span>

<span data-ttu-id="ab533-171">如果你的组织使用基于云的保护Microsoft Defender 防病毒启用基于云的保护，则此功能可用。</span><span class="sxs-lookup"><span data-stu-id="ab533-171">This feature is available if your organization uses Microsoft Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="ab533-172">有关详细信息，请参阅通过云保护在 Microsoft Defender 防病毒[中使用下一代技术](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="ab533-172">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="ab533-173">保持防篡改功能打开，以防止对安全解决方案及其基本功能进行不必要的更改。</span><span class="sxs-lookup"><span data-stu-id="ab533-173">Keep tamper protection turned on to prevent unwanted changes to your security solution and its essential features.</span></span>


## <a name="show-user-details"></a><span data-ttu-id="ab533-174">显示用户详细信息</span><span class="sxs-lookup"><span data-stu-id="ab533-174">Show user details</span></span>

<span data-ttu-id="ab533-175">启用此功能，以便你可以查看存储在Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="ab533-175">Turn on this feature so that you can see user details stored in Azure Active Directory.</span></span> <span data-ttu-id="ab533-176">详细信息包括调查用户帐户实体时的用户图片、姓名、职务和部门信息。</span><span class="sxs-lookup"><span data-stu-id="ab533-176">Details include a user's picture, name, title, and department information  when investigating user account entities.</span></span> <span data-ttu-id="ab533-177">您可以在以下视图中找到用户帐户信息：</span><span class="sxs-lookup"><span data-stu-id="ab533-177">You can find user account information in the following views:</span></span>

- <span data-ttu-id="ab533-178">安全操作仪表板</span><span class="sxs-lookup"><span data-stu-id="ab533-178">Security operations dashboard</span></span>
- <span data-ttu-id="ab533-179">警报队列</span><span class="sxs-lookup"><span data-stu-id="ab533-179">Alert queue</span></span>
- <span data-ttu-id="ab533-180">设备详细信息页面</span><span class="sxs-lookup"><span data-stu-id="ab533-180">Device details page</span></span>

<span data-ttu-id="ab533-181">有关详细信息，请参阅 [调查用户帐户](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="ab533-181">For more information, see [Investigate a user account](investigate-user.md).</span></span>


## <a name="skype-for-business-integration"></a><span data-ttu-id="ab533-182">Skype for Business 集成</span><span class="sxs-lookup"><span data-stu-id="ab533-182">Skype for Business integration</span></span>

<span data-ttu-id="ab533-183">通过Skype for Business集成，可以使用电子邮件、电子邮件或Skype for Business与用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="ab533-183">Enabling the Skype for Business integration gives you the ability to communicate with users using Skype for Business, email, or phone.</span></span> <span data-ttu-id="ab533-184">当你需要与用户通信并降低风险时，这很方便。</span><span class="sxs-lookup"><span data-stu-id="ab533-184">This can be handy when you need to communicate with the user and mitigate risks.</span></span>

> [!NOTE]
> <span data-ttu-id="ab533-185">当设备与网络隔离时，有一个弹出窗口，你可以选择启用 Outlook 和 Skype 通信，这将允许用户在断开与网络的连接时与其通信。</span><span class="sxs-lookup"><span data-stu-id="ab533-185">When a device is being isolated from the network, there's a pop-up where you can choose to enable Outlook and Skype communications which allows communications to the user while they are disconnected from the network.</span></span> <span data-ttu-id="ab533-186">此设置适用于设备在Skype Outlook时的通信和通信。</span><span class="sxs-lookup"><span data-stu-id="ab533-186">This setting applies to Skype and Outlook communication when devices are in isolation mode.</span></span>

## <a name="microsoft-defender-for-identity-integration"></a><span data-ttu-id="ab533-187">Microsoft Defender for Identity 集成</span><span class="sxs-lookup"><span data-stu-id="ab533-187">Microsoft Defender for Identity integration</span></span>

<span data-ttu-id="ab533-188">与 Microsoft Defender for Identity 的集成允许你直接透视另一个 Microsoft Identity 安全产品。</span><span class="sxs-lookup"><span data-stu-id="ab533-188">The integration with Microsoft Defender for Identity allows you to pivot directly into another Microsoft Identity security product.</span></span> <span data-ttu-id="ab533-189">Microsoft Defender for Identity 通过有关可疑遭到入侵的帐户和相关资源的其他见解来扩大调查。</span><span class="sxs-lookup"><span data-stu-id="ab533-189">Microsoft Defender for Identity augments an investigation with additional insights about a suspected compromised account and related resources.</span></span> <span data-ttu-id="ab533-190">通过启用此功能，你将通过从标识的角度透视网络来丰富基于设备的调查功能。</span><span class="sxs-lookup"><span data-stu-id="ab533-190">By enabling this feature, you'll enrich the device-based investigation capability by pivoting across the network from an identify point of view.</span></span>

> [!NOTE]
> <span data-ttu-id="ab533-191">你需要具有相应的许可证才能启用此功能。</span><span class="sxs-lookup"><span data-stu-id="ab533-191">You'll need to have the appropriate license to enable this feature.</span></span>

## <a name="office-365-threat-intelligence-connection"></a><span data-ttu-id="ab533-192">Office 365威胁智能连接</span><span class="sxs-lookup"><span data-stu-id="ab533-192">Office 365 Threat Intelligence connection</span></span>

<span data-ttu-id="ab533-193">此功能仅在你拥有活动Office 365 E5或威胁智能加载项时可用。</span><span class="sxs-lookup"><span data-stu-id="ab533-193">This feature is only available if you have an active Office 365 E5 or the Threat Intelligence add-on.</span></span> <span data-ttu-id="ab533-194">有关详细信息，请参阅 Office 365 企业版 E5 产品页。</span><span class="sxs-lookup"><span data-stu-id="ab533-194">For more information, see the Office 365 Enterprise E5 product page.</span></span>

<span data-ttu-id="ab533-195">启用此功能后，你将能够将 Microsoft Defender for Office 365 数据合并到 Microsoft 365 Defender 中，以便跨 Office 365 邮箱和 Windows 设备进行全面安全调查。</span><span class="sxs-lookup"><span data-stu-id="ab533-195">When you turn this feature on, you'll be able to incorporate data from Microsoft Defender for Office 365 into Microsoft 365 Defender to conduct a comprehensive security investigation across Office 365 mailboxes and Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="ab533-196">你需要具有相应的许可证才能启用此功能。</span><span class="sxs-lookup"><span data-stu-id="ab533-196">You'll need to have the appropriate license to enable this feature.</span></span>

<span data-ttu-id="ab533-197">若要在威胁情报Office 365上下文设备集成，你需要在安全与合规中心仪表板中启用 Defender for Endpoint &设置。</span><span class="sxs-lookup"><span data-stu-id="ab533-197">To receive contextual device integration in Office 365 Threat Intelligence, you'll need to enable the Defender for Endpoint settings in the Security & Compliance dashboard.</span></span> <span data-ttu-id="ab533-198">有关详细信息，请参阅威胁 [调查和响应](/microsoft-365/security/office-365-security/office-365-ti)。</span><span class="sxs-lookup"><span data-stu-id="ab533-198">For more information, see [Threat investigation and response](/microsoft-365/security/office-365-security/office-365-ti).</span></span>

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a><span data-ttu-id="ab533-199">Microsoft 威胁专家 - 目标攻击通知</span><span class="sxs-lookup"><span data-stu-id="ab533-199">Microsoft Threat Experts - Targeted Attack Notifications</span></span>

<span data-ttu-id="ab533-200">在两个 Microsoft 威胁专家组件中，目标攻击通知一般可用。</span><span class="sxs-lookup"><span data-stu-id="ab533-200">Out of the two Microsoft Threat Expert components, targeted attack notification is in general availability.</span></span> <span data-ttu-id="ab533-201">专家按需功能仍处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="ab533-201">Experts-on-demand capability is still in preview.</span></span> <span data-ttu-id="ab533-202">只有在应用预览版且应用程序已获得批准后，才能使用专家按需功能。</span><span class="sxs-lookup"><span data-stu-id="ab533-202">You can only use the experts-on-demand capability if you have applied for preview and your application has been approved.</span></span> <span data-ttu-id="ab533-203">可以通过 Defender for Endpoint 门户的警报仪表板Microsoft 威胁专家接收来自你的终结点门户的定向攻击通知（如果已配置的话）。</span><span class="sxs-lookup"><span data-stu-id="ab533-203">You can receive targeted attack notifications from Microsoft Threat Experts through your Defender for Endpoint portal's alerts dashboard and via email if you configure it.</span></span>

> [!NOTE]
> <span data-ttu-id="ab533-204">Defender for Endpoint 中的 Microsoft 威胁专家 功能随适用于 企业移动性 + 安全性 的 E5[许可证一企业移动性 + 安全性。](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)</span><span class="sxs-lookup"><span data-stu-id="ab533-204">The Microsoft Threat Experts capability in Defender for Endpoint is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).</span></span>
## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="ab533-205">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ab533-205">Microsoft Cloud App Security</span></span>

<span data-ttu-id="ab533-206">启用此设置将 Defender for Endpoint 信号转发到Microsoft Cloud App Security深入了解云应用程序使用情况。</span><span class="sxs-lookup"><span data-stu-id="ab533-206">Enabling this setting forwards Defender for Endpoint signals to Microsoft Cloud App Security to provide deeper visibility into cloud application usage.</span></span> <span data-ttu-id="ab533-207">转发数据的存储和处理位置与转发数据云应用安全位置。</span><span class="sxs-lookup"><span data-stu-id="ab533-207">Forwarded data is stored and processed in the same location as your Cloud App Security data.</span></span>

> [!NOTE]
> <span data-ttu-id="ab533-208">在运行 Windows 10 版本 1709 (OS 内部版本 16299.1085（具有[KB4493441](https://support.microsoft.com/help/4493441)版本）的设备上，此功能将随 企业移动性 + 安全性 的 E5 许可证一起) 。 Windows 10，版本 1803 (OS 内部版本 17134.704（带[KB4493464](https://support.microsoft.com/help/4493464)) 、Windows 10 版本 1809 (OS 内部版本 17763.379，KB4489899) 或更高版本 Windows 10）。 [](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) [](https://support.microsoft.com/help/4489899)</span><span class="sxs-lookup"><span data-stu-id="ab533-208">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)), or later Windows 10 versions.</span></span>

## <a name="microsoft-secure-score"></a><span data-ttu-id="ab533-209">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="ab533-209">Microsoft Secure Score</span></span>

<span data-ttu-id="ab533-210">将 Microsoft Defender for Endpoint 信号转发到安全中心中的 Microsoft Microsoft 365分数。</span><span class="sxs-lookup"><span data-stu-id="ab533-210">Forwards Microsoft Defender for Endpoint signals to Microsoft Secure Score in the Microsoft 365 security center.</span></span> <span data-ttu-id="ab533-211">打开此功能后，Microsoft 安全功能分数可了解设备的安全状态。</span><span class="sxs-lookup"><span data-stu-id="ab533-211">Turning on this feature gives Microsoft Secure Score visibility into the device's security posture.</span></span> <span data-ttu-id="ab533-212">转发数据的存储和处理位置与 Microsoft 安全分数数据位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="ab533-212">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>


### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a><span data-ttu-id="ab533-213">从 Microsoft Defender 标识门户启用适用于终结点的 Microsoft Defender 集成</span><span class="sxs-lookup"><span data-stu-id="ab533-213">Enable the Microsoft Defender for Endpoint integration from the Microsoft Defender for Identity portal</span></span>

<span data-ttu-id="ab533-214">若要在 Microsoft Defender for Identity 中接收上下文设备集成，你还需要在 Microsoft Defender 标识门户中启用该功能。</span><span class="sxs-lookup"><span data-stu-id="ab533-214">To receive contextual device integration in Microsoft Defender for Identity, you'll also need to enable the feature in the Microsoft Defender for Identity portal.</span></span>

1. <span data-ttu-id="ab533-215">使用全局管理员或安全管理员角色登录到 [Microsoft Defender for Identity](https://portal.atp.azure.com/) 门户。</span><span class="sxs-lookup"><span data-stu-id="ab533-215">Log in to the [Microsoft Defender for Identity portal](https://portal.atp.azure.com/) with a Global Administrator or Security Administrator role.</span></span>

2. <span data-ttu-id="ab533-216">单击 **"创建实例"。**</span><span class="sxs-lookup"><span data-stu-id="ab533-216">Click **Create your instance**.</span></span>

3. <span data-ttu-id="ab533-217">将"集成"设置切换 **为"打开"，** 然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="ab533-217">Toggle the Integration setting to **On** and click **Save**.</span></span>

<span data-ttu-id="ab533-218">在两个门户上完成集成步骤后，你将能够查看设备详细信息或用户详细信息页面中的相关警报。</span><span class="sxs-lookup"><span data-stu-id="ab533-218">After completing the integration steps on both portals, you'll be able to see relevant alerts in the device details or user details page.</span></span>

## <a name="web-content-filtering"></a><span data-ttu-id="ab533-219">Web 内容筛选</span><span class="sxs-lookup"><span data-stu-id="ab533-219">Web content filtering</span></span>
<span data-ttu-id="ab533-220">阻止访问包含不需要的内容的网站，并跟踪所有域中的 Web 活动。</span><span class="sxs-lookup"><span data-stu-id="ab533-220">Block access to websites containing unwanted content and track web activity across all domains.</span></span> <span data-ttu-id="ab533-221">若要指定要阻止的 Web 内容类别，请创建 [Web 内容筛选策略](https://security.microsoft.com/preferences2/web_content_filtering_policy)。</span><span class="sxs-lookup"><span data-stu-id="ab533-221">To specify the web content categories you want to block, create a [web content filtering policy](https://security.microsoft.com/preferences2/web_content_filtering_policy).</span></span> <span data-ttu-id="ab533-222">确保你在部署 Microsoft Defender for Endpoint 安全基线时具有阻止 [模式下的网络保护](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)。</span><span class="sxs-lookup"><span data-stu-id="ab533-222">Ensure you have network protection in block mode when deploying the [Microsoft Defender for Endpoint security baseline](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2).</span></span>


## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a><span data-ttu-id="ab533-223">与 Microsoft 合规中心共享终结点警报</span><span class="sxs-lookup"><span data-stu-id="ab533-223">Share endpoint alerts with Microsoft Compliance Center</span></span>
<span data-ttu-id="ab533-224">将终结点安全警报及其会审状态转发到 Microsoft 合规中心，从而通过警报增强内部风险管理策略，并修正内部风险，然后再造成危害。</span><span class="sxs-lookup"><span data-stu-id="ab533-224">Forwards endpoint security alerts and their triage status to Microsoft Compliance Center, allowing you to enhance insider risk management policies with alerts and remediate internal risks before they cause harm.</span></span> <span data-ttu-id="ab533-225">转发的数据将处理并存储在与传输数据相同的Office 365位置。</span><span class="sxs-lookup"><span data-stu-id="ab533-225">Forwarded data is processed and stored in the same location as your Office 365 data.</span></span>

<span data-ttu-id="ab533-226">在内部风险管理 [设置中](/microsoft-365/compliance/insider-risk-management-settings#indicators) 配置安全策略违反指示器后，适用于终结点的 Defender 警报将共享与适用用户的内部风险管理。</span><span class="sxs-lookup"><span data-stu-id="ab533-226">After configuring the [Security policy violation indicators](/microsoft-365/compliance/insider-risk-management-settings#indicators) in the insider risk management settings, Defender for Endpoint alerts will be shared with insider risk management for applicable users.</span></span>



## <a name="microsoft-intune-connection"></a><span data-ttu-id="ab533-227">Microsoft Intune连接</span><span class="sxs-lookup"><span data-stu-id="ab533-227">Microsoft Intune connection</span></span>

<span data-ttu-id="ab533-228">Defender for Endpoint 可以[](/intune/what-is-intune)与 Microsoft Intune[集成，以启用基于设备风险的条件访问](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="ab533-228">Defender for Endpoint can be integrated with [Microsoft Intune](/intune/what-is-intune) to [enable device risk-based conditional access](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span> <span data-ttu-id="ab533-229">当你 [启用此功能时](configure-conditional-access.md)，你将能够与 Intune 共享 Defender for Endpoint 设备信息，从而增强策略实施。</span><span class="sxs-lookup"><span data-stu-id="ab533-229">When you [turn on this feature](configure-conditional-access.md), you'll be able to share Defender for Endpoint device information with Intune, enhancing policy enforcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab533-230">你需要在 Intune 和 Defender for Endpoint 上启用集成才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="ab533-230">You'll need to enable the integration on both Intune and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="ab533-231">有关特定步骤详细信息，请参阅在 [Defender for Endpoint 中配置条件访问](configure-conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ab533-231">For more information on specific steps, see [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).</span></span>

<span data-ttu-id="ab533-232">此功能仅在具有以下功能时可用：</span><span class="sxs-lookup"><span data-stu-id="ab533-232">This feature is only available if you have the following:</span></span>

- <span data-ttu-id="ab533-233">适用于 E5 企业移动性 + 安全性 E3或 Windows E5 (或 Microsoft 365 企业版 的许可) </span><span class="sxs-lookup"><span data-stu-id="ab533-233">A licensed tenant for Enterprise Mobility + Security E3, and Windows E5 (or Microsoft 365 Enterprise E5)</span></span>
- <span data-ttu-id="ab533-234">一个Microsoft Intune环境，与已加入 Azure AD Windows 10 [Intune 托管的设备](/azure/active-directory/devices/concept-azure-ad-join/)。</span><span class="sxs-lookup"><span data-stu-id="ab533-234">An active Microsoft Intune environment, with Intune-managed Windows 10 devices [Azure AD-joined](/azure/active-directory/devices/concept-azure-ad-join/).</span></span>


### <a name="conditional-access-policy"></a><span data-ttu-id="ab533-235">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="ab533-235">Conditional Access policy</span></span>

<span data-ttu-id="ab533-236">启用 Intune 集成后，Intune 将自动创建经典条件访问 (CA) 策略。</span><span class="sxs-lookup"><span data-stu-id="ab533-236">When you enable Intune integration, Intune will automatically create a classic Conditional Access (CA) policy.</span></span> <span data-ttu-id="ab533-237">此经典 CA 策略是设置到 Intune 的状态报告的先决条件。</span><span class="sxs-lookup"><span data-stu-id="ab533-237">This classic CA policy is a prerequisite for setting up status reports to Intune.</span></span> <span data-ttu-id="ab533-238">不应删除它。</span><span class="sxs-lookup"><span data-stu-id="ab533-238">It should not be deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="ab533-239">Intune 创建的经典 CA 策略与用于配置[](/azure/active-directory/conditional-access/overview/)终结点的新式条件访问策略不同。</span><span class="sxs-lookup"><span data-stu-id="ab533-239">The classic CA policy created by Intune is distinct from modern [Conditional Access policies](/azure/active-directory/conditional-access/overview/), which are used for configuring endpoints.</span></span>


## <a name="device-discovery"></a><span data-ttu-id="ab533-240">设备发现</span><span class="sxs-lookup"><span data-stu-id="ab533-240">Device discovery</span></span>
<span data-ttu-id="ab533-241">帮助你查找连接到公司网络的非托管设备，而无需额外的设备或繁琐的流程更改。</span><span class="sxs-lookup"><span data-stu-id="ab533-241">Helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span> <span data-ttu-id="ab533-242">使用载入的设备，可以在网络中查找非托管设备，并评估漏洞和风险。</span><span class="sxs-lookup"><span data-stu-id="ab533-242">Using onboarded devices, you can find unmanaged devices in your network and assess vulnerabilities and risks.</span></span> <span data-ttu-id="ab533-243">有关详细信息，请参阅设备 [发现](device-discovery.md)。</span><span class="sxs-lookup"><span data-stu-id="ab533-243">For more information, see [Device discovery](device-discovery.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ab533-244">你始终可以应用筛选器以从设备清单列表中排除非托管设备。</span><span class="sxs-lookup"><span data-stu-id="ab533-244">You can always apply filters to exclude unmanaged devices from the device inventory list.</span></span> <span data-ttu-id="ab533-245">您还可以使用 API 查询上的载入状态列筛选出非托管设备。</span><span class="sxs-lookup"><span data-stu-id="ab533-245">You can also use the onboarding status column on API queries to filter out unmanaged devices.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="ab533-246">预览功能</span><span class="sxs-lookup"><span data-stu-id="ab533-246">Preview features</span></span>

<span data-ttu-id="ab533-247">了解 Defender for Endpoint 预览版中的新功能。</span><span class="sxs-lookup"><span data-stu-id="ab533-247">Learn about new features in the Defender for Endpoint preview release.</span></span> <span data-ttu-id="ab533-248">通过打开预览体验来尝试即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="ab533-248">Try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="ab533-249">你将有权访问即将推出的功能，你可以提供反馈，以帮助在功能全面可用之前改进整体体验。</span><span class="sxs-lookup"><span data-stu-id="ab533-249">You'll have access to upcoming features, which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>




## <a name="related-topics"></a><span data-ttu-id="ab533-250">相关主题</span><span class="sxs-lookup"><span data-stu-id="ab533-250">Related topics</span></span>

- [<span data-ttu-id="ab533-251">更新数据保留设置</span><span class="sxs-lookup"><span data-stu-id="ab533-251">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="ab533-252">配置警报通知</span><span class="sxs-lookup"><span data-stu-id="ab533-252">Configure alert notifications</span></span>](configure-email-notifications.md)
