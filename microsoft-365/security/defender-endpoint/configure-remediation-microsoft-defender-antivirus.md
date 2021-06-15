---
title: 为 Microsoft Defender 防病毒检测配置修正
description: 配置Microsoft Defender 防病毒威胁时应执行哪些操作，以及隔离文件应在隔离文件夹中保留多久
keywords: 修正， 修复， 删除， 威胁， 隔离， 扫描， 还原
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 9b765d14e31d6c4890aeace41e4fe79bafdd889e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925571"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a><span data-ttu-id="d47ab-104">为 Microsoft Defender 防病毒检测配置修正</span><span class="sxs-lookup"><span data-stu-id="d47ab-104">Configure remediation for Microsoft Defender Antivirus detections</span></span>


<span data-ttu-id="d47ab-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d47ab-105">**Applies to:**</span></span>

- [<span data-ttu-id="d47ab-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d47ab-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d47ab-107">当Microsoft Defender 防病毒扫描时，它会尝试修正或删除检测到的威胁。</span><span class="sxs-lookup"><span data-stu-id="d47ab-107">When Microsoft Defender Antivirus runs a scan, it attempts to remediate or remove threats that are detected.</span></span> <span data-ttu-id="d47ab-108">你可以配置Microsoft Defender 防病毒应对特定威胁、是否应在修正前创建还原点以及何时应删除威胁。</span><span class="sxs-lookup"><span data-stu-id="d47ab-108">You can configure how Microsoft Defender Antivirus should address certain threats, whether a restore point should be created before remediating, and when threats should be removed.</span></span>

<span data-ttu-id="d47ab-109">本文介绍如何使用组策略配置这些设置，但您也可以使用 Microsoft Endpoint Configuration Manager[和](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings)[Microsoft Intune](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="d47ab-109">This article describes how to configure these settings by using Group Policy, but you can also use [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) and [Microsoft Intune](/intune/device-restrictions-configure).</span></span> 

<span data-ttu-id="d47ab-110">您还可以使用[ `Set-MpPreference` PowerShell cmdlet](/powershell/module/defender/set-mppreference)或[ `MSFT_MpPreference` WMI 类](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="d47ab-110">You can also use the [`Set-MpPreference` PowerShell cmdlet](/powershell/module/defender/set-mppreference) or [`MSFT_MpPreference` WMI class](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) to configure these settings.</span></span>

## <a name="configure-remediation-options"></a><span data-ttu-id="d47ab-111">配置修正选项</span><span class="sxs-lookup"><span data-stu-id="d47ab-111">Configure remediation options</span></span>

1. <span data-ttu-id="d47ab-112">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="d47ab-112">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="d47ab-113">在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后选择 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="d47ab-113">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="d47ab-114">展开树以Windows **组件**  >  **Microsoft Defender 防病毒。**</span><span class="sxs-lookup"><span data-stu-id="d47ab-114">Expand the tree to **Windows components** > **Microsoft Defender Antivirus**.</span></span> 

4. <span data-ttu-id="d47ab-115">使用下表选择一个位置，然后根据需要编辑策略。</span><span class="sxs-lookup"><span data-stu-id="d47ab-115">Using the table below, select a location, and then edit the policy as needed.</span></span> 

5. <span data-ttu-id="d47ab-116">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="d47ab-116">Select **OK**.</span></span>

|<span data-ttu-id="d47ab-117">位置</span><span class="sxs-lookup"><span data-stu-id="d47ab-117">Location</span></span> | <span data-ttu-id="d47ab-118">设置</span><span class="sxs-lookup"><span data-stu-id="d47ab-118">Setting</span></span> | <span data-ttu-id="d47ab-119">说明</span><span class="sxs-lookup"><span data-stu-id="d47ab-119">Description</span></span> | <span data-ttu-id="d47ab-120">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="d47ab-120">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="d47ab-121">扫描</span><span class="sxs-lookup"><span data-stu-id="d47ab-121">Scan</span></span> | <span data-ttu-id="d47ab-122">创建系统还原点</span><span class="sxs-lookup"><span data-stu-id="d47ab-122">Create a system restore point</span></span> | <span data-ttu-id="d47ab-123">在尝试清理或扫描之前，将每天创建一个系统还原点</span><span class="sxs-lookup"><span data-stu-id="d47ab-123">A system restore point will be created each day before cleaning or scanning is attempted</span></span> | <span data-ttu-id="d47ab-124">禁用</span><span class="sxs-lookup"><span data-stu-id="d47ab-124">Disabled</span></span>|
|<span data-ttu-id="d47ab-125">扫描</span><span class="sxs-lookup"><span data-stu-id="d47ab-125">Scan</span></span> | <span data-ttu-id="d47ab-126">打开从扫描历史记录文件夹中删除项目</span><span class="sxs-lookup"><span data-stu-id="d47ab-126">Turn on removal of items from scan history folder</span></span> | <span data-ttu-id="d47ab-127">指定项目应在扫描历史记录中保留的天数</span><span class="sxs-lookup"><span data-stu-id="d47ab-127">Specify how many days items should be kept in the scan history</span></span> | <span data-ttu-id="d47ab-128">30 天</span><span class="sxs-lookup"><span data-stu-id="d47ab-128">30 days</span></span> |
|<span data-ttu-id="d47ab-129">根</span><span class="sxs-lookup"><span data-stu-id="d47ab-129">Root</span></span> | <span data-ttu-id="d47ab-130">关闭常规修正</span><span class="sxs-lookup"><span data-stu-id="d47ab-130">Turn off routine remediation</span></span> | <span data-ttu-id="d47ab-131">你可以指定是Microsoft Defender 防病毒自动修正威胁，还是应询问终结点用户应该怎么办。</span><span class="sxs-lookup"><span data-stu-id="d47ab-131">You can specify whether Microsoft Defender Antivirus automatically remediates threats, or if it should ask the endpoint user what to do.</span></span> | <span data-ttu-id="d47ab-132">禁用 (自动修正威胁) </span><span class="sxs-lookup"><span data-stu-id="d47ab-132">Disabled (threats are remediated automatically)</span></span> |
|<span data-ttu-id="d47ab-133">隔离</span><span class="sxs-lookup"><span data-stu-id="d47ab-133">Quarantine</span></span> | <span data-ttu-id="d47ab-134">配置从隔离文件夹删除项目</span><span class="sxs-lookup"><span data-stu-id="d47ab-134">Configure removal of items from Quarantine folder</span></span> | <span data-ttu-id="d47ab-135">指定在删除项目之前应在隔离中保留的天数</span><span class="sxs-lookup"><span data-stu-id="d47ab-135">Specify how many days items should be kept in quarantine before being removed</span></span> | <span data-ttu-id="d47ab-136">90 天</span><span class="sxs-lookup"><span data-stu-id="d47ab-136">90 days</span></span> |
|<span data-ttu-id="d47ab-137">威胁</span><span class="sxs-lookup"><span data-stu-id="d47ab-137">Threats</span></span> | <span data-ttu-id="d47ab-138">指定检测到威胁警报时不应采取默认操作的威胁警报级别</span><span class="sxs-lookup"><span data-stu-id="d47ab-138">Specify threat alert levels at which default action should not be taken when detected</span></span> | <span data-ttu-id="d47ab-139">系统为每个检测到的威胁Microsoft Defender 防病毒一个威胁级别 (低、中等、高或严重级别) 。</span><span class="sxs-lookup"><span data-stu-id="d47ab-139">Every threat that is detected by Microsoft Defender Antivirus is assigned a threat level (low, medium, high, or severe).</span></span> <span data-ttu-id="d47ab-140">可以使用此设置定义在隔离、删除或忽略每个威胁级别 (、删除或忽略威胁) </span><span class="sxs-lookup"><span data-stu-id="d47ab-140">You can use this setting to define how all threats for each of the threat levels should be remediated (quarantined, removed, or ignored)</span></span> | <span data-ttu-id="d47ab-141">不适用</span><span class="sxs-lookup"><span data-stu-id="d47ab-141">Not applicable</span></span> |
|<span data-ttu-id="d47ab-142">威胁</span><span class="sxs-lookup"><span data-stu-id="d47ab-142">Threats</span></span> | <span data-ttu-id="d47ab-143">指定检测到时不应采取默认操作的威胁</span><span class="sxs-lookup"><span data-stu-id="d47ab-143">Specify threats upon which default action should not be taken when detected</span></span> | <span data-ttu-id="d47ab-144">指定应该如何 (威胁 ID 来) 特定威胁。</span><span class="sxs-lookup"><span data-stu-id="d47ab-144">Specify how specific threats (using their threat ID) should be remediated.</span></span> <span data-ttu-id="d47ab-145">你可以指定是应隔离、删除还是忽略特定威胁</span><span class="sxs-lookup"><span data-stu-id="d47ab-145">You can specify whether the specific threat should be quarantined, removed, or ignored</span></span> | <span data-ttu-id="d47ab-146">不适用</span><span class="sxs-lookup"><span data-stu-id="d47ab-146">Not applicable</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="d47ab-147">Microsoft Defender 防病毒基于许多因素检测并修正文件。</span><span class="sxs-lookup"><span data-stu-id="d47ab-147">Microsoft Defender Antivirus detects and remediates files based on many factors.</span></span> <span data-ttu-id="d47ab-148">有时，完成修正需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="d47ab-148">Sometimes, completing a remediation requires a reboot.</span></span> <span data-ttu-id="d47ab-149">即使检测稍后被确定为误报，也必须完成重新启动以确保所有其他修正步骤已完成。</span><span class="sxs-lookup"><span data-stu-id="d47ab-149">Even if the detection is later determined to be a false positive, the reboot must be completed to ensure all additional remediation steps have been completed.</span></span>
>
> <span data-ttu-id="d47ab-150">如果确定已Microsoft Defender 防病毒误报隔离文件，可以在设备重启后从隔离中还原文件。</span><span class="sxs-lookup"><span data-stu-id="d47ab-150">If you are certain Microsoft Defender Antivirus quarantined a file based on a false positive, you can restore the file from quarantine after the device reboots.</span></span> <span data-ttu-id="d47ab-151">请参阅[Restore quarantined files in Microsoft Defender 防病毒](restore-quarantined-files-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="d47ab-151">See [Restore quarantined files in Microsoft Defender Antivirus](restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> 
> <span data-ttu-id="d47ab-152">若要在将来避免此问题，可以从扫描中排除文件。</span><span class="sxs-lookup"><span data-stu-id="d47ab-152">To avoid this problem in the future, you can exclude files from the scans.</span></span> <span data-ttu-id="d47ab-153">请参阅[配置并验证扫描Microsoft Defender 防病毒排除项](configure-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="d47ab-153">See [Configure and validate exclusions for Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="d47ab-154">另请参阅[配置修正所需的计划完整Microsoft Defender 防病毒扫描，](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed)了解与修正相关的更多设置。</span><span class="sxs-lookup"><span data-stu-id="d47ab-154">Also see [Configure remediation-required scheduled full Microsoft Defender Antivirus scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) for more remediation-related settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="d47ab-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d47ab-155">See also</span></span>

- [<span data-ttu-id="d47ab-156">配置 Microsoft Defender 防病毒软件扫描选项</span><span class="sxs-lookup"><span data-stu-id="d47ab-156">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d47ab-157">配置计划Microsoft Defender 防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="d47ab-157">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d47ab-158">配置并运行按需 Microsoft Defender 防病毒软件扫描</span><span class="sxs-lookup"><span data-stu-id="d47ab-158">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d47ab-159">配置终结点上显示的通知</span><span class="sxs-lookup"><span data-stu-id="d47ab-159">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d47ab-160">配置最终用户Microsoft Defender 防病毒交互</span><span class="sxs-lookup"><span data-stu-id="d47ab-160">Configure end-user Microsoft Defender Antivirus interaction</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d47ab-161">自定义、启动和查看扫描Microsoft Defender 防病毒修正的结果</span><span class="sxs-lookup"><span data-stu-id="d47ab-161">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d47ab-162">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d47ab-162">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
