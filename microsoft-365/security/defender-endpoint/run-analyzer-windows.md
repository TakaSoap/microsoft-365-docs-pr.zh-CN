---
title: 在 Windows 上运行客户端分析器
description: 了解如何在 Windows 运行 Microsoft Defender for Endpoint Client Analyzer。
keywords: 客户端分析器， 传感器疑难解答， 分析器， mdeanalyzer， windows
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 754ec7b6cdd6e6c5e3c9f5765d839bd94a1d720b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59197261"
---
#  <a name="run-the-client-analyzer-on-windows"></a>在 Windows 上运行客户端分析器

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)


1.  将[MDE 客户端分析器工具](https://aka.ms/mdatpanalyzer)下载到Windows调查的客户端计算机。

2.  提取计算机上MDEClientAnalyzer.zip的内容。

3.  打开提升的命令行:
    1. 转到“**开始**”并键入“**cmd**”。
    2. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

4.  输入以下命令，再按 **Enter**：

```
HardDrivePath\MDEClientAnalyzer.cmd
```

**将 HardDrivePath 替换为工具提取到的路径，例如：**

`C:\Work\tools\MDATPClientAnalyzer\MDEClientAnalyzer.cmd`

除上述内容外，还有一个选项使用 [实时响应收集分析器支持日志](troubleshoot-collect-support-log.md)。

> [!NOTE]  
> 在 windows 10 Windows Server 2019 或更高版本的操作系统版本上，客户端分析器脚本将调用可执行文件，以运行对云服务 URL 的连接 `MDEClientAnalyzer.exe` 测试。 <br> <br> 在 Windows 8.1、Windows Server 2016 或以前的操作系统版本上，客户端分析器脚本将调用可执行文件，以运行命令和控制 (CnC) URL 的连接测试，同时还调用用于网络数据通道 URL 的 Microsoft Monitoring Agent 连接工具。 `MDEClientAnalyzerPreviousVersion.exe` `TestCloudConnection.exe`

## <a name="result-package-contents-on-windows"></a>结果包内容Windows

> [!NOTE]    
> 捕获的确切文件可能会因以下因素而更改：
> -   运行分析器的窗口的版本。
> -   计算机上事件日志通道的可用性。
> -   如果计算机尚未EDR， (感知的启动状态将) 。
>-   如果分析器命令使用了高级疑难解答参数。

默认情况下，解压缩MDEClientAnalyzerResult.zip文件将包含以下项目。

-   MDEClientAnalyzer.htm 这是主要的 HTML 输出文件，其中包含计算机上运行的分析器脚本可以 \| 生成的结果和指导。

-   SystemInfoLogs [Folder]

    -   AddRemovePrograms.csv <br> 说明：从注册表收集的已安装软件的列表。

-   AddRemoveProgramsWOW64.csv <br> 说明：从注册表收集的 x64 操作系统软件上安装的 x86 软件列表。

    -   CertValidate.log <br> 说明：通过调用 [CertUtil](/windows-server/administration/windows-commands/certutil)执行证书吊销的详细结果。

    -   dsregcmd.txt <br> 说明：输出运行 [dsregcmd](/azure/active-directory/devices/troubleshoot-device-dsregcmd)。
        这将提供有关计算机 Azure AD 状态的详细信息。

    -   IFEO.txt <br> 说明：计算机上 [配置的映像](/previous-versions/windows/desktop/xperf/image-file-execution-options) 文件执行选项的输出

    -   MDEClientAnalyzer.txt <br> 说明：这是详细的文本文件，其中显示分析器脚本执行的详细信息。

    -   MDEClientAnalyzer.xml <br> 说明：包含分析器脚本结果的 XML 格式。

    -   RegOnboardedInfoCurrent.Js打开 <br> 说明：从注册表中以 JSON 格式收集的载入计算机信息。

    -   RegOnboardingInfoPolicy.Js打开 <br> 说明：从注册表中以 JSON 格式收集的载入策略配置。

    -   SCHANNEL.txt <br> 说明：有关 [应用于计算机（如](/windows-server/security/tls/manage-tls) 从注册表中收集）的 SCHANNEL 配置的详细信息。

    -   SessionManager.txt <br> 说明：会话管理器特定设置从注册表中收集。

    -   SSL_00010002.txt <br> 说明：有关 [应用于从](/windows-server/security/tls/manage-tls) 注册表中收集的机器的 SSL 配置的详细信息。

-   EventLogs [Folder]

    -   utc.evtx <br> 说明：导出 DiagTrack 事件日志

    -   senseIR.evtx <br> 说明：导出自动调查事件日志

    -   sense.evtx <br> 说明：导出传感器主事件日志

    -   OperationsManager.evtx <br> 说明：导出Microsoft Monitoring Agent事件日志


## <a name="see-also"></a>另请参阅
- [客户端分析器概述](overview-client-analyzer.md)
- [下载并运行分析器](download-client-analyzer.md)
- [用于在 Windows 上进行高级故障排除的数据收集](data-collection-analyzer.md)
- [了解分析器 HTML 报表](analyzer-report.md)
