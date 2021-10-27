---
title: 实时响应命令示例
description: 了解如何为 Microsoft Defender for Endpoint 运行基本或高级实时响应命令，并查看有关其使用方式的示例。
keywords: 示例， command， cli， remote， shell， connection， live， response， real-time， command， script， remediate， hunt， export， log， drop， download， file
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b234a27ccf011cdc20b7c1c5ab34e4322bfc5fd
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587703"
---
# <a name="live-response-command-examples"></a>实时响应命令示例

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

了解实时响应中使用的常用命令，并查看常用命令使用方法的示例。

根据已授予的角色，可以运行基本或高级实时响应命令。 有关基本命令和高级命令详细信息，请参阅使用实时响应调查 [设备上的实体](live-response.md)。

## <a name="analyze"></a>analyze

```console
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```console
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a>connections

```console
# List active connections in json format using parameter name
connections -output json
```

```console
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a>dir

```console
# List files and sub-folders in the current folder
dir
```

```console
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```console
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a>fileinfo

```console
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a>findfile

```console
# Find file by name
findfile test.txt
```

## <a name="getfile"></a>getfile

```console
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```console
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

> [!NOTE]
>
> 无法使用此命令 **从** 实时响应中下载以下文件类型：
>
> - [重新分析点文件](/windows/desktop/fileio/reparse-points/)
> - [稀疏文件](/windows/desktop/fileio/sparse-files/)
> - 空文件
> - 虚拟文件或在本地未完全呈现的文件
>
> PowerShell **支持** 这些 [文件类型](/powershell/scripting/overview)。
>
> 如果遇到在实时响应中使用此命令时遇到问题，请使用 PowerShell 作为备选方法。

## <a name="library"></a>库

```console
# List files in the library
library
```

```console
# Delete a file from the library
library delete script.ps1
```

## <a name="processes"></a>processes

```console
# Show all processes
processes
```

```console
# Get process by pid
processes 123
```

```console
# Get process by pid with argument name
processes -pid 123
```

```console
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a>putfile

```console
# Upload file from library
putfile get-process-by-name.ps1
```

```console
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```console
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a>注册表

```console
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```console
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a>修正

```console
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```console
# Remediate process with specific PID
remediate process 7960
```

```console
# See list of all remediated entities
remediate list
```

## <a name="run"></a>run

```console
# Run PowerShell script from the library without arguments
run script.ps1
```

```console
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```

> [!NOTE]
>
> 对于长时间运行的命令（如 **"run"** 或 **"getfile"，** 您可能需要在命令末尾使用""符号在后台 **&** 执行该操作。
> 这将允许你在使用 **'fg'** 基本命令完成时继续调查计算机并返回到 [后台命令](live-response.md#basic-commands)。

## <a name="scheduledtask"></a>scheduledtask

```console
# Get all scheduled tasks
scheduledtasks
```

```console
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```

## <a name="undo"></a>undo

```console
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```console
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```
