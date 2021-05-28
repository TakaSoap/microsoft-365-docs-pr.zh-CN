---
title: 排查问题并查找与 iOS 上的 Microsoft Defender for Endpoint 相关的常见问题解答
description: 疑难解答和常见问题解答 - 适用于 iOS 上的终结点的 Microsoft Defender
keywords: microsoft， defender， Microsoft Defender for Endpoint， ios， 疑难解答， 如何
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
ms.openlocfilehash: 2f9d56b7e72befb8acddf6d9f810a7ba5cec1083
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694361"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="6333d-104">排查问题并查找 iOS 上 Microsoft Defender for Endpoint 上的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="6333d-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6333d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6333d-105">**Applies to:**</span></span>
- [<span data-ttu-id="6333d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6333d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6333d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6333d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6333d-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="6333d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6333d-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6333d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="6333d-110">本主题提供疑难解答信息，以帮助你解决在 iOS 上使用 Microsoft Defender for Endpoint 时可能出现的问题。</span><span class="sxs-lookup"><span data-stu-id="6333d-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="6333d-111">iOS 上的 Defender for Endpoint 将使用 VPN 来提供 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="6333d-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="6333d-112">这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。</span><span class="sxs-lookup"><span data-stu-id="6333d-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="6333d-113">打开 VPN 后，应用无法工作</span><span class="sxs-lookup"><span data-stu-id="6333d-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="6333d-114">某些应用在检测到活动 VPN 时停止运行。</span><span class="sxs-lookup"><span data-stu-id="6333d-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="6333d-115">可以在使用此类应用时禁用 VPN。</span><span class="sxs-lookup"><span data-stu-id="6333d-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="6333d-116">默认情况下，iOS 上的 Defender for Endpoint 包括并启用 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="6333d-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="6333d-117">[Web](web-protection-overview.md) 保护有助于保护设备免受 Web 威胁，并保护用户免受网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="6333d-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="6333d-118">iOS 上的 Defender for Endpoint 使用 VPN 来提供此保护。</span><span class="sxs-lookup"><span data-stu-id="6333d-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="6333d-119">请注意，这是本地 VPN，与传统 VPN 不同，网络流量不会在设备外部发送。</span><span class="sxs-lookup"><span data-stu-id="6333d-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="6333d-120">虽然默认启用，但在某些情况下可能需要你禁用 VPN。</span><span class="sxs-lookup"><span data-stu-id="6333d-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="6333d-121">例如，你想要运行一些在配置 VPN 时不起作用的应用。</span><span class="sxs-lookup"><span data-stu-id="6333d-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="6333d-122">在这种情况下，你可以选择按照以下步骤在设备上禁用应用中的 VPN：</span><span class="sxs-lookup"><span data-stu-id="6333d-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="6333d-123">在 iOS 设备上，打开 **"设置应用**"，单击 **或点击"** 常规"，然后单击 **"VPN"。**</span><span class="sxs-lookup"><span data-stu-id="6333d-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="6333d-124">单击或点击 Microsoft Defender for Endpoint 的"i"按钮。</span><span class="sxs-lookup"><span data-stu-id="6333d-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="6333d-125">关闭 **"连接按需"** 以禁用 VPN。</span><span class="sxs-lookup"><span data-stu-id="6333d-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6333d-126">![VPN 配置按需连接](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="6333d-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="6333d-127">禁用 VPN 后，Web 保护将不可用。</span><span class="sxs-lookup"><span data-stu-id="6333d-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="6333d-128">若要重新启用 Web 保护，请在设备上打开 Microsoft Defender for Endpoint 应用，然后单击或点击"启动 **VPN"。**</span><span class="sxs-lookup"><span data-stu-id="6333d-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="6333d-129">多个 VPN 配置文件的问题</span><span class="sxs-lookup"><span data-stu-id="6333d-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="6333d-130">Apple iOS 不支持多个 **设备范围的** VPN 同时处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="6333d-130">Apple iOS does not support multiple **device-wide** VPNs to be active simultaneously.</span></span> <span data-ttu-id="6333d-131">虽然设备上可以存在多个 VPN 配置文件，但一次只能有一个 VPN 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="6333d-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

<span data-ttu-id="6333d-132">Microsoft Defender for Endpoint VPN 可以与配置为每应用或"个人"的其他 VPN *共存*。</span><span class="sxs-lookup"><span data-stu-id="6333d-132">Microsoft Defender for Endpoint VPN can co-exist with other VPNs that are configured as *per-app* or *"Personal"*.</span></span>

## <a name="battery-consumption"></a><span data-ttu-id="6333d-133">电池消耗</span><span class="sxs-lookup"><span data-stu-id="6333d-133">Battery consumption</span></span>

<span data-ttu-id="6333d-134">在设置应用中，iOS 仅显示特定持续时间内对用户可见的应用的电池使用情况。</span><span class="sxs-lookup"><span data-stu-id="6333d-134">In the Settings app, iOS only shows battery usage of apps that are visible to the user for a specific duration of time.</span></span> <span data-ttu-id="6333d-135">屏幕上显示的应用的电池使用情况仅在该持续时间内，由 iOS 根据大量因素（包括 CPU 和网络使用情况）计算。</span><span class="sxs-lookup"><span data-stu-id="6333d-135">The battery usage by apps shown on the screen are only for that time duration and is computed by iOS based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="6333d-136">Microsoft Defender for Endpoint 在后台使用本地/环回 VPN 来检查任何恶意网站或连接的 Web 流量。</span><span class="sxs-lookup"><span data-stu-id="6333d-136">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="6333d-137">来自任何应用的网络数据包都经过此检查，这会导致 Microsoft Defender for Endpoint 的电池使用情况计算不准确。</span><span class="sxs-lookup"><span data-stu-id="6333d-137">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="6333d-138">Microsoft Defender for Endpoint 的实际电池消耗远小于设备上"电池设置页面上显示的内容。</span><span class="sxs-lookup"><span data-stu-id="6333d-138">The actual battery consumption of Microsoft Defender for Endpoint is much less than what is shown on the Battery Settings page on the device.</span></span>

<span data-ttu-id="6333d-139">平均而言，运行在后台的终结点的 Microsoft Defender 每天的电池使用量大约为当天消耗的总电池的 **8.81%。**</span><span class="sxs-lookup"><span data-stu-id="6333d-139">On an average, per-day battery usage by Microsoft Defender for Endpoint running on the background is **approximately 8.81% of overall battery consumed in that day**.</span></span> <span data-ttu-id="6333d-140">Apple 根据最终用户设备上 Microsoft Defender for Endpoint 的实际使用情况报告此指标，并且由于上述原因，还可以将指标计算到具有网络活动的其他应用。</span><span class="sxs-lookup"><span data-stu-id="6333d-140">This metric is reported by Apple based on actual usage of Microsoft Defender for Endpoint on end-user devices and due to reasons mentioned above can also be accounted to other apps that have network activity.</span></span>

<span data-ttu-id="6333d-141">此外，使用的 VPN 是本地 VPN，与传统 VPN 不同，网络流量不会在设备外部发送。</span><span class="sxs-lookup"><span data-stu-id="6333d-141">Also, the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="6333d-142">数据使用情况</span><span class="sxs-lookup"><span data-stu-id="6333d-142">Data usage</span></span>

<span data-ttu-id="6333d-143">Microsoft Defender for Endpoint 使用本地/环回 VPN 检查任何恶意网站或连接的 Web 流量。</span><span class="sxs-lookup"><span data-stu-id="6333d-143">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="6333d-144">由于此原因，Microsoft Defender 终结点数据使用情况可能不准确。</span><span class="sxs-lookup"><span data-stu-id="6333d-144">Due to this reason, Microsoft Defender for Endpoint data usage can be inaccurately accounted for.</span></span> <span data-ttu-id="6333d-145">Microsoft Defender for Endpoint 的实际数据使用量并不明显，并且小于设备上"数据设置上显示的数据使用量。</span><span class="sxs-lookup"><span data-stu-id="6333d-145">The actual data usage by Microsoft Defender for Endpoint is not significant and lesser than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="6333d-146">报告不安全网站</span><span class="sxs-lookup"><span data-stu-id="6333d-146">Report unsafe site</span></span>

<span data-ttu-id="6333d-147">网络钓鱼网站会模拟可信赖的网站，以获取你的个人或财务信息。</span><span class="sxs-lookup"><span data-stu-id="6333d-147">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="6333d-148">访问 ["提供有关网络保护的反馈"页](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) ，以报告可能是网络钓鱼网站的网站。</span><span class="sxs-lookup"><span data-stu-id="6333d-148">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="6333d-149">检测到恶意站点</span><span class="sxs-lookup"><span data-stu-id="6333d-149">Malicious site detected</span></span>

<span data-ttu-id="6333d-150">Microsoft Defender for Endpoint 可保护你免受网络钓鱼或其他基于 Web 的攻击。</span><span class="sxs-lookup"><span data-stu-id="6333d-150">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="6333d-151">如果检测到恶意站点，连接将被阻止，并且会向组织的安全中心门户发送警报。</span><span class="sxs-lookup"><span data-stu-id="6333d-151">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="6333d-152">警报包括连接的域名、远程 IP 地址和设备详细信息。</span><span class="sxs-lookup"><span data-stu-id="6333d-152">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="6333d-153">此外，iOS 设备上还显示通知。</span><span class="sxs-lookup"><span data-stu-id="6333d-153">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="6333d-154">点击通知将打开以下屏幕，供用户查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="6333d-154">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6333d-155">![报告为不安全通知的网站的图像](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="6333d-155">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="6333d-156">数据和隐私</span><span class="sxs-lookup"><span data-stu-id="6333d-156">Data and Privacy</span></span>

<span data-ttu-id="6333d-157">有关收集的数据和隐私的详细信息，请参阅 [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="6333d-157">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

