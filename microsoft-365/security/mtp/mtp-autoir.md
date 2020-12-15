---
title: Microsoft 365 Defender 中的自动调查和响应
description: 在 Microsoft 365 Defender 中大致了解自动调查和响应功能（也称为自我修复）
keywords: 自动化， 调查， 警报， 触发器， 操作， 修正， 自我修复
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 7c28b7f3ac797f7402cfdb1f604fcef1e142a31b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683303"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="3bd72-104">Microsoft 365 Defender 中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="3bd72-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3bd72-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3bd72-105">**Applies to:**</span></span>
- <span data-ttu-id="3bd72-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3bd72-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="3bd72-107">想要体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="3bd72-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="3bd72-108">可以在[实验室环境中对其进行评估或在](https://aka.ms/mtp-trial-lab)[生产中运行试点项目](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="3bd72-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="3bd72-109">自动调查和自我修复的工作原理</span><span class="sxs-lookup"><span data-stu-id="3bd72-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="3bd72-110">在触发安全警报时，由安全运营团队来调查这些警报，并采取措施来保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="3bd72-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="3bd72-111">对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。</span><span class="sxs-lookup"><span data-stu-id="3bd72-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="3bd72-112">安全运营团队可能对必须监视和防范的大量威胁感到不知所措。</span><span class="sxs-lookup"><span data-stu-id="3bd72-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="3bd72-113">Microsoft 365 Defender 中的自动调查和响应功能以及自我修复可提供帮助。</span><span class="sxs-lookup"><span data-stu-id="3bd72-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="3bd72-114">观看以下视频，了解自我修复的工作原理：</span><span class="sxs-lookup"><span data-stu-id="3bd72-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="3bd72-115">在 Microsoft 365 Defender 中，使用自我修复功能自动调查和响应适用于你的设备、电子邮件&内容和标识。</span><span class="sxs-lookup"><span data-stu-id="3bd72-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="3bd72-116">本文介绍自动调查和响应的工作原理。</span><span class="sxs-lookup"><span data-stu-id="3bd72-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="3bd72-117">若要配置这些功能，请参阅在 [Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)中配置自动调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="3bd72-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="3bd72-118">你自己的虚拟分析师</span><span class="sxs-lookup"><span data-stu-id="3bd72-118">Your own virtual analyst</span></span>

<span data-ttu-id="3bd72-119">想象一下，你的第 1 层/第 2 层安全运营团队中有一名虚拟分析师。</span><span class="sxs-lookup"><span data-stu-id="3bd72-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="3bd72-120">虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。</span><span class="sxs-lookup"><span data-stu-id="3bd72-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="3bd72-121">虚拟助手可以全天候工作，且容量无限制，它承担大量的调查和威胁修正工作。</span><span class="sxs-lookup"><span data-stu-id="3bd72-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="3bd72-122">这样的虚拟助手可以大大减少响应时间，让你的安全运营团队腾出时间来进行其他重要的战略项目。</span><span class="sxs-lookup"><span data-stu-id="3bd72-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="3bd72-123">如果此方案看起来像科学虚构，则不是！</span><span class="sxs-lookup"><span data-stu-id="3bd72-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="3bd72-124">此类虚拟分析师是 Microsoft 365 Defender 套件的一部分，其名称是 *自动调查和响应*。</span><span class="sxs-lookup"><span data-stu-id="3bd72-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="3bd72-125">通过自动调查和响应，安全运营团队可以显著提高组织处理安全警报和事件的能力。</span><span class="sxs-lookup"><span data-stu-id="3bd72-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="3bd72-126">通过自动调查和响应，你可以降低调查和修正活动的成本，并利用威胁防护套件的最大功能。</span><span class="sxs-lookup"><span data-stu-id="3bd72-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="3bd72-127">自动调查和响应可帮助你的安全运营团队：</span><span class="sxs-lookup"><span data-stu-id="3bd72-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="3bd72-128">确定是否需要针对威胁执行操作；</span><span class="sxs-lookup"><span data-stu-id="3bd72-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="3bd72-129">执行（或建议执行）任何必要的修正操作；</span><span class="sxs-lookup"><span data-stu-id="3bd72-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="3bd72-130">确定应进行哪些其他调查；以及</span><span class="sxs-lookup"><span data-stu-id="3bd72-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="3bd72-131">根据需要对其他警报重复此过程。</span><span class="sxs-lookup"><span data-stu-id="3bd72-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="3bd72-132">自动调查流程</span><span class="sxs-lookup"><span data-stu-id="3bd72-132">The automated investigation process</span></span>

<span data-ttu-id="3bd72-133">**警报** > **事件** > **自动调查** > **裁定** > **修正操作**</span><span class="sxs-lookup"><span data-stu-id="3bd72-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="3bd72-134">触发的警报将创建一个事件，可以启动自动调查。</span><span class="sxs-lookup"><span data-stu-id="3bd72-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="3bd72-135">该调查可能会导致执行一项或多项修正操作。</span><span class="sxs-lookup"><span data-stu-id="3bd72-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="3bd72-136">在 Microsoft 365 Defender 中，每个自动调查将跨 Microsoft Defender for Identity、Microsoft Defender for Endpoint 和 Defender for Office 365 的信号关联起来，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="3bd72-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="3bd72-137">实体</span><span class="sxs-lookup"><span data-stu-id="3bd72-137">Entities</span></span> |<span data-ttu-id="3bd72-138">威胁防护服务</span><span class="sxs-lookup"><span data-stu-id="3bd72-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="3bd72-139">设备（也称为终结点）</span><span class="sxs-lookup"><span data-stu-id="3bd72-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="3bd72-140">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3bd72-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="3bd72-141">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="3bd72-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="3bd72-142">电子邮件内容（邮箱中的文件和邮件）</span><span class="sxs-lookup"><span data-stu-id="3bd72-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="3bd72-143">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="3bd72-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="3bd72-144">每项调查都会 (*调查* 的每个证据) 恶意、可疑或无威胁"裁定。</span><span class="sxs-lookup"><span data-stu-id="3bd72-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="3bd72-145">根据威胁的类型和结果裁定，修正操作会自动执行，或在组织的安全运营团队批准后执行。</span><span class="sxs-lookup"><span data-stu-id="3bd72-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="3bd72-146">"[操作中心](mtp-action-center.md)中列出了待处理和已完成的操作。</span><span class="sxs-lookup"><span data-stu-id="3bd72-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="3bd72-147">运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。</span><span class="sxs-lookup"><span data-stu-id="3bd72-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="3bd72-148">如果在其他位置看到受影响的实体，自动调查将扩大其范围，以包括该实体，并且将运行常规安全性 Playbook。</span><span class="sxs-lookup"><span data-stu-id="3bd72-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="3bd72-149">不是每个警报都会触发自动调查，而不是每个调查都会触发自动修正操作;这一切都取决于如何为组织配置自动调查和响应。</span><span class="sxs-lookup"><span data-stu-id="3bd72-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="3bd72-150">请参阅 [在 Microsoft 365 Defender 中配置自动调查和响应功能](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="3bd72-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="3bd72-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3bd72-151">Next steps</span></span>

- [<span data-ttu-id="3bd72-152">查看 Microsoft 365 Defender 中自动调查和响应的先决条件</span><span class="sxs-lookup"><span data-stu-id="3bd72-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="3bd72-153">为组织配置自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="3bd72-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="3bd72-154">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="3bd72-154">Learn more about the Action center</span></span>](mtp-action-center.md)
