---
title: 监视和报告Microsoft Defender 防病毒保护
description: 使用 Configuration Manager 或安全信息以及事件管理 (SIEM) 工具使用报表，并使用 PowerShell 和 WMI 监视 Microsoft Defender AV。
keywords: siem， monitor， report， Microsoft Defender AV
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: b6593784b0df1109eb7729b3df91ef467d30c4bb
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788405"
---
# <a name="report-on-microsoft-defender-antivirus"></a>关于 Microsoft Defender 防病毒软件的报告

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

Microsoft Defender 防病毒内置于 Windows 10、Windows 11、Windows Server 2019、Windows Server 2022 和 Windows Server 2016 中。 Microsoft Defender 防病毒是Microsoft Defender for Endpoint中的下一代保护。 下一代保护有助于保护设备免受软件威胁，例如电子邮件、应用、云和 Web 中的病毒、恶意软件和间谍软件。

使用Microsoft Defender 防病毒，你可以使用多个选项来查看保护状态和警报。 可以使用Microsoft Endpoint Manager[监视Microsoft Defender 防病毒](/configmgr/protect/deploy-use/monitor-endpoint-protection)或[创建电子邮件警报](/configmgr/protect/deploy-use/endpoint-configure-alerts)。 或者，可以使用[Microsoft Intune](/intune/introduction-intune)监视保护。

如果在 SIEM) 服务器 (具有第三方安全信息和事件管理，则还可以使用[Windows Defender客户端事件](/windows/win32/events/windows-events)。

Windows事件包括多个安全事件源，包括安全帐户管理器 (SAM) 事件 ([增强Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)，还请参阅[安全审核](/windows/device-security/auditing/security-auditing-overview)主题) 和[Windows Defender事件](troubleshoot-microsoft-defender-antivirus.md)。

可以使用[Windows事件收集器](/windows/win32/wec/windows-event-collector)集中聚合这些事件。 通常，SIEM 服务器具有用于Windows事件的连接器，使你能够关联 SIEM 服务器中的所有安全事件。

还可以 [使用 Log Analytics 中的恶意软件评估解决方案监视恶意软件事件](/azure/log-analytics/log-analytics-malware)。

若要使用 PowerShell、WMI 或 Microsoft Azure 监视或确定状态，请参阅[ (部署、管理和报告选项表) ](deploy-manage-report-microsoft-defender-antivirus.md#ref2)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="see-also"></a>另请参阅

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [部署Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)
