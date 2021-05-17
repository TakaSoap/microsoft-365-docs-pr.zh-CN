---
title: 解决性能问题
description: 解决与 Microsoft Defender for Endpoint 中的实时保护服务相关的高 CPU 使用率问题。
keywords: 疑难解答， 性能， 高 CPU 使用率， 高 CPU 使用率， 错误， 修复， 更新合规性， oms， 监视器， 报告， Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: normal
manager: dansimp
ms.date: 04/14/2021
audience: ITPro
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 71c2391361c645d26cdaddff0bff86796da50391
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995077"
---
# <a name="troubleshoot-performance-issues-related-to-real-time-protection"></a><span data-ttu-id="bc767-104">解决与实时保护相关的性能问题</span><span class="sxs-lookup"><span data-stu-id="bc767-104">Troubleshoot performance issues related to real-time protection</span></span>


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bc767-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bc767-105">**Applies to:**</span></span>

- [<span data-ttu-id="bc767-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bc767-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
 
<span data-ttu-id="bc767-107">如果你的系统具有与 Microsoft Defender for Endpoint 中的实时保护服务相关的高 CPU 使用率或性能问题，你可以向 Microsoft 支持部门提交票证。</span><span class="sxs-lookup"><span data-stu-id="bc767-107">If your system is having high CPU usage or performance issues related to the real-time protection service in Microsoft Defender for Endpoint, you can submit a ticket to Microsoft support.</span></span> <span data-ttu-id="bc767-108">按照收集诊断[Microsoft Defender 防病毒中的步骤操作](collect-diagnostic-data.md)。</span><span class="sxs-lookup"><span data-stu-id="bc767-108">Follow the steps in [Collect Microsoft Defender Antivirus diagnostic data](collect-diagnostic-data.md).</span></span>

<span data-ttu-id="bc767-109">作为管理员，还可以自行解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="bc767-109">As an admin, you can also troubleshoot these issues on your own.</span></span> 

<span data-ttu-id="bc767-110">首先，您可能需要检查该问题是否由另一个软件导致。</span><span class="sxs-lookup"><span data-stu-id="bc767-110">First, you might want to check if the issue is being caused by another software.</span></span> <span data-ttu-id="bc767-111">请阅读 [与供应商核实防病毒排除项](#check-with-vendor-for-antivirus-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="bc767-111">Read [Check with vendor for antivirus exclusions](#check-with-vendor-for-antivirus-exclusions).</span></span>

<span data-ttu-id="bc767-112">否则，你可以按照分析 Microsoft 保护日志 中的步骤识别与标识的 [性能问题相关的软件](#analyze-the-microsoft-protection-log)。</span><span class="sxs-lookup"><span data-stu-id="bc767-112">Otherwise, you can identify which software is related to the identified performance issue by following the steps in [Analyze the Microsoft Protection Log](#analyze-the-microsoft-protection-log).</span></span> 

<span data-ttu-id="bc767-113">还可以按照以下步骤向 Microsoft 支持人员提供提交的其他日志：</span><span class="sxs-lookup"><span data-stu-id="bc767-113">You can also provide additional logs to your submission to Microsoft support by following the steps in:</span></span>
- [<span data-ttu-id="bc767-114">使用进程监视器捕获进程日志</span><span class="sxs-lookup"><span data-stu-id="bc767-114">Capture process logs using Process Monitor</span></span>](#capture-process-logs-using-process-monitor)
- [<span data-ttu-id="bc767-115">使用 Performance Recorder Windows性能日志</span><span class="sxs-lookup"><span data-stu-id="bc767-115">Capture performance logs using Windows Performance Recorder</span></span>](#capture-performance-logs-using-windows-performance-recorder) 

## <a name="check-with-vendor-for-antivirus-exclusions"></a><span data-ttu-id="bc767-116">与供应商核实防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="bc767-116">Check with vendor for antivirus exclusions</span></span>

<span data-ttu-id="bc767-117">如果您能够轻松识别影响系统性能的软件，请转到软件供应商的知识库或支持中心。</span><span class="sxs-lookup"><span data-stu-id="bc767-117">If you can readily identify the software affecting system performance, go to the software vendor's knowledge base or support center.</span></span> <span data-ttu-id="bc767-118">如果他们对防病毒排除项有建议，请进行搜索。</span><span class="sxs-lookup"><span data-stu-id="bc767-118">Search if they have recommendations about antivirus exclusions.</span></span> <span data-ttu-id="bc767-119">如果供应商的网站没有支持票证，可以打开支持票证，并要求他们发布一个支持票证。</span><span class="sxs-lookup"><span data-stu-id="bc767-119">If the vendor's website does not have them, you can open a support ticket with them and ask them to publish one.</span></span> 

<span data-ttu-id="bc767-120">我们建议软件供应商遵循与行业合作中的各种准则，尽量减少 [误报](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/)。</span><span class="sxs-lookup"><span data-stu-id="bc767-120">We recommend that software vendors follow the various guidelines in [Partnering with the industry to minimize false positives](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/).</span></span> <span data-ttu-id="bc767-121">供应商可以通过 MICROSOFT Defender 安全智能门户或[MDSI (提交) 。 ](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper)</span><span class="sxs-lookup"><span data-stu-id="bc767-121">The vendor can submit their software through the [Microsoft Defender Security Intelligence portal (MDSI)](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper).</span></span>


## <a name="analyze-the-microsoft-protection-log"></a><span data-ttu-id="bc767-122">分析 Microsoft 保护日志</span><span class="sxs-lookup"><span data-stu-id="bc767-122">Analyze the Microsoft Protection Log</span></span>

<span data-ttu-id="bc767-123">在 **MPLog-xxxxxxxx-xxxxxx.log** 中，可以找到以 *EstimatedImpact* 格式运行软件对性能的影响估计信息：</span><span class="sxs-lookup"><span data-stu-id="bc767-123">In **MPLog-xxxxxxxx-xxxxxx.log**, you can find the estimated performance impact information of running software as *EstimatedImpact*:</span></span>
    
`Per-process counts:ProcessImageName: smsswd.exe, TotalTime: 6597, Count: 1406, MaxTime: 609, MaxTimeFile: \Device\HarddiskVolume3\_SMSTaskSequence\Packages\WQ1008E9\Files\FramePkg.exe, EstimatedImpact: 65%`

| <span data-ttu-id="bc767-124">字段名</span><span class="sxs-lookup"><span data-stu-id="bc767-124">Field name</span></span> | <span data-ttu-id="bc767-125">说明</span><span class="sxs-lookup"><span data-stu-id="bc767-125">Description</span></span> |
|---|---|
|<span data-ttu-id="bc767-126">ProcessImageName</span><span class="sxs-lookup"><span data-stu-id="bc767-126">ProcessImageName</span></span> | <span data-ttu-id="bc767-127">进程映像名称</span><span class="sxs-lookup"><span data-stu-id="bc767-127">Process image name</span></span> |
| <span data-ttu-id="bc767-128">TotalTime</span><span class="sxs-lookup"><span data-stu-id="bc767-128">TotalTime</span></span> | <span data-ttu-id="bc767-129">扫描此过程访问的文件所用的累积持续时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="bc767-129">The cumulative duration in milliseconds spent in scans of files accessed by this process</span></span> |
|<span data-ttu-id="bc767-130">计数</span><span class="sxs-lookup"><span data-stu-id="bc767-130">Count</span></span> | <span data-ttu-id="bc767-131">此过程访问的已扫描文件数</span><span class="sxs-lookup"><span data-stu-id="bc767-131">The number of scanned files accessed by this process</span></span> |
|<span data-ttu-id="bc767-132">MaxTime</span><span class="sxs-lookup"><span data-stu-id="bc767-132">MaxTime</span></span> |  <span data-ttu-id="bc767-133">此过程访问的文件的最长单次扫描持续时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="bc767-133">The duration in milliseconds in the longest single scan of a file accessed by this process</span></span> |
| <span data-ttu-id="bc767-134">MaxTimeFile</span><span class="sxs-lookup"><span data-stu-id="bc767-134">MaxTimeFile</span></span> | <span data-ttu-id="bc767-135">此进程访问的文件的路径，其中记录了持续时间最长的 `MaxTime` 扫描</span><span class="sxs-lookup"><span data-stu-id="bc767-135">The path of the file accessed by this process for which the longest scan of `MaxTime` duration was recorded</span></span> |
| <span data-ttu-id="bc767-136">EstimatedImpact</span><span class="sxs-lookup"><span data-stu-id="bc767-136">EstimatedImpact</span></span> | <span data-ttu-id="bc767-137">在此过程遇到扫描活动的时间段外，扫描此过程访问的文件所花费的时间百分比</span><span class="sxs-lookup"><span data-stu-id="bc767-137">The percentage of time spent in scans for files accessed by this process out of the period in which this process experienced scan activity</span></span> |

<span data-ttu-id="bc767-138">如果性能影响很大，请尝试按照配置并验证进程扫描的排除项中的步骤将进程添加到路径[/Microsoft Defender 防病毒排除项](collect-diagnostic-data.md)。</span><span class="sxs-lookup"><span data-stu-id="bc767-138">If the performance impact is high, try adding the process to the Path/Process exclusions by following the steps in [Configure and validate exclusions for Microsoft Defender Antivirus scans](collect-diagnostic-data.md).</span></span>

<span data-ttu-id="bc767-139">如果上一步不能解决问题，可以通过以下部分中的进程监视器或Windows[记录器](#capture-performance-logs-using-windows-performance-recorder)来收集[](#capture-process-logs-using-process-monitor)更多信息。</span><span class="sxs-lookup"><span data-stu-id="bc767-139">If the previous step doesn't solve the problem, you can collect more information through the [Process Monitor](#capture-process-logs-using-process-monitor) or the [Windows Performance Recorder](#capture-performance-logs-using-windows-performance-recorder) in the following sections.</span></span>
     
## <a name="capture-process-logs-using-process-monitor"></a><span data-ttu-id="bc767-140">使用进程监视器捕获进程日志</span><span class="sxs-lookup"><span data-stu-id="bc767-140">Capture process logs using Process Monitor</span></span>

<span data-ttu-id="bc767-141">Process Monitor (ProcMon) 是一种高级监视工具，可显示实时进程。</span><span class="sxs-lookup"><span data-stu-id="bc767-141">Process Monitor (ProcMon) is an advanced monitoring tool that can show real-time processes.</span></span> <span data-ttu-id="bc767-142">您可以使用它来捕获性能问题发生时。</span><span class="sxs-lookup"><span data-stu-id="bc767-142">You can use this to capture the performance issue as it is occurring.</span></span>

1. <span data-ttu-id="bc767-143">将 [进程监视器 v3.60](/sysinternals/downloads/procmon) 下载到类似 的文件夹 `C:\temp` 。</span><span class="sxs-lookup"><span data-stu-id="bc767-143">Download [Process Monitor v3.60](/sysinternals/downloads/procmon) to a folder like `C:\temp`.</span></span>

2. <span data-ttu-id="bc767-144">若要删除文件的 Web 标记，请进行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bc767-144">To remove the file's mark of the web:</span></span>
    1. <span data-ttu-id="bc767-145">右键单击 **"ProcessMonitor.zip** 并选择"属性 **"。**</span><span class="sxs-lookup"><span data-stu-id="bc767-145">Right-click **ProcessMonitor.zip** and select **Properties**.</span></span>
    1. <span data-ttu-id="bc767-146">在"*常规"选项卡* 下，查找"安全性 *"。*</span><span class="sxs-lookup"><span data-stu-id="bc767-146">Under the *General* tab, look for *Security*.</span></span>
    1. <span data-ttu-id="bc767-147">选中"取消阻止 **"旁边的框**。</span><span class="sxs-lookup"><span data-stu-id="bc767-147">Check the box beside **Unblock**.</span></span>
    1. <span data-ttu-id="bc767-148">选择 **应用**。</span><span class="sxs-lookup"><span data-stu-id="bc767-148">Select **Apply**.</span></span>
    
    ![删除 MOTW](images/procmon-motw.png) 

3. <span data-ttu-id="bc767-150">在 中解压缩文件 `C:\temp` ，使文件夹路径为 `C:\temp\ProcessMonitor` 。</span><span class="sxs-lookup"><span data-stu-id="bc767-150">Unzip the file in `C:\temp` so that the folder path will be `C:\temp\ProcessMonitor`.</span></span> 

4. <span data-ttu-id="bc767-151">将 **ProcMon.exe** 复制到Windows故障排除Windows客户端或服务器。</span><span class="sxs-lookup"><span data-stu-id="bc767-151">Copy **ProcMon.exe**  to the Windows client or Windows server you're troubleshooting.</span></span>  

5. <span data-ttu-id="bc767-152">在运行 ProcMon 之前，请确保已关闭与 CPU 使用率高问题不相关的所有其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="bc767-152">Before running ProcMon, make sure all other applications not related to the high CPU usage issue are closed.</span></span> <span data-ttu-id="bc767-153">执行此操作将最大程度地减少要检查的进程数。</span><span class="sxs-lookup"><span data-stu-id="bc767-153">Doing this will minimize the number of processes to check.</span></span>

6. <span data-ttu-id="bc767-154">可以通过两种方式启动 ProcMon。</span><span class="sxs-lookup"><span data-stu-id="bc767-154">You can launch ProcMon in two ways.</span></span>
    1. <span data-ttu-id="bc767-155">右键单击 **"ProcMon.exe** 并选择"**以管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="bc767-155">Right-click **ProcMon.exe** and select **Run as administrator**.</span></span> 
    

        <span data-ttu-id="bc767-156">由于日志记录会自动启动，请选择放大镜图标以停止当前捕获或使用键盘快捷方式 **Ctrl+E。**</span><span class="sxs-lookup"><span data-stu-id="bc767-156">Since logging starts automatically, select the magnifying glass icon  to stop the current capture or use the keyboard shortcut **Ctrl+E**.</span></span>
 
        ![放大镜图标](images/procmon-magglass.png)

        <span data-ttu-id="bc767-158">若要验证是否已停止捕获，请检查放大镜图标现在是否显示红色 X。</span><span class="sxs-lookup"><span data-stu-id="bc767-158">To verify that you have stopped the capture, check if the magnifying glass icon now appears with a red X.</span></span>

        ![红色斜杠](images/procmon-magglass-stop.png)         

        <span data-ttu-id="bc767-160">接下来，若要清除之前捕获，请选择橡皮擦图标。</span><span class="sxs-lookup"><span data-stu-id="bc767-160">Next, to clear the earlier capture, select the eraser icon.</span></span>

        ![清除图标](images/procmon-eraser-clear.png)

        <span data-ttu-id="bc767-162">或使用键盘快捷方式 **Ctrl+X。**</span><span class="sxs-lookup"><span data-stu-id="bc767-162">Or use the keyboard shortcut **Ctrl+X**.</span></span>

    2. <span data-ttu-id="bc767-163">第二种方式是以管理员角色 **运行命令行** ，然后从进程监视器路径运行：</span><span class="sxs-lookup"><span data-stu-id="bc767-163">The second way is to run the **command line** as admin, then from the Process Monitor path, run:</span></span>

        ![cmd procmon](images/cmd-procmon.png)
 
        ```console
        Procmon.exe /AcceptEula /Noconnect /Profiling
        ```
        
        >[!TIP] 
        ><span data-ttu-id="bc767-165">在捕获数据时使 ProcMon 窗口尽可能小，以便轻松启动和停止跟踪。</span><span class="sxs-lookup"><span data-stu-id="bc767-165">Make the ProcMon window as small as possible when capturing data so you can easily start and stop the trace.</span></span>
        > 
        >![最小化 Procmon](images/procmon-minimize.png)
    
7. <span data-ttu-id="bc767-167">执行步骤 6 中的其中一个过程后，你将看到设置筛选器的选项。</span><span class="sxs-lookup"><span data-stu-id="bc767-167">After following one of the procedures in step 6, you'll next see an option to set filters.</span></span> <span data-ttu-id="bc767-168">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="bc767-168">Select **OK**.</span></span> <span data-ttu-id="bc767-169">捕获完成后，你始终可以筛选结果。</span><span class="sxs-lookup"><span data-stu-id="bc767-169">You can always filter the results after the capture is completed.</span></span>
 
    ![筛选出进程名称为系统排除](images/procmon-filter-options.png) 

8. <span data-ttu-id="bc767-171">若要启动捕获，请再次选择放大镜图标。</span><span class="sxs-lookup"><span data-stu-id="bc767-171">To start the capture, select the magnifying glass icon again.</span></span>
     
9. <span data-ttu-id="bc767-172">重现问题。</span><span class="sxs-lookup"><span data-stu-id="bc767-172">Reproduce the problem.</span></span>
 
    >[!TIP] 
    ><span data-ttu-id="bc767-173">等待问题完全重现，然后记下开始跟踪的时间戳。</span><span class="sxs-lookup"><span data-stu-id="bc767-173">Wait for the problem to be fully reproduced, then take note of the timestamp when the trace started.</span></span>

10. <span data-ttu-id="bc767-174">在高 CPU 使用率条件期间具有两到四分钟的进程活动后，通过选择放大镜图标停止捕获。</span><span class="sxs-lookup"><span data-stu-id="bc767-174">Once you have two to four minutes of process activity during the high CPU usage condition, stop the capture by selecting the magnifying glass icon.</span></span>

11. <span data-ttu-id="bc767-175">若要使用唯一的名称和 .pml 格式保存捕获，请选择" **文件** "，然后选择"保存 **..."。** 确保选择单选按钮 所有 **事件** 和本机进程监视器格式 **(PML)**。</span><span class="sxs-lookup"><span data-stu-id="bc767-175">To save the capture with a unique name and with the .pml format, select **File** then select **Save...**. Make sure to select the radio buttons **All events** and **Native Process Monitor Format (PML)**.</span></span>

    ![保存设置](images/procmon-savesettings1.png)

12. <span data-ttu-id="bc767-177">为了更好地进行跟踪，将默认路径从 `C:\temp\ProcessMonitor\LogFile.PML` 以下 `C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML` 位置更改为：</span><span class="sxs-lookup"><span data-stu-id="bc767-177">For better tracking, change the default path from `C:\temp\ProcessMonitor\LogFile.PML` to `C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML` where:</span></span>
    - <span data-ttu-id="bc767-178">`%ComputerName%` 是设备名称</span><span class="sxs-lookup"><span data-stu-id="bc767-178">`%ComputerName%` is the device name</span></span>
    - <span data-ttu-id="bc767-179">`MMDDYEAR` 是月、日、年</span><span class="sxs-lookup"><span data-stu-id="bc767-179">`MMDDYEAR` is the month, day, and year</span></span>
    -  <span data-ttu-id="bc767-180">`Repro_of_issue` 是你要尝试重现的问题的名称</span><span class="sxs-lookup"><span data-stu-id="bc767-180">`Repro_of_issue` is the name of the issue you're trying to reproduce</span></span>

    >[!TIP] 
    > <span data-ttu-id="bc767-181">如果您有一个工作系统，您可能需要获取一个示例日志进行比较。</span><span class="sxs-lookup"><span data-stu-id="bc767-181">If you have a working system, you might want to get a sample log to compare.</span></span>

13. <span data-ttu-id="bc767-182">压缩 .pml 文件，并提交到 Microsoft 支持。</span><span class="sxs-lookup"><span data-stu-id="bc767-182">Zip the .pml file and submit it to Microsoft support.</span></span>


## <a name="capture-performance-logs-using-windows-performance-recorder"></a><span data-ttu-id="bc767-183">使用 Performance Recorder Windows性能日志</span><span class="sxs-lookup"><span data-stu-id="bc767-183">Capture performance logs using Windows Performance Recorder</span></span>

<span data-ttu-id="bc767-184">可以使用 WPR Windows记录器 (WPR) 向 Microsoft 支持人员提交其他信息。</span><span class="sxs-lookup"><span data-stu-id="bc767-184">You can use Windows Performance Recorder (WPR) to include additional information in your submission to Microsoft support.</span></span> <span data-ttu-id="bc767-185">WPR 是一款功能强大的录制工具，可创建记录Windows跟踪。</span><span class="sxs-lookup"><span data-stu-id="bc767-185">WPR is a powerful recording tool that creates Event Tracing for Windows recordings.</span></span> 

<span data-ttu-id="bc767-186">WPR 是 Windows Assessment and Deployment Kit (Windows ADK) 的一部分，可以从下载并安装 Windows [ADK 下载](/windows-hardware/get-started/adk-install)。</span><span class="sxs-lookup"><span data-stu-id="bc767-186">WPR is part of the Windows Assessment and Deployment Kit (Windows ADK) and can be downloaded from [Download and install the Windows ADK](/windows-hardware/get-started/adk-install).</span></span> <span data-ttu-id="bc767-187">也可以下载它作为 Windows 10 SDK 中 Windows 10 软件开发[工具包的一部分](https://developer.microsoft.com/windows/downloads/windows-10-sdk/)。</span><span class="sxs-lookup"><span data-stu-id="bc767-187">You can also download it as part of the Windows 10 Software Development Kit at [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk/).</span></span>

<span data-ttu-id="bc767-188">可以按照使用 WPR UI 捕获性能日志中的步骤使用 [WPR 用户界面](#capture-performance-logs-using-the-wpr-ui)。</span><span class="sxs-lookup"><span data-stu-id="bc767-188">You can use the WPR user interface by following the steps in [Capture performance logs using the WPR UI](#capture-performance-logs-using-the-wpr-ui).</span></span> 

<span data-ttu-id="bc767-189">或者，也可以按照使用 [WPR CLI](#capture-performance-logs-using-the-wpr-cli)捕获性能日志中的步骤，使用 Windows 8 及更高版本中提供的命令行工具 *wpr.exe*。</span><span class="sxs-lookup"><span data-stu-id="bc767-189">Alternatively, you can also use the command-line tool *wpr.exe*, which is available in Windows 8 and later versions  by following the steps in [Capture performance logs using the WPR CLI](#capture-performance-logs-using-the-wpr-cli).</span></span>


### <a name="capture-performance-logs-using-the-wpr-ui"></a><span data-ttu-id="bc767-190">使用 WPR UI 捕获性能日志</span><span class="sxs-lookup"><span data-stu-id="bc767-190">Capture performance logs using the WPR UI</span></span>

>[!TIP]
><span data-ttu-id="bc767-191">如果有多个设备发生问题，请使用 RAM 量最多的设备。</span><span class="sxs-lookup"><span data-stu-id="bc767-191">If you have multiple devices where the issue is occurring, use the one which has the most amount of RAM.</span></span>

1. <span data-ttu-id="bc767-192">下载并安装 WPR。</span><span class="sxs-lookup"><span data-stu-id="bc767-192">Download and install WPR.</span></span>

2. <span data-ttu-id="bc767-193">在 *Windows工具包"* 下，右键单击Windows **录制器"。**</span><span class="sxs-lookup"><span data-stu-id="bc767-193">Under *Windows Kits*, right-click **Windows Performance Recorder**.</span></span> 

    ![“开始”菜单](images/wpr-01.png)

    <span data-ttu-id="bc767-195">选择 **"更多"。**</span><span class="sxs-lookup"><span data-stu-id="bc767-195">Select **More**.</span></span> <span data-ttu-id="bc767-196">选择 **"以管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="bc767-196">Select **Run as administrator**.</span></span>

3. <span data-ttu-id="bc767-197">当出现"用户帐户控制"对话框时，选择"**是"。**</span><span class="sxs-lookup"><span data-stu-id="bc767-197">When the User Account Control dialog box appears, select **Yes**.</span></span>

    ![UAC](images/wpt-yes.png)

4. <span data-ttu-id="bc767-199">接下来，下载 [Microsoft Defender for Endpoint 分析](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp) 配置文件，并另存为 `WD.wprp` 文件夹，如 `C:\temp` 。</span><span class="sxs-lookup"><span data-stu-id="bc767-199">Next, download the [Microsoft Defender for Endpoint analysis](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp) profile and save as `WD.wprp` to a folder like `C:\temp`.</span></span> 
     
5. <span data-ttu-id="bc767-200">在"WPR"对话框中，选择"**更多选项"。**</span><span class="sxs-lookup"><span data-stu-id="bc767-200">On the WPR dialog box, select **More options**.</span></span>

    ![选择更多选项](images/wpr-03.png)

6. <span data-ttu-id="bc767-202">选择 **"添加配置文件..."，** 然后浏览到文件 `WD.wprp` 的路径。</span><span class="sxs-lookup"><span data-stu-id="bc767-202">Select **Add Profiles...** and browse to the path of the `WD.wprp` file.</span></span>

7. <span data-ttu-id="bc767-203">此后，你应该会看到"自定义度量"下的 *"Microsoft Defender 终结点分析*"下的新配置文件集。</span><span class="sxs-lookup"><span data-stu-id="bc767-203">After that, you should see a new profile set under *Custom measurements* named *Microsoft Defender for Endpoint analysis* underneath it.</span></span>

    ![in-file](images/wpr-infile.png)

    >[!WARNING]
    ><span data-ttu-id="bc767-205">如果你的 Windows Server 具有 64 GB 或更多的 RAM，请使用自定义度量 `Microsoft Defender for Endpoint analysis for large servers` ，而不是 `Microsoft Defender for Endpoint analysis` 。</span><span class="sxs-lookup"><span data-stu-id="bc767-205">If your Windows Server has 64 GB of RAM or more, use the custom measurement `Microsoft Defender for Endpoint analysis for large servers` instead of `Microsoft Defender for Endpoint analysis`.</span></span> <span data-ttu-id="bc767-206">否则，你的系统可能会占用大量未分页的池内存或缓冲区，这可能会导致系统不稳定。</span><span class="sxs-lookup"><span data-stu-id="bc767-206">Otherwise, your system could consume a high amount of non-paged pool memory or buffers which can lead to system instability.</span></span> <span data-ttu-id="bc767-207">您可以通过展开"资源分析"选择要 **添加的配置文件**。</span><span class="sxs-lookup"><span data-stu-id="bc767-207">You can choose which profiles to add by expanding **Resource Analysis**.</span></span> <span data-ttu-id="bc767-208">此自定义配置文件提供深入性能分析的必要上下文。</span><span class="sxs-lookup"><span data-stu-id="bc767-208">This custom profile provides the necessary context for in-depth performance analysis.</span></span>
 
8. <span data-ttu-id="bc767-209">若要在 WPR UI 中使用自定义度量 Microsoft Defender for Endpoint 详细分析配置文件：</span><span class="sxs-lookup"><span data-stu-id="bc767-209">To use the custom measurement Microsoft Defender for Endpoint verbose analysis profile in the WPR UI:</span></span>

    1. <span data-ttu-id="bc767-210">确保未在一级会审、资源分析和方案分析组 *下选择任何* 配置文件。</span><span class="sxs-lookup"><span data-stu-id="bc767-210">Ensure no profiles are selected under the *First-level triage*, *Resource Analysis* and *Scenario Analysis* groups.</span></span>
    2. <span data-ttu-id="bc767-211">选择 **"自定义度量"。**</span><span class="sxs-lookup"><span data-stu-id="bc767-211">Select **Custom measurements**.</span></span>
    3. <span data-ttu-id="bc767-212">选择 **Microsoft Defender 进行终结点分析**。</span><span class="sxs-lookup"><span data-stu-id="bc767-212">Select **Microsoft Defender for Endpoint analysis**.</span></span>
    4. <span data-ttu-id="bc767-213">在 \**"详细信息级别\*\*\*"下选择"详细*"。</span><span class="sxs-lookup"><span data-stu-id="bc767-213">Select **Verbose** under *Detail* level.</span></span>
    1. <span data-ttu-id="bc767-214">在 **"日志记录\*\*\*\*"模式下选择**"文件或内存"。</span><span class="sxs-lookup"><span data-stu-id="bc767-214">Select **File** or **Memory** under Logging mode.</span></span> 

    >[!important]
    ><span data-ttu-id="bc767-215">如果用户可以直接 *重现* 性能问题，则应该选择"文件"以使用文件日志记录模式。</span><span class="sxs-lookup"><span data-stu-id="bc767-215">You should select *File* to use the file logging mode if the performance issue can be reproduced directly by the user.</span></span> <span data-ttu-id="bc767-216">大多数问题属于此类别。</span><span class="sxs-lookup"><span data-stu-id="bc767-216">Most issues fall under this category.</span></span> <span data-ttu-id="bc767-217">但是，如果用户无法直接重现问题，但在出现问题后很容易注意到该问题，则用户应选择"内存"以使用内存日志记录模式。</span><span class="sxs-lookup"><span data-stu-id="bc767-217">However, if the user cannot directly reproduce the issue but can easily notice it once the issue occurs, the user should select *Memory* to use the memory logging mode.</span></span> <span data-ttu-id="bc767-218">这可确保跟踪日志不会由于长时间运行而过度增长。</span><span class="sxs-lookup"><span data-stu-id="bc767-218">This ensures that the trace log will not inflate excessively due to the long run time.</span></span>

9. <span data-ttu-id="bc767-219">现在，你已准备好收集数据。</span><span class="sxs-lookup"><span data-stu-id="bc767-219">Now you're ready to collect data.</span></span> <span data-ttu-id="bc767-220">退出与重现性能问题不相关的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="bc767-220">Exit all the applications that are not relevant to reproducing the performance issue.</span></span> <span data-ttu-id="bc767-221">可以选择隐藏 **选项** ，使 WPR 窗口所占用的空间保持较小。</span><span class="sxs-lookup"><span data-stu-id="bc767-221">You can select **Hide options** to keep the space occupied by the WPR window small.</span></span>

    ![Hipe 选项](images/wpr-08.png)

    >[!TIP]
    ><span data-ttu-id="bc767-223">尝试以完整的秒数开始跟踪。</span><span class="sxs-lookup"><span data-stu-id="bc767-223">Try starting the trace at whole number seconds.</span></span> <span data-ttu-id="bc767-224">例如，01：30：00。</span><span class="sxs-lookup"><span data-stu-id="bc767-224">For instance, 01:30:00.</span></span> <span data-ttu-id="bc767-225">这样更易于分析数据。</span><span class="sxs-lookup"><span data-stu-id="bc767-225">This will make it easier to analyze the data.</span></span> <span data-ttu-id="bc767-226">此外，尝试跟踪重现问题的精确时间戳。</span><span class="sxs-lookup"><span data-stu-id="bc767-226">Also try to keep track of the timestamp of exactly when the issue is reproduced.</span></span>

10. <span data-ttu-id="bc767-227">选择“开始”。</span><span class="sxs-lookup"><span data-stu-id="bc767-227">Select **Start**.</span></span>

    ![选择跟踪的开始](images/wpr-09.png)

11. <span data-ttu-id="bc767-229">重现问题。</span><span class="sxs-lookup"><span data-stu-id="bc767-229">Reproduce the issue.</span></span>

    >[!TIP]
    ><span data-ttu-id="bc767-230">使数据收集不超过五分钟。</span><span class="sxs-lookup"><span data-stu-id="bc767-230">Keep the data collection to no more than five minutes.</span></span> <span data-ttu-id="bc767-231">2 到 3 分钟是一个很好的范围，因为正在收集大量的数据。</span><span class="sxs-lookup"><span data-stu-id="bc767-231">Two to three minutes is a good range since a lot of data is being collected.</span></span>

12. <span data-ttu-id="bc767-232">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="bc767-232">Select **Save**.</span></span>

    ![选择"保存"](images/wpr-10.png)

13. <span data-ttu-id="bc767-234">填写 **问题的详细描述类型** ：包含问题相关信息以及问题重现方法。</span><span class="sxs-lookup"><span data-stu-id="bc767-234">Fill up **Type in a detailed description of the problem:** with information about the problem and how you reproduced the issue.</span></span>

    ![填写详细信息](images/wpr-12.png)

    1. <span data-ttu-id="bc767-236">选择 **"文件名："** 以确定跟踪文件的保存位置。</span><span class="sxs-lookup"><span data-stu-id="bc767-236">Select **File Name:** to determine where your trace file will be saved.</span></span> <span data-ttu-id="bc767-237">默认情况下，它 1.is 另存为 `%user%\Documents\WPR Files\` 。</span><span class="sxs-lookup"><span data-stu-id="bc767-237">By default, it 1.is saved to `%user%\Documents\WPR Files\`.</span></span>
    1. <span data-ttu-id="bc767-238">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="bc767-238">Select **Save**.</span></span>

14. <span data-ttu-id="bc767-239">在合并跟踪时等待。</span><span class="sxs-lookup"><span data-stu-id="bc767-239">Wait while the trace is being merged.</span></span>

    ![WPR 收集常规跟踪](images/wpr-13.png)

15. <span data-ttu-id="bc767-241">保存跟踪后，选择"打开 **文件夹"。**</span><span class="sxs-lookup"><span data-stu-id="bc767-241">Once the trace is saved, select **Open folder**.</span></span>

    ![已保存 WPR 跟踪](images/wpr-14.png)

    <span data-ttu-id="bc767-243">在提交到 Microsoft 支持人员时，同时包括 文件和 文件夹。</span><span class="sxs-lookup"><span data-stu-id="bc767-243">Include both the file and the folder in your submission to Microsoft support.</span></span>

    ![文件和文件夹](images/wpr-15.png)

### <a name="capture-performance-logs-using-the-wpr-cli"></a><span data-ttu-id="bc767-245">使用 WPR CLI 捕获性能日志</span><span class="sxs-lookup"><span data-stu-id="bc767-245">Capture performance logs using the WPR CLI</span></span>

<span data-ttu-id="bc767-246">命令行工具 *wpr.exe* 操作系统的一部分，从 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="bc767-246">The command-line tool *wpr.exe* is part of the operating system starting with Windows 8.</span></span> <span data-ttu-id="bc767-247">若要使用命令行工具收集 WPR 跟踪，wpr.exe：</span><span class="sxs-lookup"><span data-stu-id="bc767-247">To collect a WPR trace using the command-line tool wpr.exe:</span></span>

1. <span data-ttu-id="bc767-248">将 **[Microsoft Defender for Endpoint 分析](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** 配置文件的性能跟踪下载到本地目录中名为 的文件，例如 `WD.wprp` `C:\traces` 。</span><span class="sxs-lookup"><span data-stu-id="bc767-248">Download **[Microsoft Defender for Endpoint analysis](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** profile for performance traces to a file named `WD.wprp` in a local directory such as `C:\traces`.</span></span>

3. <span data-ttu-id="bc767-249">右键单击"**开始"** 菜单图标，然后选择"Windows PowerShell (**管理员**) 或命令提示符 **(") "** 管理员"命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="bc767-249">Right-click the **Start Menu** icon and select **Windows PowerShell (Admin)** or **Command Prompt (Admin)** to open an Admin command prompt window.</span></span>

4. <span data-ttu-id="bc767-250">当出现"用户帐户控制"对话框时，选择"**是"。**</span><span class="sxs-lookup"><span data-stu-id="bc767-250">When the User Account Control dialog box appears, select **Yes**.</span></span>

5. <span data-ttu-id="bc767-251">在提升的提示符下，运行以下命令以启动 Microsoft Defender for Endpoint 性能跟踪：</span><span class="sxs-lookup"><span data-stu-id="bc767-251">At the elevated prompt, run the following command to start a Microsoft Defender for Endpoint performance trace:</span></span>

    ```console
    wpr.exe -start C:\traces\WD.wprp!WD.Verbose -filemode
    ```
    
    >[!WARNING]
    ><span data-ttu-id="bc767-252">如果您的 Windows 服务器具有 64 GB 或 RAM 或更多，请分别使用配置文件， `WDForLargeServers.Light` `WDForLargeServers.Verbose` 而不是配置文件和 `WD.Light` `WD.Verbose` 。</span><span class="sxs-lookup"><span data-stu-id="bc767-252">If your Windows Server has 64 GB or RAM or more, use profiles `WDForLargeServers.Light` and `WDForLargeServers.Verbose` instead of profiles `WD.Light` and `WD.Verbose`, respectively.</span></span> <span data-ttu-id="bc767-253">否则，你的系统可能会占用大量未分页的池内存或缓冲区，这可能会导致系统不稳定。</span><span class="sxs-lookup"><span data-stu-id="bc767-253">Otherwise, your system could consume a high amount of non-paged pool memory or buffers which can lead to system instability.</span></span>

6. <span data-ttu-id="bc767-254">重现问题。</span><span class="sxs-lookup"><span data-stu-id="bc767-254">Reproduce the issue.</span></span>

    >[!TIP]
    ><span data-ttu-id="bc767-255">保持数据收集不超过五分钟。</span><span class="sxs-lookup"><span data-stu-id="bc767-255">Keep the data collection no to more than five minutes.</span></span>  <span data-ttu-id="bc767-256">根据具体方案，2 到 3 分钟是一个很好的范围，因为正在收集大量的数据。</span><span class="sxs-lookup"><span data-stu-id="bc767-256">Depending on the scenario, two to three minutes is a good range since a lot of data is being collected.</span></span>

7. <span data-ttu-id="bc767-257">在提升的提示符下，运行以下命令以停止性能跟踪，确保提供有关问题以及如何重现问题的信息：</span><span class="sxs-lookup"><span data-stu-id="bc767-257">At the elevated prompt, run the following command to stop the performance trace, making sure to provide information about the problem and how you reproduced the issue:</span></span>

    ```console
    wpr.exe -stop merged.etl "Timestamp when the issue was reproduced, in HH:MM:SS format" "Description of the issue" "Any error that popped up"
    ```

8. <span data-ttu-id="bc767-258">等待跟踪合并。</span><span class="sxs-lookup"><span data-stu-id="bc767-258">Wait until the trace is merged.</span></span> 

9. <span data-ttu-id="bc767-259">在提交到 Microsoft 支持人员时，同时包括 文件和 文件夹。</span><span class="sxs-lookup"><span data-stu-id="bc767-259">Include both the file and the folder in your submission to Microsoft support.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc767-260">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc767-260">See also</span></span>

- [<span data-ttu-id="bc767-261">收集Microsoft Defender 防病毒诊断数据</span><span class="sxs-lookup"><span data-stu-id="bc767-261">Collect Microsoft Defender Antivirus diagnostic data</span></span>](collect-diagnostic-data.md)
- [<span data-ttu-id="bc767-262">配置并验证扫描的Microsoft Defender 防病毒项</span><span class="sxs-lookup"><span data-stu-id="bc767-262">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
