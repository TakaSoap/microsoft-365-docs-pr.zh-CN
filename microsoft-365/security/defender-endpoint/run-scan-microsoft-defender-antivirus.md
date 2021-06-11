---
title: 运行并自定义按需扫描Microsoft Defender 防病毒
description: 使用 PowerShell、Windows Management Instrumentation 运行和配置按需扫描，或者使用 Windows 安全中心 应用在终结点上单独运行和配置Windows 安全中心扫描
keywords: 扫描， 按需， dos， intune， 即时扫描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 3ee37d7220527c9032b630e02258c684b6c860b3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878798"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="99d23-104">配置并运行按需 Microsoft Defender 防病毒软件扫描</span><span class="sxs-lookup"><span data-stu-id="99d23-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="99d23-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="99d23-105">**Applies to:**</span></span>

- [<span data-ttu-id="99d23-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="99d23-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="99d23-107">可以在个别终结点上运行按需扫描。</span><span class="sxs-lookup"><span data-stu-id="99d23-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="99d23-108">这些扫描将立即启动，并且你可以定义扫描的参数，如位置或类型。</span><span class="sxs-lookup"><span data-stu-id="99d23-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span> <span data-ttu-id="99d23-109">运行扫描时，可以从以下三种类型中选择：快速扫描、完全扫描和自定义扫描。</span><span class="sxs-lookup"><span data-stu-id="99d23-109">When you run a scan, you can choose from among three types: Quick scan, full scan, and custom scan.</span></span> <span data-ttu-id="99d23-110">在大多数情况下，请使用快速扫描。</span><span class="sxs-lookup"><span data-stu-id="99d23-110">In most cases, use a quick scan.</span></span> <span data-ttu-id="99d23-111">快速扫描将查找所有可能注册为从系统启动的恶意软件的位置，例如注册表项和已知Windows文件夹。</span><span class="sxs-lookup"><span data-stu-id="99d23-111">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="99d23-112">与始终启用实时保护相结合，可在打开和关闭文件时以及用户导航到文件夹时查看文件，快速扫描可帮助提供强大的保护，防止因系统和内核级别恶意软件而启动的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="99d23-112">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="99d23-113">在大多数情况下，快速扫描已足够，是计划扫描或按需扫描的推荐选项。</span><span class="sxs-lookup"><span data-stu-id="99d23-113">In most cases, a quick scan is sufficient and is the recommended option for scheduled or on-demand scans.</span></span>  <span data-ttu-id="99d23-114">[详细了解扫描类型](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)。</span><span class="sxs-lookup"><span data-stu-id="99d23-114">[Learn more about scan types](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99d23-115">Microsoft Defender 防病毒执行本地扫描时，在[LocalSystem](/windows/win32/services/localsystem-account)帐户的上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="99d23-115">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="99d23-116">对于网络扫描，它使用设备帐户的上下文。</span><span class="sxs-lookup"><span data-stu-id="99d23-116">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="99d23-117">如果域设备帐户没有访问共享的适当权限，扫描将不起作用。</span><span class="sxs-lookup"><span data-stu-id="99d23-117">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="99d23-118">确保设备具有访问网络共享的权限。</span><span class="sxs-lookup"><span data-stu-id="99d23-118">Ensure that the device has permissions to the access network share.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="99d23-119">使用Microsoft Endpoint Manager运行扫描</span><span class="sxs-lookup"><span data-stu-id="99d23-119">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="99d23-120">转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="99d23-120">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="99d23-121">选择 **终结点安全**  >  **防病毒**。</span><span class="sxs-lookup"><span data-stu-id="99d23-121">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="99d23-122">在选项卡列表中，选择 **"Windows 10不正常的终结点"。**</span><span class="sxs-lookup"><span data-stu-id="99d23-122">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>

4. <span data-ttu-id="99d23-123">从所提供的操作列表中，选择"快速扫描" (推荐) "**完全扫描"。**</span><span class="sxs-lookup"><span data-stu-id="99d23-123">From the list of actions provided, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

<span data-ttu-id="99d23-124">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="99d23-124">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="99d23-125">有关使用 Microsoft Endpoint Manager 运行扫描的信息，请参阅[反恶意软件和防火墙任务：如何执行按需扫描](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。</span><span class="sxs-lookup"><span data-stu-id="99d23-125">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="99d23-126">使用mpcmdrun.exe命令行实用工具运行扫描</span><span class="sxs-lookup"><span data-stu-id="99d23-126">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="99d23-127">使用以下 `-scan` 参数：</span><span class="sxs-lookup"><span data-stu-id="99d23-127">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="99d23-128">有关如何使用该工具和其他参数（包括启动完全扫描或定义路径）的信息，请参阅使用[mpcmdrun.exe 命令行](command-line-arguments-microsoft-defender-antivirus.md)工具配置和管理Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="99d23-128">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="99d23-129">使用 Microsoft Intune 运行扫描</span><span class="sxs-lookup"><span data-stu-id="99d23-129">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="99d23-130">转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="99d23-130">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="99d23-131">从边栏中，**选择"设备**  >  **""** 所有设备"，然后选择你想要扫描的设备。</span><span class="sxs-lookup"><span data-stu-id="99d23-131">From the sidebar, select **Devices** > **All Devices** and choose the device you want to scan.</span></span>

3. <span data-ttu-id="99d23-132">选择 **...更多**。</span><span class="sxs-lookup"><span data-stu-id="99d23-132">Select **...More**.</span></span> <span data-ttu-id="99d23-133">从选项中，选择快速 **扫描** (推荐) 或 **完全扫描**。</span><span class="sxs-lookup"><span data-stu-id="99d23-133">From the options, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="99d23-134">使用Windows 安全中心运行扫描</span><span class="sxs-lookup"><span data-stu-id="99d23-134">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="99d23-135">有关[在个别终结点上运行Windows 安全中心](microsoft-defender-security-center-antivirus.md)的说明，请参阅在应用中运行扫描。</span><span class="sxs-lookup"><span data-stu-id="99d23-135">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="99d23-136">使用 PowerShell cmdlet 运行扫描</span><span class="sxs-lookup"><span data-stu-id="99d23-136">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="99d23-137">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="99d23-137">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="99d23-138">若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和[Defender cmdlet。](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="99d23-138">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="99d23-139">使用 Windows Management Instruction (WMI) 运行扫描</span><span class="sxs-lookup"><span data-stu-id="99d23-139">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="99d23-140">使用 [**类** 的 Start](/previous-versions/windows/desktop/defender/start-msft-mpscan) **MSFT_MpScan** 类。</span><span class="sxs-lookup"><span data-stu-id="99d23-140">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="99d23-141">有关允许哪些参数的信息，请参阅Windows Defender [WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="99d23-141">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

