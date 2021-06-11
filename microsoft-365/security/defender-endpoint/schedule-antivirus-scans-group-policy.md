---
title: 使用组策略计划防病毒扫描
description: 使用组策略设置防病毒扫描
keywords: 快速扫描， 完全扫描， 计划， 组策略， 防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 6f6018ec8b514234ab4f98e3d5416b472ff88739
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879664"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a><span data-ttu-id="c0e79-104">使用组策略计划防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="c0e79-104">Schedule antivirus scans using Group Policy</span></span>

<span data-ttu-id="c0e79-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c0e79-105">**Applies to:**</span></span>

- [<span data-ttu-id="c0e79-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c0e79-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c0e79-107">本文介绍如何使用组策略配置计划扫描。</span><span class="sxs-lookup"><span data-stu-id="c0e79-107">This article describes how to configure scheduled scans using Group Policy.</span></span> <span data-ttu-id="c0e79-108">若要了解有关计划扫描和扫描类型有关详细信息，请参阅配置计划的快速或完全Microsoft Defender 防病毒[扫描](schedule-antivirus-scans.md)。</span><span class="sxs-lookup"><span data-stu-id="c0e79-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="configure-antivirus-scans-using-group-policy"></a><span data-ttu-id="c0e79-109">使用组策略配置防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="c0e79-109">Configure antivirus scans using Group Policy</span></span>

1. <span data-ttu-id="c0e79-110">在组策略管理计算机上，在组策略编辑器中，转到计算机配置管理模板 Windows 组件 Microsoft Defender 防病毒  >    >    >    >  **扫描**。</span><span class="sxs-lookup"><span data-stu-id="c0e79-110">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="c0e79-111">右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="c0e79-111">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="c0e79-112">指定组策略对象的设置，**然后选择确定。**</span><span class="sxs-lookup"><span data-stu-id="c0e79-112">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="c0e79-113">对要配置的每个设置重复步骤 1-4。</span><span class="sxs-lookup"><span data-stu-id="c0e79-113">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="c0e79-114">像平常一样部署组策略对象。</span><span class="sxs-lookup"><span data-stu-id="c0e79-114">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="c0e79-115">如果需要有关组策略对象的帮助，请参阅 [创建组策略对象](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。</span><span class="sxs-lookup"><span data-stu-id="c0e79-115">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

> [!TIP]
> <span data-ttu-id="c0e79-116">请参阅 [管理何时应下载](manage-protection-update-schedule-microsoft-defender-antivirus.md) 和应用保护更新和阻止或 [允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="c0e79-116">See the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="group-policy-settings-for-scheduling-scans"></a><span data-ttu-id="c0e79-117">计划扫描的组策略设置</span><span class="sxs-lookup"><span data-stu-id="c0e79-117">Group Policy settings for scheduling scans</span></span>

| <span data-ttu-id="c0e79-118">位置</span><span class="sxs-lookup"><span data-stu-id="c0e79-118">Location</span></span> | <span data-ttu-id="c0e79-119">设置</span><span class="sxs-lookup"><span data-stu-id="c0e79-119">Setting</span></span> | <span data-ttu-id="c0e79-120">说明</span><span class="sxs-lookup"><span data-stu-id="c0e79-120">Description</span></span> | <span data-ttu-id="c0e79-121">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="c0e79-121">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
| <span data-ttu-id="c0e79-122">扫描</span><span class="sxs-lookup"><span data-stu-id="c0e79-122">Scan</span></span> | <span data-ttu-id="c0e79-123">指定用于计划扫描的扫描类型</span><span class="sxs-lookup"><span data-stu-id="c0e79-123">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="c0e79-124">快速扫描</span><span class="sxs-lookup"><span data-stu-id="c0e79-124">Quick scan</span></span> |
| <span data-ttu-id="c0e79-125">扫描</span><span class="sxs-lookup"><span data-stu-id="c0e79-125">Scan</span></span> | <span data-ttu-id="c0e79-126">指定一周中的哪些天运行计划扫描</span><span class="sxs-lookup"><span data-stu-id="c0e79-126">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="c0e79-127">指定运行 () 或从不运行扫描的日。</span><span class="sxs-lookup"><span data-stu-id="c0e79-127">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="c0e79-128">永不</span><span class="sxs-lookup"><span data-stu-id="c0e79-128">Never</span></span> |
| <span data-ttu-id="c0e79-129">扫描</span><span class="sxs-lookup"><span data-stu-id="c0e79-129">Scan</span></span> | <span data-ttu-id="c0e79-130">指定运行计划扫描的时间</span><span class="sxs-lookup"><span data-stu-id="c0e79-130">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="c0e79-131">指定午夜过后的分钟数 (例如，输入 **60** 表示上午 1 点) 。</span><span class="sxs-lookup"><span data-stu-id="c0e79-131">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="c0e79-132">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="c0e79-132">2 a.m.</span></span> |
| <span data-ttu-id="c0e79-133">根</span><span class="sxs-lookup"><span data-stu-id="c0e79-133">Root</span></span> | <span data-ttu-id="c0e79-134">随机化计划任务时间</span><span class="sxs-lookup"><span data-stu-id="c0e79-134">Randomize scheduled task times</span></span> |<span data-ttu-id="c0e79-135">在Microsoft Defender 防病毒中，将扫描的开始时间随机化为 0 到 4 小时之间的任意间隔。</span><span class="sxs-lookup"><span data-stu-id="c0e79-135">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="c0e79-136">在 [SCEP](/mem/intune/protect/certificates-scep-configure)中，将扫描随机化为任意间隔加减 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="c0e79-136">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="c0e79-137">这可在虚拟机或 VDI 部署中非常有用。</span><span class="sxs-lookup"><span data-stu-id="c0e79-137">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="c0e79-138">已启用</span><span class="sxs-lookup"><span data-stu-id="c0e79-138">Enabled</span></span> |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="c0e79-139">计划终结点不使用时扫描的组策略设置</span><span class="sxs-lookup"><span data-stu-id="c0e79-139">Group Policy settings for scheduling scans for when an endpoint is not in use</span></span>

| <span data-ttu-id="c0e79-140">位置</span><span class="sxs-lookup"><span data-stu-id="c0e79-140">Location</span></span> | <span data-ttu-id="c0e79-141">设置</span><span class="sxs-lookup"><span data-stu-id="c0e79-141">Setting</span></span> | <span data-ttu-id="c0e79-142">说明</span><span class="sxs-lookup"><span data-stu-id="c0e79-142">Description</span></span> | <span data-ttu-id="c0e79-143">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="c0e79-143">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
| <span data-ttu-id="c0e79-144">扫描</span><span class="sxs-lookup"><span data-stu-id="c0e79-144">Scan</span></span> | <span data-ttu-id="c0e79-145">仅在计算机打开但没有使用时启动计划扫描</span><span class="sxs-lookup"><span data-stu-id="c0e79-145">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="c0e79-146">计划的扫描将不会运行，除非计算机已打开但没有使用</span><span class="sxs-lookup"><span data-stu-id="c0e79-146">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="c0e79-147">已启用</span><span class="sxs-lookup"><span data-stu-id="c0e79-147">Enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="c0e79-148">在终结点不使用时计划扫描时，扫描不会接受 CPU 限制配置，并且将充分利用可用资源尽快完成扫描。</span><span class="sxs-lookup"><span data-stu-id="c0e79-148">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a><span data-ttu-id="c0e79-149">用于计划修正所需扫描的组策略设置</span><span class="sxs-lookup"><span data-stu-id="c0e79-149">Group Policy settings for scheduling remediation-required scans</span></span>

| <span data-ttu-id="c0e79-150">位置</span><span class="sxs-lookup"><span data-stu-id="c0e79-150">Location</span></span> | <span data-ttu-id="c0e79-151">设置</span><span class="sxs-lookup"><span data-stu-id="c0e79-151">Setting</span></span> | <span data-ttu-id="c0e79-152">说明</span><span class="sxs-lookup"><span data-stu-id="c0e79-152">Description</span></span> | <span data-ttu-id="c0e79-153">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="c0e79-153">Default setting (if not configured)</span></span> |
|---|---|---|---|
| <span data-ttu-id="c0e79-154">修正</span><span class="sxs-lookup"><span data-stu-id="c0e79-154">Remediation</span></span> | <span data-ttu-id="c0e79-155">指定一周中的哪些天运行计划的完全扫描以完成修正</span><span class="sxs-lookup"><span data-stu-id="c0e79-155">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="c0e79-156">指定运行 () 或从不运行扫描的日。</span><span class="sxs-lookup"><span data-stu-id="c0e79-156">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="c0e79-157">永不</span><span class="sxs-lookup"><span data-stu-id="c0e79-157">Never</span></span> |
| <span data-ttu-id="c0e79-158">修正</span><span class="sxs-lookup"><span data-stu-id="c0e79-158">Remediation</span></span> | <span data-ttu-id="c0e79-159">指定一天中运行计划完整扫描以完成修正的时间</span><span class="sxs-lookup"><span data-stu-id="c0e79-159">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="c0e79-160">指定午夜过后的分钟数 (例如，输入 **60** 表示凌晨 1 点) </span><span class="sxs-lookup"><span data-stu-id="c0e79-160">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="c0e79-161">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="c0e79-161">2 a.m.</span></span> |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a><span data-ttu-id="c0e79-162">用于计划每日扫描的组策略设置</span><span class="sxs-lookup"><span data-stu-id="c0e79-162">Group Policy settings for scheduling daily scans</span></span>

| <span data-ttu-id="c0e79-163">位置</span><span class="sxs-lookup"><span data-stu-id="c0e79-163">Location</span></span> | <span data-ttu-id="c0e79-164">设置</span><span class="sxs-lookup"><span data-stu-id="c0e79-164">Setting</span></span> | <span data-ttu-id="c0e79-165">说明</span><span class="sxs-lookup"><span data-stu-id="c0e79-165">Description</span></span> | <span data-ttu-id="c0e79-166">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="c0e79-166">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
| <span data-ttu-id="c0e79-167">扫描</span><span class="sxs-lookup"><span data-stu-id="c0e79-167">Scan</span></span> | <span data-ttu-id="c0e79-168">指定每天运行快速扫描的间隔</span><span class="sxs-lookup"><span data-stu-id="c0e79-168">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="c0e79-169">指定下一次快速扫描之前应经过的小时数。</span><span class="sxs-lookup"><span data-stu-id="c0e79-169">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="c0e79-170">例如，若要每两小时运行一次，请输入 **2，** 一天一次，请输入 **24**。</span><span class="sxs-lookup"><span data-stu-id="c0e79-170">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="c0e79-171">输入 **0** 从不运行每日快速扫描。</span><span class="sxs-lookup"><span data-stu-id="c0e79-171">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="c0e79-172">永不</span><span class="sxs-lookup"><span data-stu-id="c0e79-172">Never</span></span> |
| <span data-ttu-id="c0e79-173">扫描</span><span class="sxs-lookup"><span data-stu-id="c0e79-173">Scan</span></span> | <span data-ttu-id="c0e79-174">指定每日快速扫描的时间</span><span class="sxs-lookup"><span data-stu-id="c0e79-174">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="c0e79-175">指定午夜过后的分钟数 (例如，输入 **60** 表示凌晨 1 点) </span><span class="sxs-lookup"><span data-stu-id="c0e79-175">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="c0e79-176">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="c0e79-176">2 a.m.</span></span> |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a><span data-ttu-id="c0e79-177">用于计划保护更新后扫描的组策略设置</span><span class="sxs-lookup"><span data-stu-id="c0e79-177">Group Policy settings for scheduling scans after protection updates</span></span>

| <span data-ttu-id="c0e79-178">位置</span><span class="sxs-lookup"><span data-stu-id="c0e79-178">Location</span></span> | <span data-ttu-id="c0e79-179">设置</span><span class="sxs-lookup"><span data-stu-id="c0e79-179">Setting</span></span> | <span data-ttu-id="c0e79-180">说明</span><span class="sxs-lookup"><span data-stu-id="c0e79-180">Description</span></span> | <span data-ttu-id="c0e79-181">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="c0e79-181">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
| <span data-ttu-id="c0e79-182">签名更新</span><span class="sxs-lookup"><span data-stu-id="c0e79-182">Signature updates</span></span> | <span data-ttu-id="c0e79-183">在安全智能更新后打开扫描</span><span class="sxs-lookup"><span data-stu-id="c0e79-183">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="c0e79-184">扫描将在下载新保护更新后立即发生</span><span class="sxs-lookup"><span data-stu-id="c0e79-184">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="c0e79-185">已启用</span><span class="sxs-lookup"><span data-stu-id="c0e79-185">Enabled</span></span> |

