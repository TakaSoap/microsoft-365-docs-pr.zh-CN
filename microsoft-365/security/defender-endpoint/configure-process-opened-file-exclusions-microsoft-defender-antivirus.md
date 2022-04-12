---
title: 为由特定进程打开的文件配置排除项
description: 如果特定进程已打开文件，则可以从扫描中排除文件。
keywords: Microsoft Defender 防病毒、进程、排除、文件、扫描
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
ms.openlocfilehash: e8cf075c0a35095f72d847a17f1fb48d590ad385
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788977"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>为进程打开的文件配置排除项


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows 

可以从Microsoft Defender 防病毒扫描中排除由特定进程打开的文件。 在定义排除列表之前，请参阅[推荐定义排除](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)项。

本文介绍如何配置排除列表。

## <a name="examples-of-exclusions"></a>排除示例

<br/><br/>

|排除|示例|
|---|---|
|计算机上由具有特定文件名的任何进程打开的任何文件|`test.exe`指定将排除通过以下方式打开的文件： <p>`c:\sample\test.exe` <p> `d:\internal\files\test.exe`|
|计算机上由特定文件夹下的任何进程打开的任何文件|`c:\test\sample\*`指定将排除通过以下方式打开的文件： <p> `c:\test\sample\test.exe` <p> `c:\test\sample\test2.exe` <p> `c:\test\sample\utility.exe`|
|计算机上由特定进程在特定文件夹中打开的任何文件|`c:\test\process.exe`指定将排除仅由打开的文件`c:\test\process.exe`|

将进程添加到进程排除列表时，无论文件位于何处，Microsoft Defender 防病毒都不会扫描由该进程打开的文件。 但是，除非进程也已添加到 [文件排除列表](configure-extension-file-exclusions-microsoft-defender-antivirus.md)，否则会扫描该进程本身。

排除项仅适用于 [始终实时保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)。 它们不适用于计划扫描或按需扫描。

使用组策略对排除列表所做的更改 **将显示** 在 [Windows 安全中心应用](microsoft-defender-security-center-antivirus.md)中的列表中。 但是，Windows 安全中心应用中所做的更改 **不会显示** 在组策略列表中。

可以在组策略、Microsoft Endpoint Configuration Manager、Microsoft Intune和Windows 安全中心应用中添加、删除和查看排除项的列表，并且可以使用通配符进一步自定义列表。

还可以使用 PowerShell cmdlet 和 WMI 配置排除列表，包括查看列表。

默认情况下，对具有管理员权限的用户 (列表进行的本地更改;使用 PowerShell 和 WMI) 所做的更改将与 (定义的列表合并，并由组策略、Configuration Manager或Intune部署) 。 在发生冲突时，组策略列表优先。

可以 [配置本地和全局定义的排除列表的合并](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) 方式，以允许本地更改替代托管部署设置。

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>配置指定进程打开的文件的排除项列表

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用Microsoft Intune从扫描中排除指定进程打开的文件

有关详细信息，请参阅[Microsoft Intune](/intune/device-restrictions-configure) 和 [Microsoft Defender Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) Windows 10 防病毒设备限制设置。

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用Microsoft Endpoint Manager从扫描中排除指定进程打开的文件

有关配置 Microsoft Endpoint Manager (当前分支) 的详细信息，请参阅[如何创建和部署反恶意软件策略：排除设置](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)。

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用组策略从扫描中排除指定进程打开的文件

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 在 **组策略管理编辑器** 中转到 **“计算机配置**”，然后单击 **“管理模板**”。

3. 将树展开为 **Windows组件\>Microsoft Defender 防病毒\>排除项**。

4. 双击 **“进程排除”** 并添加排除项：
    1. 将选项设置为 **“已启用**”。
    2. 在 **“选项”** 部分下，单击 **“显示...**”。
    3. 在“ **值名称** ”列下的自身行上输入每个进程。 有关不同类型的进程排除项，请参阅示例表。 在所有进程的 **“值**”列中输入 **0**。

5. 单击“确定”。

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用 PowerShell cmdlet 从扫描中排除指定进程打开的文件

使用 PowerShell 添加或删除进程打开的文件的排除项需要将三个 cmdlet 与 `-ExclusionProcess` 参数结合使用。 cmdlet 全部在 [Defender 模块](/powershell/module/defender/)中。

cmdlet 的格式为：

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

以下内容允许如下所示 \<cmdlet\>：

<br/><br/>

|配置操作|PowerShell cmdlet|
|---|---|
|创建或覆盖列表|`Set-MpPreference`|
|添加到列表|`Add-MpPreference`|
|从列表中删除项|`Remove-MpPreference`|

