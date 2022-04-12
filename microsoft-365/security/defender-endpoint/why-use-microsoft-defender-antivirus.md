---
title: 为何应将Microsoft Defender 防病毒与Microsoft Defender for Endpoint一起使用
description: 为了获得最佳结果，请将Microsoft Defender 防病毒与其他 Microsoft 产品/服务一起使用。
keywords: windows defender， 防病毒， 第三方 av
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: afb8a113ca6257164524027dacd9ce38765e5812
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790297"
---
# <a name="better-together-microsoft-defender-antivirus-and-microsoft-defender-for-endpoint"></a>更好地结合：Microsoft Defender 防病毒软件和 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

Microsoft Defender 防病毒是[Microsoft Defender for Endpoint (Microsoft Defender for Endpoint) ](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)的下一代保护组件。

尽管可以将非 Microsoft 防病毒解决方案与Microsoft Defender for Endpoint结合使用，但将Microsoft Defender 防病毒与 Defender for Endpoint 结合使用是有优势的。 不仅Microsoft Defender 防病毒优秀的下一代防病毒解决方案，而且与其他 Defender for Endpoint 功能（如[终结点检测和响应](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)和[自动调查和修正）](/microsoft-365/security/defender-endpoint/automated-investigations)结合使用，可以获得跨产品和服务协调的更好的保护。

## <a name="11-reasons-to-use-microsoft-defender-antivirus-together-with-microsoft-defender-for-endpoint"></a>将Microsoft Defender 防病毒与Microsoft Defender for Endpoint结合使用的 11 个原因

|#|优点|为什么它很重要|
|--|--|--|
|1|防病毒信号共享|Microsoft 应用程序和服务在企业组织中共享信号，提供更强大的单一平台。 请参阅 [MITRE ATT&基于 CK 的Microsoft Defender for Endpoint评估中的Insights](https://www.microsoft.com/security/blog/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。|
|2|威胁分析和设备分数|Microsoft Defender 防病毒收集[威胁分析](/microsoft-365/security/defender-endpoint/threat-analytics)和 [Microsoft Secure Score for Devices](/microsoft-365/security/defender-endpoint/tvm-microsoft-secure-score-devices) 使用的基础系统数据。 这为组织的安全团队提供了更有意义的信息，例如建议和改进组织安全状况的机会。|
|3|性能|Microsoft Defender for Endpoint设计用于Microsoft Defender 防病毒，因此在一起使用这些产品/服务时，可以获得更好的性能。 [评估Microsoft Defender 防病毒](evaluate-microsoft-defender-antivirus.md)和[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/evaluate-mde)。|
|4|有关已阻止的恶意软件的详细信息|有关已阻止恶意软件的更多详细信息和操作，Microsoft Defender 防病毒和Microsoft Defender for Endpoint。 [了解恶意软件&其他威胁](/windows/security/threat-protection/intelligence/understanding-malware)。|
|5|网络保护|组织的安全团队可以通过阻止特定 URL 和 IP 地址来保护网络。 [保护网络](/microsoft-365/security/defender-endpoint/network-protection)。|
|6 |文件阻止|组织的安全团队可以阻止特定文件。 [在网络中停止和隔离文件](/microsoft-365/security/defender-endpoint/respond-file-alerts#stop-and-quarantine-files-in-your-network)。|
|7 |攻击面减少|组织的安全团队可以减少攻击面)  (漏洞，从而减少攻击者执行攻击的方法。 攻击面减少对许多规则使用云保护。 [获取攻击面减少的概述](/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction)。|
|8 |审核事件|审核事件信号在[终结点检测和响应功能](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)中可用。  (这些信号在非 Microsoft 防病毒解决方案中不可用。) |
|9 |地理数据|符合 ISO 270001和数据保留，地理数据是根据组织选择的地理主权提供的。 请参阅 [符合性产品/服务：ISO/IEC 27001：2013 信息安全管理标准](/microsoft-365/compliance/offering-iso-27001)。|
|10 |通过OneDrive进行文件恢复|如果将Microsoft Defender 防病毒与[Office 365](/Office365/Enterprise)一起使用，并且设备受到勒索软件的攻击，则文件会受到保护和恢复。 [OneDrive文件还原和Windows Defender更进一步地保护勒索软件](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/OneDrive-Files-Restore-and-Windows-Defender-takes-ransomware/ba-p/188001)。|
|11|技术支持|通过将Microsoft Defender for Endpoint与Microsoft Defender 防病毒一起使用，你拥有一家公司来请求技术支持。 [排查服务问题](/microsoft-365/security/defender-endpoint/troubleshoot-mdatp)，并[使用Microsoft Defender 防病毒查看事件日志和错误代码](troubleshoot-microsoft-defender-antivirus.md)。|

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="learn-more"></a>了解详细信息

[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

[威胁&漏洞管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
