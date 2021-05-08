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
ms.openlocfilehash: 80546d44bc1ba222c736b397a272f9f1f1a01d4a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269464"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="55b21-104">Microsoft 365 Defender 中的修正操作</span><span class="sxs-lookup"><span data-stu-id="55b21-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="55b21-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="55b21-105">**Applies to:**</span></span>
- <span data-ttu-id="55b21-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55b21-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="55b21-107">在 Microsoft 365 Defender 的自动调查期间和之后，会针对恶意或可疑项目识别修正操作。</span><span class="sxs-lookup"><span data-stu-id="55b21-107">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="55b21-108">某些类型的修正操作在设备上执行，也称为终结点。</span><span class="sxs-lookup"><span data-stu-id="55b21-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="55b21-109">对电子邮件内容执行其他修正操作。</span><span class="sxs-lookup"><span data-stu-id="55b21-109">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="55b21-110">自动调查在采取、批准或拒绝修正操作后完成。</span><span class="sxs-lookup"><span data-stu-id="55b21-110">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55b21-111">修正操作是自动执行还是仅在审批后执行取决于某些设置，例如自动化级别的方式。</span><span class="sxs-lookup"><span data-stu-id="55b21-111">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="55b21-112">若要了解更多信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="55b21-112">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="55b21-113">在 Microsoft 365 Defender 中配置自动调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="55b21-113">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="55b21-114">如何在设备上修正威胁</span><span class="sxs-lookup"><span data-stu-id="55b21-114">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="55b21-115">对电子邮件和协作内容&和修正操作</span><span class="sxs-lookup"><span data-stu-id="55b21-115">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="55b21-116">下表总结了 Microsoft 365 Defender 中当前支持的修正操作。</span><span class="sxs-lookup"><span data-stu-id="55b21-116">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender.</span></span> 

