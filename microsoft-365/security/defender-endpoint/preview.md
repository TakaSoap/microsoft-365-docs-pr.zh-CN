---
title: 适用于终结点的 Microsoft Defender 预览功能
description: 了解如何访问适用于终结点预览功能的 Microsoft Defender。
keywords: 预览， 预览体验， 适用于终结点的 Microsoft Defender， 功能， 更新
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0ed494cc29eb990430be590e62db5f0365ace494
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322421"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="a7e48-104">适用于终结点的 Microsoft Defender 预览功能</span><span class="sxs-lookup"><span data-stu-id="a7e48-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a7e48-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a7e48-105">**Applies to:**</span></span>
- [<span data-ttu-id="a7e48-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a7e48-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a7e48-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7e48-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a7e48-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a7e48-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a7e48-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a7e48-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="a7e48-110">Defender for Endpoint 服务会不断更新，以包含新功能增强功能和功能。</span><span class="sxs-lookup"><span data-stu-id="a7e48-110">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="a7e48-111">了解 Defender for Endpoint 预览版中的新功能，并首先通过打开预览体验来试用即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="a7e48-111">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="a7e48-112">在此页面更新时收到通知，方法为将以下 URL 复制并粘贴到源阅读器中： `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="a7e48-112">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="a7e48-113">有关已普遍提供的新功能详细信息，请参阅 Defender for [Endpoint 中的新增功能](whats-new-in-microsoft-defender-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e48-113">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="a7e48-114">您需要了解哪些信息</span><span class="sxs-lookup"><span data-stu-id="a7e48-114">What you need to know</span></span>

<span data-ttu-id="a7e48-115">使用公共预览版中的功能时，这些功能：</span><span class="sxs-lookup"><span data-stu-id="a7e48-115">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="a7e48-116">功能可能受限或受限。</span><span class="sxs-lookup"><span data-stu-id="a7e48-116">May have restricted or limited functionality.</span></span> <span data-ttu-id="a7e48-117">例如，此功能可能仅适用于一个平台。</span><span class="sxs-lookup"><span data-stu-id="a7e48-117">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="a7e48-118">通常先完成功能更改，然后再在 GA (正式) 。</span><span class="sxs-lookup"><span data-stu-id="a7e48-118">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="a7e48-119">完全受 Microsoft 支持。</span><span class="sxs-lookup"><span data-stu-id="a7e48-119">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="a7e48-120">可能仅在选定的地理区域或云环境中可用。</span><span class="sxs-lookup"><span data-stu-id="a7e48-120">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="a7e48-121">例如，此功能可能不存在于政府云中。</span><span class="sxs-lookup"><span data-stu-id="a7e48-121">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="a7e48-122">预览版中的单个功能可能具有更多用法和支持限制。</span><span class="sxs-lookup"><span data-stu-id="a7e48-122">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="a7e48-123">如果是这样，此信息通常会记录在功能文档中。</span><span class="sxs-lookup"><span data-stu-id="a7e48-123">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="a7e48-124">预览版本提供标准支持级别，建议用于生产工作负载。</span><span class="sxs-lookup"><span data-stu-id="a7e48-124">The preview versions are provided with a standard support level, and it is recommended for production workloads.</span></span> 



## <a name="turn-on-preview-features"></a><span data-ttu-id="a7e48-125">启用预览功能</span><span class="sxs-lookup"><span data-stu-id="a7e48-125">Turn on preview features</span></span>

<span data-ttu-id="a7e48-126">你有权访问即将推出的功能，可以在这些功能全面发布之前提供反馈以帮助改善整体体验。</span><span class="sxs-lookup"><span data-stu-id="a7e48-126">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="a7e48-127">启用预览体验设置，以率先体验即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="a7e48-127">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="a7e48-128">在导航窗格中，选择 **"设置**  >  **高级功能**  >  **预览功能"。**</span><span class="sxs-lookup"><span data-stu-id="a7e48-128">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="a7e48-129">切换 **开和关** 之间的 **设置，** 然后选择 **保存首选项**。</span><span class="sxs-lookup"><span data-stu-id="a7e48-129">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="a7e48-130">预览功能</span><span class="sxs-lookup"><span data-stu-id="a7e48-130">Preview features</span></span>

<span data-ttu-id="a7e48-131">预览版中包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="a7e48-131">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="a7e48-132">Web 内容筛选</span><span class="sxs-lookup"><span data-stu-id="a7e48-132">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="a7e48-133">Web 内容筛选是 Microsoft Defender for Endpoint 中的 Web 保护功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="a7e48-133">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a7e48-134">它使组织能够根据网站的内容类别跟踪和监管对网站的访问。</span><span class="sxs-lookup"><span data-stu-id="a7e48-134">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="a7e48-135">许多此类网站虽然不是恶意网站，但由于合规性法规、带宽使用情况或其他问题，可能存在问题。</span><span class="sxs-lookup"><span data-stu-id="a7e48-135">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="a7e48-136">设备运行状况和合规性报告</span><span class="sxs-lookup"><span data-stu-id="a7e48-136">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="a7e48-137">设备运行状况和合规性报告提供有关组织中设备的高级别信息。</span><span class="sxs-lookup"><span data-stu-id="a7e48-137">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="a7e48-138">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a7e48-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a7e48-139">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a7e48-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
