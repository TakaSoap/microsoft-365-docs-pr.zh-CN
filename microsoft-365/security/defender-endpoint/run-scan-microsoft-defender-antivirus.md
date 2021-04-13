---
title: 在 Microsoft Defender AV 中运行和自定义按需扫描
description: 使用 PowerShell、Windows Management Instrumentation 运行和配置按需扫描，或者使用 Windows 安全中心应用在终结点上单独运行和配置扫描
keywords: 扫描， 按需， dos， intune， 即时扫描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2f60bdb0bbd8b87895547e608b5c3c92414ea834
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689972"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="55d46-104">配置并运行按需 Microsoft Defender 防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="55d46-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55d46-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="55d46-105">**Applies to:**</span></span>

- [<span data-ttu-id="55d46-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="55d46-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="55d46-107">可以在个别终结点上运行按需扫描。</span><span class="sxs-lookup"><span data-stu-id="55d46-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="55d46-108">这些扫描将立即启动，并且你可以定义扫描的参数，如位置或类型。</span><span class="sxs-lookup"><span data-stu-id="55d46-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="55d46-109">快速扫描与完全扫描</span><span class="sxs-lookup"><span data-stu-id="55d46-109">Quick scan versus full scan</span></span>

<span data-ttu-id="55d46-110">快速扫描将查找所有可能注册为从系统启动的恶意软件的位置，例如注册表项和已知的 Windows 启动文件夹。</span><span class="sxs-lookup"><span data-stu-id="55d46-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55d46-111">执行本地扫描时，Microsoft Defender 防病毒在 [LocalSystem](/windows/win32/services/localsystem-account) 帐户的上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="55d46-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="55d46-112">对于网络扫描，它使用设备帐户的上下文。</span><span class="sxs-lookup"><span data-stu-id="55d46-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="55d46-113">如果域设备帐户没有访问共享的适当权限，扫描将不起作用。</span><span class="sxs-lookup"><span data-stu-id="55d46-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="55d46-114">确保设备具有访问网络共享的权限。</span><span class="sxs-lookup"><span data-stu-id="55d46-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="55d46-115">与 [始终启用](configure-real-time-protection-microsoft-defender-antivirus.md)实时保护功能（在打开和关闭文件时以及用户导航到文件夹时查看文件）相结合，快速扫描可帮助针对以系统开头的恶意软件和内核级恶意软件提供强大的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="55d46-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md)--which reviews files when they're opened and closed, and whenever a user navigates to a folder--a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="55d46-116">在大多数情况下，快速扫描足以找到实时保护未选取的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="55d46-116">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="55d46-117">完全扫描在报告恶意软件威胁的终结点上可能很有用。</span><span class="sxs-lookup"><span data-stu-id="55d46-117">A full scan can be useful on endpoints that have reported a malware threat.</span></span> <span data-ttu-id="55d46-118">扫描可以标识是否有需要更彻底清理的非活动组件。</span><span class="sxs-lookup"><span data-stu-id="55d46-118">The scan can identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="55d46-119">如果组织正在运行按需扫描，则这是理想情况。</span><span class="sxs-lookup"><span data-stu-id="55d46-119">This is  ideal if your organization is running on-demand scans.</span></span>

> [!NOTE]
> <span data-ttu-id="55d46-120">默认情况下，快速扫描在装载的可移动设备（如 USB 驱动器）上运行。</span><span class="sxs-lookup"><span data-stu-id="55d46-120">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="55d46-121">使用 Microsoft Endpoint Manager 运行扫描</span><span class="sxs-lookup"><span data-stu-id="55d46-121">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="55d46-122">转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="55d46-122">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="55d46-123">选择 **终结点安全**  >  **防病毒**。</span><span class="sxs-lookup"><span data-stu-id="55d46-123">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="55d46-124">在选项卡列表中，选择 **"Windows 10 不正常终结点"。**</span><span class="sxs-lookup"><span data-stu-id="55d46-124">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="55d46-125">从所提供的操作列表中，选择 **快速扫描** 或 **完全扫描**。</span><span class="sxs-lookup"><span data-stu-id="55d46-125">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="55d46-126">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="55d46-126">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="55d46-127">有关使用 Microsoft Endpoint Manager 运行扫描的信息，请参阅 [反恶意软件和防火墙任务：如何执行按需扫描](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。</span><span class="sxs-lookup"><span data-stu-id="55d46-127">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="55d46-128">使用mpcmdrun.exe命令行实用工具运行扫描</span><span class="sxs-lookup"><span data-stu-id="55d46-128">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="55d46-129">使用以下 `-scan` 参数：</span><span class="sxs-lookup"><span data-stu-id="55d46-129">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="55d46-130">有关如何使用该工具和其他参数（包括启动完全扫描或定义路径）的信息，请参阅使用 mpcmdrun.exe 命令行工具配置 [和管理 Microsoft Defender 防病毒](command-line-arguments-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="55d46-130">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="55d46-131">使用 Microsoft Intune 运行扫描</span><span class="sxs-lookup"><span data-stu-id="55d46-131">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="55d46-132">转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="55d46-132">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="55d46-133">从边栏中， **选择">所有设备"，** 然后选择要扫描的设备。</span><span class="sxs-lookup"><span data-stu-id="55d46-133">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="55d46-134">选择 **...更多**。</span><span class="sxs-lookup"><span data-stu-id="55d46-134">Select **...More**.</span></span> <span data-ttu-id="55d46-135">从选项中，选择 **"快速扫描"或**"**完全扫描"。**</span><span class="sxs-lookup"><span data-stu-id="55d46-135">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="55d46-136">使用 Windows 安全应用运行扫描</span><span class="sxs-lookup"><span data-stu-id="55d46-136">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="55d46-137">有关 [在个别终结点上运行](microsoft-defender-security-center-antivirus.md) 扫描的说明，请参阅在 Windows 安全应用中运行扫描。</span><span class="sxs-lookup"><span data-stu-id="55d46-137">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="55d46-138">使用 PowerShell cmdlet 运行扫描</span><span class="sxs-lookup"><span data-stu-id="55d46-138">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="55d46-139">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="55d46-139">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="55d46-140">若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒和[Defender cmdlet。](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="55d46-140">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="55d46-141">使用 Windows Management Instruction (WMI) 运行扫描</span><span class="sxs-lookup"><span data-stu-id="55d46-141">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="55d46-142">使用 [**类** 的 Start](/previous-versions/windows/desktop/defender/start-msft-mpscan) **MSFT_MpScan** 类。</span><span class="sxs-lookup"><span data-stu-id="55d46-142">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="55d46-143">有关允许哪些参数的信息，请参阅Windows Defender [WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="55d46-143">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="55d46-144">相关文章</span><span class="sxs-lookup"><span data-stu-id="55d46-144">Related articles</span></span>

- [<span data-ttu-id="55d46-145">配置 Microsoft Defender 防病毒扫描选项</span><span class="sxs-lookup"><span data-stu-id="55d46-145">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="55d46-146">配置计划的 Microsoft Defender 防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="55d46-146">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="55d46-147">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="55d46-147">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)