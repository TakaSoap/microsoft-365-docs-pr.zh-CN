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
ms.date: 06/15/2021
ms.openlocfilehash: f9ca83fcfba4b79898a0fed527e38947a4c230d6
ms.sourcegitcommit: 959c3c3633e40b7b0f5e2c8372409778005a24db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2021
ms.locfileid: "52950127"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="ef17a-104">定义排除时要避免的常见错误</span><span class="sxs-lookup"><span data-stu-id="ef17a-104">Common mistakes to avoid when defining exclusions</span></span>

<span data-ttu-id="ef17a-105">你可以为不希望扫描的项目定义Microsoft Defender 防病毒列表。</span><span class="sxs-lookup"><span data-stu-id="ef17a-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="ef17a-106">此类排除项目可能包含使设备易受攻击的威胁。</span><span class="sxs-lookup"><span data-stu-id="ef17a-106">Such excluded items could contain threats that make your device vulnerable.</span></span> <span data-ttu-id="ef17a-107">本文介绍定义排除项时应避免的一些常见错误。</span><span class="sxs-lookup"><span data-stu-id="ef17a-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="ef17a-108">定义排除列表之前，请参阅推荐[排除项。](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)</span><span class="sxs-lookup"><span data-stu-id="ef17a-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="ef17a-109">排除某些受信任的项目</span><span class="sxs-lookup"><span data-stu-id="ef17a-109">Excluding certain trusted items</span></span>

<span data-ttu-id="ef17a-110">某些文件、文件类型、文件夹或进程不应从扫描中排除，即使你信任它们不是恶意文件。</span><span class="sxs-lookup"><span data-stu-id="ef17a-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="ef17a-111">不要为以下部分中列出的文件夹位置、文件扩展名和进程定义排除项：</span><span class="sxs-lookup"><span data-stu-id="ef17a-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following sections:</span></span>
- <span data-ttu-id="ef17a-112">文件夹位置</span><span class="sxs-lookup"><span data-stu-id="ef17a-112">Folder locations</span></span>
- <span data-ttu-id="ef17a-113">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="ef17a-113">File extensions</span></span>
- <span data-ttu-id="ef17a-114">进程</span><span class="sxs-lookup"><span data-stu-id="ef17a-114">Processes</span></span>

### <a name="folder-locations"></a><span data-ttu-id="ef17a-115">文件夹位置</span><span class="sxs-lookup"><span data-stu-id="ef17a-115">Folder locations</span></span>

<span data-ttu-id="ef17a-116">通常，不要为以下文件夹位置定义排除项：</span><span class="sxs-lookup"><span data-stu-id="ef17a-116">In general, do not define exclusions for the following folder locations:</span></span>

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

<span data-ttu-id="ef17a-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\`**请注意以下例外情况SharePoint：** 在文件级别防病毒保护中 `C:\Users\ServiceAccount\AppData\Local\Temp` SharePoint。 [](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)</span><span class="sxs-lookup"><span data-stu-id="ef17a-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\ServiceAccount\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

<span data-ttu-id="ef17a-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**请注意以下例外情况SharePoint：** 在文件级别防病毒保护中 `C:\Users\Default\AppData\Local\Temp` SharePoint。 [](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)</span><span class="sxs-lookup"><span data-stu-id="ef17a-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\Default\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

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

### <a name="file-extensions"></a><span data-ttu-id="ef17a-119">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="ef17a-119">File extensions</span></span>

<span data-ttu-id="ef17a-120">通常，不要定义以下文件扩展名的排除项：</span><span class="sxs-lookup"><span data-stu-id="ef17a-120">In general, do not define exclusions for the following file extensions:</span></span>

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

### <a name="processes"></a><span data-ttu-id="ef17a-121">进程</span><span class="sxs-lookup"><span data-stu-id="ef17a-121">Processes</span></span> 

<span data-ttu-id="ef17a-122">通常，不要为以下过程定义排除项：</span><span class="sxs-lookup"><span data-stu-id="ef17a-122">In general, do not define exclusions for the following processes:</span></span>

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

> [!NOTE]
> <span data-ttu-id="ef17a-123">可以选择排除文件类型，如 、，或者如果您的环境具有现代、最新的软件，具有严格的更新策略来处理 `.gif` `.jpg` `.jpeg` `.png` 任何漏洞。</span><span class="sxs-lookup"><span data-stu-id="ef17a-123">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="ef17a-124">仅使用排除列表中的文件名</span><span class="sxs-lookup"><span data-stu-id="ef17a-124">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="ef17a-125">恶意软件可能与受信任的文件同名，并且想要从扫描中排除。</span><span class="sxs-lookup"><span data-stu-id="ef17a-125">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="ef17a-126">因此，为了避免从扫描中排除潜在的恶意软件，请使用要排除的文件的完全限定路径，而不只是使用文件名。</span><span class="sxs-lookup"><span data-stu-id="ef17a-126">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="ef17a-127">例如，如果要从扫描 `Filename.exe` 中排除，请使用文件的完整路径，例如 `C:\program files\contoso\Filename.exe` 。</span><span class="sxs-lookup"><span data-stu-id="ef17a-127">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="ef17a-128">将单个排除列表用于多个服务器工作负载</span><span class="sxs-lookup"><span data-stu-id="ef17a-128">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="ef17a-129">请勿使用单个排除列表来定义多个服务器工作负荷的排除项。</span><span class="sxs-lookup"><span data-stu-id="ef17a-129">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="ef17a-130">将不同应用程序或服务工作负荷的排除项拆分为多个排除列表。</span><span class="sxs-lookup"><span data-stu-id="ef17a-130">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="ef17a-131">例如，IIS 服务器工作负荷的排除列表必须不同于您的 IIS 服务器工作负荷的排除SQL Server列表。</span><span class="sxs-lookup"><span data-stu-id="ef17a-131">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="ef17a-132">在文件名和文件夹路径或扩展名排除列表中将不正确的环境变量用作通配符</span><span class="sxs-lookup"><span data-stu-id="ef17a-132">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="ef17a-133">Microsoft Defender 防病毒服务使用 LocalSystem 帐户在系统上下文中运行，这意味着它从系统环境变量而不是用户环境变量获取信息。</span><span class="sxs-lookup"><span data-stu-id="ef17a-133">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="ef17a-134">将环境变量用作排除列表的通配符仅限于系统变量和那些适用于作为 NT AUTHORITY\SYSTEM 帐户运行的进程。</span><span class="sxs-lookup"><span data-stu-id="ef17a-134">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="ef17a-135">因此，在添加文件夹和进程排除项时，Microsoft Defender 防病毒变量作为通配符。</span><span class="sxs-lookup"><span data-stu-id="ef17a-135">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="ef17a-136">有关系统环境变量 [的完整](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 列表，请参阅系统环境变量下的表。</span><span class="sxs-lookup"><span data-stu-id="ef17a-136">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="ef17a-137">请参阅 [在文件名和文件夹路径](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 或扩展名排除列表中使用通配符，了解如何在排除列表中使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ef17a-137">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

