---
title: Microsoft 365 Defender 中的自动化调查和响应
description: 在 Microsoft 365 Defender 中获取自动化调查和响应功能的概述（也称为自我修复）
keywords: 自动化、调查、警报、触发、操作、修正、自我修复
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
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 2b8872288291adc0b9fc5e1c1541f885711df230
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356699"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="0b1c1-104">Microsoft 365 Defender 中的自动化调查和响应</span><span class="sxs-lookup"><span data-stu-id="0b1c1-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0b1c1-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0b1c1-105">**Applies to:**</span></span>
- <span data-ttu-id="0b1c1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b1c1-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="0b1c1-107">想要体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="0b1c1-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="0b1c1-108">您可以 [在实验室环境中对其进行评估](https://aka.ms/mtp-trial-lab) ，也可以 [在生产中运行试点项目](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="0b1c1-109">随着安全警报的触发，安全操作团队可查看这些警报并采取措施来保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-109">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="0b1c1-110">对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-110">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="0b1c1-111">安全运营团队可能对必须监视和防范的大量威胁感到不知所措。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-111">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="0b1c1-112">Microsoft 365 Defender 中的自动化调查和响应功能（通过自我修复）可能会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-112">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="0b1c1-113">观看以下视频，了解自我修复的工作原理：</span><span class="sxs-lookup"><span data-stu-id="0b1c1-113">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="0b1c1-114">在 Microsoft 365 Defender 中，使用自愈功能的自动调查和响应可在您的设备、电子邮件 & 内容和标识之间运行。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-114">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span> <span data-ttu-id="0b1c1-115">Microsoft 365 Defender 将功能汇集在一起：</span><span class="sxs-lookup"><span data-stu-id="0b1c1-115">Microsoft 365 Defender brings together capabilities from:</span></span> 
- [<span data-ttu-id="0b1c1-116">Microsoft Defender for Endpoint 中的自动调查和修正</span><span class="sxs-lookup"><span data-stu-id="0b1c1-116">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [<span data-ttu-id="0b1c1-117">Microsoft Defender for Office 365 中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="0b1c1-117">Automated investigation and response in Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [<span data-ttu-id="0b1c1-118">Azure 高级威胁检测</span><span class="sxs-lookup"><span data-stu-id="0b1c1-118">Azure advanced threat detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [<span data-ttu-id="0b1c1-119">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0b1c1-119">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
<span data-ttu-id="0b1c1-120">本文介绍了自动化调查和响应的工作方式。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="0b1c1-121">若要配置这些功能，请参阅 [在 Microsoft 365 Defender 中配置自动调查和响应功能](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-virtual-analyst"></a><span data-ttu-id="0b1c1-122">你的虚拟分析师</span><span class="sxs-lookup"><span data-stu-id="0b1c1-122">Your virtual analyst</span></span>

<span data-ttu-id="0b1c1-123">想象一下，你的第 1 层/第 2 层安全运营团队中有一名虚拟分析师。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-123">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="0b1c1-124">虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="0b1c1-125">虚拟助手可以全天候工作，且容量无限制，它承担大量的调查和威胁修正工作。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-125">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="0b1c1-126">这样的虚拟助手可以大大减少响应时间，让你的安全运营团队腾出时间来进行其他重要的战略项目。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-126">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="0b1c1-127">如果此方案听起来像科学 fiction，则不是！</span><span class="sxs-lookup"><span data-stu-id="0b1c1-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="0b1c1-128">此类虚拟分析员是 Microsoft 365 Defender 套件的一部分，其名称是 *自动调查和响应*。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="0b1c1-129">自动化调查和响应使安全操作团队能够显著提高组织处理安全警报和事件的能力。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-129">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="0b1c1-130">通过自动调查和响应，可以降低处理调查和补救活动的成本，并充分利用威胁防护套件。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-130">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="0b1c1-131">自动调查和响应通过以下方式帮助您的安全运营团队：</span><span class="sxs-lookup"><span data-stu-id="0b1c1-131">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="0b1c1-132">确定是否需要针对威胁执行操作；</span><span class="sxs-lookup"><span data-stu-id="0b1c1-132">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="0b1c1-133">执行（或建议执行）任何必要的修正操作；</span><span class="sxs-lookup"><span data-stu-id="0b1c1-133">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="0b1c1-134">确定应进行哪些其他调查；以及</span><span class="sxs-lookup"><span data-stu-id="0b1c1-134">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="0b1c1-135">根据需要对其他警报重复此过程。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="0b1c1-136">自动调查流程</span><span class="sxs-lookup"><span data-stu-id="0b1c1-136">The automated investigation process</span></span>

<span data-ttu-id="0b1c1-137">**警报** > **事件** > **自动调查** > **裁定** > **修正操作**</span><span class="sxs-lookup"><span data-stu-id="0b1c1-137">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="0b1c1-138">触发的警报创建一个事件，该事件可以开始进行自动调查。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-138">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="0b1c1-139">该调查可能会导致执行一项或多项修正操作。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-139">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="0b1c1-140">在 Microsoft 365 Defender 中，每个自动调查都将来自 Microsoft Defender for Identity、Microsoft Defender for Endpoint 和 Defender for Office 365 的信号关联起来，如下表中所汇总：</span><span class="sxs-lookup"><span data-stu-id="0b1c1-140">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="0b1c1-141">实体</span><span class="sxs-lookup"><span data-stu-id="0b1c1-141">Entities</span></span> |<span data-ttu-id="0b1c1-142">威胁防护服务</span><span class="sxs-lookup"><span data-stu-id="0b1c1-142">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="0b1c1-143">设备（也称为终结点）</span><span class="sxs-lookup"><span data-stu-id="0b1c1-143">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="0b1c1-144">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0b1c1-144">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="0b1c1-145">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="0b1c1-145">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="0b1c1-146">电子邮件内容（邮箱中的文件和邮件）</span><span class="sxs-lookup"><span data-stu-id="0b1c1-146">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="0b1c1-147">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0b1c1-147">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="0b1c1-148">每个调查都会为调查) 的每个证据生成 verdicts (*恶意*、 *可疑* 或不会 *发现的威胁* 。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-148">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="0b1c1-149">根据威胁的类型和得到的结论，将自动执行更正操作，或在组织的安全操作团队批准时执行。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-149">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="0b1c1-150">"[操作中心](mtp-action-center.md)中列出了待处理和已完成的操作。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-150">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="0b1c1-151">运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-151">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="0b1c1-152">如果在其他位置看到受影响的实体，自动调查将扩大其范围，以包括该实体，并且将运行常规安全性 Playbook。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-152">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="0b1c1-153">并不是每个警报都会触发自动调查，并且并非每个调查都会导致自动修正操作;这一切都取决于为您的组织配置自动调查和响应的方式。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-153">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="0b1c1-154">请参阅 [在 Microsoft 365 Defender 中配置自动调查和响应功能](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="0b1c1-154">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="0b1c1-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0b1c1-155">Next steps</span></span>

- [<span data-ttu-id="0b1c1-156">请参阅 Microsoft 365 Defender 中的自动调查和响应的先决条件</span><span class="sxs-lookup"><span data-stu-id="0b1c1-156">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="0b1c1-157">为你的组织配置自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="0b1c1-157">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="0b1c1-158">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="0b1c1-158">Learn more about the Action center</span></span>](mtp-action-center.md)