|<span data-ttu-id="55b21-117">设备 (终结点) 修正操作</span><span class="sxs-lookup"><span data-stu-id="55b21-117">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="55b21-118">电子邮件修正操作</span><span class="sxs-lookup"><span data-stu-id="55b21-118">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="55b21-119">- 收集调查包</span><span class="sxs-lookup"><span data-stu-id="55b21-119">- Collect investigation package</span></span> <br/><span data-ttu-id="55b21-120">- 隔离 (可以撤消此操作) </span><span class="sxs-lookup"><span data-stu-id="55b21-120">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="55b21-121">- 载出计算机</span><span class="sxs-lookup"><span data-stu-id="55b21-121">- Offboard machine</span></span> <br/><span data-ttu-id="55b21-122">- 释放代码执行</span><span class="sxs-lookup"><span data-stu-id="55b21-122">- Release code execution</span></span> <br/><span data-ttu-id="55b21-123">- 解除隔离</span><span class="sxs-lookup"><span data-stu-id="55b21-123">- Release from quarantine</span></span> <br/><span data-ttu-id="55b21-124">- 请求示例</span><span class="sxs-lookup"><span data-stu-id="55b21-124">- Request sample</span></span> <br/><span data-ttu-id="55b21-125">- 限制代码 (此操作可以撤消) </span><span class="sxs-lookup"><span data-stu-id="55b21-125">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="55b21-126">- 运行防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="55b21-126">- Run antivirus scan</span></span> <br/><span data-ttu-id="55b21-127">- 停止和隔离</span><span class="sxs-lookup"><span data-stu-id="55b21-127">- Stop and quarantine</span></span>      |<span data-ttu-id="55b21-128">- 单击 (阻止 URL) </span><span class="sxs-lookup"><span data-stu-id="55b21-128">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="55b21-129">- 软删除电子邮件或群集</span><span class="sxs-lookup"><span data-stu-id="55b21-129">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="55b21-130">- 隔离电子邮件</span><span class="sxs-lookup"><span data-stu-id="55b21-130">- Quarantine email</span></span><br/><span data-ttu-id="55b21-131">- 隔离电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="55b21-131">- Quarantine an email attachment</span></span><br/><span data-ttu-id="55b21-132">- 关闭外部邮件转发</span><span class="sxs-lookup"><span data-stu-id="55b21-132">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="55b21-133">可在操作中心中查看修正操作（无论是等待审批还是 [已完成](m365d-action-center.md)）。</span><span class="sxs-lookup"><span data-stu-id="55b21-133">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="55b21-134">执行自动调查的修正操作</span><span class="sxs-lookup"><span data-stu-id="55b21-134">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="55b21-135">自动调查完成后，将针对涉及的每一条证据做出裁定。</span><span class="sxs-lookup"><span data-stu-id="55b21-135">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="55b21-136">根据裁定，确定修正操作。</span><span class="sxs-lookup"><span data-stu-id="55b21-136">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="55b21-137">在某些情况下，将自动执行修正操作;其他情况下，修正操作等待审批。</span><span class="sxs-lookup"><span data-stu-id="55b21-137">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="55b21-138">这完全取决于自动 [调查和响应的配置方式](m365d-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="55b21-138">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="55b21-139">下表列出了可能裁定和结果：</span><span class="sxs-lookup"><span data-stu-id="55b21-139">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="55b21-140">Verdict</span><span class="sxs-lookup"><span data-stu-id="55b21-140">Verdict</span></span>    | <span data-ttu-id="55b21-141">受影响的实体</span><span class="sxs-lookup"><span data-stu-id="55b21-141">Affected entities</span></span>    | <span data-ttu-id="55b21-142">结果</span><span class="sxs-lookup"><span data-stu-id="55b21-142">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="55b21-143">恶意</span><span class="sxs-lookup"><span data-stu-id="55b21-143">Malicious</span></span>    | <span data-ttu-id="55b21-144">设备 (终结点) </span><span class="sxs-lookup"><span data-stu-id="55b21-144">Devices (endpoints)</span></span>    | <span data-ttu-id="55b21-145">如果组织的设备组 ("完全 "，将自动执行修正操作 [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) **-** 自动) </span><span class="sxs-lookup"><span data-stu-id="55b21-145">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="55b21-146">恶意</span><span class="sxs-lookup"><span data-stu-id="55b21-146">Malicious</span></span>    | <span data-ttu-id="55b21-147">电子邮件内容 (URL 或附件) </span><span class="sxs-lookup"><span data-stu-id="55b21-147">Email content (URLs or attachments)</span></span> | <span data-ttu-id="55b21-148">建议的修正操作正在等待审批</span><span class="sxs-lookup"><span data-stu-id="55b21-148">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="55b21-149">可疑</span><span class="sxs-lookup"><span data-stu-id="55b21-149">Suspicious</span></span>    | <span data-ttu-id="55b21-150">设备或电子邮件内容</span><span class="sxs-lookup"><span data-stu-id="55b21-150">Devices or email content</span></span> | <span data-ttu-id="55b21-151">建议的修正操作正在等待审批</span><span class="sxs-lookup"><span data-stu-id="55b21-151">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="55b21-152">未发现威胁</span><span class="sxs-lookup"><span data-stu-id="55b21-152">No threats found</span></span>    | <span data-ttu-id="55b21-153">设备或电子邮件内容</span><span class="sxs-lookup"><span data-stu-id="55b21-153">Devices or email content</span></span>    | <span data-ttu-id="55b21-154">无需修正操作</span><span class="sxs-lookup"><span data-stu-id="55b21-154">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="55b21-155">手动采取的修正操作</span><span class="sxs-lookup"><span data-stu-id="55b21-155">Remediation actions that are taken manually</span></span>

<span data-ttu-id="55b21-156">除了执行自动调查的修正操作之外，安全运营团队还可以手动执行某些修正操作。</span><span class="sxs-lookup"><span data-stu-id="55b21-156">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="55b21-157">其中包括以下项：</span><span class="sxs-lookup"><span data-stu-id="55b21-157">These include the following:</span></span>

- <span data-ttu-id="55b21-158">手动设备操作，例如设备隔离或文件隔离</span><span class="sxs-lookup"><span data-stu-id="55b21-158">Manual device action, such as device isolation or file quarantine</span></span>
- <span data-ttu-id="55b21-159">手动电子邮件操作，例如软删除电子邮件</span><span class="sxs-lookup"><span data-stu-id="55b21-159">Manual email action, such as soft-deleting email messages</span></span> 
- <span data-ttu-id="55b21-160">[设备或](../defender-endpoint/advanced-hunting-overview.md) 电子邮件上的高级搜寻操作</span><span class="sxs-lookup"><span data-stu-id="55b21-160">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email</span></span>
- <span data-ttu-id="55b21-161">[对](../office-365-security/threat-explorer.md) 电子邮件内容的资源管理器操作，例如将电子邮件移动到垃圾邮件、软删除电子邮件或硬删除电子邮件</span><span class="sxs-lookup"><span data-stu-id="55b21-161">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email</span></span>
- <span data-ttu-id="55b21-162">手动 [实时响应](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) 操作，例如删除文件、停止进程和删除计划任务</span><span class="sxs-lookup"><span data-stu-id="55b21-162">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task</span></span>
- <span data-ttu-id="55b21-163">使用 Microsoft [Defender for Endpoint API](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)执行实时响应操作，例如隔离设备、运行防病毒扫描和获取有关文件的信息</span><span class="sxs-lookup"><span data-stu-id="55b21-163">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file</span></span>

## <a name="next-steps"></a><span data-ttu-id="55b21-164">后续步骤</span><span class="sxs-lookup"><span data-stu-id="55b21-164">Next steps</span></span>

- [<span data-ttu-id="55b21-165">访问操作中心</span><span class="sxs-lookup"><span data-stu-id="55b21-165">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="55b21-166">查看和管理修正操作</span><span class="sxs-lookup"><span data-stu-id="55b21-166">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="55b21-167">解决误报或漏报问题</span><span class="sxs-lookup"><span data-stu-id="55b21-167">Address false positives or false negatives</span></span>](m365d-autoir-report-false-positives-negatives.md)
