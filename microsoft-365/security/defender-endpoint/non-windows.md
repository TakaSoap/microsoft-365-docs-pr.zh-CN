---
title: 适用于非 Windows 平台的 Microsoft Defender ATP
description: 了解适用于非 Windows 平台的 Microsoft Defender ATP 功能
keywords: 非 Windows， mac， macos， linux， android
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6d9d376f63f35fb86641a7f805860eb448d7460d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054714"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a><span data-ttu-id="aa822-104">适用于非 Windows 平台的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa822-104">Microsoft Defender for Endpoint for non-Windows platforms</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aa822-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="aa822-105">**Applies to:**</span></span>
- [<span data-ttu-id="aa822-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa822-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="aa822-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa822-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="aa822-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="aa822-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aa822-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="aa822-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="aa822-110">Microsoft 一直在向 macOS、Linux、Android 和很快的 iOS 扩展 Windows 和 Windows Server 以外的行业领先的终结点安全性。</span><span class="sxs-lookup"><span data-stu-id="aa822-110">Microsoft has been on a journey to extend its industry leading endpoint security capabilities beyond Windows and Windows Server to macOS, Linux, Android, and soon iOS.</span></span>

<span data-ttu-id="aa822-111">组织面临各种平台和设备的威胁。</span><span class="sxs-lookup"><span data-stu-id="aa822-111">Organizations face threats across a variety of platforms and devices.</span></span> <span data-ttu-id="aa822-112">Our teams have committed to building security solutions not just *for* Microsoft， and also *from* Microsoft to enable our customers to protect and secure their heterogenous environments.</span><span class="sxs-lookup"><span data-stu-id="aa822-112">Our teams have committed to building security solutions not just *for* Microsoft, but also *from* Microsoft to enable our customers to protect and secure their heterogenous environments.</span></span> <span data-ttu-id="aa822-113">我们期待聆听客户反馈，并与客户密切合作，以构建满足其需求的解决方案。</span><span class="sxs-lookup"><span data-stu-id="aa822-113">We're listening to customer feedback and partnering closely with our customers to build solutions that meet their needs.</span></span>

<span data-ttu-id="aa822-114">借助 Microsoft Defender for Endpoint，客户可以跨 Windows 和非 Windows 平台从 Microsoft Defender 安全中心中所有威胁和警报的统一视图中获益，从而全面了解环境中发生的情况，从而可以更快速地评估和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="aa822-114">With Microsoft Defender for Endpoint, customers benefit from a unified view of all threats and alerts in the Microsoft Defender Security Center, across Windows and non-Windows platforms, enabling them to get a full picture of what's happening in their environment, which empowers them to more quickly assess and respond to threats.</span></span>

## <a name="microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="aa822-115">macOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa822-115">Microsoft Defender for Endpoint on macOS</span></span> 

<span data-ttu-id="aa822-116">macOS 上的 Microsoft Defender for Endpoint 为三个最新发布的 macOS (EDR) 提供防病毒和终结点检测和响应功能。</span><span class="sxs-lookup"><span data-stu-id="aa822-116">Microsoft Defender for Endpoint on macOS offers antivirus and endpoint detection and response (EDR) capabilities for the three latest released versions of macOS.</span></span> <span data-ttu-id="aa822-117">客户可以通过 Microsoft Endpoint Manager 和 Jamf 部署和管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="aa822-117">Customers can deploy and manage the solution through Microsoft Endpoint Manager and Jamf.</span></span> <span data-ttu-id="aa822-118">就像在 macOS Microsoft Office一样，Microsoft 自动更新用于管理 Mac 上的 Microsoft Defender for Endpoint 更新。</span><span class="sxs-lookup"><span data-stu-id="aa822-118">Just like with Microsoft Office applications on macOS, Microsoft Auto Update is used to manage Microsoft Defender for Endpoint on Mac updates.</span></span> <span data-ttu-id="aa822-119">有关关键功能和优势的信息，请阅读 [我们的公告](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS)。</span><span class="sxs-lookup"><span data-stu-id="aa822-119">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS).</span></span>

