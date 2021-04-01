---
title: 创建指示器
ms.reviewer: ''
description: 创建文件哈希、IP 地址、URL 或域的指示器，以定义实体的检测、防护和排除。
keywords: 管理， 允许， 阻止， 阻止， 清理， 恶意， 文件哈希， ip 地址， url， 域
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 481051b74c1be88ba78bbd44e4fc0c174ed0bdad
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470889"
---
# <a name="create-indicators"></a><span data-ttu-id="de09c-104">创建指示器</span><span class="sxs-lookup"><span data-stu-id="de09c-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="de09c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="de09c-105">**Applies to:**</span></span>
- [<span data-ttu-id="de09c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="de09c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="de09c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de09c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> <span data-ttu-id="de09c-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="de09c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="de09c-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="de09c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="de09c-110">ICS (泄露) 是每个终结点保护解决方案中的重要功能。</span><span class="sxs-lookup"><span data-stu-id="de09c-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="de09c-111">此功能使 SecOps 能够设置指示器列表，用于检测并阻止 (防护和响应) 。</span><span class="sxs-lookup"><span data-stu-id="de09c-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="de09c-112">创建定义实体的检测、防护和排除的指示器。</span><span class="sxs-lookup"><span data-stu-id="de09c-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="de09c-113">你可以定义要采取的操作以及何时应用该操作的持续时间，以及要应用该操作的设备组的范围。</span><span class="sxs-lookup"><span data-stu-id="de09c-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="de09c-114">当前支持的源是 Defender for Endpoint 的云检测引擎、自动调查和修正引擎以及 Microsoft Defender 防病毒 (终结点) 。</span><span class="sxs-lookup"><span data-stu-id="de09c-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender Antivirus).</span></span>

<span data-ttu-id="de09c-115">**云检测引擎**</span><span class="sxs-lookup"><span data-stu-id="de09c-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="de09c-116">Defender for Endpoint 的云检测引擎会定期扫描收集的数据并尝试匹配你设置的指示器。</span><span class="sxs-lookup"><span data-stu-id="de09c-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="de09c-117">当有匹配时，将按照你为 IoC 指定的设置来采取措施。</span><span class="sxs-lookup"><span data-stu-id="de09c-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="de09c-118">**终结点防护引擎**</span><span class="sxs-lookup"><span data-stu-id="de09c-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="de09c-119">保护代理会遵守相同的指示器列表。</span><span class="sxs-lookup"><span data-stu-id="de09c-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="de09c-120">这意味着，如果 Microsoft Defender AV 是配置的主要 AV，将按照设置处理匹配的指示器。</span><span class="sxs-lookup"><span data-stu-id="de09c-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="de09c-121">例如，如果操作为"警报和阻止"，Microsoft Defender AV 将阻止文件执行 (并修正) 并引发相应的警报。</span><span class="sxs-lookup"><span data-stu-id="de09c-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="de09c-122">另一方面，如果操作设置为"允许"，Microsoft Defender AV 将不会检测也不会阻止文件运行。</span><span class="sxs-lookup"><span data-stu-id="de09c-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="de09c-123">**自动调查和修正引擎**</span><span class="sxs-lookup"><span data-stu-id="de09c-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="de09c-124">自动调查和修正的行为相同。</span><span class="sxs-lookup"><span data-stu-id="de09c-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="de09c-125">如果指示器设置为"允许"，自动调查和修正将忽略它的"错误"裁定。</span><span class="sxs-lookup"><span data-stu-id="de09c-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="de09c-126">如果设置为"阻止"，自动调查和修正将视为"错误"。</span><span class="sxs-lookup"><span data-stu-id="de09c-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>

> [!NOTE]
> <span data-ttu-id="de09c-127">EnableFileHashComputation 设置在文件扫描期间计算证书和文件 IoC 的文件哈希。</span><span class="sxs-lookup"><span data-stu-id="de09c-127">The EnableFileHashComputation setting computes the file hash for the cert and file IoC during file scans.</span></span> <span data-ttu-id="de09c-128">它支持对哈希和证书属于受信任应用程序的 IoC 强制。</span><span class="sxs-lookup"><span data-stu-id="de09c-128">It supports IoC enforcement of hashes and certs belong to trusted applications.</span></span> <span data-ttu-id="de09c-129">它将通过允许或阻止文件设置同时启用和禁用。</span><span class="sxs-lookup"><span data-stu-id="de09c-129">It will be concurrently enabled and disabled with the allow or block file setting.</span></span> <span data-ttu-id="de09c-130">EnableFileHashComputation 通过组策略手动启用，默认情况下处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="de09c-130">EnableFileHashComputation is enabled manually through Group Policy, and is disabled by default.</span></span>


<span data-ttu-id="de09c-131">当前支持的操作包括：</span><span class="sxs-lookup"><span data-stu-id="de09c-131">The current supported actions are:</span></span>
- <span data-ttu-id="de09c-132">允许</span><span class="sxs-lookup"><span data-stu-id="de09c-132">Allow</span></span>
- <span data-ttu-id="de09c-133">仅警报</span><span class="sxs-lookup"><span data-stu-id="de09c-133">Alert only</span></span>
- <span data-ttu-id="de09c-134">警报和阻止</span><span class="sxs-lookup"><span data-stu-id="de09c-134">Alert and block</span></span>


<span data-ttu-id="de09c-135">你可以为：</span><span class="sxs-lookup"><span data-stu-id="de09c-135">You can create an indicator for:</span></span>
- [<span data-ttu-id="de09c-136">Files</span><span class="sxs-lookup"><span data-stu-id="de09c-136">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="de09c-137">IP 地址、URL/域</span><span class="sxs-lookup"><span data-stu-id="de09c-137">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="de09c-138">证书</span><span class="sxs-lookup"><span data-stu-id="de09c-138">Certificates</span></span>](indicator-certificates.md)


> [!NOTE]
> <span data-ttu-id="de09c-139">每个租户限制为 15，000 个指示器。</span><span class="sxs-lookup"><span data-stu-id="de09c-139">There is a limit of 15,000 indicators per tenant.</span></span> <span data-ttu-id="de09c-140">文件和证书指示器不会阻止为 [Microsoft Defender 防病毒定义的排除项](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="de09c-140">File and certificate indicators do not block [exclusions defined for Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="de09c-141">当 Microsoft Defender 防病毒处于被动模式时，该标记不受支持。</span><span class="sxs-lookup"><span data-stu-id="de09c-141">Indicators are not supported in Microsoft Defender Antivirus when it is in passive mode.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="de09c-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="de09c-142">Related topics</span></span>

- [<span data-ttu-id="de09c-143">创建上下文 IoC</span><span class="sxs-lookup"><span data-stu-id="de09c-143">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="de09c-144">使用 Microsoft Defender 终结点指示器 API</span><span class="sxs-lookup"><span data-stu-id="de09c-144">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="de09c-145">使用合作伙伴集成解决方案</span><span class="sxs-lookup"><span data-stu-id="de09c-145">Use partner integrated solutions</span></span>](partner-applications.md)
