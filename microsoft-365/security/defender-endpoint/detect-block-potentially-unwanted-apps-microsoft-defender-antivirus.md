---
title: 使用 Microsoft Defender 防病毒阻止可能不需要的应用程序
description: 启用可能不需要的应用程序 (PUA) 防病毒功能，以阻止不需要的软件，如广告软件。
keywords: pua， 启用， 不需要的软件， 不需要的应用， 广告软件， 浏览器工具栏， 检测， 阻止， Microsoft Defender 防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bee92dfa998596578c27bda579a86776bc77c07b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690230"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="4cbe4-104">检测和阻止可能不需要的应用程序</span><span class="sxs-lookup"><span data-stu-id="4cbe4-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4cbe4-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4cbe4-105">**Applies to:**</span></span>

- [<span data-ttu-id="4cbe4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4cbe4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="4cbe4-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4cbe4-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

> [!NOTE]
> <span data-ttu-id="4cbe4-108">PUA (可能不需要) 是一类软件，可能会导致计算机运行缓慢、显示意外广告或最差时安装其他可能意外或不需要的软件。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software which might be unexpected or unwanted.</span></span> <span data-ttu-id="4cbe4-109">默认情况下，在 Windows 10 (版本 2004 和更高版本) 中，Microsoft Defender 防病毒会阻止被视为 PUA 的应用，适用于企业版 (E5) 设备。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-109">By default in Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA, for Enterprise (E5) devices.</span></span>

<span data-ttu-id="4cbe4-110">PUA (可能不需要) 不会被视为病毒、恶意软件或其他类型的威胁，但它们可能在终结点上执行对终结点性能或使用产生不利影响的操作。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-110">Potentially unwanted applications (PUA) are not considered viruses, malware, or other types of threats, but they might perform actions on endpoints which adversely affect endpoint performance or use.</span></span> <span data-ttu-id="4cbe4-111">_PUA_ 还可以指由于某些类型的不良行为而信誉不佳的应用程序（由 Microsoft Defender for Endpoint 评估）。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-111">_PUA_ can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="4cbe4-112">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="4cbe4-112">Here are some examples:</span></span>

- <span data-ttu-id="4cbe4-113">**显示** 广告或促销的广告软件，包括向网页插入广告的软件。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-113">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="4cbe4-114">**提供用于** 安装未由同一实体进行数字签名的其他软件的捆绑软件。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-114">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="4cbe4-115">此外，提供用于安装符合 PUA 资格的其他软件的软件。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-115">Also, software that offers to install other software that qualify as PUA.</span></span>
- <span data-ttu-id="4cbe4-116">**主动** 尝试规避安全产品检测的恶意软件，包括存在安全产品时行为不同的软件。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-116">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="4cbe4-117">有关我们用于标记应用程序以特别注意安全功能的条件的更多示例和讨论，请参阅 Microsoft 如何识别恶意软件和 [可能不需要的应用程序](/windows/security/threat-protection/intelligence/criteria)。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-117">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="4cbe4-118">可能不需要的应用程序会增加网络受到实际恶意软件感染的风险，使恶意软件感染更难识别，或浪费 IT 资源来清理它们。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-118">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="4cbe4-119">PUA 保护在 Windows 10、Windows Server 2019 和 Windows Server 2016 上受支持。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-119">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="4cbe4-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4cbe4-120">Microsoft Edge</span></span>

<span data-ttu-id="4cbe4-121">新的 [Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)基于 Chromium，可阻止可能不需要的应用程序下载和关联的资源 URL。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="4cbe4-122">此功能通过 Microsoft [Defender SmartScreen 提供](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="4cbe4-123">在基于 Chromium 的 Microsoft Edge 中启用 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="4cbe4-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="4cbe4-124">尽管基于 Chromium 的 Microsoft Edge (版本 80.0.361.50) 中可能不需要的应用程序保护在默认情况下处于关闭状态，但可以轻松地从浏览器内打开它。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="4cbe4-125">选择省略号，然后选择设置 **。**</span><span class="sxs-lookup"><span data-stu-id="4cbe4-125">Select the ellipses, and then choose **Settings**.</span></span>
2. <span data-ttu-id="4cbe4-126">选择 **"隐私、搜索和服务"。**</span><span class="sxs-lookup"><span data-stu-id="4cbe4-126">Select **Privacy, search, and services**.</span></span>
3. <span data-ttu-id="4cbe4-127">在"**安全性"** 部分下，打开"**阻止可能不需要的应用"。**</span><span class="sxs-lookup"><span data-stu-id="4cbe4-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="4cbe4-128">如果你运行的是基于 Chromium (Chromium) ，可以通过在我们的 Microsoft [Defender SmartScreen](https://demo.smartscreen.msft.net/)演示页面上测试 PUA 保护的 URL 阻止功能来安全地浏览它。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="4cbe4-129">使用 Microsoft Defender SmartScreen 阻止 URL</span><span class="sxs-lookup"><span data-stu-id="4cbe4-129">Blocking URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="4cbe4-130">在启用 PUA 保护的基于 Chromium 的边缘中，Microsoft Defender SmartScreen 可保护你免受与 PUA 关联的 URL 的影响。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="4cbe4-131">安全 [管理员可以配置](/DeployEdge/configure-microsoft-edge) Microsoft Edge 和 Microsoft Defender SmartScreen 如何协同工作，以保护用户组免受与 PUA 关联的 URL 影响。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="4cbe4-132">Microsoft Defender SmartScreen [明确提供了](/DeployEdge/microsoft-edge-policies#smartscreen-settings) 多个组策略设置，其中包括 [一个用于阻止 PUA 的组策略设置](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="4cbe4-133">此外，管理员可以使用组策略设置来打开或关闭 Microsoft Defender SmartScreen，将 [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) 配置为一个整体。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="4cbe4-134">尽管 Microsoft Defender for Endpoint 具有自己的基于由 Microsoft 管理的数据集的阻止列表，但你可以根据自己的威胁情报自定义此列表。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-134">Although Microsoft Defender for Endpoint has its own block list based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="4cbe4-135">如果你在 Microsoft Defender [终结点门户](/microsoft-365/security/defender-endpoint/manage-indicators) 创建和管理指示器，Microsoft Defender SmartScreen 将遵守新设置。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-135">If you [create and manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus"></a><span data-ttu-id="4cbe4-136">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="4cbe4-136">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="4cbe4-137">Microsoft Defender 防病毒 (PUA) 保护功能可能不需要的应用程序可以检测和阻止网络中终结点上的 PUA。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUAs on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="4cbe4-138">此功能在 Windows 10、Windows Server 2019 和 Windows Server 2016 中可用。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="4cbe4-139">Microsoft Defender 防病毒阻止检测到的 PUA 文件以及下载、移动、运行或安装这些文件的任何尝试。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="4cbe4-140">然后，阻止的 PUA 文件移动到隔离区。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="4cbe4-141">当在终结点上检测到 PUA 文件时，Microsoft Defender 防病毒会向用户 (除非通知已禁用[](configure-notifications-microsoft-defender-antivirus.md)) ，格式与其他威胁检测相同。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="4cbe4-142">通知的前言以 `PUA:` 指示其内容。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="4cbe4-143">通知显示在 Windows 安全中心 [应用内常用的隔离列表中](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="4cbe4-144">在 Microsoft Defender 防病毒中配置 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="4cbe4-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="4cbe4-145">可以使用[Microsoft Intune、Microsoft](/mem/intune/protect/device-protect)Endpoint [Configuration Manager、](/mem/configmgr/protect/deploy-use/endpoint-protection)[组](/azure/active-directory-domain-services/manage-group-policy)策略或[PowerShell cmdlet](/powershell/module/defender/?preserve-view=true&view=win10-ps)启用 PUA 保护。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="4cbe4-146">还可以在审核模式下使用 PUA 保护来检测可能不需要的应用程序，而不会阻止它们。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="4cbe4-147">检测在 Windows 事件日志中捕获。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="4cbe4-148">请访问 Microsoft Defender for Endpoint 演示 [网站，demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) 以确认该功能是否正常工作，并查看它是否正在操作。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="4cbe4-149">如果你的公司正在执行内部软件安全合规性检查，并且你要避免任何误报，则审核模式下的 PUA 保护非常有用。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

#### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="4cbe4-150">使用 Intune 配置 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="4cbe4-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="4cbe4-151">有关详细信息 [，请参阅在 Microsoft Intune 中](/intune/device-restrictions-configure) 配置设备限制设置和 Intune 中 [Windows 10](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 的 Microsoft Defender 防病毒设备限制设置。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

#### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="4cbe4-152">使用 Configuration Manager 配置 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="4cbe4-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="4cbe4-153">默认情况下，PuA 保护在 Microsoft Endpoint Manager (Current Branch) 。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="4cbe4-154">请参阅 [如何创建和部署反恶意软件策略：计划](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) 扫描设置，了解有关配置 Microsoft Endpoint Manager (Current Branch) 。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="4cbe4-155">有关System Center 2012管理器，请参阅如何在 Configuration Manager 中为 Endpoint Protection 部署可能不需要 [的应用程序保护策略](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="4cbe4-156">Microsoft Defender 防病毒阻止的 PUA 事件在 Windows 事件查看器中报告，而不是在 Microsoft Endpoint Configuration Manager 中报告。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

#### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="4cbe4-157">使用组策略配置 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="4cbe4-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="4cbe4-158">下载并安装 Windows [10 (.admx) 2020 年 10](https://www.microsoft.com/download/details.aspx?id=102157)月更新 (20H2) </span><span class="sxs-lookup"><span data-stu-id="4cbe4-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="4cbe4-159">在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="4cbe4-160">选择要配置的组策略对象，然后选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="4cbe4-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="4cbe4-161">在组 **策略管理编辑器中**，转到计算机 **配置，** 然后选择 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="4cbe4-162">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="4cbe4-163">双击配置 **对可能不需要的应用程序的检测**。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="4cbe4-164">选择 **"已启用** "以启用 PUA 保护。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="4cbe4-165">在 **"选项**"**中**，选择"阻止"以阻止可能不需要的应用程序，或选择"审核模式"以测试该设置在环境中的工作方式。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="4cbe4-166">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-166">Select **OK**.</span></span>

9. <span data-ttu-id="4cbe4-167">像通常一样部署组策略对象。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-167">Deploy your Group Policy object as you usually do.</span></span>

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="4cbe4-168">使用 PowerShell cmdlet 配置 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="4cbe4-168">Use PowerShell cmdlets to configure PUA protection</span></span>

##### <a name="to-enable-pua-protection"></a><span data-ttu-id="4cbe4-169">启用 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="4cbe4-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="4cbe4-170">如果禁用此功能，则设置此 cmdlet `Enabled` 的值以打开该功能。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-170">Setting the value for this cmdlet to `Enabled` turns the feature on if it has been disabled.</span></span>

##### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="4cbe4-171">将 PUA 保护设置为审核模式</span><span class="sxs-lookup"><span data-stu-id="4cbe4-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="4cbe4-172">设置 `AuditMode` 可检测 PUA 而不阻止它们。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

##### <a name="to-disable-pua-protection"></a><span data-ttu-id="4cbe4-173">禁用 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="4cbe4-173">To disable PUA protection</span></span>

<span data-ttu-id="4cbe4-174">我们建议保持 PUA 保护打开。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="4cbe4-175">但是，您可以使用以下 cmdlet 将其关闭：</span><span class="sxs-lookup"><span data-stu-id="4cbe4-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="4cbe4-176">设置此 cmdlet 的值 `Disabled` 可关闭该功能（如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-176">Setting the value for this cmdlet to `Disabled` turns the feature off if it has been enabled.</span></span>

<span data-ttu-id="4cbe4-177">请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/index) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-177">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="view-pua-events"></a><span data-ttu-id="4cbe4-178">查看 PUA 事件</span><span class="sxs-lookup"><span data-stu-id="4cbe4-178">View PUA events</span></span>

<span data-ttu-id="4cbe4-179">PUA 事件在 Windows 事件查看器中报告，但不在 Microsoft Endpoint Manager 或 Intune 中报告。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="4cbe4-180">您还可以使用 `Get-MpThreat` cmdlet 查看 Microsoft Defender 防病毒处理的威胁。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="4cbe4-181">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="4cbe4-181">Here's an example:</span></span>

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

<span data-ttu-id="4cbe4-182">你可以打开电子邮件通知以接收有关 PUA 检测的邮件。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-182">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="4cbe4-183">有关查看 Microsoft Defender 防病毒事件的详细信息，请参阅事件 [ID](troubleshoot-microsoft-defender-antivirus.md) 疑难解答。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-183">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="4cbe4-184">PUA 事件记录在事件 ID **1160 下**。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-184">PUA events are recorded under event ID **1160**.</span></span>

## <a name="excluding-files"></a><span data-ttu-id="4cbe4-185">排除文件</span><span class="sxs-lookup"><span data-stu-id="4cbe4-185">Excluding files</span></span>

<span data-ttu-id="4cbe4-186">有时 PUA 保护错误地阻止了文件，或者需要 PUA 的功能才能完成任务。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-186">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="4cbe4-187">在这些情况下，可以将文件添加到排除列表。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-187">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="4cbe4-188">有关详细信息，请参阅配置和 [验证基于文件扩展名和文件夹位置的排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="4cbe4-188">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4cbe4-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cbe4-189">See also</span></span>

- [<span data-ttu-id="4cbe4-190">下一代保护</span><span class="sxs-lookup"><span data-stu-id="4cbe4-190">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="4cbe4-191">配置行为、启发式和实时保护</span><span class="sxs-lookup"><span data-stu-id="4cbe4-191">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)