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
ms.openlocfilehash: ca0c557de24320692d903a1136fc434d635f0507
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955587"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="76eb2-104">Microsoft 威胁防护中的自动调查遵循的补救措施</span><span class="sxs-lookup"><span data-stu-id="76eb2-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="76eb2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="76eb2-105">**Applies to:**</span></span>
- <span data-ttu-id="76eb2-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="76eb2-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="76eb2-107">修正操作</span><span class="sxs-lookup"><span data-stu-id="76eb2-107">Remediation actions</span></span>

<span data-ttu-id="76eb2-108">在 Microsoft 威胁防护的自动调查过程中和之后，会为恶意项目或可疑项目标识修正操作。</span><span class="sxs-lookup"><span data-stu-id="76eb2-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="76eb2-109">对设备（也称为终结点）执行某些类型的修正操作。</span><span class="sxs-lookup"><span data-stu-id="76eb2-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="76eb2-110">对电子邮件内容执行其他补救措施。</span><span class="sxs-lookup"><span data-stu-id="76eb2-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="76eb2-111">在执行、批准或拒绝补救措施之后，自动调查完成。</span><span class="sxs-lookup"><span data-stu-id="76eb2-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="76eb2-112">下表汇总了 Microsoft 威胁防护当前支持的补救措施：</span><span class="sxs-lookup"><span data-stu-id="76eb2-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="76eb2-113">设备（终结点）修正操作</span><span class="sxs-lookup"><span data-stu-id="76eb2-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="76eb2-114">电子邮件修正操作</span><span class="sxs-lookup"><span data-stu-id="76eb2-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="76eb2-115">隔离</span><span class="sxs-lookup"><span data-stu-id="76eb2-115">Quarantine file</span></span><br/><span data-ttu-id="76eb2-116">删除注册表项</span><span class="sxs-lookup"><span data-stu-id="76eb2-116">Remove registry key</span></span><br/><span data-ttu-id="76eb2-117">终止进程</span><span class="sxs-lookup"><span data-stu-id="76eb2-117">Kill process</span></span> <br/><span data-ttu-id="76eb2-118">停止服务</span><span class="sxs-lookup"><span data-stu-id="76eb2-118">Stop service</span></span> <br/><span data-ttu-id="76eb2-119">禁用驱动程序</span><span class="sxs-lookup"><span data-stu-id="76eb2-119">Disable driver</span></span> <br/><span data-ttu-id="76eb2-120">删除计划任务</span><span class="sxs-lookup"><span data-stu-id="76eb2-120">Remove scheduled task</span></span>      |<span data-ttu-id="76eb2-121">软删除电子邮件或群集</span><span class="sxs-lookup"><span data-stu-id="76eb2-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="76eb2-122">阻止 URL（单击时）</span><span class="sxs-lookup"><span data-stu-id="76eb2-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="76eb2-123">关闭外部邮件转发</span><span class="sxs-lookup"><span data-stu-id="76eb2-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="76eb2-124">在[操作中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)中，可以查看更正操作（无论是等待审批还是已完成）。</span><span class="sxs-lookup"><span data-stu-id="76eb2-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="76eb2-125">补救措施遵循自动调查</span><span class="sxs-lookup"><span data-stu-id="76eb2-125">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="76eb2-126">当自动调查完成时，将达到涉及的每条证据的结论，并确定修正操作。</span><span class="sxs-lookup"><span data-stu-id="76eb2-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="76eb2-127">在某些情况下，将自动执行更正操作;在其他情况下，补救措施等待审批。</span><span class="sxs-lookup"><span data-stu-id="76eb2-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="76eb2-128">下表列出了可能的 verdicts 和结果：</span><span class="sxs-lookup"><span data-stu-id="76eb2-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="76eb2-129">Verdict</span><span class="sxs-lookup"><span data-stu-id="76eb2-129">Verdict</span></span>    |<span data-ttu-id="76eb2-130">区域</span><span class="sxs-lookup"><span data-stu-id="76eb2-130">Area</span></span>    |<span data-ttu-id="76eb2-131">结果</span><span class="sxs-lookup"><span data-stu-id="76eb2-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="76eb2-132">恶意</span><span class="sxs-lookup"><span data-stu-id="76eb2-132">Malicious</span></span>    |<span data-ttu-id="76eb2-133">设备（终结点）</span><span class="sxs-lookup"><span data-stu-id="76eb2-133">Devices (endpoints)</span></span>    |<span data-ttu-id="76eb2-134">将自动执行更正操作</span><span class="sxs-lookup"><span data-stu-id="76eb2-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="76eb2-135">恶意</span><span class="sxs-lookup"><span data-stu-id="76eb2-135">Malicious</span></span>    |<span data-ttu-id="76eb2-136">电子邮件内容（Url 或附件）</span><span class="sxs-lookup"><span data-stu-id="76eb2-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="76eb2-137">建议的修正操作处于待审批状态</span><span class="sxs-lookup"><span data-stu-id="76eb2-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="76eb2-138">引入</span><span class="sxs-lookup"><span data-stu-id="76eb2-138">Suspicious</span></span>    |<span data-ttu-id="76eb2-139">设备或电子邮件内容</span><span class="sxs-lookup"><span data-stu-id="76eb2-139">Devices or email content</span></span> |<span data-ttu-id="76eb2-140">建议的修正操作处于待审批状态</span><span class="sxs-lookup"><span data-stu-id="76eb2-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="76eb2-141">未发现威胁</span><span class="sxs-lookup"><span data-stu-id="76eb2-141">No threats found</span></span>    |<span data-ttu-id="76eb2-142">设备或电子邮件内容</span><span class="sxs-lookup"><span data-stu-id="76eb2-142">Devices or email content</span></span>    |<span data-ttu-id="76eb2-143">不需要任何修正操作</span><span class="sxs-lookup"><span data-stu-id="76eb2-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="76eb2-144">在操作中心中查看挂起的操作</span><span class="sxs-lookup"><span data-stu-id="76eb2-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="76eb2-145">如果你认为在 Microsoft 威胁防护中，自动调查和响应功能已丢失或错误地检测到了某些内容，请告诉我们！</span><span class="sxs-lookup"><span data-stu-id="76eb2-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="76eb2-146">[报告误报/否定](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="76eb2-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="76eb2-147">后续步骤</span><span class="sxs-lookup"><span data-stu-id="76eb2-147">Next steps</span></span>

- [<span data-ttu-id="76eb2-148">批准或拒绝操作</span><span class="sxs-lookup"><span data-stu-id="76eb2-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="76eb2-149">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="76eb2-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
