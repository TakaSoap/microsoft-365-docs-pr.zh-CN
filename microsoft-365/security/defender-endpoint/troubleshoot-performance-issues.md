---
title: 解决性能问题
description: 解决与 Microsoft Defender for Endpoint 中的实时保护服务相关的高 CPU 使用率问题。
keywords: 疑难解答， 性能， 高 CPU 使用率， 高 CPU 使用率， 错误， 修复， 更新合规性， oms， 监视器， 报告， Microsoft Defender 防病毒
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
ms.date: 10/19/2021
audience: ITPro
ms.topic: troubleshooting
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 1dfe480f36d99acfdc9dcb36e63d2eed4f22054a
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074782"
---
# <a name="troubleshoot-performance-issues-related-to-real-time-protection"></a>解决与实时保护相关的性能问题


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

如果你的系统具有与 Microsoft Defender for Endpoint 中的实时保护服务相关的高 CPU 使用率或性能问题，你可以向 Microsoft 支持部门提交票证。 按照收集诊断[Microsoft Defender 防病毒中的步骤操作](collect-diagnostic-data.md)。

作为管理员，还可以自行解决这些问题。

首先，您可能需要检查该问题是否由另一个软件导致。 请阅读 [与供应商核实防病毒排除项](#check-with-vendor-for-antivirus-exclusions)。

否则，你可以按照分析 Microsoft 保护日志 中的步骤识别与标识的 [性能问题相关的软件](#analyze-the-microsoft-protection-log)。

还可以按照以下步骤向 Microsoft 支持人员提供提交的其他日志：

- [使用进程监视器捕获进程日志](#capture-process-logs-using-process-monitor)
- [使用 Performance Recorder Windows性能日志](#capture-performance-logs-using-windows-performance-recorder)

## <a name="check-with-vendor-for-antivirus-exclusions"></a>与供应商核实防病毒排除项

如果您能够轻松识别影响系统性能的软件，请转到软件供应商的知识库或支持中心。 如果他们对防病毒排除项有建议，请进行搜索。 如果供应商的网站没有支持票证，可以打开支持票证，并要求他们发布一个支持票证。

我们建议软件供应商遵循与行业合作中的各种准则，尽量减少 [误报](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/)。 供应商可以通过客户门户提交[Microsoft 安全智能软件](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper)。

## <a name="analyze-the-microsoft-protection-log"></a>分析 Microsoft 保护日志

在 **MPLog-xxxxxxxx-xxxxxx.log** 中，可以找到以 *EstimatedImpact* 格式运行软件对性能的影响估计信息：

`Per-process counts:ProcessImageName: smsswd.exe, TotalTime: 6597, Count: 1406, MaxTime: 609, MaxTimeFile: \Device\HarddiskVolume3\_SMSTaskSequence\Packages\WQ1008E9\Files\FramePkg.exe, EstimatedImpact: 65%`

<br>

****

|字段名|说明|
|---|---|
|ProcessImageName|进程映像名称|
|TotalTime|扫描此过程访问的文件所用的累积持续时间（以毫秒为单位）|
|Count|此过程访问的已扫描文件数|
|MaxTime|此过程访问的文件的最长单次扫描的持续时间（以毫秒为单位）|
|MaxTimeFile|此进程访问的文件的路径，其中记录了持续时间最长的 `MaxTime` 扫描|
|EstimatedImpact|在此过程遇到扫描活动的时间段外，扫描此进程访问的文件所花费的时间百分比|
|

如果性能影响很大，请尝试按照配置并验证应用扫描的排除项中的步骤将进程添加到[Microsoft Defender 防病毒排除项](collect-diagnostic-data.md)。

如果上一步不能解决问题，可以通过以下部分中的进程监视器或Windows[记录](#capture-performance-logs-using-windows-performance-recorder)器来收集[](#capture-process-logs-using-process-monitor)更多信息。

## <a name="capture-process-logs-using-process-monitor"></a>使用进程监视器捕获进程日志

Process Monitor (ProcMon) 是一种高级监视工具，可显示实时进程。 您可以使用它来捕获性能问题发生时。

1. 将 [进程监视器 v3.60](/sysinternals/downloads/procmon) 下载到类似 的文件夹 `C:\temp` 。

2. 若要删除文件的 Web 标记，请进行以下操作：
    1. 右键单击 **"ProcessMonitor.zip** 并选择"属性 **"。**
    1. 在"*常规"选项卡* 下，查找"安全性 *"。*
    1. 选中"取消阻止 **"旁边的框**。
    1. 选择“**应用**”。

    ![删除 MOTW。](images/procmon-motw.png)

3. 在 中解压缩文件 `C:\temp` ，使文件夹路径为 `C:\temp\ProcessMonitor` 。

4. 将 **ProcMon.exe** 复制到Windows故障排除Windows客户端或服务器。

5. 在运行 ProcMon 之前，请确保已关闭与 CPU 使用率高问题不相关的所有其他应用程序。 执行此操作将最大程度地减少要检查的进程数。

6. 可以通过两种方式启动 ProcMon。
    1. 右键单击 **"ProcMon.exe** 并选择"**以管理员角色运行"。**

        由于日志记录会自动启动，请选择放大镜图标以停止当前捕获或使用键盘快捷方式 **Ctrl+E。**

        ![放大镜图标。](images/procmon-magglass.png)

        若要验证是否已停止捕获，请检查放大镜图标现在是否显示红色 X。

        ![红色斜杠。](images/procmon-magglass-stop.png)

        接下来，若要清除之前捕获，请选择橡皮擦图标。

        ![清除图标。](images/procmon-eraser-clear.png)

        或使用键盘快捷方式 **Ctrl+X。**

    2. 第二种方式是以管理员角色 **运行命令行** ，然后从进程监视器路径运行：

        ![cmd procmon。](images/cmd-procmon.png)

        ```console
        Procmon.exe /AcceptEula /Noconnect /Profiling
        ```

        > [!TIP]
        > 在捕获数据时使 ProcMon 窗口尽可能小，以便轻松启动和停止跟踪。
        >
        > ![最小化 Procmon。](images/procmon-minimize.png)

7. 执行步骤 6 中的其中一个过程后，你将看到设置筛选器的选项。 选择“确定”。 捕获完成后，你始终可以筛选结果。

    ![将进程名称筛选掉为"系统排除"。](images/procmon-filter-options.png)

8. 若要启动捕获，请再次选择放大镜图标。

9. 重现问题。

    > [!TIP]
    > 等待问题完全重现，然后记下开始跟踪的时间戳。

10. 在高 CPU 使用率条件期间具有两到四分钟的进程活动后，通过选择放大镜图标停止捕获。

11. 若要使用唯一的名称和 .pml 格式保存捕获，请选择"文件 **"，然后选择** "保存 **..."。** 确保选择单选按钮"所有 **事件** "和"本机进程监视器格式 (**PML) "**。

    ![保存设置。](images/procmon-savesettings1.png)

12. 为了更好地进行跟踪，将默认路径从 `C:\temp\ProcessMonitor\LogFile.PML` 以下 `C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML` 位置更改为：
    - `%ComputerName%` 是设备名称
    - `MMDDYEAR` 是月、日、年
    - `Repro_of_issue` 是你要尝试重现的问题的名称

    > [!TIP]
    > 如果您有一个工作系统，您可能需要获取一个示例日志进行比较。

13. 压缩 .pml 文件，并提交到 Microsoft 支持。

## <a name="capture-performance-logs-using-windows-performance-recorder"></a>使用 Performance Recorder Windows性能日志

可以使用 WPR Windows记录器 (WPR) 向 Microsoft 支持人员提交其他信息。 WPR 是一个强大的录制工具，可创建用于记录Windows跟踪。

WPR 是 Windows Assessment and Deployment Kit (Windows ADK) 的一部分，可以从下载并安装 Windows [ADK 下载](/windows-hardware/get-started/adk-install)。 您还可以下载它作为 Windows 10 SDK 中 Windows 10软件开发[工具包的一部分](https://developer.microsoft.com/windows/downloads/windows-10-sdk/)。

可以按照使用 WPR UI 捕获性能日志中的步骤使用 [WPR 用户界面](#capture-performance-logs-using-the-wpr-ui)。

或者，也可以按照使用 [WPR CLI](#capture-performance-logs-using-the-wpr-cli)捕获性能日志中的步骤，使用 Windows 8 和更高版本中提供的命令行工具 *wpr.exe*。

### <a name="capture-performance-logs-using-the-wpr-ui"></a>使用 WPR UI 捕获性能日志

> [!TIP]
> 如果多个设备遇到此问题，请使用 RAM 最多的设备。

1. 下载并安装 WPR。

2. 在 *Windows工具包"* 下，右键单击Windows **录制器"。**

    !["开始"菜单。](images/wpr-01.png)

    选择 **"更多"。** 选择 **"以管理员角色运行"。**

3. 当出现"用户帐户控制"对话框时，选择"**是"。**

    ![UAC。](images/wpt-yes.png)

4. 接下来，下载 [Microsoft Defender for Endpoint 分析](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp) 配置文件，并另存为 `MDAV.wprp` 文件夹，如 `C:\temp` 。

5. 在"WPR"对话框中，选择"**更多选项"。**

    ![选择更多选项。](images/wpr-03.png)

6. 选择 **"添加配置文件..."，** 然后浏览到文件 `MDAV.wprp` 的路径。

7. 此后，你应该会看到"自定义度量"下的 *"Microsoft Defender 终结点分析*"下的新配置文件集。

    ![in-file.](images/wpr-infile.png)

    > [!WARNING]
    > 如果 Windows 服务器具有 64 GB 或更多的 RAM，请使用自定义度量 `Microsoft Defender for Endpoint analysis for large servers` ，而不是 `Microsoft Defender for Endpoint analysis` 。 否则，你的系统可能会占用大量未分页的池内存或缓冲区，这可能会导致系统不稳定。 您可以通过展开"资源分析"选择要 **添加的配置文件**。
    此自定义配置文件提供深入性能分析的必要上下文。

8. 若要在 WPR UI 中使用自定义度量 Microsoft Defender for Endpoint 详细分析配置文件：

    1. 确保未在一级会审、资源分析和方案分析组 *下选择任何* 配置文件。
    2. 选择 **"自定义度量"。**
    3. 选择 **Microsoft Defender 进行终结点分析**。
    4. 在 **"详细信息级别***"下选择"详细*"。
    5. 在 **"日志记录****"模式下选择**"文件或内存"。

    > [!IMPORTANT]
    > 如果用户可以直接 *重现* 性能问题，则应该选择"文件"以使用文件日志记录模式。 大多数问题属于此类别。 但是，如果用户无法直接重现问题，但在出现问题后很容易注意到该问题，则用户应选择"内存"以使用内存日志记录模式。 这可确保跟踪日志不会由于长时间运行而过度增长。

9. 现在，你已准备好收集数据了。 退出与重现性能问题不相关的所有应用程序。 可以选择" **隐藏选项** "，将 WPR 窗口所占用的空间保持较小。

    ![隐藏选项。](images/wpr-08.png)

    > [!TIP]
    > 尝试以完整的秒数开始跟踪。 例如，01：30：00。 这样更易于分析数据。 此外，尝试跟踪重现问题的精确时间戳。

10. 选择“开始”。

    ![选择"开始跟踪"。](images/wpr-09.png)

11. 重现问题。

    > [!TIP]
    > 使数据收集不超过五分钟。 2 到 3 分钟是一个很好的范围，因为正在收集大量的数据。

12. 选择“保存”。

    ![选择"保存"。](images/wpr-10.png)

13. 填写 **问题的详细说明类型** ：包含问题相关信息以及问题重现方法。

    ![填写详细信息。](images/wpr-12.png)

    1. 选择 **"文件名："** 以确定跟踪文件的保存位置。 默认情况下，它保存到 `%user%\Documents\WPR Files\` 。
    1. 选择“保存”。

14. 在合并跟踪时等待。

    ![WPR 收集常规跟踪。](images/wpr-13.png)

15. 保存跟踪后，选择"打开 **文件夹"。**

    ![已保存 WPR 跟踪。](images/wpr-14.png)

    在提交到 Microsoft 支持时同时包括 文件和 文件夹。

    ![文件和文件夹。](images/wpr-15.png)

### <a name="capture-performance-logs-using-the-wpr-cli"></a>使用 WPR CLI 捕获性能日志

命令行工具 *wpr.exe* 操作系统的一部分，从 Windows 8。 若要使用命令行工具收集 WPR 跟踪，wpr.exe：

1. 将 **[Microsoft Defender for Endpoint 分析](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** 配置文件的性能跟踪下载到本地目录中名为 的文件，例如 `MDAV.wprp` `C:\traces` 。

2. 右键单击"**开始**"菜单图标并选择"管理员Windows PowerShell (") "命令提示 **(") "** 管理员"命令提示符窗口。

3. 当出现"用户帐户控制"对话框时，选择"**是"。**

4. 在提升的提示符下，运行以下命令以启动 Microsoft Defender for Endpoint 性能跟踪：

    ```console
    wpr.exe -start C:\traces\MDAV.wprp!WD.Verbose -filemode
    ```

    > [!WARNING]
    > 如果您的 Windows 服务器具有 64 GB 或 RAM 或更多，请分别使用配置文件而不是配置文件和 `WDForLargeServers.Light` `WDForLargeServers.Verbose` `WD.Light` `WD.Verbose` 。 否则，你的系统可能会占用大量未分页的池内存或缓冲区，这可能会导致系统不稳定。

5. 重现问题。

    > [!TIP]
    > 保持数据收集不超过五分钟。 根据具体方案，2 到 3 分钟是一个很好的范围，因为正在收集大量的数据。

6. 在提升的提示符下，运行以下命令以停止性能跟踪，确保提供有关问题以及如何重现问题的信息：

    ```console
    wpr.exe -stop merged.etl "Timestamp when the issue was reproduced, in HH:MM:SS format" "Description of the issue" "Any error that popped up"
    ```

7. 等待跟踪合并。

8. 在提交到 Microsoft 支持人员时同时包括 文件和 文件夹。

## <a name="see-also"></a>另请参阅

- [收集Microsoft Defender 防病毒诊断数据](collect-diagnostic-data.md)
- [配置并验证扫描的Microsoft Defender 防病毒项](configure-exclusions-microsoft-defender-antivirus.md)
