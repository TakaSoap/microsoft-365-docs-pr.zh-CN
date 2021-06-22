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
ms.openlocfilehash: 65edf54ea0bf5cb0a0210dd306db07c756149f65
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062136"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="2724f-104">适用于终结点的 Microsoft Defender 预览功能</span><span class="sxs-lookup"><span data-stu-id="2724f-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="2724f-105">预览版本在没有服务级别协议的情况下提供，不建议用于生产工作负载。</span><span class="sxs-lookup"><span data-stu-id="2724f-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="2724f-106">某些功能可能不受支持，或者可能具有受限功能。</span><span class="sxs-lookup"><span data-stu-id="2724f-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="2724f-107">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2724f-107">**Applies to:**</span></span>
- [<span data-ttu-id="2724f-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2724f-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2724f-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2724f-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2724f-110">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2724f-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2724f-111">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="2724f-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="2724f-112">Defender for Endpoint 服务会不断更新，以包含新功能增强功能和功能。</span><span class="sxs-lookup"><span data-stu-id="2724f-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="2724f-113">了解 Defender for Endpoint 预览版中的新功能，并首先通过打开预览体验来试用即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="2724f-113">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="2724f-114">在此页面更新时收到通知，方法为将以下 URL 复制并粘贴到源阅读器中： `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="2724f-114">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="2724f-115">有关已普遍提供的新功能详细信息，请参阅 Defender for [Endpoint 中的新增功能](whats-new-in-microsoft-defender-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="2724f-115">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="2724f-116">启用预览功能</span><span class="sxs-lookup"><span data-stu-id="2724f-116">Turn on preview features</span></span>

<span data-ttu-id="2724f-117">你有权访问即将推出的功能，可以在这些功能全面发布之前提供反馈以帮助改善整体体验。</span><span class="sxs-lookup"><span data-stu-id="2724f-117">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="2724f-118">启用预览体验设置，以率先体验即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="2724f-118">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="2724f-119">在导航窗格中，选择 **"设置**  >  **高级功能**  >  **预览功能"。**</span><span class="sxs-lookup"><span data-stu-id="2724f-119">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="2724f-120">切换 **开和关** 之间的 **设置，** 然后选择 **保存首选项**。</span><span class="sxs-lookup"><span data-stu-id="2724f-120">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="2724f-121">预览功能</span><span class="sxs-lookup"><span data-stu-id="2724f-121">Preview features</span></span>

<span data-ttu-id="2724f-122">预览版中包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="2724f-122">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="2724f-123">Web 内容筛选</span><span class="sxs-lookup"><span data-stu-id="2724f-123">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="2724f-124">Web 内容筛选是 Microsoft Defender for Endpoint 中的 Web 保护功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="2724f-124">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="2724f-125">它使组织能够根据网站的内容类别跟踪和监管对网站的访问。</span><span class="sxs-lookup"><span data-stu-id="2724f-125">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="2724f-126">许多此类网站虽然不是恶意网站，但由于合规性法规、带宽使用情况或其他问题，可能存在问题。</span><span class="sxs-lookup"><span data-stu-id="2724f-126">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="2724f-127">设备运行状况和合规性报告</span><span class="sxs-lookup"><span data-stu-id="2724f-127">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="2724f-128">设备运行状况和合规性报告提供有关组织中设备的高级别信息。</span><span class="sxs-lookup"><span data-stu-id="2724f-128">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="2724f-129">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2724f-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2724f-130">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="2724f-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
