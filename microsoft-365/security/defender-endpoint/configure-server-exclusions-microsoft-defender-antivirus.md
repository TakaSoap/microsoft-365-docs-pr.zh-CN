---
title: 在 Windows Server 上配置 Microsoft Defender 防病毒排除项
ms.reviewer: ''
manager: dansimp
description: Windows Server 包括基于服务器角色的自动排除项。 还可以添加自定义排除项。
keywords: 排除项， 服务器， 自动排除， 自动， 自定义， 扫描， Microsoft Defender 防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.openlocfilehash: 507edb980f671b2f39403cc41e540150f5e82891
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764337"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a><span data-ttu-id="0d11e-105">在 Windows Server 上配置 Microsoft Defender 防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-105">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0d11e-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0d11e-106">**Applies to:**</span></span>

- [<span data-ttu-id="0d11e-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0d11e-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0d11e-108">Windows Server 2016 和 Windows Server 2019 上的 Microsoft Defender 防病毒会按照你指定的服务器角色的定义，在某些排除项中自动注册你。</span><span class="sxs-lookup"><span data-stu-id="0d11e-108">Microsoft Defender Antivirus on Windows Server 2016 and Windows Server 2019 automatically enrolls you in certain exclusions, as defined by your specified server role.</span></span> <span data-ttu-id="0d11e-109">这些排除项不会显示在 Windows 安全应用中显示的标准排除 [列表中](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="0d11e-109">These exclusions do not appear in the standard exclusion lists that are shown in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0d11e-110">自动排除项仅适用于 RTP 扫描 (实时) 保护。</span><span class="sxs-lookup"><span data-stu-id="0d11e-110">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="0d11e-111">自动排除在完全/快速或按需扫描期间不适用。</span><span class="sxs-lookup"><span data-stu-id="0d11e-111">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>

<span data-ttu-id="0d11e-112">除了服务器角色定义的自动排除项之外，还可以添加或删除自定义排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-112">In addition to server role-defined automatic exclusions, you can add or remove custom exclusions.</span></span> <span data-ttu-id="0d11e-113">为此，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="0d11e-113">To do that, refer to these articles:</span></span>
- [<span data-ttu-id="0d11e-114">根据文件名、扩展名和文件夹位置配置并验证排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-114">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0d11e-115">配置并验证进程打开的文件的排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-115">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a><span data-ttu-id="0d11e-116">需要记住的几点</span><span class="sxs-lookup"><span data-stu-id="0d11e-116">A few points to keep in mind</span></span>

<span data-ttu-id="0d11e-117">请记住以下要点：</span><span class="sxs-lookup"><span data-stu-id="0d11e-117">Keep the following important points in mind:</span></span>

- <span data-ttu-id="0d11e-118">自定义排除项优先于自动排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-118">Custom exclusions take precedence over automatic exclusions.</span></span>
- <span data-ttu-id="0d11e-119">自动排除项仅适用于 RTP 扫描 (实时) 保护。</span><span class="sxs-lookup"><span data-stu-id="0d11e-119">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="0d11e-120">自动排除在完全/快速或按需扫描期间不适用。</span><span class="sxs-lookup"><span data-stu-id="0d11e-120">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>
- <span data-ttu-id="0d11e-121">自定义排除项和重复排除项与自动排除项不冲突。</span><span class="sxs-lookup"><span data-stu-id="0d11e-121">Custom and duplicate exclusions do not conflict with automatic exclusions.</span></span>
- <span data-ttu-id="0d11e-122">Microsoft Defender 防病毒使用部署映像服务和管理 (DISM) 工具来确定计算机上安装了哪些角色。</span><span class="sxs-lookup"><span data-stu-id="0d11e-122">Microsoft Defender Antivirus uses the Deployment Image Servicing and Management (DISM) tools to determine which roles are installed on your computer.</span></span>

## <a name="opt-out-of-automatic-exclusions"></a><span data-ttu-id="0d11e-123">选择退出自动排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-123">Opt out of automatic exclusions</span></span>

<span data-ttu-id="0d11e-124">在 Windows Server 2016 和 Windows Server 2019 中，安全智能更新提供的预定义排除项仅排除角色或功能的默认路径。</span><span class="sxs-lookup"><span data-stu-id="0d11e-124">In Windows Server 2016 and Windows Server 2019, the predefined exclusions delivered by Security intelligence updates only exclude the default paths for a role or feature.</span></span> <span data-ttu-id="0d11e-125">如果在自定义路径中安装了角色或功能，或者希望手动控制排除项集，请确保选择退出安全智能更新中提供的自动排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-125">If you installed a role or feature in a custom path, or you want to manually control the set of exclusions, make sure to opt out of the automatic exclusions delivered in Security intelligence updates.</span></span> <span data-ttu-id="0d11e-126">但请记住，自动提供的排除项已针对 Windows Server 2016 和 2019 角色进行了优化。</span><span class="sxs-lookup"><span data-stu-id="0d11e-126">But keep in mind that the exclusions that are delivered automatically are optimized for Windows Server 2016 and 2019 roles.</span></span> <span data-ttu-id="0d11e-127">请参阅 [定义排除列表之前](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 定义排除项的建议。</span><span class="sxs-lookup"><span data-stu-id="0d11e-127">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

> [!WARNING]
> <span data-ttu-id="0d11e-128">选择退出自动排除可能会对性能产生不利影响，或会导致数据损坏。</span><span class="sxs-lookup"><span data-stu-id="0d11e-128">Opting out of automatic exclusions may adversely impact performance, or result in data corruption.</span></span> <span data-ttu-id="0d11e-129">自动提供的排除项针对 Windows Server 2016 和 Windows Server 2019 角色进行了优化。</span><span class="sxs-lookup"><span data-stu-id="0d11e-129">The exclusions that are delivered automatically are optimized for Windows Server 2016 and Windows Server 2019 roles.</span></span>

<span data-ttu-id="0d11e-130">由于预定义的排除仅排除默认路径 ，因此如果将 NTDS 和 SYSVOL 移动到不同于原始路径的另一个驱动器或路径，则必须使用此处的信息手动添加排除项[。](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)</span><span class="sxs-lookup"><span data-stu-id="0d11e-130">Because predefined exclusions only exclude **default paths**, if you move NTDS and SYSVOL to another drive or path that is *different from the original path*, you must add exclusions manually using the information [here](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span></span>

<span data-ttu-id="0d11e-131">可以使用组策略、PowerShell cmdlet 和 WMI 禁用自动排除列表。</span><span class="sxs-lookup"><span data-stu-id="0d11e-131">You can disable the automatic exclusion lists with Group Policy, PowerShell cmdlets, and WMI.</span></span>

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="0d11e-132">使用组策略在 Windows Server 2016 和 Windows Server 2019 上禁用自动排除列表</span><span class="sxs-lookup"><span data-stu-id="0d11e-132">Use Group Policy to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

1. <span data-ttu-id="0d11e-133">在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="0d11e-133">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span></span> <span data-ttu-id="0d11e-134">右键单击要配置的组策略对象，然后单击编辑 **。**</span><span class="sxs-lookup"><span data-stu-id="0d11e-134">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>
2. <span data-ttu-id="0d11e-135">在"**组策略管理编辑器**"中，转到"**计算机配置**"，然后单击"**管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="0d11e-135">In the **Group Policy Management Editor** go to **Computer configuration**, and then click **Administrative templates**.</span></span>
3. <span data-ttu-id="0d11e-136">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **排除项**。</span><span class="sxs-lookup"><span data-stu-id="0d11e-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>
4. <span data-ttu-id="0d11e-137">双击关闭 **自动排除项**，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="0d11e-137">Double-click **Turn off Auto Exclusions**, and set the option to **Enabled**.</span></span> <span data-ttu-id="0d11e-138">单击" **确定**"。</span><span class="sxs-lookup"><span data-stu-id="0d11e-138">Then click **OK**.</span></span> 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a><span data-ttu-id="0d11e-139">使用 PowerShell cmdlet 禁用 Windows Server 2016 和 Windows Server 2019 上的自动排除列表</span><span class="sxs-lookup"><span data-stu-id="0d11e-139">Use PowerShell cmdlets to disable the auto-exclusions list on Windows Server 2016 and 2019</span></span>

<span data-ttu-id="0d11e-140">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0d11e-140">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

<span data-ttu-id="0d11e-141">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="0d11e-141">To learn more, see the following resources:</span></span>

- <span data-ttu-id="0d11e-142">[使用 PowerShell cmdlet 配置和运行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="0d11e-142">[Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>
- <span data-ttu-id="0d11e-143">[将 PowerShell 与 Microsoft Defender 防病毒一同使用](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="0d11e-143">[Use PowerShell with Microsoft Defender Antivirus](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="0d11e-144">使用 Windows Management Instruction (WMI) 禁用 Windows Server 2016 和 Windows Server 2019 上的自动排除列表</span><span class="sxs-lookup"><span data-stu-id="0d11e-144">Use Windows Management Instruction (WMI) to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

<span data-ttu-id="0d11e-145">对以下 [属性MSFT_MpPreference类](/previous-versions/windows/desktop/defender/msft-mppreference)的 **Set** 方法：</span><span class="sxs-lookup"><span data-stu-id="0d11e-145">Use the **Set** method of the [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) class for the following properties:</span></span>

```WMI
DisableAutoExclusions
```

<span data-ttu-id="0d11e-146">有关详细信息和允许的参数，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="0d11e-146">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="0d11e-147">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="0d11e-147">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a><span data-ttu-id="0d11e-148">自动排除项列表</span><span class="sxs-lookup"><span data-stu-id="0d11e-148">List of automatic exclusions</span></span>

<span data-ttu-id="0d11e-149">以下各节包含随自动排除项文件路径和文件类型一起提供的排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-149">The following sections contain the exclusions that are delivered with automatic exclusions file paths and file types.</span></span>

### <a name="default-exclusions-for-all-roles"></a><span data-ttu-id="0d11e-150">所有角色的默认排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-150">Default exclusions for all roles</span></span>

<span data-ttu-id="0d11e-151">本部分列出了所有 Windows Server 2016 和 2019 角色的默认排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-151">This section lists the default exclusions for all Windows Server 2016 and 2019 roles.</span></span>

> [!NOTE]
> <span data-ttu-id="0d11e-152">默认位置可能不同于本文中列出的位置。</span><span class="sxs-lookup"><span data-stu-id="0d11e-152">The default locations could be different than what's listed in this article.</span></span>

#### <a name="windows-tempedb-files"></a><span data-ttu-id="0d11e-153">Windows"temp.edb"文件</span><span class="sxs-lookup"><span data-stu-id="0d11e-153">Windows "temp.edb" files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a><span data-ttu-id="0d11e-154">Windows 更新文件或自动更新文件</span><span class="sxs-lookup"><span data-stu-id="0d11e-154">Windows Update files or Automatic Update files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a><span data-ttu-id="0d11e-155">Windows 安全文件</span><span class="sxs-lookup"><span data-stu-id="0d11e-155">Windows Security files</span></span>

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a><span data-ttu-id="0d11e-156">组策略文件</span><span class="sxs-lookup"><span data-stu-id="0d11e-156">Group Policy files</span></span>

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a><span data-ttu-id="0d11e-157">WINS 文件</span><span class="sxs-lookup"><span data-stu-id="0d11e-157">WINS files</span></span>

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a><span data-ttu-id="0d11e-158">文件复制服务 (FRS) 排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-158">File Replication Service (FRS) exclusions</span></span>

- <span data-ttu-id="0d11e-159">文件复制服务中的 (FRS) 工作文件夹。</span><span class="sxs-lookup"><span data-stu-id="0d11e-159">Files in the File Replication Service (FRS) working folder.</span></span> <span data-ttu-id="0d11e-160">FRS 工作文件夹在注册表项中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span><span class="sxs-lookup"><span data-stu-id="0d11e-160">The FRS working folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span></span>

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- <span data-ttu-id="0d11e-161">FRS 数据库日志文件。</span><span class="sxs-lookup"><span data-stu-id="0d11e-161">FRS Database log files.</span></span> <span data-ttu-id="0d11e-162">FRS 数据库日志文件文件夹在注册表项中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span><span class="sxs-lookup"><span data-stu-id="0d11e-162">The FRS Database log file folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span></span>

  - `%windir%\Ntfrs\*\Edb\*.log`

- <span data-ttu-id="0d11e-163">FRS 临时文件夹。</span><span class="sxs-lookup"><span data-stu-id="0d11e-163">The FRS staging folder.</span></span> <span data-ttu-id="0d11e-164">暂存文件夹在注册表项中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span><span class="sxs-lookup"><span data-stu-id="0d11e-164">The staging folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span></span>

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- <span data-ttu-id="0d11e-165">FRS 预安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="0d11e-165">The FRS preinstall folder.</span></span> <span data-ttu-id="0d11e-166">此文件夹由文件夹指定 `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span><span class="sxs-lookup"><span data-stu-id="0d11e-166">This folder is specified by the folder `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span></span>

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- <span data-ttu-id="0d11e-167">分布式文件系统复制 (DFSR) 和工作文件夹。</span><span class="sxs-lookup"><span data-stu-id="0d11e-167">The Distributed File System Replication (DFSR) database and working folders.</span></span> <span data-ttu-id="0d11e-168">这些文件夹由注册表项指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span><span class="sxs-lookup"><span data-stu-id="0d11e-168">These folders are specified by the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span></span>

  > [!NOTE]
  > <span data-ttu-id="0d11e-169">有关自定义位置，请参阅[选择退出自动排除。](#opt-out-of-automatic-exclusions)</span><span class="sxs-lookup"><span data-stu-id="0d11e-169">For custom locations, see [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span></span>

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

#### <a name="process-exclusions"></a><span data-ttu-id="0d11e-170">进程排除</span><span class="sxs-lookup"><span data-stu-id="0d11e-170">Process exclusions</span></span>

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a><span data-ttu-id="0d11e-171">Hyper-V排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-171">Hyper-V exclusions</span></span>

<span data-ttu-id="0d11e-172">下表列出了安装角色角色时自动提供的文件类型排除项、文件夹排除项Hyper-V排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-172">The following table lists the file type exclusions, folder exclusions, and process exclusions that are delivered automatically when you install the Hyper-V role.</span></span>

|<span data-ttu-id="0d11e-173">文件类型排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-173">File type exclusions</span></span> |<span data-ttu-id="0d11e-174">文件夹排除</span><span class="sxs-lookup"><span data-stu-id="0d11e-174">Folder exclusions</span></span>  | <span data-ttu-id="0d11e-175">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="0d11e-175">Process exclusions</span></span> |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a><span data-ttu-id="0d11e-176">SYSVOL 文件</span><span class="sxs-lookup"><span data-stu-id="0d11e-176">SYSVOL files</span></span>

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a><span data-ttu-id="0d11e-177">Active Directory 排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-177">Active Directory exclusions</span></span>

<span data-ttu-id="0d11e-178">本节列出了安装 Active Directory 域服务时自动提供的排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-178">This section lists the exclusions that are delivered automatically when you install Active Directory Domain Services.</span></span>

#### <a name="ntds-database-files"></a><span data-ttu-id="0d11e-179">NTDS 数据库文件</span><span class="sxs-lookup"><span data-stu-id="0d11e-179">NTDS database files</span></span>

<span data-ttu-id="0d11e-180">数据库文件在注册表项中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span><span class="sxs-lookup"><span data-stu-id="0d11e-180">The database files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span></span>

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a><span data-ttu-id="0d11e-181">AD DS 事务日志文件</span><span class="sxs-lookup"><span data-stu-id="0d11e-181">The AD DS transaction log files</span></span>

<span data-ttu-id="0d11e-182">事务日志文件在注册表项中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span><span class="sxs-lookup"><span data-stu-id="0d11e-182">The transaction log files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span></span>

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a><span data-ttu-id="0d11e-183">NTDS 工作文件夹</span><span class="sxs-lookup"><span data-stu-id="0d11e-183">The NTDS working folder</span></span>

<span data-ttu-id="0d11e-184">此文件夹在注册表项中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span><span class="sxs-lookup"><span data-stu-id="0d11e-184">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span></span>

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a><span data-ttu-id="0d11e-185">AD DS 和 AD DS 相关支持文件的进程排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-185">Process exclusions for AD DS and AD DS-related support files</span></span>

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a><span data-ttu-id="0d11e-186">DHCP 服务器排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-186">DHCP Server exclusions</span></span>

<span data-ttu-id="0d11e-187">本节列出了安装 DHCP 服务器角色时自动提供的排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-187">This section lists the exclusions that are delivered automatically when you install the DHCP Server role.</span></span> <span data-ttu-id="0d11e-188">DHCP 服务器文件位置由注册表项中的DatabasePath、DhcpLogFilePath 和 *BackupDatabasePath* 参数指定`HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span><span class="sxs-lookup"><span data-stu-id="0d11e-188">The DHCP Server file locations are specified by the *DatabasePath*, *DhcpLogFilePath*, and *BackupDatabasePath* parameters in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span></span>

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a><span data-ttu-id="0d11e-189">DNS 服务器排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-189">DNS Server exclusions</span></span>

<span data-ttu-id="0d11e-190">本节列出了文件和文件夹排除项，以及安装 DNS 服务器角色时自动提供的进程排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-190">This section lists the file and folder exclusions and the process exclusions that are delivered automatically when you install the DNS Server role.</span></span>

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a><span data-ttu-id="0d11e-191">DNS 服务器角色的文件和文件夹排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-191">File and folder exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a><span data-ttu-id="0d11e-192">DNS 服务器角色的进程排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-192">Process exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a><span data-ttu-id="0d11e-193">文件和存储服务排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-193">File and Storage Services exclusions</span></span>

<span data-ttu-id="0d11e-194">本节列出了安装文件和存储服务角色时自动传递的文件和文件夹排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-194">This section lists the file and folder exclusions that are delivered automatically when you install the File and Storage Services role.</span></span> <span data-ttu-id="0d11e-195">下面列出的排除项不包括群集角色的排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-195">The exclusions listed below do not include exclusions for the Clustering role.</span></span>

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a><span data-ttu-id="0d11e-196">打印服务器排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-196">Print Server exclusions</span></span>

<span data-ttu-id="0d11e-197">本节列出了安装打印服务器角色时自动提供的文件类型排除项、文件夹排除项和进程排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-197">This section lists the file type exclusions, folder exclusions, and the process exclusions that are delivered automatically when you install the Print Server role.</span></span>

#### <a name="file-type-exclusions"></a><span data-ttu-id="0d11e-198">文件类型排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-198">File type exclusions</span></span>

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a><span data-ttu-id="0d11e-199">文件夹排除</span><span class="sxs-lookup"><span data-stu-id="0d11e-199">Folder exclusions</span></span>

<span data-ttu-id="0d11e-200">此文件夹在注册表项中指定 `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span><span class="sxs-lookup"><span data-stu-id="0d11e-200">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span></span>

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a><span data-ttu-id="0d11e-201">进程排除</span><span class="sxs-lookup"><span data-stu-id="0d11e-201">Process exclusions</span></span>

- `spoolsv.exe`

### <a name="web-server-exclusions"></a><span data-ttu-id="0d11e-202">Web 服务器排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-202">Web Server exclusions</span></span>

<span data-ttu-id="0d11e-203">本节列出了安装 Web 服务器角色时自动提供的文件夹排除项和进程排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-203">This section lists the folder exclusions and the process exclusions that are delivered automatically when you install the Web Server role.</span></span>

#### <a name="folder-exclusions"></a><span data-ttu-id="0d11e-204">文件夹排除</span><span class="sxs-lookup"><span data-stu-id="0d11e-204">Folder exclusions</span></span>

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a><span data-ttu-id="0d11e-205">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="0d11e-205">Process exclusions</span></span>

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a><span data-ttu-id="0d11e-206">关闭 Sysvol\Sysvol 文件夹或 SYSVOL_DFSR\Sysvol 文件夹中的文件扫描</span><span class="sxs-lookup"><span data-stu-id="0d11e-206">Turning off scanning of files in the Sysvol\Sysvol folder or the SYSVOL_DFSR\Sysvol folder</span></span>

<span data-ttu-id="0d11e-207">或 文件夹及所有子文件夹的当前位置是副本集根目录的 `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` 文件系统重新分析目标。</span><span class="sxs-lookup"><span data-stu-id="0d11e-207">The current location of the `Sysvol\Sysvol` or `SYSVOL_DFSR\Sysvol` folder and all the subfolders is the file system reparse target of the replica set root.</span></span> <span data-ttu-id="0d11e-208">`Sysvol\Sysvol`和 `SYSVOL_DFSR\Sysvol` 文件夹默认使用以下位置：</span><span class="sxs-lookup"><span data-stu-id="0d11e-208">The `Sysvol\Sysvol` and `SYSVOL_DFSR\Sysvol` folders use the following locations by default:</span></span>

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

<span data-ttu-id="0d11e-209">当前活动的路径由 NETLOGON 共享引用，并且可以通过以下子项中的 `SYSVOL` SysVol 值名称确定： `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span><span class="sxs-lookup"><span data-stu-id="0d11e-209">The path to the currently active `SYSVOL` is referenced by the NETLOGON share and can be determined by the SysVol value name in the following subkey: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span></span>

<span data-ttu-id="0d11e-210">从此文件夹及其所有子文件夹中排除以下文件：</span><span class="sxs-lookup"><span data-stu-id="0d11e-210">Exclude the following files from this folder and all its subfolders:</span></span>

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

### <a name="windows-server-update-services-exclusions"></a><span data-ttu-id="0d11e-211">Windows Server Update Services 排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-211">Windows Server Update Services exclusions</span></span>

<span data-ttu-id="0d11e-212">本部分列出了在 WSUS 角色中安装 Windows Server Update Services (自动) 排除项。</span><span class="sxs-lookup"><span data-stu-id="0d11e-212">This section lists the folder exclusions that are delivered automatically when you install the Windows Server Update Services (WSUS) role.</span></span> <span data-ttu-id="0d11e-213">WSUS 文件夹在注册表项中指定 `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span><span class="sxs-lookup"><span data-stu-id="0d11e-213">The WSUS folder is specified in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span></span>

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a><span data-ttu-id="0d11e-214">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d11e-214">See also</span></span>

- [<span data-ttu-id="0d11e-215">配置并验证 Microsoft Defender 防病毒扫描的排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-215">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0d11e-216">根据文件名、扩展名和文件夹位置配置并验证排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-216">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0d11e-217">配置并验证进程打开的文件的排除项</span><span class="sxs-lookup"><span data-stu-id="0d11e-217">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0d11e-218">定义排除时要避免的常见错误</span><span class="sxs-lookup"><span data-stu-id="0d11e-218">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0d11e-219">自定义、启动和查看 Microsoft Defender 防病毒扫描和修正的结果</span><span class="sxs-lookup"><span data-stu-id="0d11e-219">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0d11e-220">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="0d11e-220">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)