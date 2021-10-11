---
title: 监视并报告Microsoft Defender 防病毒保护
description: 使用 CONFIGURATION Manager 或 SIEM (事件) 使用报告，并使用 PowerShell 和 WMI 监视 Microsoft Defender AV。
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
ms.date: 10/11/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 9aecf89ca654bb4f1896fb8f632a72da83f2f1e9
ms.sourcegitcommit: e3b0515fd8f2aad7b8cb308159c7bcecc2bcaa24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2021
ms.locfileid: "60264692"
---
# <a name="report-on-microsoft-defender-antivirus"></a>关于 Microsoft Defender 防病毒软件的报告

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防病毒内置于 Windows 10、Windows Server 2019、Windows Server 2022 和 Windows Server 2016。 Microsoft Defender 防病毒是 Microsoft Defender for Endpoint 中的下一代保护。 下一代保护可帮助保护设备免受电子邮件、应用、云和 Web 中的软件威胁，如病毒、恶意软件和间谍软件。

通过Microsoft Defender 防病毒，你可以查看保护状态和警报的几个选项。 可以使用此Microsoft Endpoint Manager[监视Microsoft Defender 防病毒](/configmgr/protect/deploy-use/monitor-endpoint-protection)[或创建电子邮件警报](/configmgr/protect/deploy-use/endpoint-configure-alerts)。 或者，您可以使用 Microsoft Intune 监视[保护](/intune/introduction-intune)。

如果你拥有 SIEM 服务器的第三方安全 (事件) ，还可以使用Windows Defender[事件](/windows/win32/events/windows-events)。

Windows 事件由多个安全事件源组成，包括安全帐户管理器 (SAM) 事件 ([增强了 Windows 10，](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)另请参阅安全审核主题) 和[Windows Defender 事件](troubleshoot-microsoft-defender-antivirus.md)。 [](/windows/device-security/auditing/security-auditing-overview)

可以使用事件收集器 集中聚合Windows[事件](/windows/win32/wec/windows-event-collector)。 通常，SIEM 服务器具有用于Windows事件的连接器，从而使你可以关联 SIEM 服务器中的所有安全事件。

您还可以使用 [Log Analytics 中的恶意软件评估解决方案监视恶意软件事件](/azure/log-analytics/log-analytics-malware)。

有关使用 PowerShell、WMI 或 Microsoft Azure 监视或确定状态的信息， (部署、管理和报告选项[表) 。 ](deploy-manage-report-microsoft-defender-antivirus.md#ref2)

## <a name="see-also"></a>另请参阅

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 2016 和 2019 上的 Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md)
- [部署Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)
