---
title: Microsoft 365 Defender 中的自动调查遵循的补救措施
description: 获取遵循 Microsoft 365 Defender 中的自动调查的修正操作概述
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 71cdf2d1b9a40e9cfbf487ca8596a0c2b09475d1
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847208"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-365-defender"></a><span data-ttu-id="9448d-104">Microsoft 365 Defender 中的自动调查遵循的补救措施</span><span class="sxs-lookup"><span data-stu-id="9448d-104">Remediation actions following automated investigations in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9448d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9448d-105">**Applies to:**</span></span>
- <span data-ttu-id="9448d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9448d-106">Microsoft 365 Defender</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="9448d-107">修正操作</span><span class="sxs-lookup"><span data-stu-id="9448d-107">Remediation actions</span></span>

<span data-ttu-id="9448d-108">在 Microsoft 365 Defender 中进行自动调查的过程中和之后，会为恶意项目或可疑项目标识修正操作。</span><span class="sxs-lookup"><span data-stu-id="9448d-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="9448d-109">对设备（也称为终结点）执行某些类型的修正操作。</span><span class="sxs-lookup"><span data-stu-id="9448d-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="9448d-110">对电子邮件内容执行其他补救措施。</span><span class="sxs-lookup"><span data-stu-id="9448d-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="9448d-111">在执行、批准或拒绝补救措施之后，自动调查完成。</span><span class="sxs-lookup"><span data-stu-id="9448d-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="9448d-112">下表汇总了 Microsoft 365 Defender 当前支持的补救措施：</span><span class="sxs-lookup"><span data-stu-id="9448d-112">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="9448d-113">设备 (终结点) 修正操作</span><span class="sxs-lookup"><span data-stu-id="9448d-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="9448d-114">电子邮件修正操作</span><span class="sxs-lookup"><span data-stu-id="9448d-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="9448d-115">-收集调查包</span><span class="sxs-lookup"><span data-stu-id="9448d-115">- Collect investigation package</span></span> <br/><span data-ttu-id="9448d-116">-隔离设备 (可以撤消此操作) </span><span class="sxs-lookup"><span data-stu-id="9448d-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="9448d-117">-分离 machine</span><span class="sxs-lookup"><span data-stu-id="9448d-117">- Offboard machine</span></span> <br/><span data-ttu-id="9448d-118">-释放代码执行</span><span class="sxs-lookup"><span data-stu-id="9448d-118">- Release code execution</span></span> <br/><span data-ttu-id="9448d-119">-从隔离区发布</span><span class="sxs-lookup"><span data-stu-id="9448d-119">- Release from quarantine</span></span> <br/><span data-ttu-id="9448d-120">-请求示例</span><span class="sxs-lookup"><span data-stu-id="9448d-120">- Request sample</span></span> <br/><span data-ttu-id="9448d-121">-限制代码执行 (可以撤消此操作) </span><span class="sxs-lookup"><span data-stu-id="9448d-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="9448d-122">-运行防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="9448d-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="9448d-123">-停止和隔离</span><span class="sxs-lookup"><span data-stu-id="9448d-123">- Stop and quarantine</span></span>      |<span data-ttu-id="9448d-124">-阻止 URL (单击时间) </span><span class="sxs-lookup"><span data-stu-id="9448d-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="9448d-125">-软删除电子邮件或群集</span><span class="sxs-lookup"><span data-stu-id="9448d-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="9448d-126">-隔离电子邮件</span><span class="sxs-lookup"><span data-stu-id="9448d-126">- Quarantine email</span></span><br/><span data-ttu-id="9448d-127">-隔离电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="9448d-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="9448d-128">-关闭外部邮件转发</span><span class="sxs-lookup"><span data-stu-id="9448d-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="9448d-129">在 [操作中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)中，可以查看更正操作（无论是待批准还是已完成）。</span><span class="sxs-lookup"><span data-stu-id="9448d-129">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="9448d-130">补救措施遵循自动调查</span><span class="sxs-lookup"><span data-stu-id="9448d-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="9448d-131">当自动调查完成时，涉及的每条证据都将达到一个结论。</span><span class="sxs-lookup"><span data-stu-id="9448d-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="9448d-132">根据判定的具体情况，将确定修正操作。</span><span class="sxs-lookup"><span data-stu-id="9448d-132">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="9448d-133">在某些情况下，将自动执行更正操作;在其他情况下，补救措施等待审批。</span><span class="sxs-lookup"><span data-stu-id="9448d-133">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="9448d-134">这一切都取决于如何 [配置自动调查和响应](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="9448d-134">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="9448d-135">下表列出了可能的 verdicts 和结果：</span><span class="sxs-lookup"><span data-stu-id="9448d-135">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="9448d-136">Verdict</span><span class="sxs-lookup"><span data-stu-id="9448d-136">Verdict</span></span>    |<span data-ttu-id="9448d-137">区域</span><span class="sxs-lookup"><span data-stu-id="9448d-137">Area</span></span>    |<span data-ttu-id="9448d-138">结果</span><span class="sxs-lookup"><span data-stu-id="9448d-138">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="9448d-139">恶意</span><span class="sxs-lookup"><span data-stu-id="9448d-139">Malicious</span></span>    |<span data-ttu-id="9448d-140">设备 (终结点) </span><span class="sxs-lookup"><span data-stu-id="9448d-140">Devices (endpoints)</span></span>    |<span data-ttu-id="9448d-141">如果您的组织的 [设备组](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) 自动设置为 **完全修正的威胁** ，则会自动执行更正操作 () </span><span class="sxs-lookup"><span data-stu-id="9448d-141">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically** )</span></span>|
|<span data-ttu-id="9448d-142">恶意</span><span class="sxs-lookup"><span data-stu-id="9448d-142">Malicious</span></span>    |<span data-ttu-id="9448d-143"> (Url 或附件的电子邮件内容) </span><span class="sxs-lookup"><span data-stu-id="9448d-143">Email content (URLs or attachments)</span></span> | <span data-ttu-id="9448d-144">建议的修正操作处于待审批状态</span><span class="sxs-lookup"><span data-stu-id="9448d-144">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="9448d-145">引入</span><span class="sxs-lookup"><span data-stu-id="9448d-145">Suspicious</span></span>    |<span data-ttu-id="9448d-146">设备或电子邮件内容</span><span class="sxs-lookup"><span data-stu-id="9448d-146">Devices or email content</span></span> |<span data-ttu-id="9448d-147">建议的修正操作处于待审批状态</span><span class="sxs-lookup"><span data-stu-id="9448d-147">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="9448d-148">未发现威胁</span><span class="sxs-lookup"><span data-stu-id="9448d-148">No threats found</span></span>    |<span data-ttu-id="9448d-149">设备或电子邮件内容</span><span class="sxs-lookup"><span data-stu-id="9448d-149">Devices or email content</span></span>    |<span data-ttu-id="9448d-150">不需要任何修正操作</span><span class="sxs-lookup"><span data-stu-id="9448d-150">No remediation actions are needed</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="9448d-151">是否自动执行更正操作，或仅在批准操作时才会依赖某些设置，如组织的设备组策略。</span><span class="sxs-lookup"><span data-stu-id="9448d-151">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as your organization's device group policies.</span></span> <span data-ttu-id="9448d-152">若要了解详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="9448d-152">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="9448d-153">在 Microsoft 365 Defender 中配置自动调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="9448d-153">Configure automated investigation and response capabilities in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="9448d-154">如何修正设备上的威胁</span><span class="sxs-lookup"><span data-stu-id="9448d-154">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a><span data-ttu-id="9448d-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9448d-155">Next steps</span></span>

- [<span data-ttu-id="9448d-156">访问操作中心</span><span class="sxs-lookup"><span data-stu-id="9448d-156">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="9448d-157">批准或拒绝挂起的操作</span><span class="sxs-lookup"><span data-stu-id="9448d-157">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="9448d-158">处理自动调查和响应功能中的误报/否定</span><span class="sxs-lookup"><span data-stu-id="9448d-158">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
