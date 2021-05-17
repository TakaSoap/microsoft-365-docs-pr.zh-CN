---
title: Microsoft Defender 脱机版Windows 10
description: 你可以直接从Microsoft Defender 脱机版直接使用Windows Defender 防病毒应用。 还可以管理如何在网络中部署它。
keywords: 扫描， defender， 脱机
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
ms.openlocfilehash: a25a2ec513cd7c25f9f6ddf3d5e328928837bf2d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275140"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a><span data-ttu-id="a4ddb-105">运行并查看 Microsoft Defender 脱机扫描的结果</span><span class="sxs-lookup"><span data-stu-id="a4ddb-105">Run and review the results of a Microsoft Defender Offline scan</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a4ddb-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a4ddb-106">**Applies to:**</span></span>

- [<span data-ttu-id="a4ddb-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a4ddb-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a4ddb-108">Microsoft Defender 脱机版是一种反恶意软件扫描工具，允许你从受信任的环境启动和运行扫描。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-108">Microsoft Defender Offline is an antimalware scanning tool that lets you boot and run a scan from a trusted environment.</span></span> <span data-ttu-id="a4ddb-109">扫描从正常的 Windows 内核外部运行，因此它可以定位尝试绕过 Windows shell 的恶意软件，例如感染或覆盖主启动记录 (MBR) 的病毒和 rootkit。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-109">The scan runs from outside the normal Windows kernel so it can target malware that attempts to bypass the Windows shell, such as viruses and rootkits that infect or overwrite the master boot record (MBR).</span></span>

<span data-ttu-id="a4ddb-110">如果您怀疑Microsoft Defender 脱机版恶意软件感染，或者希望确认恶意软件爆发后对终结点进行彻底清理，您可以使用该终结点。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-110">You can use Microsoft Defender Offline if you suspect a malware infection, or you want to confirm a thorough clean of the endpoint after a malware outbreak.</span></span>

<span data-ttu-id="a4ddb-111">在Windows 10中，Microsoft Defender 脱机版直接从应用单击一次即可Windows 安全中心[运行](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-111">In Windows 10, Microsoft Defender Offline can be run with one click directly from the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="a4ddb-112">在早期版本的 Windows，用户必须Microsoft Defender 脱机版可启动媒体、重新启动终结点和加载可启动媒体。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-112">In previous versions of Windows, a user had to install Microsoft Defender Offline to bootable media, restart the endpoint, and load the bootable media.</span></span>

## <a name="prerequisites-and-requirements"></a><span data-ttu-id="a4ddb-113">先决条件和要求</span><span class="sxs-lookup"><span data-stu-id="a4ddb-113">prerequisites and requirements</span></span>

<span data-ttu-id="a4ddb-114">Microsoft Defender 脱机版中Windows 10具有相同的硬件要求Windows 10。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-114">Microsoft Defender Offline in Windows 10 has the same hardware requirements as Windows 10.</span></span> 

<span data-ttu-id="a4ddb-115">有关这些要求Windows 10，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a4ddb-115">For more information about Windows 10 requirements, see the following topics:</span></span>

- [<span data-ttu-id="a4ddb-116">最低硬件要求</span><span class="sxs-lookup"><span data-stu-id="a4ddb-116">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [<span data-ttu-id="a4ddb-117">硬件组件准则</span><span class="sxs-lookup"><span data-stu-id="a4ddb-117">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> <span data-ttu-id="a4ddb-118">Microsoft Defender 脱机版处理器的计算机或 ARM 服务器库存Windows不支持此配置。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-118">Microsoft Defender Offline is not supported on machines with ARM processors, or on Windows Server Stock Keeping Units.</span></span>

<span data-ttu-id="a4ddb-119">若要Microsoft Defender 脱机版终结点运行应用程序，用户必须使用管理员权限登录。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-119">To run Microsoft Defender Offline from the endpoint, the user must be logged in with administrator privileges.</span></span>
 
## <a name="microsoft-defender-offline-updates"></a><span data-ttu-id="a4ddb-120">Microsoft Defender 脱机版更新</span><span class="sxs-lookup"><span data-stu-id="a4ddb-120">Microsoft Defender Offline updates</span></span>

<span data-ttu-id="a4ddb-121">Microsoft Defender 脱机版使用终结点上提供的最新保护更新;每当更新时，Windows Defender 防病毒更新。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-121">Microsoft Defender Offline uses the most recent protection updates available on the endpoint; it's updated whenever Windows Defender Antivirus is updated.</span></span> 

> [!NOTE]
> <span data-ttu-id="a4ddb-122">在运行脱机扫描之前，应尝试更新 Microsoft Defender AV 保护。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-122">Before running an offline scan, you should attempt to update Microsoft Defender AV protection.</span></span> <span data-ttu-id="a4ddb-123">可以使用组策略强制更新，或者通常将更新部署到终结点，也可以手动下载并安装来自 Microsoft 恶意软件防护中心[的最新保护更新](https://www.microsoft.com/security/portal/definitions/adl.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-123">You can either force an update with Group Policy or however you normally deploy updates to endpoints, or you can manually download and install the latest protection updates from the [Microsoft Malware Protection Center](https://www.microsoft.com/security/portal/definitions/adl.aspx).</span></span>

<span data-ttu-id="a4ddb-124">有关详细信息[，请参阅](manage-protection-updates-microsoft-defender-antivirus.md)Microsoft Defender 防病毒安全智能更新主题。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-124">See the [Manage Microsoft Defender Antivirus Security intelligence  updates](manage-protection-updates-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="usage-scenarios"></a><span data-ttu-id="a4ddb-125">使用方案</span><span class="sxs-lookup"><span data-stu-id="a4ddb-125">Usage scenarios</span></span>

<span data-ttu-id="a4ddb-126">在Windows 10版本 1607 中，可以手动强制脱机扫描。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-126">In Windows 10, version 1607, you can manually force an offline scan.</span></span> <span data-ttu-id="a4ddb-127">或者，Windows Defender确定Microsoft Defender 脱机版需要运行，它将在终结点上提示用户。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-127">Alternatively, if Windows Defender determines that Microsoft Defender Offline needs to run, it will prompt the user on the endpoint.</span></span> 

<span data-ttu-id="a4ddb-128">如果使用脱机扫描来管理终结点，Microsoft Endpoint Manager也会在客户端中显示需要执行脱机扫描。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-128">The need to perform an offline scan will also be revealed in Microsoft Endpoint Manager if you're using it to manage your endpoints.</span></span>

<span data-ttu-id="a4ddb-129">该提示可以通过通知发生，类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="a4ddb-129">The prompt can occur via a notification, similar to the following:</span></span>

![Windows运行应用程序的要求的Microsoft Defender 脱机版](images/defender/notification.png)

<span data-ttu-id="a4ddb-131">用户还将在客户端Windows Defender通知。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-131">The user will also be notified within the Windows Defender client.</span></span>

<span data-ttu-id="a4ddb-132">在 Configuration Manager 中，可以通过导航到"监视">"安全>状态"> Endpoint Protection"状态> System Center Endpoint Protection **终结点的状态**。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-132">In Configuration Manager, you can identify the status of endpoints by navigating to **Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**.</span></span> 

<span data-ttu-id="a4ddb-133">Microsoft Defender 脱机版扫描在"恶意软件修正状态"**下指示** 为 **"需要脱机扫描"。**</span><span class="sxs-lookup"><span data-stu-id="a4ddb-133">Microsoft Defender Offline scans are indicated under **Malware remediation status** as **Offline scan required**.</span></span>

![Microsoft Endpoint Manager需要Microsoft Defender 脱机版扫描的行](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a><span data-ttu-id="a4ddb-135">配置通知</span><span class="sxs-lookup"><span data-stu-id="a4ddb-135">Configure notifications</span></span>

<span data-ttu-id="a4ddb-136">Microsoft Defender 脱机版通知与其他 Microsoft Defender AV 通知在同一策略设置中配置。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-136">Microsoft Defender Offline notifications are configured in the same policy setting as other Microsoft Defender AV notifications.</span></span>

<span data-ttu-id="a4ddb-137">有关终结点中的通知Windows Defender，请参阅配置[终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)主题。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-137">For more information about notifications in Windows Defender, see the [Configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md) topic.</span></span>

## <a name="run-a-scan"></a><span data-ttu-id="a4ddb-138">运行扫描</span><span class="sxs-lookup"><span data-stu-id="a4ddb-138">Run a scan</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a4ddb-139">使用前Microsoft Defender 脱机版，请确保保存所有文件并关闭正在运行的程序。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-139">Before you use Microsoft Defender Offline, make sure you save any files and shut down running programs.</span></span> <span data-ttu-id="a4ddb-140">运行Microsoft Defender 脱机版扫描需要大约 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-140">The Microsoft Defender Offline scan takes about 15 minutes to run.</span></span> <span data-ttu-id="a4ddb-141">扫描完成后，它将重新启动终结点。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-141">It will restart the endpoint when the scan is complete.</span></span> <span data-ttu-id="a4ddb-142">扫描在常规运行环境Windows执行。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-142">The scan is performed outside of the usual Windows operating environment.</span></span> <span data-ttu-id="a4ddb-143">用户界面将显示不同于由用户执行的正常Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-143">The user interface will appear different to a normal scan performed by Windows Defender.</span></span> <span data-ttu-id="a4ddb-144">扫描完成后，终结点将重新启动，Windows正常加载。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-144">After the scan is completed, the endpoint will be restarted and Windows will load normally.</span></span>

<span data-ttu-id="a4ddb-145">可以使用以下Microsoft Defender 脱机版运行自动扫描：</span><span class="sxs-lookup"><span data-stu-id="a4ddb-145">You can run a Microsoft Defender Offline scan with the following:</span></span>

- <span data-ttu-id="a4ddb-146">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4ddb-146">PowerShell</span></span>
- <span data-ttu-id="a4ddb-147">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="a4ddb-147">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="a4ddb-148">应用程序Windows 安全中心应用程序</span><span class="sxs-lookup"><span data-stu-id="a4ddb-148">The Windows Security app</span></span>



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a><span data-ttu-id="a4ddb-149">使用 PowerShell cmdlet 运行脱机扫描</span><span class="sxs-lookup"><span data-stu-id="a4ddb-149">Use PowerShell cmdlets to run an offline scan</span></span>

<span data-ttu-id="a4ddb-150">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a4ddb-150">Use the following cmdlets:</span></span>

```PowerShell
Start-MpWDOScan
```

<span data-ttu-id="a4ddb-151">请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender cmdlet](/powershell/module/defender/) ，了解有关如何通过 Microsoft Defender 防病毒软件使用 PowerShell 的信息。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-151">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a><span data-ttu-id="a4ddb-152">使用 Windows Management Instruction (WMI) 运行脱机扫描</span><span class="sxs-lookup"><span data-stu-id="a4ddb-152">Use Windows Management Instruction (WMI) to run an offline scan</span></span>

<span data-ttu-id="a4ddb-153">使用 [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 类运行脱机扫描。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-153">Use the [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class to run an offline scan.</span></span>

<span data-ttu-id="a4ddb-154">以下 WMI 脚本代码段将立即运行Microsoft Defender 脱机版扫描，这会使终结点重新启动、运行脱机扫描，然后重新启动并启动到 Windows。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-154">The following WMI script snippet will immediately run a Microsoft Defender Offline scan, which will cause the endpoint to restart, run the offline scan, and then restart and boot into Windows.</span></span>

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

<span data-ttu-id="a4ddb-155">有关详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="a4ddb-155">See the following for more information:</span></span>
- [<span data-ttu-id="a4ddb-156">Windows DefenderWMIv2 API</span><span class="sxs-lookup"><span data-stu-id="a4ddb-156">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a><span data-ttu-id="a4ddb-157">使用 Windows Defender 安全应用运行脱机扫描</span><span class="sxs-lookup"><span data-stu-id="a4ddb-157">Use the Windows Defender Security app to run an offline scan</span></span>

1. <span data-ttu-id="a4ddb-158">通过Windows 安全中心任务栏中的防护图标或搜索 Defender 的"开始"菜单打开"开始 **"菜单。**</span><span class="sxs-lookup"><span data-stu-id="a4ddb-158">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="a4ddb-159">单击病毒&**威胁** 防护磁贴 (左侧菜单栏上的防护图标或) 高级 **扫描标签：**</span><span class="sxs-lookup"><span data-stu-id="a4ddb-159">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Advanced scan** label:</span></span>
    
3. <span data-ttu-id="a4ddb-160">选择 **Microsoft Defender 脱机版扫描"，** 然后单击"**立即扫描"。**</span><span class="sxs-lookup"><span data-stu-id="a4ddb-160">Select **Microsoft Defender Offline scan** and click **Scan now**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a4ddb-161">在 Windows 10 版本 1607 中，脱机扫描可以在 **Windows 设置** Update & 安全Windows Defender下运行，也可以从  >    >  Windows Defender 客户端运行。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-161">In Windows 10, version 1607, the offline scan could be run from under **Windows Settings** > **Update & security** > **Windows Defender** or from the Windows Defender client.</span></span>


## <a name="review-scan-results"></a><span data-ttu-id="a4ddb-162">查看扫描结果</span><span class="sxs-lookup"><span data-stu-id="a4ddb-162">Review scan results</span></span>

<span data-ttu-id="a4ddb-163">Microsoft Defender 脱机版扫描结果将列在应用扫描[Windows 安全中心部分中](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="a4ddb-163">Microsoft Defender Offline scan results will be listed in the [Scan history section of the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> 


## <a name="related-articles"></a><span data-ttu-id="a4ddb-164">相关文章</span><span class="sxs-lookup"><span data-stu-id="a4ddb-164">Related articles</span></span>

- [<span data-ttu-id="a4ddb-165">自定义、启动和查看扫描和修正的结果</span><span class="sxs-lookup"><span data-stu-id="a4ddb-165">Customize, initiate, and review the results of scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a4ddb-166">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="a4ddb-166">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)