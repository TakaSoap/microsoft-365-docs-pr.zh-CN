---
title: 查看 Microsoft Defender AV 扫描的结果
description: 使用应用、Microsoft Endpoint Configuration Manager或Microsoft Intune查看Windows 安全中心结果
keywords: 扫描结果， 修正， 完全扫描， 快速扫描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ec3dd2edc09d504af0ed76b17577130b1cdce1b7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275368"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a><span data-ttu-id="fa5c6-104">查看Microsoft Defender 防病毒扫描结果</span><span class="sxs-lookup"><span data-stu-id="fa5c6-104">Review Microsoft Defender Antivirus scan results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fa5c6-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="fa5c6-105">**Applies to:**</span></span>

- [<span data-ttu-id="fa5c6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fa5c6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="fa5c6-107">在Microsoft Defender 防病毒扫描完成后，无论是按需扫描还是计划扫描，将记录[](run-scan-microsoft-defender-antivirus.md)结果，并且您可以查看[](scheduled-catch-up-scans-microsoft-defender-antivirus.md)结果。</span><span class="sxs-lookup"><span data-stu-id="fa5c6-107">After a Microsoft Defender Antivirus scan completes, whether it is an [on-demand](run-scan-microsoft-defender-antivirus.md) or [scheduled scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md), the results are recorded and you can view the results.</span></span> 


## <a name="use-configuration-manager-to-review-scan-results"></a><span data-ttu-id="fa5c6-108">使用 Configuration Manager 查看扫描结果</span><span class="sxs-lookup"><span data-stu-id="fa5c6-108">Use Configuration Manager to review scan results</span></span>

<span data-ttu-id="fa5c6-109">请参阅[如何监视Endpoint Protection状态](/configmgr/protect/deploy-use/monitor-endpoint-protection)。</span><span class="sxs-lookup"><span data-stu-id="fa5c6-109">See [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span>

## <a name="use-powershell-cmdlets-to-review-scan-results"></a><span data-ttu-id="fa5c6-110">使用 PowerShell cmdlet 查看扫描结果</span><span class="sxs-lookup"><span data-stu-id="fa5c6-110">Use PowerShell cmdlets to review scan results</span></span>

<span data-ttu-id="fa5c6-111">以下 cmdlet 将返回终结点上的每个检测。</span><span class="sxs-lookup"><span data-stu-id="fa5c6-111">The following cmdlet will return each detection on the endpoint.</span></span> <span data-ttu-id="fa5c6-112">如果对同一威胁进行多次检测，将基于每次检测的时间单独列出每个检测：</span><span class="sxs-lookup"><span data-stu-id="fa5c6-112">If there are multiple detections of the same threat, each detection will be listed separately, based on the time of each detection:</span></span>

```PowerShell
Get-MpThreatDetection
```

![PowerShell cmdlet 和输出的屏幕截图](images/defender/wdav-get-mpthreatdetection.png)

<span data-ttu-id="fa5c6-114">你可以指定 `-ThreatID` 将输出限制为只显示特定威胁的检测。</span><span class="sxs-lookup"><span data-stu-id="fa5c6-114">You can specify `-ThreatID` to limit the output to only show the detections for a specific threat.</span></span>

<span data-ttu-id="fa5c6-115">如果要列出威胁检测，但将同一威胁的检测组合到单个项目，可以使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="fa5c6-115">If you want to list threat detections, but combine detections of the same threat into a single item, you can use the following cmdlet:</span></span>

```PowerShell
Get-MpThreat
```

![PowerShell 屏幕截图](images/defender/wdav-get-mpthreat.png)

<span data-ttu-id="fa5c6-117">请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender cmdlet](/powershell/module/defender/) ，了解有关如何通过 Microsoft Defender 防病毒软件使用 PowerShell 的信息。</span><span class="sxs-lookup"><span data-stu-id="fa5c6-117">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a><span data-ttu-id="fa5c6-118">使用 Windows Management Instruction (WMI) 查看扫描结果</span><span class="sxs-lookup"><span data-stu-id="fa5c6-118">Use Windows Management Instruction (WMI) to review scan results</span></span>

<span data-ttu-id="fa5c6-119">使用 [**Get** 方法的 **MSFT_MpThreat** 和 **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) 类。</span><span class="sxs-lookup"><span data-stu-id="fa5c6-119">Use the [**Get** method of the **MSFT_MpThreat** and **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) classes.</span></span>


## <a name="related-articles"></a><span data-ttu-id="fa5c6-120">相关文章</span><span class="sxs-lookup"><span data-stu-id="fa5c6-120">Related articles</span></span>

- [<span data-ttu-id="fa5c6-121">自定义、启动和查看扫描Microsoft Defender 防病毒修正的结果</span><span class="sxs-lookup"><span data-stu-id="fa5c6-121">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fa5c6-122">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="fa5c6-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)