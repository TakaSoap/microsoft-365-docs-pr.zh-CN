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
ms.openlocfilehash: 79ec44a44c3939a4a868b98d75ab4f24eaf949fcd9bbafb7c0a3173e267f4680
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53896295"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Microsoft Defender 防病毒 检测到的威胁

Microsoft Defender 防病毒保护你的Windows设备免受软件威胁，如病毒、恶意软件和间谍软件。

- 病毒通常通过将其代码附加到设备或网络上的其他文件来传播，并可能导致受感染的程序无法正常工作。
- 恶意软件包括可能导致设备损坏和中断正常使用的恶意文件、应用程序和代码。 此外，恶意软件还可以允许未经授权的访问、使用系统资源、窃取密码和帐户信息、将你锁定在计算机外并请求勒索等。
- 间谍软件收集数据（如 Web 浏览活动）并将数据发送到远程服务器。
 
为了提供威胁防护，Microsoft Defender 防病毒多种方法。 这些方法包括云保护、实时保护和专用保护更新。

- 云提供的保护可帮助提供对新出现的威胁的即时检测和阻止。
- 始终打开扫描使用文件和进程行为监视以及其他技术 (也称为实时 *保护) 。*
- 专用保护更新基于机器学习、人工和自动大数据分析以及深度威胁防御研究。 

若要了解有关恶意软件和恶意软件Microsoft Defender 防病毒，请参阅以下文章： 

- [了解恶意软件&其他威胁](/windows/security/threat-protection/intelligence/understanding-malware)
- [Microsoft 如何识别恶意软件和可能不需要的应用程序](/windows/security/threat-protection/intelligence/criteria)
- [Windows 10 中的下一代保护](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>使用非 Microsoft 防病毒解决方案时会发生什么情况？ 

Microsoft Defender 防病毒操作系统的一部分，在运行操作系统的设备上Windows 10。 但是，如果你使用的是非 Microsoft 防病毒解决方案，并且没有使用[Microsoft Defender for Endpoint，](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)则Microsoft Defender 防病毒自动进入禁用模式。  

处于禁用模式时，用户和客户仍可以使用Microsoft Defender 防病毒扫描或按需扫描来识别威胁;但是，Microsoft Defender 防病毒将不再：

- 用作默认防病毒应用。
- 主动扫描文件的威胁。
- 修正或解决威胁。

如果卸载非 Microsoft 防病毒解决方案，Microsoft Defender 防病毒自动进入活动模式，Windows设备免受威胁。

> [!TIP]
> - 如果你使用的是防病毒Microsoft 365，请考虑Microsoft Defender 防病毒作为主要防病毒解决方案。 集成可以提供更好的保护。 请参阅[更好的一起：Microsoft Defender 防病毒 和 Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)。
> - 请确保使Microsoft Defender 防病毒保持最新，即使您使用的是非 Microsoft 防病毒解决方案。

## <a name="what-to-expect-when-threats-are-detected"></a>检测到威胁时预期的结果

当检测到威胁时Microsoft Defender 防病毒，将发生以下情况：

- 用户会收到[来自 Windows 的通知](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e)。 
- "保护历史记录 ["页上Windows 安全中心](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)应用 **中列出的检测**。  
- 如果你已保护 [Windows 10](secure-win-10-pcs.md)设备，并且在 [Intune](/mem/intune/enrollment/windows-enrollment-methods)中注册了这些设备，并且你的组织注册了 800 台或更少的设备，你将在"威胁和防病毒"页面上看到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心威胁</a>检测和见解，你可以从 (主页上的 **Microsoft Defender 防病毒** 卡或导航窗格中选择"运行状况威胁"& 防病毒) 来访问该页面。  >  

    如果你的组织在 Intune 中注册了 800 多个设备，系统将提示你查看[来自 Microsoft Endpoint Manager](/mem/endpoint-manager-overview)而非威胁和防病毒页面的威胁检测和见解。 
 
    > [!NOTE]
    > the **Microsoft Defender 防病毒** card and **Threats and antivirus** page are being rolled out in phases， so you may not have immediate access to them.

在大多数情况下，用户无需执行任何进一步的操作。 一旦在设备上检测到恶意文件或程序，Microsoft Defender 防病毒阻止它并阻止其运行。 此外，新检测到的威胁将添加到防病毒和反恶意软件引擎，以便其他设备和用户也受到保护。  

如果用户需要执行一些操作（如批准删除恶意文件）时，他们会在收到通知时看到该操作。 若要了解有关用户Microsoft Defender 防病毒用户采取的操作或用户可能需要采取的操作，请参阅[保护历史记录](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)。 若要了解如何以 IT 专业人员/管理员角色管理威胁检测，请参阅查看检测到的威胁 [并采取措施](review-threats-take-action.md)。

若要了解有关不同威胁的信息，请访问Microsoft 安全智能<a href="https://www.microsoft.com/wdsi/threats" target="_blank">威胁站点</a>，可在其中执行以下操作： 

- 查看有关首要威胁的当前信息。
- 查看特定区域的最新威胁。
- 搜索威胁情报场，了解有关特定威胁的详细信息。

## <a name="related-content"></a>相关内容

[安全Windows 10设备](secure-windows-10-devices.md) (文章) \
[评估Microsoft Defender 防病毒 (](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus)文章) \
[How to turn on real-time and cloud-delivered antivirus protection](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (article) \
[如何打开和使用应用Microsoft Defender 防病毒应用Windows 安全中心 (](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)应用) \
[How to turn on Microsoft Defender 防病毒 by using Group Policy](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (article) \
[如何更新防病毒定义 (](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) 文章) \
[如何将恶意软件和非](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) 恶意软件提交给 Microsoft 进行分析 (文章) 
