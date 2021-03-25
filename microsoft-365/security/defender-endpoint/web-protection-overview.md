---
title: Web 保护
description: 了解 Microsoft Defender ATP 中的 Web 保护及其如何保护你的组织
keywords: Web 保护， Web 威胁防护， Web 浏览， 安全， 网络钓鱼， 恶意软件， 攻击， 网站， 网络保护， Edge， Internet Explorer， Chrome， Firefox， Web 浏览器， 恶意网站
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
ms.openlocfilehash: 059f960bae8a5a00f678bb6f52ef217b4f8ed7d6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185989"
---
# <a name="web-protection"></a><span data-ttu-id="db4c9-104">Web 保护</span><span class="sxs-lookup"><span data-stu-id="db4c9-104">Web protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="db4c9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="db4c9-105">**Applies to:**</span></span>
- [<span data-ttu-id="db4c9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="db4c9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="db4c9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db4c9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="db4c9-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="db4c9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="db4c9-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="db4c9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="db4c9-110">Microsoft Defender for Endpoint 中的 Web 保护是一项由 [Web 威胁](web-threat-protection.md) 防护和 Web 内容筛选 [构成的功能](web-content-filtering.md)。</span><span class="sxs-lookup"><span data-stu-id="db4c9-110">Web protection in Microsoft Defender for Endpoint is a capability made up of [Web threat protection](web-threat-protection.md) and [Web content filtering](web-content-filtering.md).</span></span> <span data-ttu-id="db4c9-111">通过 Web 保护，您可以保护设备免受 Web 威胁，并帮助您控制不需要的内容。</span><span class="sxs-lookup"><span data-stu-id="db4c9-111">Web protection lets you secure your devices against web threats and helps you regulate unwanted content.</span></span> <span data-ttu-id="db4c9-112">可以通过访问"报告"或"Web 保护"，在 Microsoft Defender 安全中心 **> Web 保护报告**。</span><span class="sxs-lookup"><span data-stu-id="db4c9-112">You can find Web protection reports in the Microsoft Defender Security Center by going to **Reports > Web protection**.</span></span>

![所有 Web 保护卡的图像](images/web-protection.png)

## <a name="web-threat-protection"></a><span data-ttu-id="db4c9-114">Web 威胁防护</span><span class="sxs-lookup"><span data-stu-id="db4c9-114">Web threat protection</span></span>

<span data-ttu-id="db4c9-115">构成 Web 威胁防护的卡片是一段时间 **的 Web 威胁检测和** **Web 威胁摘要**。</span><span class="sxs-lookup"><span data-stu-id="db4c9-115">The cards that make up web threat protection are **Web threat detections over time** and **Web threat summary**.</span></span>

<span data-ttu-id="db4c9-116">Web 威胁防护包括：</span><span class="sxs-lookup"><span data-stu-id="db4c9-116">Web threat protection includes:</span></span>
- <span data-ttu-id="db4c9-117">全面了解影响组织的 Web 威胁</span><span class="sxs-lookup"><span data-stu-id="db4c9-117">Comprehensive visibility into web threats affecting your organization</span></span>
- <span data-ttu-id="db4c9-118">通过警报和 URL 以及访问这些 URL 的设备的全面配置文件，调查与 Web 相关的威胁活动的功能</span><span class="sxs-lookup"><span data-stu-id="db4c9-118">Investigation capabilities over web-related threat activity through alerts and comprehensive profiles of URLs and the devices that access these URLs</span></span>
- <span data-ttu-id="db4c9-119">跟踪恶意和不需要的网站的常规访问趋势的完整安全功能</span><span class="sxs-lookup"><span data-stu-id="db4c9-119">A full set of security features that track general access trends to malicious and unwanted websites</span></span>

## <a name="web-content-filtering"></a><span data-ttu-id="db4c9-120">Web 内容筛选</span><span class="sxs-lookup"><span data-stu-id="db4c9-120">Web content filtering</span></span>

<span data-ttu-id="db4c9-121">构成 Web 内容筛选的卡片是按类别 **、Web\*\*\*\*内容筛选摘要** 和 **Web 活动摘要表示的 Web 活动**。</span><span class="sxs-lookup"><span data-stu-id="db4c9-121">The cards that comprise web content filtering are **Web activity by category**, **Web content filtering summary**, and **Web activity summary**.</span></span>

<span data-ttu-id="db4c9-122">Web 内容筛选包括：</span><span class="sxs-lookup"><span data-stu-id="db4c9-122">Web content filtering includes:</span></span>
- <span data-ttu-id="db4c9-123">阻止用户访问被阻止类别的网站，无论他们是在内部浏览还是离开</span><span class="sxs-lookup"><span data-stu-id="db4c9-123">Users are prevented from accessing websites in blocked categories, whether they are browsing on-premises or away</span></span>
- <span data-ttu-id="db4c9-124">可以使用 Microsoft Defender for Endpoint 基于角色的访问控制设置中定义的设备组，便捷地将各种策略部署到各种 [用户集](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span><span class="sxs-lookup"><span data-stu-id="db4c9-124">You can conveniently deploy varied policies to various sets of users using the device groups defined in the [Microsoft Defender for Endpoint role-based access control settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="db4c9-125">你可以访问位于相同中心位置的 Web 报告，并查看实际块和 Web 使用情况</span><span class="sxs-lookup"><span data-stu-id="db4c9-125">You can access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="in-this-section"></a><span data-ttu-id="db4c9-126">本节内容</span><span class="sxs-lookup"><span data-stu-id="db4c9-126">In this section</span></span>

<span data-ttu-id="db4c9-127">主题</span><span class="sxs-lookup"><span data-stu-id="db4c9-127">Topic</span></span> | <span data-ttu-id="db4c9-128">说明</span><span class="sxs-lookup"><span data-stu-id="db4c9-128">Description</span></span>
:---|:---
[<span data-ttu-id="db4c9-129">Web 威胁防护</span><span class="sxs-lookup"><span data-stu-id="db4c9-129">Web threat protection</span></span>](web-threat-protection.md) | <span data-ttu-id="db4c9-130">停止对钓鱼网站、恶意软件矢量、攻击网站、不受信任的或低信誉网站以及已阻止的网站的访问。</span><span class="sxs-lookup"><span data-stu-id="db4c9-130">Stop access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked.</span></span>
[<span data-ttu-id="db4c9-131">Web 内容筛选</span><span class="sxs-lookup"><span data-stu-id="db4c9-131">Web content filtering</span></span>](web-content-filtering.md) | <span data-ttu-id="db4c9-132">根据网站的内容类别跟踪和监管对网站的访问。</span><span class="sxs-lookup"><span data-stu-id="db4c9-132">Track and regulate access to websites based on their content categories.</span></span>
