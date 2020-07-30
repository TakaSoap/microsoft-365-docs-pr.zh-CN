---
title: Microsoft 威胁防护中的自动调查遵循的补救措施
description: 获取遵循 Microsoft 威胁防护中的自动调查的修正操作概述
keywords: 自动化, 调查, 警报, 触发器, 操作, 修正
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502933"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="9a4f3-104">Microsoft 威胁防护中的自动调查遵循的补救措施</span><span class="sxs-lookup"><span data-stu-id="9a4f3-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="9a4f3-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9a4f3-105">**Applies to:**</span></span>
- <span data-ttu-id="9a4f3-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="9a4f3-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="9a4f3-107">修正操作</span><span class="sxs-lookup"><span data-stu-id="9a4f3-107">Remediation actions</span></span>

<span data-ttu-id="9a4f3-108">在 Microsoft 威胁防护的自动调查过程中和之后，会为恶意项目或可疑项目标识修正操作。</span><span class="sxs-lookup"><span data-stu-id="9a4f3-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="9a4f3-109">对设备（也称为终结点）执行某些类型的修正操作。</span><span class="sxs-lookup"><span data-stu-id="9a4f3-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="9a4f3-110">对电子邮件内容执行其他补救措施。</span><span class="sxs-lookup"><span data-stu-id="9a4f3-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="9a4f3-111">在执行、批准或拒绝补救措施之后，自动调查完成。</span><span class="sxs-lookup"><span data-stu-id="9a4f3-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="9a4f3-112">下表汇总了 Microsoft 威胁防护当前支持的补救措施：</span><span class="sxs-lookup"><span data-stu-id="9a4f3-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="9a4f3-113">设备（终结点）修正操作</span><span class="sxs-lookup"><span data-stu-id="9a4f3-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="9a4f3-114">电子邮件修正操作</span><span class="sxs-lookup"><span data-stu-id="9a4f3-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="9a4f3-115">-收集调查包</span><span class="sxs-lookup"><span data-stu-id="9a4f3-115">- Collect investigation package</span></span> <br/><span data-ttu-id="9a4f3-116">-隔离设备（可以撤消此操作）</span><span class="sxs-lookup"><span data-stu-id="9a4f3-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="9a4f3-117">-分离 machine</span><span class="sxs-lookup"><span data-stu-id="9a4f3-117">- Offboard machine</span></span> <br/><span data-ttu-id="9a4f3-118">-释放代码执行</span><span class="sxs-lookup"><span data-stu-id="9a4f3-118">- Release code execution</span></span> <br/><span data-ttu-id="9a4f3-119">-从隔离区发布</span><span class="sxs-lookup"><span data-stu-id="9a4f3-119">- Release from quarantine</span></span> <br/><span data-ttu-id="9a4f3-120">-请求示例</span><span class="sxs-lookup"><span data-stu-id="9a4f3-120">- Request sample</span></span> <br/><span data-ttu-id="9a4f3-121">-限制代码执行（可以撤消此操作）</span><span class="sxs-lookup"><span data-stu-id="9a4f3-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="9a4f3-122">-运行防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="9a4f3-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="9a4f3-123">-停止和隔离</span><span class="sxs-lookup"><span data-stu-id="9a4f3-123">- Stop and quarantine</span></span>      |<span data-ttu-id="9a4f3-124">-阻止 URL （单击时间）</span><span class="sxs-lookup"><span data-stu-id="9a4f3-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="9a4f3-125">-软删除电子邮件或群集</span><span class="sxs-lookup"><span data-stu-id="9a4f3-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="9a4f3-126">-隔离电子邮件</span><span class="sxs-lookup"><span data-stu-id="9a4f3-126">- Quarantine email</span></span><br/><span data-ttu-id="9a4f3-127">-隔离电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="9a4f3-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="9a4f3-128">-关闭外部邮件转发</span><span class="sxs-lookup"><span data-stu-id="9a4f3-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="9a4f3-129">在[操作中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)中，可以查看更正操作（无论是等待审批还是已完成）。</span><span class="sxs-lookup"><span data-stu-id="9a4f3-129">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="9a4f3-130">补救措施遵循自动调查</span><span class="sxs-lookup"><span data-stu-id="9a4f3-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="9a4f3-131">当自动调查完成时，将达到涉及的每条证据的结论，并确定修正操作。</span><span class="sxs-lookup"><span data-stu-id="9a4f3-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="9a4f3-132">在某些情况下，将自动执行更正操作;在其他情况下，补救措施等待审批。</span><span class="sxs-lookup"><span data-stu-id="9a4f3-132">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="9a4f3-133">下表列出了可能的 verdicts 和结果：</span><span class="sxs-lookup"><span data-stu-id="9a4f3-133">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="9a4f3-134">Verdict</span><span class="sxs-lookup"><span data-stu-id="9a4f3-134">Verdict</span></span>    |<span data-ttu-id="9a4f3-135">区域</span><span class="sxs-lookup"><span data-stu-id="9a4f3-135">Area</span></span>    |<span data-ttu-id="9a4f3-136">结果</span><span class="sxs-lookup"><span data-stu-id="9a4f3-136">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="9a4f3-137">恶意</span><span class="sxs-lookup"><span data-stu-id="9a4f3-137">Malicious</span></span>    |<span data-ttu-id="9a4f3-138">设备（终结点）</span><span class="sxs-lookup"><span data-stu-id="9a4f3-138">Devices (endpoints)</span></span>    |<span data-ttu-id="9a4f3-139">将自动执行更正操作</span><span class="sxs-lookup"><span data-stu-id="9a4f3-139">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="9a4f3-140">恶意</span><span class="sxs-lookup"><span data-stu-id="9a4f3-140">Malicious</span></span>    |<span data-ttu-id="9a4f3-141">电子邮件内容（Url 或附件）</span><span class="sxs-lookup"><span data-stu-id="9a4f3-141">Email content (URLs or attachments)</span></span> | <span data-ttu-id="9a4f3-142">建议的修正操作处于待审批状态</span><span class="sxs-lookup"><span data-stu-id="9a4f3-142">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="9a4f3-143">引入</span><span class="sxs-lookup"><span data-stu-id="9a4f3-143">Suspicious</span></span>    |<span data-ttu-id="9a4f3-144">设备或电子邮件内容</span><span class="sxs-lookup"><span data-stu-id="9a4f3-144">Devices or email content</span></span> |<span data-ttu-id="9a4f3-145">建议的修正操作处于待审批状态</span><span class="sxs-lookup"><span data-stu-id="9a4f3-145">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="9a4f3-146">未发现威胁</span><span class="sxs-lookup"><span data-stu-id="9a4f3-146">No threats found</span></span>    |<span data-ttu-id="9a4f3-147">设备或电子邮件内容</span><span class="sxs-lookup"><span data-stu-id="9a4f3-147">Devices or email content</span></span>    |<span data-ttu-id="9a4f3-148">不需要任何修正操作</span><span class="sxs-lookup"><span data-stu-id="9a4f3-148">No remediation actions are needed</span></span>|

[<span data-ttu-id="9a4f3-149">在操作中心中查看挂起的操作</span><span class="sxs-lookup"><span data-stu-id="9a4f3-149">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="9a4f3-150">如果你认为在 Microsoft 威胁防护中，自动调查和响应功能已丢失或错误地检测到了某些内容，请告诉我们！</span><span class="sxs-lookup"><span data-stu-id="9a4f3-150">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="9a4f3-151">[报告误报/否定](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="9a4f3-151">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9a4f3-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9a4f3-152">Next steps</span></span>

- [<span data-ttu-id="9a4f3-153">批准或拒绝操作</span><span class="sxs-lookup"><span data-stu-id="9a4f3-153">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="9a4f3-154">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="9a4f3-154">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
