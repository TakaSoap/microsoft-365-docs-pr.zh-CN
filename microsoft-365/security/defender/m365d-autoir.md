---
title: Microsoft 365 Defender 中的自动调查和响应
description: 在 Microsoft 365 Defender 中大致了解自动调查和响应功能（也称为自我修复）
keywords: 自动化， 调查， 警报， 触发器， 操作， 修正， 自我修复
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c12937c016875c26a7212117e41aac4349cb540d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055868"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="db94a-104">Microsoft 365 Defender 中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="db94a-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="db94a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="db94a-105">**Applies to:**</span></span>
- <span data-ttu-id="db94a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db94a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="db94a-107">如果你的组织使用的是 [Microsoft 365 Defender，](microsoft-365-defender.md)则安全运营团队将在检测到恶意或可疑项目时收到警报。</span><span class="sxs-lookup"><span data-stu-id="db94a-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert whenever a malicious or suspicious artifact is detected.</span></span> <span data-ttu-id="db94a-108">鉴于似乎永远不会结束的威胁流，安全团队通常会面临解决大量警报的挑战。</span><span class="sxs-lookup"><span data-stu-id="db94a-108">Given the seemingly never-ending flow of threats that come in, security teams often face challenges in addressing the high volume of alerts.</span></span> <span data-ttu-id="db94a-109">幸运的是，Microsoft 365 Defender 包括自动调查和修正 (AIR) 功能，可帮助你的安全运营团队更有效地应对威胁。</span><span class="sxs-lookup"><span data-stu-id="db94a-109">Fortunately, Microsoft 365 Defender includes automated investigation and remediation (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="db94a-110">本文概述了 AIR，并包含指向下一步步骤和其他资源的链接。</span><span class="sxs-lookup"><span data-stu-id="db94a-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="db94a-111">想要体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="db94a-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="db94a-112">可以在[实验室环境中评估它或在](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)[生产中运行你的试验项目](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="db94a-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="db94a-113">自动调查和自我修复的工作原理</span><span class="sxs-lookup"><span data-stu-id="db94a-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="db94a-114">触发安全警报时，由安全运营团队来调查这些警报，并采取措施来保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="db94a-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="db94a-115">对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。</span><span class="sxs-lookup"><span data-stu-id="db94a-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="db94a-116">安全运营团队可能对必须监视和防范的大量威胁感到不知所措。</span><span class="sxs-lookup"><span data-stu-id="db94a-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="db94a-117">Microsoft 365 Defender 中的自动调查和响应功能以及自我修复可提供帮助。</span><span class="sxs-lookup"><span data-stu-id="db94a-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="db94a-118">观看以下视频，了解自我修复的工作原理：</span><span class="sxs-lookup"><span data-stu-id="db94a-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="db94a-119">在 Microsoft 365 Defender 中，具有自我修复功能的自动调查和响应适用于你的设备、电子邮件&内容和标识。</span><span class="sxs-lookup"><span data-stu-id="db94a-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="db94a-120">本文介绍了自动调查和响应的工作原理。</span><span class="sxs-lookup"><span data-stu-id="db94a-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="db94a-121">若要配置这些功能，请参阅在 [Microsoft 365 Defender](m365d-configure-auto-investigation-response.md)中配置自动调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="db94a-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="db94a-122">你自己的虚拟分析师</span><span class="sxs-lookup"><span data-stu-id="db94a-122">Your own virtual analyst</span></span>

<span data-ttu-id="db94a-123">假设你的第 1 层或第 2 层安全运营团队有一个虚拟分析师。</span><span class="sxs-lookup"><span data-stu-id="db94a-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="db94a-124">虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。</span><span class="sxs-lookup"><span data-stu-id="db94a-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="db94a-125">虚拟助手可以全天候工作，且容量无限制，它承担大量的调查和威胁修正工作。</span><span class="sxs-lookup"><span data-stu-id="db94a-125">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="db94a-126">这样的虚拟助手可以大大减少响应时间，让你的安全运营团队腾出时间来进行其他重要的战略项目。</span><span class="sxs-lookup"><span data-stu-id="db94a-126">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="db94a-127">如果此方案看起来像科学虚构，则不是！</span><span class="sxs-lookup"><span data-stu-id="db94a-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="db94a-128">此类虚拟分析师是 Microsoft 365 Defender 套件的一部分，其名称是 *自动调查和响应*。</span><span class="sxs-lookup"><span data-stu-id="db94a-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="db94a-129">自动调查和响应功能使安全运营团队可以大大增加组织处理安全警报和事件的能力。</span><span class="sxs-lookup"><span data-stu-id="db94a-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="db94a-130">通过自动调查和响应，你可以降低调查和修正活动处理的成本，并能够最利用威胁防护套件。</span><span class="sxs-lookup"><span data-stu-id="db94a-130">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="db94a-131">自动调查和响应功能可有助于安全运营团队：</span><span class="sxs-lookup"><span data-stu-id="db94a-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="db94a-132">确定是否需要针对威胁执行操作；</span><span class="sxs-lookup"><span data-stu-id="db94a-132">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="db94a-133">采取 (或建议) 必要的修正操作;</span><span class="sxs-lookup"><span data-stu-id="db94a-133">Taking (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="db94a-134">确定是否应进行其他调查以及应进行哪些其他调查;和</span><span class="sxs-lookup"><span data-stu-id="db94a-134">Determining whether and what other investigations should occur; and</span></span>
4. <span data-ttu-id="db94a-135">根据需要对其他警报重复此过程。</span><span class="sxs-lookup"><span data-stu-id="db94a-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="db94a-136">自动调查流程</span><span class="sxs-lookup"><span data-stu-id="db94a-136">The automated investigation process</span></span>

<span data-ttu-id="db94a-137">警报将创建一个事件，可以启动自动调查。</span><span class="sxs-lookup"><span data-stu-id="db94a-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="db94a-138">自动调查会针对每条证据做出裁定。</span><span class="sxs-lookup"><span data-stu-id="db94a-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="db94a-139">裁定可以是：</span><span class="sxs-lookup"><span data-stu-id="db94a-139">Verdicts can be:</span></span>
- <span data-ttu-id="db94a-140">*恶意*;</span><span class="sxs-lookup"><span data-stu-id="db94a-140">*Malicious*;</span></span>
- <span data-ttu-id="db94a-141">*可疑*;或</span><span class="sxs-lookup"><span data-stu-id="db94a-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="db94a-142">*未找到威胁*。</span><span class="sxs-lookup"><span data-stu-id="db94a-142">*No threats found*.</span></span> 

<span data-ttu-id="db94a-143">识别恶意或可疑实体的修正操作。</span><span class="sxs-lookup"><span data-stu-id="db94a-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="db94a-144">修正操作的示例包括：</span><span class="sxs-lookup"><span data-stu-id="db94a-144">Examples of remediation actions include:</span></span>
- <span data-ttu-id="db94a-145">将文件发送到隔离区;</span><span class="sxs-lookup"><span data-stu-id="db94a-145">Sending a file to quarantine;</span></span>
- <span data-ttu-id="db94a-146">停止进程;</span><span class="sxs-lookup"><span data-stu-id="db94a-146">Stopping a process;</span></span>
- <span data-ttu-id="db94a-147">隔离设备;</span><span class="sxs-lookup"><span data-stu-id="db94a-147">Isolating a device;</span></span>
- <span data-ttu-id="db94a-148">阻止 URL;和</span><span class="sxs-lookup"><span data-stu-id="db94a-148">Blocking a URL; and</span></span> 
- <span data-ttu-id="db94a-149">其他操作。</span><span class="sxs-lookup"><span data-stu-id="db94a-149">other actions.</span></span> <span data-ttu-id="db94a-150"> ([Microsoft 365 Defender](m365d-remediation-actions.md).) 中的修正操作</span><span class="sxs-lookup"><span data-stu-id="db94a-150">(See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).)</span></span>

<span data-ttu-id="db94a-151">根据 [组织的自动](m365d-configure-auto-investigation-response.md) 调查和响应功能配置方式，自动执行修正操作，或仅在安全运营团队批准后执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="db94a-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="db94a-152">所有操作（无论是挂起操作还是已完成操作）都列在操作 [中心中](m365d-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="db94a-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="db94a-153">运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。</span><span class="sxs-lookup"><span data-stu-id="db94a-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="db94a-154">如果在其他地方看到已规定实体，则自动调查会扩展其范围以包括该实体，并且调查过程将重复。</span><span class="sxs-lookup"><span data-stu-id="db94a-154">If an incriminated entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="db94a-155">在 Microsoft 365 Defender 中，每个自动调查将跨 Microsoft Defender for Identity、Microsoft Defender for Endpoint 和 Defender for Office 365 的信号关联起来，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="db94a-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="db94a-156">实体</span><span class="sxs-lookup"><span data-stu-id="db94a-156">Entities</span></span> |<span data-ttu-id="db94a-157">威胁防护服务</span><span class="sxs-lookup"><span data-stu-id="db94a-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="db94a-158">设备 (也称为终结点，有时也称为计算机) </span><span class="sxs-lookup"><span data-stu-id="db94a-158">Devices (also referred to as endpoints, and sometimes referred to as machines)</span></span>     |[<span data-ttu-id="db94a-159">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="db94a-159">Microsoft Defender for Endpoint</span></span>](../defender-endpoint/automated-investigations.md)<br/>[<span data-ttu-id="db94a-160">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="db94a-160">Microsoft Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="db94a-161">电子邮件 (可能包含文件和 URL 的电子邮件) </span><span class="sxs-lookup"><span data-stu-id="db94a-161">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="db94a-162">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="db94a-162">Microsoft Defender for Office 365</span></span>](../defender-365-security/defender-for-office-365.md)         |

> [!NOTE]
> <span data-ttu-id="db94a-163">不是每个警报都会触发自动调查，并且并非所有调查都会触发自动修正操作;这取决于如何为组织配置自动调查和响应。</span><span class="sxs-lookup"><span data-stu-id="db94a-163">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; it depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="db94a-164">请参阅 [在 Microsoft 365 Defender](m365d-configure-auto-investigation-response.md)中配置自动调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="db94a-164">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="db94a-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="db94a-165">Next steps</span></span>

- [<span data-ttu-id="db94a-166">请参阅 Microsoft 365 Defender 中自动调查和响应的先决条件</span><span class="sxs-lookup"><span data-stu-id="db94a-166">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="db94a-167">为组织配置自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="db94a-167">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="db94a-168">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="db94a-168">Learn more about the Action center</span></span>](m365d-action-center.md)
