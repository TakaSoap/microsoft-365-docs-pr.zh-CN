---
title: Microsoft 威胁防护中的自动调查和响应
description: 了解 Microsoft 威胁防护中的自动化调查和响应功能（也称为自我修复）概述
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
ms.openlocfilehash: 32bf5f1ada91ae67f72bd26c7fe68fe91897be7c
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429355"
---
# <a name="automated-investigation-and-response-in-microsoft-threat-protection"></a><span data-ttu-id="c8b80-104">Microsoft 威胁防护中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="c8b80-104">Automated investigation and response in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c8b80-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c8b80-105">**Applies to:**</span></span>
- <span data-ttu-id="c8b80-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="c8b80-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c8b80-107">随着安全警报的触发，安全操作团队可查看这些警报并采取措施来保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="c8b80-107">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="c8b80-108">对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。</span><span class="sxs-lookup"><span data-stu-id="c8b80-108">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="c8b80-109">安全运营团队可能对必须监视和防范的大量威胁感到不知所措。</span><span class="sxs-lookup"><span data-stu-id="c8b80-109">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="c8b80-110">Microsoft 威胁防护中的自动化调查和响应功能（通过自我修复）可能会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="c8b80-110">Automated investigation and response capabilities, with self-healing, in Microsoft Threat Protection can help.</span></span>

