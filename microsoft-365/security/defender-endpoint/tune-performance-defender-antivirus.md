---
title: 用于Microsoft Defender 防病毒的性能分析器
description: 介绍优化Microsoft Defender 防病毒性能的过程。
keywords: tune， performance， microsoft defender for endpoint， defender 防病毒
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
ms.openlocfilehash: 73afd0751e34fbb020019e6f28056c9f2a935c07
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788581"
---
# <a name="performance-analyzer-for-microsoft-defender-antivirus"></a>用于Microsoft Defender 防病毒的性能分析器

**适用对象**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

**什么是性能分析器Microsoft Defender 防病毒？**

在某些情况下，可能需要在扫描特定文件和文件夹时调整Microsoft Defender 防病毒的性能。 性能分析器是一种 PowerShell 命令行工具，可帮助确定哪些文件、文件扩展名和进程可能导致各个终结点上的性能问题。 此信息可用于更好地评估性能问题并应用修正操作。

要分析的一些选项包括：

- 影响扫描时间的顶级文件
- 影响扫描时间的顶级进程
- 影响扫描时间的顶级文件扩展名
- 组合 - 例如，每个扩展名的顶级文件、每个文件的最高扫描、每个进程每个文件的最高扫描数

## <a name="running-performance-analyzer"></a>运行性能分析器

运行性能分析器的高级过程涉及以下步骤：

1. 运行性能分析器，收集终结点上Microsoft Defender 防病毒事件的性能记录。

   > [!NOTE]
   > 通过性能分析器记录 **microsoft-Antimalware-Engine** 类型的Microsoft Defender 防病毒事件的性能。

2. 使用不同的录制报表分析扫描结果。

## <a name="using-performance-analyzer"></a>使用性能分析器

若要开始录制系统事件，请在管理模式下打开 PowerShell 并执行以下步骤：

1. 运行以下命令以启动录制：

   `New-MpPerformanceRecording -RecordTo <recording.etl>`

    其中 `-RecordTo` 参数指定保存跟踪文件的完整路径位置。 有关更多 cmdlet 信息，请参阅[Microsoft Defender 防病毒 cmdlet](/powershell/module/defender)。

2. 如果有些进程或服务被认为会影响性能，请执行相关任务来重现情况。

3. 按 **ENTER** 停止并保存录制，或 **按 Ctrl+C** 取消录制。

4. 使用性能分析器的 `Get-MpPerformanceReport`参数分析结果。 例如，在执行命令 `Get-MpPerformanceReport -Path <recording.etl> -TopFiles 3 -TopScansPerFile 10`时，向用户提供影响性能的前 3 个文件的前 10 个扫描列表。

