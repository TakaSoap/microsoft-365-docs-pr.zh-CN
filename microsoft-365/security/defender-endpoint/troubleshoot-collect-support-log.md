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
ms.openlocfilehash: 07593fac6ed9a3fbc00d904718380b386f31dba3
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893409"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a><span data-ttu-id="9199d-104">使用实时响应收集 Microsoft Defender for Endpoint 中的支持日志</span><span class="sxs-lookup"><span data-stu-id="9199d-104">Collect support logs in Microsoft Defender for Endpoint using live response</span></span> 


<span data-ttu-id="9199d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9199d-105">**Applies to:**</span></span>
- [<span data-ttu-id="9199d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9199d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9199d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9199d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9199d-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="9199d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9199d-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="9199d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="9199d-110">联系支持人员时，系统可能会要求你提供 Microsoft Defender for Endpoint Client Analyzer 工具的输出程序包。</span><span class="sxs-lookup"><span data-stu-id="9199d-110">When contacting support, you may be asked to provide the output package of the Microsoft Defender for Endpoint Client Analyzer tool.</span></span>

<span data-ttu-id="9199d-111">本主题提供有关如何通过实时响应运行该工具的说明。</span><span class="sxs-lookup"><span data-stu-id="9199d-111">This topic provides instructions on how to run the tool via Live Response.</span></span>

1. <span data-ttu-id="9199d-112">下载相应的脚本</span><span class="sxs-lookup"><span data-stu-id="9199d-112">Download the appropriate script</span></span>
    * <span data-ttu-id="9199d-113">仅适用于 Endpoint 客户端传感器日志的 Microsoft [ Defender：LiveAnalyzer.ps1脚本](https://aka.ms/MDELiveAnalyzer)。</span><span class="sxs-lookup"><span data-stu-id="9199d-113">Microsoft Defender for Endpoint client sensor logs only: [LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer).</span></span>
      - <span data-ttu-id="9199d-114">结果包近似大小：~100Kb</span><span class="sxs-lookup"><span data-stu-id="9199d-114">Result package approximate size: ~100Kb</span></span> 
    *  <span data-ttu-id="9199d-115">Microsoft Defender for Endpoint 客户端传感器和防病毒日志 [：LiveAnalyzer+MDAV.ps1脚本](https://aka.ms/MDELiveAnalyzerAV)。</span><span class="sxs-lookup"><span data-stu-id="9199d-115">Microsoft Defender for Endpoint client sensor and Antivirus logs: [LiveAnalyzer+MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV).</span></span>
       - <span data-ttu-id="9199d-116">结果包近似大小：~10Mb</span><span class="sxs-lookup"><span data-stu-id="9199d-116">Result package approximate size: ~10Mb</span></span> 
 
2.  <span data-ttu-id="9199d-117">在 [需要调查的](live-response.md#initiate-a-live-response-session-on-a-device) 计算机上启动实时响应会话。</span><span class="sxs-lookup"><span data-stu-id="9199d-117">Initiate a [Live Response session](live-response.md#initiate-a-live-response-session-on-a-device) on the machine you need to investigate.</span></span>

3.  <span data-ttu-id="9199d-118">选择 **Upload文件到库"**。</span><span class="sxs-lookup"><span data-stu-id="9199d-118">Select **Upload file to library**.</span></span>

    ![上传文件的图像](images/upload-file.png)

4. <span data-ttu-id="9199d-120">选择 **"选择文件"。**</span><span class="sxs-lookup"><span data-stu-id="9199d-120">Select **Choose file**.</span></span>

    ![选择文件按钮 1 的图像](images/choose-file.png)

5. <span data-ttu-id="9199d-122">选择下载的名为 MDELiveAnalyzer.ps1 文件，然后单击"确认 **"**</span><span class="sxs-lookup"><span data-stu-id="9199d-122">Select the downloaded file named MDELiveAnalyzer.ps1 and then click on **Confirm**</span></span>


   ![选择文件按钮 2 的图像](images/analyzer-file.png)


6. <span data-ttu-id="9199d-124">仍在 LiveResponse 会话中时，请使用下面的命令运行分析器并收集结果文件：</span><span class="sxs-lookup"><span data-stu-id="9199d-124">While still in the LiveResponse session, use the commands below to run the analyzer and collect the result file:</span></span>

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
    ```

    <span data-ttu-id="9199d-125">[![命令图像 ](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9199d-125">[ ![Image of commands](images/analyzer-commands.png) ](images/analyzer-commands.png#lightbox)</span></span>


>[!NOTE]
> - <span data-ttu-id="9199d-126">可在此处下载 MDEClientAnalyzer 的最新预览版本 [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) ：。</span><span class="sxs-lookup"><span data-stu-id="9199d-126">The latest preview version of MDEClientAnalyzer can be downloaded here: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer).</span></span>
> 
> - <span data-ttu-id="9199d-127">LiveAnalyzer 脚本从 目标计算机上下载疑难解答包 https://mdatpclientanalyzer.blob.core.windows.net ：。</span><span class="sxs-lookup"><span data-stu-id="9199d-127">The LiveAnalyzer script downloads the troubleshooting package on the destination machine from: https://mdatpclientanalyzer.blob.core.windows.net.</span></span>
> 
>   <span data-ttu-id="9199d-128">如果不允许计算机访问上述 URL，则MDEClientAnalyzerPreview.zip LiveAnalyzer 脚本之前将文件上载到库中：</span><span class="sxs-lookup"><span data-stu-id="9199d-128">If you cannot allow the machine to reach the above URL, then upload MDEClientAnalyzerPreview.zip file to the library before running the LiveAnalyzer script:</span></span>
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
>   ```
> 
> - <span data-ttu-id="9199d-129">有关在计算机本地收集数据（如果计算机未与适用于 Endpoint 云服务的 Microsoft Defender 通信，或未按预期显示在 Microsoft Defender for Endpoint 门户中）上的数据详细信息，请参阅验证与 [Microsoft Defender for Endpoint](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)服务 URL 的客户端连接。</span><span class="sxs-lookup"><span data-stu-id="9199d-129">For more information on gathering data locally on a machine in case the machine isn't communicating with Microsoft Defender for Endpoint cloud services, or does not appear in Microsoft Defender for Endpoint portal as expected, see [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls).</span></span>
