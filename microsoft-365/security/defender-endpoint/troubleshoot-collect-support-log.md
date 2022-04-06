---
title: 使用实时响应收集 Microsoft Defender for Endpoint 中的支持日志
description: 了解如何使用实时响应收集日志，以排查 Microsoft Defender 终结点问题
keywords: 支持， 日志， 收集， 疑难解答， 实时响应， liveanalyzer， 分析器， 实时， 响应
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 138b532e7786a3d142c3cbbe68f668a4b0e05591
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472564"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>使用实时响应收集 Microsoft Defender for Endpoint 中的支持日志


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)。


联系支持人员时，系统可能会要求你提供 Microsoft Defender for Endpoint Client Analyzer 工具的输出程序包。

本主题提供有关如何通过实时响应运行该工具的说明。

1. 从 [Microsoft Defender for Endpoint Client Analyzer](https://aka.ms/BetaMDEAnalyzer) 的"工具"子目录中下载和提取所需的脚本。 <br>
例如，若要获取基本传感器和设备运行状况日志，请获取"."。\Tools\MDELiveAnalyzer.ps1"。<br>
如果你还需要 Defender 防病毒支持日志 (MpSupportFiles.cab) ，则提取"."。\Tools\MDELiveAnalyzerAV.ps1" 

2. 在 [需要调查的](live-response.md#initiate-a-live-response-session-on-a-device) 计算机上启动实时响应会话。

3. 选择 **Upload文件到库"**。

   :::image type="content" source="images/upload-file.png" alt-text="上载文件" lightbox="images/upload-file.png":::

4. 选择 **"选择文件"**。

   :::image type="content" source="images/choose-file.png" alt-text="选择文件按钮-1" lightbox="images/choose-file.png":::

5. 选择下载的名为 MDELiveAnalyzer.ps1 文件，然后单击"确认 **"**

   :::image type="content" source="images/analyzer-file.png" alt-text="选择文件按钮-2" lightbox="images/analyzer-file.png":::

6. 仍在 LiveResponse 会话中时，请使用下面的命令运行分析器并收集结果文件：

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
    ```

    [![命令的图像。](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)

> [!NOTE]
>
> - 可在此处下载 MDEClientAnalyzer 的最新预览版本： [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer)。
>
> - LiveAnalyzer 脚本从 目标计算机上下载疑难解答包： https://mdatpclientanalyzer.blob.core.windows.net。
>
>   如果不允许计算机访问上述 URL，则MDEClientAnalyzerPreview.zip LiveAnalyzer 脚本之前将文件上载到库中：
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
>   ```
>
> - 有关在计算机中本地收集数据（如果计算机未与适用于 Endpoint 云服务的 Microsoft Defender 通信，或未按预期显示在 Microsoft Defender for Endpoint 门户中）上的数据详细信息，请参阅验证与适用于终结点服务的 [Microsoft Defender](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls) 服务 URL 的客户端连接。
> 
> - 如 [实时响应命令示例中](live-response-command-examples.md)所述，你可能想要在命令末尾使用"&"符号来收集日志作为后台操作：
>   ```console
>   Run MDELiveAnalyzer.ps1&
>   ```


## <a name="see-also"></a>另请参阅
- [客户端分析器概述](overview-client-analyzer.md)
- [下载并运行分析器](download-client-analyzer.md)
- [在 Windows 上运行客户端分析器](run-analyzer-windows.md)
- [在 macOS 或 Linux 上运行客户端分析器](run-analyzer-macos-linux.md)
- [用于在 Windows 上进行高级故障排除的数据收集](data-collection-analyzer.md)
- [了解分析器 HTML 报表](analyzer-report.md)
