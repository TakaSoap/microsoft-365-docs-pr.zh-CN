---
title: 在 Windows 上运行客户端分析器
description: 了解如何在 Windows 运行 Microsoft Defender for Endpoint Client Analyzer。
keywords: 客户端分析器， 传感器疑难解答， 分析器， mdeanalyzer， windows
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
ms.openlocfilehash: 092a89e41efebafae36e81f5faa7cd3b52fde8d9
ms.sourcegitcommit: af73b93a904ce8604be319e8dc7cadaf65d50534
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/31/2022
ms.locfileid: "62281527"
---
# <a name="run-the-client-analyzer-on-windows"></a>在 Windows 上运行客户端分析器

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

1. 将 [MDE 客户端分析器工具](https://aka.ms/mdatpanalyzer)下载到Windows调查的客户端计算机。

2. 提取计算机上MDEClientAnalyzer.zip的内容。

3. 打开提升的命令行:
    1. 转到“**开始**”并键入“**cmd**”。
    2. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

4. 输入以下命令，再按 **Enter**：

   ```dos
   HardDrivePath\MDEClientAnalyzer.cmd
   ```

   **将 HardDrivePath 替换为工具提取到的路径，例如：**

   ```dos
   C:\Work\tools\MDEClientAnalyzer\MDEClientAnalyzer.cmd
   ```

除上述内容外，还有一个选项使用 [实时响应收集分析器支持日志](troubleshoot-collect-support-log.md)。

> [!NOTE]
> 在 Windows 10/11、Windows Server 2019/2022 或安装了新式统一解决方案的 Windows Server 2012R2/2016 [](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview) `MDEClientAnalyzer.exe` 上，客户端分析器脚本将调用可执行文件，以运行对云服务 URL 的连接测试。
>
> 在 Windows 8.1、Windows Server 2016 或任何之前的操作系统版本（其中 Microsoft Monitoring Agent (MMA) `MDEClientAnalyzerPreviousVersion.exe` 用于载入）上，客户端分析器脚本会调用可执行文件，以运行命令和控制 (CnC) URL 的连接测试，同时调用Microsoft Monitoring Agent网络`TestCloudConnection.exe`数据通道 URL 的连接工具。


分析工具中包含的所有 PowerShell 脚本和模块都由 Microsoft 签名。
如果文件已经过任何修改，则分析器应退出，并出现以下错误：

![客户端分析器错误的图像](images/sigerror.png)


如果显示此错误，则issuerInfo.txt输出将包含有关发生此错误的原因和受影响的文件的详细信息：

![颁发者信息的图像](images/issuerinfo.png)


修改MDEClientAnalyzer.ps1后的示例内容：

![修改后的 ps1 文件的图像](images/modified-ps1.png)



## <a name="result-package-contents-on-windows"></a>结果包内容Windows

> [!NOTE]
> 捕获的确切文件可能会因以下因素而更改：
>
> - 运行分析器的窗口的版本。
> - 计算机上事件日志通道的可用性。
> - 如果计算机尚未EDR， (感知的启动状态将) 。
> - 如果分析器命令使用了高级疑难解答参数。

默认情况下，解压缩MDEClientAnalyzerResult.zip文件将包含以下项目。

- MDEClientAnalyzer.htm

  这是主要的 HTML 输出文件，其中包含计算机上运行的分析器脚本可以生成的结果和指导。

- SystemInfoLogs \[文件夹\]
  - AddRemovePrograms.csv

    说明：从注册表收集的 x64 操作系统软件上安装的 x86 软件列表。

  - AddRemoveProgramsWOW64.csv

    说明：从注册表收集的 x64 操作系统软件上安装的 x86 软件列表。

    - CertValidate.log

      说明：通过调用 [CertUtil](/windows-server/administration/windows-commands/certutil) 执行的证书吊销的详细结果。

    - dsregcmd.txt

      说明：运行 [dsregcmd 的输出](/azure/active-directory/devices/troubleshoot-device-dsregcmd)。 这将提供有关计算机Azure AD状态的详细信息。

    - IFEO.txt

      说明：计算机上 [配置的映像](/previous-versions/windows/desktop/xperf/image-file-execution-options) 文件执行选项的输出

    - MDEClientAnalyzer.txt

      说明：这是详细的文本文件，其中显示分析器脚本执行的详细信息。

    - MDEClientAnalyzer.xml

      说明：包含分析器脚本结果的 XML 格式。

    - RegOnboardedInfoCurrent.Json

      说明：从注册表中以 JSON 格式收集的载入计算机信息。

  - RegOnboardingInfoPolicy.Json

    说明：从注册表中以 JSON 格式收集的载入策略配置。

    - SCHANNEL.txt

      说明：有关 [应用于计算机（如](/windows-server/security/tls/manage-tls) 从注册表中收集）的 SCHANNEL 配置的详细信息。

    - SessionManager.txt

      说明：会话管理器特定设置从注册表中收集。

    - SSL_00010002.txt

      说明：有关 [应用于从](/windows-server/security/tls/manage-tls) 注册表中收集的机器的 SSL 配置的详细信息。

- EventLogs [Folder]

  - utc.evtx

    说明：导出 DiagTrack 事件日志

  - senseIR.evtx

    说明：导出自动调查事件日志

  - sense.evtx

    说明：导出传感器主事件日志

  - OperationsManager.evtx

    说明：导出Microsoft Monitoring Agent事件日志




## <a name="see-also"></a>另请参阅

- [客户端分析器概述](overview-client-analyzer.md)
- [下载并运行分析器](download-client-analyzer.md)
- [用于在 Windows 上进行高级故障排除的数据收集](data-collection-analyzer.md)
- [了解分析器 HTML 报表](analyzer-report.md)
