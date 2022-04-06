---
title: Microsoft Defender for Endpoint计划 1 概述
description: 获取 Defender for Endpoint Plan 1 的概述。 了解此终结点保护订阅中包含的功能和功能。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 01/19/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.custom: intro-overview
ms.openlocfilehash: 774d54aee080fbe3d6f5576fb29c85d887717b70
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663503"
---
# <a name="overview-of-microsoft-defender-for-endpoint-plan-1"></a>Microsoft Defender for Endpoint计划 1 概述

**适用对象**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint是一个企业终结点安全平台，旨在帮助像你这样的组织防止、检测、调查和响应高级威胁。 我们很高兴地宣布，Defender for Endpoint 现已在两个计划中提供： 

- **Defender for Endpoint Plan 1**，本文介绍;和 
- **[Defender for Endpoint Plan 2](microsoft-defender-endpoint.md)** 正式发布，以前称为 [Defender for Endpoint](microsoft-defender-endpoint.md)。

下图中的绿色框描绘了 Defender for Endpoint Plan 1 中包含的内容：

:::image type="content" source="../../media/mde-p1/mde-p1-overview-diagram.png" alt-text="Defender for Endpoint Plan 1 中灌输的内容" lightbox="../../media/mde-p1/mde-p1-overview-diagram.png":::

使用本指南可执行以下操作：

