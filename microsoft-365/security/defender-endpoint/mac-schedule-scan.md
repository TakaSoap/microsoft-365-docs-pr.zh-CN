---
title: 如何使用 macOS 上的 Microsoft Defender for Endpoint 计划扫描
description: 了解如何在 macOS 中为 Microsoft Defender for Endpoint 安排自动扫描时间，以更好地保护组织的资产。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 扫描， 防病毒
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
ms.openlocfilehash: 2c1dc16dc3fbb61a77e1d7348d47fdfd778c56e2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934509"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>在 macOS 上使用 Microsoft Defender for Endpoint 计划扫描

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

虽然你随时可以使用 Microsoft Defender for Endpoint 启动威胁扫描，但企业可能会从计划扫描或定期扫描中获益。 例如，可以将扫描计划为每个工作日或每周的开始运行。 

## <a name="schedule-a-scan-with-launchd"></a>计划已启动 *的扫描*

可以在 macOS 设备上使用启动 *的守护程序* 创建扫描计划。

1. 以下代码显示计划扫描所需的架构。 打开文本编辑器，并使用此示例作为你自己的计划扫描文件的指南。

    有关此处使用的 *.plist* 文件格式详细信息，请参阅官方 Apple 开发人员网站的关于 [信息属性](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) 列表文件。

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

    > [!TIP]
    > 若要运行完全扫描而不是快速扫描，请更改第 12 行，以使用 选项而不是 (即) ，将文件另存为 `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist，* 而不是 *com.microsoft.wdav.sched **quick** scan.plist*。

3. 打开 **终端**。
4. 输入以下命令以加载文件：

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. 计划扫描将按你在 p-list 中定义的日期、时间和频率运行。 在示例中，扫描每周五的上午 2：00 运行。 

    `Weekday`的值 `StartCalendarInterval` 使用整数指示一周的第五天或星期五。

 > [!IMPORTANT]
 > 当设备处于 *运行状态时* ，通过启动执行的代理不会在计划时间运行。 它们将在设备从睡眠模式恢复后运行。
 >
 > 如果设备已关闭，则扫描将在下一个计划扫描时间运行。

## <a name="schedule-a-scan-with-intune"></a>使用 Intune 计划扫描

还可使用 Microsoft Intune 计划扫描。 当 [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) 睡眠模式恢复时， [适用于 Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) 的脚本中提供的命令行管理程序脚本将持续存在。 

有关如何 [在企业中使用此脚本](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) 的详细说明，请参阅在 Intune 中使用 macOS 设备的 shell 脚本。
