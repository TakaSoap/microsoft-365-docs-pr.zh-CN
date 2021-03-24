---
title: 对 Microsoft Defender for Endpoint 中的文件执行响应操作
description: 通过停止和隔离文件或阻止文件并检查活动详细信息，对与文件相关的警报执行响应操作。
keywords: 响应、停止和隔离、阻止文件、深入分析
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ba48adcf93c5b768b2280729b33a1a7d361919cb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055941"
---
# <a name="take-response-actions-on-a-file"></a><span data-ttu-id="8742f-104">对文件执行响应操作</span><span class="sxs-lookup"><span data-stu-id="8742f-104">Take response actions on a file</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8742f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8742f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8742f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8742f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> <span data-ttu-id="8742f-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="8742f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8742f-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="8742f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-responddile-abovefoldlink)

<span data-ttu-id="8742f-109">通过停止和隔离文件或阻止文件来快速响应检测到的攻击。</span><span class="sxs-lookup"><span data-stu-id="8742f-109">Quickly respond to detected attacks by stopping and quarantining files or blocking a file.</span></span> <span data-ttu-id="8742f-110">对文件采取操作后，可以在操作中心查看活动详细信息。</span><span class="sxs-lookup"><span data-stu-id="8742f-110">After taking action on files, you can check activity details in the Action center.</span></span>

<span data-ttu-id="8742f-111">响应操作在文件的详细配置文件页上可用。</span><span class="sxs-lookup"><span data-stu-id="8742f-111">Response actions are available on a file's detailed profile page.</span></span> <span data-ttu-id="8742f-112">进入此页面后，可以通过切换新的"文件"页面在新页面布局和旧 **页面布局之间切换**。</span><span class="sxs-lookup"><span data-stu-id="8742f-112">Once on this page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="8742f-113">本文的其余部分介绍了较新的页面布局。</span><span class="sxs-lookup"><span data-stu-id="8742f-113">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="8742f-114">响应操作沿着文件页的顶部运行，包括：</span><span class="sxs-lookup"><span data-stu-id="8742f-114">Response actions run along the top of the file page, and include:</span></span>

- <span data-ttu-id="8742f-115">停止和隔离文件</span><span class="sxs-lookup"><span data-stu-id="8742f-115">Stop and Quarantine File</span></span>
- <span data-ttu-id="8742f-116">添加指示器</span><span class="sxs-lookup"><span data-stu-id="8742f-116">Add Indicator</span></span>
- <span data-ttu-id="8742f-117">下载文件</span><span class="sxs-lookup"><span data-stu-id="8742f-117">Download file</span></span>
- <span data-ttu-id="8742f-118">咨询威胁专家</span><span class="sxs-lookup"><span data-stu-id="8742f-118">Consult a threat expert</span></span>
- <span data-ttu-id="8742f-119">操作中心</span><span class="sxs-lookup"><span data-stu-id="8742f-119">Action center</span></span>

<span data-ttu-id="8742f-120">还可以提交文件进行深入分析，以在安全的云沙盒中运行该文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-120">You can also submit files for deep analysis, to run the file in a secure cloud sandbox.</span></span> <span data-ttu-id="8742f-121">分析完成后，您将获得提供有关文件行为的信息的详细报告。</span><span class="sxs-lookup"><span data-stu-id="8742f-121">When the analysis is complete, you'll get a detailed report that provides information about the behavior of the file.</span></span> <span data-ttu-id="8742f-122">可以通过选择"深入分析"选项卡来提交文件进行深入分析并阅读 **过去的** 报告。它位于文件信息卡下方。</span><span class="sxs-lookup"><span data-stu-id="8742f-122">You can submit files for deep analysis and read past reports by selecting the **Deep analysis** tab. It's located below the file information cards.</span></span>

<span data-ttu-id="8742f-123">某些操作需要某些权限。</span><span class="sxs-lookup"><span data-stu-id="8742f-123">Some actions require certain permissions.</span></span> <span data-ttu-id="8742f-124">下表介绍了某些权限对 PE 文件和非 PE (可执行文件) 的操作：</span><span class="sxs-lookup"><span data-stu-id="8742f-124">The following table describes what action certain permissions can take on portable executable (PE) and non-PE files:</span></span>

| <span data-ttu-id="8742f-125">权限</span><span class="sxs-lookup"><span data-stu-id="8742f-125">Permission</span></span>             | <span data-ttu-id="8742f-126">PE 文件</span><span class="sxs-lookup"><span data-stu-id="8742f-126">PE files</span></span> | <span data-ttu-id="8742f-127">非 PE 文件</span><span class="sxs-lookup"><span data-stu-id="8742f-127">Non-PE files</span></span> |
| :--------------------- | :------: | :----------: |
| <span data-ttu-id="8742f-128">查看数据</span><span class="sxs-lookup"><span data-stu-id="8742f-128">View data</span></span>              |     <span data-ttu-id="8742f-129">X</span><span class="sxs-lookup"><span data-stu-id="8742f-129">X</span></span>    |       <span data-ttu-id="8742f-130">X</span><span class="sxs-lookup"><span data-stu-id="8742f-130">X</span></span>      |
| <span data-ttu-id="8742f-131">警报调查</span><span class="sxs-lookup"><span data-stu-id="8742f-131">Alerts investigation</span></span>   | <span data-ttu-id="8742f-132">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="8742f-132">&#x2611;</span></span> |       <span data-ttu-id="8742f-133">X</span><span class="sxs-lookup"><span data-stu-id="8742f-133">X</span></span>      |
| <span data-ttu-id="8742f-134">实时响应基本</span><span class="sxs-lookup"><span data-stu-id="8742f-134">Live response basic</span></span>    |     <span data-ttu-id="8742f-135">X</span><span class="sxs-lookup"><span data-stu-id="8742f-135">X</span></span>    |       <span data-ttu-id="8742f-136">X</span><span class="sxs-lookup"><span data-stu-id="8742f-136">X</span></span>      |
| <span data-ttu-id="8742f-137">实时响应高级</span><span class="sxs-lookup"><span data-stu-id="8742f-137">Live response advanced</span></span> | <span data-ttu-id="8742f-138">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="8742f-138">&#x2611;</span></span> |   <span data-ttu-id="8742f-139">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="8742f-139">&#x2611;</span></span>   |

