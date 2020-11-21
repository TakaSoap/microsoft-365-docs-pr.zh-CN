---
title: Microsoft Defender 防病毒检测到的威胁
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 了解 Microsoft Defender 防病毒如何保护你的 Windows 设备免受软件威胁（如病毒、恶意软件和间谍软件）的攻击。
ms.openlocfilehash: e3c8a1071625bba41af5f3cccd50f8484acac18d
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376681"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a><span data-ttu-id="88568-103">Microsoft Defender 防病毒检测到的威胁</span><span class="sxs-lookup"><span data-stu-id="88568-103">Threats detected by Microsoft Defender Antivirus</span></span>

<span data-ttu-id="88568-104">Microsoft Defender 防病毒保护你的 Windows 设备免受软件威胁（如病毒、恶意软件和间谍软件）的攻击。</span><span class="sxs-lookup"><span data-stu-id="88568-104">Microsoft Defender Antivirus protects your Windows devices from software threats, such as viruses, malware, and spyware.</span></span>

- <span data-ttu-id="88568-105">病毒通常通过将其代码附加到设备或网络上的其他文件来传播，并可能导致受感染的程序无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="88568-105">Viruses typically spread by attaching their code to other files on your device or network and can cause infected programs to work incorrectly.</span></span>
- <span data-ttu-id="88568-106">恶意软件包括恶意文件、应用程序和可能导致损坏和破坏正常使用设备的代码。</span><span class="sxs-lookup"><span data-stu-id="88568-106">Malware includes malicious files, applications, and code that can cause damage and disrupt normal use of devices.</span></span> <span data-ttu-id="88568-107">此外，恶意软件还可以允许未经授权的访问、使用系统资源、窃取密码和帐户信息，并将您锁定在您的计算机上并要求勒索等。</span><span class="sxs-lookup"><span data-stu-id="88568-107">Also, malware can allow unauthorized access, use system resources, steal passwords and account information, lock you out of your computer and ask for ransom, and more.</span></span>
- <span data-ttu-id="88568-108">间谍软件收集数据（如 web 浏览活动），并将数据发送到远程服务器。</span><span class="sxs-lookup"><span data-stu-id="88568-108">Spyware collects data, such as web-browsing activity, and sends the data to remote servers.</span></span>
 
<span data-ttu-id="88568-109">为了提供威胁防护，Microsoft Defender 防病毒使用多种方法。</span><span class="sxs-lookup"><span data-stu-id="88568-109">To provide threat protection, Microsoft Defender Antivirus uses several methods.</span></span> <span data-ttu-id="88568-110">这些方法包括云提供的保护、实时保护和专用的保护更新。</span><span class="sxs-lookup"><span data-stu-id="88568-110">These methods include cloud-delivered protection, real-time protection, and dedicated protection updates.</span></span>

- <span data-ttu-id="88568-111">云提供的保护有助于提供近乎即时的检测和阻止新的和新兴的威胁。</span><span class="sxs-lookup"><span data-stu-id="88568-111">Cloud-delivered protection helps provide near-instant detection and blocking of new and emerging threats.</span></span>
- <span data-ttu-id="88568-112">Always on 扫描使用文件和进程行为监视和其他技术 (也称为 " *实时保护* ") 。</span><span class="sxs-lookup"><span data-stu-id="88568-112">Always-on scanning uses file- and process-behavior monitoring and other techniques (also known as *real-time protection*).</span></span>
- <span data-ttu-id="88568-113">专用的保护更新基于机器学习、人工和自动大型数据分析和深层威胁抵抗研究。</span><span class="sxs-lookup"><span data-stu-id="88568-113">Dedicated protection updates are based on machine learning, human and automated big-data analysis, and in-depth threat resistance research.</span></span> 

<span data-ttu-id="88568-114">若要了解有关恶意软件和 Microsoft Defender 防病毒的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="88568-114">To learn more about malware and Microsoft Defender Antivirus, see the following articles:</span></span> 

