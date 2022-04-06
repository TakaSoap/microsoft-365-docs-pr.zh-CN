---
title: 性能分析器Microsoft Defender 防病毒
description: 介绍调整应用程序性能Microsoft Defender 防病毒。
keywords: 优化， 性能， 适用于终结点的 microsoft defender， defender 防病毒
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b5d9346746dba3b7b4c75909cb8e36e47c3c9d99
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472498"
---
# <a name="performance-analyzer-for-microsoft-defender-antivirus"></a>性能分析器Microsoft Defender 防病毒

**适用对象**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**什么是Microsoft Defender 防病毒器？**

在某些情况下，你可能需要在扫描特定文件和文件夹时Microsoft Defender 防病毒性能。 性能分析器是一个 PowerShell 命令行工具，可帮助确定哪些文件、文件扩展名和进程可能导致各个终结点出现性能问题。 此信息可用于更好地评估性能问题和应用修正操作。

要分析的一些选项包括：

- 影响扫描时间的顶部文件
- 影响扫描时间的顶部进程
- 影响扫描时间的顶部文件扩展名
- 组合 – 例如，每个扩展名的顶级文件、每个文件的顶部扫描、每个进程的文件的顶级扫描

## <a name="running-performance-analyzer"></a>运行性能分析器

运行性能分析器的高级别过程包括以下步骤：

1. 运行性能分析器以收集终结点上Microsoft Defender 防病毒事件的性能记录。

   > [!NOTE]
   > **Microsoft-antimalware-Engine** 类型的 Microsoft Defender 防病毒 事件的性能通过性能分析器进行记录。

2. 使用不同的录制报告分析扫描结果。

## <a name="using-performance-analyzer"></a>使用性能分析器

若要开始录制系统事件，请以管理模式打开 PowerShell 并执行以下步骤：

1. 运行以下命令以开始录制：

   `New-MpPerformanceRecording -RecordTo <recording.etl>`
 
    其中 `-RecordTo` 参数指定保存跟踪文件的完整路径位置。 有关 cmdlet 的更多信息，请参阅[Microsoft Defender 防病毒 cmdlet](/powershell/module/defender)。

2. 如果认为进程或服务会影响性能，请通过执行相关任务重现这种情况。

3. 按 **Enter** 停止并保存录制，或 **按 Ctrl+C** 取消录制。

4. 使用性能分析器的参数分析结果 `Get-MpPerformanceReport`。 例如，在执行命令 `Get-MpPerformanceReport -Path <recording.etl> -TopFiles 3 -TopScansPerFile 10`时，会向用户提供影响性能的前 3 个文件前 10 次扫描的列表。 

