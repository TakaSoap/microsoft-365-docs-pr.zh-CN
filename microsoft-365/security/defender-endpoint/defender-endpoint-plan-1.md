---
title: '适用于终结点计划 1 的 Microsoft Defender 预览 (概述) '
description: 获取适用于 Endpoint Plan 1 的 Defender 的概述。 了解此终结点保护订阅中包含的特性和功能。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 10/29/2021
ms.prod: m365-security
ms.technology: mde
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: e6f02abb96ff04271cfb84fa333b476b7120115f
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111791"
---
# <a name="overview-of-microsoft-defender-for-endpoint-plan-1-preview"></a>适用于终结点计划 1 的 Microsoft Defender 预览 (概述) 

> [!TIP]
> 如果你已Microsoft 365 E3 A3，Microsoft 365 E5或 A5，请访问 [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) 注册预览计划！

Microsoft Defender for Endpoint 是一个企业终结点安全平台，旨在帮助类似你的组织防止、检测、调查和响应高级威胁。 我们很高兴宣布 Defender for Endpoint 现已在两个计划中可用： 

- **Defender for Endpoint Plan 1，** 目前处于预览阶段，本文对此进行了介绍;和 
- **[Defender for Endpoint Plan 2](microsoft-defender-endpoint.md)**， generally available， and formerly known as [Defender for Endpoint](microsoft-defender-endpoint.md).

下图中的绿色框描述了 Defender for Endpoint Plan 1 (预览版) ：

:::image type="content" source="../../media/mde-p1/mde-p1-overview-diagram.png" alt-text="Defender for Endpoint Plan 1 图表":::

使用本指南可：

