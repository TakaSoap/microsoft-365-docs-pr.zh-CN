---
title: Microsoft Defender 防病毒 检测到的威胁
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
description: 了解如何Microsoft Defender 防病毒设备Windows软件威胁，如病毒、恶意软件和间谍软件。
ms.openlocfilehash: 7c5d000e2a8c30e17d1f890cef69fe88beed75bb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198359"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a><span data-ttu-id="bdd96-103">Microsoft Defender 防病毒 检测到的威胁</span><span class="sxs-lookup"><span data-stu-id="bdd96-103">Threats detected by Microsoft Defender Antivirus</span></span>

<span data-ttu-id="bdd96-104">Microsoft Defender 防病毒保护你的Windows设备免受软件威胁，如病毒、恶意软件和间谍软件。</span><span class="sxs-lookup"><span data-stu-id="bdd96-104">Microsoft Defender Antivirus protects your Windows devices from software threats, such as viruses, malware, and spyware.</span></span>

- <span data-ttu-id="bdd96-105">病毒通常通过将其代码附加到设备或网络上的其他文件来传播，并可能导致受感染的程序无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="bdd96-105">Viruses typically spread by attaching their code to other files on your device or network and can cause infected programs to work incorrectly.</span></span>
- <span data-ttu-id="bdd96-106">恶意软件包括可能导致设备损坏和中断正常使用的恶意文件、应用程序和代码。</span><span class="sxs-lookup"><span data-stu-id="bdd96-106">Malware includes malicious files, applications, and code that can cause damage and disrupt normal use of devices.</span></span> <span data-ttu-id="bdd96-107">此外，恶意软件还可以允许未经授权的访问、使用系统资源、窃取密码和帐户信息、将你锁定在计算机外并请求勒索等。</span><span class="sxs-lookup"><span data-stu-id="bdd96-107">Also, malware can allow unauthorized access, use system resources, steal passwords and account information, lock you out of your computer and ask for ransom, and more.</span></span>
- <span data-ttu-id="bdd96-108">间谍软件收集数据（如 Web 浏览活动）并将数据发送到远程服务器。</span><span class="sxs-lookup"><span data-stu-id="bdd96-108">Spyware collects data, such as web-browsing activity, and sends the data to remote servers.</span></span>
 
<span data-ttu-id="bdd96-109">为了提供威胁防护，Microsoft Defender 防病毒多种方法。</span><span class="sxs-lookup"><span data-stu-id="bdd96-109">To provide threat protection, Microsoft Defender Antivirus uses several methods.</span></span> <span data-ttu-id="bdd96-110">这些方法包括云保护、实时保护和专用保护更新。</span><span class="sxs-lookup"><span data-stu-id="bdd96-110">These methods include cloud-delivered protection, real-time protection, and dedicated protection updates.</span></span>

- <span data-ttu-id="bdd96-111">云提供的保护可帮助提供对新出现的威胁的即时检测和阻止。</span><span class="sxs-lookup"><span data-stu-id="bdd96-111">Cloud-delivered protection helps provide near-instant detection and blocking of new and emerging threats.</span></span>
- <span data-ttu-id="bdd96-112">始终打开扫描使用文件和进程行为监视以及其他技术 (也称为实时 *保护) 。*</span><span class="sxs-lookup"><span data-stu-id="bdd96-112">Always-on scanning uses file- and process-behavior monitoring and other techniques (also known as *real-time protection*).</span></span>
- <span data-ttu-id="bdd96-113">专用保护更新基于机器学习、人工和自动大数据分析以及深度威胁防御研究。</span><span class="sxs-lookup"><span data-stu-id="bdd96-113">Dedicated protection updates are based on machine learning, human and automated big-data analysis, and in-depth threat resistance research.</span></span> 

<span data-ttu-id="bdd96-114">若要了解有关恶意软件和恶意软件Microsoft Defender 防病毒，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="bdd96-114">To learn more about malware and Microsoft Defender Antivirus, see the following articles:</span></span> 