有关命令行参数和选项的详细信息，请参阅 [New-MpPerformanceRecording](#new-mpperformancerecording) 和 [Get-MpPerformanceReport](#get-mpperformancereport)。

> [!NOTE]
> 运行录制时，如果收到错误“无法启动性能录制，因为Windows性能录制器已在录制”，请运行以下命令以使用新命令停止现有跟踪：**wpr -cancel -instancename MSFT_MpPerformanceRecording**

### <a name="performance-tuning-data-and-information"></a>性能优化数据和信息

根据查询，用户将能够查看扫描计数、持续时间 (总计/最小/平均/最大/中位数) 、路径、进程和扫描原因的数据。 下图显示了扫描影响前 10 个文件的简单查询的示例输出。

:::image type="content" source="images/example-output.png" alt-text="基本 TopFiles 查询的示例输出" lightbox="images/example-output.png":::

### <a name="additional-functionality-exporting-and-converting-to-csv-and-json"></a>其他功能：导出并转换为 CSV 和 JSON

性能分析器的结果也可以导出并转换为 CSV 或 JSON 文件。
有关描述通过示例代码“导出”和“转换”过程的示例，请参阅下文。

#### <a name="for-csv"></a>对于 CSV

- **导出**： `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | Export-CSV -Path:.\Repro-Install-Scans.csv -Encoding:UTF8 -NoTypeInformation`

- **若要转换**： `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:100). TopScans | ConvertTo-Csv -NoTypeInformation`

#### <a name="for-json"></a>对于 JSON

- **若要转换**： `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | ConvertTo-Json -Depth:1`

### <a name="requirements"></a>要求

Microsoft Defender 防病毒性能分析器具有以下先决条件：

- 支持的Windows版本：Windows 10、Windows 11和Windows Server 2016及更高版本
- 平台版本：4.18.2108.7+
- PowerShell 版本：PowerShell 版本 5.1、PowerShell ISE、远程 PowerShell (4.18.2201.10+) 、PowerShell 7.x (4.18.2201.10+) 

## <a name="powershell-reference"></a>PowerShell 参考

有两个新的 PowerShell cmdlet 用于优化Microsoft Defender 防病毒的性能：

- [New-MpPerformanceRecording](#new-mpperformancerecording)
- [Get-MpPerformanceReport](#get-mpperformancereport)

### <a name="new-mpperformancerecording"></a>New-MpPerformanceRecording

以下部分介绍新 PowerShell cmdlet New-MpPerformanceRecording 的引用。 此 cmdlet 收集Microsoft Defender 防病毒扫描的性能记录。

#### <a name="syntax-new-mpperformancerecording"></a>语法：New-MpPerformanceRecording

```powershell
New-MpPerformanceRecording -RecordTo <String >
```

#### <a name="description-new-mpperformancerecording"></a>说明：New-MpPerformanceRecording

该 `New-MpPerformanceRecording` cmdlet 收集Microsoft Defender 防病毒扫描的性能记录。 这些性能录制包含 Microsoft-Antimalware-Engine 和 NT 内核进程事件，可在集合后使用 [Get-MpPerformanceReport](#get-mpperformancereport) cmdlet 进行分析。

此 `New-MpPerformanceRecording` cmdlet 可深入了解可能导致Microsoft Defender 防病毒性能下降的问题文件。 此工具提供“AS IS”，不用于提供有关排除的建议。 排除可以降低终结点上的保护级别。 应谨慎定义排除项（如果有）。

有关性能分析器的详细信息，请[参阅性能分析器](/windows-hardware/test/wpt/windows-performance-analyzer)文档。

> [!IMPORTANT]
> 此 cmdlet 需要提升的管理员权限。

**支持的 OS 版本**：

Windows版本 10 及更高版本。

> [!NOTE]
> 此功能从平台版本 4.18.2108.X 及更高版本开始可用。

#### <a name="examples-new-mpperformancerecording"></a>示例：New-MpPerformanceRecording

##### <a name="example-1-collect-a-performance-recording-and-save-it"></a>示例 1：收集性能录制并保存

```powershell
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl
```

上述命令收集性能记录并将其保存到指定路径： **.\Defender-scans.etl**。

##### <a name="example-2-collect-a-performance-recording-for-remote-powershell-session"></a>示例 2：收集远程 PowerShell 会话的性能录制

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
New-MpPerformanceRecording -RecordTo C:\LocalPathOnServer02\trace.etl -Session $s
```

上述命令在 Server02 (上收集由参数会话) 的参数$s指定的性能记录，并将其保存到指定路径： **C：\LocalPathOnServer02\trace.etl** on Server02。

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

指定要在其中创建和保存Microsoft Defender 防病毒性能录制的 PSSession 对象。 使用此参数时，RecordTo 参数引用远程计算机上的本地路径。 适用于 Defender 平台版本 4.18.2201.10。

```yaml
Type: PSSession[]
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="get-mpperformancereport"></a>Get-MpPerformanceReport

以下部分介绍 Get-MpPerformanceReport PowerShell cmdlet。 分析和报告Microsoft Defender 防病毒 (MDAV) 性能录制。

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

该 `Get-MpPerformanceReport` cmdlet 分析以前收集的Microsoft Defender 防病毒性能记录 ([New-MpPerformanceRecording](#new-mpperformancerecording)) ，并报告对Microsoft Defender 防病毒扫描产生最大影响的文件路径、文件扩展名和进程。

性能分析器可深入了解可能导致Microsoft Defender 防病毒性能下降的问题文件。 此工具提供“AS IS”，不用于提供有关排除的建议。 排除可以降低终结点上的保护级别。 应谨慎定义排除项（如果有）。

有关性能分析器的详细信息，请[参阅性能分析器](/windows-hardware/test/wpt/windows-performance-analyzer)文档。

**支持的 OS 版本**：

Windows版本 10 及更高版本。

> [!NOTE]
> 此功能从平台版本 4.18.2108.X 及更高版本开始可用。

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

指定报表中包含的文件、扩展名和进程的任何扫描或总扫描持续时间的最短持续时间;接受  **0.1234567sec**、 **0.1234ms**、 **0.1us** 或有效 TimeSpan 等值。

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-path"></a>-Path

指定 () 到一个或多个位置的路径。

```yaml
Type: String
Position: 0
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### <a name="-topextensions"></a>-TopExtensions

指定要输出的顶级扩展数，按“Duration”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topextensionsperprocess"></a>-TopExtensionsPerProcess

指定每个顶级进程要输出的顶级扩展数，按“Duration”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfiles"></a>-TopFiles

请求顶级文件报表，并指定要输出的顶级文件数（按“持续时间”排序）。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfilesperextension"></a>-TopFilesPerExtension

指定每个顶级扩展插件要输出的顶级文件数，按“Duration”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfilesperprocess"></a>-TopFilesPerProcess

指定每个顶级进程要输出的顶级文件数，按“Duration”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topprocesses"></a>-TopProcesses

请求顶级进程报表，并指定要输出的顶级进程数（按“持续时间”排序）。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topprocessesperextension"></a>-TopProcessesPerExtension

指定要为每个顶级扩展输出的顶级进程数，按“Duration”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topprocessesperfile"></a>-TopProcessesPerFile

指定每个顶级文件要输出的顶级进程数，按“Duration”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscans"></a>-TopScans

请求顶部扫描报表，并指定要输出的顶级扫描数（按“持续时间”排序）。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperextension"></a>-TopScansPerExtension

指定要为每个顶部扩展输出的顶级扫描数，按“Duration”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperextensionperprocess"></a>-TopScansPerExtensionPerProcess

指定每个顶部进程的每个顶部扩展输出的顶级扫描数，按“Duration”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperfile"></a>-TopScansPerFile

指定要为每个顶部文件输出的顶级扫描数，按“Duration”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperfileperextension"></a>-TopScansPerFilePerExtension

指定每个顶部扩展名的每个顶部文件要输出的顶级扫描数，按“Duration”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperfileperprocess"></a>-TopScansPerFilePerProcess

指定每个顶部进程的每个顶部文件的输出顶部扫描数，按“Duration”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperprocess"></a>-TopScansPerProcess

指定要为顶部进程报表中的每个顶级进程输出的顶级扫描数，按“持续时间”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperprocessperextension"></a>-TopScansPerProcessPerExtension

指定每个顶部扩展的每个顶部进程的输出的顶级扫描数，按“Duration”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperprocessperfile"></a>-TopScansPerProcessPerFile

指定每个顶部文件的每个顶部进程的输出顶部扫描数，按“持续时间”排序。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```
> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)
