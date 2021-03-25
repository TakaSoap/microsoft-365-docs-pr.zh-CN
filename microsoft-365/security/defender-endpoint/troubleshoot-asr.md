---
title: 解决攻击面减少规则的问题
description: 用于解决 Microsoft Defender for Endpoint 中攻击面减少规则的问题的资源和示例代码。
keywords: 疑难解答， 错误， 修复， windows defender eg， asr， 规则， hips， 疑难解答， 审核， 排除， 误报， 损坏， 阻止， microsoft defender 终结点， microsoft defender 高级威胁防护
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: d483c098f221e2d4d2e61a10393154b8f5d1498d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198737"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a><span data-ttu-id="9877e-104">攻击面减少规则疑难解答</span><span class="sxs-lookup"><span data-stu-id="9877e-104">Troubleshoot attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9877e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9877e-105">**Applies to:**</span></span>
- [<span data-ttu-id="9877e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9877e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9877e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9877e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9877e-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="9877e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9877e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="9877e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="9877e-110">当你使用 [攻击面减少规则时](attack-surface-reduction.md) ，你可能会遇到问题，例如：</span><span class="sxs-lookup"><span data-stu-id="9877e-110">When you use [attack surface reduction rules](attack-surface-reduction.md) you may run into issues, such as:</span></span>

- <span data-ttu-id="9877e-111">规则阻止文件、进程或执行其他一些不应 (误报) </span><span class="sxs-lookup"><span data-stu-id="9877e-111">A rule blocks a file, process, or performs some other action that it shouldn't (false positive)</span></span>

- <span data-ttu-id="9877e-112">规则不能如前文所述工作，也不阻止文件或进程 (漏报) </span><span class="sxs-lookup"><span data-stu-id="9877e-112">A rule doesn't work as described, or doesn't block a file or process that it should (false negative)</span></span>

<span data-ttu-id="9877e-113">解决这些问题有四个步骤：</span><span class="sxs-lookup"><span data-stu-id="9877e-113">There are four steps to troubleshooting these problems:</span></span>

1. [<span data-ttu-id="9877e-114">确认先决条件</span><span class="sxs-lookup"><span data-stu-id="9877e-114">Confirm prerequisites</span></span>](#confirm-prerequisites)

2. [<span data-ttu-id="9877e-115">使用审核模式测试规则</span><span class="sxs-lookup"><span data-stu-id="9877e-115">Use audit mode to test the rule</span></span>](#use-audit-mode-to-test-the-rule)

3. <span data-ttu-id="9877e-116">[为指定的误报规则添加 (](#add-exclusions-for-a-false-positive) 排除项) </span><span class="sxs-lookup"><span data-stu-id="9877e-116">[Add exclusions for the specified rule](#add-exclusions-for-a-false-positive) (for false positives)</span></span>

4. [<span data-ttu-id="9877e-117">提交支持日志</span><span class="sxs-lookup"><span data-stu-id="9877e-117">Submit support logs</span></span>](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a><span data-ttu-id="9877e-118">确认先决条件</span><span class="sxs-lookup"><span data-stu-id="9877e-118">Confirm prerequisites</span></span>

<span data-ttu-id="9877e-119">攻击面减少规则仅适用于具有以下条件的设备：</span><span class="sxs-lookup"><span data-stu-id="9877e-119">Attack surface reduction rules will only work on devices with the following conditions:</span></span>

- <span data-ttu-id="9877e-120">终结点运行的是 Windows 10 企业版版本 1709 (也称为 Fall Creators Update) 。</span><span class="sxs-lookup"><span data-stu-id="9877e-120">Endpoints are running Windows 10 Enterprise, version 1709 (also known as the Fall Creators Update).</span></span>

- <span data-ttu-id="9877e-121">终结点使用 Microsoft Defender 防病毒作为唯一的防病毒保护应用。</span><span class="sxs-lookup"><span data-stu-id="9877e-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="9877e-122">[使用任何其他防病毒应用将导致 Microsoft Defender AV 自行禁用](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="9877e-122">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

- <span data-ttu-id="9877e-123">[实时保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) 已启用。</span><span class="sxs-lookup"><span data-stu-id="9877e-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>

- <span data-ttu-id="9877e-124">审核模式未启用。</span><span class="sxs-lookup"><span data-stu-id="9877e-124">Audit mode isn't enabled.</span></span> <span data-ttu-id="9877e-125">使用组策略将规则设置为已禁用 (值 **：0**) 启用攻击 [面减少规则中所述](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="9877e-125">Use Group Policy to set the rule to **Disabled** (value: **0**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

<span data-ttu-id="9877e-126">如果满足所有先决条件，请继续执行下一步以在审核模式下测试规则。</span><span class="sxs-lookup"><span data-stu-id="9877e-126">If these prerequisites have all been met, proceed to the next step to test the rule in audit mode.</span></span>

## <a name="use-audit-mode-to-test-the-rule"></a><span data-ttu-id="9877e-127">使用审核模式测试规则</span><span class="sxs-lookup"><span data-stu-id="9877e-127">Use audit mode to test the rule</span></span>

<span data-ttu-id="9877e-128">你可以访问 demo.wd.microsoft.com 上的 [Windows Defender](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 测试场网站，以确认攻击面减少规则通常适用于设备上预配置的方案和流程，或者可以使用审核模式（启用仅报告规则）。</span><span class="sxs-lookup"><span data-stu-id="9877e-128">You can visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm attack surface reduction rules are generally working for pre-configured scenarios and processes on a device, or you can use audit mode, which enables rules for reporting only.</span></span>

<span data-ttu-id="9877e-129">按照使用演示 [工具中的以下](evaluate-attack-surface-reduction.md) 说明查看攻击面减少规则如何工作，以测试遇到问题的特定规则。</span><span class="sxs-lookup"><span data-stu-id="9877e-129">Follow these instructions in [Use the demo tool to see how attack surface reduction rules work](evaluate-attack-surface-reduction.md) to test the specific rule you're encountering problems with.</span></span>

1. <span data-ttu-id="9877e-130">为要测试的特定规则启用审核模式。</span><span class="sxs-lookup"><span data-stu-id="9877e-130">Enable audit mode for the specific rule you want to test.</span></span> <span data-ttu-id="9877e-131">使用组策略将规则设置为审核模式 (值 **：2**) 启用 [攻击面减少规则中所述](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="9877e-131">Use Group Policy to set the rule to **Audit mode** (value: **2**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span> <span data-ttu-id="9877e-132">审核模式允许规则报告文件或进程，但仍允许它运行。</span><span class="sxs-lookup"><span data-stu-id="9877e-132">Audit mode allows the rule to report the file or process, but will still allow it to run.</span></span>

2. <span data-ttu-id="9877e-133">执行导致问题的活动 (例如，打开或执行应阻止但允许阻止的文件或) 。</span><span class="sxs-lookup"><span data-stu-id="9877e-133">Perform the activity that is causing an issue (for example, open or execute the file or process that should be blocked but is being allowed).</span></span>

3. <span data-ttu-id="9877e-134">[查看攻击面减少规则事件](attack-surface-reduction.md) 日志，以查看如果规则已设置为"已启用"，该规则是否阻止文件或 **进程**。</span><span class="sxs-lookup"><span data-stu-id="9877e-134">[Review the attack surface reduction rule event logs](attack-surface-reduction.md) to see if the rule would have blocked the file or process if the rule had been set to **Enabled**.</span></span>

<span data-ttu-id="9877e-135">如果某个规则未阻止预期应阻止的文件或进程，则首先检查审核模式是否已启用。</span><span class="sxs-lookup"><span data-stu-id="9877e-135">If a rule isn't blocking a file or process that you're expecting it should block, first check if audit mode is enabled.</span></span>

<span data-ttu-id="9877e-136">审核模式可能已启用以测试其他功能，或者由自动 PowerShell 脚本启用，并且可能在测试完成后未禁用。</span><span class="sxs-lookup"><span data-stu-id="9877e-136">Audit mode may have been enabled for testing another feature, or by an automated PowerShell script, and may not have been disabled after the tests were completed.</span></span>

<span data-ttu-id="9877e-137">如果你已使用演示工具和审核模式测试了规则，并且攻击面减少规则正在预配置的方案中运行，但规则未按预期工作，请根据你的情况继续执行以下任一部分：</span><span class="sxs-lookup"><span data-stu-id="9877e-137">If you've tested the rule with the demo tool and with audit mode, and attack surface reduction rules are working on pre-configured scenarios, but the rule isn't working as expected, proceed to either of the following sections based on your situation:</span></span>

1. <span data-ttu-id="9877e-138">如果攻击面减少规则阻止了不应阻止的攻击 (也称为误报) ，你可以首先添加攻击面减少[规则排除 。](#add-exclusions-for-a-false-positive)</span><span class="sxs-lookup"><span data-stu-id="9877e-138">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can [first add an attack surface reduction rule exclusion](#add-exclusions-for-a-false-positive).</span></span>

2. <span data-ttu-id="9877e-139">如果攻击面减少规则不会阻止应阻止 (也称为漏报) ，你可以立即继续执行最后一步，收集诊断数据，将问题提交给 [我们](#collect-diagnostic-data-for-file-submissions)。</span><span class="sxs-lookup"><span data-stu-id="9877e-139">If the attack surface reduction rule isn't blocking something that it should block (also known as a false negative), you can proceed immediately to the last step, [collecting diagnostic data and submitting the issue to us](#collect-diagnostic-data-for-file-submissions).</span></span>

## <a name="add-exclusions-for-a-false-positive"></a><span data-ttu-id="9877e-140">添加误报的排除项</span><span class="sxs-lookup"><span data-stu-id="9877e-140">Add exclusions for a false positive</span></span>

<span data-ttu-id="9877e-141">如果攻击面减少规则阻止不应阻止的内容 (也称为误报) ，你可以添加排除项以防止攻击面减少规则评估排除的文件或文件夹。</span><span class="sxs-lookup"><span data-stu-id="9877e-141">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can add exclusions to prevent attack surface reduction rules from evaluating the excluded files or folders.</span></span>

<span data-ttu-id="9877e-142">若要添加排除项，请参阅 [自定义攻击面减少](customize-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="9877e-142">To add an exclusion, see [Customize Attack surface reduction](customize-attack-surface-reduction.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="9877e-143">可以指定要排除的单个文件和文件夹，但不能指定单个规则。</span><span class="sxs-lookup"><span data-stu-id="9877e-143">You can specify individual files and folders to be excluded, but you cannot specify individual rules.</span></span>
><span data-ttu-id="9877e-144">这意味着排除的任何文件或文件夹都将从所有 ASR 规则中排除。</span><span class="sxs-lookup"><span data-stu-id="9877e-144">This means any files or folders that are excluded will be excluded from all ASR rules.</span></span>

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="9877e-145">报告误报或漏报</span><span class="sxs-lookup"><span data-stu-id="9877e-145">Report a false positive or false negative</span></span>

<span data-ttu-id="9877e-146">使用Windows Defender [安全智能基于 Web](https://www.microsoft.com/wdsi/filesubmission) 的提交表单报告网络保护的漏报或误报。</span><span class="sxs-lookup"><span data-stu-id="9877e-146">Use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="9877e-147">使用 Windows E5 订阅，还可以 [提供指向任何关联警报的链接](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="9877e-147">With a Windows E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="9877e-148">收集文件提交的诊断数据</span><span class="sxs-lookup"><span data-stu-id="9877e-148">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="9877e-149">当你报告攻击面减少规则问题时，会要求你收集和提交诊断数据，Microsoft 支持和工程团队可以使用这些数据来帮助解决问题。</span><span class="sxs-lookup"><span data-stu-id="9877e-149">When you report a problem with attack surface reduction rules, you're asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="9877e-150">打开提升的命令提示符并更改为Windows Defender目录：</span><span class="sxs-lookup"><span data-stu-id="9877e-150">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd "c:\program files\windows defender"
   ```

2. <span data-ttu-id="9877e-151">运行此命令以生成诊断日志：</span><span class="sxs-lookup"><span data-stu-id="9877e-151">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="9877e-152">默认情况下，它们保存到 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 。</span><span class="sxs-lookup"><span data-stu-id="9877e-152">By default, they're saved to `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> <span data-ttu-id="9877e-153">将文件附加到提交表单。</span><span class="sxs-lookup"><span data-stu-id="9877e-153">Attach the file to the submission form.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9877e-154">相关文章</span><span class="sxs-lookup"><span data-stu-id="9877e-154">Related articles</span></span>

- [<span data-ttu-id="9877e-155">攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="9877e-155">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="9877e-156">启用攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="9877e-156">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)

- [<span data-ttu-id="9877e-157">评估攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="9877e-157">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