- [大致了解 Defender for Endpoint Plan 1 (预览版) ](#defender-for-endpoint-plan-1-capabilities)
- [Compare Defender for Endpoint Plan 1 到计划 2](defender-endpoint-plan-1-2.md)
- [了解如何为终结点计划 1 设置和配置 Defender](mde-p1-setup-configuration.md)
- [开始使用 Microsoft 365 Defender 门户，可在其中查看事件和警报、管理设备和使用有关检测到的威胁的报告](mde-plan1-getting-started.md)
- [获取维护和操作概述](mde-p1-maintenance-operations.md)

> [!TIP]
> [详细了解 Defender for Endpoint Plan 1 和 Plan 2 之间的差异](defender-endpoint-plan-1-2.md)。

## <a name="defender-for-endpoint-plan-1-capabilities"></a>Defender for Endpoint Plan 1 功能

Defender for Endpoint Plan 1 (preview) 包括以下功能：

- **[下一代保护](#next-generation-protection)** ，包括行业领先的可靠反恶意软件和防病毒保护
- **[检测到威胁](#manual-response-actions)** 时，安全团队可以对设备或文件执行手动响应操作（如将文件发送到隔离区）
- **[攻击面减少功能](#attack-surface-reduction)** ，可强化设备、防止零时差攻击，并提供对终结点访问和行为精细的控制
- **[集中配置和管理与](#centralized-management)** Microsoft 365 Defender 门户，并集成Microsoft Endpoint Manager
- **[对各种平台的保护](#cross-platform-support)**，包括 Windows、macOS、iOS 和 Android 设备

以下各节提供有关这些功能的更多详细信息。 

> [!IMPORTANT]
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 本指南包含指向在线内容的链接，这些链接可能描述或描述 Defender for Endpoint Plan 1 (预览版中未) 。

## <a name="next-generation-protection"></a>下一代保护

下一代保护包括强大的防病毒和反恶意软件保护。 使用下一代保护，你可以： 

- 基于行为的启发式实时防病毒保护 
- 云提供的保护，包括快速检测和阻止新出现的威胁 
- 专用保护和产品更新，包括与产品相关的Microsoft Defender 防病毒 

若要了解更多信息，请参阅下 [一代保护概述](next-generation-protection.md)。

## <a name="manual-response-actions"></a>手动响应操作

手动响应操作是安全团队在终结点或文件中检测到威胁时可采取的操作。 Defender for Endpoint 包括某些 [可在](respond-machine-alerts.md) 检测到可能受到威胁或包含可疑内容的设备上采取的手动响应操作。 还可以对 [被检测为](respond-file-alerts.md) 威胁的文件运行响应操作。 下表总结了 Defender for Endpoint Plan 1 中提供的手动响应操作。 <br/><br/>

| 文件/设备 | 操作 | 说明 |
|:---|:---|:---|
| 设备 | 运行防病毒扫描 | 启动防病毒扫描。 如果在设备上检测到任何威胁，则防病毒扫描期间通常会解决这些威胁。 |
| Device | 隔离设备 | 断开设备与组织的网络的连接，同时保留与 Defender for Endpoint 的连接。 此操作使你能够监视设备并根据需要执行进一步操作。 |
| 文件 | 停止和隔离 |停止进程运行并隔离关联的文件。 |
| 文件 | 添加用于阻止或允许文件的指示器 | 阻止指示器阻止在设备上读取、写入或执行可移植可执行文件。 <p>允许指示器可防止阻止或修正文件。 |

若要了解更多信息，请参阅以下文章：

- [在设备上执行响应操作](respond-machine-alerts.md) 
- [对文件执行响应操作](respond-file-alerts.md)

## <a name="attack-surface-reduction"></a>攻击面减少

组织的攻击面是易受网络攻击的所有位置。 借助 Defender for Endpoint Plan 1 (预览) ，可以通过保护组织使用的设备和应用程序来减少攻击面。 以下部分介绍了 Defender for Endpoint Plan 1 (预览版) 攻击面减少功能。

- [攻击面减少规则](#attack-surface-reduction-rules)
- [勒索软件缓解](#ransomware-mitigation)
- [设备控制](#device-control)
- [Web 保护功能](#web-protection)
- [网络保护功能](#web-protection)
- [网络防火墙](#network-firewall)
- [应用程序控制](#application-control)

若要了解有关 Defender for Endpoint 中攻击面减少功能有关详细信息，请参阅 [攻击面减少概述](overview-attack-surface-reduction.md)。

### <a name="attack-surface-reduction-rules"></a>攻击面减少规则

攻击面减少规则针对被视为有风险的某些软件行为。 此类行为包括：

- 启动尝试下载或运行其他文件的可执行文件和脚本
- 运行混淆的或可疑的脚本
- 启动应用通常在正常工作期间不启动的行为

合法业务应用程序可以展示此类软件行为;但是，这些行为通常被视为有风险，因为它们通常被攻击者通过恶意软件滥用。 攻击面减少规则可以限制风险行为，并有助于保证组织安全。

若要了解更多信息，请参阅使用 [攻击面减少规则来防止恶意软件感染](attack-surface-reduction.md)。

### <a name="ransomware-mitigation"></a>勒索软件缓解

借助受控文件夹访问权限，你可以获取勒索软件缓解。 受控文件夹访问权限仅允许受信任的应用访问终结点上的受保护文件夹。 根据应用的普遍程度和信誉，将应用添加到受信任的应用列表中。 安全运营团队还可以在受信任的应用列表中添加或删除应用。

若要了解更多信息，请参阅使用受控 [文件夹访问权限保护重要文件夹](controlled-folders.md)。

### <a name="device-control"></a>设备控件

有时，对组织设备的威胁以可移动驱动器（如 USB 驱动器）上的文件的形式出现。 Defender for Endpoint 包括可帮助防止未经授权的外围设备威胁威胁设备的功能。 你可以将 Defender for Endpoint 配置为阻止或允许可移动设备上可移动设备和文件。 

若要了解更多信息，请参阅 [控制 USB 设备和可移动媒体](control-usb-devices-using-intune.md)。

### <a name="web-protection"></a>Web 保护

借助 Web 保护，你可以保护组织设备免受 Web 威胁和不需要的内容。 Web 保护包括 Web 威胁防护和 Web 内容筛选。

- [Web 威胁防护](web-threat-protection.md) 阻止对钓鱼网站、恶意软件矢量、攻击网站、不受信任的或低信誉网站以及您明确阻止的网站的访问。
- [Web 内容筛选](web-content-filtering.md) (预览) 基于其类别阻止访问某些网站。 类别可以包括成人内容、成人网站、法定责任网站等。

若要了解更多信息，请参阅 [Web 保护](web-protection-overview.md)。

### <a name="network-protection"></a>网络保护

借助网络保护，你可以阻止组织访问可能承载 Internet 上的网络钓鱼欺诈、攻击和其他恶意内容危险域。 

若要了解更多信息，请参阅 [保护网络](network-protection.md)。

### <a name="network-firewall"></a>网络防火墙

使用网络防火墙保护，可以设置规则，以确定允许哪些网络流量流入或流出组织设备。 借助使用 Defender for Endpoint 获取的网络防火墙和高级安全，你可以：

- 降低网络安全威胁的风险
- 保护敏感数据和知识产权
- 扩展安全投资

若要了解更多信息，请参阅[Windows Defender高级安全防火墙。](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)

### <a name="application-control"></a>应用程序控制

应用程序控件通过仅在系统核心和内核Windows中运行受信任的应用程序和代码来保护 (终结点) 。 安全团队可以定义考虑应用程序属性的应用程序控制规则，例如其代码签名证书、信誉、启动过程等。 应用程序控件在 Windows 10或更高版本中可用。

若要了解更多信息，请参阅[应用程序控件Windows。](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

## <a name="centralized-management"></a>集中管理

Defender for Endpoint Plan 1 (preview) 包括 Microsoft 365 Defender 门户，使安全团队能够查看有关检测到的威胁的当前信息，采取适当的措施缓解威胁，并集中管理组织的威胁防护设置。

若要了解更多信息，请参阅[Microsoft 365 Defender门户概述](portal-overview.md)。

### <a name="role-based-access-control"></a>基于角色的访问控制

通过使用基于角色的访问控制 (RBAC) ，安全管理员可以创建角色和组，以授予对 Microsoft 365 Defender 门户 [https://security.microsoft.com](https://security.microsoft.com) () 。 借助 RBAC，你可以精细控制谁可以访问 Defender for Cloud，以及他们可以看到和执行哪些操作。 

若要了解更多信息，请参阅 [使用基于角色的访问控制管理门户访问](rbac.md)。

### <a name="reporting"></a>报表

通过Microsoft 365 Defender门户 () 可轻松访问有关检测到的威胁和操作的信息 [https://security.microsoft.com](https://security.microsoft.com) ，以解决这些威胁。 

- **主页** 包含卡片，可一目了然地显示哪些用户或设备处于风险中、检测到的威胁数量以及创建哪些警报/事件。
- **"事件&** 警报"部分列出了因触发的警报而创建的任何事件。 当跨设备检测到威胁时，将生成警报和事件。
- 操作 **中心** 列出了已采取的修正操作。 例如，如果文件被发送到隔离区，或 URL 被阻止，每个操作都列在"历史记录"选项卡上的"操作 **中心** "中。
- " **报告** "部分包括显示检测到的威胁及其状态的报告。 

若要了解的详细信息，请参阅 Microsoft Defender 终结点计划[1 (预览版) 。 ](mde-plan1-getting-started.md)

### <a name="apis"></a>API

使用 Defender for Endpoint API，可以自动执行工作流，并与组织的自定义解决方案集成。 

若要了解更多信息，请参阅[适用于终结点 API 的 Defender。](management-apis.md) 

## <a name="cross-platform-support"></a>跨平台支持

大多数组织使用各种设备和操作系统。 目前，Defender for Endpoint Plan 1 (preview) 支持以下操作系统：

- Windows 10版本 1709 或更高版本
- macOS：11.5 (Big Sur) 、10.15.7 (加泰罗尼亚语) 或 10.14.6 (Mojave) 
- iOS
- Android OS

## <a name="next-steps"></a>后续步骤

- [比较 Microsoft Defender for Endpoint Plan 1 (preview) To Plan 2](defender-endpoint-plan-1-2.md)
- [为终结点计划 1 设置和配置 Defender (预览) ](mde-p1-setup-configuration.md)
- [适用于终结点计划 1 的 Defender (预览版) ](mde-plan1-getting-started.md)
- [管理 Defender for Endpoint Plan 1 (预览) ](mde-p1-maintenance-operations.md)
