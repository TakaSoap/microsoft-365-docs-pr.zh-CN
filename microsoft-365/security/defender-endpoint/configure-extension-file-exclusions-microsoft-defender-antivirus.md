---
title: 根据扩展名、名称或位置配置和验证排除项
description: 根据文件Microsoft Defender 防病毒文件扩展名、文件名或位置，从扫描中排除文件。
keywords: 排除项， 文件， 扩展名， 文件类型， 文件夹名称， 文件名， 扫描
search.product: eADQiWindows 10XVcnh
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
ms.date: 10/25/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: f31af157470a64984968f2a7befd23aab7af37e0
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60588217"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a>根据文件扩展名和文件夹位置配置和验证排除项

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 防病毒

你可以定义适用于Microsoft Defender 防病毒扫描、按需扫描以及始终打开、[](schedule-antivirus-scans.md)实时保护和监视[的扫描的排除项](configure-real-time-protection-microsoft-defender-antivirus.md)。 [](run-scan-microsoft-defender-antivirus.md) **通常，你无需应用排除项**。 如果需要应用排除项，可以从多种不同类型的选项中选择：

- 本文介绍的基于文件扩展名和 (位置的) 
- [进程打开的文件排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

> [!IMPORTANT]
> Microsoft Defender 防病毒不适用于其他 Microsoft Defender for Endpoint 功能，包括终结点检测和响应[ (EDR) 、](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)攻击面减少[ (ASR) ](/microsoft-365/security/defender-endpoint/attack-surface-reduction)规则和受控文件夹[访问权限。](/microsoft-365/security/defender-endpoint/controlled-folders) 使用本文中所述的方法排除的文件仍可以触发EDR检测。
> 若要广泛排除文件，请将它们添加到 Microsoft Defender for Endpoint [自定义指示器](/microsoft-365/security/defender-endpoint/manage-indicators)。

## <a name="before-you-begin"></a>开始之前...

请参阅[推荐定义排除](configure-exclusions-microsoft-defender-antivirus.md)项，然后再定义排除列表。

## <a name="exclusion-lists"></a>排除列表

若要从扫描中排除Microsoft Defender 防病毒，请修改排除列表。 Microsoft Defender 防病毒许多基于已知操作系统行为和典型管理文件（如在企业管理、数据库管理以及其他企业方案和情况中使用的文件）的自动排除项。

> [!NOTE]
> 排除项也适用于可能不需要 (PUA) 检测。
>
> 自动排除项仅适用于Windows Server 2016及更高版本。 这些排除项在 Windows 安全中心和 PowerShell 中不可见。

下表列出了一些基于文件扩展名和文件夹位置的排除示例。 
<br/><br/>

|排除|示例|排除列表|
|---|---|---|
|具有特定扩展名的任何文件|计算机上任意位置具有指定扩展名的所有文件。 <p> 有效语法： `.test` 和 `test`|扩展排除项|
|特定文件夹下的任何文件|文件夹下的所有 `c:\test\sample` 文件|文件和文件夹排除项|
|特定文件夹中的特定文件|仅 `c:\sample\sample.test` 文件|文件和文件夹排除项|
|特定过程|可执行文件 `c:\test\process.exe`|文件和文件夹排除项|

## <a name="characteristics-of-exclusion-lists"></a>排除列表的特征

- 文件夹排除项适用于该文件夹下的所有文件和文件夹，除非子文件夹是重新分析点。 必须单独排除重新分析点子文件夹。
- 如果未定义路径或文件夹，则文件扩展名将应用于具有定义扩展名的任何文件名。

## <a name="important-notes-about-exclusions-based-on-file-extensions-and-folder-locations"></a>有关基于文件扩展名和文件夹位置的排除项的重要说明

- 使用通配符（如星号 () \* 将改变排除规则的解释方式。 有关 [通配符如何工作的](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 重要信息，请参阅在文件名和文件夹路径或扩展名排除列表中使用通配符部分。

- 不要排除映射的网络驱动器。 指定实际网络路径。

- 不包括重新分析在启动 Microsoft Defender 防病毒 服务后创建且已添加到排除列表的文件夹。 重新启动服务 (重新启动Windows) 可识别为有效排除目标的新重新分析点。

- 排除项适用于 [计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、按需 [扫描](run-scan-microsoft-defender-antivirus.md)和实时 [保护](configure-real-time-protection-microsoft-defender-antivirus.md)，但不能跨 Defender for Endpoint。 若要定义跨 Defender for Endpoint 的排除项，请使用 [自定义指示器](manage-indicators.md)。

- 默认情况下，具有管理员权限的用户对 (列表进行的本地更改（包括使用 PowerShell 和 WMI) 所做的更改）将与 (定义的列表合并，并按组策略、Configuration Manager 或 Intune 部署) 。 存在冲突时，组策略列表优先。 此外，使用组策略进行排除列表更改在应用Windows 安全中心[可见](microsoft-defender-security-center-antivirus.md)。

- 若要允许本地更改覆盖托管部署设置，请配置合并本地和全局定义的 [排除列表的方式](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists)。

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a>根据文件夹名称或文件扩展名配置排除项列表

可以从多种方法中选择来定义用于Microsoft Defender 防病毒。

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用 Intune 配置文件名、文件夹或文件扩展名排除项

另请参阅以下文章：

- [配置设备限制Microsoft Intune](/intune/device-restrictions-configure)
- [Microsoft Defender 防病毒 Intune 中Windows 10设备限制设置](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用 Configuration Manager 配置文件名、文件夹或文件扩展名排除项

请参阅[如何创建和部署反恶意软件策略：](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)排除设置，详细了解如何Microsoft Endpoint Manager (当前分支) 。

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a>使用组策略配置文件夹或文件扩展名排除项

> [!NOTE]
> 如果指定文件的完全限定路径，则仅排除该文件。 如果在排除中定义了文件夹，则排除该文件夹下的所有文件和子目录。

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后选择 **编辑**。

2. 在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后选择 **管理模板**。

3. 展开树以 **Windows排除** \> **Microsoft Defender 防病毒** \> **组件**。

4. 打开 **"路径排除项** "设置进行编辑，并添加排除项。
    1. 将选项设置为 **已启用**。
    2. 在"**选项"** 部分下，选择"显示 **"。**
    3. 在"值名称"列下的其自己的 **行中指定每个** 文件夹。
    4. 如果要指定文件，请确保输入该文件的完全限定路径，包括驱动器号、文件夹路径、文件名和扩展名。 在 **"值"****列中输入** 0。

5. 选择“**确定**”。

6. 打开 **扩展排除** 项设置进行编辑并添加排除项。
    1. 将选项设置为 **已启用**。
    2. 在"**选项"** 部分下，选择"显示 **"。**
    3. 在"值"列中的"值名称 **columnEnter** **0"** 下，在其自己的行中输入每个 **文件** 扩展名。

7. 选择“**确定**”。

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用 PowerShell cmdlet 配置文件名、文件夹或文件扩展名排除项

使用 PowerShell 添加或删除基于扩展名、位置或文件名的文件排除项需要结合使用三个 cmdlet 和相应的排除列表参数。 cmdlet 全部在 Defender [模块中](/powershell/module/defender/)。

cmdlet 的格式如下：

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

下表列出了可在 PowerShell cmdlet 部分使用的 `<cmdlet>` cmdlet：

<br/><br/>

|配置操作|PowerShell cmdlet|
|:---|:---|
|创建或覆盖列表|`Set-MpPreference`|
|添加到列表|`Add-MpPreference`|
|从列表中删除项目|`Remove-MpPreference`|

下表列出了可在 `<exclusion list>` PowerShell cmdlet 部分使用的值：

<br/><br/>

|排除类型|PowerShell 参数|
|---|---|
|具有指定文件扩展名的所有文件|`-ExclusionExtension`|
|文件夹下的所有文件 (包括子目录中的文件) 或特定文件|`-ExclusionPath`|

> [!IMPORTANT]
> 如果已使用 或 创建列表， `Set-MpPreference` `Add-MpPreference` 则再次使用 `Set-MpPreference` cmdlet 将覆盖现有列表。

例如，以下代码段将导致Microsoft Defender 防病毒扫描排除具有文件扩展 `.test` 名的任何文件：

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

> [!TIP]
> 有关详细信息，请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)和 [Defender cmdlet](/powershell/module/defender/)。

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用 Windows Management Instruction (WMI) 配置文件名、文件夹或文件扩展名排除项

对 [以下属性使用 MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 类的 Set、Add 和 Remove 方法：

```WMI
ExclusionExtension
ExclusionPath
```

使用 **Set、Add** 和 **Remove** 与 PowerShell 中的对应类类似 `Set-MpPreference` ：、 和 `Add-MpPreference` `Remove-MpPreference` 。

> [!TIP]
> 有关详细信息，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用Windows 安全中心配置文件名、文件夹或文件扩展名排除项

有关[说明，请参阅Windows 安全中心应用添加](microsoft-defender-security-center-antivirus.md)排除项。

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>在文件名和文件夹路径或扩展名排除列表中使用通配符

在文件名或文件夹路径排除列表中定义项目时 (星号、问号或环境变量（如 `*` `?` `%ALLUSERSPROFILE%`) ）用作通配符。 解释这些通配符的方式与其他应用和语言中的常用用法不同。 请务必阅读本节以了解其特定限制。

> [!IMPORTANT]
> 这些通配符存在一些关键限制和使用方案：
>
> - 环境变量的使用仅限于计算机变量和那些适用于作为 NT AUTHORITY\SYSTEM 帐户运行的进程。
> - 不能使用通配符来表示驱动器号。
> - 文件夹排除中的 `*` 星号代表单个文件夹。 使用多个实例指示具有未指定 `\*\` 名称的多个嵌套文件夹。
> - 目前，Microsoft Endpoint Configuration Manager不支持通配符 (如 `*` 或 `?`) 。
    
下表介绍了如何使用通配符，并提供了一些示例。

<br/><br/>

|通配符|示例|
|---|---|
|`*` (星号)  <p> 在 **文件名和文件** 扩展名包含中，星号将替换任意数目的字符，并且仅适用于参数中定义的最后一个文件夹中的文件。 <p> 在 **文件夹排除** 中，星号将替换单个文件夹。 将 multiple `*` 与文件夹斜杠 `\` 一同使用，以指示多个嵌套文件夹。 匹配通配符和命名文件夹的数量后，还将包含所有子文件夹。|`C:\MyData\*.txt` 包括 `C:\MyData\notes.txt` <p> `C:\somepath\*\Data` 包括 及其 `C:\somepath\Archives\Data` 子文件夹及其 `C:\somepath\Authorized\Data` 子文件夹内的任何文件 <p> `C:\Serv\*\*\Backup` 包括 及其 `C:\Serv\Primary\Denied\Backup` 子文件夹及其 `C:\Serv\Secondary\Allowed\Backup` 子文件夹内的任何文件|
|`?` (问号)   <p> 在 **文件名和文件扩展名包含** 中，问号将替换单个字符，并且仅适用于参数中定义的最后一个文件夹中的文件。 <p> 在 **文件夹排除** 中，问号替换文件夹名称中的单个字符。 匹配通配符和命名文件夹的数量后，还将包含所有子文件夹。|`C:\MyData\my?.zip` 包括 `C:\MyData\my1.zip` <p> `C:\somepath\?\Data` 包括 及其 `C:\somepath\P\Data` 子文件夹内的任何文件  <p> `C:\somepath\test0?\Data` 将包含 及其 `C:\somepath\test01\Data` 子文件夹内的任何文件|
|环境变量 <p> 在计算排除时，定义的变量将填充为路径。|`%ALLUSERSPROFILE%\CustomLogFiles` 将包括 `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`|

> [!IMPORTANT]
> 如果将文件排除参数与文件夹排除参数混合，则规则将在匹配文件夹中的 file 参数匹配时停止，并且不会在任何子文件夹中查找文件匹配项。
>
> 例如，可以使用规则参数 排除文件夹中以"date"开始的所有 `c:\data\final\marked` `c:\data\review\marked` 文件 `c:\data\*\marked\date*` 。
>
> 但是，此参数与 或 下的子文件夹内的任何文件 `c:\data\final\marked` 都不匹配 `c:\data\review\marked` 。

<a id="review"></a>

### <a name="system-environment-variables"></a>系统环境变量

下表列出并描述了系统帐户环境变量。
    <br/><br/>
    
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

您可以使用以下方法之一检索排除列表中的项：

- [Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- MpCmdRun
- PowerShell
- [Windows 安全中心应用](microsoft-defender-security-center-antivirus.md)

> [!IMPORTANT]
> 使用组策略进行排除列表 **更改将显示在** 应用Windows 安全中心 [列表中](microsoft-defender-security-center-antivirus.md)。
>
> 在组策略Windows 安全中心 **中所做的更改** 将不会显示在组策略列表中。

如果使用 PowerShell，可以通过两种方式检索列表：

- 检索所有首选项Microsoft Defender 防病毒状态。 每个列表显示在单独的行上，但每个列表中的项组合到同一行中。
- 将所有首选项的状态写入变量，并使用该变量仅调用您感兴趣的特定列表。 每次使用 `Add-MpPreference` 都写入新行。

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>使用 MpCmdRun 验证排除列表

若要检查专用命令行工具 [的 ](./command-line-arguments-microsoft-defender-antivirus.md)排除mpcmdrun.exe，请使用以下命令：

```DOS
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.2110-3.0 (Where 4.18.2110-3.0 is this month's Microsoft Defender Antivirus "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> 检查 MpCmdRun 的排除项需要 Microsoft Defender 防病毒 CAMP 版本 4.18.2110-3.0 (2021 年 10 月) 或更高版本。

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>使用 PowerShell 查看所有其他首选项Microsoft Defender 防病毒列表

使用以下 cmdlet：

```PowerShell
Get-MpPreference
```

在下面的示例中，突出显示了列表中包含的 `ExclusionExtension` 项：

:::image type="content" source="../../media/wdav-powershell-get-exclusions-variable.png" alt-text="Get-MpPreference 的 PowerShell 输出。":::

有关详细信息，请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)和 [Defender cmdlet](/powershell/module/defender/)。

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>使用 PowerShell 检索特定排除项列表

使用以下代码段 (代码段作为单独的命令代码段输入) ;将 **WDAVprefs** 替换为要命名变量的任何标签：

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

在下面的示例中，列表将拆分为每次使用 `Add-MpPreference` cmdlet 的新行：

:::image type="content" source="../../media/wdav-powershell-get-exclusions-variable.png" alt-text="仅显示排除列表中的条目的 PowerShell 输出。":::

有关详细信息，请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)和 [Defender cmdlet](/powershell/module/defender/)。

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>使用 EICAR 测试文件验证排除列表

可以通过将 PowerShell 与 cmdlet 或 .NET WebClient 类一同使用来下载测试文件，来验证排除列表 `Invoke-WebRequest` 是否正常工作。

在下面的 PowerShell 代码段中，将 替换为 `test.txt` 符合排除规则的文件。 例如，如果已排除扩展 `.testing` ，请将 替换为 `test.txt` `test.testing` 。 如果要测试路径，请确保在此路径内运行 cmdlet。

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

如果Microsoft Defender 防病毒报告恶意软件，则规则无法工作。 如果没有任何恶意软件报告且下载的文件存在，则排除将正常工作。 你可以打开文件以确认内容与 EICAR 测试文件网站上 [介绍的内容相同](http://www.eicar.org/86-0-Intended-use.html)。

您还可以使用以下 PowerShell 代码，该代码调用 .NET WebClient 类以下载测试文件（与 cmdlet 一样）;将 替换为符合要验证的规则 `Invoke-WebRequest` `c:\test.txt` 的文件：

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

如果你没有 Internet 访问权限，可以通过以下 PowerShell 命令将 EICAR 字符串写入新的文本文件来创建你自己的 EICAR 测试文件：

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

还可以将字符串复制到空白文本文件中，并尝试使用文件名或试图排除的文件夹中保存它。

## <a name="see-also"></a>另请参阅

- [配置并验证扫描中的Microsoft Defender 防病毒项](configure-exclusions-microsoft-defender-antivirus.md)
- [配置并验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [在 Microsoft Defender 防病毒 服务器上配置Windows排除项](configure-server-exclusions-microsoft-defender-antivirus.md)
- [定义排除时要避免的常见错误](common-exclusion-mistakes-microsoft-defender-antivirus.md)
