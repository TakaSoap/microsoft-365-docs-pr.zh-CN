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
ms.openlocfilehash: 13c0a575fd2614f58eb6a2163cda04118c2a391d
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636274"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="42abe-104">排查问题并查找 iOS 上 Microsoft Defender for Endpoint 上的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="42abe-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="42abe-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="42abe-105">**Applies to:**</span></span>
- [<span data-ttu-id="42abe-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="42abe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="42abe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42abe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="42abe-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="42abe-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="42abe-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="42abe-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="42abe-110">本主题提供疑难解答信息，以帮助你解决在 iOS 上使用 Microsoft Defender for Endpoint 时可能出现的问题。</span><span class="sxs-lookup"><span data-stu-id="42abe-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="42abe-111">iOS 上的 Defender for Endpoint 将使用 VPN 来提供 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="42abe-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="42abe-112">这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。</span><span class="sxs-lookup"><span data-stu-id="42abe-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="42abe-113">打开 VPN 后，应用无法工作</span><span class="sxs-lookup"><span data-stu-id="42abe-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="42abe-114">某些应用在检测到活动 VPN 时停止运行。</span><span class="sxs-lookup"><span data-stu-id="42abe-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="42abe-115">可以在使用此类应用时禁用 VPN。</span><span class="sxs-lookup"><span data-stu-id="42abe-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="42abe-116">默认情况下，iOS 上的 Defender for Endpoint 包括并启用 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="42abe-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="42abe-117">[Web](web-protection-overview.md) 保护有助于保护设备免受 Web 威胁，并保护用户免受网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="42abe-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="42abe-118">iOS 上的 Defender for Endpoint 使用 VPN 来提供此保护。</span><span class="sxs-lookup"><span data-stu-id="42abe-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="42abe-119">请注意，这是本地 VPN，与传统 VPN 不同，网络流量不会在设备外部发送。</span><span class="sxs-lookup"><span data-stu-id="42abe-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="42abe-120">虽然默认启用，但在某些情况下可能需要你禁用 VPN。</span><span class="sxs-lookup"><span data-stu-id="42abe-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="42abe-121">例如，你想要运行一些在配置 VPN 时不起作用的应用。</span><span class="sxs-lookup"><span data-stu-id="42abe-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="42abe-122">在这种情况下，你可以选择按照以下步骤在设备上禁用应用中的 VPN：</span><span class="sxs-lookup"><span data-stu-id="42abe-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="42abe-123">在 iOS 设备上，打开 **"设置应用**"，单击 **或点击"** 常规"，然后单击 **"VPN"。**</span><span class="sxs-lookup"><span data-stu-id="42abe-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="42abe-124">单击或点击 Microsoft Defender for Endpoint 的"i"按钮。</span><span class="sxs-lookup"><span data-stu-id="42abe-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="42abe-125">关闭 **"连接按需"** 以禁用 VPN。</span><span class="sxs-lookup"><span data-stu-id="42abe-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="42abe-126">![VPN 配置按需连接](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="42abe-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="42abe-127">禁用 VPN 后，Web 保护将不可用。</span><span class="sxs-lookup"><span data-stu-id="42abe-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="42abe-128">若要重新启用 Web 保护，请在设备上打开 Microsoft Defender for Endpoint 应用，然后单击或点击"启动 **VPN"。**</span><span class="sxs-lookup"><span data-stu-id="42abe-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="42abe-129">多个 VPN 配置文件的问题</span><span class="sxs-lookup"><span data-stu-id="42abe-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="42abe-130">Apple iOS 不支持多个设备范围的 VPN 同时处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="42abe-130">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="42abe-131">虽然设备上可以存在多个 VPN 配置文件，但一次只能有一个 VPN 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="42abe-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="battery-consumption"></a><span data-ttu-id="42abe-132">电池消耗</span><span class="sxs-lookup"><span data-stu-id="42abe-132">Battery consumption</span></span>

<span data-ttu-id="42abe-133">应用的电池使用情况由 Apple 根据大量因素（包括 CPU 和网络使用情况）计算。</span><span class="sxs-lookup"><span data-stu-id="42abe-133">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="42abe-134">Microsoft Defender for Endpoint 在后台使用本地/环回 VPN 来检查任何恶意网站或连接的 Web 流量。</span><span class="sxs-lookup"><span data-stu-id="42abe-134">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="42abe-135">来自任何应用的网络数据包都经过此检查，这会导致 Microsoft Defender for Endpoint 的电池使用情况计算不准确。</span><span class="sxs-lookup"><span data-stu-id="42abe-135">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="42abe-136">这会给用户留下假印象。</span><span class="sxs-lookup"><span data-stu-id="42abe-136">This gives a false impression to the user.</span></span> <span data-ttu-id="42abe-137">Microsoft Defender for Endpoint 的实际电池消耗低于设备上"电池设置页面上显示的内容。</span><span class="sxs-lookup"><span data-stu-id="42abe-137">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="42abe-138">这是基于在 Microsoft Defender for Endpoint 应用上执行的测试，以了解电池消耗。</span><span class="sxs-lookup"><span data-stu-id="42abe-138">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="42abe-139">此外，使用的 VPN 是本地 VPN，与传统的 VPN 不同，网络流量不会在设备外部发送。</span><span class="sxs-lookup"><span data-stu-id="42abe-139">Also the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="42abe-140">数据使用情况</span><span class="sxs-lookup"><span data-stu-id="42abe-140">Data usage</span></span>

<span data-ttu-id="42abe-141">Microsoft Defender for Endpoint 使用本地/环回 VPN 检查任何恶意网站或连接的 Web 流量。</span><span class="sxs-lookup"><span data-stu-id="42abe-141">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="42abe-142">由于此原因，Apple 会向 Microsoft Defender for Endpoint 准确记录数据使用情况。</span><span class="sxs-lookup"><span data-stu-id="42abe-142">Due to this reason Apple accounts data usage to Microsoft Defender for Endpoint inaccurately.</span></span> <span data-ttu-id="42abe-143">Microsoft Defender for Endpoint 的实际数据使用量并不明显，并且比设备上"数据使用情况"设置要小得多。</span><span class="sxs-lookup"><span data-stu-id="42abe-143">The actual data usage by Microsoft Defender for Endpoint is not significant and much less than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="42abe-144">报告不安全网站</span><span class="sxs-lookup"><span data-stu-id="42abe-144">Report unsafe site</span></span>

<span data-ttu-id="42abe-145">网络钓鱼网站会模拟可信赖的网站，以获取你的个人或财务信息。</span><span class="sxs-lookup"><span data-stu-id="42abe-145">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="42abe-146">访问 ["提供有关网络保护的反馈"页](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) ，以报告可能是网络钓鱼网站的网站。</span><span class="sxs-lookup"><span data-stu-id="42abe-146">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="42abe-147">检测到恶意站点</span><span class="sxs-lookup"><span data-stu-id="42abe-147">Malicious site detected</span></span>

<span data-ttu-id="42abe-148">Microsoft Defender for Endpoint 可保护你免受网络钓鱼或其他基于 Web 的攻击。</span><span class="sxs-lookup"><span data-stu-id="42abe-148">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="42abe-149">如果检测到恶意站点，连接将被阻止，并且会向组织的安全中心门户发送警报。</span><span class="sxs-lookup"><span data-stu-id="42abe-149">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="42abe-150">警报包括连接的域名、远程 IP 地址和设备详细信息。</span><span class="sxs-lookup"><span data-stu-id="42abe-150">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="42abe-151">此外，iOS 设备上还显示通知。</span><span class="sxs-lookup"><span data-stu-id="42abe-151">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="42abe-152">点击通知将打开以下屏幕，供用户查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="42abe-152">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="42abe-153">![报告为不安全通知的网站的图像](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="42abe-153">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="42abe-154">数据和隐私</span><span class="sxs-lookup"><span data-stu-id="42abe-154">Data and Privacy</span></span>

<span data-ttu-id="42abe-155">有关收集的数据和隐私的详细信息，请参阅 [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="42abe-155">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

