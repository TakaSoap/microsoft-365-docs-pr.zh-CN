---
title: 在特定事件后应用 Microsoft Defender 防病毒更新
description: 管理 Microsoft Defender 防病毒在启动或接收云提供的检测报告后应用安全智能更新的方式。
keywords: 更新， 保护， 强制更新， 事件， 启动， 检查最新， 通知
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 78a04105fce0a3a1f9f7ea3f9ee993dd53750f3f
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764551"
---
# <a name="manage-event-based-forced-updates"></a><span data-ttu-id="0b489-104">管理基于事件的强制更新</span><span class="sxs-lookup"><span data-stu-id="0b489-104">Manage event-based forced updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0b489-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0b489-105">**Applies to:**</span></span>

- [<span data-ttu-id="0b489-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0b489-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0b489-107">Microsoft Defender 防病毒允许你确定更新是应 (还是不应) 某些事件之后发生，例如启动时还是从云提供的保护服务接收特定报告之后。</span><span class="sxs-lookup"><span data-stu-id="0b489-107">Microsoft Defender Antivirus allows you to determine if updates should (or should not) occur after certain events, such as at startup or after receiving specific reports from the cloud-delivered protection service.</span></span>

## <a name="check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="0b489-108">在运行扫描之前检查保护更新</span><span class="sxs-lookup"><span data-stu-id="0b489-108">Check for protection updates before running a scan</span></span>

<span data-ttu-id="0b489-109">可以使用 Microsoft Endpoint Configuration Manager、组策略、PowerShell cmdlet 和 WMI 强制 Microsoft Defender 防病毒在运行计划扫描之前检查和下载保护更新。</span><span class="sxs-lookup"><span data-stu-id="0b489-109">You can use Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, and WMI to force Microsoft Defender Antivirus to check and download protection updates before running a scheduled scan.</span></span>

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="0b489-110">运行扫描之前，使用 Configuration Manager 检查保护更新</span><span class="sxs-lookup"><span data-stu-id="0b489-110">Use Configuration Manager to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="0b489-111">在 Microsoft Endpoint Manager 控制台上，打开要更改的反恶意软件策略 (单击左侧导航窗格中的"资产和合规性"，然后将树展开到"终结点保护反恶意软件策略概述")  >    >  </span><span class="sxs-lookup"><span data-stu-id="0b489-111">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2. <span data-ttu-id="0b489-112">转到计划 **扫描** 部分，将运行扫描之前检查最新的安全 **智能更新** 设置为 **是**。</span><span class="sxs-lookup"><span data-stu-id="0b489-112">Go to the **Scheduled scans** section and set **Check for the latest security intelligence updates before running a scan** to **Yes**.</span></span>

3. <span data-ttu-id="0b489-113">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0b489-113">Click **OK**.</span></span>

4. <span data-ttu-id="0b489-114">[像往常一样部署更新的策略](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。</span><span class="sxs-lookup"><span data-stu-id="0b489-114">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="0b489-115">运行扫描之前，使用组策略检查保护更新</span><span class="sxs-lookup"><span data-stu-id="0b489-115">Use Group Policy to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="0b489-116">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="0b489-116">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="0b489-117">使用组 **策略管理编辑器转到** 计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="0b489-117">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="0b489-118">单击 **"策略\*\*\*\*"，然后单击"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="0b489-118">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="0b489-119">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **扫描**。</span><span class="sxs-lookup"><span data-stu-id="0b489-119">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="0b489-120">在运行计划 **扫描之前** ，双击检查最新的病毒和间谍软件定义，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="0b489-120">Double-click **Check for the latest virus and spyware definitions before running a scheduled scan** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="0b489-121">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0b489-121">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="0b489-122">运行扫描之前，使用 PowerShell cmdlet 检查保护更新</span><span class="sxs-lookup"><span data-stu-id="0b489-122">Use PowerShell cmdlets to check for protection updates before running a scan</span></span>

<span data-ttu-id="0b489-123">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0b489-123">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="0b489-124">有关详细信息，请参阅使用[PowerShell cmdlet 配置](use-powershell-cmdlets-microsoft-defender-antivirus.md)和运行 Microsoft Defender 防病毒和[Defender cmdlet。](/powershell/module/defender/index)</span><span class="sxs-lookup"><span data-stu-id="0b489-124">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="0b489-125">使用 Windows Management Instruction (WMI) 在运行扫描之前检查保护更新</span><span class="sxs-lookup"><span data-stu-id="0b489-125">Use Windows Management Instruction (WMI) to check for protection updates before running a scan</span></span>

<span data-ttu-id="0b489-126">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="0b489-126">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="0b489-127">有关详细信息，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="0b489-127">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="check-for-protection-updates-on-startup"></a><span data-ttu-id="0b489-128">启动时检查保护更新</span><span class="sxs-lookup"><span data-stu-id="0b489-128">Check for protection updates on startup</span></span>

<span data-ttu-id="0b489-129">可以使用组策略强制 Microsoft Defender 防病毒在计算机启动时检查和下载保护更新。</span><span class="sxs-lookup"><span data-stu-id="0b489-129">You can use Group Policy to force Microsoft Defender Antivirus to check and download protection updates when the machine is started.</span></span>

1. <span data-ttu-id="0b489-130">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="0b489-130">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="0b489-131">使用组 **策略管理编辑器转到** 计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="0b489-131">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="0b489-132">单击 **"策略\*\*\*\*"，然后单击"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="0b489-132">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="0b489-133">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **安全智能更新**。</span><span class="sxs-lookup"><span data-stu-id="0b489-133">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="0b489-134">双击启动时 **检查最新的病毒和** 间谍软件定义，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="0b489-134">Double-click **Check for the latest virus and spyware definitions on startup** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="0b489-135">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0b489-135">Click **OK**.</span></span>

<span data-ttu-id="0b489-136">您还可以使用组策略、PowerShell 或 WMI 将 Microsoft Defender 防病毒配置为在启动时检查更新，即使更新未运行。</span><span class="sxs-lookup"><span data-stu-id="0b489-136">You can also use Group Policy, PowerShell, or WMI to configure Microsoft Defender Antivirus to check for updates at startup even when it is not running.</span></span>

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="0b489-137">当 Microsoft Defender 防病毒不存在时，使用组策略下载更新</span><span class="sxs-lookup"><span data-stu-id="0b489-137">Use Group Policy to download updates when Microsoft Defender Antivirus is not present</span></span>

1. <span data-ttu-id="0b489-138">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="0b489-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="0b489-139">使用组 **策略管理编辑器，** 转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="0b489-139">Using the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="0b489-140">单击 **"策略\*\*\*\*"，然后单击"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="0b489-140">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="0b489-141">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **安全智能更新**。</span><span class="sxs-lookup"><span data-stu-id="0b489-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="0b489-142">双击启动时 **启动安全智能更新** ，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="0b489-142">Double-click **Initiate security intelligence update on startup** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="0b489-143">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0b489-143">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="0b489-144">当 Microsoft Defender 防病毒不存在时，使用 PowerShell cmdlet 下载更新</span><span class="sxs-lookup"><span data-stu-id="0b489-144">Use PowerShell cmdlets to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="0b489-145">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0b489-145">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="0b489-146">有关详细信息，请参阅使用 [PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 管理 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/index) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。</span><span class="sxs-lookup"><span data-stu-id="0b489-146">For more information, see [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="0b489-147">使用 Windows Management Instruction (WMI) 在 Microsoft Defender 防病毒不存在时下载更新</span><span class="sxs-lookup"><span data-stu-id="0b489-147">Use Windows Management Instruction (WMI) to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="0b489-148">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="0b489-148">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="0b489-149">有关详细信息，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="0b489-149">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a><span data-ttu-id="0b489-150">允许对基于云保护的保护进行临时更改</span><span class="sxs-lookup"><span data-stu-id="0b489-150">Allow ad hoc changes to protection based on cloud-delivered protection</span></span>

<span data-ttu-id="0b489-151">Microsoft Defender AV 可以基于云保护更改其保护。</span><span class="sxs-lookup"><span data-stu-id="0b489-151">Microsoft Defender AV can make changes to its protection based on cloud-delivered protection.</span></span> <span data-ttu-id="0b489-152">此类更改可能会发生在正常或计划的保护更新之外。</span><span class="sxs-lookup"><span data-stu-id="0b489-152">Such changes can occur outside of normal or scheduled protection updates.</span></span>

<span data-ttu-id="0b489-153">如果你已启用云保护，Microsoft Defender AV 会将其可疑的文件发送到Windows Defender云。</span><span class="sxs-lookup"><span data-stu-id="0b489-153">If you have enabled cloud-delivered protection, Microsoft Defender AV will send files it is suspicious about to the Windows Defender cloud.</span></span> <span data-ttu-id="0b489-154">如果云服务报告该文件是恶意文件，并且最近一次保护更新中检测到该文件，可以使用组策略配置 Microsoft Defender AV 以自动接收该保护更新。</span><span class="sxs-lookup"><span data-stu-id="0b489-154">If the cloud service reports that the file is malicious, and the file is detected in a recent protection update, you can use Group Policy to configure Microsoft Defender AV to automatically receive that protection update.</span></span> <span data-ttu-id="0b489-155">也可以应用其他重要的保护更新。</span><span class="sxs-lookup"><span data-stu-id="0b489-155">Other important protection updates can also be applied.</span></span>

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a><span data-ttu-id="0b489-156">使用组策略根据云提供的保护自动下载最近更新</span><span class="sxs-lookup"><span data-stu-id="0b489-156">Use Group Policy to automatically download recent updates based on cloud-delivered protection</span></span>

1. <span data-ttu-id="0b489-157">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="0b489-157">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="0b489-158">使用组 **策略管理编辑器转到** 计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="0b489-158">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="0b489-159">单击 **"策略\*\*\*\*"，然后单击"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="0b489-159">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="0b489-160">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **安全智能更新**。</span><span class="sxs-lookup"><span data-stu-id="0b489-160">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="0b489-161">双击允许基于 Microsoft **MAPS** 报告进行实时安全智能更新，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="0b489-161">Double-click **Allow real-time security intelligence updates based on reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="0b489-162">单击" **确定**"。</span><span class="sxs-lookup"><span data-stu-id="0b489-162">Then click **OK**.</span></span>

6. <span data-ttu-id="0b489-163">**允许通知禁用 Microsoft MAPS 的基于** 定义的报告，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="0b489-163">**Allow notifications to disable definitions-based reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="0b489-164">单击" **确定**"。</span><span class="sxs-lookup"><span data-stu-id="0b489-164">Then click **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0b489-165">**允许通知以禁用基于定义的报告** 使 Microsoft MAPS 可以禁用已知导致误报报告的定义。</span><span class="sxs-lookup"><span data-stu-id="0b489-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span></span> <span data-ttu-id="0b489-166">必须配置计算机以加入 Microsoft MAPS，此函数正常运行。</span><span class="sxs-lookup"><span data-stu-id="0b489-166">You must configure your computer to join Microsoft MAPS for this function to work.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b489-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b489-167">See also</span></span>

- [<span data-ttu-id="0b489-168">部署 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="0b489-168">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0b489-169">管理 Microsoft Defender 防病毒更新和应用基线</span><span class="sxs-lookup"><span data-stu-id="0b489-169">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0b489-170">管理何时应下载和应用保护更新</span><span class="sxs-lookup"><span data-stu-id="0b489-170">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0b489-171">管理过期终结点的更新</span><span class="sxs-lookup"><span data-stu-id="0b489-171">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0b489-172">管理移动设备和虚拟机 （VM） 的更新</span><span class="sxs-lookup"><span data-stu-id="0b489-172">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0b489-173">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="0b489-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)