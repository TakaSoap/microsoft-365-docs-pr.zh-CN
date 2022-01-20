---
title: 如何使用 macOS 上的 Microsoft Defender for Endpoint 计划扫描
description: 了解如何在 macOS 中为 Microsoft Defender for Endpoint 安排自动扫描时间，以更好地保护组织的资产。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 扫描， 防病毒
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5621ce43443a3e620ef0166c4b362e9dc04becae
ms.sourcegitcommit: cde34d38bdfb6335b980f1c48c6b218da6a64bf8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2022
ms.locfileid: "62156324"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>在 macOS 上使用 Microsoft Defender for Endpoint 计划扫描

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

虽然你随时可以使用 Microsoft Defender for Endpoint 启动威胁扫描，但企业可能会从计划扫描或定期扫描中获益。 例如，可以将扫描计划为每个工作日或每周的开始运行。 

## <a name="schedule-a-scan-with-launchd"></a>计划已启动 *的扫描*

可以在 macOS 设备上使用启动 *的守护程序* 创建扫描计划。

有关此处使用的 *.plist* 文件格式详细信息，请参阅官方 Apple 开发人员网站的关于信息 [属性](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) 列表文件。

### <a name="schedule-a-quick-scan"></a>计划快速扫描

以下代码显示了计划快速扫描所需的架构。 

1. 打开文本编辑器，并使用此示例作为你自己的计划扫描文件的指南。

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

2. 将文件另存为 *com.microsoft.wdav.schedquickscan.plist*。

### <a name="schedule-a-full-scan"></a>计划完全扫描

1. 打开文本编辑器，并使用此示例进行完整扫描。

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedfullscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan full</string>
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
            <integer>50</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. 将文件另存为 *com.microsoft.wdav.schedfullscan.plist*。
 
### <a name="load-your-file"></a>加载文件

1. 打开 **终端**。
2. 输入以下命令以加载文件：

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

3. 计划扫描将按你在 p-list 中定义的日期、时间和频率运行。 在之前的示例中，扫描每周五的上午 2：50 运行。 

    - `Weekday`的值 `StartCalendarInterval` 使用整数指示一周的第五天或星期五。 范围介于 0 到 7 之间，7 表示星期日。
    - `Day`的值 `StartCalendarInterval` 使用整数来指示月的第三天。 范围介于 1 和 31 之间。
    - `Hour`的值 `StartCalendarInterval` 使用整数来指示一天的第二小时。 范围介于 0 到 24 之间。
    `Minute`的值 `StartCalendarInterval` 使用整数指示一小时中的 50 分钟。 范围介于 0 和 59 之间。
    
    
 > [!IMPORTANT]
 > 当设备处于 *运行状态时* ，通过启动执行的代理不会在计划时间运行。 它们将在设备从睡眠模式恢复后运行。
 >
 > 如果设备已关闭，则扫描将在下一个计划扫描时间运行。

## <a name="schedule-a-scan-with-intune"></a>使用 Intune 计划扫描

还可以计划使用扫描Microsoft Intune。 当 [设备 runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) 睡眠模式时， [适用于 Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) 的脚本中提供的命令行管理程序脚本将持续存在。 

有关如何 [在企业中使用此脚本](/mem/intune/apps/macos-shell-scripts) 的详细说明，请参阅在 Intune 中使用 macOS 设备的 shell 脚本。
