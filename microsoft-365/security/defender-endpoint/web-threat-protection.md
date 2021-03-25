---
title: 保护组织免受 Web 威胁
description: 了解 Microsoft Defender ATP 中的 Web 保护及其如何保护你的组织。
keywords: Web 保护， Web 威胁防护， Web 浏览， 安全， 网络钓鱼， 恶意软件， 攻击， 网站， 网络保护， Edge， Internet Explorer， Chrome， Firefox， Web 浏览器
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
ms.openlocfilehash: 7754fa586b24fdedaa9691b45f5da4654c882a5b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185977"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="47c2a-104">保护组织免受 Web 威胁</span><span class="sxs-lookup"><span data-stu-id="47c2a-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="47c2a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="47c2a-105">**Applies to:**</span></span>
- [<span data-ttu-id="47c2a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="47c2a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="47c2a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47c2a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="47c2a-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="47c2a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="47c2a-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="47c2a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="47c2a-110">Web 威胁防护是 [Defender](web-protection-overview.md) for Endpoint 中的 Web 保护的一部分。</span><span class="sxs-lookup"><span data-stu-id="47c2a-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="47c2a-111">它 [使用网络保护](network-protection.md) 保护你的设备免受 Web 威胁。</span><span class="sxs-lookup"><span data-stu-id="47c2a-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="47c2a-112">通过与 Microsoft Edge 和热门第三方浏览器（如 Chrome 和 Firefox）集成，Web 威胁防护无需 Web 代理即可阻止 Web 威胁，并可在设备离开或位于本地时保护设备。</span><span class="sxs-lookup"><span data-stu-id="47c2a-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="47c2a-113">Web 威胁防护会停止对钓鱼网站、恶意软件矢量、攻击网站、不受信任的或低信誉网站以及自定义指示器列表中阻止 [的网站的访问](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="47c2a-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="47c2a-114">设备可能需要一小时才能收到新的客户指标。</span><span class="sxs-lookup"><span data-stu-id="47c2a-114">It can take up to an hour for devices to receive new customer indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="47c2a-115">先决条件</span><span class="sxs-lookup"><span data-stu-id="47c2a-115">Prerequisites</span></span>
<span data-ttu-id="47c2a-116">Web 保护使用网络保护在 Microsoft Edge 和第三方 Web 浏览器上提供 Web 浏览安全性。</span><span class="sxs-lookup"><span data-stu-id="47c2a-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="47c2a-117">若要在设备上打开网络保护，请运行：</span><span class="sxs-lookup"><span data-stu-id="47c2a-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="47c2a-118">在 Web 网络保护下编辑 Defender for Endpoint **&，** 以在部署或重新部署网络保护之前启用网络保护。</span><span class="sxs-lookup"><span data-stu-id="47c2a-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="47c2a-119">了解如何查看和分配 Defender for Endpoint 安全基线</span><span class="sxs-lookup"><span data-stu-id="47c2a-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="47c2a-120">使用 Intune 设备配置、SCCM、组策略或 MDM 解决方案打开网络保护。</span><span class="sxs-lookup"><span data-stu-id="47c2a-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="47c2a-121">阅读有关启用网络保护的更多信息</span><span class="sxs-lookup"><span data-stu-id="47c2a-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="47c2a-122">如果将网络保护设置为"仅 **审核"，** 则阻止将不可用。</span><span class="sxs-lookup"><span data-stu-id="47c2a-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="47c2a-123">此外，你将能够检测并记录仅在 Microsoft Edge 上访问恶意和不需要的网站的尝试。</span><span class="sxs-lookup"><span data-stu-id="47c2a-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="47c2a-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="47c2a-124">Related topics</span></span>

- [<span data-ttu-id="47c2a-125">Web 保护概述</span><span class="sxs-lookup"><span data-stu-id="47c2a-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="47c2a-126">Web 威胁防护</span><span class="sxs-lookup"><span data-stu-id="47c2a-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="47c2a-127">监视 Web 安全</span><span class="sxs-lookup"><span data-stu-id="47c2a-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="47c2a-128">响应 Web 威胁</span><span class="sxs-lookup"><span data-stu-id="47c2a-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="47c2a-129">网络保护</span><span class="sxs-lookup"><span data-stu-id="47c2a-129">Network protection</span></span>](network-protection.md)
