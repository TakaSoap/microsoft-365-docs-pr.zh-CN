---
title: 启用和配置Microsoft Defender 防病毒保护功能
description: 在 Microsoft Defender AV 中启用基于行为的启发式实时保护。
keywords: 启发式， 机器学习， 行为监视器， 实时保护， 始终打开， Microsoft Defender 防病毒， 反恶意软件， 安全性， defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 53b1e1474e0870388ec1cfaf214190eb0bdf7beb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274594"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="9aa71-104">配置方案、高要求和实时保护</span><span class="sxs-lookup"><span data-stu-id="9aa71-104">Configure behavioral, heuristic, and real-time protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9aa71-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9aa71-105">**Applies to:**</span></span>

- [<span data-ttu-id="9aa71-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9aa71-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9aa71-107">Microsoft Defender 防病毒使用多种方法来提供威胁防护：</span><span class="sxs-lookup"><span data-stu-id="9aa71-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="9aa71-108">云提供的保护，用于即时检测和阻止新出现的威胁</span><span class="sxs-lookup"><span data-stu-id="9aa71-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="9aa71-109">始终打开扫描，使用文件和进程行为监视以及其他启发 (也称为"实时保护") </span><span class="sxs-lookup"><span data-stu-id="9aa71-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="9aa71-110">基于机器学习、人工和自动化大数据分析，以及深入的威胁抵御研究的专用保护更新</span><span class="sxs-lookup"><span data-stu-id="9aa71-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="9aa71-111">你可以配置如何Microsoft Defender 防病毒组策略、System Center配置管理、PowerShell cmdlet 和 WMI Windows Management Instrumentation (这些方法) 。</span><span class="sxs-lookup"><span data-stu-id="9aa71-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="9aa71-112">本部分介绍了始终扫描的配置，包括如何检测和阻止被视为不安全但可能不会被检测为恶意软件的应用。</span><span class="sxs-lookup"><span data-stu-id="9aa71-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="9aa71-113">请参阅[通过云保护Microsoft Defender 防病毒下](cloud-protection-microsoft-defender-antivirus.md)一代技术，了解如何启用和配置Microsoft Defender 防病毒提供的保护。</span><span class="sxs-lookup"><span data-stu-id="9aa71-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9aa71-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="9aa71-114">In this section</span></span>

 <span data-ttu-id="9aa71-115">主题</span><span class="sxs-lookup"><span data-stu-id="9aa71-115">Topic</span></span> | <span data-ttu-id="9aa71-116">说明</span><span class="sxs-lookup"><span data-stu-id="9aa71-116">Description</span></span>
---|---
[<span data-ttu-id="9aa71-117">检测并阻止可能不需要的应用程序</span><span class="sxs-lookup"><span data-stu-id="9aa71-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="9aa71-118">检测并阻止网络中可能不需要的应用，如广告软件、浏览器修饰符和工具栏以及未授权或伪造的防病毒应用</span><span class="sxs-lookup"><span data-stu-id="9aa71-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="9aa71-119">启用和配置Microsoft Defender 防病毒保护功能</span><span class="sxs-lookup"><span data-stu-id="9aa71-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="9aa71-120">启用和配置实时保护、启发和其他始终启用Microsoft Defender 防病毒监视功能</span><span class="sxs-lookup"><span data-stu-id="9aa71-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>