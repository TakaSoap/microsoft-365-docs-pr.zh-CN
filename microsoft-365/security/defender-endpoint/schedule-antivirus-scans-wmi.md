---
title: 使用 Management Instrumentation 计划Windows扫描
description: 使用 WMI 计划防病毒扫描
keywords: 快速扫描， 完全扫描， WMI， 计划， 防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1aa174f4601fb57eebbc4fb7c78e1809b9f072c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879656"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a><span data-ttu-id="64f5c-104">使用 Management Instrumentation Windows WMI (安排防病毒扫描) </span><span class="sxs-lookup"><span data-stu-id="64f5c-104">Schedule antivirus scans using Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="64f5c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="64f5c-105">**Applies to:**</span></span>

- [<span data-ttu-id="64f5c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="64f5c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="64f5c-107">本文介绍如何使用 WMI 配置计划扫描。</span><span class="sxs-lookup"><span data-stu-id="64f5c-107">This article describes how to configure scheduled scans using WMI.</span></span> <span data-ttu-id="64f5c-108">若要了解有关计划扫描和扫描类型有关详细信息，请参阅配置计划的快速或完全Microsoft Defender 防病毒[扫描](schedule-antivirus-scans.md)。</span><span class="sxs-lookup"><span data-stu-id="64f5c-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="64f5c-109">使用 Windows Management Instruction (WMI) 计划扫描</span><span class="sxs-lookup"><span data-stu-id="64f5c-109">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="64f5c-110">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="64f5c-110">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="64f5c-111">有关详细信息和允许的参数，请参阅Windows Defender [WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="64f5c-111">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="64f5c-112">不使用终结点时用于计划扫描的 WMI</span><span class="sxs-lookup"><span data-stu-id="64f5c-112">WMI for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="64f5c-113">对 [以下属性MSFT_MpPreference类](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="64f5c-113">Use the [Set method of the MSFT_MpPreference class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="64f5c-114">有关 API 和允许的参数详细信息，请参阅[Windows Defender WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="64f5c-114">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="64f5c-115">在终结点不使用时计划扫描时，扫描不会接受 CPU 限制配置，并且将充分利用可用资源尽快完成扫描。</span><span class="sxs-lookup"><span data-stu-id="64f5c-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="64f5c-116">用于计划扫描以完成修正的 WMI</span><span class="sxs-lookup"><span data-stu-id="64f5c-116">WMI for scheduling scans to complete remediation</span></span>

<span data-ttu-id="64f5c-117">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="64f5c-117">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="64f5c-118">有关详细信息和允许的参数，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="64f5c-118">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="wmi-for-scheduling-daily-scans"></a><span data-ttu-id="64f5c-119">用于计划每日扫描的 WMI</span><span class="sxs-lookup"><span data-stu-id="64f5c-119">WMI for scheduling daily scans</span></span>

<span data-ttu-id="64f5c-120">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="64f5c-120">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="64f5c-121">有关详细信息和允许的参数，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="64f5c-121">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

