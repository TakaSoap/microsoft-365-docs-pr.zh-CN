---
title: 刷新确切的数据匹配信息源表文件
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 刷新敏感信息源表文件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe72fac43d3cc9a568d8aa1c5d985d34f8477a4d
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760836"
---
# <a name="refresh-your-exact-data-match-sensitive-information-source-table-file"></a>刷新与敏感信息源表文件完全匹配的数据 

每 24 小时最多可以刷新敏感信息数据库 5 次。 必须重新隐藏并上传敏感信息源表。

1. 将敏感数据重新导出到应用，例如Microsoft Excel，并将文件保存为.csv、.tsv 格式或管道 (|) 分隔格式。 保留之前哈希和上传文件时所用的文件名和位置。 请参阅， [导出源数据以获取基于确切数据匹配的敏感信息类型](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type) ，了解有关导出敏感数据并使其采用正确格式的详细信息。

      > [!NOTE]
      > 如果敏感信息源表文件的结构 (字段名称) 没有更改，则刷新数据时无需对数据库架构文件进行任何更改。 但是，如果必须进行更改，请确保相应地编辑数据库架和规则包。 请参阅，管理用于编辑或删除架构的步骤的 [确切数据匹配架构](sit-use-exact-data-manage-schema.md#manage-your-exact-data-match-schema) 。 请参阅：为编辑或删除 EDM SIT [/规则包的步骤创建与敏感信息类型/规则包完全匹配的数据](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) 。

2. 使用 [哈希中的过程，并上传敏感信息源表以获取与敏感信息类型完全匹配的精确数据](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) ，以便上传敏感信息表源文件。

3. 可以使用 [任务计划程序](/windows/desktop/TaskSchd/task-scheduler-start-page) 自动执行 [哈希操作，并上传敏感信息源表，以便完成与敏感信息类型过程完全匹配的数据](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) 。 你可以使用多种方法来计划任务：

   |方法|需执行的操作|
   |---|---|
   |Windows PowerShell|请参阅本文中的[计划任务](/powershell/module/scheduledtasks/)文档和[示例 PowerShell 脚本](#example-powershell-script-for-task-scheduler)|
   |任务计划程序 API|请参阅[任务计划程序](/windows/desktop/TaskSchd/using-the-task-scheduler)文档|
   |Windows 用户界面|在 Windows 中单击“**开始**”，然后键入 Task Scheduler。 然后，在结果列表中，右键单击“**任务计划程序**”，然后选择“**以管理员身份运行**”。|

### <a name="example-powershell-script-for-task-scheduler"></a>任务计划程序的示例 PowerShell 脚本 

此部分包含一个示例 PowerShell 脚本，你可以使用该脚本来计划为数据创建哈希并上传哈希数据的任务：

#### <a name="schedule-hashing-and-upload-in-a-combined-step"></a>在组合步骤中计划哈希和上传

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext"
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation + ' /Schema ' + $schemaFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="schedule-hashing-and-upload-as-separate-steps"></a>计划哈希和上传作为单独的步骤

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext "

\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation + ' /Schema ' + $schemaFile
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```