> [!IMPORTANT]
> 如果已使用或`Add-MpPreference`再次使用`Set-MpPreference`该 cmdlet 创建了一个列表`Set-MpPreference`，则会覆盖现有列表。

例如，以下代码片段将导致 Microsoft Defender AV 扫描排除指定进程打开的任何文件：

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

有关如何将 PowerShell 与Microsoft Defender 防病毒配合使用的详细信息，请参阅使用 PowerShell cmdlet 和 [Microsoft Defender 防病毒 cmdlet](/powershell/module/defender) 管理防病毒。

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用Windows管理指令 (WMI) 从扫描中排除指定进程打开的文件

对以下属性使用 [**MSFT_MpPreference** 类的 **Set**、**Add** 和 **Remove** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))：

```WMI
ExclusionProcess
```

**Set**、**Add** 和 **Remove** 的使用类似于 PowerShell 中的对应项： `Set-MpPreference``Add-MpPreference``Remove-MpPreference`和 .

有关详细信息和允许的参数，请[参阅Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用Windows 安全中心应用从扫描中排除指定进程打开的文件

有关说明，请参阅[Windows 安全中心应用中的“添加排除](microsoft-defender-security-center-antivirus.md)项”。

## <a name="use-wildcards-in-the-process-exclusion-list"></a>在进程排除列表中使用通配符

进程排除列表中通配符的使用不同于它们在其他排除列表中的使用。

特别是，不能使用问号 () `?` 通配符，星号 (`*`) 通配符只能在完整路径的末尾使用。 在进程排除列表中定义项时，仍可使用环境变量 (（例如 `%ALLUSERSPROFILE%`) ）作为通配符。

下表介绍了如何在进程排除列表中使用通配符：

<br/><br/>

|通配符|示例使用|示例匹配|
|---|---|---|
|`*` (星号)  <p> 替换任意数量的字符|`C:\MyData\*`|打开的任何文件 `C:\MyData\file.exe`|
|环境变量 <p> 计算排除项时，定义的变量将填充为路径|`%ALLUSERSPROFILE%\CustomLogFiles\file.exe`|打开的任何文件 `C:\ProgramData\CustomLogFiles\file.exe`|

## <a name="review-the-list-of-exclusions"></a>查看排除项列表

可以使用 MpCmdRun、PowerShell、[Microsoft Endpoint Configuration Manager、Intune](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) 或 [Windows 安全中心 应用](microsoft-defender-security-center-antivirus.md)检索排除列表中的项[](/intune/device-restrictions-configure)。

如果使用 PowerShell，可以通过两种方式检索列表：

- 检索所有Microsoft Defender 防病毒首选项的状态。 每个列表将显示在单独的行上，但每个列表中的项将合并到同一行中。
- 将所有首选项的状态写入变量，并使用该变量仅调用感兴趣的特定列表。 每种 `Add-MpPreference` 用途都写入新行。

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>使用 MpCmdRun 验证排除列表

若要使用专用 [命令行工具mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)检查排除项，请使用以下命令：

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> 使用 MpCmdRun 检查排除项需要Microsoft Defender 防病毒 2018 年 12 月) 或更高版本发布的 CAMP 版本 4.18.1812.3 (。

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>使用 PowerShell 查看排除项列表以及所有其他Microsoft Defender 防病毒首选项

使用以下 cmdlet：

```PowerShell
Get-MpPreference
```

有关如何将 PowerShell 与Microsoft Defender 防病毒配合使用的详细信息，请参阅[使用 PowerShell cmdlet 配置和运行Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md)和Microsoft Defender 防病毒 [cmdlet](/powershell/module/defender)。

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>使用 PowerShell 检索特定的排除项列表

使用以下代码片段 (输入每行作为单独的命令) ;将 **WDAVprefs** 替换为要命名变量的任何标签：

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

有关如何将 PowerShell 与Microsoft Defender 防病毒配合使用的详细信息，请参阅[使用 PowerShell cmdlet 配置和运行Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md)和Microsoft Defender 防病毒 [cmdlet](/powershell/module/defender)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="related-articles"></a>相关文章

- [在Microsoft Defender 防病毒扫描中配置和验证排除项](configure-exclusions-microsoft-defender-antivirus.md)
- [基于文件名、扩展名和文件夹位置配置和验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [在Windows服务器上配置Microsoft Defender 防病毒排除项](configure-server-exclusions-microsoft-defender-antivirus.md)
- [定义排除时要避免的常见错误](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [自定义、启动和查看Microsoft Defender 防病毒扫描和修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
