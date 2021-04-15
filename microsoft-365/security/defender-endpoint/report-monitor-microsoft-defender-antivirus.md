---
title: 监视并报告 Microsoft Defender 防病毒保护
description: 使用 CONFIGURATION Manager 或 SIEM (事件管理) 使用报告，并使用 PowerShell 和 WMI 监视 Microsoft Defender AV。
keywords: siem， 监视器， 报告， Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a31dfa7e5eba36937f4ab50205df938614e80b76
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765763"
---
# <a name="report-on-microsoft-defender-antivirus"></a>关于 Microsoft Defender 防病毒软件的报告

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防病毒内置于 Windows 10、Windows Server 2019 和 Windows Server 2016 中。 Microsoft Defender 防病毒是 Microsoft Defender for Endpoint 中的下一代保护。 下一代保护可帮助保护设备免受电子邮件、应用、云和 Web 中的软件威胁，如病毒、恶意软件和间谍软件。

借助 Microsoft Defender 防病毒，你可以选择多个选项查看保护状态和警报。 可以使用 Microsoft Endpoint Manager [监视 Microsoft Defender 防病毒](/configmgr/protect/deploy-use/monitor-endpoint-protection) 或 [创建电子邮件警报](/configmgr/protect/deploy-use/endpoint-configure-alerts)。 或者，可以使用 [Microsoft Intune](/intune/introduction-intune)监视保护。  

Microsoft Operations Management Suite 具有 [更新](/windows/deployment/update/update-compliance-get-started) 合规性加载项，可报告关键 Microsoft Defender 防病毒问题，包括保护更新和实时保护设置。

如果你拥有 SIEM 服务器的第三方安全 (事件) ，还可以使用Windows Defender [客户端事件](/windows/win32/events/windows-events)。 

Windows 事件包括多个安全事件源，包括安全帐户管理器 (SAM) 事件 ([增强的 Windows 10，](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)另请参阅安全审核主题[](/windows/device-security/auditing/security-auditing-overview)) 和 Windows Defender[事件](troubleshoot-microsoft-defender-antivirus.md)。 

可以使用 Windows 事件收集器集中聚合 [这些事件](/windows/win32/wec/windows-event-collector)。 通常，SIEM 服务器具有适用于 Windows 事件的连接器，从而使你可以关联 SIEM 服务器中的所有安全事件。 

您还可以使用 [Log Analytics 中的恶意软件评估解决方案监视恶意软件事件](/azure/log-analytics/log-analytics-malware)。

有关使用 PowerShell、WMI 或 Microsoft Azure 监视或确定状态的信息，请参阅 ([部署、管理和报告选项表) 。 ](deploy-manage-report-microsoft-defender-antivirus.md#ref2)

## <a name="related-articles"></a>相关文章

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 2016 和 2019 上的 Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md)
- [部署 Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)