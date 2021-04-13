---
title: 启用和配置 Microsoft Defender 防病毒保护功能
description: 启用和配置 Microsoft Defender 防病毒实时保护功能，例如行为监视、启发和机器学习
keywords: 防病毒， 实时保护， rtp， 机器学习， 行为监视， 启发
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 12/16/2019
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 7fa4f90282bf87c1def1917037e090b213cad3db
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689911"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a><span data-ttu-id="e2c1e-104">在组策略中启用和配置 Microsoft Defender 防病毒始终启用保护</span><span class="sxs-lookup"><span data-stu-id="e2c1e-104">Enable and configure Microsoft Defender Antivirus always-on protection in Group Policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e2c1e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-105">**Applies to:**</span></span>

- [<span data-ttu-id="e2c1e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e2c1e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e2c1e-107">始终持续保护包括实时保护、行为监视和启发，以根据已知的可疑和恶意活动识别恶意软件。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-107">Always-on protection consists of real-time protection, behavior monitoring, and heuristics to identify malware based on known suspicious and malicious activities.</span></span>

<span data-ttu-id="e2c1e-108">这些活动包括事件，如进程对现有文件进行异常更改、修改或创建自动启动注册表项和启动位置 (也称为自动启动扩展点或 ASP) ，以及文件系统或文件结构的其他更改。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-108">These activities include events, such as processes making unusual changes to existing files, modifying or creating automatic startup registry keys and startup locations (also known as auto-start extensibility points, or ASEPs), and other changes to the file system or file structure.</span></span>

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a><span data-ttu-id="e2c1e-109">在组策略中启用和配置始终启用保护</span><span class="sxs-lookup"><span data-stu-id="e2c1e-109">Enable and configure always-on protection in Group Policy</span></span>

<span data-ttu-id="e2c1e-110">可以使用本地 **组策略编辑器** 启用和配置 Microsoft Defender 防病毒始终启用保护设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-110">You can use **Local Group Policy Editor** to enable and configure Microsoft Defender Antivirus always-on protection settings.</span></span>

<span data-ttu-id="e2c1e-111">启用和配置始终启用保护：</span><span class="sxs-lookup"><span data-stu-id="e2c1e-111">To enable and configure always-on protection:</span></span>

1. <span data-ttu-id="e2c1e-112">打开 **"本地组策略编辑器"。**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-112">Open **Local Group Policy Editor**.</span></span> <span data-ttu-id="e2c1e-113">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e2c1e-113">To do this:</span></span>  

    1. <span data-ttu-id="e2c1e-114">在 Windows 10 任务栏搜索框中，键入 **gpedit**。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-114">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
    
    1. <span data-ttu-id="e2c1e-115">在 **"最佳匹配"** 下 **，单击"编辑组策略**"以启动 **"本地组策略编辑器"。**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-115">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>
    
       ![GPEdit 任务栏搜索结果](images/gpedit-search.png)

2. <span data-ttu-id="e2c1e-117">在本地组策略 **编辑器** 的左侧窗格中，将树展开到计算机 **配置** 管理模板 Windows  >    >  **组件** Microsoft Defender  >  **防病毒**。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-117">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus**.</span></span> 

3. <span data-ttu-id="e2c1e-118">配置 Microsoft Defender 防病毒反恶意软件服务策略设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-118">Configure the Microsoft Defender Antivirus antimalware service policy settings.</span></span> <span data-ttu-id="e2c1e-119">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e2c1e-119">To do this:</span></span>  

    1. <span data-ttu-id="e2c1e-120">在右侧 **Microsoft Defender 防病毒** 详细信息窗格中，双击下表中指定的策略设置：</span><span class="sxs-lookup"><span data-stu-id="e2c1e-120">In the **Microsoft Defender Antivirus** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="e2c1e-121">设置</span><span class="sxs-lookup"><span data-stu-id="e2c1e-121">Setting</span></span> | <span data-ttu-id="e2c1e-122">说明</span><span class="sxs-lookup"><span data-stu-id="e2c1e-122">Description</span></span> | <span data-ttu-id="e2c1e-123">默认设置</span><span class="sxs-lookup"><span data-stu-id="e2c1e-123">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="e2c1e-124">允许反恶意软件服务以普通优先级启动</span><span class="sxs-lookup"><span data-stu-id="e2c1e-124">Allow antimalware service to startup with normal priority</span></span> | <span data-ttu-id="e2c1e-125">你可以降低 Microsoft Defender 防病毒引擎的优先级，在希望尽可能精简启动过程的轻型部署中，这可能很有用。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-125">You can lower the priority of the Microsoft Defender Antivirus engine, which may be useful in lightweight deployments where you want to have as lean a startup process as possible.</span></span> <span data-ttu-id="e2c1e-126">这可能会影响对终结点的保护。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-126">This may impact protection on the endpoint.</span></span> | <span data-ttu-id="e2c1e-127">已启用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-127">Enabled</span></span>
       | <span data-ttu-id="e2c1e-128">允许反恶意软件服务始终运行</span><span class="sxs-lookup"><span data-stu-id="e2c1e-128">Allow antimalware service to remain running always</span></span> | <span data-ttu-id="e2c1e-129">如果保护更新已禁用，你可以将 Microsoft Defender 防病毒设置为仍运行。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-129">If protection updates have been disabled, you can set Microsoft Defender Antivirus to still run.</span></span> <span data-ttu-id="e2c1e-130">这将降低终结点上的保护。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-130">This lowers the protection on the endpoint.</span></span> | <span data-ttu-id="e2c1e-131">已禁用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-131">Disabled</span></span> |
    
    1. <span data-ttu-id="e2c1e-132">配置相应设置，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-132">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="e2c1e-133">对表中的每个设置重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-133">Repeat the previous steps for each setting in the table.</span></span>

4. <span data-ttu-id="e2c1e-134">配置 Microsoft Defender 防病毒实时保护策略设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-134">Configure the Microsoft Defender Antivirus real-time protection policy settings.</span></span> <span data-ttu-id="e2c1e-135">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e2c1e-135">To do this:</span></span>

    1. <span data-ttu-id="e2c1e-136">在 **Microsoft Defender 防病毒详细信息** 窗格中，双击实时 **保护**。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-136">In the **Microsoft Defender Antivirus** details pane, double-click **Real-time Protection**.</span></span> <span data-ttu-id="e2c1e-137">或者，在 **左窗格中的 Microsoft Defender 防病毒** 树中，单击 **"实时保护"。**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-137">Or, from the **Microsoft Defender Antivirus** tree on left pane, click **Real-time Protection**.</span></span>
    
    1. <span data-ttu-id="e2c1e-138">在 **右侧"实时保护** "详细信息窗格中，双击下表中指定的策略设置：</span><span class="sxs-lookup"><span data-stu-id="e2c1e-138">In the **Real-time Protection** details pane on right, double-click the policy setting as specified in the following table:</span></span>  

       | <span data-ttu-id="e2c1e-139">设置</span><span class="sxs-lookup"><span data-stu-id="e2c1e-139">Setting</span></span> | <span data-ttu-id="e2c1e-140">说明</span><span class="sxs-lookup"><span data-stu-id="e2c1e-140">Description</span></span> | <span data-ttu-id="e2c1e-141">默认设置</span><span class="sxs-lookup"><span data-stu-id="e2c1e-141">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="e2c1e-142">打开行为监视</span><span class="sxs-lookup"><span data-stu-id="e2c1e-142">Turn on behavior monitoring</span></span> | <span data-ttu-id="e2c1e-143">AV 引擎将监视终结点上的文件进程、文件和注册表更改以及其他事件，以发现可疑和已知的恶意活动。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-143">The AV engine will monitor file processes, file and registry changes, and other events on your endpoints for suspicious and known malicious activity.</span></span> | <span data-ttu-id="e2c1e-144">已启用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-144">Enabled</span></span> |
       | <span data-ttu-id="e2c1e-145">扫描所有下载的文件和附件</span><span class="sxs-lookup"><span data-stu-id="e2c1e-145">Scan all downloaded files and attachments</span></span> | <span data-ttu-id="e2c1e-146">将自动扫描下载的文件和附件。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-146">Downloaded files and attachments are automatically scanned.</span></span> <span data-ttu-id="e2c1e-147">除了在下载之前和Windows Defender扫描文件的 SmartScreen 筛选器之外，此操作也执行。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-147">This operates in addition to the Windows Defender SmartScreen filter, which scans files before and during downloading.</span></span> | <span data-ttu-id="e2c1e-148">已启用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-148">Enabled</span></span> |
       | <span data-ttu-id="e2c1e-149">监视您的计算机上的文件和程序活动</span><span class="sxs-lookup"><span data-stu-id="e2c1e-149">Monitor file and program activity on your computer</span></span> | <span data-ttu-id="e2c1e-150">Microsoft Defender 防病毒引擎会记录任何文件更改 (文件写入，例如移动、复制或修改) 以及打开或运行的导致其他程序运行) 的常规程序活动 (程序。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-150">The Microsoft Defender Antivirus engine makes note of any file changes (file writes, such as moves, copies, or modifications) and general program activity (programs that are opened or running and that cause other programs to run).</span></span> | <span data-ttu-id="e2c1e-151">已启用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-151">Enabled</span></span> |
       | <span data-ttu-id="e2c1e-152">打开原始卷写入通知</span><span class="sxs-lookup"><span data-stu-id="e2c1e-152">Turn on raw volume write notifications</span></span> | <span data-ttu-id="e2c1e-153">行为监视将分析有关原始卷写入的信息。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-153">Information about raw volume writes will be analyzed by behavior monitoring.</span></span> | <span data-ttu-id="e2c1e-154">已启用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-154">Enabled</span></span> |
       | <span data-ttu-id="e2c1e-155">启用实时保护时打开进程扫描</span><span class="sxs-lookup"><span data-stu-id="e2c1e-155">Turn on process scanning whenever real-time protection is enabled</span></span> | <span data-ttu-id="e2c1e-156">你可以独立启用 Microsoft Defender 防病毒引擎来扫描正在运行的进程，以发现可疑的修改或行为。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-156">You can independently enable the Microsoft Defender Antivirus engine to scan running processes for suspicious modifications or behaviors.</span></span> <span data-ttu-id="e2c1e-157">如果你暂时禁用了实时保护，并且想要自动扫描在禁用时启动的进程，这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-157">This is useful if you have temporarily disabled real-time protection and want to automatically scan processes that started while it was disabled.</span></span> | <span data-ttu-id="e2c1e-158">已启用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-158">Enabled</span></span> |
       | <span data-ttu-id="e2c1e-159">定义要扫描的已下载文件和附件的最大大小</span><span class="sxs-lookup"><span data-stu-id="e2c1e-159">Define the maximum size of downloaded files and attachments to be scanned</span></span> | <span data-ttu-id="e2c1e-160">可以定义大小（以 KB 为单位）。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-160">You can define the size in kilobytes.</span></span> | <span data-ttu-id="e2c1e-161">已启用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-161">Enabled</span></span> |
       | <span data-ttu-id="e2c1e-162">配置本地设置替代以启用行为监视</span><span class="sxs-lookup"><span data-stu-id="e2c1e-162">Configure local setting override for turn on behavior monitoring</span></span> | <span data-ttu-id="e2c1e-163">为行为监视的配置配置本地替代。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-163">Configure a local override for the configuration of behavior monitoring.</span></span> <span data-ttu-id="e2c1e-164">此设置只能由组策略设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-164">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="e2c1e-165">如果启用此设置，本地首选项设置将优先于组策略。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-165">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="e2c1e-166">如果禁用或不配置此设置，则组策略将优先于本地首选项设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-166">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="e2c1e-167">已启用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-167">Enabled</span></span> |
       | <span data-ttu-id="e2c1e-168">配置用于扫描所有下载的文件和附件的本地设置替代</span><span class="sxs-lookup"><span data-stu-id="e2c1e-168">Configure local setting override for scanning all downloaded files and attachments</span></span> | <span data-ttu-id="e2c1e-169">配置用于配置扫描的所有已下载文件和附件的本地覆盖。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-169">Configure a local override for the configuration of scanning for all downloaded files and attachments.</span></span> <span data-ttu-id="e2c1e-170">此设置只能由组策略设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-170">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="e2c1e-171">如果启用此设置，本地首选项设置将优先于组策略。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-171">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="e2c1e-172">如果禁用或不配置此设置，则组策略将优先于本地首选项设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-172">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="e2c1e-173">已启用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-173">Enabled</span></span> |
       | <span data-ttu-id="e2c1e-174">配置本地设置覆盖以监视您的计算机上的文件和程序活动</span><span class="sxs-lookup"><span data-stu-id="e2c1e-174">Configure local setting override for monitoring file and program activity on your computer</span></span> | <span data-ttu-id="e2c1e-175">为计算机上文件和程序活动的监视配置配置本地覆盖。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-175">Configure a local override for the configuration of monitoring for file and program activity on your computer.</span></span> <span data-ttu-id="e2c1e-176">此设置只能由组策略设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-176">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="e2c1e-177">如果启用此设置，本地首选项设置将优先于组策略。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-177">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="e2c1e-178">如果禁用或不配置此设置，则组策略将优先于本地首选项设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-178">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="e2c1e-179">已启用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-179">Enabled</span></span> |
       | <span data-ttu-id="e2c1e-180">配置本地设置覆盖以启用实时保护</span><span class="sxs-lookup"><span data-stu-id="e2c1e-180">Configure local setting override to turn on real-time protection</span></span> | <span data-ttu-id="e2c1e-181">为配置配置配置配置本地覆盖以启用实时保护。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-181">Configure a local override for the configuration to turn on real-time protection.</span></span> <span data-ttu-id="e2c1e-182">此设置只能由组策略设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-182">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="e2c1e-183">如果启用此设置，本地首选项设置将优先于组策略。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-183">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="e2c1e-184">如果禁用或不配置此设置，则组策略将优先于本地首选项设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-184">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="e2c1e-185">已启用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-185">Enabled</span></span> |
       | <span data-ttu-id="e2c1e-186">配置本地设置覆盖以监视传入和传出文件活动</span><span class="sxs-lookup"><span data-stu-id="e2c1e-186">Configure local setting override for monitoring for incoming and outgoing file activity</span></span> | <span data-ttu-id="e2c1e-187">为传入和传出文件活动的监视配置配置本地覆盖。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-187">Configure a local override for the configuration of monitoring for incoming and outgoing file activity.</span></span> <span data-ttu-id="e2c1e-188">此设置只能由组策略设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-188">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="e2c1e-189">如果启用此设置，本地首选项设置将优先于组策略。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-189">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="e2c1e-190">如果禁用或不配置此设置，则组策略将优先于本地首选项设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-190">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span> | <span data-ttu-id="e2c1e-191">已启用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-191">Enabled</span></span> |
       | <span data-ttu-id="e2c1e-192">配置对传入和传出文件和程序活动的监视</span><span class="sxs-lookup"><span data-stu-id="e2c1e-192">Configure monitoring for incoming and outgoing file and program activity</span></span> | <span data-ttu-id="e2c1e-193">指定监控应在传入、传出和/或两个方向上执行。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-193">Specify whether monitoring should occur on incoming, outgoing, both, or neither direction.</span></span> <span data-ttu-id="e2c1e-194">这适用于已定义特定服务器或服务器角色的 Windows Server 安装，这些服务器或角色仅看到一个方向中的大量文件更改，并且希望提高网络性能。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-194">This is relevant for Windows Server installations where you have defined specific servers or Server Roles that see large amounts of file changes in only one direction and you want to improve network performance.</span></span> <span data-ttu-id="e2c1e-195">网络上 (和) 的完全更新的终结点将几乎看不到性能影响，无论文件更改的数量或方向如何。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-195">Fully updated endpoints (and servers) on a network will see little performance impact irrespective of the number or direction of file changes.</span></span> | <span data-ttu-id="e2c1e-196">启用 (两个方向) </span><span class="sxs-lookup"><span data-stu-id="e2c1e-196">Enabled (both directions)</span></span> |

    1. <span data-ttu-id="e2c1e-197">配置相应设置，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-197">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="e2c1e-198">对表中的每个设置重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-198">Repeat the previous steps for each setting in the table.</span></span>

5. <span data-ttu-id="e2c1e-199">配置 Microsoft Defender 防病毒扫描策略设置。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-199">Configure the Microsoft Defender Antivirus scanning policy setting.</span></span> <span data-ttu-id="e2c1e-200">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e2c1e-200">To do this:</span></span>  

    1. <span data-ttu-id="e2c1e-201">在左 **窗格中的 Microsoft Defender 防病毒** 树中，**单击扫描。**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-201">From the **Microsoft Defender Antivirus** tree on left pane, click **Scan**.</span></span>
    
       ![Microsoft Defender 防病毒扫描选项](images/gpedit-windows-defender-antivirus-scan.png)

    1. <span data-ttu-id="e2c1e-203">在右侧 **"** 扫描详细信息"窗格中，双击下表中指定的策略设置：</span><span class="sxs-lookup"><span data-stu-id="e2c1e-203">In the **Scan** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="e2c1e-204">设置</span><span class="sxs-lookup"><span data-stu-id="e2c1e-204">Setting</span></span> | <span data-ttu-id="e2c1e-205">说明</span><span class="sxs-lookup"><span data-stu-id="e2c1e-205">Description</span></span> | <span data-ttu-id="e2c1e-206">默认设置</span><span class="sxs-lookup"><span data-stu-id="e2c1e-206">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|    
       | <span data-ttu-id="e2c1e-207">打开启发式</span><span class="sxs-lookup"><span data-stu-id="e2c1e-207">Turn on heuristics</span></span> | <span data-ttu-id="e2c1e-208">启发式保护将在要求 Microsoft Defender 防病毒引擎检测活动之前立即禁用或阻止可疑活动。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-208">Heuristic protection will disable or block suspicious activity immediately before the Microsoft Defender Antivirus engine is asked to detect the activity.</span></span> | <span data-ttu-id="e2c1e-209">已启用</span><span class="sxs-lookup"><span data-stu-id="e2c1e-209">Enabled</span></span> |

    1. <span data-ttu-id="e2c1e-210">配置相应设置，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-210">Configure the setting as appropriate, and click **OK**.</span></span>
    
6. <span data-ttu-id="e2c1e-211">关闭 **本地组策略编辑器**。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-211">Close **Local Group Policy Editor**.</span></span>


## <a name="disable-real-time-protection-in-group-policy"></a><span data-ttu-id="e2c1e-212">在组策略中禁用实时保护</span><span class="sxs-lookup"><span data-stu-id="e2c1e-212">Disable real-time protection in Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="e2c1e-213">禁用实时保护会大大降低终结点上的保护，不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-213">Disabling real-time protection drastically reduces the protection on your endpoints and is not recommended.</span></span>

<span data-ttu-id="e2c1e-214">默认启用主要实时保护功能，但可以使用本地组策略编辑器 **禁用该功能**。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-214">The main real-time protection capability is enabled by default, but you can disable it by using **Local Group Policy Editor**.</span></span>

<span data-ttu-id="e2c1e-215">在组策略中禁用实时保护：</span><span class="sxs-lookup"><span data-stu-id="e2c1e-215">To disable real-time protection in Group policy:</span></span>

1. <span data-ttu-id="e2c1e-216">打开 **"本地组策略编辑器"。**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-216">Open **Local Group Policy Editor**.</span></span>

   1. <span data-ttu-id="e2c1e-217">在 Windows 10 任务栏搜索框中，键入 **gpedit**。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-217">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
   
   1. <span data-ttu-id="e2c1e-218">在 **"最佳匹配"** 下 **，单击"编辑组策略**"以启动 **"本地组策略编辑器"。**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-218">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>

2.  <span data-ttu-id="e2c1e-219">在本地组策略编辑器的左侧窗格中，将树展开到计算机配置管理模板 Windows 组件 Microsoft Defender 防病毒  >    >    >    >  **实时保护**。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-219">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Real-time Protection**.</span></span>

3. <span data-ttu-id="e2c1e-220">在 **右侧"实时保护"** 详细信息窗格中，双击"**关闭实时保护"。**</span><span class="sxs-lookup"><span data-stu-id="e2c1e-220">In the **Real-time Protection** details pane on right, double-click **Turn off real-time protection**.</span></span>

   ![关闭实时保护](images/gpedit-turn-off-real-time-protection.png)

4. <span data-ttu-id="e2c1e-222">在 **关闭实时保护设置** 窗口中，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-222">In the **Turn off real-time protection** setting window, set the option to **Enabled**.</span></span>

   ![关闭启用实时保护](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. <span data-ttu-id="e2c1e-224">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-224">Click **OK**.</span></span>

6. <span data-ttu-id="e2c1e-225">关闭 **本地组策略编辑器**。</span><span class="sxs-lookup"><span data-stu-id="e2c1e-225">Close **Local Group Policy Editor**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e2c1e-226">相关文章</span><span class="sxs-lookup"><span data-stu-id="e2c1e-226">Related articles</span></span>

- [<span data-ttu-id="e2c1e-227">配置行为、启发式和实时保护</span><span class="sxs-lookup"><span data-stu-id="e2c1e-227">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e2c1e-228">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="e2c1e-228">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)