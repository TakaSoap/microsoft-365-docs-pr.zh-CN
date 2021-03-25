---
title: 为 iOS 功能配置 Microsoft Defender ATP
description: 介绍如何部署适用于 iOS 功能的 Microsoft Defender ATP
keywords: microsoft， defender， atp， ios， 配置， 功能， ios
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 90e65c57321fa05a62bc94f4f56d92062d0826a1
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186697"
---
# <a name="configure-microsoft-defender-for-endpoint-for-ios-features"></a><span data-ttu-id="965f9-104">配置适用于 iOS 功能的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="965f9-104">Configure Microsoft Defender for Endpoint for iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="965f9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="965f9-105">**Applies to:**</span></span>
- [<span data-ttu-id="965f9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="965f9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="965f9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="965f9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="965f9-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="965f9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="965f9-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="965f9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="965f9-110">适用于 iOS 的终结点的 Defender 将使用 VPN 来提供 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="965f9-110">Defender for Endpoint for iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="965f9-111">这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。</span><span class="sxs-lookup"><span data-stu-id="965f9-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-for-ios"></a><span data-ttu-id="965f9-112">使用适用于 iOS 的 Defender 终结点的条件访问</span><span class="sxs-lookup"><span data-stu-id="965f9-112">Conditional Access with Defender for Endpoint for iOS</span></span>  
<span data-ttu-id="965f9-113">Microsoft Defender for Endpoint for iOS 以及 Microsoft Intune 和 Azure Active Directory 支持根据设备风险级别强制执行设备合规性和条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="965f9-113">Microsoft Defender for Endpoint for iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="965f9-114">Defender for Endpoint 是移动威胁防护 (MTD) 解决方案，你可以部署该解决方案以通过 Intune 利用此功能。</span><span class="sxs-lookup"><span data-stu-id="965f9-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="965f9-115">若要详细了解如何使用适用于 iOS 的 Defender for Endpoint 设置条件访问，请参阅[Defender for Endpoint 和 Intune。](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="965f9-115">For more information about how to set up Conditional Access with Defender for Endpoint for iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="965f9-116">Web 保护和 VPN</span><span class="sxs-lookup"><span data-stu-id="965f9-116">Web Protection and VPN</span></span>

<span data-ttu-id="965f9-117">默认情况下，适用于 iOS 的 Defender for Endpoint 包括并启用 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="965f9-117">By default, Defender for Endpoint for iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="965f9-118">[Web](web-protection-overview.md) 保护有助于保护设备免受 Web 威胁，并保护用户免受网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="965f9-118">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="965f9-119">适用于 iOS 的终结点的 Defender 使用 VPN 来提供此保护。</span><span class="sxs-lookup"><span data-stu-id="965f9-119">Defender for Endpoint for iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="965f9-120">请注意，这是本地 VPN，与传统 VPN 不同，网络流量不会在设备外部发送。</span><span class="sxs-lookup"><span data-stu-id="965f9-120">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="965f9-121">虽然默认启用，但在某些情况下可能需要你禁用 VPN。</span><span class="sxs-lookup"><span data-stu-id="965f9-121">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="965f9-122">例如，你想要运行一些在配置 VPN 时不起作用的应用。</span><span class="sxs-lookup"><span data-stu-id="965f9-122">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="965f9-123">在这种情况下，你可以选择按照以下步骤在设备上禁用应用中的 VPN：</span><span class="sxs-lookup"><span data-stu-id="965f9-123">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="965f9-124">在 iOS 设备上，打开"设置 **"** 应用，单击或点击"**常规**"，然后单击 **"VPN"。**</span><span class="sxs-lookup"><span data-stu-id="965f9-124">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="965f9-125">单击或点击 Microsoft Defender ATP 的"i"按钮。</span><span class="sxs-lookup"><span data-stu-id="965f9-125">Click or tap the "i" button for Microsoft Defender ATP.</span></span>
1. <span data-ttu-id="965f9-126">关闭" **按需连接"** 以禁用 VPN。</span><span class="sxs-lookup"><span data-stu-id="965f9-126">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="965f9-127">![VPN 配置按需连接](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="965f9-127">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="965f9-128">禁用 VPN 后，Web 保护将不可用。</span><span class="sxs-lookup"><span data-stu-id="965f9-128">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="965f9-129">若要重新启用 Web 保护，请在设备上打开 Microsoft Defender for Endpoint 应用，然后单击或点击"启动 **VPN"。**</span><span class="sxs-lookup"><span data-stu-id="965f9-129">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="965f9-130">多个 VPN 配置文件共存</span><span class="sxs-lookup"><span data-stu-id="965f9-130">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="965f9-131">Apple iOS 不支持多个设备范围的 VPN 同时处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="965f9-131">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="965f9-132">虽然设备上可以存在多个 VPN 配置文件，但一次只能有一个 VPN 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="965f9-132">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="965f9-133">针对越狱设备配置合规性策略</span><span class="sxs-lookup"><span data-stu-id="965f9-133">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="965f9-134">若要防止在已越狱的 iOS 设备上访问公司数据，我们建议在 Intune 上设置以下合规性策略。</span><span class="sxs-lookup"><span data-stu-id="965f9-134">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="965f9-135">目前，适用于 iOS 的 Microsoft Defender for Endpoint 不提供针对越狱情形的保护。</span><span class="sxs-lookup"><span data-stu-id="965f9-135">At this time Microsoft Defender for Endpoint for iOS does not provide protection against jailbreak scenarios.</span></span> <span data-ttu-id="965f9-136">如果在已越狱设备上使用，那么在应用程序使用的特定方案中的数据（如公司电子邮件 ID 和公司个人资料图片） (如果可用) 可在本地公开</span><span class="sxs-lookup"><span data-stu-id="965f9-136">If used on a jailbroken device, then in specific scenarios data that is used by the application like your corporate email id and corporate profile picture (if available) can be exposed locally</span></span>

<span data-ttu-id="965f9-137">按照以下步骤创建针对已越狱设备的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="965f9-137">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="965f9-138">在 [Microsoft Endpoint Manager 管理中心中](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **"设备**  ->  **合规性策略**  ->  **""创建策略"。**</span><span class="sxs-lookup"><span data-stu-id="965f9-138">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="965f9-139">选择"iOS/iPadOS"作为平台，然后单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="965f9-139">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="965f9-140">![创建策略](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="965f9-140">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="965f9-141">指定策略的名称，例如"越狱合规性策略"。</span><span class="sxs-lookup"><span data-stu-id="965f9-141">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="965f9-142">在合规性设置页中，单击展开 **"设备运行状况"** 部分，**然后单击"阻止\*\*\*\*越狱设备"** 字段。</span><span class="sxs-lookup"><span data-stu-id="965f9-142">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="965f9-143">![策略设置](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="965f9-143">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="965f9-144">在"*针对不相容性* 的操作"部分，根据你的要求选择操作，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="965f9-144">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="965f9-145">![策略操作](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="965f9-145">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="965f9-146">在 *"分配*"部分，选择要为此策略包含的用户组，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="965f9-146">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="965f9-147">在"**审阅+创建**"部分，验证输入的所有信息是否正确，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="965f9-147">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="965f9-148">配置自定义指示器</span><span class="sxs-lookup"><span data-stu-id="965f9-148">Configure custom indicators</span></span>

<span data-ttu-id="965f9-149">适用于 iOS 的终结点的 Defender 使管理员能够在 iOS 设备上配置自定义指示器。</span><span class="sxs-lookup"><span data-stu-id="965f9-149">Defender for Endpoint for iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="965f9-150">若要详细了解如何配置自定义指示器，请参阅管理 [指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)。</span><span class="sxs-lookup"><span data-stu-id="965f9-150">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="965f9-151">适用于 iOS 的终结点的 Defender 仅支持为 IP 地址和 URL/域创建自定义指示器。</span><span class="sxs-lookup"><span data-stu-id="965f9-151">Defender for Endpoint for iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="965f9-152">报告不安全网站</span><span class="sxs-lookup"><span data-stu-id="965f9-152">Report unsafe site</span></span>

<span data-ttu-id="965f9-153">网络钓鱼网站会模拟可信赖的网站，以获取你的个人或财务信息。</span><span class="sxs-lookup"><span data-stu-id="965f9-153">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="965f9-154">如果要 [报告可能是网络钓鱼](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 网站的网站，请访问提供有关网络保护的反馈页面。</span><span class="sxs-lookup"><span data-stu-id="965f9-154">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>
