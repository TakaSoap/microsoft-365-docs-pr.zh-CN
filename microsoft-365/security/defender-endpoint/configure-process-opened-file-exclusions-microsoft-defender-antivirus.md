---
title: 为特定进程打开的文件配置排除项
description: 如果文件已由特定进程打开，可以从扫描中排除这些文件。
keywords: Microsoft Defender 防病毒， 进程， 排除， 文件， 扫描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: eb1b28b49bbf684f0f1845eafb1332c7fb00be12
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205627"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>为进程打开的文件配置排除项


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以从扫描中排除特定进程打开Microsoft Defender 防病毒文件。 请参阅[推荐定义排除](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)项，然后再定义排除列表。

本文介绍如何配置排除列表。

## <a name="examples-of-exclusions"></a>排除示例

<br/><br/>

|排除|示例|
|---|---|
|计算机上使用特定文件名的任何进程打开的任何文件|指定 `test.exe` 将排除由： <p>`c:\sample\test.exe` <p> `d:\internal\files\test.exe`|
|计算机上由特定文件夹下的任何进程打开的任何文件|指定 `c:\test\sample\*` 将排除由： <p> `c:\test\sample\test.exe` <p> `c:\test\sample\test2.exe` <p> `c:\test\sample\utility.exe`|
|计算机上特定进程打开的特定文件夹中的任何文件|指定 `c:\test\process.exe` 将排除仅打开者的文件 `c:\test\process.exe`|

将进程添加到进程排除列表时，Microsoft Defender 防病毒不会扫描该进程打开的文件，无论这些文件位于何处。 但是，除非进程已添加到文件排除列表 ，否则将扫描进程 [本身](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

排除项仅适用于 [始终打开实时保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)。 它们不适用于计划扫描或按需扫描。

使用组策略对排除列表所做的更改 **会显示在** Windows 安全中心 [列表中](microsoft-defender-security-center-antivirus.md)。 但是，在Windows 安全中心 **所做的更改将不会显示在** 组策略列表中。

可以在组策略、Microsoft Endpoint Configuration Manager、Microsoft Intune 以及 Windows 安全中心 应用中添加、删除和查看排除列表，并且可以使用通配符进一步自定义列表。

您还可以使用 PowerShell cmdlet 和 WMI 配置排除列表，包括查看列表。

默认情况下，对列表进行的本地更改 (管理员权限的用户进行更改;使用 PowerShell 和 WMI) 所做的更改将与 (定义的列表合并，) 组策略、配置管理器或 Intune 进行部署。 如果发生冲突，组策略列表将优先。

您可以 [配置本地和](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) 全局定义的排除列表的合并方式，以允许本地更改覆盖托管部署设置。

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>配置由指定进程打开的文件的排除项列表

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用Microsoft Intune扫描中排除指定进程打开的文件

有关详细信息，请参阅[Microsoft Intune](/intune/device-restrictions-configure) 和 [Microsoft Defender Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) Windows 10 防病毒设备限制设置。

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用Microsoft Endpoint Manager扫描中排除指定进程打开的文件

请参阅[如何创建和部署反恶意软件策略：排除](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)设置，详细了解如何Microsoft Endpoint Manager (当前分支) 。

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用组策略从扫描中排除指定进程打开的文件

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

2. 在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。

3. 展开树以 **Windows排除 \> Microsoft Defender 防病毒 \> 组件**。

4. 双击进程 **排除项** 并添加排除项：
    1. 将选项设置为 **已启用**。
    2. 在"选项 **"部分** 下，单击"**显示..."。**
    3. 在"值名称"列下，在其自己的 **行中输入每个** 进程。 有关不同类型的进程排除项，请参阅示例表。 在所有进程的值 **列中输入** **0。**

5. 单击“**确定**”。

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用 PowerShell cmdlet 从扫描中排除指定进程打开的文件

使用 PowerShell 添加或删除由进程打开的文件的排除项需要结合使用三个 cmdlet 和 `-ExclusionProcess` 参数。 cmdlet 全部在 Defender [模块中](/powershell/module/defender/)。

cmdlet 的格式为：

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

允许将以下内容作为 \<cmdlet\> ：

<br/><br/>

|配置操作|PowerShell cmdlet|
|---|---|
|创建或覆盖列表|`Set-MpPreference`|
|添加到列表|`Add-MpPreference`|
|从列表中删除项目|`Remove-MpPreference`|

> [!IMPORTANT]
> 如果已使用 或 创建列表， `Set-MpPreference` `Add-MpPreference` 则再次使用 `Set-MpPreference` cmdlet 将覆盖现有列表。

例如，以下代码段将导致 Microsoft Defender AV 扫描排除指定进程打开的任何文件：

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

若要详细了解如何使用 PowerShell 和 Microsoft Defender 防病毒，请参阅使用 PowerShell cmdlet 和 Microsoft Defender 防病毒[cmdlet](/powershell/module/defender)管理防病毒。

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用 Windows Management Instruction (WMI) 从扫描中排除指定进程打开的文件

对 [**以下属性** 使用 **MSFT_MpPreference** 类的 **Set、Add**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))和 Remove 方法：

