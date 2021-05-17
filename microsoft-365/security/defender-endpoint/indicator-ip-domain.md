---
title: 创建 IP 和 URL/域指示器
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
ms.openlocfilehash: d468a77d2c1ab4f1b363e2e91b6e8507a5390d93
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198479"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="28795-104">创建 IP 和 URL/域指示器</span><span class="sxs-lookup"><span data-stu-id="28795-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="28795-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="28795-105">**Applies to:**</span></span>
- [<span data-ttu-id="28795-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="28795-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="28795-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28795-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="28795-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="28795-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="28795-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="28795-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="28795-110">Defender for Endpoint 可以通过适用于 Microsoft 浏览器的 Windows Defender SmartScreen，以及针对非 Microsoft 浏览器或在浏览器外进行调用的网络保护，阻止 Microsoft 视为恶意 IP/URL。</span><span class="sxs-lookup"><span data-stu-id="28795-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="28795-111">针对这一点的威胁情报数据集已由 Microsoft 管理。</span><span class="sxs-lookup"><span data-stu-id="28795-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="28795-112">通过创建 IP 和 URL 或域的指示器，你现在可以基于自己的威胁情报允许或阻止 IP、URL 或域。</span><span class="sxs-lookup"><span data-stu-id="28795-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="28795-113">如果你认为某些组的风险大于或低于其他组，可以通过设置页面或计算机组来这样做。</span><span class="sxs-lookup"><span data-stu-id="28795-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="28795-114">不支持无Inter-Domain IP (CIDR) 表示法。</span><span class="sxs-lookup"><span data-stu-id="28795-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="28795-115">开始之前</span><span class="sxs-lookup"><span data-stu-id="28795-115">Before you begin</span></span>
<span data-ttu-id="28795-116">在创建 IPS、URL 或域的指示器之前，了解以下先决条件非常重要：</span><span class="sxs-lookup"><span data-stu-id="28795-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="28795-117">URL/IP 允许和阻止依赖于 Defender for Endpoint 组件网络保护在阻止模式下启用。</span><span class="sxs-lookup"><span data-stu-id="28795-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="28795-118">有关网络保护和配置说明详细信息，请参阅启用 [网络保护](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="28795-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="28795-119">反恶意软件客户端版本必须为 4.18.1906.x 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="28795-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="28795-120">在 Windows 10 版本 1709 或更高版本的计算机中受支持。</span><span class="sxs-lookup"><span data-stu-id="28795-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="28795-121">确保自定义 **网络指示器在** 高级Microsoft Defender 安全中心 > 设置 >**中启用**。</span><span class="sxs-lookup"><span data-stu-id="28795-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="28795-122">有关详细信息，请参阅高级 [功能](advanced-features.md)。</span><span class="sxs-lookup"><span data-stu-id="28795-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="28795-123">有关 iOS 上的指示器支持，请参阅 [配置自定义指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)。</span><span class="sxs-lookup"><span data-stu-id="28795-123">For support of indicators on iOS, see [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="28795-124">只能将外部 IP 添加到指示器列表。</span><span class="sxs-lookup"><span data-stu-id="28795-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="28795-125">无法为内部 IP 创建指示器。</span><span class="sxs-lookup"><span data-stu-id="28795-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="28795-126">对于 Web 保护方案，我们建议使用 Web 保护中的内置Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="28795-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="28795-127">Microsoft Edge网络保护来检查网络流量[](network-protection.md)，并允许阻止 TCP、HTTP 和 HTTPS (TLS) 。</span><span class="sxs-lookup"><span data-stu-id="28795-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="28795-128">如果存在冲突的 URL 指示器策略，则应用较长的路径。</span><span class="sxs-lookup"><span data-stu-id="28795-128">If there are conflicting URL indicator policies, the longer path is applied.</span></span> <span data-ttu-id="28795-129">例如，URL 指示器策略 `https:\\support.microsoft.com/en-us/office` 优先于 URL 指示器策略 `https:\\support.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="28795-129">For example, the URL indicator policy `https:\\support.microsoft.com/en-us/office` takes precedence over the URL indicator policy `https:\\support.microsoft.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="28795-130">对于所有其他进程，Web 保护方案利用网络保护进行检查和强制执行：</span><span class="sxs-lookup"><span data-stu-id="28795-130">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> 
> - <span data-ttu-id="28795-131">所有三种协议均支持 IP</span><span class="sxs-lookup"><span data-stu-id="28795-131">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="28795-132">没有 CIDR 块或 IP 范围 (仅支持单个 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="28795-132">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="28795-133">只有在第 (浏览器、边缘) ，才能阻止加密的 URL (Internet Explorer完整路径) </span><span class="sxs-lookup"><span data-stu-id="28795-133">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="28795-134">加密的 URL (FQDN) 可以在第一方浏览器或边缘 (Internet Explorer外部阻止) </span><span class="sxs-lookup"><span data-stu-id="28795-134">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="28795-135">完整 URL 路径块可以应用于域级别以及所有未加密的 URL</span><span class="sxs-lookup"><span data-stu-id="28795-135">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="28795-136">延迟时间可能最多为 2 小时 (通常) 操作和阻止的 URL 和 IP 之间的延迟时间通常较少。</span><span class="sxs-lookup"><span data-stu-id="28795-136">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="28795-137">从设置页面为 IP、URL 或域创建指示器</span><span class="sxs-lookup"><span data-stu-id="28795-137">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="28795-138">在导航窗格中，选择 **"设置**  >  **标记"。**</span><span class="sxs-lookup"><span data-stu-id="28795-138">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="28795-139">选择 **"IP 地址或 URL/域"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="28795-139">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="28795-140">选择 **"添加项目"。**</span><span class="sxs-lookup"><span data-stu-id="28795-140">Select **Add item**.</span></span>

4. <span data-ttu-id="28795-141">指定以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="28795-141">Specify the following details:</span></span>
   - <span data-ttu-id="28795-142">Indicator - 指定实体详细信息并定义指示器的过期时间。</span><span class="sxs-lookup"><span data-stu-id="28795-142">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="28795-143">操作 - 指定要采取的操作并提供说明。</span><span class="sxs-lookup"><span data-stu-id="28795-143">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="28795-144">Scope - 定义计算机组的范围。</span><span class="sxs-lookup"><span data-stu-id="28795-144">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="28795-145">查看"摘要"选项卡中的详细信息，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="28795-145">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="28795-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="28795-146">Related topics</span></span>
- [<span data-ttu-id="28795-147">创建指示器</span><span class="sxs-lookup"><span data-stu-id="28795-147">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="28795-148">创建文件指示器</span><span class="sxs-lookup"><span data-stu-id="28795-148">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="28795-149">创建基于证书的指示器</span><span class="sxs-lookup"><span data-stu-id="28795-149">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="28795-150">管理指示器</span><span class="sxs-lookup"><span data-stu-id="28795-150">Manage indicators</span></span>](indicator-manage.md)