- [<span data-ttu-id="bdd96-115">了解恶意软件&其他威胁</span><span class="sxs-lookup"><span data-stu-id="bdd96-115">Understanding malware & other threats</span></span>](/windows/security/threat-protection/intelligence/understanding-malware)
- [<span data-ttu-id="bdd96-116">Microsoft 如何识别恶意软件和可能不需要的应用程序</span><span class="sxs-lookup"><span data-stu-id="bdd96-116">How Microsoft identifies malware and potentially unwanted applications</span></span>](/windows/security/threat-protection/intelligence/criteria)
- [<span data-ttu-id="bdd96-117">Windows 10 中的下一代保护</span><span class="sxs-lookup"><span data-stu-id="bdd96-117">Next-generation protection in Windows 10</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a><span data-ttu-id="bdd96-118">使用非 Microsoft 防病毒解决方案时会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="bdd96-118">What happens when a non-Microsoft antivirus solution is used?</span></span> 

<span data-ttu-id="bdd96-119">Microsoft Defender 防病毒操作系统的一部分，在运行操作系统的设备上Windows 10。</span><span class="sxs-lookup"><span data-stu-id="bdd96-119">Microsoft Defender Antivirus is part of the operating system and is enabled on devices that are running Windows 10.</span></span> <span data-ttu-id="bdd96-120">但是，如果你使用的是非 Microsoft 防病毒解决方案，并且没有使用[Microsoft Defender for Endpoint，](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)则Microsoft Defender 防病毒自动进入禁用模式。</span><span class="sxs-lookup"><span data-stu-id="bdd96-120">However, if you're using a non-Microsoft antivirus solution and you aren't using [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection), then Microsoft Defender Antivirus automatically goes into disabled mode.</span></span>  

<span data-ttu-id="bdd96-121">处于禁用模式时，用户和客户仍可以使用Microsoft Defender 防病毒扫描或按需扫描来识别威胁;但是，Microsoft Defender 防病毒将不再：</span><span class="sxs-lookup"><span data-stu-id="bdd96-121">When in disabled mode, users and customers can still use Microsoft Defender Antivirus for scheduled or on-demand scans to identify threats; however, Microsoft Defender Antivirus will no longer:</span></span>

- <span data-ttu-id="bdd96-122">用作默认防病毒应用。</span><span class="sxs-lookup"><span data-stu-id="bdd96-122">be used as the default antivirus app.</span></span>
- <span data-ttu-id="bdd96-123">主动扫描文件的威胁。</span><span class="sxs-lookup"><span data-stu-id="bdd96-123">actively scan files for threats.</span></span>
- <span data-ttu-id="bdd96-124">修正或解决威胁。</span><span class="sxs-lookup"><span data-stu-id="bdd96-124">remediate, or resolve, threats.</span></span>

<span data-ttu-id="bdd96-125">如果卸载非 Microsoft 防病毒解决方案，Microsoft Defender 防病毒自动进入活动模式，Windows设备免受威胁。</span><span class="sxs-lookup"><span data-stu-id="bdd96-125">If you uninstall the non-Microsoft antivirus solution, Microsoft Defender Antivirus will automatically go into active mode to protect your Windows devices from threats.</span></span>

> [!TIP]
> - <span data-ttu-id="bdd96-126">如果你使用的是防病毒Microsoft 365，请考虑Microsoft Defender 防病毒作为主要防病毒解决方案。</span><span class="sxs-lookup"><span data-stu-id="bdd96-126">If you're using Microsoft 365, consider using Microsoft Defender Antivirus as your primary antivirus solution.</span></span> <span data-ttu-id="bdd96-127">集成可以提供更好的保护。</span><span class="sxs-lookup"><span data-stu-id="bdd96-127">Integration can provide better protection.</span></span> <span data-ttu-id="bdd96-128">请参阅[更好的一起：Microsoft Defender 防病毒 和 Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="bdd96-128">See [Better together: Microsoft Defender Antivirus and Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).</span></span>
> - <span data-ttu-id="bdd96-129">请确保使Microsoft Defender 防病毒保持最新，即使您使用的是非 Microsoft 防病毒解决方案。</span><span class="sxs-lookup"><span data-stu-id="bdd96-129">Make sure to keep Microsoft Defender Antivirus up to date, even if you're using a non-Microsoft antivirus solution.</span></span>

## <a name="what-to-expect-when-threats-are-detected"></a><span data-ttu-id="bdd96-130">检测到威胁时预期的结果</span><span class="sxs-lookup"><span data-stu-id="bdd96-130">What to expect when threats are detected</span></span>

<span data-ttu-id="bdd96-131">当检测到威胁时Microsoft Defender 防病毒，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="bdd96-131">When threats are detected by Microsoft Defender Antivirus, the following things happen:</span></span>

- <span data-ttu-id="bdd96-132">用户会收到[来自 Windows 的通知](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e)。</span><span class="sxs-lookup"><span data-stu-id="bdd96-132">Users receive [notifications in Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e).</span></span> 
- <span data-ttu-id="bdd96-133">"保护历史记录 ["页上Windows 安全中心](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)应用 **中列出的检测**。</span><span class="sxs-lookup"><span data-stu-id="bdd96-133">Detections are listed in the [Windows Security app](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) on the **Protection history** page.</span></span>  
- <span data-ttu-id="bdd96-134">如果你已保护 [Windows 10](secure-win-10-pcs.md)设备，在 [Intune](/mem/intune/enrollment/windows-enrollment-methods)中注册它们，并且你的组织注册了 800 台或更少的设备，你将在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>管理中心中看到威胁检测和见解，在"威胁和防病毒"页面上，你可以从主页 (上的 **Microsoft Defender 防病毒** 卡或导航窗格中选择"运行状况威胁"&防病毒) 访问。  >  </span><span class="sxs-lookup"><span data-stu-id="bdd96-134">If you've [secured your Windows 10 devices](secure-win-10-pcs.md) and [enrolled them in Intune](/mem/intune/enrollment/windows-enrollment-methods), and your organization has 800 or fewer devices enrolled, you'll see threat detections and insights in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> on the **Threats and antivirus** page, which you can access from the **Microsoft Defender Antivirus** card on the **Home** page (or from the navigation pane by selecting **Health** > **Threats & antivirus**).</span></span>

    <span data-ttu-id="bdd96-135">如果你的组织在 Intune 中注册了 800 多个设备，系统将提示你查看[来自 Microsoft Endpoint Manager](/mem/endpoint-manager-overview)而非威胁和防病毒页面的威胁检测和见解。 </span><span class="sxs-lookup"><span data-stu-id="bdd96-135">If your organization has more than 800 devices enrolled in Intune, you'll be prompted to view threat detections and insights from [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) instead of from the **Threats and antivirus** page.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="bdd96-136">the **Microsoft Defender 防病毒** card and **Threats and antivirus** page are being rolled out in phases， so you may not have immediate access to them.</span><span class="sxs-lookup"><span data-stu-id="bdd96-136">The **Microsoft Defender Antivirus** card and **Threats and antivirus** page are being rolled out in phases, so you may not have immediate access to them.</span></span>

