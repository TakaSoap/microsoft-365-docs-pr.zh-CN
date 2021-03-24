---
title: 响应 Microsoft Defender ATP 中的 Web 威胁
description: 响应与恶意和不需要的网站相关的警报。 了解 Web 威胁防护如何通过最终用户的 Web 浏览器和 Windows 通知通知最终用户
keywords: Web 保护， Web 威胁防护， Web 浏览， 警报， 响应， 安全性， 网络钓鱼， 恶意软件， 攻击， 网站， 网络保护， Edge， Internet Explorer， Chrome， Firefox， Web 浏览器， 通知， 最终用户， Windows 通知， 阻止页面，
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 339944b94ca55c5d73fafaabfe3f7bc26dafe7bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055312"
---
# <a name="respond-to-web-threats"></a><span data-ttu-id="f3f39-105">响应 Web 威胁</span><span class="sxs-lookup"><span data-stu-id="f3f39-105">Respond to web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f3f39-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f3f39-106">**Applies to:**</span></span>
- [<span data-ttu-id="f3f39-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f3f39-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="f3f39-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3f39-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f3f39-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f3f39-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f3f39-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f3f39-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="f3f39-111">通过 Microsoft Defender for Endpoint 中的 Web 保护，你可以高效地调查和响应自定义指示器列表中与恶意网站和网站相关的警报。</span><span class="sxs-lookup"><span data-stu-id="f3f39-111">Web protection in Microsoft Defender for Endpoint lets you efficiently investigate and respond to alerts related to malicious websites and websites in your custom indicator list.</span></span>

## <a name="view-web-threat-alerts"></a><span data-ttu-id="f3f39-112">查看 Web 威胁警报</span><span class="sxs-lookup"><span data-stu-id="f3f39-112">View web threat alerts</span></span>
<span data-ttu-id="f3f39-113">Microsoft Defender for Endpoint 针对恶意 [或](manage-alerts.md) 可疑 Web 活动生成以下警报：</span><span class="sxs-lookup"><span data-stu-id="f3f39-113">Microsoft Defender for Endpoint generates the following [alerts](manage-alerts.md) for malicious or suspicious web activity:</span></span>
- <span data-ttu-id="f3f39-114">**受网络保护阻止的** 可疑连接 - 当在阻止模式下网络保护停止尝试访问自定义指示器列表中的恶意网站或网站时，将 *生成此* 警报</span><span class="sxs-lookup"><span data-stu-id="f3f39-114">**Suspicious connection blocked by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is *stopped* by network protection in *block* mode</span></span>
- <span data-ttu-id="f3f39-115">**网络保护检测到** 的可疑连接 - 当网络保护在仅审核模式下检测到尝试访问自定义指示器列表中的恶意网站或网站时 *，将生成此* 警报</span><span class="sxs-lookup"><span data-stu-id="f3f39-115">**Suspicious connection detected by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is detected by network protection in *audit only* mode</span></span>

<span data-ttu-id="f3f39-116">每个警报都提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="f3f39-116">Each alert provides the following information:</span></span> 
- <span data-ttu-id="f3f39-117">尝试访问阻止的网站的设备</span><span class="sxs-lookup"><span data-stu-id="f3f39-117">Device that attempted to access the blocked website</span></span>
- <span data-ttu-id="f3f39-118">用于发送 Web 请求的应用程序或程序</span><span class="sxs-lookup"><span data-stu-id="f3f39-118">Application or program used to send the web request</span></span>
- <span data-ttu-id="f3f39-119">自定义指示器列表中的恶意 URL 或 URL</span><span class="sxs-lookup"><span data-stu-id="f3f39-119">Malicious URL or URL in the custom indicator list</span></span>
- <span data-ttu-id="f3f39-120">针对响应器的建议操作</span><span class="sxs-lookup"><span data-stu-id="f3f39-120">Recommended actions for responders</span></span>

![与 Web 威胁防护相关的警报的图像](images/wtp-alert.png)

>[!Note]
><span data-ttu-id="f3f39-122">为了减少警报量，Microsoft Defender for Endpoint 每天将同一设备上同一域的 Web 威胁检测合并为单个警报。</span><span class="sxs-lookup"><span data-stu-id="f3f39-122">To reduce the volume of alerts, Microsoft Defender for Endpoint consolidates web threat detections for the same domain on the same device each day to a single alert.</span></span> <span data-ttu-id="f3f39-123">仅生成一个警报，并计入 [Web 保护报告](web-protection-monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="f3f39-123">Only one alert is generated and counted into the [web protection report](web-protection-monitoring.md).</span></span>

## <a name="inspect-website-details"></a><span data-ttu-id="f3f39-124">检查网站详细信息</span><span class="sxs-lookup"><span data-stu-id="f3f39-124">Inspect website details</span></span>
<span data-ttu-id="f3f39-125">您可以通过在警报中选择网站的 URL 或域来深入了解。</span><span class="sxs-lookup"><span data-stu-id="f3f39-125">You can dive deeper by selecting the URL or domain of the website in the alert.</span></span> <span data-ttu-id="f3f39-126">这将打开一个包含各种信息的特定 URL 或域的页面，其中包括：</span><span class="sxs-lookup"><span data-stu-id="f3f39-126">This opens a page about that particular URL or domain with various information, including:</span></span>
- <span data-ttu-id="f3f39-127">尝试访问网站的设备</span><span class="sxs-lookup"><span data-stu-id="f3f39-127">Devices that attempted to access website</span></span>
- <span data-ttu-id="f3f39-128">与网站相关的事件和警报</span><span class="sxs-lookup"><span data-stu-id="f3f39-128">Incidents and alerts related to the website</span></span>
- <span data-ttu-id="f3f39-129">在组织的活动中查看网站频率</span><span class="sxs-lookup"><span data-stu-id="f3f39-129">How frequent the website was seen in events in your organization</span></span>

    ![域或 URL 实体详细信息页面的图像](images/wtp-website-details.png)

[<span data-ttu-id="f3f39-131">详细了解 URL 或域实体页面</span><span class="sxs-lookup"><span data-stu-id="f3f39-131">Learn more about URL or domain entity pages</span></span>](investigate-domain.md)

## <a name="inspect-the-device"></a><span data-ttu-id="f3f39-132">检查设备</span><span class="sxs-lookup"><span data-stu-id="f3f39-132">Inspect the device</span></span>
<span data-ttu-id="f3f39-133">还可以检查尝试访问阻止的 URL 的设备。</span><span class="sxs-lookup"><span data-stu-id="f3f39-133">You can also check the device that attempted to access a blocked URL.</span></span> <span data-ttu-id="f3f39-134">在警报页面上选择设备名称将打开一个包含有关设备的综合信息的页面。</span><span class="sxs-lookup"><span data-stu-id="f3f39-134">Selecting the name of the device on the alert page opens a page with comprehensive information about the device.</span></span>

[<span data-ttu-id="f3f39-135">了解有关设备实体页面的信息</span><span class="sxs-lookup"><span data-stu-id="f3f39-135">Learn more about device entity pages</span></span>](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a><span data-ttu-id="f3f39-136">针对最终用户的 Web 浏览器和 Windows 通知</span><span class="sxs-lookup"><span data-stu-id="f3f39-136">Web browser and Windows notifications for end users</span></span>

<span data-ttu-id="f3f39-137">借助适用于终结点的 Microsoft Defender 中的 Web 保护，将阻止最终用户使用 Microsoft Edge 或其他浏览器访问恶意或不需要的网站。</span><span class="sxs-lookup"><span data-stu-id="f3f39-137">With web protection in Microsoft Defender for Endpoint, your end users will be prevented from visiting malicious or unwanted websites using Microsoft Edge or other browsers.</span></span> <span data-ttu-id="f3f39-138">由于阻止是由网络 [保护执行的](network-protection.md)，因此他们将从 Web 浏览器看到一个常规错误。</span><span class="sxs-lookup"><span data-stu-id="f3f39-138">Because blocking is performed by [network protection](network-protection.md), they will see a generic error from the web browser.</span></span> <span data-ttu-id="f3f39-139">他们还将看到来自 Windows 的通知。</span><span class="sxs-lookup"><span data-stu-id="f3f39-139">They will also see a notification from Windows.</span></span>

<span data-ttu-id="f3f39-140">![Microsoft Edge 显示 403 错误和 Microsoft Edge 上阻止的 Windows 通知 ](images/wtp-browser-blocking-page.png)
 *Web 威胁的图像*</span><span class="sxs-lookup"><span data-stu-id="f3f39-140">![Image of Microsoft Edge showing a 403 error and the Windows notification](images/wtp-browser-blocking-page.png)
*Web threat blocked on Microsoft Edge*</span></span>

<span data-ttu-id="f3f39-141">![显示安全连接警告和 Chrome 上阻止的 Windows 通知 Web 威胁的 ](images/wtp-chrome-browser-blocking-page.png)
 *Chrome Web 浏览器的图像*</span><span class="sxs-lookup"><span data-stu-id="f3f39-141">![Image of Chrome web browser showing a secure connection warning and the Windows notification](images/wtp-chrome-browser-blocking-page.png)
*Web threat blocked on Chrome*</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3f39-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="f3f39-142">Related topics</span></span>
- [<span data-ttu-id="f3f39-143">Web 保护概述</span><span class="sxs-lookup"><span data-stu-id="f3f39-143">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="f3f39-144">Web 内容筛选</span><span class="sxs-lookup"><span data-stu-id="f3f39-144">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="f3f39-145">Web 威胁防护</span><span class="sxs-lookup"><span data-stu-id="f3f39-145">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="f3f39-146">监视 Web 安全</span><span class="sxs-lookup"><span data-stu-id="f3f39-146">Monitor web security</span></span>](web-protection-monitoring.md)
