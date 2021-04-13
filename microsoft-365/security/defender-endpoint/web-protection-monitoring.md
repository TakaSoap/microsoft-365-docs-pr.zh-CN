---
title: 在 Microsoft Defender for Endpoint 中监视 Web 浏览安全性
description: 使用 Microsoft Defender for Endpoint 中的 Web 保护监视 Web 浏览安全性
keywords: Web 保护， Web 威胁防护， Web 浏览， 监视， 报告， 卡， 域列表， 安全性， 网络钓鱼， 恶意软件， 攻击， 网站， 网络保护， Edge， Internet Explorer， Chrome， Firefox， Web 浏览器
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ee6388c779d2c5bc09a82f5e9064d1b981e885cb
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687419"
---
# <a name="monitor-web-browsing-security"></a><span data-ttu-id="f498c-104">监视 Web 浏览安全性</span><span class="sxs-lookup"><span data-stu-id="f498c-104">Monitor web browsing security</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f498c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f498c-105">**Applies to:**</span></span>
- [<span data-ttu-id="f498c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f498c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f498c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f498c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f498c-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f498c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f498c-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f498c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="f498c-110">通过 Web 保护，可以通过 Microsoft Defender 安全中心中"报告 web > Web 保护" **下的报告监视** 组织的 Web 浏览安全。</span><span class="sxs-lookup"><span data-stu-id="f498c-110">Web protection lets you monitor your organization’s web browsing security through reports under **Reports > Web protection** in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="f498c-111">该报告包含提供 Web 威胁检测统计信息的卡片。</span><span class="sxs-lookup"><span data-stu-id="f498c-111">The report contains cards that provide web threat detection statistics.</span></span>

- <span data-ttu-id="f498c-112">**随着时间的推移进行** Web 威胁防护检测 - 此趋势卡片显示在所选时间段（"最近 30 天 (最近 30 天、过去 3 个月、过去 6 个月）内按类型检测到的 Web 威胁) </span><span class="sxs-lookup"><span data-stu-id="f498c-112">**Web threat protection detections over time** - this trending card displays the number of web threats detected by type during the selected time period (Last 30 days, Last 3 months, Last 6 months)</span></span>
 
    ![显示一段时间的 Web 威胁防护检测的卡片图像](images/wtp-blocks-over-time.png)

- <span data-ttu-id="f498c-114">**Web 威胁防护摘要** - 此卡片显示过去 30 天内的 Web 威胁检测总数，显示不同类型的 Web 威胁的分布情况。</span><span class="sxs-lookup"><span data-stu-id="f498c-114">**Web threat protection summary** - this card displays the total web threat detections in the past 30 days, showing distribution across the different types of web threats.</span></span> <span data-ttu-id="f498c-115">选择切片将打开通过恶意或不需要的网站找到的域列表。</span><span class="sxs-lookup"><span data-stu-id="f498c-115">Selecting a slice opens the list of the domains that were found with malicious or unwanted websites.</span></span>

    ![显示 Web 威胁防护摘要的卡片图像](images/wtp-summary.png)

>[!Note]
><span data-ttu-id="f498c-117">阻止可能最多需要 12 个小时才能反映在卡或域列表中。</span><span class="sxs-lookup"><span data-stu-id="f498c-117">It can take up to 12 hours before a block is reflected in the cards or the domain list.</span></span>

## <a name="types-of-web-threats"></a><span data-ttu-id="f498c-118">Web 威胁的类型</span><span class="sxs-lookup"><span data-stu-id="f498c-118">Types of web threats</span></span>

<span data-ttu-id="f498c-119">Web 保护将恶意和不需要的网站分类为：</span><span class="sxs-lookup"><span data-stu-id="f498c-119">Web protection categorizes malicious and unwanted websites as:</span></span>

- <span data-ttu-id="f498c-120">**网络钓鱼** - 包含欺骗性 Web 表单和其他网络钓鱼机制的网站，旨在欺骗用户泄露凭据和其他敏感信息</span><span class="sxs-lookup"><span data-stu-id="f498c-120">**Phishing** - websites that contain spoofed web forms and other phishing mechanisms designed to trick users into divulging credentials and other sensitive information</span></span>
- <span data-ttu-id="f498c-121">**恶意** - 托管恶意软件和攻击代码的网站</span><span class="sxs-lookup"><span data-stu-id="f498c-121">**Malicious** - websites that host malware and exploit code</span></span>
- <span data-ttu-id="f498c-122">**自定义指示器** - 已添加到用于阻止的自定义指示器列表的 URL [或](manage-indicators.md) 域的网站</span><span class="sxs-lookup"><span data-stu-id="f498c-122">**Custom indicator** - websites whose URLs or domains you've added to your [custom indicator list](manage-indicators.md) for blocking</span></span>

## <a name="view-the-domain-list"></a><span data-ttu-id="f498c-123">查看域列表</span><span class="sxs-lookup"><span data-stu-id="f498c-123">View the domain list</span></span>

<span data-ttu-id="f498c-124">选择 Web 威胁防护摘要卡中的特定 **Web 威胁** 类别以打开 **"域"** 页面。</span><span class="sxs-lookup"><span data-stu-id="f498c-124">Select a specific web threat category in the **Web threat protection summary** card to open the **Domains** page.</span></span> <span data-ttu-id="f498c-125">此页面显示该威胁类别下的域列表。</span><span class="sxs-lookup"><span data-stu-id="f498c-125">This page displays the list of the domains under that threat category.</span></span> <span data-ttu-id="f498c-126">该页面提供每个域的以下信息：</span><span class="sxs-lookup"><span data-stu-id="f498c-126">The page provides the following information for each domain:</span></span>

- <span data-ttu-id="f498c-127">**访问计数** - 域中 URL 的请求数</span><span class="sxs-lookup"><span data-stu-id="f498c-127">**Access count** - number of requests for URLs in the domain</span></span>
- <span data-ttu-id="f498c-128">**块** - 阻止请求次数</span><span class="sxs-lookup"><span data-stu-id="f498c-128">**Blocks** - number of times requests were blocked</span></span>
- <span data-ttu-id="f498c-129">**访问趋势** - 访问尝试次数的变化</span><span class="sxs-lookup"><span data-stu-id="f498c-129">**Access trend** - change in number of access attempts</span></span>
- <span data-ttu-id="f498c-130">**威胁类别** - Web 威胁的类型</span><span class="sxs-lookup"><span data-stu-id="f498c-130">**Threat category** - type of web threat</span></span>
- <span data-ttu-id="f498c-131">**设备** - 尝试访问的设备数</span><span class="sxs-lookup"><span data-stu-id="f498c-131">**Devices** - number of devices with access attempts</span></span>

<span data-ttu-id="f498c-132">选择一个域以查看尝试访问该域中的 URL 的设备列表和 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="f498c-132">Select a domain to view the list of devices that have attempted to access URLs in that domain and the list of URLs.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f498c-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="f498c-133">Related topics</span></span>

- [<span data-ttu-id="f498c-134">Web 保护功能概述</span><span class="sxs-lookup"><span data-stu-id="f498c-134">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="f498c-135">Web 内容筛选</span><span class="sxs-lookup"><span data-stu-id="f498c-135">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="f498c-136">Web 威胁防护功能</span><span class="sxs-lookup"><span data-stu-id="f498c-136">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="f498c-137">响应 web 威胁</span><span class="sxs-lookup"><span data-stu-id="f498c-137">Respond to web threats</span></span>](web-protection-response.md)
