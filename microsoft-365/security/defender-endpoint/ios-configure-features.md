---
title: 在 iOS 功能上配置 Microsoft Defender for Endpoint
description: 介绍如何在 iOS 功能上部署 Microsoft Defender for Endpoint
keywords: microsoft， defender， Microsoft Defender for Endpoint， ios， 配置， 功能， ios
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 749e03cb9d14476245baea82c21d322d4d726aad
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230003"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="3629c-104">在 iOS 功能上配置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3629c-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3629c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3629c-105">**Applies to:**</span></span>
- [<span data-ttu-id="3629c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3629c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3629c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3629c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3629c-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="3629c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3629c-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="3629c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="3629c-110">iOS 上的 Defender for Endpoint 将使用 VPN 来提供 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="3629c-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="3629c-111">这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。</span><span class="sxs-lookup"><span data-stu-id="3629c-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="3629c-112">在 iOS 上通过 Defender for Endpoint 进行条件访问</span><span class="sxs-lookup"><span data-stu-id="3629c-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="3629c-113">iOS 上的 Microsoft Defender for Endpoint 以及 Microsoft Intune 和 Azure Active Directory 启用基于设备风险评分强制执行设备合规性和条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="3629c-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="3629c-114">Defender for Endpoint 是移动威胁防护 (MTD) 解决方案，你可以部署该解决方案以通过 Intune 利用此功能。</span><span class="sxs-lookup"><span data-stu-id="3629c-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="3629c-115">若要详细了解如何使用 iOS 上的 Defender for Endpoint 设置条件访问，请参阅[Defender for Endpoint 和 Intune。](/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="3629c-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a><span data-ttu-id="3629c-116">Microsoft Defender for Endpoint 的越狱检测</span><span class="sxs-lookup"><span data-stu-id="3629c-116">Jailbreak detection by Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="3629c-117">Microsoft Defender for Endpoint 能够检测已越狱的非托管和托管设备。</span><span class="sxs-lookup"><span data-stu-id="3629c-117">Microsoft Defender for Endpoint has the capability of detecting unmanaged and managed devices that are jailbroken.</span></span> <span data-ttu-id="3629c-118">如果检测到设备已越狱，则高风险警报将报告给安全中心，如果根据设备风险评分设置条件访问，则设备将阻止其访问公司数据。</span><span class="sxs-lookup"><span data-stu-id="3629c-118">If a device is detected to be jailbroken, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="3629c-119">Web 保护和 VPN</span><span class="sxs-lookup"><span data-stu-id="3629c-119">Web Protection and VPN</span></span>

<span data-ttu-id="3629c-120">默认情况下，iOS 上的 Defender for Endpoint 包括并启用 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="3629c-120">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="3629c-121">[Web](web-protection-overview.md) 保护有助于保护设备免受 Web 威胁，并保护用户免受网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="3629c-121">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="3629c-122">iOS 上的 Defender for Endpoint 使用 VPN 来提供此保护。</span><span class="sxs-lookup"><span data-stu-id="3629c-122">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="3629c-123">请注意，这是本地 VPN，与传统 VPN 不同，网络流量不会在设备外部发送。</span><span class="sxs-lookup"><span data-stu-id="3629c-123">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="3629c-124">虽然默认启用，但在某些情况下可能需要你禁用 VPN。</span><span class="sxs-lookup"><span data-stu-id="3629c-124">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="3629c-125">例如，你想要运行一些在配置 VPN 时不起作用的应用。</span><span class="sxs-lookup"><span data-stu-id="3629c-125">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="3629c-126">在这种情况下，你可以选择按照以下步骤在设备上禁用应用中的 VPN：</span><span class="sxs-lookup"><span data-stu-id="3629c-126">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="3629c-127">在 iOS 设备上，打开 **"设置应用**"，单击 **或点击"** 常规"，然后单击 **"VPN"。**</span><span class="sxs-lookup"><span data-stu-id="3629c-127">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="3629c-128">单击或点击 Microsoft Defender for Endpoint 的"i"按钮。</span><span class="sxs-lookup"><span data-stu-id="3629c-128">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="3629c-129">关闭 **"连接按需"** 以禁用 VPN。</span><span class="sxs-lookup"><span data-stu-id="3629c-129">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3629c-130">![VPN 配置按需连接](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="3629c-130">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="3629c-131">禁用 VPN 后，Web 保护将不可用。</span><span class="sxs-lookup"><span data-stu-id="3629c-131">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="3629c-132">若要重新启用 Web 保护，请在设备上打开 Microsoft Defender for Endpoint 应用，然后单击或点击"启动 **VPN"。**</span><span class="sxs-lookup"><span data-stu-id="3629c-132">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="3629c-133">多个 VPN 配置文件共存</span><span class="sxs-lookup"><span data-stu-id="3629c-133">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="3629c-134">Apple iOS 不支持多个设备范围的 VPN 同时处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="3629c-134">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="3629c-135">虽然设备上可以存在多个 VPN 配置文件，但一次只能有一个 VPN 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="3629c-135">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a><span data-ttu-id="3629c-136">在 MAM 应用保护策略中配置 Microsoft Defender (终结点) </span><span class="sxs-lookup"><span data-stu-id="3629c-136">Configure Microsoft Defender for Endpoint risk signal in app protection policy (MAM)</span></span>

<span data-ttu-id="3629c-137">Microsoft Defender for Endpoint 可以配置为发送要用于应用保护策略 (APP（也称为 iOS/iPadOS 上的 MAM) MAM）中的威胁信号。</span><span class="sxs-lookup"><span data-stu-id="3629c-137">Microsoft Defender for Endpoint can be configured to send threat signals to be used in App Protection Policies (APP, also known as MAM) on iOS/iPadOS.</span></span> <span data-ttu-id="3629c-138">借助此功能，也可使用 Microsoft Defender for Endpoint 保护从注销的设备访问公司数据。</span><span class="sxs-lookup"><span data-stu-id="3629c-138">With this capability, you can use Microsoft Defender for Endpoint to protect access to corporate data from unenrolled devices as well.</span></span>

<span data-ttu-id="3629c-139">使用 Microsoft Defender for Endpoint 设置应用保护策略的步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="3629c-139">Steps to setup app protection policies with Microsoft Defender for Endpoint are as below:</span></span>

1. <span data-ttu-id="3629c-140">设置从你的 Microsoft Endpoint Manager 到 Microsoft Defender for Endpoint 的连接。</span><span class="sxs-lookup"><span data-stu-id="3629c-140">Set up the connection from your Microsoft Endpoint Manager tenant to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3629c-141">在 [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)管理中心 中，转到"设置) "下的"跨平台) "或"终结点安全 Microsoft Defender  >    >  **for**   >  **Endpoint** ("下的"适用于终结点的 Microsoft Defender (租户管理连接器和令牌"，然后打开适用于 iOS 的应用保护策略 设置 下的切换。</span><span class="sxs-lookup"><span data-stu-id="3629c-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Tenant Administration** > **Connectors and tokens** > **Microsoft Defender for Endpoint** (under Cross platform) or **Endpoint Security** > **Microsoft Defender for Endpoint** (under Setup) and turn on the toggles under **App Protection Policy Settings for iOS**.</span></span>
1. <span data-ttu-id="3629c-142">选择“保存”。</span><span class="sxs-lookup"><span data-stu-id="3629c-142">Select Save.</span></span> <span data-ttu-id="3629c-143">应看到"**连接状态**"现在设置为"**已启用"。**</span><span class="sxs-lookup"><span data-stu-id="3629c-143">You should see **Connection status** is now set to **Enabled**.</span></span>
1. <span data-ttu-id="3629c-144">创建应用保护策略：完成 Microsoft Defender for Endpoint 连接器设置后，导航到策略 (下的应用应用保护策略) 以创建新策略或更新  >  现有策略。</span><span class="sxs-lookup"><span data-stu-id="3629c-144">Create app protection policy: After your Microsoft Defender for Endpoint connector setup is complete, navigate to **Apps** > **App protection policies** (under Policy) to create a new policy or update an existing one.</span></span>
1. <span data-ttu-id="3629c-145">选择组织为策略 **所需的** 平台、应用、数据保护、访问要求设置。</span><span class="sxs-lookup"><span data-stu-id="3629c-145">Select the platform, **Apps, Data protection, Access requirements** settings that your organization requires for your policy.</span></span>
1. <span data-ttu-id="3629c-146">在 **"条件启动**  >  **设备条件**"下，你将找到设置 **"允许的最大设备威胁级别"。**</span><span class="sxs-lookup"><span data-stu-id="3629c-146">Under **Conditional launch** > **Device conditions**, you will find the setting **Max allowed device threat level**.</span></span> <span data-ttu-id="3629c-147">这将需要配置为低、中、高或安全。</span><span class="sxs-lookup"><span data-stu-id="3629c-147">This will need to be configured to either Low, Medium, High, or Secured.</span></span> <span data-ttu-id="3629c-148">可用操作为"阻止 **访问"或**"**擦除数据"。**</span><span class="sxs-lookup"><span data-stu-id="3629c-148">The actions available to you will be **Block access** or **Wipe data**.</span></span> <span data-ttu-id="3629c-149">在此设置生效之前，你可能会看到一个信息对话框，确保你已设置连接器。</span><span class="sxs-lookup"><span data-stu-id="3629c-149">You may see an informational dialog to make sure you have your connector set up prior to this setting take effect.</span></span> <span data-ttu-id="3629c-150">如果连接器已设置，可以忽略此对话框。</span><span class="sxs-lookup"><span data-stu-id="3629c-150">If your connector is already set up, you may ignore this dialog.</span></span>
1. <span data-ttu-id="3629c-151">完成分配并保存策略。</span><span class="sxs-lookup"><span data-stu-id="3629c-151">Finish with Assignments and save your policy.</span></span>

<span data-ttu-id="3629c-152">有关 MAM 或应用保护策略的更多详细信息，请参阅 [iOS 应用保护策略设置](/mem/intune/apps/app-protection-policy-settings-ios)。</span><span class="sxs-lookup"><span data-stu-id="3629c-152">For more details on MAM or app protection policy, see [iOS app protection policy settings](/mem/intune/apps/app-protection-policy-settings-ios).</span></span>

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a><span data-ttu-id="3629c-153">为 MAM 或注销的设备上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3629c-153">Deploying Microsoft Defender for Endpoint for MAM or on unenrolled devices</span></span>

<span data-ttu-id="3629c-154">iOS 上的 Microsoft Defender for Endpoint 支持应用保护策略方案，并且适用于 Apple 应用商店。</span><span class="sxs-lookup"><span data-stu-id="3629c-154">Microsoft Defender for Endpoint on iOS enables the App Protection Policy scenario and is available in the Apple app store.</span></span>

<span data-ttu-id="3629c-155">最终用户应直接从 Apple 应用商店安装应用的最新版本。</span><span class="sxs-lookup"><span data-stu-id="3629c-155">End-users should install the latest version of the app directly from the Apple app store.</span></span>

## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="3629c-156">针对越狱设备配置合规性策略</span><span class="sxs-lookup"><span data-stu-id="3629c-156">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="3629c-157">若要防止在已越狱的 iOS 设备上访问公司数据，我们建议在 Intune 上设置以下合规性策略。</span><span class="sxs-lookup"><span data-stu-id="3629c-157">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="3629c-158">越狱检测是 Microsoft Defender for Endpoint 在 iOS 上提供的一项功能。</span><span class="sxs-lookup"><span data-stu-id="3629c-158">Jailbreak detection is a capability provided by Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="3629c-159">但是，我们建议你设置此策略作为抵御越狱情形的额外防御层。</span><span class="sxs-lookup"><span data-stu-id="3629c-159">However, we recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="3629c-160">按照以下步骤创建针对已越狱设备的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="3629c-160">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="3629c-161">In [Microsoft Endpoint Manager admin center，](https://go.microsoft.com/fwlink/?linkid=2109431)go to **Devices**  ->  **Compliance policies** Create  ->  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="3629c-161">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="3629c-162">选择"iOS/iPadOS"作为平台，然后单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="3629c-162">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3629c-163">![创建策略](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="3629c-163">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="3629c-164">指定策略的名称，例如"越狱合规性策略"。</span><span class="sxs-lookup"><span data-stu-id="3629c-164">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="3629c-165">在合规性设置页中，单击展开 **"设备运行状况"** 部分，**然后单击"阻止\*\*\*\*越狱设备"** 字段。</span><span class="sxs-lookup"><span data-stu-id="3629c-165">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3629c-166">![策略设置](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="3629c-166">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="3629c-167">在"**针对不相容性** 的操作"部分，根据你的要求选择操作，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="3629c-167">In the **Action for noncompliance** section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3629c-168">![策略操作](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="3629c-168">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="3629c-169">在 **"分配**"部分，选择要为此策略包含的用户组，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="3629c-169">In the **Assignments** section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="3629c-170">在"**审阅+创建**"部分，验证输入的所有信息是否正确，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="3629c-170">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="3629c-171">配置自定义指示器</span><span class="sxs-lookup"><span data-stu-id="3629c-171">Configure custom indicators</span></span>

<span data-ttu-id="3629c-172">通过 iOS 上的 Defender for Endpoint，管理员还可以在 iOS 设备上配置自定义指示器。</span><span class="sxs-lookup"><span data-stu-id="3629c-172">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="3629c-173">若要详细了解如何配置自定义指示器，请参阅管理 [指示器](/microsoft-365/security/defender-endpoint/manage-indicators)。</span><span class="sxs-lookup"><span data-stu-id="3629c-173">For more information on how to configure custom indicators, see [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="3629c-174">iOS 上的 Defender for Endpoint 仅支持为 IP 地址和 URL/域创建自定义指示器。</span><span class="sxs-lookup"><span data-stu-id="3629c-174">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="3629c-175">报告不安全网站</span><span class="sxs-lookup"><span data-stu-id="3629c-175">Report unsafe site</span></span>

<span data-ttu-id="3629c-176">网络钓鱼网站会模拟可信赖的网站，以获取你的个人或财务信息。</span><span class="sxs-lookup"><span data-stu-id="3629c-176">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="3629c-177">如果要 [报告可能是网络钓鱼](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 网站的网站，请访问提供有关网络保护的反馈页面。</span><span class="sxs-lookup"><span data-stu-id="3629c-177">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

