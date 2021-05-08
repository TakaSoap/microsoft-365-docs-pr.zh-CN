---
title: 启用和配置Microsoft Defender 防病毒保护功能
description: 启用和Microsoft Defender 防病毒实时保护功能，如行为监视、启发和机器学习
keywords: 防病毒， 实时保护， rtp， 机器学习， 行为监视， 启发
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 12/16/2019
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 1e39e42b79a2a767473c4473434da249a0d07228
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275128"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a><span data-ttu-id="72f4d-104">在组策略中启用和配置 Microsoft Defender 防病毒软件始终启用保护</span><span class="sxs-lookup"><span data-stu-id="72f4d-104">Enable and configure Microsoft Defender Antivirus always-on protection in Group Policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="72f4d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="72f4d-105">**Applies to:**</span></span>

- [<span data-ttu-id="72f4d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="72f4d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="72f4d-107">始终持续保护包括实时保护、行为监视和启发，以根据已知的可疑和恶意活动识别恶意软件。</span><span class="sxs-lookup"><span data-stu-id="72f4d-107">Always-on protection consists of real-time protection, behavior monitoring, and heuristics to identify malware based on known suspicious and malicious activities.</span></span>

<span data-ttu-id="72f4d-108">这些活动包括事件，如进程对现有文件进行异常更改、修改或创建自动启动注册表项和启动位置 (也称为自动启动扩展点或 ASP) ，以及文件系统或文件结构的其他更改。</span><span class="sxs-lookup"><span data-stu-id="72f4d-108">These activities include events, such as processes making unusual changes to existing files, modifying or creating automatic startup registry keys and startup locations (also known as auto-start extensibility points, or ASEPs), and other changes to the file system or file structure.</span></span>

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a><span data-ttu-id="72f4d-109">在组策略中启用和配置始终启用保护</span><span class="sxs-lookup"><span data-stu-id="72f4d-109">Enable and configure always-on protection in Group Policy</span></span>

<span data-ttu-id="72f4d-110">可以使用本地 **组策略编辑器** 启用和配置Microsoft Defender 防病毒始终启用的保护设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-110">You can use **Local Group Policy Editor** to enable and configure Microsoft Defender Antivirus always-on protection settings.</span></span>

<span data-ttu-id="72f4d-111">启用和配置始终启用保护：</span><span class="sxs-lookup"><span data-stu-id="72f4d-111">To enable and configure always-on protection:</span></span>

1. <span data-ttu-id="72f4d-112">打开 **"本地组策略编辑器"。**</span><span class="sxs-lookup"><span data-stu-id="72f4d-112">Open **Local Group Policy Editor**.</span></span> <span data-ttu-id="72f4d-113">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="72f4d-113">To do this:</span></span>  

    1. <span data-ttu-id="72f4d-114">在任务栏Windows 10框中，键入 **gpedit**。</span><span class="sxs-lookup"><span data-stu-id="72f4d-114">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
    
    1. <span data-ttu-id="72f4d-115">在 **"最佳匹配"** 下 **，单击"编辑组策略**"以启动 **"本地组策略编辑器"。**</span><span class="sxs-lookup"><span data-stu-id="72f4d-115">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>
    
       ![GPEdit 任务栏搜索结果](images/gpedit-search.png)

2. <span data-ttu-id="72f4d-117">在本地组策略 **编辑器** 的左窗格中，将树展开到计算机配置管理  >    >  **模板 Windows 组件**  >  **Microsoft Defender 防病毒**。</span><span class="sxs-lookup"><span data-stu-id="72f4d-117">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus**.</span></span> 

3. <span data-ttu-id="72f4d-118">配置Microsoft Defender 防病毒反恶意软件服务策略设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-118">Configure the Microsoft Defender Antivirus antimalware service policy settings.</span></span> <span data-ttu-id="72f4d-119">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="72f4d-119">To do this:</span></span>  

    1. <span data-ttu-id="72f4d-120">在Microsoft Defender 防病毒 **详细信息**"窗格中，双击下表中指定的策略设置：</span><span class="sxs-lookup"><span data-stu-id="72f4d-120">In the **Microsoft Defender Antivirus** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="72f4d-121">设置</span><span class="sxs-lookup"><span data-stu-id="72f4d-121">Setting</span></span> | <span data-ttu-id="72f4d-122">说明</span><span class="sxs-lookup"><span data-stu-id="72f4d-122">Description</span></span> | <span data-ttu-id="72f4d-123">默认设置</span><span class="sxs-lookup"><span data-stu-id="72f4d-123">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="72f4d-124">允许反恶意软件服务以普通优先级启动</span><span class="sxs-lookup"><span data-stu-id="72f4d-124">Allow antimalware service to startup with normal priority</span></span> | <span data-ttu-id="72f4d-125">你可以降低 Microsoft Defender 防病毒 引擎的优先级，在希望尽可能精简启动过程的轻型部署中，这可能很有用。</span><span class="sxs-lookup"><span data-stu-id="72f4d-125">You can lower the priority of the Microsoft Defender Antivirus engine, which may be useful in lightweight deployments where you want to have as lean a startup process as possible.</span></span> <span data-ttu-id="72f4d-126">这可能会影响对终结点的保护。</span><span class="sxs-lookup"><span data-stu-id="72f4d-126">This may impact protection on the endpoint.</span></span> | <span data-ttu-id="72f4d-127">已启用</span><span class="sxs-lookup"><span data-stu-id="72f4d-127">Enabled</span></span>
       | <span data-ttu-id="72f4d-128">允许反恶意软件服务始终运行</span><span class="sxs-lookup"><span data-stu-id="72f4d-128">Allow antimalware service to remain running always</span></span> | <span data-ttu-id="72f4d-129">如果已禁用保护更新，你可以将Microsoft Defender 防病毒仍运行。</span><span class="sxs-lookup"><span data-stu-id="72f4d-129">If protection updates have been disabled, you can set Microsoft Defender Antivirus to still run.</span></span> <span data-ttu-id="72f4d-130">这将降低终结点上的保护。</span><span class="sxs-lookup"><span data-stu-id="72f4d-130">This lowers the protection on the endpoint.</span></span> | <span data-ttu-id="72f4d-131">禁用的</span><span class="sxs-lookup"><span data-stu-id="72f4d-131">Disabled</span></span> |
    
    1. <span data-ttu-id="72f4d-132">配置相应设置，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="72f4d-132">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="72f4d-133">对表中的每个设置重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="72f4d-133">Repeat the previous steps for each setting in the table.</span></span>

4. <span data-ttu-id="72f4d-134">配置Microsoft Defender 防病毒实时保护策略设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-134">Configure the Microsoft Defender Antivirus real-time protection policy settings.</span></span> <span data-ttu-id="72f4d-135">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="72f4d-135">To do this:</span></span>

    1. <span data-ttu-id="72f4d-136">在 **"Microsoft Defender 防病毒** 详细信息"窗格中，双击"**实时保护"。**</span><span class="sxs-lookup"><span data-stu-id="72f4d-136">In the **Microsoft Defender Antivirus** details pane, double-click **Real-time Protection**.</span></span> <span data-ttu-id="72f4d-137">或者，**在左Microsoft Defender 防病毒** 树中，单击"**实时保护"。**</span><span class="sxs-lookup"><span data-stu-id="72f4d-137">Or, from the **Microsoft Defender Antivirus** tree on left pane, click **Real-time Protection**.</span></span>
    
    1. <span data-ttu-id="72f4d-138">在 **右侧"实时保护** "详细信息窗格中，双击下表中指定的策略设置：</span><span class="sxs-lookup"><span data-stu-id="72f4d-138">In the **Real-time Protection** details pane on right, double-click the policy setting as specified in the following table:</span></span>  

       | <span data-ttu-id="72f4d-139">设置</span><span class="sxs-lookup"><span data-stu-id="72f4d-139">Setting</span></span> | <span data-ttu-id="72f4d-140">说明</span><span class="sxs-lookup"><span data-stu-id="72f4d-140">Description</span></span> | <span data-ttu-id="72f4d-141">默认设置</span><span class="sxs-lookup"><span data-stu-id="72f4d-141">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="72f4d-142">打开行为监视</span><span class="sxs-lookup"><span data-stu-id="72f4d-142">Turn on behavior monitoring</span></span> | <span data-ttu-id="72f4d-143">AV 引擎将监视终结点上的文件进程、文件和注册表更改以及其他事件，以发现可疑和已知的恶意活动。</span><span class="sxs-lookup"><span data-stu-id="72f4d-143">The AV engine will monitor file processes, file and registry changes, and other events on your endpoints for suspicious and known malicious activity.</span></span> | <span data-ttu-id="72f4d-144">已启用</span><span class="sxs-lookup"><span data-stu-id="72f4d-144">Enabled</span></span> |
       | <span data-ttu-id="72f4d-145">扫描所有下载的文件和附件</span><span class="sxs-lookup"><span data-stu-id="72f4d-145">Scan all downloaded files and attachments</span></span> | <span data-ttu-id="72f4d-146">将自动扫描下载的文件和附件。</span><span class="sxs-lookup"><span data-stu-id="72f4d-146">Downloaded files and attachments are automatically scanned.</span></span> <span data-ttu-id="72f4d-147">除了 SmartScreen 筛选器之外，此操作Windows Defender SmartScreen 筛选器，该筛选器在下载之前和下载过程中扫描文件。</span><span class="sxs-lookup"><span data-stu-id="72f4d-147">This operates in addition to the Windows Defender SmartScreen filter, which scans files before and during downloading.</span></span> | <span data-ttu-id="72f4d-148">已启用</span><span class="sxs-lookup"><span data-stu-id="72f4d-148">Enabled</span></span> |
       | <span data-ttu-id="72f4d-149">监视您的计算机上的文件和程序活动</span><span class="sxs-lookup"><span data-stu-id="72f4d-149">Monitor file and program activity on your computer</span></span> | <span data-ttu-id="72f4d-150">Microsoft Defender 防病毒 引擎会记录 (文件写入的任何文件更改，例如移动、复制或修改) 以及打开或运行的导致其他程序运行) 的常规程序活动 (程序。</span><span class="sxs-lookup"><span data-stu-id="72f4d-150">The Microsoft Defender Antivirus engine makes note of any file changes (file writes, such as moves, copies, or modifications) and general program activity (programs that are opened or running and that cause other programs to run).</span></span> | <span data-ttu-id="72f4d-151">已启用</span><span class="sxs-lookup"><span data-stu-id="72f4d-151">Enabled</span></span> |
       | <span data-ttu-id="72f4d-152">打开原始卷写入通知</span><span class="sxs-lookup"><span data-stu-id="72f4d-152">Turn on raw volume write notifications</span></span> | <span data-ttu-id="72f4d-153">行为监视将分析有关原始卷写入的信息。</span><span class="sxs-lookup"><span data-stu-id="72f4d-153">Information about raw volume writes will be analyzed by behavior monitoring.</span></span> | <span data-ttu-id="72f4d-154">已启用</span><span class="sxs-lookup"><span data-stu-id="72f4d-154">Enabled</span></span> |
       | <span data-ttu-id="72f4d-155">启用实时保护时打开进程扫描</span><span class="sxs-lookup"><span data-stu-id="72f4d-155">Turn on process scanning whenever real-time protection is enabled</span></span> | <span data-ttu-id="72f4d-156">你可以独立启用Microsoft Defender 防病毒引擎扫描正在运行的进程，以发现可疑的修改或行为。</span><span class="sxs-lookup"><span data-stu-id="72f4d-156">You can independently enable the Microsoft Defender Antivirus engine to scan running processes for suspicious modifications or behaviors.</span></span> <span data-ttu-id="72f4d-157">如果你暂时禁用了实时保护，并且想要自动扫描在禁用时启动的进程，这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="72f4d-157">This is useful if you have temporarily disabled real-time protection and want to automatically scan processes that started while it was disabled.</span></span> | <span data-ttu-id="72f4d-158">已启用</span><span class="sxs-lookup"><span data-stu-id="72f4d-158">Enabled</span></span> |
       | <span data-ttu-id="72f4d-159">定义要扫描的已下载文件和附件的最大大小</span><span class="sxs-lookup"><span data-stu-id="72f4d-159">Define the maximum size of downloaded files and attachments to be scanned</span></span> | <span data-ttu-id="72f4d-160">可以定义大小（以 KB 为单位）。</span><span class="sxs-lookup"><span data-stu-id="72f4d-160">You can define the size in kilobytes.</span></span> | <span data-ttu-id="72f4d-161">已启用</span><span class="sxs-lookup"><span data-stu-id="72f4d-161">Enabled</span></span> |
       | <span data-ttu-id="72f4d-162">配置本地设置替代以启用行为监视</span><span class="sxs-lookup"><span data-stu-id="72f4d-162">Configure local setting override for turn on behavior monitoring</span></span> | <span data-ttu-id="72f4d-163">为行为监视的配置配置本地替代。</span><span class="sxs-lookup"><span data-stu-id="72f4d-163">Configure a local override for the configuration of behavior monitoring.</span></span> <span data-ttu-id="72f4d-164">此设置只能由组策略设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-164">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="72f4d-165">如果启用此设置，本地首选项设置将优先于组策略。</span><span class="sxs-lookup"><span data-stu-id="72f4d-165">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="72f4d-166">如果禁用或不配置此设置，则组策略将优先于本地首选项设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-166">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="72f4d-167">已启用</span><span class="sxs-lookup"><span data-stu-id="72f4d-167">Enabled</span></span> |
       | <span data-ttu-id="72f4d-168">配置用于扫描所有下载的文件和附件的本地设置替代</span><span class="sxs-lookup"><span data-stu-id="72f4d-168">Configure local setting override for scanning all downloaded files and attachments</span></span> | <span data-ttu-id="72f4d-169">配置用于配置扫描的所有已下载文件和附件的本地覆盖。</span><span class="sxs-lookup"><span data-stu-id="72f4d-169">Configure a local override for the configuration of scanning for all downloaded files and attachments.</span></span> <span data-ttu-id="72f4d-170">此设置只能由组策略设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-170">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="72f4d-171">如果启用此设置，本地首选项设置将优先于组策略。</span><span class="sxs-lookup"><span data-stu-id="72f4d-171">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="72f4d-172">如果禁用或不配置此设置，则组策略将优先于本地首选项设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-172">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="72f4d-173">已启用</span><span class="sxs-lookup"><span data-stu-id="72f4d-173">Enabled</span></span> |
       | <span data-ttu-id="72f4d-174">配置本地设置覆盖以监视您的计算机上的文件和程序活动</span><span class="sxs-lookup"><span data-stu-id="72f4d-174">Configure local setting override for monitoring file and program activity on your computer</span></span> | <span data-ttu-id="72f4d-175">为计算机上文件和程序活动的监视配置配置本地覆盖。</span><span class="sxs-lookup"><span data-stu-id="72f4d-175">Configure a local override for the configuration of monitoring for file and program activity on your computer.</span></span> <span data-ttu-id="72f4d-176">此设置只能由组策略设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-176">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="72f4d-177">如果启用此设置，本地首选项设置将优先于组策略。</span><span class="sxs-lookup"><span data-stu-id="72f4d-177">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="72f4d-178">如果禁用或不配置此设置，则组策略将优先于本地首选项设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-178">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="72f4d-179">已启用</span><span class="sxs-lookup"><span data-stu-id="72f4d-179">Enabled</span></span> |
       | <span data-ttu-id="72f4d-180">配置本地设置覆盖以启用实时保护</span><span class="sxs-lookup"><span data-stu-id="72f4d-180">Configure local setting override to turn on real-time protection</span></span> | <span data-ttu-id="72f4d-181">为配置配置配置配置本地覆盖以启用实时保护。</span><span class="sxs-lookup"><span data-stu-id="72f4d-181">Configure a local override for the configuration to turn on real-time protection.</span></span> <span data-ttu-id="72f4d-182">此设置只能由组策略设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-182">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="72f4d-183">如果启用此设置，本地首选项设置将优先于组策略。</span><span class="sxs-lookup"><span data-stu-id="72f4d-183">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="72f4d-184">如果禁用或不配置此设置，则组策略将优先于本地首选项设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-184">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="72f4d-185">已启用</span><span class="sxs-lookup"><span data-stu-id="72f4d-185">Enabled</span></span> |
       | <span data-ttu-id="72f4d-186">配置本地设置覆盖以监视传入和传出文件活动</span><span class="sxs-lookup"><span data-stu-id="72f4d-186">Configure local setting override for monitoring for incoming and outgoing file activity</span></span> | <span data-ttu-id="72f4d-187">为传入和传出文件活动的监视配置配置本地覆盖。</span><span class="sxs-lookup"><span data-stu-id="72f4d-187">Configure a local override for the configuration of monitoring for incoming and outgoing file activity.</span></span> <span data-ttu-id="72f4d-188">此设置只能由组策略设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-188">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="72f4d-189">如果启用此设置，本地首选项设置将优先于组策略。</span><span class="sxs-lookup"><span data-stu-id="72f4d-189">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="72f4d-190">如果禁用或不配置此设置，则组策略将优先于本地首选项设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-190">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span> | <span data-ttu-id="72f4d-191">已启用</span><span class="sxs-lookup"><span data-stu-id="72f4d-191">Enabled</span></span> |
       | <span data-ttu-id="72f4d-192">配置对传入和传出文件和程序活动的监视</span><span class="sxs-lookup"><span data-stu-id="72f4d-192">Configure monitoring for incoming and outgoing file and program activity</span></span> | <span data-ttu-id="72f4d-193">指定监控应在传入、传出和/或两个方向上执行。</span><span class="sxs-lookup"><span data-stu-id="72f4d-193">Specify whether monitoring should occur on incoming, outgoing, both, or neither direction.</span></span> <span data-ttu-id="72f4d-194">这适用于Windows服务器安装，其中定义了特定服务器或服务器角色，这些服务器角色仅看到一个方向中的大量文件更改，并且希望提高网络性能。</span><span class="sxs-lookup"><span data-stu-id="72f4d-194">This is relevant for Windows Server installations where you have defined specific servers or Server Roles that see large amounts of file changes in only one direction and you want to improve network performance.</span></span> <span data-ttu-id="72f4d-195">网络上 (和) 的完全更新的终结点将几乎看不到性能影响，无论文件更改的数量或方向如何。</span><span class="sxs-lookup"><span data-stu-id="72f4d-195">Fully updated endpoints (and servers) on a network will see little performance impact irrespective of the number or direction of file changes.</span></span> | <span data-ttu-id="72f4d-196">启用 (两个方向) </span><span class="sxs-lookup"><span data-stu-id="72f4d-196">Enabled (both directions)</span></span> |

    1. <span data-ttu-id="72f4d-197">配置相应设置，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="72f4d-197">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="72f4d-198">对表中的每个设置重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="72f4d-198">Repeat the previous steps for each setting in the table.</span></span>

5. <span data-ttu-id="72f4d-199">配置Microsoft Defender 防病毒扫描策略设置。</span><span class="sxs-lookup"><span data-stu-id="72f4d-199">Configure the Microsoft Defender Antivirus scanning policy setting.</span></span> <span data-ttu-id="72f4d-200">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="72f4d-200">To do this:</span></span>  

    1. <span data-ttu-id="72f4d-201">从左 **Microsoft Defender 防病毒** 树中，单击"扫描 **"。**</span><span class="sxs-lookup"><span data-stu-id="72f4d-201">From the **Microsoft Defender Antivirus** tree on left pane, click **Scan**.</span></span>
    
       ![Microsoft Defender 防病毒扫描选项](images/gpedit-windows-defender-antivirus-scan.png)

    1. <span data-ttu-id="72f4d-203">在右侧 **"** 扫描详细信息"窗格中，双击下表中指定的策略设置：</span><span class="sxs-lookup"><span data-stu-id="72f4d-203">In the **Scan** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="72f4d-204">设置</span><span class="sxs-lookup"><span data-stu-id="72f4d-204">Setting</span></span> | <span data-ttu-id="72f4d-205">说明</span><span class="sxs-lookup"><span data-stu-id="72f4d-205">Description</span></span> | <span data-ttu-id="72f4d-206">默认设置</span><span class="sxs-lookup"><span data-stu-id="72f4d-206">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|    
       | <span data-ttu-id="72f4d-207">打开启发式</span><span class="sxs-lookup"><span data-stu-id="72f4d-207">Turn on heuristics</span></span> | <span data-ttu-id="72f4d-208">启发式保护将在系统要求引擎立即Microsoft Defender 防病毒或阻止可疑活动。</span><span class="sxs-lookup"><span data-stu-id="72f4d-208">Heuristic protection will disable or block suspicious activity immediately before the Microsoft Defender Antivirus engine is asked to detect the activity.</span></span> | <span data-ttu-id="72f4d-209">已启用</span><span class="sxs-lookup"><span data-stu-id="72f4d-209">Enabled</span></span> |

    1. <span data-ttu-id="72f4d-210">配置相应设置，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="72f4d-210">Configure the setting as appropriate, and click **OK**.</span></span>
    
6. <span data-ttu-id="72f4d-211">关闭 **本地组策略编辑器**。</span><span class="sxs-lookup"><span data-stu-id="72f4d-211">Close **Local Group Policy Editor**.</span></span>


## <a name="disable-real-time-protection-in-group-policy"></a><span data-ttu-id="72f4d-212">在组策略中禁用实时保护</span><span class="sxs-lookup"><span data-stu-id="72f4d-212">Disable real-time protection in Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="72f4d-213">禁用实时保护会大大降低终结点上的保护，不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="72f4d-213">Disabling real-time protection drastically reduces the protection on your endpoints and is not recommended.</span></span>

<span data-ttu-id="72f4d-214">默认启用主要实时保护功能，但可以使用本地组策略编辑器 **禁用该功能**。</span><span class="sxs-lookup"><span data-stu-id="72f4d-214">The main real-time protection capability is enabled by default, but you can disable it by using **Local Group Policy Editor**.</span></span>

<span data-ttu-id="72f4d-215">在组策略中禁用实时保护：</span><span class="sxs-lookup"><span data-stu-id="72f4d-215">To disable real-time protection in Group policy:</span></span>

1. <span data-ttu-id="72f4d-216">打开 **"本地组策略编辑器"。**</span><span class="sxs-lookup"><span data-stu-id="72f4d-216">Open **Local Group Policy Editor**.</span></span>

   1. <span data-ttu-id="72f4d-217">在任务栏Windows 10框中，键入 **gpedit**。</span><span class="sxs-lookup"><span data-stu-id="72f4d-217">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
   
   1. <span data-ttu-id="72f4d-218">在 **"最佳匹配"** 下 **，单击"编辑组策略**"以启动 **"本地组策略编辑器"。**</span><span class="sxs-lookup"><span data-stu-id="72f4d-218">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>

2.  <span data-ttu-id="72f4d-219">在本地组策略编辑器的左窗格中，将树展开到计算机配置管理模板  >    >  **Windows 组件** Microsoft Defender 防病毒  >    >  **实时保护**。</span><span class="sxs-lookup"><span data-stu-id="72f4d-219">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Real-time Protection**.</span></span>

3. <span data-ttu-id="72f4d-220">在 **右侧"实时保护"** 详细信息窗格中，双击"**关闭实时保护"。**</span><span class="sxs-lookup"><span data-stu-id="72f4d-220">In the **Real-time Protection** details pane on right, double-click **Turn off real-time protection**.</span></span>

   ![关闭实时保护](images/gpedit-turn-off-real-time-protection.png)

4. <span data-ttu-id="72f4d-222">在 **关闭实时保护设置** 窗口中，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="72f4d-222">In the **Turn off real-time protection** setting window, set the option to **Enabled**.</span></span>

   ![关闭启用实时保护](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. <span data-ttu-id="72f4d-224">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="72f4d-224">Click **OK**.</span></span>

6. <span data-ttu-id="72f4d-225">关闭 **本地组策略编辑器**。</span><span class="sxs-lookup"><span data-stu-id="72f4d-225">Close **Local Group Policy Editor**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="72f4d-226">相关文章</span><span class="sxs-lookup"><span data-stu-id="72f4d-226">Related articles</span></span>

- [<span data-ttu-id="72f4d-227">配置方案、高要求和实时保护</span><span class="sxs-lookup"><span data-stu-id="72f4d-227">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="72f4d-228">Microsoft Defender 防病毒Windows 10</span><span class="sxs-lookup"><span data-stu-id="72f4d-228">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)