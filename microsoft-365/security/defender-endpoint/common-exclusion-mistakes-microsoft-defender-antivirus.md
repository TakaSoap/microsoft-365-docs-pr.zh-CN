---
title: 定义排除时要避免的常见错误
description: 为扫描定义排除项时，Microsoft Defender 防病毒错误。
keywords: 排除项， 文件， 扩展名， 文件类型， 文件夹名称， 文件名， 扫描
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
ms.topic: article
ms.date: 10/19/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 625b5dc2743f42d35a652582827454b3178e1786
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60881933"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>定义排除时要避免的常见错误

你可以为不希望扫描的项目定义排除Microsoft Defender 防病毒列表。 此类排除项目可能包含使设备易受攻击的威胁。 本文介绍定义排除项时应避免的一些常见错误。

定义排除列表之前，请参阅推荐[排除项。](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)

## <a name="excluding-certain-trusted-items"></a>排除某些受信任的项目

某些文件、文件类型、文件夹或进程不应从扫描中排除，即使你信任它们不是恶意文件。

不要为以下部分中列出的文件夹位置、文件扩展名和进程定义排除项：
- 文件夹位置
- 文件扩展名
- 进程

### <a name="folder-locations"></a>文件夹位置

通常，不要为以下文件夹位置定义排除项：

`%systemdrive%`

`C:`

`C:\`

`C:\*`

`%ProgramFiles%\Java`

`C:\Program Files\Java`

`%ProgramFiles%\Contoso\`

`C:\Program Files\Contoso\`

`%ProgramFiles(x86)%\Contoso\`

`C:\Program Files (x86)\Contoso\`

`C:\Temp`

`C:\Temp\`

`C:\Temp\*`

`C:\Users\`

`C:\Users\*`

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**请注意以下例外情况SharePoint：** 在文件级别防病毒保护中SharePoint `C:\Users\ServiceAccount\AppData\Local\Temp` 排除。 [](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**请注意以下例外情况SharePoint：** 在文件级别防病毒保护中SharePoint `C:\Users\Default\AppData\Local\Temp` 排除。 [](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)

`%Windir%\Prefetch`

`C:\Windows\Prefetch`

`C:\Windows\Prefetch\`

`C:\Windows\Prefetch\*`

`%Windir%\System32\Spool`

`C:\Windows\System32\Spool`

`C:\Windows\System32\CatRoot2`
`%Windir%\Temp`

`C:\Windows\Temp`

`C:\Windows\Temp\`

`C:\Windows\Temp\*`

#### <a name="linux-and-macos-platforms"></a>Linux 和 macOS 平台

`/`

`/bin`

`/sbin`

`/usr/lib`


### <a name="file-extensions"></a>文件扩展名

通常，不要定义以下文件扩展名的排除项：

`.7z`

`.bat`

`.bin`

`.cab`

`.cmd`

`.com`

`.cpl`

`.dll`

`.exe`

`.fla`

`.gif`

`.gz`

`.hta`

`.inf`

`.java`

`.jar`

`.job`

`.jpeg`

`.jpg`

`.js`

`.ko`

`.ko.gz`

`.msi`

`.ocx`

`.png`

`.ps1`

`.py`

`.rar`

`.reg`

`.scr`

`.sys`

`.tar`

`.tmp`

`.url`

`.vbe`

`.vbs`

`.wsf`

`.zip`

### <a name="processes"></a>进程

通常，不要为以下过程定义排除项：

`AcroRd32.exe`

`bitsadmin.exe`

`excel.exe`

`iexplore.exe`

`java.exe`

`outlook.exe`

`psexec.exe`

`powerpnt.exe`

`powershell.exe`

`schtasks.exe`

`svchost.exe`

`wmic.exe`

`winword.exe`

`wuauclt.exe`

`addinprocess.exe`

`addinprocess32.exe`

`addinutil.exe`

`bash.exe`

`bginfo.exe`

`cdb.exe`

`csi.exe`

`dbghost.exe`

`dbgsvc.exe`

`dnx.exe`

`dotnet.exe`

`fsi.exe`

`fsiAnyCpu.exe`

`kd.exe`

`ntkd.exe`

`lxssmanager.dll`

`msbuild.exe`

`mshta.exe`

`ntsd.exe`

`rcsi.exe`

`system.management.automation.dll`

`windbg.exe`

#### <a name="linux-and-macos-platforms"></a>Linux 和 macOS 平台

`bash`

`sh`

`python` 和 `python3`

`java`

`zsh`

> [!NOTE]
> 可以选择排除文件类型，如 、，或者如果您的环境具有现代、最新的软件，具有严格的更新策略来处理 `.gif` `.jpg` `.jpeg` `.png` 任何漏洞。

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>仅使用排除列表中的文件名

恶意软件的名称可能与信任并想要从扫描中排除的文件的名称相同。 因此，为了避免从扫描中排除潜在的恶意软件，请使用要排除的文件的完全限定路径，而不只是使用文件名。 例如，如果要从扫描 `Filename.exe` 中排除，请使用文件的完整路径，例如 `C:\program files\contoso\Filename.exe` 。

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>将单个排除列表用于多个服务器工作负载

请勿使用单个排除列表来定义多个服务器工作负荷的排除项。 将不同应用程序或服务工作负荷的排除项拆分为多个排除列表。 例如，IIS 服务器工作负荷的排除列表必须不同于您的 IIS 服务器工作负荷的排除SQL Server列表。

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>在文件名和文件夹路径或扩展名排除列表中将不正确的环境变量用作通配符

Microsoft Defender 防病毒服务使用 LocalSystem 帐户在系统上下文中运行，这意味着它从系统环境变量而不是用户环境变量获取信息。 将环境变量用作排除列表的通配符仅限于系统变量和那些适用于作为 NT AUTHORITY\SYSTEM 帐户运行的进程。 因此，在添加文件夹和进程排除项时，不要Microsoft Defender 防病毒变量作为通配符。 有关系统环境变量 [的完整](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 列表，请参阅系统环境变量下的表。

请参阅 [在文件名和文件夹路径](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 或扩展名排除列表中使用通配符，了解如何在排除列表中使用通配符。
