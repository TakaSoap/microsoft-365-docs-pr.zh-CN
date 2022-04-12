---
title: 根据扩展名、名称或位置配置和验证排除项
description: 根据文件扩展名、文件名或位置从Microsoft Defender 防病毒扫描中排除文件。
keywords: 排除项，文件，扩展名，文件类型，文件夹名称，文件名，扫描
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.date: 02/27/2022
ms.collection: M365-security-compliance
ms.openlocfilehash: e8c2b464b7a4559ba316826400cfd0ad308d8786
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790209"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a>基于文件扩展名和文件夹位置配置和验证排除项

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

可以为适用于[计划扫描](schedule-antivirus-scans.md)、[按需扫描](run-scan-microsoft-defender-antivirus.md)和[始终启用实时保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)的Microsoft Defender 防病毒定义排除项。 **通常，你不需要应用排除项**。 如果确实需要应用排除项，可以从多种不同类型中进行选择：

- 本文中所述的基于文件扩展名和文件夹位置的排除项 () 
- [进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

> [!IMPORTANT]
> Microsoft Defender 防病毒排除项不适用于其他Microsoft Defender for Endpoint功能，包括[终结点检测和响应 (EDR) ](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)、[攻击面减少 (ASR) 规则](/microsoft-365/security/defender-endpoint/attack-surface-reduction)和[受控文件夹访问权限](/microsoft-365/security/defender-endpoint/controlled-folders)。 使用本文中所述的方法排除的文件仍然可以触发EDR警报和其他检测。
> 若要广泛排除文件，请将其添加到Microsoft Defender for Endpoint[自定义指示器](/microsoft-365/security/defender-endpoint/manage-indicators)。

## <a name="before-you-begin"></a>准备工作

在定义排除列表之前，请参阅[推荐定义排除](configure-exclusions-microsoft-defender-antivirus.md)项。

## <a name="exclusion-lists"></a>排除列表

若要从Microsoft Defender 防病毒扫描中排除某些文件，请修改排除列表。 Microsoft Defender 防病毒包括许多基于已知操作系统行为和典型管理文件（例如用于企业管理、数据库管理和其他企业方案和情况）的自动排除项。

> [!NOTE]
> 排除项也适用于可能不需要的应用 (PUA) 检测。
>
> 自动排除仅适用于Windows Server 2016及更高版本。 这些排除项在Windows 安全中心应用和 PowerShell 中不可见。

下表列出了一些基于文件扩展名和文件夹位置的排除示例。

|排除|示例|排除列表|
|---|---|---|
|具有特定扩展名的任何文件|具有指定扩展名的所有文件，计算机上的任意位置。 <p> 有效语法： `.test` 和 `test`|扩展排除项|
|特定文件夹下的任何文件|文件夹下 `c:\test\sample` 的所有文件|文件和文件夹排除项|
|特定文件夹中的特定文件|仅限文件`c:\sample\sample.test`|文件和文件夹排除项|
|特定进程|可执行文件 `c:\test\process.exe`|文件和文件夹排除项|

## <a name="characteristics-of-exclusion-lists"></a>排除列表的特征

- 文件夹排除项适用于该文件夹下的所有文件和文件夹，除非子文件夹是重新分析点。 必须单独排除重新分析点子文件夹。
- 如果未定义路径或文件夹，文件扩展名将应用于具有定义扩展名的任何文件名。

## <a name="important-notes-about-exclusions-based-on-file-extensions-and-folder-locations"></a>有关基于文件扩展名和文件夹位置的排除的重要说明

- 使用星号等通配符 () \* 将更改排除规则的解释方式。 有关通配符工作原理的重要信息，请参阅 [文件名和文件夹路径或扩展排除列表部分中的“使用通配](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 符”。

- 不要排除映射的网络驱动器。 指定实际的网络路径。

- 在Microsoft Defender 防病毒服务启动并已添加到排除列表后创建的重新分析点的文件夹将不包括在内。 重启服务 (，重启Windows) 以将新的重新分析点识别为有效的排除目标。

- 排除项适用于 [计划的扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、 [按需扫描](run-scan-microsoft-defender-antivirus.md)和 [实时保护](configure-real-time-protection-microsoft-defender-antivirus.md)，但不适用于 Defender for Endpoint。 若要跨 Defender for Endpoint 定义排除项，请使用 [自定义指示器](manage-indicators.md)。

- 默认情况下，具有管理员权限的用户对列表 (进行的本地更改（包括使用 PowerShell 和 WMI) 所做的更改）将与组策略、Configuration Manager 或Intune定义的 (和部署) 的列表合并。 出现冲突时，组策略列表优先。 此外，使用组策略进行的排除列表更改在[Windows 安全中心应用](microsoft-defender-security-center-antivirus.md)中可见。

- 若要允许本地更改替代托管部署设置， [请配置本地和全局定义排除列表的合并方式](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists)。

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a>根据文件夹名称或文件扩展名配置排除列表

可以从多种方法中进行选择，为Microsoft Defender 防病毒定义排除项。

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用Intune配置文件名、文件夹或文件扩展名排除项

另请参阅以下文章：

- [在 Microsoft Intune 中配置设备限制设置](/intune/device-restrictions-configure)
- [Microsoft Defender 防病毒Intune中Windows 10的设备限制设置](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用Configuration Manager配置文件名、文件夹或文件扩展名排除项

有关配置 Microsoft Endpoint Manager (当前分支) 的详细信息，请参阅[如何创建和部署反恶意软件策略：排除设置](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)。

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a>使用组策略配置文件夹或文件扩展名排除项

> [!NOTE]
> 如果指定文件的完全限定路径，则仅排除该文件。 如果在排除项中定义了一个文件夹，则排除该文件夹下的所有文件和子目录。

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后选择 **编辑**。

2. 在 **组策略管理编辑器** 转到 **计算机配置** 并选择 **管理模板**。

3. 将树展开为Microsoft Defender 防病毒 **排除** 项 **Windows** \> **组件**\>。

4. 打开 **路径排除设置** 进行编辑，并添加排除项。
    1. 将选项设置为 **“已启用**”。
    2. 在 **“选项”** 部分下，选择 **“显示**”。
    3. 在“ **值名称** ”列下的自身行上指定每个文件夹。
    4. 如果要指定文件，请确保输入文件的完全限定路径，包括驱动器号、文件夹路径、文件名和扩展名。
    5. 在 **“值**”列中输入 **0**。

5. 选择“**确定**”。

6. 打开 **“扩展排除项** ”设置进行编辑并添加排除项。
    1. 将选项设置为 **“已启用**”。
    2. 在 **“选项”** 部分下，选择 **“显示**”。
    3. 在“ **值名称** ”列下，在其自己的行上输入每个文件扩展名。
    4. 在 **“值**”列中输入 **0**。

7. 选择“**确定**”。

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用 PowerShell cmdlet 配置文件名、文件夹或文件扩展名排除项

使用 PowerShell 根据扩展名、位置或文件名添加或删除文件的排除项需要使用三个 cmdlet 和适当的排除列表参数的组合。 cmdlet 全部在 [Defender 模块](/powershell/module/defender/)中。

cmdlet 的格式如下所示：

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

下表列出了可在 PowerShell cmdlet 部分使用的 `<cmdlet>` cmdlet：

|配置操作|PowerShell cmdlet|
|:---|:---|
|创建或覆盖列表|`Set-MpPreference`|
|添加到列表|`Add-MpPreference`|
|从列表中删除项|`Remove-MpPreference`|

下表列出了可以在 PowerShell cmdlet 部分使用的 `<exclusion list>` 值：

|排除类型|PowerShell 参数|
|---|---|
|具有指定文件扩展名的所有文件|`-ExclusionExtension`|
|文件夹下的所有文件 (包括子目录) 或特定文件中的文件|`-ExclusionPath`|

> [!IMPORTANT]
> 如果已使用或`Add-MpPreference`再次使用`Set-MpPreference`该 cmdlet 创建了一个列表`Set-MpPreference`，则会覆盖现有列表。

例如，以下代码片段将导致Microsoft Defender 防病毒扫描排除具有文件扩展名的任何文件`.test`：

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

> [!TIP]
> 有关详细信息，请参阅[使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)和 [Defender for Cloud cmdlet](/powershell/module/defender/)。

### <a name="use-windows-management-instrumentation-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用 Windows Management Instrumentation (WMI) 配置文件名、文件夹或文件扩展名排除项

对以下属性使用 [MSFT_MpPreference类的 Set、Add 和 Remove 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
ExclusionExtension
ExclusionPath
```

使用 **Set**、**Add** 和 **Remove** 类似于 PowerShell 中的对应项： `Set-MpPreference`和 `Add-MpPreference``Remove-MpPreference`.

> [!TIP]
> 有关详细信息，请参阅[Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用Windows 安全中心应用配置文件名、文件夹或文件扩展名排除项

有关说明，请参阅[Windows 安全中心应用中的“添加排除](microsoft-defender-security-center-antivirus.md)项”。

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>在文件名和文件夹路径或扩展排除列表中使用通配符

在文件名或文件夹路径排除列表中定义项时，可以使用星号 `*`、问号 `?`或环境变量 (（例如 `%ALLUSERSPROFILE%`) 作为通配符）。 这些通配符的解释方式不同于它们在其他应用和语言中通常的用法。 请务必阅读此部分，了解其特定限制。

> [!IMPORTANT]
> 这些通配符存在主要限制和使用方案：
>
> - 环境变量使用仅限于计算机变量和适用于以 NT AUTHORITY\SYSTEM 帐户运行的进程的变量。
> - 每个条目最多只能使用六个通配符。
> - 不能使用通配符来代替驱动器号。
> - 文件夹排除中的星号 `*` 为单个文件夹就位。 使用多个实例 `\*\` 指示多个具有未指定名称的嵌套文件夹。
> - 目前，Microsoft Endpoint Configuration Manager不支持通配符 (，例如`*`或`?`) 。
    
下表介绍了如何使用通配符，并提供了一些示例。

<br/><br/>

|通配符|示例|
|---|---|
|`*` (星号)  <p> 在 **文件名和文件扩展名包含中**，星号将替换任意数量的字符，并且仅适用于参数中定义的最后一个文件夹中的文件。 <p> 在 **文件夹排除项** 中，星号将替换单个文件夹。 将多个 `*` 文件夹斜杠 `\` 用于指示多个嵌套文件夹。 匹配通配符和命名文件夹的数目后，还包含所有子文件夹。|`C:\MyData\*.txt` 包括 `C:\MyData\notes.txt` <p> `C:\somepath\*\Data` 包括任何文件及其 `C:\somepath\Archives\Data` 子文件夹 `C:\somepath\Authorized\Data` 及其子文件夹 <p> `C:\Serv\*\*\Backup` 包括任何文件及其 `C:\Serv\Primary\Denied\Backup` 子文件夹 `C:\Serv\Secondary\Allowed\Backup` 及其子文件夹|
|`?` (问号)   <p> 在 **文件名和文件扩展名包含中**，问号将替换单个字符，并且仅适用于参数中定义的最后一个文件夹中的文件。 <p> 在 **文件夹排除项** 中，问号替换文件夹名称中的单个字符。 匹配通配符和命名文件夹的数目后，还包含所有子文件夹。|`C:\MyData\my?.zip` 包括 `C:\MyData\my1.zip` <p> `C:\somepath\?\Data` 包括任何文件及其 `C:\somepath\P\Data` 子文件夹  <p> `C:\somepath\test0?\Data` 将包含任何文件及其 `C:\somepath\test01\Data` 子文件夹|
|环境变量 <p> 计算排除项时，定义的变量将填充为路径。|`%ALLUSERSPROFILE%\CustomLogFiles` 将包括 `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`|

> [!IMPORTANT]
> 如果将文件排除参数与文件夹排除参数混合使用，则规则将停止匹配文件夹中的文件参数匹配，并且不会在任何子文件夹中查找文件匹配项。
>
> 例如，可以排除文件夹 `c:\data\final\marked` 中以“date”开头的所有文件，并 `c:\data\review\marked` 使用规则参数 `c:\data\*\marked\date*`。
>
> 但是，此参数与子`c:\data\final\marked`文件夹中的任何文件都不匹配。`c:\data\review\marked`

<a id="review"></a>

### <a name="system-environment-variables"></a>系统环境变量

下表列出并描述了系统帐户环境变量。

|此系统环境变量...|重定向到此|
|---|---|
|`%APPDATA%`|`C:\Users\UserName.DomainName\AppData\Roaming`|
|`%APPDATA%\Microsoft\Internet Explorer\Quick Launch`|`C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch`|
|`%APPDATA%\Microsoft\Windows\Start Menu`|`C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu`|
|`%APPDATA%\Microsoft\Windows\Start Menu\Programs`|`C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs`|
|`%LOCALAPPDATA%`|`C:\Windows\System32\config\systemprofile\AppData\Local`|
|`%ProgramData%`|`C:\ProgramData`|
|`%ProgramFiles%`|`C:\Program Files`|
|`%ProgramFiles%\Common Files`|`C:\Program Files\Common Files`|
|`%ProgramFiles%\Windows Sidebar\Gadgets`|`C:\Program Files\Windows Sidebar\Gadgets`|
|`%ProgramFiles%\Common Files`|`C:\Program Files\Common Files`|
|`%ProgramFiles(x86)%`|`C:\Program Files (x86)`|
|`%ProgramFiles(x86)%\Common Files`|`C:\Program Files (x86)\Common Files`|
|`%SystemDrive%`|`C:`|
|`%SystemDrive%\Program Files`|`C:\Program Files`|
|`%SystemDrive%\Program Files (x86)`|`C:\Program Files (x86)`|
|`%SystemDrive%\Users`|`C:\Users`|
|`%SystemDrive%\Users\Public`|`C:\Users\Public`|
|`%SystemRoot%`|`C:\Windows`|
|`%windir%`|`C:\Windows`|
|`%windir%\Fonts`|`C:\Windows\Fonts`|
|`%windir%\Resources`|`C:\Windows\Resources`|
|`%windir%\resources\0409`|`C:\Windows\resources\0409`|
|`%windir%\system32`|`C:\Windows\System32`|
|`%ALLUSERSPROFILE%`|`C:\ProgramData`|
|`%ALLUSERSPROFILE%\Application Data`|`C:\ProgramData\Application Data`|
|`%ALLUSERSPROFILE%\Documents`|`C:\ProgramData\Documents`|
|`%ALLUSERSPROFILE%\Documents\My Music\Sample Music`|`C:\ProgramData\Documents\My Music\Sample Music`|
|`%ALLUSERSPROFILE%\Documents\My Music`|`C:\ProgramData\Documents\My Music`|
|`%ALLUSERSPROFILE%\Documents\My Pictures`|`C:\ProgramData\Documents\My Pictures`|
|`%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures`|`C:\ProgramData\Documents\My Pictures\Sample Pictures`|
|`%ALLUSERSPROFILE%\Documents\My Videos`|`C:\ProgramData\Documents\My Videos`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore`|`C:\ProgramData\Microsoft\Windows\DeviceMetadataStore`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer`|`C:\ProgramData\Microsoft\Windows\GameExplorer`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones`|`C:\ProgramData\Microsoft\Windows\Ringtones`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu`|`C:\ProgramData\Microsoft\Windows\Start Menu`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs`|`C:\ProgramData\Microsoft\Windows\Start Menu\Programs`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools`|`C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp`|`C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Templates`|`C:\ProgramData\Microsoft\Windows\Templates`|
|`%ALLUSERSPROFILE%\Start Menu`|`C:\ProgramData\Start Menu`|
|`%ALLUSERSPROFILE%\Start Menu\Programs`| `C:\ProgramData\Start Menu\Programs`|
|`%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools`|`C:\ProgramData\Start Menu\Programs\Administrative Tools`|
|`%ALLUSERSPROFILE%\Templates`|`C:\ProgramData\Templates`|
|`%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates`|`C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates`|
|`%LOCALAPPDATA%\Microsoft\Windows\History`|`C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History`|
|`%PUBLIC%`|`C:\Users\Public`|
|`%PUBLIC%\AccountPictures`|`C:\Users\Public\AccountPictures`|
|`%PUBLIC%\Desktop`|`C:\Users\Public\Desktop`|
|`%PUBLIC%\Documents`|`C:\Users\Public\Documents`|
|`%PUBLIC%\Downloads`|`C:\Users\Public\Downloads`|
|`%PUBLIC%\Music\Sample Music`|`C:\Users\Public\Music\Sample Music`|
|`%PUBLIC%\Music\Sample Playlists`|`C:\Users\Public\Music\Sample Playlists`|
|`%PUBLIC%\Pictures\Sample Pictures`|`C:\Users\Public\Pictures\Sample Pictures`|
|`%PUBLIC%\RecordedTV.library-ms`|`C:\Users\Public\RecordedTV.library-ms`|
|`%PUBLIC%\Videos`|`C:\Users\Public\Videos`|
|`%PUBLIC%\Videos\Sample Videos`|`C:\Users\Public\Videos\Sample Videos`|
|`%USERPROFILE%`|`C:\Users\UserName`|
|`%USERPROFILE%\AppData\Local`|`C:\Users\UserName\AppData\Local`|
|`%USERPROFILE%\AppData\LocalLow`|`C:\Users\UserName\AppData\LocalLow`|
|`%USERPROFILE%\AppData\Roaming`|`C:\Users\UserName\AppData\Roaming`|

## <a name="review-the-list-of-exclusions"></a>查看排除项列表

可以使用以下方法之一检索排除列表中的项：

- [Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- [MpCmdRun](command-line-arguments-microsoft-defender-antivirus.md)
- [PowerShell](/powershell/module/defender)
- [Windows 安全中心应用](microsoft-defender-security-center-antivirus.md)

> [!IMPORTANT]
> 使用组策略进行的排除列表更改 **将显示** 在 [Windows 安全中心应用](microsoft-defender-security-center-antivirus.md)的列表中。
>
> Windows 安全中心应用中所做的更改 **不会显示** 在组策略列表中。

如果使用 PowerShell，可以通过两种方式检索列表：

- 检索所有Microsoft Defender 防病毒首选项的状态。 每个列表显示在单独的行上，但每个列表中的项合并到同一行中。
- 将所有首选项的状态写入变量，并使用该变量仅调用感兴趣的特定列表。 每种 `Add-MpPreference` 用途都写入新行。

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>使用 MpCmdRun 验证排除列表

若要使用专用 [命令行工具mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md)检查排除项，请使用以下命令：

```console
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.2111-5.0 (Where 4.18.2111-5.0 is this month's Microsoft Defender Antivirus "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> 使用 MpCmdRun 检查排除项需要Microsoft Defender 防病毒 2021 年 12 月) 或更高版本发布的 CAMP 版本 4.18.211-5.0 (。

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>使用 PowerShell 查看排除项列表以及所有其他Microsoft Defender 防病毒首选项

使用以下 cmdlet：

```PowerShell
Get-MpPreference
```

在以下示例中，突出显示了列表中包含的项目 `ExclusionExtension` ：

:::image type="content" source="../../media/wdav-powershell-get-exclusions-variable.png" alt-text="Get-MpPreference 的 PowerShell 输出" lightbox="../../media/wdav-powershell-get-exclusions-variable.png":::

有关详细信息，请参阅[使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)和 [Defender for Cloud cmdlet](/powershell/module/defender/)。

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>使用 PowerShell 检索特定的排除项列表

使用以下代码片段 (输入每行作为单独的命令) ;将 **WDAVprefs** 替换为要命名变量的任何标签：

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

在以下示例中，该列表将拆分为每使用 `Add-MpPreference` cmdlet 的新行：

:::image type="content" source="../../media/wdav-powershell-get-exclusions-variable.png" alt-text="PowerShell 输出仅显示排除列表中的条目" lightbox="../../media/wdav-powershell-get-exclusions-variable.png":::

有关详细信息，请参阅[使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)和 [Defender for Cloud cmdlet](/powershell/module/defender/)。

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>使用 EICAR 测试文件验证排除项列表

通过将 PowerShell 与 `Invoke-WebRequest` cmdlet 或 .NET WebClient 类配合使用来下载测试文件，可以验证排除列表是否正常工作。

在以下 PowerShell 代码片段中，替换 `test.txt` 为符合排除规则的文件。 例如，如果已排除 `.testing` 扩展，请替换 `test.txt` 为 `test.testing`。 如果要测试路径，请确保在该路径中运行 cmdlet。

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

如果Microsoft Defender 防病毒报告恶意软件，则规则不起作用。 如果没有恶意软件报告且已下载的文件存在，则排除操作正常。 可以打开文件以确认内容与 [EICAR 测试文件网站上](http://www.eicar.org/86-0-Intended-use.html)所述的内容相同。

还可以使用以下 PowerShell 代码，该代码调用 .NET WebClient 类来下载测试文件 ，如 cmdlet 一样 `Invoke-WebRequest` ;替换 `c:\test.txt` 为符合你正在验证的规则的文件：

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

如果没有 Internet 访问权限，可以通过使用以下 PowerShell 命令将 EICAR 字符串写入新文本文件来创建自己的 EICAR 测试文件：

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

还可以将字符串复制到空白文本文件中，并尝试使用文件名或尝试排除的文件夹保存该字符串。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="see-also"></a>另请参阅

- [在Microsoft Defender 防病毒扫描中配置和验证排除项](configure-exclusions-microsoft-defender-antivirus.md)
- [配置和验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [在Windows服务器上配置Microsoft Defender 防病毒排除项](configure-server-exclusions-microsoft-defender-antivirus.md)
- [定义排除时要避免的常见错误](common-exclusion-mistakes-microsoft-defender-antivirus.md)
