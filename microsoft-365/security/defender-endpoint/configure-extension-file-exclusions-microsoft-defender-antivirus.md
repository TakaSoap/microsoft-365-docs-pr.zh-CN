---
title: 根据扩展名、名称或位置配置和验证排除项
description: 根据文件扩展名、文件名或位置，从 Microsoft Defender 防病毒扫描中排除文件。
keywords: 排除项， 文件， 扩展名， 文件类型， 文件夹名称， 文件名， 扫描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 338dc249bcd4e092f5a2be39e3d045d094ed957a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765211"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a><span data-ttu-id="02036-104">根据文件扩展名和文件夹位置配置和验证排除项</span><span class="sxs-lookup"><span data-stu-id="02036-104">Configure and validate exclusions based on file extension and folder location</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="02036-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="02036-105">**Applies to:**</span></span>

- [<span data-ttu-id="02036-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="02036-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="02036-107">Microsoft Defender 防病毒排除项不适用于其他 Microsoft Defender for Endpoint 功能，包括终结点检测和响应[ (EDR) 、](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)攻击面减少[ (ASR) ](/microsoft-365/security/defender-endpoint/attack-surface-reduction)规则和受控文件夹访问权限。 [](/microsoft-365/security/defender-endpoint/controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="02036-107">Microsoft Defender Antivirus exclusions don't apply to other Microsoft Defender for Endpoint capabilities, including [endpoint detection and response (EDR)](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response), [attack surface reduction (ASR) rules](/microsoft-365/security/defender-endpoint/attack-surface-reduction), and [controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span> <span data-ttu-id="02036-108">使用本文中所述的方法排除的文件仍可以触发 EDR 警报和其他检测。</span><span class="sxs-lookup"><span data-stu-id="02036-108">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span> <span data-ttu-id="02036-109">若要广泛排除文件，请将它们添加到 Microsoft Defender for Endpoint [自定义指示器](/microsoft-365/security/defender-endpoint/manage-indicators)。</span><span class="sxs-lookup"><span data-stu-id="02036-109">To exclude files broadly, add them to the Microsoft Defender for Endpoint [custom indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

## <a name="exclusion-lists"></a><span data-ttu-id="02036-110">排除列表</span><span class="sxs-lookup"><span data-stu-id="02036-110">Exclusion lists</span></span>

<span data-ttu-id="02036-111">可以通过修改排除列表从 Microsoft Defender 防病毒扫描中排除某些文件。</span><span class="sxs-lookup"><span data-stu-id="02036-111">You can exclude certain files from Microsoft Defender Antivirus scans by modifying exclusion lists.</span></span> <span data-ttu-id="02036-112">**通常，你无需应用排除项**。</span><span class="sxs-lookup"><span data-stu-id="02036-112">**Generally, you shouldn't need to apply exclusions**.</span></span> <span data-ttu-id="02036-113">Microsoft Defender 防病毒包括许多基于已知操作系统行为和典型管理文件（例如用于企业管理、数据库管理和其他企业方案和情况的文件）的自动排除项。</span><span class="sxs-lookup"><span data-stu-id="02036-113">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>

> [!NOTE]
> <span data-ttu-id="02036-114">排除项也适用于可能不需要 (PUA) 检测。</span><span class="sxs-lookup"><span data-stu-id="02036-114">Exclusions apply to Potentially Unwanted Apps (PUA) detections as well.</span></span>

> [!NOTE]
> <span data-ttu-id="02036-115">自动排除项仅适用于 Windows Server 2016 及以上版本。</span><span class="sxs-lookup"><span data-stu-id="02036-115">Automatic exclusions apply only to Windows Server 2016 and above.</span></span> <span data-ttu-id="02036-116">这些排除项在 Windows 安全应用和 PowerShell 中不可见。</span><span class="sxs-lookup"><span data-stu-id="02036-116">These exclusions are not visible in the Windows Security app and in PowerShell.</span></span>

<span data-ttu-id="02036-117">本文介绍如何配置文件和文件夹的排除列表。</span><span class="sxs-lookup"><span data-stu-id="02036-117">This article  describes how to configure exclusion lists for the files and folders.</span></span> <span data-ttu-id="02036-118">请参阅 [定义排除列表之前](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 定义排除项的建议。</span><span class="sxs-lookup"><span data-stu-id="02036-118">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

| <span data-ttu-id="02036-119">排除</span><span class="sxs-lookup"><span data-stu-id="02036-119">Exclusion</span></span> | <span data-ttu-id="02036-120">示例</span><span class="sxs-lookup"><span data-stu-id="02036-120">Examples</span></span> | <span data-ttu-id="02036-121">排除列表</span><span class="sxs-lookup"><span data-stu-id="02036-121">Exclusion list</span></span> |
|:---|:---|:---|
|<span data-ttu-id="02036-122">具有特定扩展名的任何文件</span><span class="sxs-lookup"><span data-stu-id="02036-122">Any file with a specific extension</span></span> | <span data-ttu-id="02036-123">计算机上任意位置具有指定扩展名的所有文件。</span><span class="sxs-lookup"><span data-stu-id="02036-123">All files with the specified extension, anywhere on the machine.</span></span> <p> <span data-ttu-id="02036-124">有效语法： `.test` 和 `test`</span><span class="sxs-lookup"><span data-stu-id="02036-124">Valid syntax: `.test` and `test`</span></span>  | <span data-ttu-id="02036-125">扩展排除项</span><span class="sxs-lookup"><span data-stu-id="02036-125">Extension exclusions</span></span> |
|<span data-ttu-id="02036-126">特定文件夹下的任何文件</span><span class="sxs-lookup"><span data-stu-id="02036-126">Any file under a specific folder</span></span> | <span data-ttu-id="02036-127">文件夹下的所有 `c:\test\sample` 文件</span><span class="sxs-lookup"><span data-stu-id="02036-127">All files under the `c:\test\sample` folder</span></span> | <span data-ttu-id="02036-128">文件和文件夹排除项</span><span class="sxs-lookup"><span data-stu-id="02036-128">File and folder exclusions</span></span> |
| <span data-ttu-id="02036-129">特定文件夹中的特定文件</span><span class="sxs-lookup"><span data-stu-id="02036-129">A specific file in a specific folder</span></span> | <span data-ttu-id="02036-130">仅 `c:\sample\sample.test` 文件</span><span class="sxs-lookup"><span data-stu-id="02036-130">The file `c:\sample\sample.test` only</span></span> | <span data-ttu-id="02036-131">文件和文件夹排除项</span><span class="sxs-lookup"><span data-stu-id="02036-131">File and folder exclusions</span></span> |
| <span data-ttu-id="02036-132">特定过程</span><span class="sxs-lookup"><span data-stu-id="02036-132">A specific process</span></span> | <span data-ttu-id="02036-133">可执行文件 `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="02036-133">The executable file `c:\test\process.exe`</span></span> | <span data-ttu-id="02036-134">文件和文件夹排除项</span><span class="sxs-lookup"><span data-stu-id="02036-134">File and folder exclusions</span></span> |

<span data-ttu-id="02036-135">排除列表具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="02036-135">Exclusion lists have the following characteristics:</span></span>

- <span data-ttu-id="02036-136">文件夹排除项适用于该文件夹下的所有文件和文件夹，除非子文件夹是重新分析点。</span><span class="sxs-lookup"><span data-stu-id="02036-136">Folder exclusions apply to all files and folders under that folder, unless the subfolder is a reparse point.</span></span> <span data-ttu-id="02036-137">必须单独排除重新分析点子文件夹。</span><span class="sxs-lookup"><span data-stu-id="02036-137">Reparse point subfolders must be excluded separately.</span></span>
- <span data-ttu-id="02036-138">如果未定义路径或文件夹，则文件扩展名将应用于具有定义扩展名的任何文件名。</span><span class="sxs-lookup"><span data-stu-id="02036-138">File extensions apply to any file name with the defined extension if a path or folder is not defined.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="02036-139">使用通配符（如星号 () \* 将改变排除规则的解释方式。</span><span class="sxs-lookup"><span data-stu-id="02036-139">Using wildcards such as the asterisk (\*) will alter how the exclusion rules are interpreted.</span></span> <span data-ttu-id="02036-140">有关 [通配符如何工作的](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 重要信息，请参阅在文件名和文件夹路径或扩展名排除列表中使用通配符部分。</span><span class="sxs-lookup"><span data-stu-id="02036-140">See the [Use wildcards in the file name and folder path or extension exclusion lists](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) section for important information about how wildcards work.</span></span>
> - <span data-ttu-id="02036-141">不能排除映射的网络驱动器。</span><span class="sxs-lookup"><span data-stu-id="02036-141">You cannot exclude mapped network drives.</span></span> <span data-ttu-id="02036-142">必须指定实际网络路径。</span><span class="sxs-lookup"><span data-stu-id="02036-142">You must specify the actual network path.</span></span>
> - <span data-ttu-id="02036-143">不会包含重新分析在 Microsoft Defender 防病毒服务启动后创建且已添加到排除列表的文件夹。</span><span class="sxs-lookup"><span data-stu-id="02036-143">Folders that are reparse points that are created after the Microsoft Defender Antivirus service starts and that have been added to the exclusion list will not be included.</span></span> <span data-ttu-id="02036-144">必须通过重新启动 Windows (重新启动服务) ，才能将新的重新分析点识别为有效的排除目标。</span><span class="sxs-lookup"><span data-stu-id="02036-144">You must restart the service (by restarting Windows) for new reparse points to be recognized as a valid exclusion target.</span></span>

<span data-ttu-id="02036-145">若要排除特定进程打开的文件，请参阅配置和验证进程 [打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="02036-145">To exclude files opened by a specific process, see [Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="02036-146">排除项适用于 [计划扫描、](scheduled-catch-up-scans-microsoft-defender-antivirus.md)按需 [扫描](run-scan-microsoft-defender-antivirus.md)和 [实时保护](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="02036-146">The exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02036-147">使用组策略进行排除列表 **更改将在** Windows 安全应用 [的列表中显示](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="02036-147">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
> <span data-ttu-id="02036-148">在 Windows 安全应用中所做的更改 **不会显示在** 组策略列表中。</span><span class="sxs-lookup"><span data-stu-id="02036-148">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="02036-149">默认情况下，具有管理员权限的用户对 (列表进行的本地更改（包括使用 PowerShell 和 WMI) 所做的更改）将与 (定义的列表合并，并按组策略、Configuration Manager 或 Intune 部署) 。</span><span class="sxs-lookup"><span data-stu-id="02036-149">By default, local changes made to the lists (by users with administrator privileges, including changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="02036-150">存在冲突时，组策略列表优先。</span><span class="sxs-lookup"><span data-stu-id="02036-150">The Group Policy lists take precedence when there are conflicts.</span></span>

<span data-ttu-id="02036-151">您可以 [配置本地和](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) 全局定义的排除列表的合并方式，以允许本地更改覆盖托管部署设置。</span><span class="sxs-lookup"><span data-stu-id="02036-151">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a><span data-ttu-id="02036-152">根据文件夹名称或文件扩展名配置排除项列表</span><span class="sxs-lookup"><span data-stu-id="02036-152">Configure the list of exclusions based on folder name or file extension</span></span>

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="02036-153">使用 Intune 配置文件名、文件夹或文件扩展名排除项</span><span class="sxs-lookup"><span data-stu-id="02036-153">Use Intune to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="02036-154">另请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="02036-154">See the following articles:</span></span>
- [<span data-ttu-id="02036-155">在 Microsoft Intune 中配置设备限制设置</span><span class="sxs-lookup"><span data-stu-id="02036-155">Configure device restriction settings in Microsoft Intune</span></span>](/intune/device-restrictions-configure)
- [<span data-ttu-id="02036-156">Intune 中 Windows 10 的 Microsoft Defender 防病毒设备限制设置</span><span class="sxs-lookup"><span data-stu-id="02036-156">Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune</span></span>](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="02036-157">使用 Configuration Manager 配置文件名、文件夹或文件扩展名排除项</span><span class="sxs-lookup"><span data-stu-id="02036-157">Use Configuration Manager to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="02036-158">请参阅 [如何创建和部署反恶意软件策略：](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) 排除设置，了解有关配置 Microsoft Endpoint Manager (当前分支) 。</span><span class="sxs-lookup"><span data-stu-id="02036-158">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a><span data-ttu-id="02036-159">使用组策略配置文件夹或文件扩展名排除项</span><span class="sxs-lookup"><span data-stu-id="02036-159">Use Group Policy to configure folder or file extension exclusions</span></span>

>[!NOTE]
><span data-ttu-id="02036-160">如果指定文件的完全限定路径，则仅排除该文件。</span><span class="sxs-lookup"><span data-stu-id="02036-160">If you specify a fully qualified path to a file, then only that file is excluded.</span></span> <span data-ttu-id="02036-161">如果在排除中定义了文件夹，则排除该文件夹下的所有文件和子目录。</span><span class="sxs-lookup"><span data-stu-id="02036-161">If a folder is defined in the exclusion, then all files and subdirectories under that folder are excluded.</span></span>

1. <span data-ttu-id="02036-162">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="02036-162">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="02036-163">在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后选择 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="02036-163">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="02036-164">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **排除项**。</span><span class="sxs-lookup"><span data-stu-id="02036-164">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>

4. <span data-ttu-id="02036-165">打开 **"路径排除项** "设置进行编辑，并添加排除项。</span><span class="sxs-lookup"><span data-stu-id="02036-165">Open the **Path Exclusions** setting for editing, and add your exclusions.</span></span>

    1. <span data-ttu-id="02036-166">将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="02036-166">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="02036-167">在"选项 **"部分** 下，单击"显示 **"。**</span><span class="sxs-lookup"><span data-stu-id="02036-167">Under the **Options** section, click **Show**.</span></span>
    1. <span data-ttu-id="02036-168">在"值名称"列下，在其自己的 **行中指定每个** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="02036-168">Specify each folder on its own line under the **Value name** column.</span></span>
    1. <span data-ttu-id="02036-169">如果要指定文件，请确保输入该文件的完全限定路径，包括驱动器号、文件夹路径、文件名和扩展名。</span><span class="sxs-lookup"><span data-stu-id="02036-169">If you are specifying a file, ensure that you enter a fully qualified path to the file, including the drive letter, folder path, file name, and extension.</span></span> <span data-ttu-id="02036-170">在 **"值"\*\*\*\*列中输入** 0。</span><span class="sxs-lookup"><span data-stu-id="02036-170">Enter **0** in the **Value** column.</span></span>

5. <span data-ttu-id="02036-171">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="02036-171">Choose **OK**.</span></span>

6. <span data-ttu-id="02036-172">打开 **扩展排除** 项设置进行编辑并添加排除项。</span><span class="sxs-lookup"><span data-stu-id="02036-172">Open the **Extension Exclusions** setting for editing and add your exclusions.</span></span>

    1. <span data-ttu-id="02036-173">将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="02036-173">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="02036-174">在"**选项"** 部分下，选择"显示 **"。**</span><span class="sxs-lookup"><span data-stu-id="02036-174">Under the **Options** section, select **Show**.</span></span>
    1. <span data-ttu-id="02036-175">在"值名称"列下，在其自己的 **行中输入每个文件** 扩展名。</span><span class="sxs-lookup"><span data-stu-id="02036-175">Enter each file extension on its own line under the **Value name** column.</span></span>  <span data-ttu-id="02036-176">在 **"值"\*\*\*\*列中输入** 0。</span><span class="sxs-lookup"><span data-stu-id="02036-176">Enter **0** in the **Value** column.</span></span>

7. <span data-ttu-id="02036-177">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="02036-177">Choose **OK**.</span></span>

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="02036-178">使用 PowerShell cmdlet 配置文件名、文件夹或文件扩展名排除项</span><span class="sxs-lookup"><span data-stu-id="02036-178">Use PowerShell cmdlets to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="02036-179">使用 PowerShell 添加或删除基于扩展名、位置或文件名的文件排除项需要结合使用三个 cmdlet 和相应的排除列表参数。</span><span class="sxs-lookup"><span data-stu-id="02036-179">Using PowerShell to add or remove exclusions for files based on the extension, location, or file name requires using a combination of three cmdlets and the appropriate exclusion list parameter.</span></span> <span data-ttu-id="02036-180">cmdlet 全部在 Defender [模块中](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="02036-180">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="02036-181">cmdlet 的格式如下：</span><span class="sxs-lookup"><span data-stu-id="02036-181">The format for the cmdlets is as follows:</span></span>

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

<span data-ttu-id="02036-182">允许将以下内容作为 `<cmdlet>` ：</span><span class="sxs-lookup"><span data-stu-id="02036-182">The following are allowed as the `<cmdlet>`:</span></span>

| <span data-ttu-id="02036-183">配置操作</span><span class="sxs-lookup"><span data-stu-id="02036-183">Configuration action</span></span> | <span data-ttu-id="02036-184">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="02036-184">PowerShell cmdlet</span></span> |
|:---|:---|
|<span data-ttu-id="02036-185">创建或覆盖列表</span><span class="sxs-lookup"><span data-stu-id="02036-185">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="02036-186">添加到列表</span><span class="sxs-lookup"><span data-stu-id="02036-186">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="02036-187">从列表中删除项目</span><span class="sxs-lookup"><span data-stu-id="02036-187">Remove item from the list</span></span> | `Remove-MpPreference` |

<span data-ttu-id="02036-188">允许将以下内容作为 `<exclusion list>` ：</span><span class="sxs-lookup"><span data-stu-id="02036-188">The following are allowed as the `<exclusion list>`:</span></span>

| <span data-ttu-id="02036-189">排除类型</span><span class="sxs-lookup"><span data-stu-id="02036-189">Exclusion type</span></span> | <span data-ttu-id="02036-190">PowerShell 参数</span><span class="sxs-lookup"><span data-stu-id="02036-190">PowerShell parameter</span></span> |
|:---|:---|
| <span data-ttu-id="02036-191">具有指定文件扩展名的所有文件</span><span class="sxs-lookup"><span data-stu-id="02036-191">All files with a specified file extension</span></span> | `-ExclusionExtension` |
| <span data-ttu-id="02036-192">文件夹下的所有文件 (包括子目录中的文件) 或特定文件</span><span class="sxs-lookup"><span data-stu-id="02036-192">All files under a folder (including files in subdirectories), or a specific file</span></span> | `-ExclusionPath` |

> [!IMPORTANT]
> <span data-ttu-id="02036-193">如果已使用 或 创建列表， `Set-MpPreference` `Add-MpPreference` 则再次使用 `Set-MpPreference` cmdlet 将覆盖现有列表。</span><span class="sxs-lookup"><span data-stu-id="02036-193">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="02036-194">例如，以下代码段将导致 Microsoft Defender 防病毒扫描排除文件扩展 `.test` 名的任何文件：</span><span class="sxs-lookup"><span data-stu-id="02036-194">For example, the following code snippet would cause Microsoft Defender Antivirus scans to exclude any file with the `.test` file extension:</span></span>

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

<span data-ttu-id="02036-195">有关详细信息，请参阅使用[PowerShell cmdlet 配置](use-powershell-cmdlets-microsoft-defender-antivirus.md)和运行 Microsoft Defender 防病毒和[Defender cmdlet。](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="02036-195">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="02036-196">使用 Windows Management Instruction (WMI) 配置文件名、文件夹或文件扩展名排除项</span><span class="sxs-lookup"><span data-stu-id="02036-196">Use Windows Management Instruction (WMI) to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="02036-197">对 [**以下属性** 使用 **MSFT_MpPreference** 类的 **Set、Add**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))和 Remove 方法：</span><span class="sxs-lookup"><span data-stu-id="02036-197">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionExtension
ExclusionPath
```

<span data-ttu-id="02036-198">Set、Add和 **Remove** 的使用类似于 PowerShell 中的对应类 `Set-MpPreference` ：、、 和 `Add-MpPreference` `Remove-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="02036-198">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="02036-199">有关详细信息，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="02036-199">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="02036-200">使用 Windows 安全应用配置文件名、文件夹或文件扩展名排除项</span><span class="sxs-lookup"><span data-stu-id="02036-200">Use the Windows Security app to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="02036-201">有关 [说明，请参阅在 Windows 安全应用中添加](microsoft-defender-security-center-antivirus.md) 排除项。</span><span class="sxs-lookup"><span data-stu-id="02036-201">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="02036-202">在文件名和文件夹路径或扩展名排除列表中使用通配符</span><span class="sxs-lookup"><span data-stu-id="02036-202">Use wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="02036-203">在文件名或文件夹路径排除列表中定义项目时 (星号、问号或环境变量（如 `*` `?` `%ALLUSERSPROFILE%`) ）用作通配符。</span><span class="sxs-lookup"><span data-stu-id="02036-203">You can use the asterisk `*`, question mark `?`, or environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the file name or folder path exclusion list.</span></span> <span data-ttu-id="02036-204">解释这些通配符的方式与其他应用和语言中常用的用法不同。</span><span class="sxs-lookup"><span data-stu-id="02036-204">The way in which these wildcards are interpreted differs from their usual usage in other apps and languages.</span></span> <span data-ttu-id="02036-205">请务必阅读本节以了解其特定限制。</span><span class="sxs-lookup"><span data-stu-id="02036-205">Make sure to read this section to understand their specific limitations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02036-206">这些通配符存在一些关键限制和使用方案：</span><span class="sxs-lookup"><span data-stu-id="02036-206">There are key limitations and usage scenarios for these wildcards:</span></span>
> - <span data-ttu-id="02036-207">环境变量的使用仅限于计算机变量和那些适用于作为 NT AUTHORITY\SYSTEM 帐户运行的进程。</span><span class="sxs-lookup"><span data-stu-id="02036-207">Environment variable usage is limited to machine variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span>
> - <span data-ttu-id="02036-208">不能使用通配符来表示驱动器号。</span><span class="sxs-lookup"><span data-stu-id="02036-208">You cannot use a wildcard in place of a drive letter.</span></span>
> - <span data-ttu-id="02036-209">文件夹排除中的 `*` 星号代表单个文件夹。</span><span class="sxs-lookup"><span data-stu-id="02036-209">An asterisk `*` in a folder exclusion stands in place for a single folder.</span></span> <span data-ttu-id="02036-210">使用多个实例来 `\*\` 指示具有未指定名称的多个嵌套文件夹。</span><span class="sxs-lookup"><span data-stu-id="02036-210">Use multiple instances of `\*\` to indicate multiple nested folders with unspecified names.</span></span>

<span data-ttu-id="02036-211">下表介绍了如何使用通配符，并提供了一些示例。</span><span class="sxs-lookup"><span data-stu-id="02036-211">The following table describes how the wildcards can be used and provides some examples.</span></span>


|<span data-ttu-id="02036-212">通配符</span><span class="sxs-lookup"><span data-stu-id="02036-212">Wildcard</span></span>  |<span data-ttu-id="02036-213">示例</span><span class="sxs-lookup"><span data-stu-id="02036-213">Examples</span></span>  |
|:---------|:---------|
|<span data-ttu-id="02036-214">`*` (星号) </span><span class="sxs-lookup"><span data-stu-id="02036-214">`*` (asterisk)</span></span> <p> <span data-ttu-id="02036-215">在 **文件名和文件** 扩展名包含中，星号将替换任意数目的字符，并且仅适用于参数中定义的最后一个文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="02036-215">In **file name and file extension inclusions**, the asterisk replaces any number of characters, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="02036-216">在 **文件夹排除** 中，星号将替换单个文件夹。</span><span class="sxs-lookup"><span data-stu-id="02036-216">In **folder exclusions**, the asterisk replaces a single folder.</span></span> <span data-ttu-id="02036-217">将 multiple `*` 与文件夹斜杠 `\` 一同使用，以指示多个嵌套文件夹。</span><span class="sxs-lookup"><span data-stu-id="02036-217">Use multiple `*` with folder slashes `\` to indicate multiple nested folders.</span></span> <span data-ttu-id="02036-218">匹配通配符和命名文件夹的数量后，还将包含所有子文件夹。</span><span class="sxs-lookup"><span data-stu-id="02036-218">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   | <span data-ttu-id="02036-219">`C:\MyData\*.txt` 包括 `C:\MyData\notes.txt`</span><span class="sxs-lookup"><span data-stu-id="02036-219">`C:\MyData\*.txt` includes `C:\MyData\notes.txt`</span></span> <p> <span data-ttu-id="02036-220">`C:\somepath\*\Data` 包括 及其 `C:\somepath\Archives\Data` 子文件夹及其 `C:\somepath\Authorized\Data` 子文件夹内的任何文件</span><span class="sxs-lookup"><span data-stu-id="02036-220">`C:\somepath\*\Data` includes any file in `C:\somepath\Archives\Data` and its subfolders, and `C:\somepath\Authorized\Data` and its subfolders</span></span> <p> <span data-ttu-id="02036-221">`C:\Serv\*\*\Backup` 包括 及其 `C:\Serv\Primary\Denied\Backup` 子文件夹及其 `C:\Serv\Secondary\Allowed\Backup` 子文件夹内的任何文件</span><span class="sxs-lookup"><span data-stu-id="02036-221">`C:\Serv\*\*\Backup` includes any file in `C:\Serv\Primary\Denied\Backup` and its subfolders and `C:\Serv\Secondary\Allowed\Backup` and its subfolders</span></span>     |
|<span data-ttu-id="02036-222">`?` (问号) </span><span class="sxs-lookup"><span data-stu-id="02036-222">`?` (question mark)</span></span>  <p> <span data-ttu-id="02036-223">在 **文件名和文件扩展名包含** 中，问号将替换单个字符，并且仅适用于参数中定义的最后一个文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="02036-223">In **file name and file extension inclusions**, the question mark replaces a single character, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="02036-224">在 **文件夹排除** 中，问号替换文件夹名称中的单个字符。</span><span class="sxs-lookup"><span data-stu-id="02036-224">In **folder exclusions**, the question mark replaces a single character in a folder name.</span></span> <span data-ttu-id="02036-225">匹配通配符和命名文件夹的数量后，还将包含所有子文件夹。</span><span class="sxs-lookup"><span data-stu-id="02036-225">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   |<span data-ttu-id="02036-226">`C:\MyData\my?.zip` 包括 `C:\MyData\my1.zip`</span><span class="sxs-lookup"><span data-stu-id="02036-226">`C:\MyData\my?.zip` includes `C:\MyData\my1.zip`</span></span> <p> <span data-ttu-id="02036-227">`C:\somepath\?\Data` 包括 及其 `C:\somepath\P\Data` 子文件夹内的任何文件</span><span class="sxs-lookup"><span data-stu-id="02036-227">`C:\somepath\?\Data` includes any file in `C:\somepath\P\Data` and its subfolders</span></span>  <p> <span data-ttu-id="02036-228">`C:\somepath\test0?\Data` 将包含 及其 `C:\somepath\test01\Data` 子文件夹内的任何文件</span><span class="sxs-lookup"><span data-stu-id="02036-228">`C:\somepath\test0?\Data` would include any file in `C:\somepath\test01\Data` and its subfolders</span></span>          |
|<span data-ttu-id="02036-229">环境变量</span><span class="sxs-lookup"><span data-stu-id="02036-229">Environment variables</span></span> <p> <span data-ttu-id="02036-230">在计算排除时，定义的变量将填充为路径。</span><span class="sxs-lookup"><span data-stu-id="02036-230">The defined variable is populated as a path when the exclusion is evaluated.</span></span>          |<span data-ttu-id="02036-231">`%ALLUSERSPROFILE%\CustomLogFiles` 将包括 `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span><span class="sxs-lookup"><span data-stu-id="02036-231">`%ALLUSERSPROFILE%\CustomLogFiles` would include `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span></span>         |
        

> [!IMPORTANT]
> <span data-ttu-id="02036-232">如果将文件排除参数与文件夹排除参数混合，则规则将在匹配文件夹中的 file 参数匹配时停止，并且不会在任何子文件夹中查找文件匹配项。</span><span class="sxs-lookup"><span data-stu-id="02036-232">If you mix a file exclusion argument with a folder exclusion argument, the rules will stop at the file argument match in the matched folder, and will not look for file matches in any subfolders.</span></span>
> <span data-ttu-id="02036-233">例如，可以使用规则参数 排除文件夹中以"date"开始的所有 `c:\data\final\marked` `c:\data\review\marked` 文件 `c:\data\*\marked\date*` 。</span><span class="sxs-lookup"><span data-stu-id="02036-233">For example, you can exclude all files that start with "date" in the folders `c:\data\final\marked` and `c:\data\review\marked` by using the rule argument `c:\data\*\marked\date*`.</span></span>
> <span data-ttu-id="02036-234">但是，此参数与 或 下的子文件夹内的任何文件 `c:\data\final\marked` 都不匹配 `c:\data\review\marked` 。</span><span class="sxs-lookup"><span data-stu-id="02036-234">This argument, however, will not match any files in subfolders under `c:\data\final\marked` or `c:\data\review\marked`.</span></span>

<a id="review"></a>

### <a name="system-environment-variables"></a><span data-ttu-id="02036-235">系统环境变量</span><span class="sxs-lookup"><span data-stu-id="02036-235">System environment variables</span></span>

<span data-ttu-id="02036-236">下表列出并描述了系统帐户环境变量。</span><span class="sxs-lookup"><span data-stu-id="02036-236">The following table lists and describes the system account environment variables.</span></span> 

| <span data-ttu-id="02036-237">此系统环境变量...</span><span class="sxs-lookup"><span data-stu-id="02036-237">This system environment variable...</span></span> | <span data-ttu-id="02036-238">重定向到此</span><span class="sxs-lookup"><span data-stu-id="02036-238">Redirects to this</span></span> |
|:--|:--|
| `%APPDATA%`| `C:\Users\UserName.DomainName\AppData\Roaming` |
| `%APPDATA%\Microsoft\Internet Explorer\Quick Launch` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch` |
| `%APPDATA%\Microsoft\Windows\Start Menu` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu` |
| `%APPDATA%\Microsoft\Windows\Start Menu\Programs` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs` |
| `%LOCALAPPDATA%` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%ProgramData%` | `C:\ProgramData` |
| `%ProgramFiles%` | `C:\Program Files` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles%\Windows Sidebar\Gadgets` | `C:\Program Files\Windows Sidebar\Gadgets` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles(x86)%` | `C:\Program Files (x86)` |
| `%ProgramFiles(x86)%\Common Files` | `C:\Program Files (x86)\Common Files` |
| `%SystemDrive%` | `C:` |
| `%SystemDrive%\Program Files` | `C:\Program Files` |
| `%SystemDrive%\Program Files (x86)` | `C:\Program Files (x86)` |
| `%SystemDrive%\Users` | `C:\Users` |
| `%SystemDrive%\Users\Public` | `C:\Users\Public` |
| `%SystemRoot%` | `C:\Windows` |
| `%windir%` | `C:\Windows` |
| `%windir%\Fonts` | `C:\Windows\Fonts` |
| `%windir%\Resources` | `C:\Windows\Resources` |
| `%windir%\resources\0409` | `C:\Windows\resources\0409` |
| `%windir%\system32` | `C:\Windows\System32` |
| `%ALLUSERSPROFILE%` | `C:\ProgramData` |
| `%ALLUSERSPROFILE%\Application Data` | `C:\ProgramData\Application Data` |
| `%ALLUSERSPROFILE%\Documents` | `C:\ProgramData\Documents` |
| `%ALLUSERSPROFILE%\Documents\My Music\Sample Music` | `C:\ProgramData\Documents\My Music\Sample Music` |
| `%ALLUSERSPROFILE%\Documents\My Music` | `C:\ProgramData\Documents\My Music` |
| `%ALLUSERSPROFILE%\Documents\My Pictures` | `C:\ProgramData\Documents\My Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures` | `C:\ProgramData\Documents\My Pictures\Sample Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Videos` | `C:\ProgramData\Documents\My Videos` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore` | `C:\ProgramData\Microsoft\Windows\DeviceMetadataStore` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer` | `C:\ProgramData\Microsoft\Windows\GameExplorer` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones` | `C:\ProgramData\Microsoft\Windows\Ringtones` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu` | `C:\ProgramData\Microsoft\Windows\Start Menu` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Templates` | `C:\ProgramData\Microsoft\Windows\Templates` |
| `%ALLUSERSPROFILE%\Start Menu` | `C:\ProgramData\Start Menu` |
| `%ALLUSERSPROFILE%\Start Menu\Programs` | <span data-ttu-id="02036-239">C：\ProgramData\Start Menu\Programs</span><span class="sxs-lookup"><span data-stu-id="02036-239">C:\ProgramData\Start Menu\Programs</span></span> |
| `%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Start Menu\Programs\Administrative Tools` | 
| `%ALLUSERSPROFILE%\Templates` | `C:\ProgramData\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\History` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History` |
| `%PUBLIC%` | `C:\Users\Public` |
| `%PUBLIC%\AccountPictures` | `C:\Users\Public\AccountPictures` |
| `%PUBLIC%\Desktop` | `C:\Users\Public\Desktop` |
| `%PUBLIC%\Documents` | `C:\Users\Public\Documents` |
| `%PUBLIC%\Downloads` | `C:\Users\Public\Downloads` |
| `%PUBLIC%\Music\Sample Music` | `C:\Users\Public\Music\Sample Music` |
| `%PUBLIC%\Music\Sample Playlists` | `C:\Users\Public\Music\Sample Playlists` |
| `%PUBLIC%\Pictures\Sample Pictures` | `C:\Users\Public\Pictures\Sample Pictures` |
| `%PUBLIC%\RecordedTV.library-ms` | `C:\Users\Public\RecordedTV.library-ms` |
| `%PUBLIC%\Videos` | `C:\Users\Public\Videos` |
| `%PUBLIC%\Videos\Sample Videos` | `C:\Users\Public\Videos\Sample Videos` | 
| `%USERPROFILE%` | `C:\Windows\System32\config\systemprofile` |
| `%USERPROFILE%\AppData\Local` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%USERPROFILE%\AppData\LocalLow` | `C:\Windows\System32\config\systemprofile\AppData\LocalLow` |
| `%USERPROFILE%\AppData\Roaming` | `C:\Windows\System32\config\systemprofile\AppData\Roaming` |


## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="02036-240">查看排除项列表</span><span class="sxs-lookup"><span data-stu-id="02036-240">Review the list of exclusions</span></span>

<span data-ttu-id="02036-241">您可以使用以下方法之一检索排除列表中的项：</span><span class="sxs-lookup"><span data-stu-id="02036-241">You can retrieve the items in the exclusion list using one of the following methods:</span></span>
- [<span data-ttu-id="02036-242">Intune</span><span class="sxs-lookup"><span data-stu-id="02036-242">Intune</span></span>](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [<span data-ttu-id="02036-243">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="02036-243">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- <span data-ttu-id="02036-244">MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="02036-244">MpCmdRun</span></span>
- <span data-ttu-id="02036-245">PowerShell</span><span class="sxs-lookup"><span data-stu-id="02036-245">PowerShell</span></span>
- [<span data-ttu-id="02036-246">Windows 安全应用</span><span class="sxs-lookup"><span data-stu-id="02036-246">Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)

>[!IMPORTANT]
><span data-ttu-id="02036-247">使用组策略进行排除列表 **更改将在** Windows 安全应用 [的列表中显示](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="02036-247">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
>
><span data-ttu-id="02036-248">在 Windows 安全应用中所做的更改 **不会显示在** 组策略列表中。</span><span class="sxs-lookup"><span data-stu-id="02036-248">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="02036-249">如果使用 PowerShell，可以通过两种方式检索列表：</span><span class="sxs-lookup"><span data-stu-id="02036-249">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="02036-250">检索所有 Microsoft Defender 防病毒首选项的状态。</span><span class="sxs-lookup"><span data-stu-id="02036-250">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="02036-251">每个列表显示在单独的行上，但每个列表中的项组合到同一行中。</span><span class="sxs-lookup"><span data-stu-id="02036-251">Each list is displayed on separate lines, but the items within each list are combined into the same line.</span></span>
- <span data-ttu-id="02036-252">将所有首选项的状态写入变量，并使用该变量仅调用您感兴趣的特定列表。</span><span class="sxs-lookup"><span data-stu-id="02036-252">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="02036-253">每次使用 `Add-MpPreference` 都写入新行。</span><span class="sxs-lookup"><span data-stu-id="02036-253">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="02036-254">使用 MpCmdRun 验证排除列表</span><span class="sxs-lookup"><span data-stu-id="02036-254">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="02036-255">若要使用专用命令行工具检查排除 [mpcmdrun.exe，请使用 ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)以下命令：</span><span class="sxs-lookup"><span data-stu-id="02036-255">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.1812.3 (Where 4.18.1812.3 is this month's MDAV "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

>[!NOTE]
><span data-ttu-id="02036-256">检查 MpCmdRun 的排除项需要 Microsoft Defender 防病毒 CAMP 版本 4.18.1812.3 (2018 年 12 月) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="02036-256">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="02036-257">使用 PowerShell 查看所有其他 Microsoft Defender 防病毒首选项旁的排除项列表</span><span class="sxs-lookup"><span data-stu-id="02036-257">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="02036-258">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="02036-258">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="02036-259">在下面的示例中，突出显示了列表中包含的 `ExclusionExtension` 项：</span><span class="sxs-lookup"><span data-stu-id="02036-259">In the following example, the items contained in the `ExclusionExtension` list are highlighted:</span></span>

![PowerShell 输出Get-MpPreference排除列表以及其他首选项](images/defender/wdav-powershell-get-exclusions-all.png)

<span data-ttu-id="02036-261">有关详细信息，请参阅使用[PowerShell cmdlet 配置](use-powershell-cmdlets-microsoft-defender-antivirus.md)和运行 Microsoft Defender 防病毒和[Defender cmdlet。](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="02036-261">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="02036-262">使用 PowerShell 检索特定排除项列表</span><span class="sxs-lookup"><span data-stu-id="02036-262">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="02036-263">使用以下代码段 (代码段作为单独的命令代码段输入) ;将 **WDAVprefs** 替换为要命名变量的任何标签：</span><span class="sxs-lookup"><span data-stu-id="02036-263">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

<span data-ttu-id="02036-264">在下面的示例中，列表将拆分为每次使用 cmdlet 时的新 `Add-MpPreference` 行：</span><span class="sxs-lookup"><span data-stu-id="02036-264">In the following example, the list is split into new lines for each use of the `Add-MpPreference` cmdlet:</span></span>

![仅显示排除列表中的条目的 PowerShell 输出](images/defender/wdav-powershell-get-exclusions-variable.png)

<span data-ttu-id="02036-266">有关详细信息，请参阅使用[PowerShell cmdlet 配置](use-powershell-cmdlets-microsoft-defender-antivirus.md)和运行 Microsoft Defender 防病毒和[Defender cmdlet。](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="02036-266">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="02036-267">使用 EICAR 测试文件验证排除列表</span><span class="sxs-lookup"><span data-stu-id="02036-267">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="02036-268">可以通过将 PowerShell 与 cmdlet 或 .NET WebClient 类一同使用来下载测试文件，来验证排除列表 `Invoke-WebRequest` 是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="02036-268">You can validate that your exclusion lists are working by using PowerShell with either the `Invoke-WebRequest` cmdlet or the .NET WebClient class to download a test file.</span></span>

<span data-ttu-id="02036-269">在下面的 PowerShell 代码段中 *，test.txt替换为* 符合排除规则的文件。</span><span class="sxs-lookup"><span data-stu-id="02036-269">In the following PowerShell snippet, replace *test.txt* with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="02036-270">例如，如果已排除扩展 `.testing` ，请将 替换为 `test.txt` `test.testing` 。</span><span class="sxs-lookup"><span data-stu-id="02036-270">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="02036-271">如果要测试路径，请确保在此路径内运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="02036-271">If you are testing a path, ensure you run the cmdlet within that path.</span></span>

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

<span data-ttu-id="02036-272">如果 Microsoft Defender 防病毒报告恶意软件，则规则无法工作。</span><span class="sxs-lookup"><span data-stu-id="02036-272">If Microsoft Defender Antivirus reports malware, then the rule is not working.</span></span> <span data-ttu-id="02036-273">如果没有任何恶意软件报告且下载的文件存在，则排除将正常工作。</span><span class="sxs-lookup"><span data-stu-id="02036-273">If there is no report of malware and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="02036-274">你可以打开文件以确认内容与 EICAR 测试文件网站上 [介绍的内容相同](http://www.eicar.org/86-0-Intended-use.html)。</span><span class="sxs-lookup"><span data-stu-id="02036-274">You can open the file to confirm the contents are the same as what is described on the [EICAR test file website](http://www.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="02036-275">您还可以使用以下 PowerShell 代码，该代码调用 .NET WebClient 类以下载测试文件（与 cmdlet 一样）;将c:\test.txt替换为符合要验证的规则 `Invoke-WebRequest` 的文件： </span><span class="sxs-lookup"><span data-stu-id="02036-275">You can also use the following PowerShell code, which calls the .NET WebClient class to download the test file - as with the `Invoke-WebRequest` cmdlet; replace *c:\test.txt* with a file that conforms to the rule you are validating:</span></span>

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

<span data-ttu-id="02036-276">如果你没有 Internet 访问权限，可以通过以下 PowerShell 命令将 EICAR 字符串写入新的文本文件来创建你自己的 EICAR 测试文件：</span><span class="sxs-lookup"><span data-stu-id="02036-276">If you do not have Internet access, you can create your own EICAR test file by writing the EICAR string to a new text file with the following PowerShell command:</span></span>

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

<span data-ttu-id="02036-277">还可以将字符串复制到空白文本文件中，并尝试使用文件名或试图排除的文件夹中保存它。</span><span class="sxs-lookup"><span data-stu-id="02036-277">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="related-topics"></a><span data-ttu-id="02036-278">相关主题</span><span class="sxs-lookup"><span data-stu-id="02036-278">Related topics</span></span>

- [<span data-ttu-id="02036-279">配置并验证 Microsoft Defender 防病毒扫描中的排除项</span><span class="sxs-lookup"><span data-stu-id="02036-279">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="02036-280">配置并验证进程打开的文件的排除项</span><span class="sxs-lookup"><span data-stu-id="02036-280">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="02036-281">在 Windows Server 上配置 Microsoft Defender 防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="02036-281">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="02036-282">定义排除时要避免的常见错误</span><span class="sxs-lookup"><span data-stu-id="02036-282">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
