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
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Microsoft Defender 防病毒检测到的威胁

Microsoft Defender 防病毒保护你的 Windows 设备免受软件威胁（如病毒、恶意软件和间谍软件）的攻击。

- 病毒通常通过将其代码附加到设备或网络上的其他文件来传播，并可能导致受感染的程序无法正常工作。
- 恶意软件包括恶意文件、应用程序和可能导致损坏和破坏正常使用设备的代码。 此外，恶意软件还可以允许未经授权的访问、使用系统资源、窃取密码和帐户信息，并将您锁定在您的计算机上并要求勒索等。
- 间谍软件收集数据（如 web 浏览活动），并将数据发送到远程服务器。
 
为了提供威胁防护，Microsoft Defender 防病毒使用多种方法。 这些方法包括云提供的保护、实时保护和专用的保护更新。

- 云提供的保护有助于提供近乎即时的检测和阻止新的和新兴的威胁。
- Always on 扫描使用文件和进程行为监视和其他技术 (也称为 " *实时保护* ") 。
- 专用的保护更新基于机器学习、人工和自动大型数据分析和深层威胁抵抗研究。 

若要了解有关恶意软件和 Microsoft Defender 防病毒的详细信息，请参阅以下文章： 

- [了解 & 其他威胁的恶意软件](/windows/security/threat-protection/intelligence/understanding-malware)
- [Microsoft 如何识别恶意软件和可能不需要的应用程序](/windows/security/threat-protection/intelligence/criteria)
- [Windows 10 中的下一代保护](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>使用非 Microsoft 防病毒解决方案时会发生什么情况？ 

Microsoft Defender 防病毒是操作系统的一部分，在运行 Windows 10 的设备上启用。 但是，如果您使用的是非 Microsoft 防病毒解决方案，并且没有使用 [Microsoft defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)，则 Microsoft Defender 防病毒将自动进入禁用模式。  

在禁用模式下，用户和客户仍可以使用 Microsoft Defender 防病毒进行计划内或按需扫描以确定威胁;但是，Microsoft Defender 防病毒将不再执行以下操作：

- 用作默认的防病毒应用程序。
- 主动扫描文件以查找威胁。
- 修正或解决威胁。

如果卸载非 Microsoft 防病毒解决方案，Microsoft Defender 防病毒程序将自动进入主动模式，以防止 Windows 设备受到威胁。

> [!TIP]
> - 如果你使用的是 Microsoft 365，请考虑使用 Microsoft Defender 防病毒作为你的主要防病毒解决方案。 集成可提供更好的保护。 [更好地查看： Microsoft Defender 防病毒和 Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)。
> - 确保 Microsoft Defender 防病毒始终保持最新，即使你使用的是非 Microsoft 防病毒解决方案也是如此。

## <a name="what-to-expect-when-threats-are-detected"></a>检测到威胁时的预期行为

当 Microsoft Defender 防病毒检测到威胁时，将会发生以下情况：

- 用户 [在 Windows 中接收通知](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e)。 
- "**保护历史记录**" 页上的 [Windows 安全应用程序](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)中列出了检测项。  
- 如果你已 [对 Windows 10 设备](secure-win-10-pcs.md)进行了保护，并已 [在 Intune 中注册了这些](/mem/intune/enrollment/windows-enrollment-methods)设备，则会在 "**活动威胁**" 页上看到 " <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">microsoft 365 管理中心</a>" 中的威胁检测和见解，可以从 **主页** 上的 **microsoft Defender 防病毒** 卡 (上 **Health** 或通过选择 "  >  **& 防病毒**) 中的" 健康威胁 "来访问导航窗格。
    > [!NOTE]
    > **Microsoft Defender 防病毒** 卡和 **活动威胁** 页面将分阶段推出，因此你可能无法立即访问它们。

在大多数情况下，用户不需要执行任何进一步操作。 一旦在设备上检测到恶意文件或程序，Microsoft Defender 防病毒程序将阻止它运行，并阻止其运行。 此外，新检测到的威胁将添加到防病毒和反恶意软件引擎中，以便其他设备和用户也受到保护。  

如果有用户需要执行的操作（如批准删除恶意文件），他们将在收到的通知中看到。 若要了解有关 Microsoft Defender 防病毒代表用户采取的操作的详细信息，或者用户可能需要执行的操作，请参阅 [保护历史记录](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)。 若要了解如何将威胁检测作为 IT 专业人员/管理员进行管理，请参阅 [查看检测到的威胁并采取措施](review-threats-take-action.md)。

若要了解有关不同威胁的详细信息，请访问 <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft 安全智能威胁网站</a>，在其中可以执行以下操作： 

- 查看有关主要威胁的当前信息。
- 查看特定区域的最新威胁。
- 搜索威胁百科全书以了解有关特定威胁的详细信息。

## <a name="related-content"></a>相关内容

[保护 Windows 10 设备](secure-windows-10-devices.md) (文章) \
[评估 Microsoft Defender 防病毒](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (文章) \
[如何打开实时和云提供的防病毒保护](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (文章) \
[如何在 Windows 安全应用程序中打开和使用 Microsoft Defender 防病毒](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (文章) \
[如何使用组策略打开 Microsoft Defender 防病毒](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (文章) \
[如何更新 (文章) 的防病毒定义](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions)
[如何将恶意软件和非恶意软件提交给 Microsoft 进行分析](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (文章) 