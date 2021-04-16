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
ms.openlocfilehash: 817ed5e33505f691b11970e3da4c956afa7dc76c
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861055"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="5af0b-104">适用于终结点的 Microsoft Defender 预览功能</span><span class="sxs-lookup"><span data-stu-id="5af0b-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="5af0b-105">预览版本在没有服务级别协议的情况下提供，不建议用于生产工作负载。</span><span class="sxs-lookup"><span data-stu-id="5af0b-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="5af0b-106">某些功能可能不受支持，或者可能具有受限功能。</span><span class="sxs-lookup"><span data-stu-id="5af0b-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="5af0b-107">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5af0b-107">**Applies to:**</span></span>
- [<span data-ttu-id="5af0b-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5af0b-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5af0b-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5af0b-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5af0b-110">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5af0b-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5af0b-111">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5af0b-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="5af0b-112">Defender for Endpoint 服务会不断更新，以包含新功能增强功能和功能。</span><span class="sxs-lookup"><span data-stu-id="5af0b-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="5af0b-113">了解 Defender for Endpoint 预览版中的新功能，并首先通过打开预览体验来试用即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="5af0b-113">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="5af0b-114">在此页面更新时收到通知，方法为将以下 URL 复制并粘贴到源阅读器中： `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span><span class="sxs-lookup"><span data-stu-id="5af0b-114">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span></span>

<span data-ttu-id="5af0b-115">有关已普遍提供的新功能详细信息，请参阅 Defender for [Endpoint 中的新增功能](whats-new-in-microsoft-defender-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="5af0b-115">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="5af0b-116">启用预览功能</span><span class="sxs-lookup"><span data-stu-id="5af0b-116">Turn on preview features</span></span>

<span data-ttu-id="5af0b-117">你有权访问即将推出的功能，可以在这些功能全面发布之前提供反馈以帮助改善整体体验。</span><span class="sxs-lookup"><span data-stu-id="5af0b-117">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="5af0b-118">启用预览体验设置，以率先体验即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="5af0b-118">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="5af0b-119">在导航窗格中，选择"**设置**  >  **""高级功能**  >  **预览功能"。**</span><span class="sxs-lookup"><span data-stu-id="5af0b-119">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="5af0b-120">切换 **开和关** 之间的 **设置，** 然后选择 **保存首选项**。</span><span class="sxs-lookup"><span data-stu-id="5af0b-120">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="5af0b-121">预览功能</span><span class="sxs-lookup"><span data-stu-id="5af0b-121">Preview features</span></span>

<span data-ttu-id="5af0b-122">预览版中包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="5af0b-122">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="5af0b-123">设备发现</span><span class="sxs-lookup"><span data-stu-id="5af0b-123">Device discovery</span></span>](device-discovery.md) <br> <span data-ttu-id="5af0b-124">帮助你查找连接到公司网络的非托管设备，而无需额外的设备或繁琐的流程更改。</span><span class="sxs-lookup"><span data-stu-id="5af0b-124">Helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span> <span data-ttu-id="5af0b-125">使用载入的设备，可以在网络中查找非托管设备，并评估漏洞和风险。</span><span class="sxs-lookup"><span data-stu-id="5af0b-125">Using onboarded devices, you can find unmanaged devices in your network and assess vulnerabilities and risks.</span></span> <span data-ttu-id="5af0b-126">然后，你可以载入发现的设备，以减少与网络中具有非托管终结点相关的风险。</span><span class="sxs-lookup"><span data-stu-id="5af0b-126">You can then onboard discovered devices to reduce risks associated with having unmanaged endpoints in your network.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="5af0b-127">从 2021 年 5 月 10 开始，标准发现将成为所有预览客户的默认模式。</span><span class="sxs-lookup"><span data-stu-id="5af0b-127">Standard discovery will be the default mode for all preview customers starting May 10, 2021.</span></span> <span data-ttu-id="5af0b-128">你可以选择通过设置页保留基本模式。</span><span class="sxs-lookup"><span data-stu-id="5af0b-128">You can choose to retain the basic mode through the settings page.</span></span> 


- [<span data-ttu-id="5af0b-129">Web 内容筛选</span><span class="sxs-lookup"><span data-stu-id="5af0b-129">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="5af0b-130">Web 内容筛选是 Microsoft Defender for Endpoint 中的 Web 保护功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="5af0b-130">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="5af0b-131">它使组织能够根据网站的内容类别跟踪和监管对网站的访问。</span><span class="sxs-lookup"><span data-stu-id="5af0b-131">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="5af0b-132">许多此类网站虽然不是恶意网站，但由于合规性法规、带宽使用情况或其他问题，可能存在问题。</span><span class="sxs-lookup"><span data-stu-id="5af0b-132">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="5af0b-133">设备运行状况和合规性报告</span><span class="sxs-lookup"><span data-stu-id="5af0b-133">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="5af0b-134">设备运行状况和合规性报告提供有关组织中设备的高级别信息。</span><span class="sxs-lookup"><span data-stu-id="5af0b-134">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="5af0b-135">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5af0b-135">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5af0b-136">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5af0b-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
