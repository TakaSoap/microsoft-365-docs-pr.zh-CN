---
title: 使用 PowerShell 计划防病毒扫描
description: 使用 PowerShell 计划防病毒扫描
keywords: 快速扫描， 完全扫描， 防病毒， 计划， PowerShell
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
ms.openlocfilehash: 73ba654dd312c63651f0cf43244796e94e8ad55b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879657"
---
# <a name="schedule-antivirus-scans-using-powershell"></a><span data-ttu-id="c9b3a-104">使用 PowerShell 计划防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="c9b3a-104">Schedule antivirus scans using PowerShell</span></span>

<span data-ttu-id="c9b3a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c9b3a-105">**Applies to:**</span></span>

- [<span data-ttu-id="c9b3a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c9b3a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c9b3a-107">本文介绍如何使用 PowerShell cmdlet 配置计划扫描。</span><span class="sxs-lookup"><span data-stu-id="c9b3a-107">This article describes how to configure scheduled scans using PowerShell cmdlets.</span></span> <span data-ttu-id="c9b3a-108">若要了解有关计划扫描和扫描类型有关详细信息，请参阅配置计划的快速或完全Microsoft Defender 防病毒[扫描](schedule-antivirus-scans.md)。</span><span class="sxs-lookup"><span data-stu-id="c9b3a-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="c9b3a-109">使用 PowerShell cmdlet 计划扫描</span><span class="sxs-lookup"><span data-stu-id="c9b3a-109">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="c9b3a-110">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c9b3a-110">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="c9b3a-111">有关详细信息，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和[Defender cmdlet，](/powershell/module/defender/)了解有关如何将 PowerShell 与 Microsoft Defender 防病毒 一Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="c9b3a-111">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="c9b3a-112">在终结点不使用时用于计划扫描的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="c9b3a-112">PowerShell cmdlets for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="c9b3a-113">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c9b3a-113">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="c9b3a-114">有关详细信息，请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)和 [Defender cmdlet](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="c9b3a-114">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

> [!NOTE]
> <span data-ttu-id="c9b3a-115">在终结点不使用时计划扫描时，扫描不会接受 CPU 限制配置，并且将充分利用可用资源尽快完成扫描。</span><span class="sxs-lookup"><span data-stu-id="c9b3a-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="c9b3a-116">用于计划扫描以完成修正的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="c9b3a-116">PowerShell cmdlets for scheduling scans to complete remediation</span></span>

<span data-ttu-id="c9b3a-117">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c9b3a-117">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="c9b3a-118">请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender cmdlet](/powershell/module/defender/) ，了解有关如何通过 Microsoft Defender 防病毒软件使用 PowerShell 的信息。</span><span class="sxs-lookup"><span data-stu-id="c9b3a-118">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a><span data-ttu-id="c9b3a-119">用于计划每日扫描的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="c9b3a-119">PowerShell cmdlets for scheduling daily scans</span></span>

<span data-ttu-id="c9b3a-120">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c9b3a-120">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="c9b3a-121">若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和 Defender [cmdlet。](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="c9b3a-121">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>


