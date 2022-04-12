---
title: 定义排除时要避免的常见错误
description: 为Microsoft Defender 防病毒扫描定义排除项时避免常见错误。
keywords: 排除项，文件，扩展名，文件类型，文件夹名称，文件名，扫描
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
ms.openlocfilehash: b5dc8832839c86fee98e9f27264b70e6a63f380c
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790693"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>定义排除时要避免的常见错误

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒 

**平台**
- Windows
- macOS
- Linux

可以为不希望Microsoft Defender 防病毒扫描的项定义排除列表。 此类排除项可能包含使设备易受攻击的威胁。 本文介绍定义排除项时应避免的一些常见错误。

在定义排除列表之前，请参阅[推荐定义排除项](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)。

## <a name="excluding-certain-trusted-items"></a>排除某些受信任的项目

即使你相信某些文件、文件类型、文件夹或进程不是恶意文件，也不应将其排除在扫描之外。

请勿为以下部分中列出的文件夹位置、文件扩展名和进程定义排除项：
- 文件夹位置
- 文件扩展名
- 过程

### <a name="folder-locations"></a>文件夹位置

一般情况下，不要为以下文件夹位置定义排除项：

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

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**请注意以下SharePoint异常**：请 [在SharePoint中使用文件级防病毒保护](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)时排除`C:\Users\ServiceAccount\AppData\Local\Temp`。

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**请注意以下SharePoint异常**：请 [在SharePoint中使用文件级防病毒保护](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)时排除`C:\Users\Default\AppData\Local\Temp`。

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

通常，不要为以下文件扩展名定义排除项：

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

### <a name="processes"></a>过程

通常，不要为以下进程定义排除项：

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
> 可以选择排除文件类型，例如`.gif`，`.jpg``.jpeg``.png`如果环境具有具有严格的更新策略的新式最新软件来处理任何漏洞。

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>仅使用排除列表中的文件名

恶意软件的名称可能与你信任并且希望从扫描中排除的文件的名称相同。 因此，为了避免将潜在的恶意软件排除在扫描之外，请使用要排除的文件的完全限定路径，而不是只使用文件名。 例如，如果要从扫描中排除 `Filename.exe` ，请使用文件的完整路径，例如 `C:\program files\contoso\Filename.exe`。

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>对多个服务器工作负荷使用单个排除列表

不要使用单个排除列表来定义多个服务器工作负荷的排除项。 将不同应用程序或服务工作负荷的排除项拆分为多个排除列表。 例如，IIS Server 工作负荷的排除列表必须与SQL Server工作负荷的排除列表不同。

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>在文件名和文件夹路径或扩展排除列表中使用不正确的环境变量作为通配符

Microsoft Defender 防病毒服务使用 LocalSystem 帐户在系统上下文中运行，这意味着它从系统环境变量而不是从用户环境变量获取信息。 将环境变量用作排除列表中的通配符仅限于系统变量和适用于以 NT AUTHORITY\SYSTEM 帐户运行的进程的变量。 因此，在添加Microsoft Defender 防病毒文件夹和进程排除项时，不要将用户环境变量用作通配符。 有关系统环境变量的完整列表，请参阅 [系统环境变量](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 下的表。

有关如何在排除列表中使用通配符的信息，请参阅 [文件名和文件夹路径或扩展排除列表中的“使用通配](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 符”。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)
