---
title: Microsoft Defender ATP 预览功能
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
ms.openlocfilehash: 370048586c5ddfa6fa9ea265e929608357adf5df
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186877"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="e0217-104">适用于终结点的 Microsoft Defender 预览功能</span><span class="sxs-lookup"><span data-stu-id="e0217-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="e0217-105">预览版本在没有服务级别协议的情况下提供，不建议用于生产工作负载。</span><span class="sxs-lookup"><span data-stu-id="e0217-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="e0217-106">某些功能可能不受支持，或者可能具有受限功能。</span><span class="sxs-lookup"><span data-stu-id="e0217-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="e0217-107">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e0217-107">**Applies to:**</span></span>
- [<span data-ttu-id="e0217-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e0217-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e0217-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0217-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e0217-110">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e0217-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e0217-111">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e0217-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="e0217-112">Defender for Endpoint 服务会不断更新，以包含新功能增强功能和功能。</span><span class="sxs-lookup"><span data-stu-id="e0217-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

> [!TIP]
> <span data-ttu-id="e0217-113">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="e0217-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e0217-114">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e0217-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-abovefoldlink)

<span data-ttu-id="e0217-115">了解 Defender for Endpoint 预览版中的新功能，并首先通过打开预览体验来试用即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="e0217-115">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="e0217-116">在此页面更新时收到通知，方法为将以下 URL 复制并粘贴到源阅读器中： `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span><span class="sxs-lookup"><span data-stu-id="e0217-116">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span></span>

<span data-ttu-id="e0217-117">有关已普遍提供的新功能详细信息，请参阅 Defender for [Endpoint 中的新增功能](whats-new-in-microsoft-defender-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="e0217-117">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="e0217-118">启用预览功能</span><span class="sxs-lookup"><span data-stu-id="e0217-118">Turn on preview features</span></span>

<span data-ttu-id="e0217-119">你有权访问即将推出的功能，可以在这些功能全面发布之前提供反馈以帮助改善整体体验。</span><span class="sxs-lookup"><span data-stu-id="e0217-119">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="e0217-120">启用预览体验设置，以率先体验即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="e0217-120">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="e0217-121">在导航窗格中，选择"**设置**  >  **""高级功能**  >  **预览功能"。**</span><span class="sxs-lookup"><span data-stu-id="e0217-121">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="e0217-122">切换 **开和关** 之间的 **设置，** 然后选择 **保存首选项**。</span><span class="sxs-lookup"><span data-stu-id="e0217-122">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="e0217-123">预览功能</span><span class="sxs-lookup"><span data-stu-id="e0217-123">Preview features</span></span>

<span data-ttu-id="e0217-124">预览版中包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="e0217-124">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="e0217-125">Web 内容筛选</span><span class="sxs-lookup"><span data-stu-id="e0217-125">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="e0217-126">Web 内容筛选是 Microsoft Defender for Endpoint 中的 Web 保护功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="e0217-126">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="e0217-127">它使组织能够根据网站的内容类别跟踪和监管对网站的访问。</span><span class="sxs-lookup"><span data-stu-id="e0217-127">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="e0217-128">许多此类网站虽然不是恶意网站，但由于合规性法规、带宽使用情况或其他问题，可能存在问题。</span><span class="sxs-lookup"><span data-stu-id="e0217-128">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="e0217-129">设备运行状况和合规性报告</span><span class="sxs-lookup"><span data-stu-id="e0217-129">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="e0217-130">设备运行状况和合规性报告提供有关组织中设备的高级别信息。</span><span class="sxs-lookup"><span data-stu-id="e0217-130">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

- [<span data-ttu-id="e0217-131">信息保护</span><span class="sxs-lookup"><span data-stu-id="e0217-131">Information protection</span></span>](information-protection-in-windows-overview.md)<BR>
<span data-ttu-id="e0217-132">信息保护是 Microsoft 365 企业版套件的组成部分，可提供智能保护，在保证敏感数据安全的同时在工作场所中提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="e0217-132">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span> <span data-ttu-id="e0217-133">Microsoft Defender for Endpoint 无缝集成在 Microsoft 威胁防护中，为 Windows 设备提供完整全面的数据丢失防护 (DLP) 解决方案。</span><span class="sxs-lookup"><span data-stu-id="e0217-133">Microsoft Defender for Endpoint is seamlessly integrated in Microsoft Threat Protection to provide a complete and comprehensive data loss prevention (DLP) solution for Windows devices.</span></span>

    >[!NOTE]
    ><span data-ttu-id="e0217-134">部分提供 Windows 10 版本 1809。</span><span class="sxs-lookup"><span data-stu-id="e0217-134">Partially available from Windows 10, version 1809.</span></span>

- [<span data-ttu-id="e0217-135">载入 Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e0217-135">Onboard Windows Server 2019</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-version-1803-and-windows-server-2019) <BR> <span data-ttu-id="e0217-136">Microsoft Defender for Endpoint 现在增加了对 Windows Server 2019 的支持。</span><span class="sxs-lookup"><span data-stu-id="e0217-136">Microsoft Defender for Endpoint now adds support for Windows Server 2019.</span></span> <span data-ttu-id="e0217-137">你将能够使用可用于 Windows 10 客户端设备的相同方法载入 Windows Server 2019。</span><span class="sxs-lookup"><span data-stu-id="e0217-137">You'll be able to onboard Windows Server 2019 in the same method available for Windows 10 client devices.</span></span>


> [!TIP] 
> <span data-ttu-id="e0217-138">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e0217-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e0217-139">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e0217-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
