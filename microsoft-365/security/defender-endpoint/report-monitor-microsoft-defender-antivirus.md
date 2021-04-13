---
title: 监视并报告 Microsoft Defender 防病毒保护
description: 使用 CONFIGURATION Manager 或 SIEM (事件管理) 使用报告，并使用 PowerShell 和 WMI 监视 Microsoft Defender AV。
keywords: siem， 监视器， 报告， Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f0065792f525827ccd1471087b8a707989ef61ef
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690218"
---
# <a name="report-on-microsoft-defender-antivirus"></a><span data-ttu-id="d2be7-104">Microsoft Defender 防病毒报告</span><span class="sxs-lookup"><span data-stu-id="d2be7-104">Report on Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d2be7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d2be7-105">**Applies to:**</span></span>

- [<span data-ttu-id="d2be7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d2be7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d2be7-107">Microsoft Defender 防病毒内置于 Windows 10、Windows Server 2019 和 Windows Server 2016 中。</span><span class="sxs-lookup"><span data-stu-id="d2be7-107">Microsoft Defender Antivirus is built into Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="d2be7-108">Microsoft Defender 防病毒是 Microsoft Defender for Endpoint 中的下一代保护。</span><span class="sxs-lookup"><span data-stu-id="d2be7-108">Microsoft Defender Antivirus is of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="d2be7-109">下一代保护可帮助保护设备免受电子邮件、应用、云和 Web 中的软件威胁，如病毒、恶意软件和间谍软件。</span><span class="sxs-lookup"><span data-stu-id="d2be7-109">Next-generation protection helps protect your devices from software threats like viruses, malware, and spyware across email, apps, the cloud, and the web.</span></span>

<span data-ttu-id="d2be7-110">借助 Microsoft Defender 防病毒，你可以选择多个选项查看保护状态和警报。</span><span class="sxs-lookup"><span data-stu-id="d2be7-110">With Microsoft Defender Antivirus, you have several options for reviewing protection status and alerts.</span></span> <span data-ttu-id="d2be7-111">可以使用 Microsoft Endpoint Manager [监视 Microsoft Defender 防病毒](/configmgr/protect/deploy-use/monitor-endpoint-protection) 或 [创建电子邮件警报](/configmgr/protect/deploy-use/endpoint-configure-alerts)。</span><span class="sxs-lookup"><span data-stu-id="d2be7-111">You can use Microsoft Endpoint Manager to [monitor Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) or [create email alerts](/configmgr/protect/deploy-use/endpoint-configure-alerts).</span></span> <span data-ttu-id="d2be7-112">或者，可以使用 [Microsoft Intune](/intune/introduction-intune)监视保护。</span><span class="sxs-lookup"><span data-stu-id="d2be7-112">Or, you can monitor protection using [Microsoft Intune](/intune/introduction-intune).</span></span>  

<span data-ttu-id="d2be7-113">Microsoft Operations Management Suite 具有 [更新](/windows/deployment/update/update-compliance-get-started) 合规性加载项，可报告关键 Microsoft Defender 防病毒问题，包括保护更新和实时保护设置。</span><span class="sxs-lookup"><span data-stu-id="d2be7-113">Microsoft Operations Management Suite has an [Update Compliance add-in](/windows/deployment/update/update-compliance-get-started) that reports on key Microsoft Defender Antivirus issues, including protection updates and real-time protection settings.</span></span>

<span data-ttu-id="d2be7-114">如果你拥有 SIEM 服务器的第三方安全 (事件) ，还可以使用Windows Defender [客户端事件](/windows/win32/events/windows-events)。</span><span class="sxs-lookup"><span data-stu-id="d2be7-114">If you have a third-party security information and event management (SIEM) server, you can also consume [Windows Defender client events](/windows/win32/events/windows-events).</span></span> 

<span data-ttu-id="d2be7-115">Windows 事件包括多个安全事件源，包括安全帐户管理器 (SAM) 事件 ([增强的 Windows 10，](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)另请参阅安全审核主题[](/windows/device-security/auditing/security-auditing-overview)) 和 Windows Defender[事件](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="d2be7-115">Windows events comprise several security event sources, including Security Account Manager (SAM) events ([enhanced for Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), also see the [Security auditing](/windows/device-security/auditing/security-auditing-overview) topic) and  [Windows Defender events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="d2be7-116">可以使用 Windows 事件收集器集中聚合 [这些事件](/windows/win32/wec/windows-event-collector)。</span><span class="sxs-lookup"><span data-stu-id="d2be7-116">These events can be centrally aggregated using the [Windows event collector](/windows/win32/wec/windows-event-collector).</span></span> <span data-ttu-id="d2be7-117">通常，SIEM 服务器具有适用于 Windows 事件的连接器，从而使你可以关联 SIEM 服务器中的所有安全事件。</span><span class="sxs-lookup"><span data-stu-id="d2be7-117">Often, SIEM servers have connectors for Windows events, allowing you to correlate all security events in your SIEM server.</span></span> 

<span data-ttu-id="d2be7-118">您还可以使用 [Log Analytics 中的恶意软件评估解决方案监视恶意软件事件](/azure/log-analytics/log-analytics-malware)。</span><span class="sxs-lookup"><span data-stu-id="d2be7-118">You can also [monitor malware events using the Malware Assessment solution in Log Analytics](/azure/log-analytics/log-analytics-malware).</span></span>

<span data-ttu-id="d2be7-119">有关使用 PowerShell、WMI 或 Microsoft Azure 监视或确定状态的信息，请参阅 ([部署、管理和报告选项表) 。 ](deploy-manage-report-microsoft-defender-antivirus.md#ref2)</span><span class="sxs-lookup"><span data-stu-id="d2be7-119">For monitoring or determining status with PowerShell, WMI, or Microsoft Azure, see the [(Deployment, management, and reporting options table)](deploy-manage-report-microsoft-defender-antivirus.md#ref2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="d2be7-120">相关文章</span><span class="sxs-lookup"><span data-stu-id="d2be7-120">Related articles</span></span>

- [<span data-ttu-id="d2be7-121">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d2be7-121">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d2be7-122">Windows Server 2016 和 2019 上的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d2be7-122">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="d2be7-123">部署 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d2be7-123">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)