---
title: 如何使用适用于 macOS 的 MDATP 计划扫描
description: 了解如何在 macOS 中为 Microsoft Defender ATP 安排自动扫描时间，以更好地保护组织的资产。
keywords: microsoft， defender， atp， mac， 扫描， 防病毒
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4694ff0c0d0892b9261e61683654dfb58dfd724b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187393"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="edcb5-104">使用 Microsoft Defender for Endpoint for Mac 计划扫描</span><span class="sxs-lookup"><span data-stu-id="edcb5-104">Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="edcb5-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="edcb5-105">**Applies to:**</span></span>
- [<span data-ttu-id="edcb5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="edcb5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="edcb5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="edcb5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="edcb5-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="edcb5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="edcb5-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="edcb5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="edcb5-110">虽然你随时可以使用 Microsoft Defender for Endpoint 启动威胁扫描，但企业可能会从计划扫描或定期扫描中获益。</span><span class="sxs-lookup"><span data-stu-id="edcb5-110">While you can start a threat scan at any time with Microsoft Defender for Endpoint, your enterprise might benefit from scheduled or timed scans.</span></span> <span data-ttu-id="edcb5-111">例如，可以将扫描计划为每个工作日或每周的开始运行。</span><span class="sxs-lookup"><span data-stu-id="edcb5-111">For example, you can schedule a scan to run at the beginning of every workday or week.</span></span> 

## <a name="schedule-a-scan-with-launchd"></a><span data-ttu-id="edcb5-112">计划已启动 *的扫描*</span><span class="sxs-lookup"><span data-stu-id="edcb5-112">Schedule a scan with *launchd*</span></span>

<span data-ttu-id="edcb5-113">可以在 macOS 设备上使用启动 *的守护程序* 创建扫描计划。</span><span class="sxs-lookup"><span data-stu-id="edcb5-113">You can create a scanning schedule using the *launchd* daemon on a macOS device.</span></span>

1. <span data-ttu-id="edcb5-114">以下代码显示计划扫描所需的架构。</span><span class="sxs-lookup"><span data-stu-id="edcb5-114">The following code shows the schema you need to use to schedule a scan.</span></span> <span data-ttu-id="edcb5-115">打开文本编辑器，并使用此示例作为你自己的计划扫描文件的指南。</span><span class="sxs-lookup"><span data-stu-id="edcb5-115">Open a text editor and use this example as a guide for your own scheduled scan file.</span></span>

    <span data-ttu-id="edcb5-116">有关此处使用的 *.plist* 文件格式详细信息，请参阅官方 Apple 开发人员网站的关于 [信息属性](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) 列表文件。</span><span class="sxs-lookup"><span data-stu-id="edcb5-116">For more information on the *.plist* file format used here, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) at the official Apple developer website.</span></span>

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. <span data-ttu-id="edcb5-117">将文件另存为 *com.microsoft.wdav.schedquickscan.plist*。</span><span class="sxs-lookup"><span data-stu-id="edcb5-117">Save the file as *com.microsoft.wdav.schedquickscan.plist*.</span></span>

    > [!TIP]
    > <span data-ttu-id="edcb5-118">若要运行完全扫描而不是快速扫描，请更改第 12 行，以使用 选项而不是 (即) ，将文件另存为 `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist，* 而不是 *com.microsoft.wdav.sched **quick** scan.plist*。</span><span class="sxs-lookup"><span data-stu-id="edcb5-118">To run a full scan instead of a quick scan, change line 12, `<string>/usr/local/bin/mdatp scan quick</string>`, to use the `full` option instead of `quick` (i.e. `<string>/usr/local/bin/mdatp scan full</string>`) and save the file as *com.microsoft.wdav.sched **full** scan.plist* instead of *com.microsoft.wdav.sched **quick** scan.plist*.</span></span>

3. <span data-ttu-id="edcb5-119">打开 **终端**。</span><span class="sxs-lookup"><span data-stu-id="edcb5-119">Open **Terminal**.</span></span>
4. <span data-ttu-id="edcb5-120">输入以下命令以加载文件：</span><span class="sxs-lookup"><span data-stu-id="edcb5-120">Enter the following commands to load your file:</span></span>

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. <span data-ttu-id="edcb5-121">计划扫描将按你在 p-list 中定义的日期、时间和频率运行。</span><span class="sxs-lookup"><span data-stu-id="edcb5-121">Your scheduled scan will run at the date, time, and frequency you defined in your p-list.</span></span> <span data-ttu-id="edcb5-122">在示例中，扫描每周五的上午 2：00 运行。</span><span class="sxs-lookup"><span data-stu-id="edcb5-122">In the example, the scan runs at 2:00 AM every Friday.</span></span> 

    <span data-ttu-id="edcb5-123">`Weekday`的值 `StartCalendarInterval` 使用整数指示一周的第五天或星期五。</span><span class="sxs-lookup"><span data-stu-id="edcb5-123">The `Weekday` value of `StartCalendarInterval` uses an integer to indicate the fifth day of the week, or Friday.</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="edcb5-124">当设备处于 *运行状态时* ，通过启动执行的代理不会在计划时间运行。</span><span class="sxs-lookup"><span data-stu-id="edcb5-124">Agents executed with *launchd* will not run at the scheduled time while the device is asleep.</span></span> <span data-ttu-id="edcb5-125">它们将在设备从睡眠模式恢复后运行。</span><span class="sxs-lookup"><span data-stu-id="edcb5-125">They will instead run once the device resumes from sleep mode.</span></span>
 >
 > <span data-ttu-id="edcb5-126">如果设备已关闭，则扫描将在下一个计划扫描时间运行。</span><span class="sxs-lookup"><span data-stu-id="edcb5-126">If the device is turned off, the scan will run at the next scheduled scan time.</span></span>

## <a name="schedule-a-scan-with-intune"></a><span data-ttu-id="edcb5-127">使用 Intune 计划扫描</span><span class="sxs-lookup"><span data-stu-id="edcb5-127">Schedule a scan with Intune</span></span>

<span data-ttu-id="edcb5-128">还可使用 Microsoft Intune 计划扫描。</span><span class="sxs-lookup"><span data-stu-id="edcb5-128">You can also schedule scans with Microsoft Intune.</span></span> <span data-ttu-id="edcb5-129">当 [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) 睡眠模式恢复时， [适用于 Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) 的脚本中提供的命令行管理程序脚本将持续存在。</span><span class="sxs-lookup"><span data-stu-id="edcb5-129">The [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell script available at [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) will persist when the device resumes from sleep mode.</span></span> 

<span data-ttu-id="edcb5-130">有关如何 [在企业中使用此脚本](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) 的详细说明，请参阅在 Intune 中使用 macOS 设备的 shell 脚本。</span><span class="sxs-lookup"><span data-stu-id="edcb5-130">See [Use shell scripts on macOS devices in Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) for more detailed instructions on how to use this script in your enterprise.</span></span>
