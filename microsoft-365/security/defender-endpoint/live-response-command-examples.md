---
title: 实时响应命令示例
description: 了解如何为 Microsoft Defender for Endpoint 运行基本或高级实时响应命令，并查看有关其使用方式的示例。
keywords: 示例， command， cli， remote， shell， connection， live， response， real-time， command， script， remediate， hunt， export， log， drop， download， file
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f08f20753a1f0926abbbce01fe97f20ef1c07f2c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689085"
---
# <a name="live-response-command-examples"></a><span data-ttu-id="b288d-104">实时响应命令示例</span><span class="sxs-lookup"><span data-stu-id="b288d-104">Live response command examples</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b288d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b288d-105">**Applies to:**</span></span>
- [<span data-ttu-id="b288d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b288d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b288d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b288d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b288d-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="b288d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b288d-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b288d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="b288d-110">了解实时响应中使用的常用命令，并查看常用命令使用方法的示例。</span><span class="sxs-lookup"><span data-stu-id="b288d-110">Learn about common commands used in live response and see examples on how they are typically used.</span></span>

<span data-ttu-id="b288d-111">根据已授予的角色，可以运行基本或高级实时响应命令。</span><span class="sxs-lookup"><span data-stu-id="b288d-111">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="b288d-112">有关基本命令和高级命令详细信息，请参阅使用实时响应 [调查设备上的实体](live-response.md)。</span><span class="sxs-lookup"><span data-stu-id="b288d-112">For more information on basic and advanced commands, see [Investigate entities on devices using live response](live-response.md).</span></span>


## <a name="analyze"></a><span data-ttu-id="b288d-113">analyze</span><span class="sxs-lookup"><span data-stu-id="b288d-113">analyze</span></span> 

```
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a><span data-ttu-id="b288d-114">connections</span><span class="sxs-lookup"><span data-stu-id="b288d-114">connections</span></span>

```
# List active connections in json format using parameter name
connections -output json
```

```
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a><span data-ttu-id="b288d-115">dir</span><span class="sxs-lookup"><span data-stu-id="b288d-115">dir</span></span>

```
# List files and sub-folders in the current folder
dir
```

```
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a><span data-ttu-id="b288d-116">fileinfo</span><span class="sxs-lookup"><span data-stu-id="b288d-116">fileinfo</span></span>

```
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a><span data-ttu-id="b288d-117">findfile</span><span class="sxs-lookup"><span data-stu-id="b288d-117">findfile</span></span>

```
# Find file by name
findfile test.txt
```

## <a name="getfile"></a><span data-ttu-id="b288d-118">getfile</span><span class="sxs-lookup"><span data-stu-id="b288d-118">getfile</span></span>

```
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> <span data-ttu-id="b288d-119">无法使用此命令 **从** 实时响应中下载以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="b288d-119">The following file types **cannot** be downloaded using this command from within Live Response:</span></span>
>
> * [<span data-ttu-id="b288d-120">重新分析点文件</span><span class="sxs-lookup"><span data-stu-id="b288d-120">Reparse point files</span></span>](/windows/desktop/fileio/reparse-points/)
> * [<span data-ttu-id="b288d-121">稀疏文件</span><span class="sxs-lookup"><span data-stu-id="b288d-121">Sparse files</span></span>](/windows/desktop/fileio/sparse-files/)
> * <span data-ttu-id="b288d-122">空文件</span><span class="sxs-lookup"><span data-stu-id="b288d-122">Empty files</span></span>
> * <span data-ttu-id="b288d-123">虚拟文件或在本地未完全呈现的文件</span><span class="sxs-lookup"><span data-stu-id="b288d-123">Virtual files, or files that are not fully present locally</span></span>
>
> <span data-ttu-id="b288d-124">PowerShell **支持** 这些 [文件类型](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="b288d-124">These file types **are** supported by [PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true).</span></span>
>
> <span data-ttu-id="b288d-125">如果遇到在实时响应中使用此命令时遇到问题，请使用 PowerShell 作为备选方法。</span><span class="sxs-lookup"><span data-stu-id="b288d-125">Use PowerShell as an alternative, if you have problems using this command from within Live Response.</span></span>

## <a name="processes"></a><span data-ttu-id="b288d-126">processes</span><span class="sxs-lookup"><span data-stu-id="b288d-126">processes</span></span>
```
# Show all processes
processes
```

```
# Get process by pid
processes 123
```

```
# Get process by pid with argument name
processes -pid 123
```

```
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a><span data-ttu-id="b288d-127">putfile</span><span class="sxs-lookup"><span data-stu-id="b288d-127">putfile</span></span>

```
# Upload file from library
putfile get-process-by-name.ps1
```

```
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a><span data-ttu-id="b288d-128">注册表</span><span class="sxs-lookup"><span data-stu-id="b288d-128">registry</span></span>

```
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a><span data-ttu-id="b288d-129">修正</span><span class="sxs-lookup"><span data-stu-id="b288d-129">remediate</span></span>

```
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```
# Remediate process with specific PID
remediate process 7960
```

```
# See list of all remediated entities
remediate list
```

## <a name="run"></a><span data-ttu-id="b288d-130">run</span><span class="sxs-lookup"><span data-stu-id="b288d-130">run</span></span>

```
# Run PowerShell script from the library without arguments
run script.ps1
```

```
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```
>[!NOTE]
>
> <span data-ttu-id="b288d-131">对于长时间运行的命令（如 **"run"** 或 **"getfile"，** 您可能需要在命令末尾使用""符号在后台 **&** 执行该操作。</span><span class="sxs-lookup"><span data-stu-id="b288d-131">For long running commands such as '**run**' or '**getfile**', you may want to use the '**&**' symbol at the end of the command to perform that action in the background.</span></span>
> <span data-ttu-id="b288d-132">这将允许你在使用 **'fg'** 基本命令完成时继续调查计算机并返回到 [后台命令](live-response.md#basic-commands)。</span><span class="sxs-lookup"><span data-stu-id="b288d-132">This will allow you to continue investigating the machine and return to the background command when done using '**fg**' [basic command](live-response.md#basic-commands).</span></span>
>
## <a name="scheduledtask"></a><span data-ttu-id="b288d-133">scheduledtask</span><span class="sxs-lookup"><span data-stu-id="b288d-133">scheduledtask</span></span>

```
# Get all scheduled tasks
scheduledtasks
```

```
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```


## <a name="undo"></a><span data-ttu-id="b288d-134">undo</span><span class="sxs-lookup"><span data-stu-id="b288d-134">undo</span></span>

```
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```

