---
title: 下一代保护
description: 了解如何管理、配置和使用 Microsoft Defender 防病毒、内置反恶意软件和防病毒保护。
keywords: Microsoft Defender 防病毒、Windows Defender、反恶意软件、SCEP、System Center 端点保护、System Center Configuration Manager、病毒、恶意软件、威胁、检测、保护、安全
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: cd7fe43fafc587c21fb28b53e0084ccb8c3e5c17
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925991"
---
# <a name="next-generation-protection"></a><span data-ttu-id="49cf7-104">下一代保护</span><span class="sxs-lookup"><span data-stu-id="49cf7-104">Next-generation protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="49cf7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="49cf7-105">**Applies to:**</span></span>

- [<span data-ttu-id="49cf7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="49cf7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a><span data-ttu-id="49cf7-107">Windows Defender 防病毒：你的下一代保护</span><span class="sxs-lookup"><span data-stu-id="49cf7-107">Microsoft Defender Antivirus: Your next-generation protection</span></span>

<span data-ttu-id="49cf7-108">Microsoft Defender 防病毒是下一代 Microsoft Defender for Endpoint 的保护组件。</span><span class="sxs-lookup"><span data-stu-id="49cf7-108">Microsoft Defender Antivirus is the next-generation protection component of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="49cf7-109">此保护结合机器学习、大数据分析、深度威胁抵御研究和 Microsoft 云基础结构来保护你的企业组织中的设备。</span><span class="sxs-lookup"><span data-stu-id="49cf7-109">This protection brings together machine learning, big-data analysis, in-depth threat resistance research, and the Microsoft cloud infrastructure to protect devices in your enterprise organization.</span></span> <span data-ttu-id="49cf7-110">下一代保护服务包括以下功能：</span><span class="sxs-lookup"><span data-stu-id="49cf7-110">Your next-generation protection services include the following capabilities:</span></span>

- <span data-ttu-id="49cf7-111">[基于行为、启发式和实时防病毒保护](configure-protection-features-microsoft-defender-antivirus.md)，包括使用文件、进程行为监视和其他启发式（也称为 *实时保护*）始终进行的扫描。</span><span class="sxs-lookup"><span data-stu-id="49cf7-111">[Behavior-based, heuristic, and real-time antivirus protection](configure-protection-features-microsoft-defender-antivirus.md), which includes always-on scanning using file and process behavior monitoring and other heuristics (also known as *real-time protection*).</span></span> <span data-ttu-id="49cf7-112">它还包括检测和阻止被视为不安全、但可能不会被检测为恶意软件的应用。</span><span class="sxs-lookup"><span data-stu-id="49cf7-112">It also includes detecting and blocking apps that are deemed unsafe, but might not be detected as malware.</span></span>
- <span data-ttu-id="49cf7-113">[云提供的保护](cloud-protection-microsoft-defender-antivirus.md)，包括对新兴威胁近乎即时的检测和阻止。</span><span class="sxs-lookup"><span data-stu-id="49cf7-113">[Cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md), which includes near-instant detection and blocking of new and emerging threats.</span></span>
- <span data-ttu-id="49cf7-114">[专用保护和产品更新](manage-updates-baselines-microsoft-defender-antivirus.md)，包括与保持 Microsoft Defender 防病毒最新相关的更新。</span><span class="sxs-lookup"><span data-stu-id="49cf7-114">[Dedicated protection and product updates](manage-updates-baselines-microsoft-defender-antivirus.md), which includes updates related to keeping Microsoft Defender Antivirus up to date.</span></span>

## <a name="try-a-demo"></a><span data-ttu-id="49cf7-115">尝试演示！</span><span class="sxs-lookup"><span data-stu-id="49cf7-115">Try a demo!</span></span>

<span data-ttu-id="49cf7-116">请访问 [Microsoft Defender for Endpoint 演示网站](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)，确认以下保护功能正常工作，并使用演示场景对其进行探索：</span><span class="sxs-lookup"><span data-stu-id="49cf7-116">Visit the [Microsoft Defender for Endpoint demo website](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following protection features are working and explore them using demo scenarios:</span></span>
- <span data-ttu-id="49cf7-117">云端保护</span><span class="sxs-lookup"><span data-stu-id="49cf7-117">Cloud-delivered protection</span></span>
- <span data-ttu-id="49cf7-118">首次看到时 (BAFS) 保护</span><span class="sxs-lookup"><span data-stu-id="49cf7-118">Block at first sight (BAFS) protection</span></span>
- <span data-ttu-id="49cf7-119">潜在有害应用程序 (PUA) 保护</span><span class="sxs-lookup"><span data-stu-id="49cf7-119">Potentially unwanted applications (PUA) protection</span></span>

## <a name="minimum-system-requirements"></a><span data-ttu-id="49cf7-120">最低系统需求</span><span class="sxs-lookup"><span data-stu-id="49cf7-120">Minimum system requirements</span></span>

<span data-ttu-id="49cf7-121">Microsoft Defender 防病毒的硬件要求与 Windows 10 相同。</span><span class="sxs-lookup"><span data-stu-id="49cf7-121">Microsoft Defender Antivirus has the same hardware requirements as of Windows 10.</span></span> <span data-ttu-id="49cf7-122">有关详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="49cf7-122">For more information, see the following resources:</span></span>

- [<span data-ttu-id="49cf7-123">最低硬件要求</span><span class="sxs-lookup"><span data-stu-id="49cf7-123">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [<span data-ttu-id="49cf7-124">硬件组件准则</span><span class="sxs-lookup"><span data-stu-id="49cf7-124">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a><span data-ttu-id="49cf7-125">配置下一代保护服务</span><span class="sxs-lookup"><span data-stu-id="49cf7-125">Configure next-generation protection services</span></span>

<span data-ttu-id="49cf7-126">有关如何配置下一代保护服务的信息，请参阅[配置 Microsoft Defender 防病毒功能](configure-microsoft-defender-antivirus-features.md)。</span><span class="sxs-lookup"><span data-stu-id="49cf7-126">For information on how to configure next-generation protection services, see [Configure Microsoft Defender Antivirus features](configure-microsoft-defender-antivirus-features.md).</span></span>

> [!Note]  
> <span data-ttu-id="49cf7-127">在运行 Microsoft Defender 防病毒时，Windows Server 2016 和 Windows Server 2019 中的配置和管理基本相同；但也存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="49cf7-127">Configuration and management is largely the same in Windows Server 2016 and Windows Server 2019, while running Microsoft Defender Antivirus; however, there are some differences.</span></span> <span data-ttu-id="49cf7-128">要了解更多信息，请参阅[Windows Server 2016 和 2019 上的 Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md)。</span><span class="sxs-lookup"><span data-stu-id="49cf7-128">To learn more, see [Microsoft Defender Antivirus on Windows Server 2016 and 2019](microsoft-defender-antivirus-on-windows-server.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="49cf7-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49cf7-129">See also</span></span>

- [<span data-ttu-id="49cf7-130">Windows Server 2016 和 2019 上的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="49cf7-130">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="49cf7-131">Microsoft Defender 防病毒管理和配置</span><span class="sxs-lookup"><span data-stu-id="49cf7-131">Microsoft Defender Antivirus management and configuration</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="49cf7-132">评估 Microsoft Defender 防病毒保护</span><span class="sxs-lookup"><span data-stu-id="49cf7-132">Evaluate Microsoft Defender Antivirus protection</span></span>](evaluate-microsoft-defender-antivirus.md)
