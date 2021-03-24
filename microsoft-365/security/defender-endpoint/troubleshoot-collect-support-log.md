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
ms.openlocfilehash: 50e7bc6d84714411c89f014bb0018a3102617cb7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055907"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>使用实时响应收集 Microsoft Defender for Endpoint 中的支持日志 


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


联系支持人员时，系统可能会要求你提供 Microsoft Defender for Endpoint Client Analyzer 工具的输出程序包。

本主题提供有关如何通过实时响应运行该工具的说明。

1. 下载相应的脚本
    * 仅适用于 Endpoint 客户端传感器日志的 Microsoft [ Defender：LiveAnalyzer.ps1脚本](https://aka.ms/MDELiveAnalyzer)。
      - 结果包近似大小：~100Kb 
    *  Microsoft Defender for Endpoint 客户端传感器和防病毒日志 [：LiveAnalyzer+MDAV.ps1脚本](https://aka.ms/MDELiveAnalyzerAV)。
       - 结果包近似大小：~10Mb 
 
2.  在 [需要调查的](live-response.md#initiate-a-live-response-session-on-a-device) 计算机上启动实时响应会话。

3.  选择 **"将文件上载到库"。**

    ![上传文件的图像](images/upload-file.png)

4. 选择 **"选择文件"。**

    ![选择文件按钮 1 的图像](images/choose-file.png)

5. 选择下载的名为 MDELiveAnalyzer.ps1 文件，然后单击"确认 **"**


   ![选择文件按钮 2 的图像](images/analyzer-file.png)


6. 仍在 LiveResponse 会话中时，请使用下面的命令运行分析器并收集结果文件：

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
    ```

    ![命令图像](images/analyzer-commands.png)


>[!NOTE]
> - 可在此处下载 MDEClientAnalyzer 的最新预览版本 [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) ：。
> 
> - LiveAnalyzer 脚本从 目标计算机上下载疑难解答包 https://mdatpclientanalyzer.blob.core.windows.net ：。
> 
>   如果不允许计算机访问上述 URL，则MDEClientAnalyzerPreview.zip LiveAnalyzer 脚本之前将文件上载到库中：
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
>   ```
> 
> - 有关在计算机本地收集数据（如果计算机未与适用于 Endpoint 云服务的 Microsoft Defender 通信，或未按预期显示在 Microsoft Defender for Endpoint 门户中）上的数据详细信息，请参阅验证与 [Microsoft Defender for Endpoint](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)服务 URL 的客户端连接。
