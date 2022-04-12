---
title: 为何应为Microsoft Defender 防病毒启用云保护
description: 了解为何应为Microsoft Defender 防病毒启用云保护。 它有助于Microsoft Defender for Endpoint工作中的许多安全功能
keywords: Microsoft Defender 防病毒、云保护、安全功能、示例提交
search.product: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 10/22/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 6a0667e52474fe5e04f547d12b1f53ca47c6ea6e
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787569"
---
# <a name="why-cloud-protection-should-be-enabled-for-microsoft-defender-antivirus"></a>为何应为Microsoft Defender 防病毒启用云保护

**适用于：**

- Microsoft Defender 防病毒
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**平台**
- Windows

Microsoft Defender 防病毒云保护有助于防范终结点上和整个网络上的恶意软件。 我们建议启用云保护，因为Microsoft Defender for Endpoint某些安全功能仅在启用云保护时才有效。 

[![alt-text=“显示依赖于云保护的东西的图表](images/mde-cloud-protection.png#lightbox)](enable-cloud-protection-microsoft-defender-antivirus.md)

下表汇总了依赖于云保护的功能： <br/><br/>

| 功能/功能  | 订阅要求 |  说明  |
|---------|---------|--------|
| 检查云中的元数据  | Microsoft Defender for Endpoint计划 1 或计划 2 (独立或包含在计划中，如 Microsoft 365 E3 或 E5)  | Microsoft Defender 防病毒云服务使用机器学习模型作为额外的防御层。 这些机器学习模型包括元数据，因此当检测到可疑或恶意文件时，会检查其元数据。 <br/><br/>若要了解详细信息，请参阅[博客：了解Microsoft Defender for Endpoint下一代保护的核心先进技术](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)  |
| 云保护和示例提交 | Microsoft Defender for Endpoint计划 1 或计划 2 (独立或包含在计划中，如 Microsoft 365 E3 或 E5)  | 文件和可执行文件可以发送到Microsoft Defender 防病毒云服务进行引爆和分析。 <br/><br/>若要了解详细信息，请参阅[Microsoft Defender 防病毒中的云保护和示例提交](cloud-protection-microsoft-antivirus-sample-submission.md)。<br/><br/>**注意**：自动示例提交依赖于云保护，但也可以将其配置为独立设置。         |
| 篡改保护 | Microsoft Defender for Endpoint计划 2 (独立或包含在计划中，如Microsoft 365 E5)  | 篡改防护有助于防止对组织的安全设置进行不必要的更改。 若要在Microsoft 365 Defender门户中强制实施篡改保护，必须启用云保护。 <br/><br/>若要了解详细信息，请参阅使用 [篡改保护保护安全设置](prevent-changes-to-security-settings-with-tamper-protection.md)。        |
| 首次看到时阻止 | Microsoft Defender for Endpoint计划 1 或计划 2 (独立或包含在计划中，如 Microsoft 365 E3 或 E5)  | 首次看到时阻止会检测到新的恶意软件，并在几秒钟内阻止它。 检测到可疑或恶意文件时，首次看到时阻止功能会查询云保护后端，并应用启发式、机器学习和自动分析文件，以确定它是否为威胁。<br/><br/>若要了解详细信息，请参阅 [什么是“一见钟情”？](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)   |
| 紧急签名更新 | Microsoft Defender for Endpoint计划 2 (独立或包含在计划中，如Microsoft 365 E5)  | 检测到恶意内容时，将部署紧急签名更新和修复。 你可以在几分钟内收到这些修补程序和更新，而不是等待下一次常规更新。   |
| 阻止模式下的终结点检测和响应 (EDR)。 | Microsoft Defender for Endpoint计划 2 (独立或包含在计划中，如Microsoft 365 E5)  | 当Microsoft Defender 防病毒不是设备上的主要防病毒产品时，EDR在块模式下提供额外的保护。 EDR在块模式下修正在EDR生成的扫描期间发现的非 Microsoft 主要防病毒解决方案可能遗漏的项目。 为Microsoft Defender 防病毒作为主要防病毒解决方案的设备启用时，在块模式下EDR可提供在EDR生成的扫描过程中自动修正识别的项目的额外好处。 <br/><br/>若要了解详细信息，请参阅[阻止模式下的EDR](edr-in-block-mode.md)。|
| 攻击面减少规则 | Microsoft Defender for Endpoint计划 1 或计划 2 (独立或包含在计划中，如 Microsoft 365 E3 或 E5)  | 减少攻击面就是减少组织的终结点容易受到网络攻击的位置和方式。 攻击面减少规则是可配置的智能规则，可帮助阻止恶意软件。 某些规则要求启用云保护才能完全正常运行。 这些规则包括： <br/>- 阻止可执行文件运行，除非它们满足普遍性、年龄或受信任的列表条件 <br/>- 对勒索软件使用高级保护 <br/>- 阻止不受信任的程序从可移动驱动器运行 <br/><br/>若要了解详细信息，请参阅 [使用攻击面减少规则来防止恶意软件感染](attack-surface-reduction.md)。  |
| IoC () 泄露指标 | Microsoft Defender for Endpoint计划 2 (独立或包含在计划中，如Microsoft 365 E5)  | 可以将 Defender for Endpoint 中的 IoC 配置为定义实体的检测、预防和排除。 例如，“allow”指示器可用于定义在 Defender for Endpoint 中Microsoft Defender 防病毒扫描和修正操作的异常。 另一个例子是，“警报和阻止”指示器可用于防止文件或进程执行，并使用可在Microsoft 365 Defender门户中查看的警报跟踪这些活动。 <br/><br/>若要了解详细信息，请参阅 [“创建指示器](manage-indicators.md)”。    |

> [!TIP]
> 若要详细了解 Defender for Endpoint 计划，[请参阅Microsoft Defender for Endpoint计划 1 和计划 2](defender-endpoint-plan-1-2.md)。

## <a name="next-steps"></a>后续步骤

现在，你已概述了云保护及其在Microsoft Defender 防病毒中的作用，下面是一些后续步骤：

1. **[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)**。 可以使用Microsoft Endpoint Manager (启用云保护，现在包括Microsoft Endpoint Configuration Manager和Microsoft Intune) 、组策略或 PowerShell cmdlet。

2. **[指定云保护级别](specify-cloud-protection-level-microsoft-defender-antivirus.md)**。 可以使用Microsoft Endpoint Manager或组策略指定云提供的保护级别。 保护级别会影响与云共享的信息量，以及新文件的阻止程度。

3. **[配置和验证Microsoft Defender 防病毒的网络连接](configure-network-connections-microsoft-defender-antivirus.md)**。 网络和终结点必须能够连接到某些 Microsoft URL，才能有效地运行云保护。 本文列出了应通过防火墙或网络筛选规则允许的 URL，以及有关确认网络在云保护中正确注册的说明。

4. **[配置“一见钟情”功能](configure-block-at-first-sight-microsoft-defender-antivirus.md)**。 “一见钟情”功能可以在几秒钟内阻止新的恶意软件，而无需等待数小时才能获得传统安全智能。 可以使用Microsoft Endpoint Manager或组策略来启用和配置它。

5. **[配置云块超时期](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)**。 Microsoft Defender 防病毒可以在查询云保护服务时阻止可疑文件运行。 可以使用Microsoft Endpoint Manager或组策略来配置阻止文件运行的时间。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)