<span data-ttu-id="c8b80-111">观看以下视频，了解自我修复的工作原理：</span><span class="sxs-lookup"><span data-stu-id="c8b80-111">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="c8b80-112">在 Microsoft 威胁防护中，通过自愈功能进行的自动化调查和响应可在您的设备、电子邮件 & 内容和标识之间工作。</span><span class="sxs-lookup"><span data-stu-id="c8b80-112">In Microsoft Threat Protection, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span> <span data-ttu-id="c8b80-113">Microsoft 威胁防护将功能汇集在一起：</span><span class="sxs-lookup"><span data-stu-id="c8b80-113">Microsoft Threat Protection brings together capabilities from:</span></span> 
- [<span data-ttu-id="c8b80-114">Microsoft Defender 高级威胁防护中的自动化调查和修正</span><span class="sxs-lookup"><span data-stu-id="c8b80-114">Automated investigation and remediation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [<span data-ttu-id="c8b80-115">Office 365 高级威胁防护中的自动化调查和响应</span><span class="sxs-lookup"><span data-stu-id="c8b80-115">Automated investigation and response in Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [<span data-ttu-id="c8b80-116">Azure 高级威胁检测</span><span class="sxs-lookup"><span data-stu-id="c8b80-116">Azure advanced threat detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [<span data-ttu-id="c8b80-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c8b80-117">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
<span data-ttu-id="c8b80-118">本文介绍了自动化调查和响应的工作方式。</span><span class="sxs-lookup"><span data-stu-id="c8b80-118">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="c8b80-119">若要配置这些功能，请参阅 [在 Microsoft 威胁防护中配置自动调查和响应功能](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="c8b80-119">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-virtual-analyst"></a><span data-ttu-id="c8b80-120">你的虚拟分析师</span><span class="sxs-lookup"><span data-stu-id="c8b80-120">Your virtual analyst</span></span>

<span data-ttu-id="c8b80-121">想象一下，你的第 1 层/第 2 层安全运营团队中有一名虚拟分析师。</span><span class="sxs-lookup"><span data-stu-id="c8b80-121">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="c8b80-122">虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。</span><span class="sxs-lookup"><span data-stu-id="c8b80-122">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="c8b80-123">虚拟助手可以全天候工作，且容量无限制，它承担大量的调查和威胁修正工作。</span><span class="sxs-lookup"><span data-stu-id="c8b80-123">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="c8b80-124">这样的虚拟助手可以大大减少响应时间，让你的安全运营团队腾出时间来进行其他重要的战略项目。</span><span class="sxs-lookup"><span data-stu-id="c8b80-124">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="c8b80-125">如果此方案听起来像科学 fiction，则不是！</span><span class="sxs-lookup"><span data-stu-id="c8b80-125">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="c8b80-126">此类虚拟分析员是你的 Microsoft 威胁防护套件的一部分，其名称是 *自动调查和响应*。</span><span class="sxs-lookup"><span data-stu-id="c8b80-126">Such a virtual analyst is part of your Microsoft Threat Protection suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="c8b80-127">自动化调查和响应使安全操作团队能够显著提高组织处理安全警报和事件的能力。</span><span class="sxs-lookup"><span data-stu-id="c8b80-127">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="c8b80-128">通过自动调查和响应，可以降低处理调查和补救活动的成本，并充分利用威胁防护套件。</span><span class="sxs-lookup"><span data-stu-id="c8b80-128">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="c8b80-129">自动调查和响应通过以下方式帮助您的安全运营团队：</span><span class="sxs-lookup"><span data-stu-id="c8b80-129">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="c8b80-130">确定是否需要针对威胁执行操作；</span><span class="sxs-lookup"><span data-stu-id="c8b80-130">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="c8b80-131">执行（或建议执行）任何必要的修正操作；</span><span class="sxs-lookup"><span data-stu-id="c8b80-131">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="c8b80-132">确定应进行哪些其他调查；以及</span><span class="sxs-lookup"><span data-stu-id="c8b80-132">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="c8b80-133">根据需要对其他警报重复此过程。</span><span class="sxs-lookup"><span data-stu-id="c8b80-133">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="c8b80-134">自动调查流程</span><span class="sxs-lookup"><span data-stu-id="c8b80-134">The automated investigation process</span></span>

<span data-ttu-id="c8b80-135">**警报** > **事件** > **自动调查** > **裁定** > **修正操作**</span><span class="sxs-lookup"><span data-stu-id="c8b80-135">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="c8b80-136">触发的警报创建一个事件，该事件可以开始进行自动调查。</span><span class="sxs-lookup"><span data-stu-id="c8b80-136">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="c8b80-137">该调查可能会导致执行一项或多项修正操作。</span><span class="sxs-lookup"><span data-stu-id="c8b80-137">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="c8b80-138">在 Microsoft 威胁防护中，每次自动调查都会将 Azure 高级威胁防护 (Azure ATP)、Microsoft Defender 高级威胁防护 (Microsoft Defender ATP) 和 Office 365 高级威胁防护 (Office 365 ATP) 之间的信号相关联，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="c8b80-138">In Microsoft Threat Protection, each automated investigation correlates signals across Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP), and Office 365 Advanced Threat Protection (Office 365 ATP), as summarized in the following table:</span></span> 

|<span data-ttu-id="c8b80-139">实体</span><span class="sxs-lookup"><span data-stu-id="c8b80-139">Entities</span></span> |<span data-ttu-id="c8b80-140">威胁防护服务</span><span class="sxs-lookup"><span data-stu-id="c8b80-140">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="c8b80-141">设备（也称为终结点）</span><span class="sxs-lookup"><span data-stu-id="c8b80-141">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="c8b80-142">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="c8b80-142">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="c8b80-143">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="c8b80-143">Azure ATP</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="c8b80-144">电子邮件内容（邮箱中的文件和邮件）</span><span class="sxs-lookup"><span data-stu-id="c8b80-144">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="c8b80-145">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="c8b80-145">Office 365 ATP</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="c8b80-146">每个调查都会为调查) 的每个证据生成 verdicts (*恶意*、 *可疑*或不会 *发现的威胁* 。</span><span class="sxs-lookup"><span data-stu-id="c8b80-146">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="c8b80-147">根据威胁的类型和得到的结论，将自动执行更正操作，或在组织的安全操作团队批准时执行。</span><span class="sxs-lookup"><span data-stu-id="c8b80-147">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="c8b80-148">"[操作中心](mtp-action-center.md)中列出了待处理和已完成的操作。</span><span class="sxs-lookup"><span data-stu-id="c8b80-148">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="c8b80-149">运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。</span><span class="sxs-lookup"><span data-stu-id="c8b80-149">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="c8b80-150">如果在其他位置看到受影响的实体，自动调查将扩大其范围，以包括该实体，并且将运行常规安全性 Playbook。</span><span class="sxs-lookup"><span data-stu-id="c8b80-150">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="c8b80-151">并不是每个警报都会触发自动调查，并且并非每个调查都会导致自动修正操作;这一切都取决于为您的组织配置自动调查和响应的方式。</span><span class="sxs-lookup"><span data-stu-id="c8b80-151">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="c8b80-152">请参阅 [在 Microsoft 威胁防护中配置自动调查和响应功能](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="c8b80-152">See [Configure automated investigation and response capabilities in Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="c8b80-153">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c8b80-153">Next steps</span></span>

- [<span data-ttu-id="c8b80-154">请参阅 Microsoft 威胁防护中的自动调查和响应的先决条件</span><span class="sxs-lookup"><span data-stu-id="c8b80-154">See the prerequisites for automated investigation and response in Microsoft Threat Protection</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection)
- [<span data-ttu-id="c8b80-155">为你的组织配置自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="c8b80-155">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="c8b80-156">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="c8b80-156">Learn more about the Action center</span></span>](mtp-action-center.md)
