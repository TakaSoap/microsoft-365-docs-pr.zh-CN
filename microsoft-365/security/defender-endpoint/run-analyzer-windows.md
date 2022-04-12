---
title: 在 Windows 上运行客户端分析器
description: 了解如何在Windows上运行Microsoft Defender for Endpoint客户端分析器。
keywords: 客户端分析器，传感器故障排除，分析器，mdeanalyzer，windows
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
ms.openlocfilehash: 5ac27241297b9943f1559653777b8e1668fe7f89
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783020"
---
# <a name="run-the-client-analyzer-on-windows"></a>在 Windows 上运行客户端分析器

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

1. 将 [MDE 客户端分析器工具](https://aka.ms/mdatpanalyzer)下载到需要调查的Windows计算机。

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

除了上述内容，还可以选择 [使用实时响应收集分析器支持日志](troubleshoot-collect-support-log.md)。

> [!NOTE]
> Windows 10/11、Windows服务器 2019/2022 或 Windows服务器 2012R2/2016 上安装了[新式统一解决方案](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)，客户端分析器脚本调用到调用`MDEClientAnalyzer.exe`以运行云服务 URL 连接测试的可执行文件。
>
> 在Windows 8.1、Windows Server 2016或以前用于载入Microsoft Monitoring Agent (MMA) 的任何 OS 版本中，客户端分析器脚本会调用到调用`MDEClientAnalyzerPreviousVersion.exe`的可执行文件中，以运行命令和控制 (CnC) URL 的连接测试，同时调用到Microsoft Monitoring Agent网络数据通道 URL 的连接工具`TestCloudConnection.exe`。


分析器中包含的所有 PowerShell 脚本和模块都是 Microsoft 签名的。
如果已以任何方式修改文件，则分析器应退出并出现以下错误：

:::image type="content" source="images/sigerror.png" alt-text="客户端分析器错误" lightbox="images/sigerror.png":::


如果显示此错误，则issuerInfo.txt输出将包含有关发生此错误的原因以及受影响的文件的详细信息：

:::image type="content" source="images/issuerinfo.png" alt-text="颁发者信息" lightbox="images/issuerinfo.png":::


修改MDEClientAnalyzer.ps1后的示例内容：

:::image type="content" source="images/modified-ps1.png" alt-text="修改后的 ps1 文件" lightbox="images/modified-ps1.png":::



## <a name="result-package-contents-on-windows"></a>Windows上的结果包内容

> [!NOTE]
> 捕获的确切文件可能会根据以下因素而变化：
>
> - 运行分析器的窗口的版本。
> - 计算机上的事件日志通道可用性。
> - 如果计算机尚未载入) ，则EDR传感器 (Sense 的开始状态将停止。
> - 如果分析器命令使用了高级故障排除参数。

默认情况下，未打包的MDEClientAnalyzerResult.zip文件将包含以下项。

- MDEClientAnalyzer.htm

  这是主要的 HTML 输出文件，其中将包含分析器脚本在计算机上运行可以生成的结果和指导。

- SystemInfoLogs \[文件夹\]
  - AddRemovePrograms.csv

    说明：从注册表收集的 x64 OS 软件上安装的 x86 软件的列表。

  - AddRemoveProgramsWOW64.csv

    说明：从注册表收集的 x64 OS 软件上安装的 x86 软件的列表。

    - CertValidate.log

      说明：通过调用 [CertUtil](/windows-server/administration/windows-commands/certutil) 执行的证书吊销的详细结果。

    - dsregcmd.txt

      说明：运行 [dsregcmd](/azure/active-directory/devices/troubleshoot-device-dsregcmd) 的输出。 这提供了有关计算机Azure AD状态的详细信息。

    - IFEO.txt

      说明：在计算机上配置的 [映像文件执行选项](/previous-versions/windows/desktop/xperf/image-file-execution-options) 的输出

    - MDEClientAnalyzer.txt

      说明：这是详细文本文件，其中显示了分析器脚本执行的详细信息。

    - MDEClientAnalyzer.xml

      说明：包含分析器脚本结果的 XML 格式。

    - RegOnboardedInfoCurrent.Json

      说明：从注册表以 JSON 格式收集的载入计算机信息。

  - RegOnboardingInfoPolicy.Json

    说明：从注册表以 JSON 格式收集的载入策略配置。

    - SCHANNEL.txt

      说明：有关应用于从注册表收集的计算机的 [SCHANNEL 配置](/windows-server/security/tls/manage-tls) 的详细信息。

    - SessionManager.txt

      说明：从注册表收集特定于会话管理器的设置。

    - SSL_00010002.txt

      说明：有关应用于从注册表收集的计算机的 [SSL 配置](/windows-server/security/tls/manage-tls) 的详细信息。

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