<span data-ttu-id="bdd96-137">在大多数情况下，用户无需执行任何进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="bdd96-137">In most cases, users don't need to take any further action.</span></span> <span data-ttu-id="bdd96-138">一旦在设备上检测到恶意文件或程序，Microsoft Defender 防病毒阻止它并阻止其运行。</span><span class="sxs-lookup"><span data-stu-id="bdd96-138">As soon as a malicious file or program is detected on a device, Microsoft Defender Antivirus blocks it and prevents it from running.</span></span> <span data-ttu-id="bdd96-139">此外，新检测到的威胁将添加到防病毒和反恶意软件引擎，以便其他设备和用户也受到保护。</span><span class="sxs-lookup"><span data-stu-id="bdd96-139">Plus, newly detected threats are added to the antivirus and antimalware engine so that other devices and users are protected, as well.</span></span>  

<span data-ttu-id="bdd96-140">如果用户需要执行一些操作（如批准删除恶意文件）时，他们会在收到通知时看到该操作。</span><span class="sxs-lookup"><span data-stu-id="bdd96-140">If there's an action a user needs to take, such as approving the removal of a malicious file, they'll see that in the notification they receive.</span></span> <span data-ttu-id="bdd96-141">若要了解有关用户Microsoft Defender 防病毒用户采取的操作或用户可能需要采取的操作，请参阅[保护历史记录](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)。</span><span class="sxs-lookup"><span data-stu-id="bdd96-141">To learn more about actions that Microsoft Defender Antivirus takes on a user's behalf, or actions users might need to take, see [Protection History](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708).</span></span> <span data-ttu-id="bdd96-142">若要了解如何以 IT 专业人员/管理员角色管理威胁检测，请参阅查看检测到的威胁 [并采取措施](review-threats-take-action.md)。</span><span class="sxs-lookup"><span data-stu-id="bdd96-142">To learn how to manage threat detections as an IT professional/admin, see [Review detected threats and take action](review-threats-take-action.md).</span></span>

