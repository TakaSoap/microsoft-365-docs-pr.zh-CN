---
title: 使用实时响应收集适用于终结点的 Microsoft Defender 中的支持日志
description: 了解如何使用实时响应收集日志，以排查 Microsoft Defender for Endpoints 问题
keywords: 支持， 日志， 收集， 疑难解答， 实时响应， liveanalyzer， 分析器， 实时， 响应
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 518194e3cbf185da415104991e1d7186f5912953
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58250573"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>使用实时响应收集 Microsoft Defender for Endpoint 中的支持日志


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)。


联系支持人员时，系统可能会要求你提供 Microsoft Defender for Endpoint Client Analyzer 工具的输出程序包。

本主题提供有关如何通过实时响应运行该工具的说明。

1. 下载相应的脚本
   - 仅适用于 Endpoint 客户端传感器日志的 Microsoft [ Defender：LiveAnalyzer.ps1脚本](https://aka.ms/MDELiveAnalyzer)。
      - 结果包近似大小：~100Kb
   - Microsoft Defender for Endpoint 客户端传感器和防病毒日志 [：LiveAnalyzer+MDAV.ps1脚本](https://aka.ms/MDELiveAnalyzerAV)。
       - 结果包近似大小：~10Mb

2. 在 [需要调查的](live-response.md#initiate-a-live-response-session-on-a-device) 计算机上启动实时响应会话。

3. 选择 **Upload文件到库"**。

    ![上传文件的图像](images/upload-file.png)

4. 选择 **"选择文件"。**

    ![选择文件按钮 1 的图像](images/choose-file.png)

5. 选择下载的名为 MDELiveAnalyzer.ps1 文件，然后单击"确认 **"**

   ![选择文件按钮 2 的图像](images/analyzer-file.png)

6. 仍在 LiveResponse 会话中时，请使用下面的命令运行分析器并收集结果文件：

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
    ```

    [![命令图像](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)

> [!NOTE]
>
> - 可在此处下载 MDEClientAnalyzer 的最新预览版本 [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) ：。
>
> - LiveAnalyzer 脚本从 目标计算机上下载疑难解答包 https://mdatpclientanalyzer.blob.core.windows.net ：。
>
>   如果不允许计算机访问上述 URL，则MDEClientAnalyzerPreview.zip LiveAnalyzer 脚本之前将文件上载到库中：
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
>   ```
>
> - 有关在计算机本地收集数据（如果计算机未与适用于 Endpoint 云服务的 Microsoft Defender 通信，或未按预期显示在 Microsoft Defender for Endpoint 门户中）上的数据详细信息，请参阅验证与 [Microsoft Defender for Endpoint](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)服务 URL 的客户端连接。


## <a name="see-also"></a>另请参阅
- [客户端分析器概述](overview-client-analyzer.md)
- [下载并运行客户端分析器](download-client-analyzer.md)
- [在客户端上运行Windows](run-analyzer-windows.md)
- [在 macOS 或 Linux 上运行客户端分析器](run-analyzer-macos-linux.md)
- [用于对问题进行高级疑难解答Windows](data-collection-analyzer.md)
- [了解分析器 HTML 报告](analyzer-report.md)

