---
title: 为特定进程打开的文件配置排除项
description: 如果文件已由特定进程打开，可以从扫描中排除这些文件。
keywords: Microsoft Defender 防病毒， 进程， 排除， 文件， 扫描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 4a117d2743436381029d047693f81303e5908b2b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689915"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a><span data-ttu-id="eea17-104">为进程打开的文件配置排除项</span><span class="sxs-lookup"><span data-stu-id="eea17-104">Configure exclusions for files opened by processes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="eea17-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="eea17-105">**Applies to:**</span></span>

- [<span data-ttu-id="eea17-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eea17-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="eea17-107">你可以从 Microsoft Defender 防病毒扫描中排除特定进程打开的文件。</span><span class="sxs-lookup"><span data-stu-id="eea17-107">You can exclude files that have been opened by specific processes from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="eea17-108">请参阅 [定义排除列表之前](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 定义排除项的建议。</span><span class="sxs-lookup"><span data-stu-id="eea17-108">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

<span data-ttu-id="eea17-109">本文介绍如何配置排除列表。</span><span class="sxs-lookup"><span data-stu-id="eea17-109">This article describes how to configure exclusion lists.</span></span> 

## <a name="examples-of-exclusions"></a><span data-ttu-id="eea17-110">排除示例</span><span class="sxs-lookup"><span data-stu-id="eea17-110">Examples of exclusions</span></span>

|<span data-ttu-id="eea17-111">排除</span><span class="sxs-lookup"><span data-stu-id="eea17-111">Exclusion</span></span> | <span data-ttu-id="eea17-112">示例</span><span class="sxs-lookup"><span data-stu-id="eea17-112">Example</span></span> |
|---|---|
|<span data-ttu-id="eea17-113">计算机上使用特定文件名的任何进程打开的任何文件</span><span class="sxs-lookup"><span data-stu-id="eea17-113">Any file on the machine that is opened by any process with a specific file name</span></span> | <span data-ttu-id="eea17-114">指定 `test.exe` 将排除由：</span><span class="sxs-lookup"><span data-stu-id="eea17-114">Specifying `test.exe` would exclude files opened by:</span></span> <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|<span data-ttu-id="eea17-115">计算机上由特定文件夹下的任何进程打开的任何文件</span><span class="sxs-lookup"><span data-stu-id="eea17-115">Any file on the machine that is opened by any process under a specific folder</span></span> | <span data-ttu-id="eea17-116">指定 `c:\test\sample\*` 将排除由：</span><span class="sxs-lookup"><span data-stu-id="eea17-116">Specifying `c:\test\sample\*` would exclude files opened by:</span></span><br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|<span data-ttu-id="eea17-117">计算机上特定进程打开的特定文件夹中的任何文件</span><span class="sxs-lookup"><span data-stu-id="eea17-117">Any file on the machine that is opened by a specific process in a specific folder</span></span> | <span data-ttu-id="eea17-118">指定 `c:\test\process.exe` 将排除仅打开者的文件 `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="eea17-118">Specifying `c:\test\process.exe` would exclude files only opened by `c:\test\process.exe`</span></span> |


<span data-ttu-id="eea17-119">当你将进程添加到进程排除列表时，Microsoft Defender 防病毒不会扫描该进程打开的文件，无论这些文件位于何处。</span><span class="sxs-lookup"><span data-stu-id="eea17-119">When you add a process to the process exclusion list, Microsoft Defender Antivirus won't scan files opened by that process, no matter where the files are located.</span></span> <span data-ttu-id="eea17-120">但是，除非进程已添加到文件排除列表 ，否则将扫描进程 [本身](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="eea17-120">The process itself, however, will be scanned unless it has also been added to the [file exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="eea17-121">排除项仅适用于 [始终打开实时保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="eea17-121">The exclusions only apply to [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="eea17-122">它们不适用于计划扫描或按需扫描。</span><span class="sxs-lookup"><span data-stu-id="eea17-122">They don't apply to scheduled or on-demand scans.</span></span>

<span data-ttu-id="eea17-123">使用组策略对排除列表所做的更改 **将显示在** Windows 安全应用中 [的列表中](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="eea17-123">Changes made with Group Policy to the exclusion lists **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="eea17-124">但是，在 Windows 安全应用中所做的更改 **将不会显示在** 组策略列表中。</span><span class="sxs-lookup"><span data-stu-id="eea17-124">However, changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="eea17-125">可以在组策略、Microsoft Endpoint Configuration Manager、Microsoft Intune 以及 Windows 安全中心应用中添加、删除和查看排除列表，并且可以使用通配符进一步自定义列表。</span><span class="sxs-lookup"><span data-stu-id="eea17-125">You can add, remove, and review the lists for exclusions in Group Policy, Microsoft Endpoint Configuration Manager, Microsoft Intune, and with the Windows Security app, and you can use wildcards to further customize the lists.</span></span>

<span data-ttu-id="eea17-126">您还可以使用 PowerShell cmdlet 和 WMI 配置排除列表，包括查看列表。</span><span class="sxs-lookup"><span data-stu-id="eea17-126">You can also use PowerShell cmdlets and WMI to configure the exclusion lists, including reviewing your lists.</span></span>

<span data-ttu-id="eea17-127">默认情况下，对列表进行的本地更改 (管理员权限的用户进行更改;使用 PowerShell 和 WMI) 所做的更改将与 (定义的列表合并，) 组策略、配置管理器或 Intune 进行部署。</span><span class="sxs-lookup"><span data-stu-id="eea17-127">By default, local changes made to the lists (by users with administrator privileges; changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="eea17-128">如果发生冲突，组策略列表将优先。</span><span class="sxs-lookup"><span data-stu-id="eea17-128">The Group Policy lists will take precedence in the case of conflicts.</span></span>

<span data-ttu-id="eea17-129">您可以 [配置本地和](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) 全局定义的排除列表的合并方式，以允许本地更改覆盖托管部署设置。</span><span class="sxs-lookup"><span data-stu-id="eea17-129">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a><span data-ttu-id="eea17-130">配置由指定进程打开的文件的排除项列表</span><span class="sxs-lookup"><span data-stu-id="eea17-130">Configure the list of exclusions for files opened by specified processes</span></span>

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="eea17-131">使用 Microsoft Intune 从扫描中排除指定进程打开的文件</span><span class="sxs-lookup"><span data-stu-id="eea17-131">Use Microsoft Intune to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="eea17-132">有关详细信息 [，请参阅在 Microsoft Intune 中](/intune/device-restrictions-configure) 配置设备限制设置和 Intune 中 [Windows 10](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 的 Microsoft Defender 防病毒设备限制设置。</span><span class="sxs-lookup"><span data-stu-id="eea17-132">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="eea17-133">使用 Microsoft Endpoint Manager 从扫描中排除指定进程打开的文件</span><span class="sxs-lookup"><span data-stu-id="eea17-133">Use Microsoft Endpoint Manager to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="eea17-134">请参阅 [如何创建和部署反恶意软件策略：](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) 排除设置，了解有关配置 Microsoft Endpoint Manager (当前分支) 。</span><span class="sxs-lookup"><span data-stu-id="eea17-134">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="eea17-135">使用组策略将指定进程打开的文件从扫描中排除</span><span class="sxs-lookup"><span data-stu-id="eea17-135">Use Group Policy to exclude files that have been opened by specified processes from scans</span></span>

1. <span data-ttu-id="eea17-136">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="eea17-136">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="eea17-137">在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="eea17-137">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="eea17-138">将树展开到 **Microsoft Defender 防病毒>排除> Windows 组件**。</span><span class="sxs-lookup"><span data-stu-id="eea17-138">Expand the tree to **Windows components > Microsoft Defender Antivirus > Exclusions**.</span></span>

4. <span data-ttu-id="eea17-139">双击进程 **排除项** 并添加排除项：</span><span class="sxs-lookup"><span data-stu-id="eea17-139">Double-click **Process Exclusions** and add the exclusions:</span></span>

    1. <span data-ttu-id="eea17-140">将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="eea17-140">Set the option to **Enabled**.</span></span>
    2. <span data-ttu-id="eea17-141">在"选项 **"部分** 下，单击"**显示..."。**</span><span class="sxs-lookup"><span data-stu-id="eea17-141">Under the **Options** section, click **Show...**.</span></span>
    3. <span data-ttu-id="eea17-142">在"值名称"列下，在其自己的 **行中输入每个** 进程。</span><span class="sxs-lookup"><span data-stu-id="eea17-142">Enter each process on its own line under the **Value name** column.</span></span> <span data-ttu-id="eea17-143">有关不同类型的进程排除项，请参阅示例表。</span><span class="sxs-lookup"><span data-stu-id="eea17-143">See the example table for the different types of process exclusions.</span></span>  <span data-ttu-id="eea17-144">在所有进程的值 **列中输入** **0。**</span><span class="sxs-lookup"><span data-stu-id="eea17-144">Enter **0** in the **Value** column for all processes.</span></span>

5. <span data-ttu-id="eea17-145">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="eea17-145">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="eea17-146">使用 PowerShell cmdlet 从扫描中排除指定进程打开的文件</span><span class="sxs-lookup"><span data-stu-id="eea17-146">Use PowerShell cmdlets to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="eea17-147">使用 PowerShell 添加或删除由进程打开的文件的排除项需要结合使用三个 cmdlet 和 `-ExclusionProcess` 参数。</span><span class="sxs-lookup"><span data-stu-id="eea17-147">Using PowerShell to add or remove exclusions for files that have been opened by processes requires using a combination of three cmdlets with the `-ExclusionProcess` parameter.</span></span> <span data-ttu-id="eea17-148">cmdlet 全部在 Defender [模块中](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="eea17-148">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="eea17-149">cmdlet 的格式为：</span><span class="sxs-lookup"><span data-stu-id="eea17-149">The format for the cmdlets is:</span></span>

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

<span data-ttu-id="eea17-150">允许将以下内容作为 \<cmdlet> ：</span><span class="sxs-lookup"><span data-stu-id="eea17-150">The following are allowed as the \<cmdlet>:</span></span>

|<span data-ttu-id="eea17-151">配置操作</span><span class="sxs-lookup"><span data-stu-id="eea17-151">Configuration action</span></span> | <span data-ttu-id="eea17-152">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="eea17-152">PowerShell cmdlet</span></span> |
|---|---|
|<span data-ttu-id="eea17-153">创建或覆盖列表</span><span class="sxs-lookup"><span data-stu-id="eea17-153">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="eea17-154">添加到列表</span><span class="sxs-lookup"><span data-stu-id="eea17-154">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="eea17-155">从列表中删除项目</span><span class="sxs-lookup"><span data-stu-id="eea17-155">Remove items from the list</span></span> | `Remove-MpPreference` |

>[!IMPORTANT]
><span data-ttu-id="eea17-156">如果已使用 或 创建列表， `Set-MpPreference` `Add-MpPreference` 则再次使用 `Set-MpPreference` cmdlet 将覆盖现有列表。</span><span class="sxs-lookup"><span data-stu-id="eea17-156">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="eea17-157">例如，以下代码段将导致 Microsoft Defender AV 扫描排除指定进程打开的任何文件：</span><span class="sxs-lookup"><span data-stu-id="eea17-157">For example, the following code snippet would cause Microsoft Defender AV scans to exclude any file that is opened by the specified process:</span></span>

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

<span data-ttu-id="eea17-158">若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用，请参阅使用 PowerShell cmdlet 和 Microsoft Defender 防病毒 [cmdlet](/powershell/module/defender)管理防病毒。</span><span class="sxs-lookup"><span data-stu-id="eea17-158">For more information on how to use PowerShell with Microsoft Defender Antivirus, see Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span></span>

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="eea17-159">使用 Windows Management Instruction (WMI) 从扫描中排除指定进程打开的文件</span><span class="sxs-lookup"><span data-stu-id="eea17-159">Use Windows Management Instruction (WMI) to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="eea17-160">对 [**以下属性** 使用 **MSFT_MpPreference** 类的 **Set、Add**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))和 Remove 方法：</span><span class="sxs-lookup"><span data-stu-id="eea17-160">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionProcess
```

<span data-ttu-id="eea17-161">Set、Add和 **Remove** 的使用类似于 PowerShell 中的对应类 `Set-MpPreference` ：、、 和 `Add-MpPreference` `Remove-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="eea17-161">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="eea17-162">有关详细信息和允许的参数，请参阅 Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="eea17-162">For more information and allowed parameters, see  [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="eea17-163">使用 Windows 安全应用从扫描中排除指定进程打开的文件</span><span class="sxs-lookup"><span data-stu-id="eea17-163">Use the Windows Security app to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="eea17-164">有关 [说明，请参阅在 Windows 安全应用中添加](microsoft-defender-security-center-antivirus.md) 排除项。</span><span class="sxs-lookup"><span data-stu-id="eea17-164">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

## <a name="use-wildcards-in-the-process-exclusion-list"></a><span data-ttu-id="eea17-165">在进程排除列表中使用通配符</span><span class="sxs-lookup"><span data-stu-id="eea17-165">Use wildcards in the process exclusion list</span></span>

<span data-ttu-id="eea17-166">进程排除列表中的通配符的使用不同于在其他排除列表中的使用。</span><span class="sxs-lookup"><span data-stu-id="eea17-166">The use of wildcards in the process exclusion list is different from their use in other exclusion lists.</span></span>

<span data-ttu-id="eea17-167">特别是，不能使用问号 () 通配符，并且星号 () 通配符只能在完整路径的末尾 `?` `*` 使用。</span><span class="sxs-lookup"><span data-stu-id="eea17-167">In particular, you cannot use the question mark (`?`) wildcard, and the asterisk (`*`) wildcard can only be used at the end of a complete path.</span></span> <span data-ttu-id="eea17-168">在进程排除列表中定义 (时，您仍可以将 (`%ALLUSERSPROFILE%`) 用作通配符。</span><span class="sxs-lookup"><span data-stu-id="eea17-168">You can still use environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the process exclusion list.</span></span>

<span data-ttu-id="eea17-169">下表介绍如何在进程排除列表中使用通配符：</span><span class="sxs-lookup"><span data-stu-id="eea17-169">The following table describes how the wildcards can be used in the process exclusion list:</span></span>

|<span data-ttu-id="eea17-170">通配符</span><span class="sxs-lookup"><span data-stu-id="eea17-170">Wildcard</span></span> | <span data-ttu-id="eea17-171">示例使用</span><span class="sxs-lookup"><span data-stu-id="eea17-171">Example use</span></span> | <span data-ttu-id="eea17-172">示例匹配</span><span class="sxs-lookup"><span data-stu-id="eea17-172">Example matches</span></span> |
|:---|:---|:---|
|<span data-ttu-id="eea17-173">`*` (星号) </span><span class="sxs-lookup"><span data-stu-id="eea17-173">`*` (asterisk)</span></span> <br/><br/> <span data-ttu-id="eea17-174">替换任意数目的字符</span><span class="sxs-lookup"><span data-stu-id="eea17-174">Replaces any number of characters</span></span> | `C:\MyData\*` | <span data-ttu-id="eea17-175">打开的任何文件 `C:\MyData\file.exe`</span><span class="sxs-lookup"><span data-stu-id="eea17-175">Any file opened by `C:\MyData\file.exe`</span></span> |
|<span data-ttu-id="eea17-176">环境变量</span><span class="sxs-lookup"><span data-stu-id="eea17-176">Environment variables</span></span> <br/><br/> <span data-ttu-id="eea17-177">在计算排除时，定义的变量将填充为路径</span><span class="sxs-lookup"><span data-stu-id="eea17-177">The defined variable is populated as a path when the exclusion is evaluated</span></span> | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | <span data-ttu-id="eea17-178">打开的任何文件 `C:\ProgramData\CustomLogFiles\file.exe`</span><span class="sxs-lookup"><span data-stu-id="eea17-178">Any file opened by `C:\ProgramData\CustomLogFiles\file.exe`</span></span> |

## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="eea17-179">查看排除项列表</span><span class="sxs-lookup"><span data-stu-id="eea17-179">Review the list of exclusions</span></span>

<span data-ttu-id="eea17-180">可以使用 MpCmdRun、PowerShell、Microsoft [Endpoint Configuration Manager、Intune](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)或[](/intune/device-restrictions-configure)Windows 安全应用检索排除[列表中的项](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="eea17-180">You can retrieve the items in the exclusion list with MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure), or the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

<span data-ttu-id="eea17-181">如果使用 PowerShell，可以通过两种方式检索列表：</span><span class="sxs-lookup"><span data-stu-id="eea17-181">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="eea17-182">检索所有 Microsoft Defender 防病毒首选项的状态。</span><span class="sxs-lookup"><span data-stu-id="eea17-182">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="eea17-183">每个列表将显示在单独的行上，但每个列表中的项将组合到同一行中。</span><span class="sxs-lookup"><span data-stu-id="eea17-183">Each of the lists will be displayed on separate lines, but the items within each list will be combined into the same line.</span></span>
- <span data-ttu-id="eea17-184">将所有首选项的状态写入变量，并使用该变量仅调用您感兴趣的特定列表。</span><span class="sxs-lookup"><span data-stu-id="eea17-184">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="eea17-185">每次使用 `Add-MpPreference` 都写入新行。</span><span class="sxs-lookup"><span data-stu-id="eea17-185">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="eea17-186">使用 MpCmdRun 验证排除列表</span><span class="sxs-lookup"><span data-stu-id="eea17-186">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="eea17-187">若要使用专用命令行工具检查排除 [mpcmdrun.exe，请使用 ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)以下命令：</span><span class="sxs-lookup"><span data-stu-id="eea17-187">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> <span data-ttu-id="eea17-188">检查 MpCmdRun 的排除项需要 Microsoft Defender 防病毒 CAMP 版本 4.18.1812.3 (2018 年 12 月) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="eea17-188">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="eea17-189">使用 PowerShell 查看所有其他 Microsoft Defender 防病毒首选项旁的排除项列表</span><span class="sxs-lookup"><span data-stu-id="eea17-189">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="eea17-190">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="eea17-190">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="eea17-191">请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。</span><span class="sxs-lookup"><span data-stu-id="eea17-191">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="eea17-192">使用 PowerShell 检索特定排除项列表</span><span class="sxs-lookup"><span data-stu-id="eea17-192">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="eea17-193">使用以下代码段 (代码段作为单独的命令代码段输入) ;将 **WDAVprefs** 替换为要命名变量的任何标签：</span><span class="sxs-lookup"><span data-stu-id="eea17-193">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

<span data-ttu-id="eea17-194">请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。</span><span class="sxs-lookup"><span data-stu-id="eea17-194">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="related-articles"></a><span data-ttu-id="eea17-195">相关文章</span><span class="sxs-lookup"><span data-stu-id="eea17-195">Related articles</span></span>

- [<span data-ttu-id="eea17-196">配置并验证 Microsoft Defender 防病毒扫描中的排除项</span><span class="sxs-lookup"><span data-stu-id="eea17-196">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eea17-197">根据文件名、扩展名和文件夹位置配置并验证排除项</span><span class="sxs-lookup"><span data-stu-id="eea17-197">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eea17-198">在 Windows Server 上配置 Microsoft Defender 防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="eea17-198">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eea17-199">定义排除项时应避免的常见错误</span><span class="sxs-lookup"><span data-stu-id="eea17-199">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eea17-200">自定义、启动和查看 Microsoft Defender 防病毒扫描和修正的结果</span><span class="sxs-lookup"><span data-stu-id="eea17-200">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eea17-201">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="eea17-201">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)