- [<span data-ttu-id="88568-115">了解 & 其他威胁的恶意软件</span><span class="sxs-lookup"><span data-stu-id="88568-115">Understanding malware & other threats</span></span>](/windows/security/threat-protection/intelligence/understanding-malware)
- [<span data-ttu-id="88568-116">Microsoft 如何识别恶意软件和可能不需要的应用程序</span><span class="sxs-lookup"><span data-stu-id="88568-116">How Microsoft identifies malware and potentially unwanted applications</span></span>](/windows/security/threat-protection/intelligence/criteria)
- [<span data-ttu-id="88568-117">Windows 10 中的下一代保护</span><span class="sxs-lookup"><span data-stu-id="88568-117">Next-generation protection in Windows 10</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a><span data-ttu-id="88568-118">使用非 Microsoft 防病毒解决方案时会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="88568-118">What happens when a non-Microsoft antivirus solution is used?</span></span> 

<span data-ttu-id="88568-119">Microsoft Defender 防病毒是操作系统的一部分，在运行 Windows 10 的设备上启用。</span><span class="sxs-lookup"><span data-stu-id="88568-119">Microsoft Defender Antivirus is part of the operating system and is enabled on devices that are running Windows 10.</span></span> <span data-ttu-id="88568-120">但是，如果您使用的是非 Microsoft 防病毒解决方案，并且没有使用 [Microsoft defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)，则 Microsoft Defender 防病毒将自动进入禁用模式。</span><span class="sxs-lookup"><span data-stu-id="88568-120">However, if you're using a non-Microsoft antivirus solution and you aren't using [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection), then Microsoft Defender Antivirus automatically goes into disabled mode.</span></span>  

<span data-ttu-id="88568-121">在禁用模式下，用户和客户仍可以使用 Microsoft Defender 防病毒进行计划内或按需扫描以确定威胁;但是，Microsoft Defender 防病毒将不再执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="88568-121">When in disabled mode, users and customers can still use Microsoft Defender Antivirus for scheduled or on-demand scans to identify threats; however, Microsoft Defender Antivirus will no longer:</span></span>

- <span data-ttu-id="88568-122">用作默认的防病毒应用程序。</span><span class="sxs-lookup"><span data-stu-id="88568-122">be used as the default antivirus app.</span></span>
- <span data-ttu-id="88568-123">主动扫描文件以查找威胁。</span><span class="sxs-lookup"><span data-stu-id="88568-123">actively scan files for threats.</span></span>
- <span data-ttu-id="88568-124">修正或解决威胁。</span><span class="sxs-lookup"><span data-stu-id="88568-124">remediate, or resolve, threats.</span></span>

<span data-ttu-id="88568-125">如果卸载非 Microsoft 防病毒解决方案，Microsoft Defender 防病毒程序将自动进入主动模式，以防止 Windows 设备受到威胁。</span><span class="sxs-lookup"><span data-stu-id="88568-125">If you uninstall the non-Microsoft antivirus solution, Microsoft Defender Antivirus will automatically go into active mode to protect your Windows devices from threats.</span></span>

> [!TIP]
> - <span data-ttu-id="88568-126">如果你使用的是 Microsoft 365，请考虑使用 Microsoft Defender 防病毒作为你的主要防病毒解决方案。</span><span class="sxs-lookup"><span data-stu-id="88568-126">If you're using Microsoft 365, consider using Microsoft Defender Antivirus as your primary antivirus solution.</span></span> <span data-ttu-id="88568-127">集成可提供更好的保护。</span><span class="sxs-lookup"><span data-stu-id="88568-127">Integration can provide better protection.</span></span> <span data-ttu-id="88568-128">[更好地查看： Microsoft Defender 防病毒和 Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="88568-128">See [Better together: Microsoft Defender Antivirus and Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).</span></span>
> - <span data-ttu-id="88568-129">确保 Microsoft Defender 防病毒始终保持最新，即使你使用的是非 Microsoft 防病毒解决方案也是如此。</span><span class="sxs-lookup"><span data-stu-id="88568-129">Make sure to keep Microsoft Defender Antivirus up to date, even if you're using a non-Microsoft antivirus solution.</span></span>

## <a name="what-to-expect-when-threats-are-detected"></a><span data-ttu-id="88568-130">检测到威胁时的预期行为</span><span class="sxs-lookup"><span data-stu-id="88568-130">What to expect when threats are detected</span></span>

<span data-ttu-id="88568-131">当 Microsoft Defender 防病毒检测到威胁时，将会发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="88568-131">When threats are detected by Microsoft Defender Antivirus, the following things happen:</span></span>

- <span data-ttu-id="88568-132">用户 [在 Windows 中接收通知](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e)。</span><span class="sxs-lookup"><span data-stu-id="88568-132">Users receive [notifications in Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e).</span></span> 
- <span data-ttu-id="88568-133">"**保护历史记录**" 页上的 [Windows 安全应用程序](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)中列出了检测项。</span><span class="sxs-lookup"><span data-stu-id="88568-133">Detections are listed in the [Windows Security app](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) on the **Protection history** page.</span></span>  
- <span data-ttu-id="88568-134">如果你已 [对 Windows 10 设备](secure-win-10-pcs.md)进行了保护，并已 [在 Intune 中注册了这些](/mem/intune/enrollment/windows-enrollment-methods)设备，则会在 "**活动威胁**" 页上看到 " <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">microsoft 365 管理中心</a>" 中的威胁检测和见解，可以从 **主页** 上的 **microsoft Defender 防病毒** 卡 (上 **Health** 或通过选择 "  >  **& 防病毒**) 中的" 健康威胁 "来访问导航窗格。</span><span class="sxs-lookup"><span data-stu-id="88568-134">If you've [secured your Windows 10 devices](secure-win-10-pcs.md) and [enrolled them in Intune](/mem/intune/enrollment/windows-enrollment-methods), you'll see threat detections and insights in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> on the **Active threats** page, which you can access from the **Microsoft Defender Antivirus** card on the **Home** page (or from the navigation pane by selecting **Health** > **Threats & antivirus**).</span></span>
    > [!NOTE]
    > <span data-ttu-id="88568-135">**Microsoft Defender 防病毒** 卡和 **活动威胁** 页面将分阶段推出，因此你可能无法立即访问它们。</span><span class="sxs-lookup"><span data-stu-id="88568-135">The **Microsoft Defender Antivirus** card and **Active threats** page are being rolled out in phases, so you may not have immediate access to them.</span></span>

