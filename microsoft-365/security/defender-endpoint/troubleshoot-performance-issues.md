---
title: 解决性能问题
description: 排查与Microsoft Defender for Endpoint中的实时保护服务相关的 CPU 使用率过高的问题。
keywords: 故障排除， 性能， 高 CPU 利用率， 高 CPU 使用率， 错误， 修复， 更新符合性， oms， monitor， report， Microsoft Defender 防病毒
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
ms.openlocfilehash: dd89a2cf6d6a8cd355258376b93ca12c37ad501f
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788669"
---
# <a name="troubleshoot-performance-issues-related-to-real-time-protection"></a>排查与实时保护相关的性能问题


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

如果系统在Microsoft Defender for Endpoint中遇到与实时保护服务相关的 CPU 使用率高或性能问题，则可以向 Microsoft 支持部门提交票证。 按照[收集Microsoft Defender 防病毒诊断数据](collect-diagnostic-data.md)中的步骤进行操作。

作为管理员，还可以自行排查这些问题。

首先，你可能想要检查问题是否由另一个软件引起。 阅读 [与供应商的防病毒排除检查](#check-with-vendor-for-antivirus-exclusions)。

否则，可以按照“ [分析 Microsoft 保护日志](#analyze-the-microsoft-protection-log)”中的步骤来确定与标识的性能问题相关的软件。

还可以按照以下步骤向 Microsoft 支持人员提交其他日志：

- [使用进程监视器捕获进程日志](#capture-process-logs-using-process-monitor)
- [使用Windows性能记录器捕获性能日志](#capture-performance-logs-using-windows-performance-recorder)

## <a name="check-with-vendor-for-antivirus-exclusions"></a>请与供应商核实防病毒排除项

如果可以轻松识别影响系统性能的软件，请转到软件供应商的知识库或支持中心。 如果有有关防病毒排除的建议，请搜索。 如果供应商的网站没有它们，可以与他们一起开具支持票证，并要求他们发布一个支持票证。

我们建议软件供应商遵循 [与行业合作的各种准则，以最大程度地减少误报](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/)。 供应商可以通过[Microsoft 安全智能门户](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper)提交其软件。

## <a name="analyze-the-microsoft-protection-log"></a>分析 Microsoft 保护日志

在 **MPLog-xxxxxxxx-xxxxxx.log** 中，可以找到运行软件的估计性能影响信息，如 *EstimatedImpact*：

`Per-process counts:ProcessImageName: smsswd.exe, TotalTime: 6597, Count: 1406, MaxTime: 609, MaxTimeFile: \Device\HarddiskVolume3\_SMSTaskSequence\Packages\WQ1008E9\Files\FramePkg.exe, EstimatedImpact: 65%`

<br>

****

|字段名|说明|
|---|---|
|ProcessImageName|处理映像名称|
|TotalTime|在此进程访问的文件扫描中花费的累积持续时间（毫秒）|
|Count|此过程访问的扫描文件数|
|MaxTime|此过程访问的文件的最长单次扫描持续时间（以毫秒为单位）|
|MaxTimeFile|此过程访问的文件的路径，记录持续时间最长的扫描 `MaxTime` 时间|
|EstimatedImpact|此进程在扫描过程中经历扫描活动期间访问的文件所花费的时间百分比|
|

如果性能影响很大，请尝试按照[配置和验证Microsoft Defender 防病毒扫描的排除](collect-diagnostic-data.md)项中的步骤将进程添加到路径/进程排除项。

如果上一步无法解决问题，可通过以下部分中的[进程监视器](#capture-process-logs-using-process-monitor)或[Windows性能记录器](#capture-performance-logs-using-windows-performance-recorder)收集详细信息。

## <a name="capture-process-logs-using-process-monitor"></a>使用进程监视器捕获进程日志

进程监视器 (ProcMon) 是一种高级监视工具，可以显示实时进程。 可以使用它来捕获性能问题，因为它正在发生。

1. 将 [进程监视器 v3.60](/sysinternals/downloads/procmon) 下载到文件夹，例如 `C:\temp`。

2. 若要删除该文件的 Web 标记，请执行以下操作：
    1. 右键单击 **ProcessMonitor.zip** 并选择 **“属性**”。
    1. 在“ *常规* ”选项卡下，查找 *安全性*。
    1. 选中 **“取消阻止”旁边的** 框。
    1. 选择“**应用**”。

    :::image type="content" source="images/procmon-motw.png" alt-text="“删除 MOTW”页" lightbox="images/procmon-motw.png":::

3. 解压缩文件 `C:\temp` ，使文件夹路径为 `C:\temp\ProcessMonitor`。

4. 将 **ProcMon.exe** 复制到要进行故障排除Windows客户端或Windows服务器。

5. 在运行 ProcMon 之前，请确保已关闭与 CPU 使用率过高问题无关的所有其他应用程序。 执行此操作可最大程度地减少要检查的进程数。

6. 可以通过两种方式启动 ProcMon。
    1. 右键单击 **ProcMon.exe** ，然后选择 **“以管理员身份运行**”。

        由于日志记录自动启动，请选择放大镜图标以停止当前捕获或使用键盘快捷方式 **Ctrl+E**。

        :::image type="content" source="images/procmon-magglass.png" alt-text="放大镜图标" lightbox="images/procmon-magglass.png":::

        若要验证是否已停止捕获，请检查放大镜图标现在是否显示为红色 X。

        :::image type="content" source="images/procmon-magglass-stop.png" alt-text="红色斜杠" lightbox="images/procmon-magglass-stop.png":::

        接下来，若要清除前面的捕获，请选择橡皮擦图标。

        :::image type="content" source="images/procmon-eraser-clear.png" alt-text="清除图标" lightbox="images/procmon-eraser-clear.png":::

        或者使用键盘快捷方式 **Ctrl+X**。

    2. 第二种方法是以管理员身份运行 **命令行** ，然后从进程监视器路径运行：

       :::image type="content" source="images/cmd-procmon.png" alt-text="cmd procmon" lightbox="images/cmd-procmon.png":::

        ```console
        Procmon.exe /AcceptEula /Noconnect /Profiling
        ```

        > [!TIP]
        > 捕获数据时使 ProcMon 窗口尽可能小，以便轻松启动和停止跟踪。
        >
        > :::image type="content" source="images/procmon-minimize.png" alt-text="显示最小化 Procmon 的页面" lightbox="images/procmon-minimize.png":::

7. 按照步骤 6 中的某个过程操作后，接下来会看到设置筛选器的选项。 选择“确定”。 捕获完成后，始终可以筛选结果。

   :::image type="content" source="images/procmon-filter-options.png" alt-text="选择“系统排除”作为筛选出进程名称的页面" lightbox="images/procmon-filter-options.png":::

8. 若要开始捕获，请再次选择放大镜图标。

9. 重现问题。

    > [!TIP]
    > 等待问题完全重现，然后记下跟踪启动时的时间戳。

10. 在 CPU 使用率较高的情况下有两到四分钟的进程活动后，请选择放大镜图标来停止捕获。

11. 若要使用唯一名称和 .pml 格式保存捕获，请选择 **“文件** ”，然后选择 **“保存...**”。请务必选择单选按钮 **“所有事件** ”和 **“本机进程监视器格式” (PML)**。

    :::image type="content" source="images/procmon-savesettings1.png" alt-text="“保存设置”页" lightbox="images/procmon-savesettings1.png":::

12. 为了更好地跟踪，请将默认路径从 `C:\temp\ProcessMonitor\LogFile.PML` 以下位置更改为 `C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML` ：
    - `%ComputerName%` 是设备名称
    - `MMDDYEAR` 是月、日和年
    - `Repro_of_issue` 是您尝试重现的问题的名称

    > [!TIP]
    > 如果有工作系统，可能需要获取要比较的示例日志。

13. 压缩 .pml 文件并将其提交给 Microsoft 支持部门。

## <a name="capture-performance-logs-using-windows-performance-recorder"></a>使用Windows性能记录器捕获性能日志

可以使用Windows性能记录器 (WPR) 在提交给 Microsoft 支持部门时包含其他信息。 WPR 是一种功能强大的录制工具，可为Windows录制创建事件跟踪。

WPR 是WINDOWS评估和部署工具包 (Windows ADK) 的一部分，可从[下载和安装 Windows ADK](/windows-hardware/get-started/adk-install) 下载。 还可以将其下载为 Windows 10 [SDK 的Windows 10](https://developer.microsoft.com/windows/downloads/windows-10-sdk/)软件开发工具包的一部分。

可以通过 [使用 WPR UI 执行捕获性能日志](#capture-performance-logs-using-the-wpr-ui)中的步骤来使用 WPR 用户界面。

或者，也可以使用命令行工具 *wpr.exe*，该工具可在Windows 8及更高版本中使用，方法是 [按照 WPR CLI 捕获性能日志](#capture-performance-logs-using-the-wpr-cli)中的步骤操作。

### <a name="capture-performance-logs-using-the-wpr-ui"></a>使用 WPR UI 捕获性能日志

> [!TIP]
> 如果多个设备遇到此问题，请使用 RAM 最多的设备。

1. 下载并安装 WPR。

2. 在 *Windows工具包* 下，右键单击 **Windows性能记录器**。

   :::image type="content" source="images/wpr-01.png" alt-text="&quot;开始&quot;菜单" lightbox="images/wpr-01.png":::

    选择 **“更多**”。 选择 **“以管理员身份运行**”。

3. 出现“用户帐户控制”对话框时，选择 **“是**”。

   :::image type="content" source="images/wpt-yes.png" alt-text="UAC 页" lightbox="images/wpt-yes.png":::

4. 接下来，下载[Microsoft Defender for Endpoint分析](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)配置文件，并保存`MDAV.wprp`到文件夹，例如`C:\temp`。

5. 在“WPR”对话框中，选择 **“更多”选项**。

   :::image type="content" source="images/wpr-03.png" alt-text="可在其中选择更多选项的页面" lightbox="images/wpr-03.png":::


6. 选择 **“添加配置文件...** ”并浏览到文件的 `MDAV.wprp` 路径。

7. 之后，应会在“*自定义度量*”下看到名为 *“Microsoft Defender for Endpoint分析”* 的新配置文件集。

   :::image type="content" source="images/wpr-infile.png" alt-text="文件内" lightbox="images/wpr-infile.png":::

    > [!WARNING]
    > 如果Windows服务器具有 64 GB 的 RAM 或更高版本，请使用自定义度量，而不是`Microsoft Defender for Endpoint analysis`自定义度量`Microsoft Defender for Endpoint analysis for large servers`值。 否则，系统可能会消耗大量非分页池内存或缓冲区，从而导致系统不稳定。 可以通过扩展 **资源分析** 来选择要添加的配置文件。
    此自定义配置文件为深入的性能分析提供了必要的上下文。

8. 若要在 WPR UI 中使用自定义度量Microsoft Defender for Endpoint详细分析配置文件：

    1. 确保在 *一级会审*、 *资源分析* 和 *方案分析* 组下未选择任何配置文件。
    2. 选择 **自定义度量** 值。
    3. 选择 **Microsoft Defender for Endpoint分析**。
    4. 在 *“详细信息*”级别下选择 **详细** 信息。
    5. 在日志记录模式下选择 **“文件** ”或 **“内存** ”。

    > [!IMPORTANT]
    > 如果用户可以直接重现性能问题，则应选择 *“文件* ”以使用文件日志记录模式。 大多数问题属于此类别。 但是，如果用户无法直接重现问题，但在出现问题后可以轻松地注意到它，则用户应选择 *内存* 以使用内存日志记录模式。 这可确保跟踪日志不会由于长时间而过度膨胀。

9. 现在可以收集数据了。 退出与重现性能问题无关的所有应用程序。 可以选择 **“隐藏”选项** ，使 WPR 窗口占用的空间保持较小。

   :::image type="content" source="images/wpr-08.png" alt-text="隐藏选项" lightbox="images/wpr-08.png":::

    > [!TIP]
    > 尝试以整秒为单位启动跟踪。 例如，01：30：00。 这样可以更轻松地分析数据。 此外，请尝试跟踪问题重现的时间戳。

10. 选择“开始”。

    :::image type="content" source="images/wpr-09.png" alt-text="“记录系统信息”页" lightbox="images/wpr-09.png":::

11. 重现问题。

    > [!TIP]
    > 将数据收集保持在不超过五分钟。 两到三分钟是一个很好的范围，因为正在收集大量数据。

12. 选择“**保存**”。

    :::image type="content" source="images/wpr-10.png" alt-text="“保存”选项" lightbox="images/wpr-10.png":::

13. 填写 **问题详细说明中的类型：** 提供有关问题的信息以及如何重现问题。

    :::image type="content" source="images/wpr-12.png" alt-text="在其中填充的窗格" lightbox="images/wpr-12.png":::

    1. 选择 **文件名：** 确定跟踪文件的保存位置。 默认情况下，它将保存到 `%user%\Documents\WPR Files\`。
    1. 选择“**保存**”。

14. 在合并跟踪时等待。

    :::image type="content" source="images/wpr-13.png" alt-text="WPR 收集常规跟踪" lightbox="images/wpr-13.png":::

15. 保存跟踪后，选择 **“打开”文件夹**。

    :::image type="content" source="images/wpr-14.png" alt-text="显示已保存 WPR 跟踪的通知的页面" lightbox="images/wpr-14.png":::

    将文件和文件夹同时包含在提交Microsoft 支持部门中。

    :::image type="content" source="images/wpr-15.png" alt-text="文件和文件夹的详细信息" lightbox="images/wpr-15.png":::

### <a name="capture-performance-logs-using-the-wpr-cli"></a>使用 WPR CLI 捕获性能日志

命令行工具wpr.exe是从 *Windows 8* 开始的操作系统的一部分。 若要使用命令行工具收集 WPR 跟踪，请wpr.exe：

1. 下载 **[Microsoft Defender for Endpoint分析](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** 配置文件，以便将性能跟踪下载到本地目录中命名`MDAV.wprp`的文件，例如`C:\traces`。

2. 右键单击 **“开始菜单”** 图标，然后选择 **Windows PowerShell (“管理员)**”或 **“命令提示符” (管理员)** 打开“管理员”命令提示符窗口。

3. 出现“用户帐户控制”对话框时，选择 **“是**”。

4. 在提升的提示符下，运行以下命令以启动Microsoft Defender for Endpoint性能跟踪：

    ```console
    wpr.exe -start C:\traces\MDAV.wprp!WD.Verbose -filemode
    ```

    > [!WARNING]
    > 如果Windows服务器具有 64 GB 或 RAM 或更多，请分别使用配置文件`WDForLargeServers.Light`和`WDForLargeServers.Verbose`配置文件，`WD.Verbose`而不是配置文件`WD.Light`。 否则，系统可能会消耗大量非分页池内存或缓冲区，从而导致系统不稳定。

5. 重现问题。

    > [!TIP]
    > 将数据收集保留不超过五分钟。 根据方案，两到三分钟是一个很好的范围，因为正在收集大量数据。

6. 在提升的提示符下，运行以下命令来停止性能跟踪，确保提供有关问题的信息以及如何重现问题：

    ```console
    wpr.exe -stop merged.etl "Timestamp when the issue was reproduced, in HH:MM:SS format" "Description of the issue" "Any error that popped up"
    ```

7. 等待跟踪合并。

8. 在提交给 Microsoft 支持部门时同时包含文件和文件夹。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="see-also"></a>另请参阅

- [收集Microsoft Defender 防病毒诊断数据](collect-diagnostic-data.md)
- [配置和验证Microsoft Defender 防病毒扫描的排除项](configure-exclusions-microsoft-defender-antivirus.md)
