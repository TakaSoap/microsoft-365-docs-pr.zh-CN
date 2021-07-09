---
title: Microsoft Defender 防病毒
description: 了解如何管理、配置和使用 Microsoft Defender 防病毒、内置反恶意软件和防病毒保护。
keywords: Microsoft Defender 防病毒、Windows Defender、反恶意软件、SCEP、System Center 端点保护、System Center Configuration Manager、病毒、恶意软件、威胁、检测、保护、安全
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ceaf694d8b81e6b06ffe74efc4ad3d4d73471752
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322515"
---
# <a name="microsoft-defender-antivirus-in-windows"></a><span data-ttu-id="c3702-104">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="c3702-104">Microsoft Defender Antivirus in Windows</span></span>

<span data-ttu-id="c3702-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c3702-105">**Applies to:**</span></span>

- [<span data-ttu-id="c3702-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c3702-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c3702-107">Microsoft Defender 防病毒是 Microsoft Defender for Endpoint 中下一代保护的主要组件。</span><span class="sxs-lookup"><span data-stu-id="c3702-107">Microsoft Defender Antivirus is a major component of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c3702-108">此保护结合了机器学习、大数据分析、深度威胁抵御研究和 Microsoft 云基础结构来保护组织中的设备（或终结点）。</span><span class="sxs-lookup"><span data-stu-id="c3702-108">This protection brings together machine learning, big-data analysis, in-depth threat resistance research, and the Microsoft cloud infrastructure to protect devices (or endpoints) in your organization.</span></span> <span data-ttu-id="c3702-109">Microsoft Defender 防病毒内置于 Windows 中，与 Microsoft Defender for Endpoint 一起在设备上和云中提供保护。</span><span class="sxs-lookup"><span data-stu-id="c3702-109">Microsoft Defender Antivirus is built into Windows, and it works with Microsoft Defender for Endpoint to provide protection on your device and in the cloud.</span></span> 

## <a name="compatibility-with-other-antivirus-products"></a><span data-ttu-id="c3702-110">与其他防病毒软件产品的兼容性</span><span class="sxs-lookup"><span data-stu-id="c3702-110">Compatibility with other antivirus products</span></span>

<span data-ttu-id="c3702-111">如果正在设备上使用非 Microsoft 防病毒/反恶意软件产品，可能可以在使用非 Microsoft 防病毒软件解决方案的同时以被动模式运行 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="c3702-111">If you're using a non-Microsoft antivirus/antimalware product on your device, you might be able to run Microsoft Defender Antivirus in passive mode alongside the non-Microsoft antivirus solution.</span></span> <span data-ttu-id="c3702-112">具体取决于所使用的操作系统，以及设备是否已加入 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="c3702-112">It depends on the operating system used and whether your device is onboarded to Defender for Endpoint.</span></span> <span data-ttu-id="c3702-113">要了解详细信息，请参阅 [Microsoft Defender 防病毒](microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="c3702-113">To learn more, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a><span data-ttu-id="c3702-114">比较主动模式、被动模式和已禁用模式</span><span class="sxs-lookup"><span data-stu-id="c3702-114">Comparing active mode, passive mode, and disabled mode</span></span>

<span data-ttu-id="c3702-115">下表介绍了 Microsoft Defender 防病毒处于主动模式、被动模式或已禁用模式下应发生的情况。</span><span class="sxs-lookup"><span data-stu-id="c3702-115">The following table describes what to expect when Microsoft Defender Antivirus is in active mode, passive mode, or disabled.</span></span>

| <span data-ttu-id="c3702-116">模式</span><span class="sxs-lookup"><span data-stu-id="c3702-116">Mode</span></span>  | <span data-ttu-id="c3702-117">发生的情况</span><span class="sxs-lookup"><span data-stu-id="c3702-117">What happens</span></span>  |
|---------|---------|
| <span data-ttu-id="c3702-118">主动模式</span><span class="sxs-lookup"><span data-stu-id="c3702-118">Active mode</span></span> | <span data-ttu-id="c3702-119">在主动模式下，Microsoft Defender 防病毒用作设备上的主防病毒应用。</span><span class="sxs-lookup"><span data-stu-id="c3702-119">In active mode, Microsoft Defender Antivirus is used as the primary antivirus app on the device.</span></span> <span data-ttu-id="c3702-120">将扫描文件，修正威胁，并将检测到的威胁列在组织的安全报告中和 Windows 安全中心应用中。</span><span class="sxs-lookup"><span data-stu-id="c3702-120">Files are scanned, threats are remediated, and detected threats are listed in your organization's security reports and in your Windows Security app.</span></span> |
| <span data-ttu-id="c3702-121">被动模式</span><span class="sxs-lookup"><span data-stu-id="c3702-121">Passive mode</span></span> | <span data-ttu-id="c3702-122">在被动模式下，不将 Microsoft Defender 防病毒用作设备上的主防病毒应用。</span><span class="sxs-lookup"><span data-stu-id="c3702-122">In passive mode, Microsoft Defender Antivirus is not used as the primary antivirus app on the device.</span></span> <span data-ttu-id="c3702-123">将扫描文件，并报告检测到的威胁，但 Microsoft Defender 防病毒不会修正威胁。</span><span class="sxs-lookup"><span data-stu-id="c3702-123">Files are scanned, and detected threats are reported, but threats are not remediated by Microsoft Defender Antivirus.</span></span>   |
| <span data-ttu-id="c3702-124">已禁用或卸载</span><span class="sxs-lookup"><span data-stu-id="c3702-124">Disabled or uninstalled</span></span>  | <span data-ttu-id="c3702-125">在已禁用或卸载时，不使用 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="c3702-125">When disabled or uninstalled, Microsoft Defender Antivirus is not used.</span></span> <span data-ttu-id="c3702-126">不会扫描文件，并且不会修正威胁。</span><span class="sxs-lookup"><span data-stu-id="c3702-126">Files are not scanned, and threats are not remediated.</span></span> <span data-ttu-id="c3702-127">通常，我们不建议禁用或卸载 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="c3702-127">In general, we do not recommend disabling or uninstalling Microsoft Defender Antivirus.</span></span>  |

<span data-ttu-id="c3702-128">要了解详细信息，请参阅 [Microsoft Defender 防病毒](microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="c3702-128">To learn more, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a><span data-ttu-id="c3702-129">检查设备上的 Microsoft Defender 防病毒状态</span><span class="sxs-lookup"><span data-stu-id="c3702-129">Check the state of Microsoft Defender Antivirus on your device</span></span>

<span data-ttu-id="c3702-130">要检查设备上的 Microsoft Defender 防病毒状态，可以使用几种方法之一，例如 Windows 安全中心应用或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c3702-130">If you want to check the state of Microsoft Defender Antivirus on your device, you can use one of several methods, such as the Windows Security app or Windows PowerShell.</span></span>

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a><span data-ttu-id="c3702-131">使用 Windows 安全中心应用检查 Microsoft Defender 防病毒状态</span><span class="sxs-lookup"><span data-stu-id="c3702-131">Use the Windows Security app to check status of Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="c3702-132">在 Windows 设备上，选择“开始”菜单，然后开始键入 `Security`。</span><span class="sxs-lookup"><span data-stu-id="c3702-132">On your Windows device, select the Start menu, and begin typing `Security`.</span></span> <span data-ttu-id="c3702-133">然后在结果中打开 Windows 安全中心应用。</span><span class="sxs-lookup"><span data-stu-id="c3702-133">Then open the Windows Security app in the results.</span></span>

2. <span data-ttu-id="c3702-134">选择“**病毒和威胁防护**”。</span><span class="sxs-lookup"><span data-stu-id="c3702-134">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="c3702-135">在“**病毒和威胁防护设置**”下选择“**管理设置**”。</span><span class="sxs-lookup"><span data-stu-id="c3702-135">Under **Virus & threat protection settings**, choose **Manage settings**.</span></span>

<span data-ttu-id="c3702-136">设置页面上将显示防病毒/反恶意软件解决方案的名称。</span><span class="sxs-lookup"><span data-stu-id="c3702-136">You'll see the name of your antivirus/antimalware solution on the settings page.</span></span>

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a><span data-ttu-id="c3702-137">使用 PowerShell 检查 Microsoft Defender 防病毒状态</span><span class="sxs-lookup"><span data-stu-id="c3702-137">Use PowerShell to check status of Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="c3702-138">选择“开始”菜单，然后开始键入 `PowerShell`。</span><span class="sxs-lookup"><span data-stu-id="c3702-138">Select the Start menu, and begin typing `PowerShell`.</span></span> <span data-ttu-id="c3702-139">然后在结果中打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c3702-139">Then open Windows PowerShell in the results.</span></span>

2. <span data-ttu-id="c3702-140">类型 `Get-MpComputerStatus`。</span><span class="sxs-lookup"><span data-stu-id="c3702-140">Type `Get-MpComputerStatus`.</span></span>

3. <span data-ttu-id="c3702-141">在结果列表中，查看 **AMRunningMode** 行。</span><span class="sxs-lookup"><span data-stu-id="c3702-141">In the list of results, look at the **AMRunningMode** row.</span></span>

   - <span data-ttu-id="c3702-142">**正常** 表示 Microsoft Defender 防病毒在主动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="c3702-142">**Normal** means Microsoft Defender Antivirus is running in active mode.</span></span>
   - <span data-ttu-id="c3702-143">**被动模式** 表示 Microsoft Defender 防病毒正在运行，但不是设备上的主要防病毒/反恶意软件产品。</span><span class="sxs-lookup"><span data-stu-id="c3702-143">**Passive mode** means Microsoft Defender Antivirus running, but is not the primary antivirus/antimalware product on your device.</span></span>
   - <span data-ttu-id="c3702-144">**EDR 阻止模式** 表示 Microsoft Defender 防病毒正在运行，并且已启用 Microsoft Defender for Endpoint 中名为“阻止模式下的 EDR”的功能。</span><span class="sxs-lookup"><span data-stu-id="c3702-144">**EDR Block Mode** means Microsoft Defender Antivirus is running and a capability in Microsoft Defender for Endpoint that is called "EDR in block mode" is enabled.</span></span> <span data-ttu-id="c3702-145">（请参阅 [阻止模式下的终结点检测和响应 (EDR)](edr-in-block-mode.md)。）</span><span class="sxs-lookup"><span data-stu-id="c3702-145">(See [Endpoint detection and response (EDR) in block mode](edr-in-block-mode.md).)</span></span>
   - <span data-ttu-id="c3702-146">**SxS 被动模式** 表示 Microsoft Defender 防病毒与其他防病毒/反恶意软件产品一起运行，但处于被动模式下，并且设备未加入 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="c3702-146">**SxS Passive Mode** means Microsoft Defender Antivirus is running in passive mode alongside another antivirus/antimalware product, and your device is not onboarded to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c3702-147">在这种情况下，Microsoft Defender 防病毒使用有限的定期扫描。</span><span class="sxs-lookup"><span data-stu-id="c3702-147">In this case, limited periodic scanning is used for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="c3702-148">要了解详细信息，请参阅 [在 Microsoft Defender 防病毒中使用有限的定期扫描](limited-periodic-scanning-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="c3702-148">To learn more, see [Use limited periodic scanning in Microsoft Defender Antivirus](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="c3702-149">要了解 Get-MpComputerStatus PowerShell cmdlet 的详细信息，请参阅参考文章 [get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。</span><span class="sxs-lookup"><span data-stu-id="c3702-149">To learn more about the Get-MpComputerStatus PowerShell cmdlet, see the reference article [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).</span></span>

## <a name="get-your-antivirusantimalware-platform-updates"></a><span data-ttu-id="c3702-150">获取防病毒/反恶意软件平台更新</span><span class="sxs-lookup"><span data-stu-id="c3702-150">Get your antivirus/antimalware platform updates</span></span>

<span data-ttu-id="c3702-151">请务必确保 Microsoft Defender 防病毒或任何防病毒/反恶意软件解决方案保持最新。</span><span class="sxs-lookup"><span data-stu-id="c3702-151">It's important to keep Microsoft Defender Antivirus, or any antivirus/antimalware solution, up to date.</span></span> <span data-ttu-id="c3702-152">Microsoft 定期发布更新，以帮助确保你的设备具有最新技术来防范新的恶意软件和攻击技术。</span><span class="sxs-lookup"><span data-stu-id="c3702-152">Microsoft releases regular updates to help ensure that your devices have the latest technology to protect against new malware and attack techniques.</span></span> <span data-ttu-id="c3702-153">要了解详细信息，请参阅 [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="c3702-153">To learn more, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span> 

## <a name="see-also"></a><span data-ttu-id="c3702-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3702-154">See also</span></span>

- [<span data-ttu-id="c3702-155">Windows Server 上的 Microsoft Defender 防病毒软件</span><span class="sxs-lookup"><span data-stu-id="c3702-155">Microsoft Defender Antivirus on Windows Server</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="c3702-156">Microsoft Defender 防病毒管理和配置</span><span class="sxs-lookup"><span data-stu-id="c3702-156">Microsoft Defender Antivirus management and configuration</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c3702-157">评估 Microsoft Defender 防病毒保护</span><span class="sxs-lookup"><span data-stu-id="c3702-157">Evaluate Microsoft Defender Antivirus protection</span></span>](evaluate-microsoft-defender-antivirus.md)