<span data-ttu-id="8742f-140">有关角色详细信息，请参阅为基于角色的访问控制 [创建和管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="8742f-140">For more information on roles, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="stop-and-quarantine-files-in-your-network"></a><span data-ttu-id="8742f-141">停止和隔离网络中文件</span><span class="sxs-lookup"><span data-stu-id="8742f-141">Stop and quarantine files in your network</span></span>

<span data-ttu-id="8742f-142">通过停止恶意进程并隔离观察到的文件，你可以在你的组织中包含攻击。</span><span class="sxs-lookup"><span data-stu-id="8742f-142">You can contain an attack in your organization by stopping the malicious process and quarantining the file where it was observed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8742f-143">只有在：</span><span class="sxs-lookup"><span data-stu-id="8742f-143">You can only take this action if:</span></span>
>
> - <span data-ttu-id="8742f-144">正在采取操作的设备运行的是 Windows 10 版本 1703 或更高版本</span><span class="sxs-lookup"><span data-stu-id="8742f-144">The device you're taking the action on is running Windows 10, version 1703 or later</span></span>
> - <span data-ttu-id="8742f-145">该文件不属于受信任的第三方发布者，或者未由 Microsoft 签名</span><span class="sxs-lookup"><span data-stu-id="8742f-145">The file does not belong to trusted third-party publishers or not signed by Microsoft</span></span>
> - <span data-ttu-id="8742f-146">Microsoft Defender 防病毒必须至少在被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="8742f-146">Microsoft Defender Antivirus must at least be running on Passive mode.</span></span> <span data-ttu-id="8742f-147">有关详细信息，请参阅 [Microsoft Defender 防病毒兼容性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="8742f-147">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

<span data-ttu-id="8742f-148">停止 **和隔离文件** 操作包括停止正在运行的进程、隔离文件以及删除永久性数据（如注册表项）。</span><span class="sxs-lookup"><span data-stu-id="8742f-148">The **Stop and Quarantine File** action includes stopping running processes, quarantining the files, and deleting persistent data such as registry keys.</span></span>

<span data-ttu-id="8742f-149">此操作在 Windows 10 版本 1703 或更高版本（过去 30 天内观测到该文件）的设备上生效。</span><span class="sxs-lookup"><span data-stu-id="8742f-149">This action takes effect on devices with Windows 10, version 1703 or later, where the file was observed in the last 30 days.</span></span>

> [!NOTE]
> <span data-ttu-id="8742f-150">你将能够随时从隔离区还原文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-150">You’ll be able to restore the file from quarantine at any time.</span></span>

### <a name="stop-and-quarantine-files"></a><span data-ttu-id="8742f-151">停止和隔离文件</span><span class="sxs-lookup"><span data-stu-id="8742f-151">Stop and quarantine files</span></span>

1. <span data-ttu-id="8742f-152">选择要停止和隔离的文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-152">Select the file you want to stop and quarantine.</span></span> <span data-ttu-id="8742f-153">可以从以下任一视图中选择文件，或使用"搜索"框：</span><span class="sxs-lookup"><span data-stu-id="8742f-153">You can select a file from any of the following views or use the Search box:</span></span>

   - <span data-ttu-id="8742f-154">**警报** - 单击"项目"时间线中的"说明"或"详细信息"中的相应链接</span><span class="sxs-lookup"><span data-stu-id="8742f-154">**Alerts** - click the corresponding links from the Description or Details in the Artifact timeline</span></span>
   - <span data-ttu-id="8742f-155">**搜索框** - **从下拉菜单** 中选择"文件"，然后输入文件名</span><span class="sxs-lookup"><span data-stu-id="8742f-155">**Search box** - select **File** from the drop–down menu and enter the file name</span></span>

   > [!NOTE]
   > <span data-ttu-id="8742f-156">停止和隔离文件操作限制为最多 1000 台设备。</span><span class="sxs-lookup"><span data-stu-id="8742f-156">The stop and quarantine file action is limited to a maximum of 1000 devices.</span></span> <span data-ttu-id="8742f-157">若要在更多设备上停止文件，请参阅添加 [用于阻止或允许文件的指示器](#add-indicator-to-block-or-allow-a-file)。</span><span class="sxs-lookup"><span data-stu-id="8742f-157">To stop a file on a larger number of devices, see [Add indicator to block or allow file](#add-indicator-to-block-or-allow-a-file).</span></span>

2. <span data-ttu-id="8742f-158">转到顶部栏，然后选择"停止 **和隔离文件"。**</span><span class="sxs-lookup"><span data-stu-id="8742f-158">Go to the top bar and select **Stop and Quarantine File**.</span></span>

   ![停止和隔离文件操作的图像](images/atp-stop-quarantine-file.png)

3. <span data-ttu-id="8742f-160">指定原因，然后选择"确认 **"。**</span><span class="sxs-lookup"><span data-stu-id="8742f-160">Specify a reason, then select **Confirm**.</span></span>

   ![停止和隔离文件模式窗口的图像](images/atp-stop-quarantine.png)

   <span data-ttu-id="8742f-162">操作中心显示提交信息：</span><span class="sxs-lookup"><span data-stu-id="8742f-162">The Action center shows the submission information:</span></span>
   
   ![停止和隔离文件操作中心的图像](images/atp-stopnquarantine-file.png)

   - <span data-ttu-id="8742f-164">**提交时间** - 显示提交操作的时间。</span><span class="sxs-lookup"><span data-stu-id="8742f-164">**Submission time** - Shows when the action was submitted.</span></span>
   - <span data-ttu-id="8742f-165">**Success** - 显示已停止和隔离文件的设备数。</span><span class="sxs-lookup"><span data-stu-id="8742f-165">**Success** - Shows the number of devices where the file has been stopped and quarantined.</span></span>
   - <span data-ttu-id="8742f-166">**Failed** - 显示操作失败的设备数量和有关失败的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8742f-166">**Failed** - Shows the number of devices where the action failed and details about the failure.</span></span>
   - <span data-ttu-id="8742f-167">**挂起** - 显示文件尚未停止和隔离的设备数量。</span><span class="sxs-lookup"><span data-stu-id="8742f-167">**Pending** - Shows the number of devices where the file is yet to be stopped and quarantined from.</span></span> <span data-ttu-id="8742f-168">当设备脱机或未连接到网络时，这可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="8742f-168">This can take time for cases when the device is offline or not connected to the network.</span></span>

4. <span data-ttu-id="8742f-169">选择任何状态指示器以查看有关操作详细信息。</span><span class="sxs-lookup"><span data-stu-id="8742f-169">Select any of the status indicators to view more information about the action.</span></span> <span data-ttu-id="8742f-170">例如，选择 **"失败** "以查看操作失败的地方。</span><span class="sxs-lookup"><span data-stu-id="8742f-170">For example, select **Failed** to see where the action failed.</span></span>

<span data-ttu-id="8742f-171">**有关设备用户的通知**：</span><span class="sxs-lookup"><span data-stu-id="8742f-171">**Notification on device user**:</span></span></br>
<span data-ttu-id="8742f-172">从设备中删除文件时，将显示以下通知：</span><span class="sxs-lookup"><span data-stu-id="8742f-172">When the file is being removed from a device, the following notification is shown:</span></span>

![设备用户通知的图像](images/atp-notification-file.png)

<span data-ttu-id="8742f-174">在设备时间线中，将针对停止和隔离文件的每个设备添加一个新事件。</span><span class="sxs-lookup"><span data-stu-id="8742f-174">In the device timeline, a new event is added for each device where a file was stopped and quarantined.</span></span>

<span data-ttu-id="8742f-175">在针对整个组织中广泛使用的文件实施操作之前，会显示一条警告。</span><span class="sxs-lookup"><span data-stu-id="8742f-175">A warning is shown before the action is implemented for files widely used throughout an organization.</span></span> <span data-ttu-id="8742f-176">它用于验证操作是否预期。</span><span class="sxs-lookup"><span data-stu-id="8742f-176">It's to validate that the operation is intended.</span></span>

## <a name="restore-file-from-quarantine"></a><span data-ttu-id="8742f-177">从隔离区还原文件</span><span class="sxs-lookup"><span data-stu-id="8742f-177">Restore file from quarantine</span></span>

<span data-ttu-id="8742f-178">如果在调查后确定文件是干净的，你可以回滚并从隔离区中删除文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-178">You can roll back and remove a file from quarantine if you’ve determined that it’s clean after an investigation.</span></span> <span data-ttu-id="8742f-179">在隔离文件的每台设备上运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="8742f-179">Run the following command on each device where the file was quarantined.</span></span>

1. <span data-ttu-id="8742f-180">在设备上打开提升的命令行提示符：</span><span class="sxs-lookup"><span data-stu-id="8742f-180">Open an elevated command–line prompt on the device:</span></span>

   1. <span data-ttu-id="8742f-181">转到“**开始**”并键入“_cmd_”。</span><span class="sxs-lookup"><span data-stu-id="8742f-181">Go to **Start** and type _cmd_.</span></span>

   1. <span data-ttu-id="8742f-182">右键单击命令 **提示符** ，然后选择 **以管理员角色运行**。</span><span class="sxs-lookup"><span data-stu-id="8742f-182">Right–click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="8742f-183">输入以下命令，然后按 **Enter：**</span><span class="sxs-lookup"><span data-stu-id="8742f-183">Enter the following command, and press **Enter**:</span></span>

   ```powershell
   “%ProgramFiles%\Windows Defender\MpCmdRun.exe” –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
   ```

> [!NOTE]
> <span data-ttu-id="8742f-184">在某些情况下 **，ThreatName** 可能显示为：EUS：Win32/CustomEnterpriseBlock！cl。</span><span class="sxs-lookup"><span data-stu-id="8742f-184">In some scenarios, the **ThreatName** may appear as: EUS:Win32/CustomEnterpriseBlock!cl.</span></span>
>
> <span data-ttu-id="8742f-185">Defender for Endpoint 将还原最近 30 天内在此设备上隔离的所有自定义阻止文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-185">Defender for Endpoint will restore all custom blocked files that were quarantined on this device in the last 30 days.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8742f-186">作为潜在网络威胁隔离的文件可能无法恢复。</span><span class="sxs-lookup"><span data-stu-id="8742f-186">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="8742f-187">如果用户尝试在隔离后还原文件，则该文件可能无法访问。</span><span class="sxs-lookup"><span data-stu-id="8742f-187">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="8742f-188">这是因为系统不再具有访问该文件的网络凭据。</span><span class="sxs-lookup"><span data-stu-id="8742f-188">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="8742f-189">通常，这是临时登录到系统或共享文件夹且访问令牌过期的结果。</span><span class="sxs-lookup"><span data-stu-id="8742f-189">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

## <a name="download-or-collect-file"></a><span data-ttu-id="8742f-190">下载或收集文件</span><span class="sxs-lookup"><span data-stu-id="8742f-190">Download or collect file</span></span>

<span data-ttu-id="8742f-191">从 **响应** 操作中选择"下载文件"，可下载包含文件的本地受密码保护的 .zip 存档。</span><span class="sxs-lookup"><span data-stu-id="8742f-191">Selecting **Download file** from the response actions allows you to download a local, password-protected .zip archive containing your file.</span></span> <span data-ttu-id="8742f-192">将出现一个飞出图，可在其中记录下载文件的原因并设置密码。</span><span class="sxs-lookup"><span data-stu-id="8742f-192">A flyout will appear where you can record a reason for downloading the file, and set a password.</span></span>

<span data-ttu-id="8742f-193">默认情况下，你将无法下载隔离的文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-193">By default, you will not be able to download files that are in quarantine.</span></span>

![下载文件操作的图像](images/atp-download-file-action.png)

### <a name="collect-files"></a><span data-ttu-id="8742f-195">收集文件</span><span class="sxs-lookup"><span data-stu-id="8742f-195">Collect files</span></span>

<span data-ttu-id="8742f-196">如果 Microsoft Defender for Endpoint 尚未存储文件，则你无法下载它。</span><span class="sxs-lookup"><span data-stu-id="8742f-196">If a file is not already stored by Microsoft Defender for Endpoint, you can't download it.</span></span> <span data-ttu-id="8742f-197">相反，你将在同一 **位置看到** "收集文件"按钮。</span><span class="sxs-lookup"><span data-stu-id="8742f-197">Instead, you'll see a **Collect file** button in the same location.</span></span> <span data-ttu-id="8742f-198">如果在过去 30 天内未在组织中看到文件，将禁用收集文件。 </span><span class="sxs-lookup"><span data-stu-id="8742f-198">If a file hasn't been seen in the organization in the past 30 days, **Collect file** will be disabled.</span></span>
> [!Important]
> <span data-ttu-id="8742f-199">作为潜在网络威胁隔离的文件可能无法恢复。</span><span class="sxs-lookup"><span data-stu-id="8742f-199">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="8742f-200">如果用户尝试在隔离后还原文件，则该文件可能无法访问。</span><span class="sxs-lookup"><span data-stu-id="8742f-200">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="8742f-201">这是因为系统不再具有访问该文件的网络凭据。</span><span class="sxs-lookup"><span data-stu-id="8742f-201">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="8742f-202">通常，这是临时登录到系统或共享文件夹且访问令牌过期的结果。</span><span class="sxs-lookup"><span data-stu-id="8742f-202">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

## <a name="add-indicator-to-block-or-allow-a-file"></a><span data-ttu-id="8742f-203">添加用于阻止或允许文件的指示器</span><span class="sxs-lookup"><span data-stu-id="8742f-203">Add indicator to block or allow a file</span></span>

<span data-ttu-id="8742f-204">通过禁止潜在恶意文件或可疑恶意软件，防止攻击在组织中进一步传播。</span><span class="sxs-lookup"><span data-stu-id="8742f-204">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="8742f-205">如果你知道 PE 文件中可能存在恶意 (可执行) ，可以阻止它。</span><span class="sxs-lookup"><span data-stu-id="8742f-205">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="8742f-206">此操作将阻止在组织的设备上读取、写入或执行该操作。</span><span class="sxs-lookup"><span data-stu-id="8742f-206">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="8742f-207">如果你的组织使用 Microsoft Defender 防病毒且云提供的保护已启用，则此功能可用。</span><span class="sxs-lookup"><span data-stu-id="8742f-207">This feature is available if your organization uses Microsoft Defender Antivirus and Cloud–delivered protection is enabled.</span></span> <span data-ttu-id="8742f-208">有关详细信息，请参阅管理 [云提供的保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="8742f-208">For more information, see [Manage cloud–delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
>
> - <span data-ttu-id="8742f-209">反恶意软件客户端版本必须为 4.18.1901.x 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8742f-209">The Antimalware client version must be 4.18.1901.x or later.</span></span>
> - <span data-ttu-id="8742f-210">此功能旨在防止从 web (可疑恶意软件) 潜在恶意文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-210">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="8742f-211">它当前支持可移植的可执行 (PE) 文件，包括 _.exe_ 和 _.dll_ 文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-211">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="8742f-212">覆盖范围将随着时间的推移而延长。</span><span class="sxs-lookup"><span data-stu-id="8742f-212">The coverage will be extended over time.</span></span>
> - <span data-ttu-id="8742f-213">此响应操作适用于 Windows 10 版本 1703 或更高版本上的设备。</span><span class="sxs-lookup"><span data-stu-id="8742f-213">This response action is available for devices on Windows 10, version 1703 or later.</span></span>
> - <span data-ttu-id="8742f-214">如果在允许或阻止操作之前文件分类存在于设备的缓存中，则不能对文件执行允许或阻止功能。</span><span class="sxs-lookup"><span data-stu-id="8742f-214">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action.</span></span>

> [!NOTE]
> <span data-ttu-id="8742f-215">PE 文件需在设备时间线中，才能执行该操作。</span><span class="sxs-lookup"><span data-stu-id="8742f-215">The PE file needs to be in the device timeline for you to be able to take this action.</span></span>
>
> <span data-ttu-id="8742f-216">在采取操作和阻止实际文件之间，可能有几分钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="8742f-216">There may be a couple of minutes of latency between the time the action is taken and the actual file being blocked.</span></span>

### <a name="enable-the-block-file-feature"></a><span data-ttu-id="8742f-217">启用阻止文件功能</span><span class="sxs-lookup"><span data-stu-id="8742f-217">Enable the block file feature</span></span>

<span data-ttu-id="8742f-218">若要开始阻止文件，首先需要打开"设置"[**中的"阻止或**](advanced-features.md)允许"功能。</span><span class="sxs-lookup"><span data-stu-id="8742f-218">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
### <a name="allow-or-block-file"></a><span data-ttu-id="8742f-219">允许或阻止文件</span><span class="sxs-lookup"><span data-stu-id="8742f-219">Allow or block file</span></span>

<span data-ttu-id="8742f-220">为文件添加指示器哈希时，可以选择引发警报，并阻止组织中设备尝试运行该文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-220">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="8742f-221">由指示器自动阻止的文件不会显示在文件的"操作中心"中，但警报仍显示在警报队列中。</span><span class="sxs-lookup"><span data-stu-id="8742f-221">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

<span data-ttu-id="8742f-222">有关 [阻止和](manage-indicators.md) 引发文件警报的更多详细信息，请参阅管理指示器。</span><span class="sxs-lookup"><span data-stu-id="8742f-222">See [manage indicators](manage-indicators.md) for more details on blocking and raising alerts on files.</span></span>

<span data-ttu-id="8742f-223">若要停止阻止文件，请删除指示器。</span><span class="sxs-lookup"><span data-stu-id="8742f-223">To stop blocking a file, remove the indicator.</span></span> <span data-ttu-id="8742f-224">您可以通过文件配置文件页上 **的"编辑** 指示器"操作来这样做。</span><span class="sxs-lookup"><span data-stu-id="8742f-224">You can do so via the **Edit Indicator** action on the file's profile page.</span></span> <span data-ttu-id="8742f-225">在添加指示器之前，此操作将在添加指示器 **操作** 相同的位置可见。</span><span class="sxs-lookup"><span data-stu-id="8742f-225">This action will be visible in the same position as the **Add Indicator** action, before you added the indicator.</span></span>

<span data-ttu-id="8742f-226">还可以编辑"设置"页中的"规则指示器  >  **"下的指示器**。</span><span class="sxs-lookup"><span data-stu-id="8742f-226">You can also edit indicators from  the **Settings** page, under **Rules** > **Indicators**.</span></span> <span data-ttu-id="8742f-227">此区域中的指示器按其文件的哈希列出。</span><span class="sxs-lookup"><span data-stu-id="8742f-227">Indicators are listed in this area by their file's hash.</span></span>

## <a name="consult-a-threat-expert"></a><span data-ttu-id="8742f-228">咨询威胁专家</span><span class="sxs-lookup"><span data-stu-id="8742f-228">Consult a threat expert</span></span>

<span data-ttu-id="8742f-229">有关可能受到威胁的设备或已受到威胁的设备的更多见解，请咨询 Microsoft 威胁专家。</span><span class="sxs-lookup"><span data-stu-id="8742f-229">Consult a Microsoft threat expert for more insights on a potentially compromised device, or already compromised devices.</span></span> <span data-ttu-id="8742f-230">Microsoft 威胁专家可直接在 Microsoft Defender 安全中心内参与，以及时准确地做出响应。</span><span class="sxs-lookup"><span data-stu-id="8742f-230">Microsoft Threat Experts are engaged directly from within the Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="8742f-231">专家提供有关可能受到威胁的设备的见解，并帮助你了解复杂的威胁和目标攻击通知。</span><span class="sxs-lookup"><span data-stu-id="8742f-231">Experts provide insights on a potentially compromised device and help you understand complex threats and targeted attack notifications.</span></span> <span data-ttu-id="8742f-232">它们还可以提供有关你在门户仪表板上看到的警报或威胁智能上下文的信息。</span><span class="sxs-lookup"><span data-stu-id="8742f-232">They can also provide information about the alerts or a threat intelligence context that you see on your portal dashboard.</span></span>

<span data-ttu-id="8742f-233">有关详细信息 [，请参阅咨询 Microsoft 威胁](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) 专家。</span><span class="sxs-lookup"><span data-stu-id="8742f-233">See [Consult a Microsoft Threat Expert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) for details.</span></span>

## <a name="check-activity-details-in-action-center"></a><span data-ttu-id="8742f-234">在操作中心中检查活动详细信息</span><span class="sxs-lookup"><span data-stu-id="8742f-234">Check activity details in Action center</span></span>

<span data-ttu-id="8742f-235">**操作中心** 提供有关对设备或文件采取的操作的信息。</span><span class="sxs-lookup"><span data-stu-id="8742f-235">The **Action center** provides information on actions that were taken on a device or file.</span></span> <span data-ttu-id="8742f-236">可以查看以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="8742f-236">You can view the following details:</span></span>

- <span data-ttu-id="8742f-237">调查包集合</span><span class="sxs-lookup"><span data-stu-id="8742f-237">Investigation package collection</span></span>
- <span data-ttu-id="8742f-238">防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="8742f-238">Antivirus scan</span></span>
- <span data-ttu-id="8742f-239">应用限制</span><span class="sxs-lookup"><span data-stu-id="8742f-239">App restriction</span></span>
- <span data-ttu-id="8742f-240">设备隔离</span><span class="sxs-lookup"><span data-stu-id="8742f-240">Device isolation</span></span>

<span data-ttu-id="8742f-241">还会显示所有其他相关详细信息，如提交日期/时间、提交用户以及操作是成功还是失败。</span><span class="sxs-lookup"><span data-stu-id="8742f-241">All other related details are also shown, such as submission date/time, submitting user, and if the action succeeded or failed.</span></span>

![包含信息的操作中心图像](images/action-center-details.png)

## <a name="deep-analysis"></a><span data-ttu-id="8742f-243">深度分析</span><span class="sxs-lookup"><span data-stu-id="8742f-243">Deep analysis</span></span>

<span data-ttu-id="8742f-244">网络安全调查通常由警报触发。</span><span class="sxs-lookup"><span data-stu-id="8742f-244">Cyber security investigations are typically triggered by an alert.</span></span> <span data-ttu-id="8742f-245">警报与一个或多个观察到的文件相关，这些文件通常是新的或未知的。</span><span class="sxs-lookup"><span data-stu-id="8742f-245">Alerts are related to one or more observed files that are often new or unknown.</span></span> <span data-ttu-id="8742f-246">选择文件后，你将看到文件视图，可在其中查看文件的元数据。</span><span class="sxs-lookup"><span data-stu-id="8742f-246">Selecting a file takes you to the file view where you can see the file's metadata.</span></span> <span data-ttu-id="8742f-247">若要丰富与文件相关的数据，可以提交文件进行深入分析。</span><span class="sxs-lookup"><span data-stu-id="8742f-247">To enrich the data related to the file, you can submit the file for deep analysis.</span></span>

<span data-ttu-id="8742f-248">深度分析功能在安全的、完全检测的云环境中执行文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-248">The Deep analysis feature executes a file in a secure, fully instrumented cloud environment.</span></span> <span data-ttu-id="8742f-249">深度分析结果显示文件的活动、观察到的行为以及关联的项目，如丢弃的文件、注册表修改以及与 IP 的通信。</span><span class="sxs-lookup"><span data-stu-id="8742f-249">Deep analysis results show the file's activities, observed behaviors, and associated artifacts, such as dropped files, registry modifications, and communication with IPs.</span></span>
<span data-ttu-id="8742f-250">深度分析目前支持对可移植可执行文件 (PE) 文件 (_包括 .exe_ 和 _.dll_ 文件) 。</span><span class="sxs-lookup"><span data-stu-id="8742f-250">Deep analysis currently supports extensive analysis of portable executable (PE) files (including _.exe_ and _.dll_ files).</span></span>

<span data-ttu-id="8742f-251">文件的深入分析需要几分钟。</span><span class="sxs-lookup"><span data-stu-id="8742f-251">Deep analysis of a file takes several minutes.</span></span> <span data-ttu-id="8742f-252">文件分析完成后，"深入分析"选项卡将更新以显示摘要以及最新可用结果的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8742f-252">Once the file analysis is complete, the Deep Analysis tab will update to display a summary and the date and time of the latest available results.</span></span>

<span data-ttu-id="8742f-253">深度分析摘要包括观察到的行为列表，其中一些行为可指示恶意活动和可观测行为，包括联系的 IP 和磁盘上创建的文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-253">The deep analysis summary includes a list of observed *behaviors*, some of which can indicate malicious activity, and *observables*, including contacted IPs and files created on the disk.</span></span> <span data-ttu-id="8742f-254">如果未找到任何内容，这些部分将显示一条简短消息。</span><span class="sxs-lookup"><span data-stu-id="8742f-254">If nothing was found, these sections will display a brief message.</span></span>

<span data-ttu-id="8742f-255">深度分析结果与威胁智能匹配，任何匹配都将生成相应的警报。</span><span class="sxs-lookup"><span data-stu-id="8742f-255">Results of deep analysis are matched against threat intelligence and any matches will generate appropriate alerts.</span></span>

<span data-ttu-id="8742f-256">使用深度分析功能调查任何文件的详细信息，通常是在调查警报期间或出于任何其他怀疑恶意行为的原因。</span><span class="sxs-lookup"><span data-stu-id="8742f-256">Use the deep analysis feature to investigate the details of any file, usually during an investigation of an alert or for any other reason where you suspect malicious behavior.</span></span> <span data-ttu-id="8742f-257">此功能在文件的配置文件页上 **的** "深入分析"选项卡中提供。</span><span class="sxs-lookup"><span data-stu-id="8742f-257">This feature is available within the **Deep analysis** tab, on the file's profile page.</span></span><br/>
<br/>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4aAYy?rel=0]

<span data-ttu-id="8742f-258">**当文件在** Defender for Endpoint 后端示例集合中可用时，或在支持提交到深入分析的 Windows 10 设备上观察到该文件时，将启用提交进行深度分析。</span><span class="sxs-lookup"><span data-stu-id="8742f-258">**Submit for deep analysis** is enabled when the file is available in the Defender for Endpoint backend sample collection, or if it was observed on a Windows 10 device that supports submitting to deep analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="8742f-259">只能自动收集 Windows 10 中的文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-259">Only files from Windows 10 can be automatically collected.</span></span>

<span data-ttu-id="8742f-260">如果文件未在 Windows 10 设备上观测到，还可以通过 [Microsoft](https://www.microsoft.com/security/portal/submission/submit.aspx) 安全中心门户提交示例，并等待"提交以深入了解 **"** 按钮变为可用状态。</span><span class="sxs-lookup"><span data-stu-id="8742f-260">You can also submit a sample through the [Microsoft Security Center Portal](https://www.microsoft.com/security/portal/submission/submit.aspx) if the file wasn't observed on a Windows 10 device, and wait for **Submit for deep analysis** button to become available.</span></span>

> [!NOTE]
> <span data-ttu-id="8742f-261">由于 Microsoft 安全中心门户中的后端处理流，文件提交和 Defender for Endpoint 中深入分析功能的可用性之间最多存在 10 分钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="8742f-261">Due to backend processing flows in the Microsoft Security Center Portal, there could be up to 10 minutes of latency between file submission and availability of the deep analysis feature in Defender for Endpoint.</span></span>

<span data-ttu-id="8742f-262">收集示例后，Defender for Endpoint 在安全环境中运行文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-262">When the sample is collected, Defender for Endpoint runs the file in a secure environment.</span></span> <span data-ttu-id="8742f-263">然后，它创建观测到的行为和相关项目的详细报告，例如设备上丢弃的文件、与 IP 的通信以及注册表修改。</span><span class="sxs-lookup"><span data-stu-id="8742f-263">It then creates a detailed report of observed behaviors and associated artifacts, such as files dropped on devices, communication to IPs, and registry modifications.</span></span>

### <a name="submit-files-for-deep-analysis"></a><span data-ttu-id="8742f-264">提交文件进行深入分析</span><span class="sxs-lookup"><span data-stu-id="8742f-264">Submit files for deep analysis</span></span>

1. <span data-ttu-id="8742f-265">选择要提交进行深入分析的文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-265">Select the file that you want to submit for deep analysis.</span></span> <span data-ttu-id="8742f-266">可以从以下任一视图中选择或搜索文件：</span><span class="sxs-lookup"><span data-stu-id="8742f-266">You can select or search a file from any of the following views:</span></span>

    - <span data-ttu-id="8742f-267">警报 - 从"项目"时间线中的" **说明** " **或"详细信息** "中选择文件链接</span><span class="sxs-lookup"><span data-stu-id="8742f-267">Alerts - select the file links from the **Description** or **Details** in the Artifact timeline</span></span>
    - <span data-ttu-id="8742f-268">**设备列表**- 从"组织中设备"**部分的说明或** 详细信息 **中选择文件** 链接</span><span class="sxs-lookup"><span data-stu-id="8742f-268">**Devices list** - select the file links from the **Description** or **Details** in the **Device in organization** section</span></span>
    - <span data-ttu-id="8742f-269">搜索框 - **从下拉菜单** 中选择"文件"，然后输入文件名</span><span class="sxs-lookup"><span data-stu-id="8742f-269">Search box - select **File** from the drop–down menu and enter the file name</span></span>

2. <span data-ttu-id="8742f-270">在文件 **视图的"** 深入分析"选项卡中，选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="8742f-270">In the **Deep analysis** tab of the file view, select **Submit**.</span></span>

   ![只能在文件详细信息部分提交 PE 文件](images/submit-file.png)

   > [!NOTE]
   > <span data-ttu-id="8742f-272">仅支持 PE 文件，包括 _.exe_ 和 _.dll_ 文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-272">Only PE files are supported, including _.exe_ and _.dll_ files.</span></span>

<span data-ttu-id="8742f-273">将显示一个进度栏，并提供有关分析的不同阶段的信息。</span><span class="sxs-lookup"><span data-stu-id="8742f-273">A progress bar is displayed and provides information on the different stages of the analysis.</span></span> <span data-ttu-id="8742f-274">然后，您可以在分析完成时查看报告。</span><span class="sxs-lookup"><span data-stu-id="8742f-274">You can then view the report when the analysis is done.</span></span>

> [!NOTE]
> <span data-ttu-id="8742f-275">根据设备可用性，示例收集时间可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="8742f-275">Depending on device availability, sample collection time can vary.</span></span> <span data-ttu-id="8742f-276">示例集合有 3 小时超时。</span><span class="sxs-lookup"><span data-stu-id="8742f-276">There is a 3–hour timeout for sample collection.</span></span> <span data-ttu-id="8742f-277">如果当时没有联机 Windows 10 设备报告，则收集将失败，并且操作将中止。</span><span class="sxs-lookup"><span data-stu-id="8742f-277">The collection will fail and the operation will abort if there is no online Windows 10 device reporting at that time.</span></span> <span data-ttu-id="8742f-278">你可以重新提交文件进行深入分析，获取文件的新数据。</span><span class="sxs-lookup"><span data-stu-id="8742f-278">You can re–submit files for deep analysis to get fresh data on the file.</span></span>

### <a name="view-deep-analysis-reports"></a><span data-ttu-id="8742f-279">查看深入分析报告</span><span class="sxs-lookup"><span data-stu-id="8742f-279">View deep analysis reports</span></span>

<span data-ttu-id="8742f-280">查看提供的深入分析报告，以查看有关你提交的文件的更深入见解。</span><span class="sxs-lookup"><span data-stu-id="8742f-280">View the provided deep analysis report to see more in-depth insights on the file you submitted.</span></span> <span data-ttu-id="8742f-281">此功能在文件视图上下文中可用。</span><span class="sxs-lookup"><span data-stu-id="8742f-281">This feature is available in the file view context.</span></span>

<span data-ttu-id="8742f-282">您可以查看全面报告，该报告提供有关以下各节的详细信息：</span><span class="sxs-lookup"><span data-stu-id="8742f-282">You can view the comprehensive report that provides details on the following sections:</span></span>

- <span data-ttu-id="8742f-283">Behaviors</span><span class="sxs-lookup"><span data-stu-id="8742f-283">Behaviors</span></span>
- <span data-ttu-id="8742f-284">Observables</span><span class="sxs-lookup"><span data-stu-id="8742f-284">Observables</span></span>

<span data-ttu-id="8742f-285">提供的详细信息可以帮助你调查是否有潜在攻击的迹象。</span><span class="sxs-lookup"><span data-stu-id="8742f-285">The details provided can help you investigate if there are indications of a potential attack.</span></span>

1. <span data-ttu-id="8742f-286">选择要提交进行深入分析的文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-286">Select the file you submitted for deep analysis.</span></span>
2. <span data-ttu-id="8742f-287">选择" **深入分析"** 选项卡。如果之前有任何报告，报告摘要将显示在此选项卡中。</span><span class="sxs-lookup"><span data-stu-id="8742f-287">Select the **Deep analysis** tab. If there are any previous reports, the report summary will appear in this tab.</span></span>

    ![深度分析报告显示多个类别的详细信息](images/analysis-results-nothing500.png)

#### <a name="troubleshoot-deep-analysis"></a><span data-ttu-id="8742f-289">深度分析疑难解答</span><span class="sxs-lookup"><span data-stu-id="8742f-289">Troubleshoot deep analysis</span></span>

<span data-ttu-id="8742f-290">如果在尝试提交文件时遇到问题，请尝试以下每个疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="8742f-290">If you come across a problem when trying to submit a file, try each of the following troubleshooting steps.</span></span>

1. <span data-ttu-id="8742f-291">确保该文件是 PE 文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-291">Ensure that the file in question is a PE file.</span></span> <span data-ttu-id="8742f-292">PE 文件通常具有 _可执行程序或应用程序中 (.exe_ 或 _.dll_) 。</span><span class="sxs-lookup"><span data-stu-id="8742f-292">PE files typically have _.exe_ or _.dll_ extensions (executable programs or applications).</span></span>
2. <span data-ttu-id="8742f-293">确保服务具有对文件的访问权限，它仍然存在，并且尚未损坏或修改。</span><span class="sxs-lookup"><span data-stu-id="8742f-293">Ensure the service has access to the file, that it still exists, and hasn't been corrupted or modified.</span></span>
3. <span data-ttu-id="8742f-294">稍等一会，然后再次尝试提交文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-294">Wait a short while and try to submit the file again.</span></span> <span data-ttu-id="8742f-295">队列可能已满，或者出现临时连接或通信错误。</span><span class="sxs-lookup"><span data-stu-id="8742f-295">The queue may be full, or there was a temporary connection or communication error.</span></span>
4. <span data-ttu-id="8742f-296">如果未配置示例集合策略，则默认行为是允许示例集合。</span><span class="sxs-lookup"><span data-stu-id="8742f-296">If the sample collection policy isn't configured, then the default behavior is to allow sample collection.</span></span> <span data-ttu-id="8742f-297">如果已配置，请验证策略设置是否允许示例收集，然后再重新提交文件。</span><span class="sxs-lookup"><span data-stu-id="8742f-297">If it's configured, then verify the policy setting allows sample collection before submitting the file again.</span></span> <span data-ttu-id="8742f-298">配置示例集合后，请检查以下注册表值：</span><span class="sxs-lookup"><span data-stu-id="8742f-298">When sample collection is configured, then check the following registry value:</span></span>

    ```powershell
    Path: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
    Name: AllowSampleCollection
    Type: DWORD
    Hexadecimal value :
      Value = 0 – block sample collection
      Value = 1 – allow sample collection
    ```

1. <span data-ttu-id="8742f-299">通过组策略更改组织单位。</span><span class="sxs-lookup"><span data-stu-id="8742f-299">Change the organizational unit through the Group Policy.</span></span> <span data-ttu-id="8742f-300">有关详细信息，请参阅使用 [组策略配置](configure-endpoints-gp.md)。</span><span class="sxs-lookup"><span data-stu-id="8742f-300">For more information, see [Configure with Group Policy](configure-endpoints-gp.md).</span></span>
1. <span data-ttu-id="8742f-301">如果这些步骤无法解决问题，请与联系[winatp@microsoft.com。](mailto:winatp@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="8742f-301">If these steps do not resolve the issue, contact [winatp@microsoft.com](mailto:winatp@microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8742f-302">相关主题</span><span class="sxs-lookup"><span data-stu-id="8742f-302">Related topics</span></span>

- [<span data-ttu-id="8742f-303">在设备上执行响应操作</span><span class="sxs-lookup"><span data-stu-id="8742f-303">Take response actions on a device</span></span>](respond-machine-alerts.md)
- [<span data-ttu-id="8742f-304">调查文件</span><span class="sxs-lookup"><span data-stu-id="8742f-304">Investigate files</span></span>](investigate-files.md)