<span data-ttu-id="bdd96-143">若要了解有关不同威胁的信息，请访问Microsoft 安全智能<a href="https://www.microsoft.com/wdsi/threats" target="_blank">威胁站点</a>，可在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bdd96-143">To learn more about different threats, visit the <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft Security Intelligence Threats site</a>, where you can perform the following actions:</span></span> 

- <span data-ttu-id="bdd96-144">查看有关首要威胁的当前信息。</span><span class="sxs-lookup"><span data-stu-id="bdd96-144">View current information about top threats.</span></span>
- <span data-ttu-id="bdd96-145">查看特定区域的最新威胁。</span><span class="sxs-lookup"><span data-stu-id="bdd96-145">View the latest threats for a specific region.</span></span>
- <span data-ttu-id="bdd96-146">搜索威胁情报场，了解有关特定威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bdd96-146">Search the threat encyclopedia for details about a specific threat.</span></span>

## <a name="related-content"></a><span data-ttu-id="bdd96-147">相关内容</span><span class="sxs-lookup"><span data-stu-id="bdd96-147">Related content</span></span>

<span data-ttu-id="bdd96-148">[安全Windows 10设备](secure-windows-10-devices.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="bdd96-148">[Secure Windows 10 devices](secure-windows-10-devices.md) (article)</span></span>\
<span data-ttu-id="bdd96-149">[评估Microsoft Defender 防病毒 (](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus)文章) </span><span class="sxs-lookup"><span data-stu-id="bdd96-149">[Evaluate Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (article)</span></span>\
<span data-ttu-id="bdd96-150">[How to turn on real-time and cloud-delivered antivirus protection](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (article) </span><span class="sxs-lookup"><span data-stu-id="bdd96-150">[How to turn on real-time and cloud-delivered antivirus protection](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (article)</span></span>\
<span data-ttu-id="bdd96-151">[如何打开和使用应用Microsoft Defender 防病毒应用Windows 安全中心 (](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)应用) </span><span class="sxs-lookup"><span data-stu-id="bdd96-151">[How to turn on and use Microsoft Defender Antivirus from the Windows Security app](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (article)</span></span>\
<span data-ttu-id="bdd96-152">[How to turn on Microsoft Defender 防病毒 by using Group Policy](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (article) </span><span class="sxs-lookup"><span data-stu-id="bdd96-152">[How to turn on Microsoft Defender Antivirus by using Group Policy](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (article)</span></span>\
<span data-ttu-id="bdd96-153">[如何更新防病毒定义 (](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) 文章) </span><span class="sxs-lookup"><span data-stu-id="bdd96-153">[How to update your antivirus definitions](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (article)</span></span>\
<span data-ttu-id="bdd96-154">[如何将恶意软件和非](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) 恶意软件提交给 Microsoft 进行分析 (文章) </span><span class="sxs-lookup"><span data-stu-id="bdd96-154">[How to submit malware and non-malware to Microsoft for analysis](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (article)</span></span>
