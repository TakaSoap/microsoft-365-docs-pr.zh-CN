---
title: 查看 Microsoft Defender for Endpoint 体系结构要求和关键概念
description: Microsoft 365 Defender 中的 Microsoft Defender for Endpoint 的技术图表将帮助你在构建试用实验室或Microsoft 365之前了解 Microsoft 365 中的标识。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457645"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a><span data-ttu-id="2442d-103">查看 Microsoft Defender for Endpoint 体系结构要求和关键概念</span><span class="sxs-lookup"><span data-stu-id="2442d-103">Review Microsoft Defender for Endpoint architecture requirements and key concepts</span></span>

<span data-ttu-id="2442d-104">**适用于：Microsoft 365 Defender**</span><span class="sxs-lookup"><span data-stu-id="2442d-104">**Applies to:** Microsoft 365 Defender</span></span>

<span data-ttu-id="2442d-105">本文将指导你设置 Microsoft Defender for Endpoint 环境评估的过程。</span><span class="sxs-lookup"><span data-stu-id="2442d-105">This article will guide you in the process of setting up the evaluation for Microsoft Defender for Endpoint environment.</span></span>

<span data-ttu-id="2442d-106">有关此过程详细信息，请参阅 [概述文章](eval-defender-endpoint-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2442d-106">For more information about this process, see the [overview article](eval-defender-endpoint-overview.md).</span></span>

<span data-ttu-id="2442d-107">在启用 Microsoft Defender for Endpoint 之前，请确保你了解体系结构并满足要求。</span><span class="sxs-lookup"><span data-stu-id="2442d-107">Before enabling Microsoft Defender for Endpoint, be sure you understand the architecture and can meet the requirements.</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="2442d-108">了解体系结构</span><span class="sxs-lookup"><span data-stu-id="2442d-108">Understand the architecture</span></span>

<span data-ttu-id="2442d-109">下图说明了适用于终结点的 Microsoft Defender 体系结构和集成。</span><span class="sxs-lookup"><span data-stu-id="2442d-109">The following diagram illustrates Microsoft Defender for Endpoint architecture and integrations.</span></span> 

![将 Microsoft Defender for Office添加到 Defender 评估环境的步骤](../../media/defender/m365-defender-endpoint-architecture.png)

<span data-ttu-id="2442d-111">下表介绍了此图。</span><span class="sxs-lookup"><span data-stu-id="2442d-111">The following table describes the illustration.</span></span>

<span data-ttu-id="2442d-112">呼叫</span><span class="sxs-lookup"><span data-stu-id="2442d-112">Call-out</span></span> | <span data-ttu-id="2442d-113">说明</span><span class="sxs-lookup"><span data-stu-id="2442d-113">Description</span></span>
:---|:---|
<span data-ttu-id="2442d-114">1</span><span class="sxs-lookup"><span data-stu-id="2442d-114">1</span></span> | <span data-ttu-id="2442d-115">设备通过受支持的管理工具之一进行。</span><span class="sxs-lookup"><span data-stu-id="2442d-115">Devices are on-boarded through one of the supported management tools.</span></span> 
<span data-ttu-id="2442d-116">2</span><span class="sxs-lookup"><span data-stu-id="2442d-116">2</span></span> | <span data-ttu-id="2442d-117">On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.</span><span class="sxs-lookup"><span data-stu-id="2442d-117">On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.</span></span>
<span data-ttu-id="2442d-118">3</span><span class="sxs-lookup"><span data-stu-id="2442d-118">3</span></span> | <span data-ttu-id="2442d-119">托管设备已加入和/或注册Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="2442d-119">Managed devices are joined and/or enrolled in Azure Active Directory.</span></span>
<span data-ttu-id="2442d-120">4 </span><span class="sxs-lookup"><span data-stu-id="2442d-120">4</span></span> | <span data-ttu-id="2442d-121">已加入域Windows 10设备使用 Azure Active Directory 同步到Azure Active Directory 连接。</span><span class="sxs-lookup"><span data-stu-id="2442d-121">Domain-joined Windows 10 devices are synchronized to Azure Active Directory using Azure Active Directory Connect.</span></span>
<span data-ttu-id="2442d-122">5 </span><span class="sxs-lookup"><span data-stu-id="2442d-122">5</span></span> | <span data-ttu-id="2442d-123">Microsoft Defender for Endpoint 警报、调查和响应在 Microsoft 365 Defender 中进行管理。</span><span class="sxs-lookup"><span data-stu-id="2442d-123">Microsoft Defender for Endpoint alerts, investigations, and responses are managed in Microsoft 365 Defender.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="2442d-124">了解关键概念</span><span class="sxs-lookup"><span data-stu-id="2442d-124">Understand key concepts</span></span>

<span data-ttu-id="2442d-125">下表确定了评估、配置和部署 Microsoft Defender for Endpoint 时必须了解的重要概念：</span><span class="sxs-lookup"><span data-stu-id="2442d-125">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Defender for Endpoint:</span></span> 

<span data-ttu-id="2442d-126">概念</span><span class="sxs-lookup"><span data-stu-id="2442d-126">Concept</span></span> | <span data-ttu-id="2442d-127">说明</span><span class="sxs-lookup"><span data-stu-id="2442d-127">Description</span></span> | <span data-ttu-id="2442d-128">详细信息</span><span class="sxs-lookup"><span data-stu-id="2442d-128">More information</span></span>
:---|:---|:---|
<span data-ttu-id="2442d-129">管理门户</span><span class="sxs-lookup"><span data-stu-id="2442d-129">Administration Portal</span></span> | <span data-ttu-id="2442d-130">Microsoft 365 Defender用于监视和协助响应潜在高级永久性威胁活动或数据泄露警报的门户。</span><span class="sxs-lookup"><span data-stu-id="2442d-130">Microsoft 365 Defender portal to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> | [<span data-ttu-id="2442d-131">Microsoft Defender for Endpoint 门户概述</span><span class="sxs-lookup"><span data-stu-id="2442d-131">Microsoft Defender for Endpoint portal overview</span></span>](/defender-endpoint/portal-overview)
<span data-ttu-id="2442d-132">攻击面减少</span><span class="sxs-lookup"><span data-stu-id="2442d-132">Attack Surface Reduction</span></span> | <span data-ttu-id="2442d-133">通过最大程度地减少组织易受网络威胁和攻击的位置，帮助减少攻击面。</span><span class="sxs-lookup"><span data-stu-id="2442d-133">Help reduce your attack surfaces by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> | [<span data-ttu-id="2442d-134">减少攻击面概述</span><span class="sxs-lookup"><span data-stu-id="2442d-134">Overview of attack surface reduction</span></span>](/defender-endpoint/overview-attack-surface-reduction)
<span data-ttu-id="2442d-135">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="2442d-135">Endpoint Detection and Response</span></span> | <span data-ttu-id="2442d-136">终结点检测和响应功能提供接近实时且可操作的高级攻击检测。</span><span class="sxs-lookup"><span data-stu-id="2442d-136">Endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> | [<span data-ttu-id="2442d-137">终结点检测和响应功能概述</span><span class="sxs-lookup"><span data-stu-id="2442d-137">Overview of endpoint detection and response capabilities</span></span>](/defender-endpoint/overview-endpoint-detection-response)
<span data-ttu-id="2442d-138">行为阻止和抑制</span><span class="sxs-lookup"><span data-stu-id="2442d-138">Behavioral Blocking and Containment</span></span> | <span data-ttu-id="2442d-139">行为阻止和抑制功能可帮助根据威胁的行为和进程树识别和停止威胁，即使威胁已开始执行。</span><span class="sxs-lookup"><span data-stu-id="2442d-139">Behavioral blocking and containment capabilities can help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> | [<span data-ttu-id="2442d-140">行为阻止和控制</span><span class="sxs-lookup"><span data-stu-id="2442d-140">Behavioral blocking and containment</span></span>](/defender-endpoint/behavioral-blocking-containment)
<span data-ttu-id="2442d-141">自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="2442d-141">Automated Investigation and Response</span></span> | <span data-ttu-id="2442d-142">自动调查使用各种基于安全分析员所使用的流程的检查算法，旨在检查警报并立即采取措施来解决违规问题。</span><span class="sxs-lookup"><span data-stu-id="2442d-142">Automated investigation uses various inspection algorithms based on processes that are used by security analysts and designed to examine alerts and take immediate action to resolve breaches.</span></span> | [<span data-ttu-id="2442d-143">使用自动调查调查和修正威胁</span><span class="sxs-lookup"><span data-stu-id="2442d-143">Use automated investigations to investigate and remediate threats</span></span>](/defender-endpoint/automated-investigations)
<span data-ttu-id="2442d-144">高级搜寻</span><span class="sxs-lookup"><span data-stu-id="2442d-144">Advanced Hunting</span></span> | <span data-ttu-id="2442d-145">高级搜寻是一种基于查询的威胁搜寻工具，允许你浏览最多 30 天的原始数据，以便你可以主动检查网络中事件以查找威胁指示器和实体。</span><span class="sxs-lookup"><span data-stu-id="2442d-145">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data so that you can proactively inspect events in your network to locate threat indicators and entities.</span></span> | [<span data-ttu-id="2442d-146">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="2442d-146">Overview of advanced hunting</span></span>](/defender-endpoint/advanced-hunting-overview)
<span data-ttu-id="2442d-147">威胁分析</span><span class="sxs-lookup"><span data-stu-id="2442d-147">Threat Analytics</span></span> | <span data-ttu-id="2442d-148">威胁分析是来自专家 Microsoft 安全研究人员的一组报告，涉及最相关的威胁。</span><span class="sxs-lookup"><span data-stu-id="2442d-148">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats.</span></span> | [<span data-ttu-id="2442d-149">跟踪并响应新出现的威胁</span><span class="sxs-lookup"><span data-stu-id="2442d-149">Track and respond to emerging threats</span></span>](/defender-endpoint/threat-analytics)


<span data-ttu-id="2442d-150">有关 Microsoft Defender for Endpoint 中包含的功能的更多详细信息，请参阅什么是[Microsoft Defender for Endpoint。](/defender-endpoint/microsoft-defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="2442d-150">For more detailed information about the capabilities included with Microsoft Defender for Endpoint, see [What is Microsoft Defender for Endpoint](/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="siem-integration"></a><span data-ttu-id="2442d-151">SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="2442d-151">SIEM integration</span></span>

<span data-ttu-id="2442d-152">你可以将 Microsoft Defender for Endpoint 与 Azure Sentinel 集成，以更全面的分析整个组织的安全事件，并生成有效且即时响应的手册。</span><span class="sxs-lookup"><span data-stu-id="2442d-152">You can integrate Microsoft Defender for Endpoint with Azure Sentinel to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span> 

<span data-ttu-id="2442d-153">Microsoft Defender for Endpoint 还可以集成到 SIEM 解决方案的其他安全 (事件) 中。</span><span class="sxs-lookup"><span data-stu-id="2442d-153">Microsoft Defender for Endpoint can also be integrated into other Security Information and Event Management (SIEM) solutions.</span></span> <span data-ttu-id="2442d-154">有关详细信息，请参阅在 [Microsoft Defender for Endpoint 中启用 SIEM 集成](/defender-endpoint/enable-siem-integration)。</span><span class="sxs-lookup"><span data-stu-id="2442d-154">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](/defender-endpoint/enable-siem-integration).</span></span>


## <a name="next-steps"></a><span data-ttu-id="2442d-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2442d-155">Next steps</span></span>
[<span data-ttu-id="2442d-156">启用评估</span><span class="sxs-lookup"><span data-stu-id="2442d-156">Enable the evaluation</span></span>](eval-defender-endpoint-enable-eval.md)

<span data-ttu-id="2442d-157">返回到评估 Microsoft [Defender for Endpoint 的概述](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2442d-157">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="2442d-158">返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2442d-158">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>