- [获取 Defender for Endpoint Plan 1 中包含的内容的概述](#defender-for-endpoint-plan-1-capabilities)
- [Compare Defender for Endpoint Plan 1 到计划 2](defender-endpoint-plan-1-2.md)
- [了解如何设置和配置 Defender for Endpoint Plan 1](mde-p1-setup-configuration.md)
- [开始使用Microsoft 365 Defender门户，可在其中查看事件和警报、管理设备以及使用有关检测到的威胁的报告](mde-plan1-getting-started.md)
- [获取维护和操作概述](mde-p1-maintenance-operations.md)

> [!TIP]
> [详细了解 Defender for Endpoint Plan 1 和 Plan 2 之间的差异](defender-endpoint-plan-1-2.md)。

## <a name="defender-for-endpoint-plan-1-capabilities"></a>Defender for Endpoint Plan 1 功能

Defender for Endpoint Plan 1 包括以下功能：

- **[下一代保护](#next-generation-protection)** ，包括行业领先、强大的反恶意软件和防病毒保护
- **[手动响应操作](#manual-response-actions)**，例如将文件发送到隔离区，安全团队可以在检测到威胁时对设备或文件执行这些操作
- **[攻击面减少功能](#attack-surface-reduction)** ，可强化设备、防止零天攻击，并提供对终结点访问和行为的精细控制
- 使用Microsoft 365 Defender门户进行 **[集中式配置和管理](#centralized-management)**，并与Microsoft Endpoint Manager集成
- **[针对各种平台（](#cross-platform-support)** 包括 Windows、macOS、iOS 和 Android 设备）的保护

以下部分提供有关这些功能的更多详细信息。 

## <a name="next-generation-protection"></a>下一代保护

下一代保护包括可靠的防病毒和反恶意软件保护。 通过下一代保护，可以： 

- 基于行为、启发式和实时防病毒保护 
- 云提供的保护，包括近乎即时的检测和阻止新威胁和新出现的威胁 
- 专用保护和产品更新，包括与Microsoft Defender 防病毒相关的更新 

若要了解详细信息，请参阅 [下一代保护概述](next-generation-protection.md)。

## <a name="manual-response-actions"></a>手动响应操作

手动响应操作是安全团队在终结点或文件中检测到威胁时可以执行的操作。 Defender for Endpoint 包括某些 [手动响应操作，这些操作可在](respond-machine-alerts.md) 检测到可能泄露或具有可疑内容的设备上执行。 还可以对检测为威胁 [的文件运行响应操作](respond-file-alerts.md) 。 下表汇总了 Defender for Endpoint Plan 1 中可用的手动响应操作。 <br/><br/>

| 文件/设备 | 操作 | 说明 |
|:---|:---|:---|
| Device | 运行防病毒扫描 | 启动防病毒扫描。 如果在设备上检测到任何威胁，这些威胁通常会在防病毒扫描期间得到解决。 |
| Device | 隔离设备 | 断开设备与组织的网络的连接，同时保留与 Defender for Endpoint 的连接。 此操作使你能够监视设备，并在需要时采取进一步操作。 |
| 文件 | 停止和隔离 |停止进程运行并隔离关联的文件。 |
| 文件 | 添加指示器以阻止或允许文件 | 阻止指示器阻止在设备上读取、写入或执行可移植可执行文件。 <p>允许指示器阻止阻止或修正文件。 |

若要了解详细信息，请参阅以下文章：

- [在设备上执行响应操作](respond-machine-alerts.md) 
- [对文件执行响应操作](respond-file-alerts.md)

## <a name="attack-surface-reduction"></a>攻击面减少

组织的攻击面都是你容易受到网络攻击的地方。 使用 Defender for Endpoint Plan 1，可以通过保护组织使用的设备和应用程序来减少攻击面。 以下部分介绍了 Defender for Endpoint Plan 1 中包含的攻击面减少功能。

- [攻击面减少规则](#attack-surface-reduction-rules)
- [勒索软件缓解](#ransomware-mitigation)
- [设备控制](#device-control)
- [Web 保护功能](#web-protection)
- [网络保护功能](#web-protection)
- [网络防火墙](#network-firewall)
- [应用程序控制](#application-control)

若要详细了解 Defender for Endpoint 中的攻击面减少功能，请参 [阅攻击面减少概述](overview-attack-surface-reduction.md)。

### <a name="attack-surface-reduction-rules"></a>攻击面减少规则

攻击面减少规则针对某些被视为有风险的软件行为。 此类行为包括：

- 启动尝试下载或运行其他文件的可执行文件和脚本
- 运行模糊或以其他方式可疑的脚本
- 启动应用通常不会在正常工作期间启动的行为

合法的业务应用程序可以展示此类软件行为;但是，这些行为通常被认为是有风险的，因为它们通常通过恶意软件被攻击者滥用。 攻击面减少规则可以限制有风险的行为，并有助于确保组织的安全。

若要了解详细信息，请参阅 [使用攻击面减少规则来防止恶意软件感染](attack-surface-reduction.md)。

### <a name="ransomware-mitigation"></a>勒索软件缓解

通过受控文件夹访问，可获得勒索软件缓解。 受控文件夹访问仅允许受信任的应用访问终结点上受保护的文件夹。 应用会根据应用的流行程度和信誉添加到受信任的应用列表中。 安全运营团队也可以从受信任的应用列表中添加或删除应用。

若要了解详细信息，请参阅 [使用受控文件夹访问保护重要文件夹](controlled-folders.md)。

### <a name="device-control"></a>设备控件

有时，对组织设备的威胁以可移动驱动器（如 USB 驱动器）上的文件形式出现。 Defender for Endpoint 包括有助于防止来自未经授权外围设备的威胁损害设备的功能。 可以将 Defender for Endpoint 配置为阻止或允许可移动设备和可移动设备上的文件。 

若要了解详细信息，请参阅 [控制 USB 设备和可移动媒体](control-usb-devices-using-intune.md)。

### <a name="web-protection"></a>Web 保护

通过 Web 保护，可以保护组织的设备免受 Web 威胁和不需要的内容。 Web 保护包括 Web 威胁防护和 Web 内容筛选。

- [Web 威胁防护](web-threat-protection.md) 可阻止访问网络钓鱼网站、恶意软件向量、攻击网站、不受信任或低信誉网站以及显式阻止的网站。
- [Web 内容筛选](web-content-filtering.md) 会阻止基于其类别访问某些网站。 类别可以包括成人内容、休闲场所、法律责任网站等。

若要了解详细信息，请参阅 [Web 保护](web-protection-overview.md)。

### <a name="network-protection"></a>网络保护

通过网络保护，可以防止组织访问可能在 Internet 上托管网络钓鱼诈骗、攻击和其他恶意内容的危险域。 

若要了解详细信息，请参阅 ["保护网络](network-protection.md)"。

### <a name="network-firewall"></a>网络防火墙

通过网络防火墙保护，可以设置规则，确定允许哪些网络流量流向或流出组织的设备。 使用 Defender for Endpoint 获取的网络防火墙和高级安全性，可以：

- 降低网络安全威胁的风险
- 保护敏感数据和知识产权
- 扩展安全投资

若要了解详细信息，请参阅[Windows Defender具有高级安全性的防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。

### <a name="application-control"></a>应用程序控制

应用程序控制仅在系统核心 (内核) 中运行受信任的应用程序和代码，从而保护Windows终结点。 安全团队可以定义考虑应用程序属性的应用程序控制规则，例如其编码证书、信誉、启动过程等。 应用程序控件在Windows 10或更高版本中可用。

若要了解详细信息，请参阅[Windows的应用程序控件](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)。

## <a name="centralized-management"></a>集中管理

Defender for Endpoint Plan 1 包括Microsoft 365 Defender门户，使安全团队能够查看有关检测到的威胁的当前信息、采取适当措施来缓解威胁，以及集中管理组织的威胁防护设置。

若要了解详细信息，请参阅[Microsoft 365 Defender门户概述](portal-overview.md)。

### <a name="role-based-access-control"></a>基于角色的访问控制

使用基于角色的访问控制 (RBAC) ，安全管理员可以创建角色和组，以授予对 Microsoft 365 Defender 门户 () [https://security.microsoft.com](https://security.microsoft.com) 的适当访问权限。 使用 RBAC，你可以对谁可以访问Defender for Cloud以及他们可以看到和执行的操作进行精细控制。 

若要了解详细信息，请参阅 [使用基于角色的访问控制管理门户访问](rbac.md)。

### <a name="reporting"></a>Reporting

Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 可以轻松访问有关检测到的威胁和应对这些威胁的操作的信息。 

- **主** 页包含一些卡片，一目了然地显示哪些用户或设备处于危险之中，检测到多少威胁，以及创建了哪些警报/事件。
- " **事件&警报** "部分列出了因触发的警报而创建的任何事件。 警报和事件在设备之间检测到威胁时生成。
- **操作中心** 列出了已执行的修正操作。 例如，如果将文件发送到隔离区或阻止 URL，则每个操作都列在 **"历史记录** "选项卡上的操作中心。
- " **报表** "部分包含显示检测到的威胁及其状态的报表。 

若要了解详细信息，请参阅[Microsoft Defender for Endpoint计划 1 的开始](mde-plan1-getting-started.md)。

### <a name="apis"></a>API

借助 Defender for Endpoint API，可以自动执行工作流并与组织的自定义解决方案集成。 

若要了解详细信息，请参阅 [Defender for Endpoint API](management-apis.md)。 

## <a name="cross-platform-support"></a>跨平台支持

大多数组织使用各种设备和操作系统。 目前，Defender for Endpoint Plan 1 支持以下操作系统：

- Windows 7 (ESU 必需) 
- Windows 8.1
- Windows 10版本 1709 或更高版本
- macOS： 11.5 (Big Sur) ， 10.15.7 (Catalina) ， 或 10.14.6 (Mojave) 
- iOS
- Android OS

## <a name="next-steps"></a>后续步骤

- [将Microsoft Defender for Endpoint计划 1 与计划 2 进行比较](defender-endpoint-plan-1-2.md)
- [设置和配置 Defender for Endpoint 计划 1](mde-p1-setup-configuration.md)
- [使用 Defender for Endpoint Plan 1 开始](mde-plan1-getting-started.md)
- [管理 Defender for Endpoint Plan 1](mde-p1-maintenance-operations.md)
