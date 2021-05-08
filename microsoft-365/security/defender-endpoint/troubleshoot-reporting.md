---
title: Microsoft Defender AV 报告工具问题疑难解答
description: 确定并解决尝试在更新合规性中报告 Microsoft Defender AV 保护状态的常见问题
keywords: 疑难解答， 错误， 修复， 更新合规性， oms， 监视器， 报告， Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ca62db922a13ab2cb3226eaf0efb92bfaf8c572b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274888"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a><span data-ttu-id="61871-104">解决更新合规性中的 Microsoft Defender 防病毒软件报告问题</span><span class="sxs-lookup"><span data-stu-id="61871-104">Troubleshoot Microsoft Defender Antivirus reporting in Update Compliance</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="61871-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="61871-105">**Applies to:**</span></span>

- [<span data-ttu-id="61871-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61871-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="61871-107">2020 年 3 月 31 Microsoft Defender 防病毒，将删除更新合规性报告功能。</span><span class="sxs-lookup"><span data-stu-id="61871-107">On March 31, 2020, the Microsoft Defender Antivirus reporting feature of Update Compliance will be removed.</span></span> <span data-ttu-id="61871-108">你可以继续使用 Microsoft Endpoint Manager 定义[和查看](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)安全合规性策略，从而可以更精细地控制安全功能和更新。</span><span class="sxs-lookup"><span data-stu-id="61871-108">You can continue to define and review security compliance policies using [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), which allows finer control over security features and updates.</span></span>

<span data-ttu-id="61871-109">可以使用更新Microsoft Defender 防病毒一致性。</span><span class="sxs-lookup"><span data-stu-id="61871-109">You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="61871-110">你将看到 E3、B、F1、VL 和 Pro状态。</span><span class="sxs-lookup"><span data-stu-id="61871-110">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="61871-111">但是，对于 E5 许可证，你需要使用 [Microsoft Defender for Endpoint 门户](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="61871-111">However, for E5 licenses, you need to use the [Microsoft Defender for Endpoint portal](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="61871-112">若要了解有关许可选项的详细信息，请参阅Windows 10[许可选项](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)。</span><span class="sxs-lookup"><span data-stu-id="61871-112">To learn more about licensing options, see [Windows 10 product licensing options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).</span></span>

<span data-ttu-id="61871-113">当你使用[Windows 分析](/windows/deployment/update/update-compliance-using#wdav-assessment)更新合规性获取有关网络中正在使用 Microsoft Defender 防病毒 的设备或终结点的保护状态的报告时，你可能会遇到问题或问题。</span><span class="sxs-lookup"><span data-stu-id="61871-113">When you use [Windows Analytics Update Compliance to obtain reporting into the protection status of devices or endpoints](/windows/deployment/update/update-compliance-using#wdav-assessment) in your network that are using Microsoft Defender Antivirus, you might encounter problems or issues.</span></span>

<span data-ttu-id="61871-114">通常，最常见的问题指标是：</span><span class="sxs-lookup"><span data-stu-id="61871-114">Typically, the most common indicators of a problem are:</span></span>
- <span data-ttu-id="61871-115">你只能看到预期看到的所有设备的一小部分或一部分</span><span class="sxs-lookup"><span data-stu-id="61871-115">You only see a small number or subset of all the devices you were expecting to see</span></span>
- <span data-ttu-id="61871-116">你完全看不到任何设备</span><span class="sxs-lookup"><span data-stu-id="61871-116">You do not see any devices at all</span></span>
- <span data-ttu-id="61871-117">您看到的报告和信息已过时 (超过几天) </span><span class="sxs-lookup"><span data-stu-id="61871-117">The reports and information you do see is outdated (older than a few days)</span></span>

<span data-ttu-id="61871-118">有关与更新合规性不相关的 Microsoft Defender 防病毒 服务相关的常见错误代码和事件MICROSOFT DEFENDER 防病毒[事件](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="61871-118">For common error codes and event IDs related to the Microsoft Defender Antivirus service that are not related to Update Compliance, see [Microsoft Defender Antivirus events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="61871-119">解决这些问题有三个步骤：</span><span class="sxs-lookup"><span data-stu-id="61871-119">There are three steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="61871-120">确认已满足所有先决条件</span><span class="sxs-lookup"><span data-stu-id="61871-120">Confirm that you have met all prerequisites</span></span>
2. <span data-ttu-id="61871-121">检查与基于云的Windows Defender的连接</span><span class="sxs-lookup"><span data-stu-id="61871-121">Check your connectivity to the Windows Defender cloud-based service</span></span>
3. <span data-ttu-id="61871-122">提交支持日志</span><span class="sxs-lookup"><span data-stu-id="61871-122">Submit support logs</span></span>

>[!IMPORTANT]
><span data-ttu-id="61871-123">设备通常需要 3 天时间开始在更新合规性中显示。</span><span class="sxs-lookup"><span data-stu-id="61871-123">It typically takes 3 days for devices to start appearing in Update Compliance.</span></span>


## <a name="confirm-prerequisites"></a><span data-ttu-id="61871-124">确认先决条件</span><span class="sxs-lookup"><span data-stu-id="61871-124">Confirm prerequisites</span></span>

<span data-ttu-id="61871-125">为了使设备正确显示在更新合规性中，必须满足更新合规性服务和更新合规性服务的某些Microsoft Defender 防病毒：</span><span class="sxs-lookup"><span data-stu-id="61871-125">In order for devices to properly show up in Update Compliance, you have to meet certain prerequisites for both the Update Compliance service and for Microsoft Defender Antivirus:</span></span>

>[!div class="checklist"]
>- <span data-ttu-id="61871-126">终结点将 Microsoft Defender 防病毒用作唯一的防病毒保护应用。</span><span class="sxs-lookup"><span data-stu-id="61871-126">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="61871-127">[使用任何其他防病毒应用将导致 Microsoft Defender AV](microsoft-defender-antivirus-compatibility.md) 自行禁用，并且不会在更新合规性中报告终结点。</span><span class="sxs-lookup"><span data-stu-id="61871-127">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](microsoft-defender-antivirus-compatibility.md) and the endpoint will not be reported in Update Compliance.</span></span>
> - <span data-ttu-id="61871-128">[云提供的保护已启用](enable-cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="61871-128">[Cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="61871-129">终结点可以 [连接到 Microsoft Defender AV 云](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="61871-129">Endpoints can [connect to the Microsoft Defender AV cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span></span>
> - <span data-ttu-id="61871-130">如果终结点在版本 1607 Windows 10版本运行，Windows 10诊断数据[必须设置为增强级别](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)。</span><span class="sxs-lookup"><span data-stu-id="61871-130">If the endpoint is running Windows 10 version 1607 or earlier, [Windows 10 diagnostic data must be set to the Enhanced level](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span></span>
> - <span data-ttu-id="61871-131">已满足所有要求 3 天</span><span class="sxs-lookup"><span data-stu-id="61871-131">It has been 3 days since all requirements have been met</span></span>

<span data-ttu-id="61871-132">"你可以将Microsoft Defender 防病毒更新合规性。</span><span class="sxs-lookup"><span data-stu-id="61871-132">“You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="61871-133">你将看到 E3、B、F1、VL 和 Pro状态。</span><span class="sxs-lookup"><span data-stu-id="61871-133">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="61871-134">但是，对于 E5 许可证，你需要使用 Microsoft Defender for Endpoint 门户 https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) (。</span><span class="sxs-lookup"><span data-stu-id="61871-134">However, for E5 licenses, you need to use the Microsoft Defender for Endpoint portal (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="61871-135">若要了解有关许可选项的详细信息，请参阅Windows 10许可选项"</span><span class="sxs-lookup"><span data-stu-id="61871-135">To learn more about licensing options, see Windows 10 product licensing options"</span></span>

<span data-ttu-id="61871-136">如果满足上述所有先决条件，您可能需要继续执行下一步以收集诊断信息并将其发送给我们。</span><span class="sxs-lookup"><span data-stu-id="61871-136">If the above prerequisites have all been met, you might need to proceed to the next step to collect diagnostic information and send it to us.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="61871-137">收集诊断数据以进行更新合规性疑难解答</span><span class="sxs-lookup"><span data-stu-id="61871-137">Collect diagnostic data for Update Compliance troubleshooting</span></span>](collect-diagnostic-data.md)  

## <a name="related-topics"></a><span data-ttu-id="61871-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="61871-138">Related topics</span></span>

- [<span data-ttu-id="61871-139">Microsoft Defender 防病毒Windows 10</span><span class="sxs-lookup"><span data-stu-id="61871-139">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="61871-140">部署Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="61871-140">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)