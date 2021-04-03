---
title: 威胁和漏洞管理中的曝光评分
description: 威胁和漏洞管理暴露分数反映了组织对网络安全威胁的易受攻击程度。
keywords: 曝光分数， mdatp 曝光分数， mdatp 电视曝光分数， 组织曝光分数， 电视组织曝光分数， 威胁和漏洞管理， Microsoft Defender for Endpoint
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 34c3122b017b14605fdbb3358f31f73e26361a4d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500129"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a><span data-ttu-id="4953e-104">曝光评分 - 威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="4953e-104">Exposure score - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4953e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4953e-105">**Applies to:**</span></span>

- [<span data-ttu-id="4953e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4953e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="4953e-107">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="4953e-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="4953e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4953e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4953e-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4953e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4953e-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4953e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="4953e-111">你的曝光分数显示在 Microsoft Defender 安全中心的威胁 [和](tvm-dashboard-insights.md) 漏洞管理仪表板中。</span><span class="sxs-lookup"><span data-stu-id="4953e-111">Your exposure score is visible in the [Threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="4953e-112">它反映了你的组织对网络安全威胁的易受攻击程度。</span><span class="sxs-lookup"><span data-stu-id="4953e-112">It reflects how vulnerable your organization is to cybersecurity threats.</span></span> <span data-ttu-id="4953e-113">低曝光分数意味着你的设备更容易被利用。</span><span class="sxs-lookup"><span data-stu-id="4953e-113">Low exposure score means your devices are less vulnerable from exploitation.</span></span>

- <span data-ttu-id="4953e-114">快速了解和识别有关组织中安全状态的高层次要点。</span><span class="sxs-lookup"><span data-stu-id="4953e-114">Quickly understand and identify high-level takeaways about the state of security in your organization.</span></span>
- <span data-ttu-id="4953e-115">检测和响应需要调查或操作以改进当前状态的区域。</span><span class="sxs-lookup"><span data-stu-id="4953e-115">Detect and respond to areas that require investigation or action to improve the current state.</span></span>
- <span data-ttu-id="4953e-116">与对等方和管理人员就安全工作的影响进行沟通。</span><span class="sxs-lookup"><span data-stu-id="4953e-116">Communicate with peers and management about the impact of security efforts.</span></span>

<span data-ttu-id="4953e-117">卡片可让你高级查看一段时间的曝光分数趋势。</span><span class="sxs-lookup"><span data-stu-id="4953e-117">The card gives you a high-level view of your exposure score trend over time.</span></span> <span data-ttu-id="4953e-118">图表中的任何峰值都直观地指示高网络安全威胁暴露，你可以进一步调查。</span><span class="sxs-lookup"><span data-stu-id="4953e-118">Any spikes in the chart give you a visual indication of a high cybersecurity threat exposure that you can investigate further.</span></span>

![曝光分数卡](images/tvm_exp_score.png)

## <a name="how-it-works"></a><span data-ttu-id="4953e-120">运作方式</span><span class="sxs-lookup"><span data-stu-id="4953e-120">How it works</span></span>

<span data-ttu-id="4953e-121">曝光分数分为以下级别：</span><span class="sxs-lookup"><span data-stu-id="4953e-121">The exposure score is broken down into the following levels:</span></span>

- <span data-ttu-id="4953e-122">0–29：低曝光分数</span><span class="sxs-lookup"><span data-stu-id="4953e-122">0–29: low exposure score</span></span>
- <span data-ttu-id="4953e-123">30–69：中等曝光分数</span><span class="sxs-lookup"><span data-stu-id="4953e-123">30–69: medium exposure score</span></span>
- <span data-ttu-id="4953e-124">70–100：高曝光分数</span><span class="sxs-lookup"><span data-stu-id="4953e-124">70–100: high exposure score</span></span>

<span data-ttu-id="4953e-125">你可以根据优先的安全建议修正问题 [，](tvm-security-recommendation.md) 以减少曝光评分。</span><span class="sxs-lookup"><span data-stu-id="4953e-125">You can remediate the issues based on prioritized [security recommendations](tvm-security-recommendation.md) to reduce the exposure score.</span></span> <span data-ttu-id="4953e-126">每个软件都有一些缺陷，这些缺陷会转换为建议，并基于组织的风险确定优先级。</span><span class="sxs-lookup"><span data-stu-id="4953e-126">Each software has weaknesses that are transformed into recommendations and prioritized based on risk to the organization.</span></span>

## <a name="reduce-your-threat-and-vulnerability-exposure"></a><span data-ttu-id="4953e-127">减少威胁和漏洞暴露</span><span class="sxs-lookup"><span data-stu-id="4953e-127">Reduce your threat and vulnerability exposure</span></span>

<span data-ttu-id="4953e-128">通过修正安全建议降低威胁 [和漏洞暴露](tvm-security-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="4953e-128">Lower your threat and vulnerability exposure by remediating [security recommendations](tvm-security-recommendation.md).</span></span> <span data-ttu-id="4953e-129">通过修正最高安全建议（可在威胁和漏洞管理仪表板中查看）来对曝光评分 [产生最大影响](tvm-dashboard-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="4953e-129">Make the most impact to your exposure score by remediating the top security recommendations, which can be viewed in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4953e-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="4953e-130">Related topics</span></span>

- [<span data-ttu-id="4953e-131">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="4953e-131">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="4953e-132">设备的 Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="4953e-132">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="4953e-133">安全性建议</span><span class="sxs-lookup"><span data-stu-id="4953e-133">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="4953e-134">活动日程表</span><span class="sxs-lookup"><span data-stu-id="4953e-134">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
