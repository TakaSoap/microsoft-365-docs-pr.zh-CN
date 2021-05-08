---
title: 使用Microsoft Defender防病毒功能阻止可能有害的应用程序
description: 启用可能会不需要的应用程序 （PUA） 防病毒软件，以阻止不需要的软件，如 adware。
keywords: pua，启用，不需要的软件，不需要的应用，adware，浏览器工具栏，检测，阻止，Microsoft Defender 防病毒软件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: fbd897b025db2317dd1c213e5adf5d64ba88e7ac
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275236"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="964b3-104">检测并阻止可能不需要的应用程序</span><span class="sxs-lookup"><span data-stu-id="964b3-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="964b3-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="964b3-105">**Applies to:**</span></span>

- [<span data-ttu-id="964b3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="964b3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="964b3-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="964b3-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

<span data-ttu-id="964b3-108">可能不需要的应用程序 (PUA) 用来指代一类软件，它们会导致计算机运行缓慢、显示意外广告，最糟的是，它还会安装其他意外的或不需要的软件。</span><span class="sxs-lookup"><span data-stu-id="964b3-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="964b3-109">PUA 不是病毒、恶意软件或其他威胁，但它可能会对终结点进行一些操作，对其性能或使用产生负面的影响。</span><span class="sxs-lookup"><span data-stu-id="964b3-109">PUA is not considered a virus, malware, or other type of threat, but it might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="964b3-110">*PUA* 这个术语也可以指那些由于某些不当行为，被 Microsoft Defender for Endpoint 评估为具有较差信誉的应用程序。</span><span class="sxs-lookup"><span data-stu-id="964b3-110">The term *PUA* can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="964b3-111">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="964b3-111">Here are some examples:</span></span>

- <span data-ttu-id="964b3-112">显示广告或促销的 **广告软件**，包括将广告插入网页的软件。</span><span class="sxs-lookup"><span data-stu-id="964b3-112">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="964b3-113">**捆绑软件** ，用于安装不由同一实体进行数字签名的其他软件。</span><span class="sxs-lookup"><span data-stu-id="964b3-113">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="964b3-114">此外，提出安装其他软件的软件属于 PUA。</span><span class="sxs-lookup"><span data-stu-id="964b3-114">Also, software that offers to install other software that qualifies as PUA.</span></span>
- <span data-ttu-id="964b3-115">积极尝试逃避安全产品检测的 **规避软件**，包括在存在安全产品的情况下行为不同的软件。</span><span class="sxs-lookup"><span data-stu-id="964b3-115">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="964b3-116">有关更多示例和讨论我们用于标记应用程序以引起对安全功能特别关注的条件，请参阅 [Microsoft 如何识别恶意软件和可能不需要的应用程序](/windows/security/threat-protection/intelligence/criteria)。</span><span class="sxs-lookup"><span data-stu-id="964b3-116">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="964b3-117">可能不需要的应用程序会增加网络受到实际恶意软件感染的风险，使恶意软件感染更加难以识别，或浪费 IT 资源清理它们。</span><span class="sxs-lookup"><span data-stu-id="964b3-117">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="964b3-118">Windows 10、Windows Server 2019 和 Windows Server 2016 支持 PUA 保护。</span><span class="sxs-lookup"><span data-stu-id="964b3-118">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="964b3-119">在 Windows 10（版本 2004 和更高版本）中，Microsoft Defender 防病毒软件会默认为企业 (E5) 设备阻止 PUA 应用。</span><span class="sxs-lookup"><span data-stu-id="964b3-119">In Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA for Enterprise (E5) devices by default.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="964b3-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="964b3-120">Microsoft Edge</span></span>

<span data-ttu-id="964b3-121">新的 [Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)（基于 Chromium） 会阻止潜在的不需要的应用程序下载和关联的资源 URL。</span><span class="sxs-lookup"><span data-stu-id="964b3-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="964b3-122">此功能通过[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)提供。</span><span class="sxs-lookup"><span data-stu-id="964b3-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="964b3-123">在基于 Chromium 的 Microsoft Edge 中启用 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="964b3-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="964b3-124">虽然默认情况下会关闭 Microsoft Edge 中可能不需要的应用程序保护（基于 Chromium 的版本 80.0.361.50），但可在浏览器中轻松启用。</span><span class="sxs-lookup"><span data-stu-id="964b3-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="964b3-125">在 Microsoft Edge 浏览器中，选择省略号，然后选择“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="964b3-125">In your Edge browser, select the ellipses, and then choose **Settings**.</span></span>

2. <span data-ttu-id="964b3-126">选择 **隐私、搜索和服务**。</span><span class="sxs-lookup"><span data-stu-id="964b3-126">Select **Privacy, search, and services**.</span></span>

3. <span data-ttu-id="964b3-127">在" **安全** 部分， **阻止可能不需要的应用**。</span><span class="sxs-lookup"><span data-stu-id="964b3-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="964b3-128">如果运行的是 Microsoft Edge（基于 Chromium），您可以通过在我们的 [Microsoft Defender SmartScreen 演示页面之一测试并测试 PUA 保护的 URL 阻止功能](https://demo.smartscreen.msft.net/)。</span><span class="sxs-lookup"><span data-stu-id="964b3-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="block-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="964b3-129">使用 Microsoft Defender SmartScreen 阻止 URL</span><span class="sxs-lookup"><span data-stu-id="964b3-129">Block URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="964b3-130">在启用 PUA 保护的基于 Chromium 的 Microsoft Edge 中，Microsoft Defender SmartScreen 可保护用户免遭 PUA 关联的 URL 的影响。</span><span class="sxs-lookup"><span data-stu-id="964b3-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="964b3-131">安全管理员可 [Microsoft Edge](/DeployEdge/configure-microsoft-edge) Microsoft Defender SmartScreen 如何协同工作来保护用户组免遭 PUA 关联的 URL 的威胁。</span><span class="sxs-lookup"><span data-stu-id="964b3-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="964b3-132">可显式 [Microsoft Defender SmartScreen](/DeployEdge/microsoft-edge-policies#smartscreen-settings) 多个组策略设置，包括 [PUA 策略设置的](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)。</span><span class="sxs-lookup"><span data-stu-id="964b3-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="964b3-133">此外，管理员可 [将 Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) 配置成整体，使用组策略设置打开或关闭 Microsoft Defender SmartScreen。</span><span class="sxs-lookup"><span data-stu-id="964b3-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="964b3-134">虽然 Microsoft Defender for Endpoint 基于 Microsoft 托管的数据集具有自己的阻止列表，但它也可以基于自己的威胁智能自定义此列表。</span><span class="sxs-lookup"><span data-stu-id="964b3-134">Although Microsoft Defender for Endpoint has its own blocklist based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="964b3-135">若要在 Microsoft Defender for Endpoint 中“[创建和管理指示器](manage-indicators.md)”，Microsoft Defender SmartScreen 将应用新设置。</span><span class="sxs-lookup"><span data-stu-id="964b3-135">If you [create and manage indicators](manage-indicators.md) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus-and-pua-protection"></a><span data-ttu-id="964b3-136">Microsoft Defender 防病毒和 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="964b3-136">Microsoft Defender Antivirus and PUA protection</span></span>

<span data-ttu-id="964b3-137">Microsoft Defender 防病毒软件中可能不需要的应用程序 (PUA) 保护功能可检测和阻止网络中终结点上的 PUA。</span><span class="sxs-lookup"><span data-stu-id="964b3-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUA on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="964b3-138">Windows 10、Windows Server 2019 和 Windows Server 2016 中提供此功能。</span><span class="sxs-lookup"><span data-stu-id="964b3-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="964b3-139">Microsoft Defender 防病毒软件阻止检测到 PUA 文件，以及尝试下载、移动、运行或安装它们的任何尝试。</span><span class="sxs-lookup"><span data-stu-id="964b3-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="964b3-140">阻止的 PUA 文件随即移动到隔离区。</span><span class="sxs-lookup"><span data-stu-id="964b3-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="964b3-141">在终结点上检测到 PUA 文件时，Microsoft Defender 防病毒软件会以与其他威胁检测相同的格式向用户发送通知（[除非通知已禁用](configure-notifications-microsoft-defender-antivirus.md)）。</span><span class="sxs-lookup"><span data-stu-id="964b3-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="964b3-142">以通知的字体作为 `PUA:` 以指示其内容。</span><span class="sxs-lookup"><span data-stu-id="964b3-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="964b3-143">该通知显示在 Windows 安全应用 [中正常出现的隔离](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="964b3-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="964b3-144">在 Microsoft Defender 防病毒软件中配置 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="964b3-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="964b3-145">您可以使用[Microsoft Intune](/mem/intune/protect/device-protect)，[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection)，[组策略](/azure/active-directory-domain-services/manage-group-policy)或通过[PowerShell cmdlet](/powershell/module/defender/?preserve-view=true&view=win10-ps)启用PUA保护。</span><span class="sxs-lookup"><span data-stu-id="964b3-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="964b3-146">还可在审核模式下使用 PUA 保护检测可能不需要的应用程序，同时不阻止它们。</span><span class="sxs-lookup"><span data-stu-id="964b3-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="964b3-147">检测将捕获到 Windows 事件日志中。</span><span class="sxs-lookup"><span data-stu-id="964b3-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="964b3-148">请访问 microsoft Defender for Endpoint 演示网站 [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) 确认该功能是否正常工作，并查看其操作结果。</span><span class="sxs-lookup"><span data-stu-id="964b3-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="964b3-149">如果你的公司正在进行内部软件安全合规性检查，并且希望避免出现任何误报，则审核模式下的 PUA 保护十分有用。</span><span class="sxs-lookup"><span data-stu-id="964b3-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="964b3-150">使用 Intune 配置 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="964b3-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="964b3-151">有关详细信息，请参阅[Microsoft Intune](/intune/device-restrictions-configure) 和 [Microsoft Defender Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) Windows 10 防病毒设备限制设置。</span><span class="sxs-lookup"><span data-stu-id="964b3-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="964b3-152">使用配置管理器配置 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="964b3-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="964b3-153">在 Microsoft Endpoint Manager （Current Branch） 中默认启用 PUA 保护。</span><span class="sxs-lookup"><span data-stu-id="964b3-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="964b3-154">请参阅 [创建和部署反恶意软件策略的信息：计划扫描设置](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) 配置 Microsoft Endpoint Manager （Current Branch） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="964b3-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="964b3-155">对于 System Center 2012 Configuration Manager，请参阅 [Configuration Manager 管理中心中如何部署用于终结点保护的潜在的不需要的应用程序保护](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)。</span><span class="sxs-lookup"><span data-stu-id="964b3-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="964b3-156">Windows 事件查看器中报告称 Microsoft Defender 防病毒软件阻止的 PUA 事件，而不是 Microsoft Endpoint Configuration Manager 中。</span><span class="sxs-lookup"><span data-stu-id="964b3-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="964b3-157">使用组策略配置 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="964b3-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="964b3-158">下载并安装 [Windows 10 2020 年 10 月更新 （20H2） 管理模板 （.admx）](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="964b3-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="964b3-159">在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="964b3-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="964b3-160">选择要配置的组策略对象，然后选择" **策略**。</span><span class="sxs-lookup"><span data-stu-id="964b3-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="964b3-161">在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="964b3-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="964b3-162">展开树，从 Microsoft Defender **Windows Components** > **Microsoft Defender 防病毒软件**。</span><span class="sxs-lookup"><span data-stu-id="964b3-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="964b3-163">双击配置 **中可能不需要的应用程序**。</span><span class="sxs-lookup"><span data-stu-id="964b3-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="964b3-164">选择 **启用** 以启用 PUA 保护。</span><span class="sxs-lookup"><span data-stu-id="964b3-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="964b3-165">在 **选项** 中，选择 **阻止** 以阻止可能不需要的应用程序，或选择 **审核模式** 测试设置在环境中的工作方式。</span><span class="sxs-lookup"><span data-stu-id="964b3-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="964b3-166">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="964b3-166">Select **OK**.</span></span>

9. <span data-ttu-id="964b3-167">如通常一样部署组策略对象。</span><span class="sxs-lookup"><span data-stu-id="964b3-167">Deploy your Group Policy object as you usually do.</span></span>

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="964b3-168">使用 PowerShell cmdlet 配置 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="964b3-168">Use PowerShell cmdlets to configure PUA protection</span></span>

#### <a name="to-enable-pua-protection"></a><span data-ttu-id="964b3-169">启用 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="964b3-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="964b3-170">如果已禁用该功能，将此 cmdlet 的值设置为 `Enabled` 将启用该功能。</span><span class="sxs-lookup"><span data-stu-id="964b3-170">Setting the value for this cmdlet to `Enabled` turns on the feature if it has been disabled.</span></span>

#### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="964b3-171">将 PUA 保护设置为审核模式</span><span class="sxs-lookup"><span data-stu-id="964b3-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="964b3-172">设置 `AuditMode` 可检测 PUA，且不会阻止它们。</span><span class="sxs-lookup"><span data-stu-id="964b3-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

#### <a name="to-disable-pua-protection"></a><span data-ttu-id="964b3-173">禁用 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="964b3-173">To disable PUA protection</span></span>

<span data-ttu-id="964b3-174">建议保持启用 PUA 保护。</span><span class="sxs-lookup"><span data-stu-id="964b3-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="964b3-175">但是，可以通过以下 cmdlet 将其关闭：</span><span class="sxs-lookup"><span data-stu-id="964b3-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="964b3-176">如果已启用该功能，将此 cmdlet 的值设置为 `Disabled` 将禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="964b3-176">Setting the value for this cmdlet to `Disabled` turns off the feature if it has been enabled.</span></span>

<span data-ttu-id="964b3-177">有关详细信息，请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)和 [Defender cmdlet](/powershell/module/defender/index)。</span><span class="sxs-lookup"><span data-stu-id="964b3-177">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

## <a name="view-pua-events-using-powershell"></a><span data-ttu-id="964b3-178">使用 PowerShell 查看 PUA 事件</span><span class="sxs-lookup"><span data-stu-id="964b3-178">View PUA events using PowerShell</span></span>

<span data-ttu-id="964b3-179">PUA 事件在 Windows 事件查看器中报告，但不在 Microsoft 终结点管理器或 Intune 中。</span><span class="sxs-lookup"><span data-stu-id="964b3-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="964b3-180">还可使用 `Get-MpThreat` cmdlet 查看 Microsoft Defender 防病毒软件处理的威胁。</span><span class="sxs-lookup"><span data-stu-id="964b3-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="964b3-181">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="964b3-181">Here's an example:</span></span>

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

## <a name="get-email-notifications-about-pua-detections"></a><span data-ttu-id="964b3-182">获取有关 PUA 检测的电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="964b3-182">Get email notifications about PUA detections</span></span>

<span data-ttu-id="964b3-183">你可以打开电子邮件通知以接收有关 PUA 检测的邮件。</span><span class="sxs-lookup"><span data-stu-id="964b3-183">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="964b3-184">请参阅 [解决事件 ID](troubleshoot-microsoft-defender-antivirus.md) ，了解有关查看 Microsoft Defender 防病毒事件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="964b3-184">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="964b3-185">PUA 事件记录在事件 ID **1160**。</span><span class="sxs-lookup"><span data-stu-id="964b3-185">PUA events are recorded under event ID **1160**.</span></span>

## <a name="view-pua-events-using-advanced-hunting"></a><span data-ttu-id="964b3-186">使用高级搜寻查看 PUA 事件</span><span class="sxs-lookup"><span data-stu-id="964b3-186">View PUA events using advanced hunting</span></span>

<span data-ttu-id="964b3-187">如果你正在使用 [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)，你可以使用高级搜寻查询来查看 PUA 事件。</span><span class="sxs-lookup"><span data-stu-id="964b3-187">If you're using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), you can use an advanced hunting query to view PUA events.</span></span> <span data-ttu-id="964b3-188">示例查询如下：</span><span class="sxs-lookup"><span data-stu-id="964b3-188">Here's an example query:</span></span>

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

<span data-ttu-id="964b3-189">若要了解高级搜寻的详细信息，请参阅[使用高级搜寻来主动搜寻威胁](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="964b3-189">To learn more about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="exclude-files-from-pua-protection"></a><span data-ttu-id="964b3-190">排除来自 PUA 保护的文件</span><span class="sxs-lookup"><span data-stu-id="964b3-190">Exclude files from PUA protection</span></span>

<span data-ttu-id="964b3-191">有时文件被 PUA 保护错误阻止，或需要 PUA 的功能才能完成任务。</span><span class="sxs-lookup"><span data-stu-id="964b3-191">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="964b3-192">在这些情况下，可以将文件添加到排除列表。</span><span class="sxs-lookup"><span data-stu-id="964b3-192">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="964b3-193">有关详细信息，请参阅 [扩展名和文件夹位置配置和验证排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="964b3-193">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="964b3-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="964b3-194">See also</span></span>

- [<span data-ttu-id="964b3-195">下一代保护</span><span class="sxs-lookup"><span data-stu-id="964b3-195">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="964b3-196">配置方案、高要求和实时保护</span><span class="sxs-lookup"><span data-stu-id="964b3-196">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)