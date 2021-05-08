---
title: 定义排除时要避免的常见错误
description: 为扫描定义排除项时，Microsoft Defender 防病毒错误。
keywords: 排除项， 文件， 扩展名， 文件类型， 文件夹名称， 文件名， 扫描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: de739ca3c6a4ab305b575fa7e2f419d044d997a8
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274965"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="8648e-104">定义排除时要避免的常见错误</span><span class="sxs-lookup"><span data-stu-id="8648e-104">Common mistakes to avoid when defining exclusions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8648e-105">你可以为不希望扫描的项目定义Microsoft Defender 防病毒列表。</span><span class="sxs-lookup"><span data-stu-id="8648e-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="8648e-106">此类排除项目可能包含使设备易受攻击的威胁。</span><span class="sxs-lookup"><span data-stu-id="8648e-106">Such excluded items could contain threats that make your device vulnerable.</span></span> 

<span data-ttu-id="8648e-107">本文介绍定义排除项时应避免的一些常见错误。</span><span class="sxs-lookup"><span data-stu-id="8648e-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="8648e-108">定义排除列表之前，请参阅推荐[排除项。](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)</span><span class="sxs-lookup"><span data-stu-id="8648e-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="8648e-109">排除某些受信任的项目</span><span class="sxs-lookup"><span data-stu-id="8648e-109">Excluding certain trusted items</span></span>

<span data-ttu-id="8648e-110">某些文件、文件类型、文件夹或进程不应从扫描中排除，即使你信任它们不是恶意文件。</span><span class="sxs-lookup"><span data-stu-id="8648e-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="8648e-111">不要为下表中列出的文件夹位置、文件扩展名和进程定义排除项：</span><span class="sxs-lookup"><span data-stu-id="8648e-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following table:</span></span>

| <span data-ttu-id="8648e-112">文件夹位置</span><span class="sxs-lookup"><span data-stu-id="8648e-112">Folder locations</span></span> | <span data-ttu-id="8648e-113">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="8648e-113">File extensions</span></span> | <span data-ttu-id="8648e-114">进程</span><span class="sxs-lookup"><span data-stu-id="8648e-114">Processes</span></span> |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> <span data-ttu-id="8648e-115">`bginfo.exe`[1]</span><span class="sxs-lookup"><span data-stu-id="8648e-115">`bginfo.exe`[1]</span></span> <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> <span data-ttu-id="8648e-116">`msbuild.exe`[2]</span><span class="sxs-lookup"><span data-stu-id="8648e-116">`msbuild.exe`[2]</span></span> <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> <span data-ttu-id="8648e-117">可以选择排除文件类型，如 、，或者如果您的环境具有现代、最新的软件，具有严格的更新策略来处理 `.gif` `.jpg` `.jpeg` `.png` 任何漏洞。</span><span class="sxs-lookup"><span data-stu-id="8648e-117">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="8648e-118">仅使用排除列表中的文件名</span><span class="sxs-lookup"><span data-stu-id="8648e-118">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="8648e-119">恶意软件可能与受信任的文件同名，并且想要从扫描中排除。</span><span class="sxs-lookup"><span data-stu-id="8648e-119">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="8648e-120">因此，为了避免从扫描中排除潜在的恶意软件，请使用要排除的文件的完全限定路径，而不只是使用文件名。</span><span class="sxs-lookup"><span data-stu-id="8648e-120">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="8648e-121">例如，如果要从扫描 `Filename.exe` 中排除，请使用文件的完整路径，例如 `C:\program files\contoso\Filename.exe` 。</span><span class="sxs-lookup"><span data-stu-id="8648e-121">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="8648e-122">将单个排除列表用于多个服务器工作负载</span><span class="sxs-lookup"><span data-stu-id="8648e-122">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="8648e-123">请勿使用单个排除列表来定义多个服务器工作负荷的排除项。</span><span class="sxs-lookup"><span data-stu-id="8648e-123">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="8648e-124">将不同应用程序或服务工作负荷的排除项拆分为多个排除列表。</span><span class="sxs-lookup"><span data-stu-id="8648e-124">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="8648e-125">例如，IIS 服务器工作负荷的排除列表必须不同于您的 IIS 服务器工作负荷的排除SQL Server列表。</span><span class="sxs-lookup"><span data-stu-id="8648e-125">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="8648e-126">在文件名和文件夹路径或扩展名排除列表中将不正确的环境变量用作通配符</span><span class="sxs-lookup"><span data-stu-id="8648e-126">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="8648e-127">Microsoft Defender 防病毒服务使用 LocalSystem 帐户在系统上下文中运行，这意味着它从系统环境变量而不是用户环境变量获取信息。</span><span class="sxs-lookup"><span data-stu-id="8648e-127">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="8648e-128">将环境变量用作排除列表的通配符仅限于系统变量和那些适用于作为 NT AUTHORITY\SYSTEM 帐户运行的进程。</span><span class="sxs-lookup"><span data-stu-id="8648e-128">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="8648e-129">因此，在添加文件夹和进程排除项时，Microsoft Defender 防病毒变量作为通配符。</span><span class="sxs-lookup"><span data-stu-id="8648e-129">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="8648e-130">有关系统环境变量 [的完整](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 列表，请参阅系统环境变量下的表。</span><span class="sxs-lookup"><span data-stu-id="8648e-130">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="8648e-131">请参阅 [在文件名和文件夹路径](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 或扩展名排除列表中使用通配符，了解如何在排除列表中使用通配符。</span><span class="sxs-lookup"><span data-stu-id="8648e-131">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8648e-132">相关文章</span><span class="sxs-lookup"><span data-stu-id="8648e-132">Related articles</span></span>

- [<span data-ttu-id="8648e-133">配置并验证扫描中的Microsoft Defender 防病毒项</span><span class="sxs-lookup"><span data-stu-id="8648e-133">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8648e-134">根据文件扩展名和文件夹位置配置和验证排除项</span><span class="sxs-lookup"><span data-stu-id="8648e-134">Configure and validate exclusions based on file extension and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8648e-135">配置并验证进程打开的文件的排除项</span><span class="sxs-lookup"><span data-stu-id="8648e-135">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8648e-136">在 Microsoft Defender 防病毒 服务器上配置Windows排除项</span><span class="sxs-lookup"><span data-stu-id="8648e-136">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
