---
title: 为 IP 和 URL/域创建指示器
ms.reviewer: ''
description: 为定义实体的检测、防护和排除的 IP 和 URL/域创建指示器。
keywords: ip， url， 域， 管理， 允许， 阻止， 阻止， 清理， 恶意， 文件哈希， ip 地址， url， 域
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
ms.openlocfilehash: 0196148c9dbf3ec769594d714524a3fd9e4d18fd
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185953"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="f310e-104">为 IP 和 URL/域创建指示器</span><span class="sxs-lookup"><span data-stu-id="f310e-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f310e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f310e-105">**Applies to:**</span></span>
- [<span data-ttu-id="f310e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f310e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f310e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f310e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="f310e-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="f310e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f310e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f310e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="f310e-110">Defender for Endpoint 可以阻止 Microsoft 视为恶意 IP/URL、通过适用于 Microsoft 浏览器的 Windows Defender SmartScreen，以及针对非 Microsoft 浏览器或在浏览器外进行调用的网络保护。</span><span class="sxs-lookup"><span data-stu-id="f310e-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="f310e-111">针对这一点的威胁情报数据集已由 Microsoft 管理。</span><span class="sxs-lookup"><span data-stu-id="f310e-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="f310e-112">通过创建 IP 和 URL 或域的指示器，你现在可以基于自己的威胁情报允许或阻止 IP、URL 或域。</span><span class="sxs-lookup"><span data-stu-id="f310e-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="f310e-113">如果你认为某些组的风险大于或低于其他组，可以通过设置页面或计算机组来这样做。</span><span class="sxs-lookup"><span data-stu-id="f310e-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="f310e-114">不支持无Inter-Domain IP (CIDR) 表示法。</span><span class="sxs-lookup"><span data-stu-id="f310e-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="f310e-115">准备工作</span><span class="sxs-lookup"><span data-stu-id="f310e-115">Before you begin</span></span>
<span data-ttu-id="f310e-116">在创建 IPS、URL 或域的指示器之前，了解以下先决条件非常重要：</span><span class="sxs-lookup"><span data-stu-id="f310e-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="f310e-117">URL/IP 允许和阻止依赖于 Defender for Endpoint 组件网络保护在阻止模式下启用。</span><span class="sxs-lookup"><span data-stu-id="f310e-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="f310e-118">有关网络保护和配置说明详细信息，请参阅启用 [网络保护](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="f310e-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="f310e-119">反恶意软件客户端版本必须为 4.18.1906.x 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="f310e-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="f310e-120">在 Windows 10 版本 1709 或更高版本上支持的计算机。</span><span class="sxs-lookup"><span data-stu-id="f310e-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="f310e-121">确保 Microsoft Defender **安全中心中的** 自定义网络指示器已启用> **设置>高级功能**。</span><span class="sxs-lookup"><span data-stu-id="f310e-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="f310e-122">有关详细信息，请参阅高级 [功能](advanced-features.md)。</span><span class="sxs-lookup"><span data-stu-id="f310e-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="f310e-123">有关 iOS 上的指示器支持，请参阅 [配置自定义指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)。</span><span class="sxs-lookup"><span data-stu-id="f310e-123">For support of indicators on iOS, see [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="f310e-124">只能将外部 IP 添加到指示器列表。</span><span class="sxs-lookup"><span data-stu-id="f310e-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="f310e-125">无法为内部 IP 创建指示器。</span><span class="sxs-lookup"><span data-stu-id="f310e-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="f310e-126">对于 Web 保护方案，我们建议使用 Microsoft Edge 中的内置功能。</span><span class="sxs-lookup"><span data-stu-id="f310e-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="f310e-127">Microsoft Edge 利用 [网络保护](network-protection.md) 来检查网络流量，并允许阻止 TCP、HTTP 和 HTTPS (TLS) 。</span><span class="sxs-lookup"><span data-stu-id="f310e-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="f310e-128">对于所有其他进程，Web 保护方案利用网络保护进行检查和强制执行：</span><span class="sxs-lookup"><span data-stu-id="f310e-128">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> <br>
> <span data-ttu-id="f310e-129">注意：</span><span class="sxs-lookup"><span data-stu-id="f310e-129">NOTE:</span></span>
> - <span data-ttu-id="f310e-130">所有三种协议均支持 IP</span><span class="sxs-lookup"><span data-stu-id="f310e-130">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="f310e-131">没有 CIDR 块或 IP 范围 (仅支持单个 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="f310e-131">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="f310e-132">只有在第 (浏览器、边缘) ，才能阻止加密的 URL (Internet Explorer完整路径) </span><span class="sxs-lookup"><span data-stu-id="f310e-132">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="f310e-133">加密的 URL (FQDN) 可以在第一方浏览器或边缘 (Internet Explorer外部阻止) </span><span class="sxs-lookup"><span data-stu-id="f310e-133">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="f310e-134">完整 URL 路径块可以应用于域级别以及所有未加密的 URL</span><span class="sxs-lookup"><span data-stu-id="f310e-134">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="f310e-135">延迟时间可能最多为 2 小时 (通常) 操作和阻止的 URL 和 IP 之间的延迟时间通常较少。</span><span class="sxs-lookup"><span data-stu-id="f310e-135">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="f310e-136">从设置页面为 IP、URL 或域创建指示器</span><span class="sxs-lookup"><span data-stu-id="f310e-136">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="f310e-137">在导航窗格中，选择"**设置**  >  **""指示器"。**</span><span class="sxs-lookup"><span data-stu-id="f310e-137">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="f310e-138">选择 **"IP 地址或 URL/域"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f310e-138">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="f310e-139">选择 **"添加项目"。**</span><span class="sxs-lookup"><span data-stu-id="f310e-139">Select **Add item**.</span></span>

4. <span data-ttu-id="f310e-140">指定以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="f310e-140">Specify the following details:</span></span>
   - <span data-ttu-id="f310e-141">Indicator - 指定实体详细信息并定义指示器的过期时间。</span><span class="sxs-lookup"><span data-stu-id="f310e-141">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="f310e-142">操作 - 指定要采取的操作并提供说明。</span><span class="sxs-lookup"><span data-stu-id="f310e-142">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="f310e-143">Scope - 定义计算机组的范围。</span><span class="sxs-lookup"><span data-stu-id="f310e-143">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="f310e-144">查看"摘要"选项卡中的详细信息，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="f310e-144">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f310e-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="f310e-145">Related topics</span></span>
- [<span data-ttu-id="f310e-146">创建指示器</span><span class="sxs-lookup"><span data-stu-id="f310e-146">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="f310e-147">创建文件指示器</span><span class="sxs-lookup"><span data-stu-id="f310e-147">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="f310e-148">创建基于证书的指示器</span><span class="sxs-lookup"><span data-stu-id="f310e-148">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="f310e-149">管理指示器</span><span class="sxs-lookup"><span data-stu-id="f310e-149">Manage indicators</span></span>](indicator-manage.md)
