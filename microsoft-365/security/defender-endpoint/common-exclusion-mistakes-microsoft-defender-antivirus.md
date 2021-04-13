---
title: 定义排除项时应避免的常见错误
description: 避免在定义 Microsoft Defender 防病毒扫描的排除项时出现常见错误。
keywords: 排除项， 文件， 扩展名， 文件类型， 文件夹名称， 文件名， 扫描
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
ms.openlocfilehash: d14e37c8f3cfdfe8d88bfd4e255a431fbb8d6d41
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689953"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>定义排除项时应避免的常见错误

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

你可以为不希望 Microsoft Defender 防病毒扫描的项目定义排除列表。 此类排除项目可能包含使设备易受攻击的威胁。 

本文介绍定义排除项时应避免的一些常见错误。 

定义排除列表之前，请参阅 [用于定义排除项的建议](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)。

## <a name="excluding-certain-trusted-items"></a>排除某些受信任的项目

某些文件、文件类型、文件夹或进程不应从扫描中排除，即使你信任它们不是恶意文件。 

不要为下表中列出的文件夹位置、文件扩展名和进程定义排除项：

| 文件夹位置 | 文件扩展名 | 进程 |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> `bginfo.exe`[1] <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> `msbuild.exe`[2] <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> 可以选择排除文件类型，如 、，或者如果您的环境具有现代、最新的软件，具有严格的更新策略来处理 `.gif` `.jpg` `.jpeg` `.png` 任何漏洞。

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>仅使用排除列表中的文件名

恶意软件可能与受信任的文件同名，并且想要从扫描中排除。 因此，为了避免从扫描中排除潜在的恶意软件，请使用要排除的文件的完全限定路径，而不只是使用文件名。 例如，如果要从扫描 `Filename.exe` 中排除，请使用文件的完整路径，例如 `C:\program files\contoso\Filename.exe` 。

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>将单个排除列表用于多个服务器工作负载

请勿使用单个排除列表来定义多个服务器工作负荷的排除项。 将不同应用程序或服务工作负荷的排除项拆分为多个排除列表。 例如，IIS 服务器工作负荷的排除列表必须不同于您的 IIS 服务器工作负荷的排除SQL Server列表。

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>在文件名和文件夹路径或扩展名排除列表中将不正确的环境变量用作通配符

Microsoft Defender 防病毒服务使用 LocalSystem 帐户在系统上下文中运行，这意味着它从系统环境变量而不是用户环境变量获取信息。 将环境变量用作排除列表的通配符仅限于系统变量和那些适用于作为 NT AUTHORITY\SYSTEM 帐户运行的进程。 因此，添加 Microsoft Defender 防病毒文件夹和进程排除项时，不要将用户环境变量用作通配符。 有关系统环境变量 [的完整](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 列表，请参阅系统环境变量下的表。

请参阅 [在文件名和文件夹路径](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 或扩展名排除列表中使用通配符，了解如何在排除列表中使用通配符。

## <a name="related-articles"></a>相关文章

- [配置并验证 Microsoft Defender 防病毒扫描中的排除项](configure-exclusions-microsoft-defender-antivirus.md)
- [根据文件扩展名和文件夹位置配置和验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [配置并验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [在 Windows Server 上配置 Microsoft Defender 防病毒排除项](configure-server-exclusions-microsoft-defender-antivirus.md)