有关命令行参数和选项的详细信息，请参阅 [New-MpPerformanceRecording](#new-mpperformancerecording) 和 [Get-MpPerformanceReport](#get-mpperformancereport)。

> [!NOTE]
> 运行录制时，如果收到错误"由于 Windows Performance Recorder 已在录制，无法启动性能录制"，请运行以下命令以使用新命令停止现有跟踪：**wpr -cancel -instancename** MSFT_MpPerformanceRecording

### <a name="performance-tuning-data-and-information"></a>性能优化数据和信息

根据查询，用户将能够查看扫描计数、持续时间 (总/分钟/平均/最大值/中值) 、路径、进程和扫描原因的数据。 下图显示了扫描影响前 10 个文件的简单查询的示例输出。 

:::image type="content" source="images/example-output.png" alt-text="基本 TopFiles 查询的示例输出" lightbox="images/example-output.png":::

### <a name="additional-functionality-exporting-and-converting-to-csv-and-json"></a>其他功能：导出并转换为 CSV 和 JSON

还可以导出性能分析器的结果，并转换为 CSV 或 JSON 文件。
有关描述通过示例代码"导出"和"转换"过程的示例，请参阅下文。

#### <a name="for-csv"></a>对于 CSV

- **导出：**`(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | Export-CSV -Path:.\Repro-Install-Scans.csv -Encoding:UTF8 -NoTypeInformation`

- **转换：**`(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:100). TopScans | ConvertTo-Csv -NoTypeInformation`

#### <a name="for-json"></a>对于 JSON

- **转换：**`(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | ConvertTo-Json -Depth:1`

### <a name="requirements"></a>要求
Microsoft Defender 防病毒性能分析器具有以下先决条件：

- 支持Windows版本：Windows 10、Windows 11 和 Windows Server 2016 及以上版本
- 平台版本：4.18.2108.7+
- PowerShell 版本：PowerShell 版本 5.1、PowerShell ISE、远程 PowerShell (4.18.2201.10+) 、PowerShell 7.x (4.18.2201.10) 

## <a name="powershell-reference"></a>PowerShell 参考
有两个新的 PowerShell cmdlet 用于优化Microsoft Defender 防病毒： 

- [New-MpPerformanceRecording](#new-mpperformancerecording)
- [Get-MpPerformanceReport](#get-mpperformancereport)


### <a name="new-mpperformancerecording"></a>New-MpPerformanceRecording

以下部分介绍了新 PowerShell cmdlet New-MpPerformanceRecording 的引用。 此 cmdlet 收集扫描Microsoft Defender 防病毒记录。

#### <a name="syntax-new-mpperformancerecording"></a>语法：New-MpPerformanceRecording

```powershell
New-MpPerformanceRecording -RecordTo <String >
```

#### <a name="description-new-mpperformancerecording"></a>说明：New-MpPerformanceRecording
此 `New-MpPerformanceRecording` cmdlet 可收集扫描Microsoft Defender 防病毒记录。 这些性能记录包含 Microsoft-Antimalware-Engine 和 NT 内核进程事件，可在收集后使用 [Get-MpPerformanceReport](#get-mpperformancereport) cmdlet 进行分析。

此 `New-MpPerformanceRecording` cmdlet 可深入了解可能导致文件性能下降的问题Microsoft Defender 防病毒。 此工具是"AS IS"提供的，并不用于提供有关排除项的建议。 排除项会降低终结点上的保护级别。 应谨慎定义排除项（如果有）。

有关性能分析器详细信息，请参阅 [Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer) 文档。

> [!IMPORTANT]
> 此 cmdlet 需要提升的管理员权限。

**受支持的操作系统版本**

Windows版本 10 及更高版本。

> [!NOTE]
> 此功能从平台版本 4.18.2108.X 及更高版本开始提供。

#### <a name="examples-new-mpperformancerecording"></a>示例：New-MpPerformanceRecording

##### <a name="example-1-collect-a-performance-recording-and-save-it"></a>示例 1：收集并保存性能记录

```powershell
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl
```

上述命令收集性能记录，并保存到指定路径： **.\Defender-scans.etl**。

##### <a name="example-2-collect-a-performance-recording-for-remote-powershell-session"></a>示例 2：收集远程 PowerShell 会话的性能记录

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
New-MpPerformanceRecording -RecordTo C:\LocalPathOnServer02\trace.etl -Session $s
```

上述命令在 Server02 (上收集由参数 Session) 的参数 $s 指定的性能记录，并保存到指定路径： **C：\LocalPathOnServer02\trace.etl** on Server02。

#### <a name="parameters-new-mpperformancerecording"></a>参数：New-MpPerformanceRecording

##### <a name="-recordto"></a>-RecordTo
指定保存 Microsoft Defender 反恶意软件性能记录的位置。

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False 
Accept wildcard characters: False
```

##### <a name="-session"></a>-Session 
指定要创建和保存性能记录Microsoft Defender 防病毒 PSSession 对象。 使用此参数时，RecordTo 参数引用远程计算机上本地路径。 适用于 Defender 平台版本 4.18.2201.10。

```yaml
Type: PSSession[]
Position: 0
Default value: None
Accept pipeline input: False 
Accept wildcard characters: False
```

### <a name="get-mpperformancereport"></a>Get-MpPerformanceReport

下一节介绍 Get-MpPerformanceReport PowerShell cmdlet。 分析和报告 MDAV Microsoft Defender 防病毒 (记录) 记录。

#### <a name="syntax-get-mpperformancereport"></a>语法：Get-MpPerformanceReport

```powershell
Get-MpPerformanceReport    [-Path] <String>
[-TopScans <Int32>]
[-TopFiles  <Int32>
    [-TopScansPerFile <Int32>]
    [-TopProcessesPerFile  <Int32>  
        [-TopScansPerProcessPerFile <Int32>]
    ]
] 
[-TopExtensions  <Int32>
    [-TopScansPerExtension <Int32>]
    [-TopProcessesPerExtension <Int32>
        [-TopScansPerProcessPerExtension <Int32>]
        ]
    [-TopFilesPerExtension  <Int32>
        [-TopScansPerFilePerExtension <Int32>]
        ]
    ] 
]
[-TopProcesses  <Int32>
    [-TopScansPerProcess <Int32>]
    [-TopExtensionsPerProcess <Int32>
        [-TopScansPerExtensionPerProcess <Int32>]
    ]
]
[-TopFilesPerProcess  <Int32>
    [-TopScansPerFilePerProcess <Int32>]
]
[-MinDuration <String>]
```

#### <a name="description-get-mpperformancereport"></a>说明：Get-MpPerformanceReport
`Get-MpPerformanceReport`此 cmdlet 分析以前收集的 Microsoft Defender 防病毒 性能记录 ([New-MpPerformanceRecording](#new-mpperformancerecording)) 并报告对 Microsoft Defender 防病毒 扫描产生最大影响的文件路径、文件扩展名和进程。

性能分析器可深入了解可能导致性能降低的有问题的Microsoft Defender 防病毒。 此工具是"AS IS"提供的，并不用于提供有关排除项的建议。 排除项会降低终结点上的保护级别。 应谨慎定义排除项（如果有）。

有关性能分析器详细信息，请参阅 [Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer) 文档。

**受支持的操作系统版本**

Windows版本 10 及更高版本。

> [!NOTE]
> 此功能从平台版本 4.18.2108.X 及更高版本开始提供。

#### <a name="examples-get-mpperformancereport"></a>示例：Get-MpPerformanceReport

##### <a name="example-1-single-query"></a>示例 1：单个查询 

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:20
```

##### <a name="example-2-multiple-queries"></a>示例 2：多个查询 

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10 -TopExtensions:10 -TopProcesses:10 -TopScans:10
```

##### <a name="example-3-nested-queries"></a>示例 3：嵌套查询 

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopExtensionsPerProcess:3 -TopScansPerExtensionPerProcess:3
```

##### <a name="example-4-using--minduration-parameter"></a>示例 4：使用 -MinDuration 参数

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:100 -MinDuration:100ms
```

#### <a name="parameters-get-mpperformancereport"></a>参数：Get-MpPerformanceReport

##### <a name="-minduration"></a>-MinDuration
指定报告中包含的文件、扩展名和进程的任何扫描或总扫描持续时间的最短持续时间;接受  **0.1234567sec**、 **0.1234ms**、 **0.1us** 或有效 TimeSpan 等值。

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False 
Accept wildcard characters: False
```

##### <a name="-path"></a>-Path
指定要 () 位置的路径。

```yaml
Type: String
Position: 0
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### <a name="-topextensions"></a>-TopExtensions 
指定要输出的顶级扩展数，按"持续时间"排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topextensionsperprocess"></a>-TopExtensionsPerProcess 
指定要针对每个顶部进程输出的顶级扩展数，按"持续时间"排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfiles"></a>-TopFiles
请求一个顶级文件报告，并指定要输出的顶级文件数（按"持续时间"排序）。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfilesperextension"></a>-TopFilesPerExtension 
指定要针对每个顶部扩展名输出多少个顶级文件，按"持续时间"排序。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfilesperprocess"></a>-TopFilesPerProcess
指定每个顶部进程要输出的顶级文件数，按"持续时间"排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topprocesses"></a>-TopProcesses
请求一个顶级进程报告，并指定要输出的顶级进程数（按"持续时间"排序）。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topprocessesperextension"></a>-TopProcessesPerExtension 
指定要针对每个顶级扩展输出的顶级进程数，按"持续时间"排序。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topprocessesperfile"></a>-TopProcessesPerFile
指定要针对每个顶部文件输出的顶级进程数，按"持续时间"排序。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscans"></a>-TopScans
请求一个顶级扫描报告，并指定要输出的顶级扫描数（按"持续时间"排序）。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperextension"></a>-TopScansPerExtension
指定要针对每个顶部扩展输出的顶级扫描数，按"持续时间"排序。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperextensionperprocess"></a>-TopScansPerExtensionPerProcess 
指定要针对每个顶部进程的每个顶级扩展输出的顶级扫描数，按"持续时间"排序。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperfile"></a>-TopScansPerFile
指定要针对每个顶部文件输出的顶级扫描数，按"持续时间"排序。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperfileperextension"></a>-TopScansPerFilePerExtension 
指定要针对每个顶部扩展名的每个顶部文件输出多少个顶部扫描，按"持续时间"排序。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperfileperprocess"></a>-TopScansPerFilePerProcess 
指定每个顶部进程每个顶部文件的输出（按"持续时间"排序）的顶级扫描次数。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperprocess"></a>-TopScansPerProcess 
指定要针对"首要进程"报告中每个顶级进程输出的顶级扫描数，按"持续时间"排序。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperprocessperextension"></a>-TopScansPerProcessPerExtension
指定每个顶部扩展的每个顶级进程的输出的顶级扫描数，按"持续时间"排序。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperprocessperfile"></a>-TopScansPerProcessPerFile
指定每个顶部文件的每个顶部进程的输出的顶级扫描数，按"持续时间"排序。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```
