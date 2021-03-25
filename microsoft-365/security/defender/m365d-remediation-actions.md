---
title: Microsoft 365 Defender 中的修正操作
description: 大致了解在 Microsoft 365 Defender 中执行自动调查后采取的修正操作
keywords: 自动化, 调查, 警报, 触发器, 操作, 修正
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
ms.openlocfilehash: c81f824a0faaca1c228aa650c003576cce210a67
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199203"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="be4cc-104">Microsoft 365 Defender 中的修正操作</span><span class="sxs-lookup"><span data-stu-id="be4cc-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="be4cc-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="be4cc-105">**Applies to:**</span></span>
- <span data-ttu-id="be4cc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be4cc-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="be4cc-107">修正操作</span><span class="sxs-lookup"><span data-stu-id="be4cc-107">Remediation actions</span></span>

<span data-ttu-id="be4cc-108">在 Microsoft 365 Defender 的自动调查期间和之后，会针对恶意或可疑项目识别修正操作。</span><span class="sxs-lookup"><span data-stu-id="be4cc-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="be4cc-109">某些类型的修正操作在设备上执行，也称为终结点。</span><span class="sxs-lookup"><span data-stu-id="be4cc-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="be4cc-110">对电子邮件内容执行其他修正操作。</span><span class="sxs-lookup"><span data-stu-id="be4cc-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="be4cc-111">自动调查在采取、批准或拒绝修正操作后完成。</span><span class="sxs-lookup"><span data-stu-id="be4cc-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be4cc-112">修正操作是自动执行还是仅在审批后执行取决于某些设置，例如自动化级别的方式。</span><span class="sxs-lookup"><span data-stu-id="be4cc-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="be4cc-113">若要了解更多信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="be4cc-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="be4cc-114">在 Microsoft 365 Defender 中配置自动调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="be4cc-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="be4cc-115">如何在设备上修正威胁</span><span class="sxs-lookup"><span data-stu-id="be4cc-115">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="be4cc-116">对电子邮件和协作内容&和修正操作</span><span class="sxs-lookup"><span data-stu-id="be4cc-116">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="be4cc-117">下表总结了 Microsoft 365 Defender 中当前支持的修正操作：</span><span class="sxs-lookup"><span data-stu-id="be4cc-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="be4cc-118">设备 (终结点) 修正操作</span><span class="sxs-lookup"><span data-stu-id="be4cc-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="be4cc-119">电子邮件修正操作</span><span class="sxs-lookup"><span data-stu-id="be4cc-119">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="be4cc-120">- 收集调查包</span><span class="sxs-lookup"><span data-stu-id="be4cc-120">- Collect investigation package</span></span> <br/><span data-ttu-id="be4cc-121">- 隔离 (可以撤消此操作) </span><span class="sxs-lookup"><span data-stu-id="be4cc-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="be4cc-122">- 载出计算机</span><span class="sxs-lookup"><span data-stu-id="be4cc-122">- Offboard machine</span></span> <br/><span data-ttu-id="be4cc-123">- 释放代码执行</span><span class="sxs-lookup"><span data-stu-id="be4cc-123">- Release code execution</span></span> <br/><span data-ttu-id="be4cc-124">- 解除隔离</span><span class="sxs-lookup"><span data-stu-id="be4cc-124">- Release from quarantine</span></span> <br/><span data-ttu-id="be4cc-125">- 请求示例</span><span class="sxs-lookup"><span data-stu-id="be4cc-125">- Request sample</span></span> <br/><span data-ttu-id="be4cc-126">- 限制代码 (此操作可以撤消) </span><span class="sxs-lookup"><span data-stu-id="be4cc-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="be4cc-127">- 运行防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="be4cc-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="be4cc-128">- 停止和隔离</span><span class="sxs-lookup"><span data-stu-id="be4cc-128">- Stop and quarantine</span></span>      |<span data-ttu-id="be4cc-129">- 单击 (阻止 URL) </span><span class="sxs-lookup"><span data-stu-id="be4cc-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="be4cc-130">- 软删除电子邮件或群集</span><span class="sxs-lookup"><span data-stu-id="be4cc-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="be4cc-131">- 隔离电子邮件</span><span class="sxs-lookup"><span data-stu-id="be4cc-131">- Quarantine email</span></span><br/><span data-ttu-id="be4cc-132">- 隔离电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="be4cc-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="be4cc-133">- 关闭外部邮件转发</span><span class="sxs-lookup"><span data-stu-id="be4cc-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="be4cc-134">可在操作中心中查看修正操作（无论是等待审批还是 [已完成](m365d-action-center.md)）。</span><span class="sxs-lookup"><span data-stu-id="be4cc-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="be4cc-135">执行自动调查的修正操作</span><span class="sxs-lookup"><span data-stu-id="be4cc-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="be4cc-136">自动调查完成后，将针对涉及的每一条证据做出裁定。</span><span class="sxs-lookup"><span data-stu-id="be4cc-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="be4cc-137">根据裁定，确定修正操作。</span><span class="sxs-lookup"><span data-stu-id="be4cc-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="be4cc-138">在某些情况下，将自动执行修正操作;其他情况下，修正操作等待审批。</span><span class="sxs-lookup"><span data-stu-id="be4cc-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="be4cc-139">这完全取决于自动 [调查和响应的配置方式](m365d-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="be4cc-139">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="be4cc-140">下表列出了可能裁定和结果：</span><span class="sxs-lookup"><span data-stu-id="be4cc-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="be4cc-141">Verdict</span><span class="sxs-lookup"><span data-stu-id="be4cc-141">Verdict</span></span>    | <span data-ttu-id="be4cc-142">区域</span><span class="sxs-lookup"><span data-stu-id="be4cc-142">Area</span></span>    | <span data-ttu-id="be4cc-143">结果</span><span class="sxs-lookup"><span data-stu-id="be4cc-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="be4cc-144">恶意</span><span class="sxs-lookup"><span data-stu-id="be4cc-144">Malicious</span></span>    | <span data-ttu-id="be4cc-145">设备 (终结点) </span><span class="sxs-lookup"><span data-stu-id="be4cc-145">Devices (endpoints)</span></span>    | <span data-ttu-id="be4cc-146">如果组织的设备组 ("完全 "，将自动执行修正操作 [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) **-** 自动) </span><span class="sxs-lookup"><span data-stu-id="be4cc-146">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="be4cc-147">恶意</span><span class="sxs-lookup"><span data-stu-id="be4cc-147">Malicious</span></span>    | <span data-ttu-id="be4cc-148">电子邮件内容 (URL 或附件) </span><span class="sxs-lookup"><span data-stu-id="be4cc-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="be4cc-149">建议的修正操作正在等待审批</span><span class="sxs-lookup"><span data-stu-id="be4cc-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="be4cc-150">可疑</span><span class="sxs-lookup"><span data-stu-id="be4cc-150">Suspicious</span></span>    | <span data-ttu-id="be4cc-151">设备或电子邮件内容</span><span class="sxs-lookup"><span data-stu-id="be4cc-151">Devices or email content</span></span> | <span data-ttu-id="be4cc-152">建议的修正操作正在等待审批</span><span class="sxs-lookup"><span data-stu-id="be4cc-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="be4cc-153">未发现威胁</span><span class="sxs-lookup"><span data-stu-id="be4cc-153">No threats found</span></span>    | <span data-ttu-id="be4cc-154">设备或电子邮件内容</span><span class="sxs-lookup"><span data-stu-id="be4cc-154">Devices or email content</span></span>    | <span data-ttu-id="be4cc-155">无需修正操作</span><span class="sxs-lookup"><span data-stu-id="be4cc-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="be4cc-156">手动采取的修正操作</span><span class="sxs-lookup"><span data-stu-id="be4cc-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="be4cc-157">除了执行自动调查的修正操作之外，安全运营团队还可以手动执行某些修正操作。</span><span class="sxs-lookup"><span data-stu-id="be4cc-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="be4cc-158">其中包括以下操作：</span><span class="sxs-lookup"><span data-stu-id="be4cc-158">These include the following actions:</span></span>

- <span data-ttu-id="be4cc-159">手动设备操作，例如设备隔离或文件隔离。</span><span class="sxs-lookup"><span data-stu-id="be4cc-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="be4cc-160">手动电子邮件操作，例如软删除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="be4cc-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="be4cc-161">[设备或](../defender-endpoint/advanced-hunting-overview.md) 电子邮件上的高级搜寻操作。</span><span class="sxs-lookup"><span data-stu-id="be4cc-161">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email.</span></span>
- <span data-ttu-id="be4cc-162">[对](../office-365-security/threat-explorer.md) 电子邮件内容执行资源管理器操作，例如将电子邮件移动到垃圾邮件、软删除电子邮件或硬删除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="be4cc-162">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="be4cc-163">手动 [实时响应](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) 操作，例如删除文件、停止进程和删除计划任务。</span><span class="sxs-lookup"><span data-stu-id="be4cc-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="be4cc-164">使用 [适用于终结点](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)API 的 Microsoft Defender 执行实时响应操作，例如隔离设备、运行防病毒扫描和获取有关文件的信息。</span><span class="sxs-lookup"><span data-stu-id="be4cc-164">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="be4cc-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="be4cc-165">Next steps</span></span>

- [<span data-ttu-id="be4cc-166">访问操作中心</span><span class="sxs-lookup"><span data-stu-id="be4cc-166">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="be4cc-167">查看和管理修正操作</span><span class="sxs-lookup"><span data-stu-id="be4cc-167">View and manage remediation actions</span></span>]( m365d-autoir-actions.md)
- [<span data-ttu-id="be4cc-168">处理自动调查和响应功能中的误报/负面影响</span><span class="sxs-lookup"><span data-stu-id="be4cc-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](m365d-autoir-report-false-positives-negatives.md)