<span data-ttu-id="88568-136">在大多数情况下，用户不需要执行任何进一步操作。</span><span class="sxs-lookup"><span data-stu-id="88568-136">In most cases, users don't need to take any further action.</span></span> <span data-ttu-id="88568-137">一旦在设备上检测到恶意文件或程序，Microsoft Defender 防病毒程序将阻止它运行，并阻止其运行。</span><span class="sxs-lookup"><span data-stu-id="88568-137">As soon as a malicious file or program is detected on a device, Microsoft Defender Antivirus blocks it and prevents it from running.</span></span> <span data-ttu-id="88568-138">此外，新检测到的威胁将添加到防病毒和反恶意软件引擎中，以便其他设备和用户也受到保护。</span><span class="sxs-lookup"><span data-stu-id="88568-138">Plus, newly detected threats are added to the antivirus and antimalware engine so that other devices and users are protected, as well.</span></span>  

<span data-ttu-id="88568-139">如果有用户需要执行的操作（如批准删除恶意文件），他们将在收到的通知中看到。</span><span class="sxs-lookup"><span data-stu-id="88568-139">If there's an action a user needs to take, such as approving the removal of a malicious file, they'll see that in the notification they receive.</span></span> <span data-ttu-id="88568-140">若要了解有关 Microsoft Defender 防病毒代表用户采取的操作的详细信息，或者用户可能需要执行的操作，请参阅 [保护历史记录](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)。</span><span class="sxs-lookup"><span data-stu-id="88568-140">To learn more about actions that Microsoft Defender Antivirus takes on a user's behalf, or actions users might need to take, see [Protection History](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708).</span></span> <span data-ttu-id="88568-141">若要了解如何将威胁检测作为 IT 专业人员/管理员进行管理，请参阅 [查看检测到的威胁并采取措施](review-threats-take-action.md)。</span><span class="sxs-lookup"><span data-stu-id="88568-141">To learn how to manage threat detections as an IT professional/admin, see [Review detected threats and take action](review-threats-take-action.md).</span></span>

<span data-ttu-id="88568-142">若要了解有关不同威胁的详细信息，请访问 <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft 安全智能威胁网站</a>，在其中可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="88568-142">To learn more about different threats, visit the <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft Security Intelligence Threats site</a>, where you can perform the following actions:</span></span> 

- <span data-ttu-id="88568-143">查看有关主要威胁的当前信息。</span><span class="sxs-lookup"><span data-stu-id="88568-143">View current information about top threats.</span></span>
- <span data-ttu-id="88568-144">查看特定区域的最新威胁。</span><span class="sxs-lookup"><span data-stu-id="88568-144">View the latest threats for a specific region.</span></span>
- <span data-ttu-id="88568-145">搜索威胁百科全书以了解有关特定威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="88568-145">Search the threat encyclopedia for details about a specific threat.</span></span>

## <a name="related-content"></a><span data-ttu-id="88568-146">相关内容</span><span class="sxs-lookup"><span data-stu-id="88568-146">Related content</span></span>

<span data-ttu-id="88568-147">[保护 Windows 10 设备](secure-windows-10-devices.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="88568-147">[Secure Windows 10 devices](secure-windows-10-devices.md) (article)</span></span>\
<span data-ttu-id="88568-148">[评估 Microsoft Defender 防病毒](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (文章) </span><span class="sxs-lookup"><span data-stu-id="88568-148">[Evaluate Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (article)</span></span>\
<span data-ttu-id="88568-149">[如何打开实时和云提供的防病毒保护](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (文章) </span><span class="sxs-lookup"><span data-stu-id="88568-149">[How to turn on real-time and cloud-delivered antivirus protection](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (article)</span></span>\
<span data-ttu-id="88568-150">[如何在 Windows 安全应用程序中打开和使用 Microsoft Defender 防病毒](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (文章) </span><span class="sxs-lookup"><span data-stu-id="88568-150">[How to turn on and use Microsoft Defender Antivirus from the Windows Security app](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (article)</span></span>\
<span data-ttu-id="88568-151">[如何使用组策略打开 Microsoft Defender 防病毒](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (文章) </span><span class="sxs-lookup"><span data-stu-id="88568-151">[How to turn on Microsoft Defender Antivirus by using Group Policy](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (article)</span></span>\
<span data-ttu-id="88568-152">[如何更新 (文章) 的防病毒定义](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions)</span><span class="sxs-lookup"><span data-stu-id="88568-152">[How to update your antivirus definitions](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (article)\</span></span>
<span data-ttu-id="88568-153">[如何将恶意软件和非恶意软件提交给 Microsoft 进行分析](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (文章) </span><span class="sxs-lookup"><span data-stu-id="88568-153">[How to submit malware and non-malware to Microsoft for analysis](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (article)</span></span>