```WMI
ExclusionProcess
```

Set、Add和 **Remove** 的使用类似于 PowerShell 中的对应类 `Set-MpPreference` ：、、 和 `Add-MpPreference` `Remove-MpPreference` 。

有关详细信息和允许的参数，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用 Windows 安全中心应用从扫描中排除指定进程打开的文件

有关[说明，请参阅Windows 安全中心应用添加](microsoft-defender-security-center-antivirus.md)排除项。

## <a name="use-wildcards-in-the-process-exclusion-list"></a>在进程排除列表中使用通配符

进程排除列表中的通配符的使用不同于在其他排除列表中的使用。

特别是，不能使用问号 () 通配符，并且星号 () 通配符只能在完整路径的末尾 `?` `*` 使用。 在进程排除列表中定义 (时，仍可以使用) 变量（如通配符 `%ALLUSERSPROFILE%` ）。

下表介绍如何在进程排除列表中使用通配符：

<br/><br/>

|通配符|示例使用|示例匹配|
|---|---|---|
|`*` (星号)  <p> 替换任意数目的字符|`C:\MyData\*`|打开的任何文件 `C:\MyData\file.exe`|
|环境变量 <p> 在计算排除时，定义的变量将填充为路径|`%ALLUSERSPROFILE%\CustomLogFiles\file.exe`|打开的任何文件 `C:\ProgramData\CustomLogFiles\file.exe`|

## <a name="review-the-list-of-exclusions"></a>查看排除项列表

可以使用 MpCmdRun、PowerShell、Microsoft Endpoint Configuration Manager、Intune 或应用检索[](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)排除Windows 安全中心[项](microsoft-defender-security-center-antivirus.md)。 [](/intune/device-restrictions-configure)

如果使用 PowerShell，可以通过两种方式检索列表：

- 检索所有首选项Microsoft Defender 防病毒状态。 每个列表将显示在单独的行上，但每个列表中的项将组合到同一行中。
- 将所有首选项的状态写入变量，并使用该变量仅调用您感兴趣的特定列表。 每次使用 `Add-MpPreference` 都写入新行。

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>使用 MpCmdRun 验证排除列表

若要使用专用命令行工具检查排除 [mpcmdrun.exe，请使用 ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)以下命令：

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> 检查 MpCmdRun 的排除项Microsoft Defender 防病毒 2018 年 12 月或 (发布的 CAMP 版本 4.18.1812.3) 。

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>使用 PowerShell 查看所有其他Microsoft Defender 防病毒首选项的列表

使用以下 cmdlet：

```PowerShell
Get-MpPreference
```

请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender cmdlet](/powershell/module/defender) ，了解有关如何通过 Microsoft Defender 防病毒软件使用 PowerShell 的信息。

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>使用 PowerShell 检索特定排除项列表

使用以下代码段 (代码段作为单独的命令代码段输入) ;将 **WDAVprefs** 替换为你想要为变量命名的任何标签：

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender cmdlet](/powershell/module/defender) ，了解有关如何通过 Microsoft Defender 防病毒软件使用 PowerShell 的信息。

## <a name="related-articles"></a>相关文章

- [配置并验证扫描中的Microsoft Defender 防病毒项](configure-exclusions-microsoft-defender-antivirus.md)
- [根据文件名、扩展名和文件夹位置配置并验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [在 Microsoft Defender 防病毒 服务器上配置Windows排除项](configure-server-exclusions-microsoft-defender-antivirus.md)
- [定义排除时要避免的常见错误](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [自定义、启动和查看Microsoft Defender 防病毒扫描和修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
