---
title: 为 Microsoft Defender AV 设置配置本地覆盖
description: 启用或禁用用户在本地更改 Microsoft Defender AV 中的设置。
keywords: 本地覆盖， 本地策略， 组策略， gpo， 锁定， 合并， 列表
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f3c2b7ae70f42cb7ffc2deef1786ad43e65f33b6
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764635"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a><span data-ttu-id="9f4ae-104">阻止或允许用户在本地修改 Microsoft Defender 防病毒策略设置</span><span class="sxs-lookup"><span data-stu-id="9f4ae-104">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9f4ae-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9f4ae-105">**Applies to:**</span></span>

- [<span data-ttu-id="9f4ae-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9f4ae-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9f4ae-107">默认情况下，通过组策略对象部署到网络中终结点的 Microsoft Defender 防病毒设置将阻止用户在本地更改设置。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-107">By default, Microsoft Defender Antivirus settings that are deployed via a Group Policy Object to the endpoints in your network will prevent users from locally changing the settings.</span></span> <span data-ttu-id="9f4ae-108">在某些实例中可以更改此情况。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-108">You can change this in some instances.</span></span>

<span data-ttu-id="9f4ae-109">例如，可能需要允许某些用户组 (例如安全研究人员和威胁) 进一步控制他们使用的终结点上的单个设置。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-109">For example, it may be necessary to allow certain user groups (such as security researchers and threat investigators) further control over individual settings on the endpoints they use.</span></span>

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a><span data-ttu-id="9f4ae-110">配置 Microsoft Defender 防病毒设置的本地覆盖</span><span class="sxs-lookup"><span data-stu-id="9f4ae-110">Configure local overrides for Microsoft Defender Antivirus settings</span></span>

<span data-ttu-id="9f4ae-111">这些策略的默认设置是 **Disabled**。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-111">The default setting for these policies is **Disabled**.</span></span>

<span data-ttu-id="9f4ae-112">如果设置为"已启用"，则终结点上的用户可以使用[Windows](microsoft-defender-security-center-antivirus.md)安全应用、本地组策略设置和 PowerShell cmdlet 对关联的设置进行更改， (适当的) 。 </span><span class="sxs-lookup"><span data-stu-id="9f4ae-112">If they are set to **Enabled**, users on endpoints can make changes to the associated setting with the [Windows Security](microsoft-defender-security-center-antivirus.md) app, local Group Policy settings, and PowerShell cmdlets (where appropriate).</span></span>

<span data-ttu-id="9f4ae-113">下表列出了每个替代策略设置以及关联的功能或设置的配置说明。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-113">The following table lists each of the override policy setting and the configuration instructions for the associated feature or setting.</span></span>

<span data-ttu-id="9f4ae-114">配置这些设置：</span><span class="sxs-lookup"><span data-stu-id="9f4ae-114">To configure these settings:</span></span>

1. <span data-ttu-id="9f4ae-115">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="9f4ae-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="9f4ae-116">在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="9f4ae-117">将树展开到 **Microsoft Defender > Windows** 组件，然后展开下表中指定的位置。 </span><span class="sxs-lookup"><span data-stu-id="9f4ae-117">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

4. <span data-ttu-id="9f4ae-118">双击 **下表中指定的** 策略设置，将选项设置为所需的配置。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-118">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> <span data-ttu-id="9f4ae-119">单击 **"确定**"，然后对任何其他设置重复上述操作。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-119">Click **OK**, and repeat for any other settings.</span></span>

5. <span data-ttu-id="9f4ae-120">像往常一样部署组策略对象。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-120">Deploy the Group Policy Object as usual.</span></span>

<span data-ttu-id="9f4ae-121">位置</span><span class="sxs-lookup"><span data-stu-id="9f4ae-121">Location</span></span> | <span data-ttu-id="9f4ae-122">设置</span><span class="sxs-lookup"><span data-stu-id="9f4ae-122">Setting</span></span> | <span data-ttu-id="9f4ae-123">文章</span><span class="sxs-lookup"><span data-stu-id="9f4ae-123">Article</span></span>
---|---|---|---
<span data-ttu-id="9f4ae-124">MAPS</span><span class="sxs-lookup"><span data-stu-id="9f4ae-124">MAPS</span></span> | <span data-ttu-id="9f4ae-125">配置向 Microsoft MAPS 报告的本地设置替代</span><span class="sxs-lookup"><span data-stu-id="9f4ae-125">Configure local setting override for reporting to Microsoft MAPS</span></span> | [<span data-ttu-id="9f4ae-126">启用云保护</span><span class="sxs-lookup"><span data-stu-id="9f4ae-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="9f4ae-127">隔离</span><span class="sxs-lookup"><span data-stu-id="9f4ae-127">Quarantine</span></span> | <span data-ttu-id="9f4ae-128">为从隔离文件夹中删除项目配置本地设置替代</span><span class="sxs-lookup"><span data-stu-id="9f4ae-128">Configure local setting override for the removal of items from Quarantine folder</span></span> | [<span data-ttu-id="9f4ae-129">配置扫描修正</span><span class="sxs-lookup"><span data-stu-id="9f4ae-129">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
<span data-ttu-id="9f4ae-130">实时保护</span><span class="sxs-lookup"><span data-stu-id="9f4ae-130">Real-time protection</span></span> | <span data-ttu-id="9f4ae-131">配置本地设置覆盖以监视您的计算机上的文件和程序活动</span><span class="sxs-lookup"><span data-stu-id="9f4ae-131">Configure local setting override for monitoring file and program activity on your computer</span></span> | [<span data-ttu-id="9f4ae-132">启用和配置 Microsoft Defender 防病毒始终启用保护和监视</span><span class="sxs-lookup"><span data-stu-id="9f4ae-132">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="9f4ae-133">实时保护</span><span class="sxs-lookup"><span data-stu-id="9f4ae-133">Real-time protection</span></span> | <span data-ttu-id="9f4ae-134">配置本地设置覆盖以监视传入和传出文件活动</span><span class="sxs-lookup"><span data-stu-id="9f4ae-134">Configure local setting override for monitoring for incoming and outgoing file activity</span></span> | [<span data-ttu-id="9f4ae-135">启用和配置 Microsoft Defender 防病毒始终启用保护和监视</span><span class="sxs-lookup"><span data-stu-id="9f4ae-135">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="9f4ae-136">实时保护</span><span class="sxs-lookup"><span data-stu-id="9f4ae-136">Real-time protection</span></span> | <span data-ttu-id="9f4ae-137">配置用于扫描所有下载的文件和附件的本地设置替代</span><span class="sxs-lookup"><span data-stu-id="9f4ae-137">Configure local setting override for scanning all downloaded files and attachments</span></span> | [<span data-ttu-id="9f4ae-138">启用和配置 Microsoft Defender 防病毒始终启用保护和监视</span><span class="sxs-lookup"><span data-stu-id="9f4ae-138">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="9f4ae-139">实时保护</span><span class="sxs-lookup"><span data-stu-id="9f4ae-139">Real-time protection</span></span> | <span data-ttu-id="9f4ae-140">配置本地设置替代以启用行为监视</span><span class="sxs-lookup"><span data-stu-id="9f4ae-140">Configure local setting override for turn on behavior monitoring</span></span> | [<span data-ttu-id="9f4ae-141">启用和配置 Microsoft Defender 防病毒始终启用保护和监视</span><span class="sxs-lookup"><span data-stu-id="9f4ae-141">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="9f4ae-142">实时保护</span><span class="sxs-lookup"><span data-stu-id="9f4ae-142">Real-time protection</span></span> | <span data-ttu-id="9f4ae-143">配置本地设置覆盖以启用实时保护</span><span class="sxs-lookup"><span data-stu-id="9f4ae-143">Configure local setting override to turn on real-time protection</span></span> | [<span data-ttu-id="9f4ae-144">启用和配置 Microsoft Defender 防病毒始终启用保护和监视</span><span class="sxs-lookup"><span data-stu-id="9f4ae-144">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="9f4ae-145">修正</span><span class="sxs-lookup"><span data-stu-id="9f4ae-145">Remediation</span></span> | <span data-ttu-id="9f4ae-146">为运行计划的完整扫描以完成修正的时间配置本地设置替代</span><span class="sxs-lookup"><span data-stu-id="9f4ae-146">Configure local setting override for the time of day to run a scheduled full scan to complete remediation</span></span> | [<span data-ttu-id="9f4ae-147">配置扫描修正</span><span class="sxs-lookup"><span data-stu-id="9f4ae-147">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
<span data-ttu-id="9f4ae-148">扫描</span><span class="sxs-lookup"><span data-stu-id="9f4ae-148">Scan</span></span> | <span data-ttu-id="9f4ae-149">为 CPU 使用率的最大百分比配置本地设置覆盖</span><span class="sxs-lookup"><span data-stu-id="9f4ae-149">Configure local setting override for maximum percentage of CPU utilization</span></span> | [<span data-ttu-id="9f4ae-150">配置并运行扫描</span><span class="sxs-lookup"><span data-stu-id="9f4ae-150">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md)
<span data-ttu-id="9f4ae-151">扫描</span><span class="sxs-lookup"><span data-stu-id="9f4ae-151">Scan</span></span> | <span data-ttu-id="9f4ae-152">为计划扫描日配置本地设置覆盖</span><span class="sxs-lookup"><span data-stu-id="9f4ae-152">Configure local setting override for schedule scan day</span></span> | [<span data-ttu-id="9f4ae-153">配置计划扫描</span><span class="sxs-lookup"><span data-stu-id="9f4ae-153">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="9f4ae-154">扫描</span><span class="sxs-lookup"><span data-stu-id="9f4ae-154">Scan</span></span> | <span data-ttu-id="9f4ae-155">为计划的快速扫描时间配置本地设置覆盖</span><span class="sxs-lookup"><span data-stu-id="9f4ae-155">Configure local setting override for scheduled quick scan time</span></span> | [<span data-ttu-id="9f4ae-156">配置计划扫描</span><span class="sxs-lookup"><span data-stu-id="9f4ae-156">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="9f4ae-157">扫描</span><span class="sxs-lookup"><span data-stu-id="9f4ae-157">Scan</span></span> | <span data-ttu-id="9f4ae-158">为计划扫描时间配置本地设置覆盖</span><span class="sxs-lookup"><span data-stu-id="9f4ae-158">Configure local setting override for scheduled scan time</span></span> | [<span data-ttu-id="9f4ae-159">配置计划扫描</span><span class="sxs-lookup"><span data-stu-id="9f4ae-159">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="9f4ae-160">扫描</span><span class="sxs-lookup"><span data-stu-id="9f4ae-160">Scan</span></span> | <span data-ttu-id="9f4ae-161">为要用于计划扫描的扫描类型配置本地设置覆盖</span><span class="sxs-lookup"><span data-stu-id="9f4ae-161">Configure local setting override for the scan type to use for a scheduled scan</span></span> | [<span data-ttu-id="9f4ae-162">配置计划扫描</span><span class="sxs-lookup"><span data-stu-id="9f4ae-162">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a><span data-ttu-id="9f4ae-163">配置本地和全局定义的威胁修正和排除列表的合并方式</span><span class="sxs-lookup"><span data-stu-id="9f4ae-163">Configure how locally and globally defined threat remediation and exclusions lists are merged</span></span>

<span data-ttu-id="9f4ae-164">还可以配置本地定义的列表与全局定义列表的组合或合并方式。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-164">You can also configure how locally defined lists are combined or merged with globally defined lists.</span></span> <span data-ttu-id="9f4ae-165">此设置适用于排除列表 [、](configure-exclusions-microsoft-defender-antivirus.md)指定的 [修正列表](configure-remediation-microsoft-defender-antivirus.md)和 [攻击面减少](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-165">This setting applies to [exclusion lists](configure-exclusions-microsoft-defender-antivirus.md), [specified remediation lists](configure-remediation-microsoft-defender-antivirus.md), and [attack surface reduction](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).</span></span>

<span data-ttu-id="9f4ae-166">默认情况下，在本地组策略和 Windows 安全应用中配置的列表将与网络上部署的适当组策略对象定义的列表合并。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-166">By default, lists that have been configured in local group policy and the Windows Security app are merged with lists that are defined by the appropriate Group Policy Object that you have deployed on your network.</span></span> <span data-ttu-id="9f4ae-167">存在冲突时，全局定义的列表优先。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-167">Where there are conflicts, the globally-defined list takes precedence.</span></span>

<span data-ttu-id="9f4ae-168">你可以禁用此设置，以确保仅使用全局定义的 (如来自任何已部署的 GPO 列表) 列表。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-168">You can disable this setting to ensure that only globally-defined lists (such as those from any deployed GPOs) are used.</span></span>

### <a name="use-group-policy-to-disable-local-list-merging"></a><span data-ttu-id="9f4ae-169">使用组策略禁用本地列表合并</span><span class="sxs-lookup"><span data-stu-id="9f4ae-169">Use Group Policy to disable local list merging</span></span>

1. <span data-ttu-id="9f4ae-170">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="9f4ae-170">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="9f4ae-171">在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-171">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="9f4ae-172">将树展开到 **Microsoft Defender 防病毒> Windows 组件**。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-172">Expand the tree to **Windows components > Microsoft Defender Antivirus**.</span></span>

4. <span data-ttu-id="9f4ae-173">双击配置 **列表的本地管理员合并行为** ，将选项设置为 **已禁用**。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-173">Double-click **Configure local administrator merge behavior for lists** and set the option to **Disabled**.</span></span> <span data-ttu-id="9f4ae-174">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-174">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="9f4ae-175">如果禁用本地列表合并，它将覆盖受控文件夹访问权限设置。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-175">If you disable local list merging, it will override controlled folder access settings.</span></span> <span data-ttu-id="9f4ae-176">它还会覆盖本地管理员设置的任何受保护的文件夹或允许的应用。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-176">It also overrides any protected folders or allowed apps set by the local administrator.</span></span> <span data-ttu-id="9f4ae-177">有关受控文件夹访问权限设置详细信息，请参阅在 Windows 安全中 [允许阻止的应用](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security)。</span><span class="sxs-lookup"><span data-stu-id="9f4ae-177">For more information about controlled folder access settings, see [Allow a blocked app in Windows Security](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9f4ae-178">相关主题</span><span class="sxs-lookup"><span data-stu-id="9f4ae-178">Related topics</span></span>

- [<span data-ttu-id="9f4ae-179">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="9f4ae-179">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="9f4ae-180">配置最终用户与 Microsoft Defender 防病毒的交互</span><span class="sxs-lookup"><span data-stu-id="9f4ae-180">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)