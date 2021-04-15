---
title: 下一代保护
description: 了解如何管理、配置和使用 Microsoft Defender 防病毒内置反恶意软件和防病毒保护。
keywords: Microsoft Defender 防病毒， windows defender， 反恶意软件， scep， system center endpoint protection， system center configuration manager， 病毒， 恶意软件， 威胁， 检测， 保护， 安全
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: eb7e0253b3761d05d112500c0410fffa58548221
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765415"
---
# <a name="next-generation-protection"></a><span data-ttu-id="ba403-104">下一代保护</span><span class="sxs-lookup"><span data-stu-id="ba403-104">Next-generation protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ba403-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ba403-105">**Applies to:**</span></span>

- [<span data-ttu-id="ba403-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ba403-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a><span data-ttu-id="ba403-107">Microsoft Defender 防病毒：你的下一代保护</span><span class="sxs-lookup"><span data-stu-id="ba403-107">Microsoft Defender Antivirus: Your next-generation protection</span></span>

<span data-ttu-id="ba403-108">Microsoft Defender 防病毒是 Microsoft Defender for Endpoint 的下一代保护组件。</span><span class="sxs-lookup"><span data-stu-id="ba403-108">Microsoft Defender Antivirus is the next-generation protection component of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ba403-109">此保护将机器学习、大数据分析、深度威胁防范研究和 Microsoft 云基础结构汇集在一起，以保护企业组织的设备。</span><span class="sxs-lookup"><span data-stu-id="ba403-109">This protection brings together machine learning, big-data analysis, in-depth threat resistance research, and the Microsoft cloud infrastructure to protect devices in your enterprise organization.</span></span> <span data-ttu-id="ba403-110">下一代保护服务包括以下功能：</span><span class="sxs-lookup"><span data-stu-id="ba403-110">Your next-generation protection services include the following capabilities:</span></span>

- <span data-ttu-id="ba403-111">基于行为的[启发](configure-protection-features-microsoft-defender-antivirus.md)式实时防病毒保护，其中包括使用文件和进程行为监视以及其他启发式 (扫描，也称为实时保护) 。 </span><span class="sxs-lookup"><span data-stu-id="ba403-111">[Behavior-based, heuristic, and real-time antivirus protection](configure-protection-features-microsoft-defender-antivirus.md), which includes always-on scanning using file and process behavior monitoring and other heuristics (also known as *real-time protection*).</span></span> <span data-ttu-id="ba403-112">它还包括检测和阻止被视为不安全但可能未检测为恶意软件的应用。</span><span class="sxs-lookup"><span data-stu-id="ba403-112">It also includes detecting and blocking apps that are deemed unsafe, but might not be detected as malware.</span></span>
- <span data-ttu-id="ba403-113">[云提供的保护](cloud-protection-microsoft-defender-antivirus.md)，包括快速检测和阻止新出现的威胁。</span><span class="sxs-lookup"><span data-stu-id="ba403-113">[Cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md), which includes near-instant detection and blocking of new and emerging threats.</span></span>
- <span data-ttu-id="ba403-114">[专用保护和产品更新](manage-updates-baselines-microsoft-defender-antivirus.md)，其中包括与使 Microsoft Defender 防病毒保持最新相关的更新。</span><span class="sxs-lookup"><span data-stu-id="ba403-114">[Dedicated protection and product updates](manage-updates-baselines-microsoft-defender-antivirus.md), which includes updates related to keeping Microsoft Defender Antivirus up to date.</span></span>

## <a name="try-a-demo"></a><span data-ttu-id="ba403-115">试用演示！</span><span class="sxs-lookup"><span data-stu-id="ba403-115">Try a demo!</span></span>

<span data-ttu-id="ba403-116">访问 [Microsoft Defender for Endpoint 演示网站](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 以确认以下保护功能是否正常工作，然后使用演示方案探索它们：</span><span class="sxs-lookup"><span data-stu-id="ba403-116">Visit the [Microsoft Defender for Endpoint demo website](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following protection features are working and explore them using demo scenarios:</span></span>
- <span data-ttu-id="ba403-117">云保护</span><span class="sxs-lookup"><span data-stu-id="ba403-117">Cloud-delivered protection</span></span>
- <span data-ttu-id="ba403-118">在 BAFS 保护 (首次看到) 阻止</span><span class="sxs-lookup"><span data-stu-id="ba403-118">Block at first sight (BAFS) protection</span></span>
- <span data-ttu-id="ba403-119">PUA 保护 (可能不需要) 的应用程序</span><span class="sxs-lookup"><span data-stu-id="ba403-119">Potentially unwanted applications (PUA) protection</span></span>

## <a name="minimum-system-requirements"></a><span data-ttu-id="ba403-120">最低系统要求</span><span class="sxs-lookup"><span data-stu-id="ba403-120">Minimum system requirements</span></span>

<span data-ttu-id="ba403-121">从 Windows 10 起，Microsoft Defender 防病毒具有相同的硬件要求。</span><span class="sxs-lookup"><span data-stu-id="ba403-121">Microsoft Defender Antivirus has the same hardware requirements as of Windows 10.</span></span> <span data-ttu-id="ba403-122">有关更多信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="ba403-122">For more information, see the following resources:</span></span>

- [<span data-ttu-id="ba403-123">最低硬件要求</span><span class="sxs-lookup"><span data-stu-id="ba403-123">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [<span data-ttu-id="ba403-124">硬件组件指南</span><span class="sxs-lookup"><span data-stu-id="ba403-124">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a><span data-ttu-id="ba403-125">配置下一代保护服务</span><span class="sxs-lookup"><span data-stu-id="ba403-125">Configure next-generation protection services</span></span>

<span data-ttu-id="ba403-126">若要了解如何配置下一代保护服务，请参阅配置 [Microsoft Defender 防病毒功能](configure-microsoft-defender-antivirus-features.md)。</span><span class="sxs-lookup"><span data-stu-id="ba403-126">For information on how to configure next-generation protection services, see [Configure Microsoft Defender Antivirus features](configure-microsoft-defender-antivirus-features.md).</span></span>

> [!Note]  
> <span data-ttu-id="ba403-127">配置和管理在 Windows Server 2016 和 Windows Server 2019 中基本相同，同时运行 Microsoft Defender 防病毒;但是，存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="ba403-127">Configuration and management is largely the same in Windows Server 2016 and Windows Server 2019, while running Microsoft Defender Antivirus; however, there are some differences.</span></span> <span data-ttu-id="ba403-128">若要了解更多信息，请参阅 [Windows Server 2016 和 Windows Server 2019 上的 Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md)。</span><span class="sxs-lookup"><span data-stu-id="ba403-128">To learn more, see [Microsoft Defender Antivirus on Windows Server 2016 and 2019](microsoft-defender-antivirus-on-windows-server.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ba403-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba403-129">See also</span></span>

- [<span data-ttu-id="ba403-130">Windows Server 2016 和 2019 上的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="ba403-130">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="ba403-131">Microsoft Defender 防病毒管理和配置</span><span class="sxs-lookup"><span data-stu-id="ba403-131">Microsoft Defender Antivirus management and configuration</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ba403-132">评估 Microsoft Defender 防病毒保护</span><span class="sxs-lookup"><span data-stu-id="ba403-132">Evaluate Microsoft Defender Antivirus protection</span></span>](evaluate-microsoft-defender-antivirus.md)