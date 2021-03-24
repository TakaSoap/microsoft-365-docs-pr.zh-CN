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
description: 了解 Microsoft Defender 防病毒如何保护 Windows 设备免受软件威胁（如病毒、恶意软件和间谍软件）的侵害。
ms.openlocfilehash: 5fe55817018eeae49e6e41c95d93006b6f05ece0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052214"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Microsoft Defender 防病毒 检测到的威胁

Microsoft Defender 防病毒可保护你的 Windows 设备免受软件威胁（如病毒、恶意软件和间谍软件）的侵害。

- 病毒通常通过将其代码附加到设备或网络上的其他文件来传播，并可能导致受感染的程序无法正常工作。
- 恶意软件包括可能导致设备损坏和中断正常使用的恶意文件、应用程序和代码。 此外，恶意软件还可以允许未经授权的访问、使用系统资源、窃取密码和帐户信息、将你锁定在计算机外并请求勒索等。
- 间谍软件收集数据（如 Web 浏览活动）并将数据发送到远程服务器。
 
为了提供威胁防护，Microsoft Defender 防病毒使用几种方法。 这些方法包括云保护、实时保护和专用保护更新。

- 云提供的保护可帮助提供对新出现的威胁的即时检测和阻止。
- 始终打开扫描使用文件和进程行为监视以及其他技术 (也称为实时 *保护) 。*
- 专用保护更新基于机器学习、人工和自动大数据分析以及深度威胁防御研究。 

若要详细了解恶意软件和 Microsoft Defender 防病毒，请参阅以下文章： 

- [了解恶意软件&其他威胁](/windows/security/threat-protection/intelligence/understanding-malware)
- [Microsoft 如何识别恶意软件和可能不需要的应用程序](/windows/security/threat-protection/intelligence/criteria)
- [Windows 10 中的下一代保护](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>使用非 Microsoft 防病毒解决方案时会发生什么情况？ 

Microsoft Defender 防病毒是操作系统的一部分，在运行 Windows 10 的设备上启用。 但是，如果你使用的是非 Microsoft 防病毒解决方案，并且没有使用 [Microsoft Defender for Endpoint，](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)则 Microsoft Defender 防病毒将自动进入禁用模式。  

处于禁用模式时，用户和客户仍可以使用 Microsoft Defender 防病毒进行计划扫描或按需扫描，以确定威胁;但是，Microsoft Defender 防病毒将不再：

- 用作默认防病毒应用。
- 主动扫描文件的威胁。
- 修正或解决威胁。

如果卸载非 Microsoft 防病毒解决方案，Microsoft Defender 防病毒将自动进入活动模式，以保护你的 Windows 设备免受威胁。

> [!TIP]
> - 如果你使用的是 Microsoft 365，请考虑使用 Microsoft Defender 防病毒作为主要防病毒解决方案。 集成可以提供更好的保护。 请参阅[更好的一起：Microsoft Defender 防病毒和 Office 365。](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)
> - 确保 Microsoft Defender 防病毒保持最新，即使你使用的是非 Microsoft 防病毒解决方案。

## <a name="what-to-expect-when-threats-are-detected"></a>检测到威胁时预期的结果

当 Microsoft Defender 防病毒检测到威胁时，将发生以下情况：

- 用户在 [Windows 中接收通知](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e)。 
- 检测在"保护历史记录"页上 [的 Windows 安全](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)**应用中** 列出。  
- 如果你已保护 [Windows 10](secure-win-10-pcs.md)设备，在 [Intune](/mem/intune/enrollment/windows-enrollment-methods)中注册它们，并且你的组织注册了 800 台或更少的设备，你将在 Microsoft <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365</a>管理中心的"威胁和防病毒"页面上看到威胁检测和见解，你可以从主页 (上的 **Microsoft Defender** 防病毒卡或导航窗格中选择"运行状况威胁"& 防病毒) 来访问这些威胁和见解。  >  

    如果你的组织在 Intune 中注册了 800 多个设备，系统将提示你查看 [来自 Microsoft Endpoint Manager](/mem/endpoint-manager-overview) 的威胁检测和见解，而不是从威胁和防病毒 **页面** 。
 
    > [!NOTE]
    > **Microsoft Defender 防病毒** 卡和 **威胁** 和防病毒页面正在阶段推出，因此你可能无法立即访问它们。

在大多数情况下，用户无需执行任何进一步的操作。 在设备上检测到恶意文件或程序后，Microsoft Defender 防病毒会阻止它并阻止其运行。 此外，新检测到的威胁将添加到防病毒和反恶意软件引擎，以便其他设备和用户也受到保护。  

如果用户需要执行一些操作（如批准删除恶意文件）时，他们会在收到通知时看到该操作。 若要了解有关 Microsoft Defender 防病毒代表用户采取的操作或用户可能需要采取的操作，请参阅 [保护历史记录](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)。 若要了解如何以 IT 专业人员/管理员角色管理威胁检测，请参阅查看检测到的威胁 [并采取措施](review-threats-take-action.md)。

若要了解有关不同威胁的信息，请访问 <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft 安全智能威胁</a>站点 ，可在其中执行以下操作： 

- 查看有关首要威胁的当前信息。
- 查看特定区域的最新威胁。
- 搜索威胁情报场，了解有关特定威胁的详细信息。

## <a name="related-content"></a>相关内容

[保护 Windows 10 设备 (](secure-windows-10-devices.md) 文章) \
[评估 Microsoft Defender 防病毒](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (文章) \
[How to turn on real-time and cloud-delivered antivirus protection](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (article) \
[如何打开和使用 Windows](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) 安全中心应用中的 Microsoft Defender 防病毒 (文章) \
[如何使用组策略启用 Microsoft Defender](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) 防病毒 (文章) \
[如何更新防病毒定义 (](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) 文章) \
[如何将恶意软件和非](/microsoft-365/security/defender-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) 恶意软件提交给 Microsoft 进行分析 (文章) 