<span data-ttu-id="aa822-120">若要详细了解如何开始使用，请访问 macOS 上的 Defender for Endpoint [文档](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)。</span><span class="sxs-lookup"><span data-stu-id="aa822-120">For more details on how to get started, visit the Defender for Endpoint on macOS [documentation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).</span></span>

## <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="aa822-121">Linux 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa822-121">Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="aa822-122">Linux 上的 Microsoft Defender for Endpoint 为 Linux (提供) AV 功能。</span><span class="sxs-lookup"><span data-stu-id="aa822-122">Microsoft Defender for Endpoint on Linux offers preventative (AV) capabilities for Linux servers.</span></span> <span data-ttu-id="aa822-123">这包括配置和管理代理、启动扫描和管理威胁的完整命令行体验。</span><span class="sxs-lookup"><span data-stu-id="aa822-123">This includes a full command line experience to configure and manage the agent, initiate scans, and manage threats.</span></span> <span data-ttu-id="aa822-124">我们支持六个最常见的 Linux Server 分发的最新版本：RHEL 7.2+、CentOS Linux 7.2+、Ubuntu 16 LTS 或更高版本 LTS、SLES 12+、Debian 9+和 Oracle Linux 7.2。</span><span class="sxs-lookup"><span data-stu-id="aa822-124">We support recent versions of the six most common Linux Server distributions: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS, or higher LTS, SLES 12+, Debian 9+, and Oracle Linux 7.2.</span></span> <span data-ttu-id="aa822-125">可以使用部署和配置 Linux 上的 Microsoft Defender for Endpoint、Ansible 或现有的 Linux 配置管理工具进行部署和配置。</span><span class="sxs-lookup"><span data-stu-id="aa822-125">Microsoft Defender for Endpoint on Linux can be deployed and configured using Puppet, Ansible, or using your existing Linux configuration management tool.</span></span> <span data-ttu-id="aa822-126">有关关键功能和优势的信息，请阅读 [我们的公告](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux)。</span><span class="sxs-lookup"><span data-stu-id="aa822-126">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux).</span></span>

<span data-ttu-id="aa822-127">若要详细了解如何开始使用，请访问 Linux 上的 Microsoft Defender for Endpoint [文档](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux)。</span><span class="sxs-lookup"><span data-stu-id="aa822-127">For more details on how to get started, visit the Microsoft Defender for Endpoint on Linux [documentation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux).</span></span>

## <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="aa822-128">Android 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa822-128">Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="aa822-129">Android 版 Microsoft Defender for Endpoint 是适用于运行 Android 6.0 及更高版本的设备的移动威胁防护解决方案。</span><span class="sxs-lookup"><span data-stu-id="aa822-129">Microsoft Defender for Endpoint on Android is our mobile threat defense solution for devices running Android 6.0 and higher.</span></span> <span data-ttu-id="aa822-130">Android Enterprise (Work Profile) 和设备管理员模式均受支持。</span><span class="sxs-lookup"><span data-stu-id="aa822-130">Both Android Enterprise (Work Profile) and Device Administrator modes are supported.</span></span> <span data-ttu-id="aa822-131">在 Android 上，我们提供 Web 保护，包括防钓鱼、阻止不安全连接以及设置自定义指示器。</span><span class="sxs-lookup"><span data-stu-id="aa822-131">On Android, we offer web protection, which includes anti-phishing, blocking of unsafe connections, and setting of custom indicators.</span></span> <span data-ttu-id="aa822-132">解决方案扫描 PUA 中恶意软件和可能不需要 (应用程序) 与 Microsoft Endpoint Manager 和条件访问集成，从而提供额外的泄露防护功能。</span><span class="sxs-lookup"><span data-stu-id="aa822-132">The solution scans for malware and potentially unwanted applications (PUA) and offers additional breach prevention capabilities through integration with Microsoft Endpoint Manager and Conditional Access.</span></span> <span data-ttu-id="aa822-133">有关关键功能和优势的信息，请阅读 [我们的公告](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android)。</span><span class="sxs-lookup"><span data-stu-id="aa822-133">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android).</span></span>

