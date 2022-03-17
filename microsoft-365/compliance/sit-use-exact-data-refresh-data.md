---
title: 刷新精确的数据匹配信息源表文件
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
ms.openlocfilehash: 347ff88391a19cb3d8688b1142e524a163159b6f
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525482"
---
# <a name="refresh-your-exact-data-match-sensitive-information-source-table-file"></a>刷新准确数据匹配敏感信息源表文件 

每 24 小时，您最多可以刷新敏感信息数据库 5 次。 您必须重新Hash and upload your sensitive information source table。

1. 将敏感数据重新导出到应用程序（如 Microsoft Excel）以 .csv.tsv 格式或管道分隔 (|) 文件。 保持之前对文件进行哈希处理和上载时所使用的文件名和位置相同。 有关导出 [敏感数据和获取正确](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type) 格式的详细信息，请参阅导出源数据，了解基于准确数据匹配的敏感信息类型。

      > [!NOTE]
      > 如果对敏感信息源 (文件 (字段名) 没有变化，则刷新数据时无需对数据库架构文件进行任何更改。 但是，如果必须进行更改，请确保相应地编辑数据库架和规则包。 请参阅 [管理确切的数据匹配架构](sit-use-exact-data-manage-schema.md#manage-your-exact-data-match-schema) ，了解编辑或删除架构的步骤。 请参阅创建 [精确数据匹配敏感信息类型/规则](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) 包，了解编辑或删除 EDM SIT/规则包的步骤。

2. 使用哈希 [中的过程并上载敏感信息源表，](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) 以精确匹配敏感信息类型，以上传敏感信息表源文件。

2. 可以使用任务 [计划程序自动](/windows/desktop/TaskSchd/task-scheduler-start-page) 执行哈希操作并上载敏感信息源表，以执行准确 [数据匹配敏感信息类型](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) 过程。 你可以使用多种方法来计划任务：

   |方法|需执行的操作|
   |---|---|
   |Windows PowerShell|请参阅本文中的[计划任务](/powershell/module/scheduledtasks/)文档和[示例 PowerShell 脚本](#example-powershell-script-for-task-scheduler)|
   |任务计划程序 API|请参阅[任务计划程序](/windows/desktop/TaskSchd/using-the-task-scheduler)文档|
   |Windows 用户界面|在 Windows 中单击“**开始**”，然后键入 Task Scheduler。 然后，在结果列表中，右键单击“**任务计划程序**”，然后选择“**以管理员身份运行**”。|

### <a name="example-powershell-script-for-task-scheduler"></a>任务计划程序的示例 PowerShell 脚本 

此部分包含一个示例 PowerShell 脚本，你可以使用该脚本来计划为数据创建哈希并上传哈希数据的任务：

#### <a name="schedule-hashing-and-upload-in-a-combined-step"></a>在组合步骤中安排哈希和上载

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

#### <a name="schedule-hashing-and-upload-as-separate-steps"></a>将哈希和上载安排为单独的步骤

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
