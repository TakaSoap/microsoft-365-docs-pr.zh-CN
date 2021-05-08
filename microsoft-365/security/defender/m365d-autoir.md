---
title: Microsoft 365 Defender 中的自动调查和响应
description: 大致了解 Microsoft 365 Defender 中的自动调查和响应功能（也称为自我修复）
keywords: 自动化， 调查， 警报， 触发器， 操作， 修正， 自我修复
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fcb7283faed6fe8c5af59cedeeb90577b557ab34
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259531"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="e350f-104">Microsoft 365 Defender 中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="e350f-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e350f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e350f-105">**Applies to:**</span></span>
- <span data-ttu-id="e350f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e350f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e350f-107">如果你的组织使用[Microsoft 365 Defender，](microsoft-365-defender.md)则每当检测到恶意或可疑活动或项目Microsoft 365安全中心内收到警报。</span><span class="sxs-lookup"><span data-stu-id="e350f-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert within the Microsoft 365 security center whenever a malicious or suspicious activity or artifact is detected.</span></span> <span data-ttu-id="e350f-108">鉴于可能进入的威胁流看起来从未结束，安全团队经常面临解决大量警报的挑战。</span><span class="sxs-lookup"><span data-stu-id="e350f-108">Given the seemingly never-ending flow of threats that can come in, security teams often face the challenge of addressing the high volume of alerts.</span></span> <span data-ttu-id="e350f-109">幸运的是，Microsoft 365 Defender 包括自动调查和修正 (AIR) 功能，可帮助你的安全运营团队更高效地应对威胁。</span><span class="sxs-lookup"><span data-stu-id="e350f-109">Fortunately, Microsoft 365 Defender includes automated investigation and remediation (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="e350f-110">本文概述了 AIR，并包含指向下一步步骤和其他资源的链接。</span><span class="sxs-lookup"><span data-stu-id="e350f-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="e350f-111">希望体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="e350f-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="e350f-112">你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="e350f-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="e350f-113">自动调查和自我修复的工作原理</span><span class="sxs-lookup"><span data-stu-id="e350f-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="e350f-114">触发安全警报时，由安全运营团队来调查这些警报，并采取措施来保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="e350f-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="e350f-115">对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。</span><span class="sxs-lookup"><span data-stu-id="e350f-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="e350f-116">安全运营团队可能对必须监视和防范的大量威胁感到不知所措。</span><span class="sxs-lookup"><span data-stu-id="e350f-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="e350f-117">Defender 中的自动调查和响应功能以及自我修复Microsoft 365 Defender 可以提供帮助。</span><span class="sxs-lookup"><span data-stu-id="e350f-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="e350f-118">观看以下视频，了解自我修复的工作原理：</span><span class="sxs-lookup"><span data-stu-id="e350f-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="e350f-119">在 Microsoft 365 Defender 中，具有自我修复功能的自动调查和响应适用于你的设备、电子邮件&内容和标识。</span><span class="sxs-lookup"><span data-stu-id="e350f-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="e350f-120">本文介绍了自动调查和响应的工作原理。</span><span class="sxs-lookup"><span data-stu-id="e350f-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="e350f-121">若要配置这些功能，请参阅在 Microsoft 365 Defender 中配置[自动调查和响应功能](m365d-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="e350f-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="e350f-122">你自己的虚拟分析师</span><span class="sxs-lookup"><span data-stu-id="e350f-122">Your own virtual analyst</span></span>

<span data-ttu-id="e350f-123">Imagine级别 1 或第 2 层安全运营团队中具有虚拟分析师。</span><span class="sxs-lookup"><span data-stu-id="e350f-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="e350f-124">虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。</span><span class="sxs-lookup"><span data-stu-id="e350f-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="e350f-125">虚拟分析师可以 24x7 工作，且容量不受限制，并承担大量的调查和威胁修正工作。</span><span class="sxs-lookup"><span data-stu-id="e350f-125">The virtual analyst could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="e350f-126">此类虚拟分析师可以显著减少响应时间，释放安全运营团队用于其他重要威胁或战略项目。</span><span class="sxs-lookup"><span data-stu-id="e350f-126">Such a virtual analyst could significantly reduce the time to respond, freeing up your security operations team for other important threats or strategic projects.</span></span> <span data-ttu-id="e350f-127">如果此方案看起来像科学虚构，则不是！</span><span class="sxs-lookup"><span data-stu-id="e350f-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="e350f-128">此类虚拟分析师是你的 Microsoft 365 Defender 套件的一部分，其名称是 *自动调查和响应*。</span><span class="sxs-lookup"><span data-stu-id="e350f-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="e350f-129">自动调查和响应功能使安全运营团队可以大大增加组织处理安全警报和事件的能力。</span><span class="sxs-lookup"><span data-stu-id="e350f-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="e350f-130">通过自动调查和响应，你可以降低调查和修正活动处理的成本，并能够最利用威胁防护套件。</span><span class="sxs-lookup"><span data-stu-id="e350f-130">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="e350f-131">自动调查和响应功能可有助于安全运营团队：</span><span class="sxs-lookup"><span data-stu-id="e350f-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="e350f-132">确定威胁是否需要操作。</span><span class="sxs-lookup"><span data-stu-id="e350f-132">Determining whether a threat requires action.</span></span>
2. <span data-ttu-id="e350f-133">采取 (或建议) 必要的修正操作。</span><span class="sxs-lookup"><span data-stu-id="e350f-133">Taking (or recommending) any necessary remediation actions.</span></span>
3. <span data-ttu-id="e350f-134">确定是否应进行其他调查以及应进行哪些其他调查。</span><span class="sxs-lookup"><span data-stu-id="e350f-134">Determining whether and what other investigations should occur.</span></span>
4. <span data-ttu-id="e350f-135">根据需要对其他警报重复此过程。</span><span class="sxs-lookup"><span data-stu-id="e350f-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="e350f-136">自动调查流程</span><span class="sxs-lookup"><span data-stu-id="e350f-136">The automated investigation process</span></span>

<span data-ttu-id="e350f-137">警报将创建一个事件，可以启动自动调查。</span><span class="sxs-lookup"><span data-stu-id="e350f-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="e350f-138">自动调查会针对每条证据做出裁定。</span><span class="sxs-lookup"><span data-stu-id="e350f-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="e350f-139">裁定可以是：</span><span class="sxs-lookup"><span data-stu-id="e350f-139">Verdicts can be:</span></span>
- <span data-ttu-id="e350f-140">*恶意*</span><span class="sxs-lookup"><span data-stu-id="e350f-140">*Malicious*</span></span>
- <span data-ttu-id="e350f-141">*可疑*</span><span class="sxs-lookup"><span data-stu-id="e350f-141">*Suspicious*</span></span> 
- <span data-ttu-id="e350f-142">*未发现威胁*</span><span class="sxs-lookup"><span data-stu-id="e350f-142">*No threats found*</span></span> 

<span data-ttu-id="e350f-143">识别恶意或可疑实体的修正操作。</span><span class="sxs-lookup"><span data-stu-id="e350f-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="e350f-144">修正操作的示例包括：</span><span class="sxs-lookup"><span data-stu-id="e350f-144">Examples of remediation actions include:</span></span>

- <span data-ttu-id="e350f-145">将文件发送到隔离区</span><span class="sxs-lookup"><span data-stu-id="e350f-145">Sending a file to quarantine</span></span>
- <span data-ttu-id="e350f-146">停止进程</span><span class="sxs-lookup"><span data-stu-id="e350f-146">Stopping a process</span></span>
- <span data-ttu-id="e350f-147">隔离设备</span><span class="sxs-lookup"><span data-stu-id="e350f-147">Isolating a device</span></span>
- <span data-ttu-id="e350f-148">阻止 URL</span><span class="sxs-lookup"><span data-stu-id="e350f-148">Blocking a URL</span></span> 
- <span data-ttu-id="e350f-149">其他操作</span><span class="sxs-lookup"><span data-stu-id="e350f-149">Other actions</span></span>

<span data-ttu-id="e350f-150">有关详细信息，请参阅 Defender 中的修正[Microsoft 365操作](m365d-remediation-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="e350f-150">For more information, see See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).</span></span>

<span data-ttu-id="e350f-151">根据 [组织的自动](m365d-configure-auto-investigation-response.md) 调查和响应功能配置方式，自动执行修正操作，或仅在安全运营团队批准后执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="e350f-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="e350f-152">所有操作（无论是挂起操作还是已完成操作）都列在操作 [中心中](m365d-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e350f-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="e350f-153">运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。</span><span class="sxs-lookup"><span data-stu-id="e350f-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="e350f-154">如果在其他地方看到受影响的实体，则自动调查会扩展其范围以包括该实体，并且调查过程将重复。</span><span class="sxs-lookup"><span data-stu-id="e350f-154">If an affected entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="e350f-155">在 Microsoft 365 Defender 中，每个自动调查将 Microsoft Defender for Identity、Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 信号关联起来，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="e350f-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="e350f-156">实体</span><span class="sxs-lookup"><span data-stu-id="e350f-156">Entities</span></span> |<span data-ttu-id="e350f-157">威胁防护服务</span><span class="sxs-lookup"><span data-stu-id="e350f-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="e350f-158">设备 (也称为终结点或计算机) </span><span class="sxs-lookup"><span data-stu-id="e350f-158">Devices (also referred to as endpoints or machines)</span></span> |[<span data-ttu-id="e350f-159">适用于终结点的 Defender</span><span class="sxs-lookup"><span data-stu-id="e350f-159">Defender for Endpoint</span></span>](../defender-endpoint/automated-investigations.md) |      
|<span data-ttu-id="e350f-160">本地 Active Directory 用户、实体行为和活动</span><span class="sxs-lookup"><span data-stu-id="e350f-160">On-premises Active Directory users, entity behavior, and activities</span></span>     |[<span data-ttu-id="e350f-161">Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e350f-161">Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="e350f-162">电子邮件 (可能包含文件和 URL 的电子邮件) </span><span class="sxs-lookup"><span data-stu-id="e350f-162">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="e350f-163">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="e350f-163">Defender for Office 365</span></span>](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> <span data-ttu-id="e350f-164">不是每个警报都会触发自动调查，而并非所有调查都会触发自动修正操作。</span><span class="sxs-lookup"><span data-stu-id="e350f-164">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions.</span></span> <span data-ttu-id="e350f-165">这取决于如何为组织配置自动调查和响应。</span><span class="sxs-lookup"><span data-stu-id="e350f-165">It depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="e350f-166">请参阅 [配置自动调查和响应功能](m365d-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="e350f-166">See [Configure automated investigation and response capabilities](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="viewing-a-list-of-investigations"></a><span data-ttu-id="e350f-167">查看调查列表</span><span class="sxs-lookup"><span data-stu-id="e350f-167">Viewing a list of investigations</span></span>

<span data-ttu-id="e350f-168">若要查看调查，请转到" **事件"** 页面。</span><span class="sxs-lookup"><span data-stu-id="e350f-168">To view investigations, go to the **Incidents** page.</span></span> <span data-ttu-id="e350f-169">选择事件，然后选择" **调查"** 选项卡。若要了解详细信息， [请参阅详细信息和自动调查的结果](m365d-autoir-results.md)。</span><span class="sxs-lookup"><span data-stu-id="e350f-169">Select an incident, and then select the **Investigations** tab. To learn more, see [Details and results of an automated investigation](m365d-autoir-results.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="e350f-170">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e350f-170">Next steps</span></span>

- [<span data-ttu-id="e350f-171">请参阅自动调查和响应的先决条件</span><span class="sxs-lookup"><span data-stu-id="e350f-171">See the prerequisites for automated investigation and response</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="e350f-172">为组织配置自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="e350f-172">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="e350f-173">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="e350f-173">Learn more about the Action center</span></span>](m365d-action-center.md)