<span data-ttu-id="aa822-134">若要详细了解如何开始使用，请访问 Android 版 Microsoft Defender for Endpoint [文档](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-android)。</span><span class="sxs-lookup"><span data-stu-id="aa822-134">For more details on how to get started, visit the Microsoft Defender for Endpoint on Android [documentation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-android).</span></span>

## <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="aa822-135">iOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa822-135">Microsoft Defender for Endpoint on iOS</span></span>

<span data-ttu-id="aa822-136">iOS 上的 Microsoft Defender for Endpoint 是适用于运行 iOS 11.0 及更高版本的设备的移动威胁防护解决方案。</span><span class="sxs-lookup"><span data-stu-id="aa822-136">Microsoft Defender for Endpoint on iOS is our mobile threat defense solution for devices running iOS 11.0 and higher.</span></span> <span data-ttu-id="aa822-137">支持监督设备和未监督设备。</span><span class="sxs-lookup"><span data-stu-id="aa822-137">Both Supervised and Unsupervised devices are supported.</span></span> <span data-ttu-id="aa822-138">在 iOS 上，我们提供包括防钓鱼、阻止不安全连接和设置自定义指示器的 Web 保护。</span><span class="sxs-lookup"><span data-stu-id="aa822-138">On iOS, we offer web protection which includes anti-phishing, blocking unsafe connections, and setting custom indicators.</span></span> <span data-ttu-id="aa822-139">有关主要功能和优点详细信息，请阅读 [我们的公告](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。</span><span class="sxs-lookup"><span data-stu-id="aa822-139">For more information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span> 

<span data-ttu-id="aa822-140">若要详细了解如何开始使用，请访问 iOS 上的 Microsoft Defender for Endpoint [文档](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-ios)。</span><span class="sxs-lookup"><span data-stu-id="aa822-140">For more details on how to get started, visit the Microsoft Defender for Endpoint on iOS [documentation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-ios).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="aa822-141">许可要求</span><span class="sxs-lookup"><span data-stu-id="aa822-141">Licensing requirements</span></span> 

<span data-ttu-id="aa822-142">符合条件的许可用户可以在最多五台并发设备上使用 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="aa822-142">Eligible Licensed Users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span> <span data-ttu-id="aa822-143">Microsoft Defender for Endpoint 还可从云解决方案提供商云解决方案提供商 (云解决方案提供商) 。</span><span class="sxs-lookup"><span data-stu-id="aa822-143">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="aa822-144">客户可以通过独立 Microsoft Defender for Endpoint 许可证（作为 Microsoft 365 A5/E5 或 Microsoft 365 安全性的一部分）在 macOS 上获取 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="aa822-144">Customers can obtain Microsoft Defender for Endpoint on macOS through a standalone Microsoft Defender for Endpoint license, as part of Microsoft 365 A5/E5, or Microsoft 365 Security.</span></span>

<span data-ttu-id="aa822-145">上述产品/服务中包含最近宣布的适用于 Android 和 iOS 的 Microsoft Defender for Endpoint 的功能，这些功能是适用于合格许可用户的五个合格设备的一部分。</span><span class="sxs-lookup"><span data-stu-id="aa822-145">Recently announced capabilities of Microsoft Defender for Endpoint for Android and iOS are included in the above mentioned offers as part of the five qualified devices for eligible licensed users.</span></span>

<span data-ttu-id="aa822-146">Linux 上的 Defender for Endpoint 通过 Defender for Endpoint Server SKU 提供，适用于商业和教育客户。</span><span class="sxs-lookup"><span data-stu-id="aa822-146">Defender for Endpoint on Linux is available through the Defender for Endpoint Server SKU that is available for both commercial and education customers.</span></span>

<span data-ttu-id="aa822-147">有关定价和其他资格要求，请联系你的帐户团队或云解决方案提供商。</span><span class="sxs-lookup"><span data-stu-id="aa822-147">Please contact your account team or CSP for pricing and additional eligibility requirements.</span></span>
