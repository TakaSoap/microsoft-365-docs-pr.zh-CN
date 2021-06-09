---
title: 解决 Microsoft Defender for Endpoint 实时响应问题
description: 解决在 Microsoft Defender for Endpoint 中使用实时响应时可能出现的问题
keywords: 实时响应， 实时， 响应， 锁定， 文件
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
ms.openlocfilehash: 99a52188dd5f6eca2f8368aa3c114d0bfb950b10
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844150"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a><span data-ttu-id="f18d4-104">解决 Microsoft Defender for Endpoint 实时响应问题</span><span class="sxs-lookup"><span data-stu-id="f18d4-104">Troubleshoot Microsoft Defender for Endpoint live response issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f18d4-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f18d4-105">**Applies to:**</span></span>
- [<span data-ttu-id="f18d4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f18d4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f18d4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f18d4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f18d4-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="f18d4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f18d4-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f18d4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="f18d4-110">此页面提供解决实时响应问题的详细步骤。</span><span class="sxs-lookup"><span data-stu-id="f18d4-110">This page provides detailed steps to troubleshoot live response issues.</span></span>

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a><span data-ttu-id="f18d4-111">在实时响应会话期间无法访问文件</span><span class="sxs-lookup"><span data-stu-id="f18d4-111">File cannot be accessed during live response sessions</span></span>
<span data-ttu-id="f18d4-112">如果在实时响应会话期间尝试采取操作时，您遇到一条错误消息，指出无法访问该文件，您需要使用以下步骤来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="f18d4-112">If while trying to take an action during a live response session, you encounter an error message stating that the file can't be accessed, you'll need to use the steps below to address the issue.</span></span>

1. <span data-ttu-id="f18d4-113">复制以下脚本代码段并将其另存为 PS1 文件：</span><span class="sxs-lookup"><span data-stu-id="f18d4-113">Copy the following script code snippet and save it as a PS1 file:</span></span>

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. <span data-ttu-id="f18d4-114">将脚本添加到实时响应库。</span><span class="sxs-lookup"><span data-stu-id="f18d4-114">Add the script to the live response library.</span></span>
3. <span data-ttu-id="f18d4-115">使用一个参数运行脚本：要复制的文件的文件路径。</span><span class="sxs-lookup"><span data-stu-id="f18d4-115">Run the script with one parameter: the file path of the file to be copied.</span></span>
4. <span data-ttu-id="f18d4-116">导航到 TEMP 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f18d4-116">Navigate to your TEMP folder.</span></span>
5. <span data-ttu-id="f18d4-117">对复制的文件运行要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="f18d4-117">Run the action you wanted to take on the copied file.</span></span>

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a><span data-ttu-id="f18d4-118">初始连接期间实时响应会话慢或延迟</span><span class="sxs-lookup"><span data-stu-id="f18d4-118">Slow live response sessions or delays during initial connections</span></span>
<span data-ttu-id="f18d4-119">实时响应利用 Defender for Endpoint 传感器注册和 WNS 服务在 Windows。</span><span class="sxs-lookup"><span data-stu-id="f18d4-119">Live response leverages Defender for Endpoint sensor registration with WNS service in Windows.</span></span> <span data-ttu-id="f18d4-120">如果实时响应的连接问题，请确认以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="f18d4-120">If you are having connectivity issues with live response, confirm the following details:</span></span>
1. <span data-ttu-id="f18d4-121">`notify.windows.com` 不会在你的环境中被阻止。</span><span class="sxs-lookup"><span data-stu-id="f18d4-121">`notify.windows.com` is not blocked in your environment.</span></span> <span data-ttu-id="f18d4-122">有关详细信息，请参阅配置 [设备代理和 Internet 连接设置](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="f18d4-122">For more information, see, [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>
2. <span data-ttu-id="f18d4-123">未 (Windows WpnService) 推送通知系统服务。</span><span class="sxs-lookup"><span data-stu-id="f18d4-123">WpnService (Windows Push Notifications System Service) is not disabled.</span></span>

<span data-ttu-id="f18d4-124">请参阅以下文章，以完全了解 WpnService 服务行为和要求：</span><span class="sxs-lookup"><span data-stu-id="f18d4-124">Refer to the articles below to fully understand the WpnService service behavior and requirements:</span></span>
- [<span data-ttu-id="f18d4-125">Windows推送通知服务 (WNS) 概述</span><span class="sxs-lookup"><span data-stu-id="f18d4-125">Windows Push Notification Services (WNS) overview</span></span>](/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [<span data-ttu-id="f18d4-126">Enterprise支持 WNS 流量的防火墙和代理配置</span><span class="sxs-lookup"><span data-stu-id="f18d4-126">Enterprise Firewall and Proxy Configurations to Support WNS Traffic</span></span>](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [<span data-ttu-id="f18d4-127">Microsoft 推送通知服务 (MPNS) 公共 IP 范围</span><span class="sxs-lookup"><span data-stu-id="f18d4-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

