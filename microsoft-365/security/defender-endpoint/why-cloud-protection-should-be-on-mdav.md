---
title: 为什么应为云保护启用Microsoft Defender 防病毒
description: 了解为什么应该为云保护启用Microsoft Defender 防病毒。 它可以帮助 Microsoft Defender for Endpoint 中的许多安全功能工作
keywords: Microsoft Defender 防病毒， 云保护， 安全功能， 示例提交
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
ms.openlocfilehash: 65bd7dd0a494cd5b68216265015e80f1f003a5cb
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64467062"
---
# <a name="why-cloud-protection-should-be-enabled-for-microsoft-defender-antivirus"></a>为什么应为云保护启用Microsoft Defender 防病毒

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

Microsoft Defender 防病毒云保护有助于在终结点和整个网络中抵御恶意软件。 我们建议启用云保护，因为 Microsoft Defender for Endpoint 中的某些安全功能仅在启用云保护时可用。 

[![alt-text="显示依赖于云保护的内容的关系图](images/mde-cloud-protection.png#lightbox)](enable-cloud-protection-microsoft-defender-antivirus.md)

下表总结了依赖于云保护的特性和功能： <br/><br/>

| 功能  | 订阅要求 |  说明  |
|---------|---------|--------|
| 检查云中的元数据  | Microsoft Defender for Endpoint Plan 1 或 Plan 2 (Standalone 或包含在计划（如 Microsoft 365 E3 或 E5)  | 云服务Microsoft Defender 防病毒机器学习模型作为额外防护层。 这些机器学习模型包括元数据，因此当检测到可疑或恶意文件时，将检查其元数据。 <br/><br/>若要了解更多信息，请参阅博客：了解 [Microsoft Defender for Endpoint](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/) 下一代保护的核心高级技术  |
| 云保护和示例提交 | Microsoft Defender for Endpoint Plan 1 或 Plan 2 (Standalone 或包含在计划（如 Microsoft 365 E3 或 E5)  | 文件和可执行文件可以发送到 Microsoft Defender 防病毒 云服务进行触发和分析。 <br/><br/>若要了解更多信息，请参阅云[保护和 Microsoft Defender 防病毒 中的示例提交](cloud-protection-microsoft-antivirus-sample-submission.md)。<br/><br/>**注意**：自动提交示例依赖于云保护，但也可以配置为独立设置。         |
| 防篡改保护 | Microsoft Defender for Endpoint Plan 2 (独立版或包含在计划（如 Microsoft 365 E5) ） | 篡改保护可帮助防止对组织的安全设置进行不必要的更改。 若要在门户中强制执行Microsoft 365 Defender保护，必须启用云保护。 <br/><br/>若要了解更多信息，请参阅使用防篡改 [保护保护安全设置](prevent-changes-to-security-settings-with-tamper-protection.md)。        |
| 首次看到时阻止 | Microsoft Defender for Endpoint Plan 1 或 Plan 2 (Standalone 或包含在计划（如 Microsoft 365 E3 或 E5)  | "首次看到时阻止"检测到新的恶意软件，并会在数秒钟内阻止它。 当检测到可疑或恶意文件时，"首次看到时阻止"功能会查询云保护后端，并应用启发式、机器学习和自动分析文件，以确定它是否是威胁。<br/><br/>若要了解更多信息， [请参阅什么是"首次看到时阻止"？](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)   |
| 紧急签名更新 | Microsoft Defender for Endpoint Plan 2 (独立版或包含在计划（如 Microsoft 365 E5) ） | 检测到恶意内容时，将部署紧急签名更新和修复。 你可以几分钟内收到这些修补程序和更新，而不是等待下一次定期更新。   |
| 阻止模式下的终结点检测和响应 (EDR)。 | Microsoft Defender for Endpoint Plan 2 (独立版或包含在计划（如 Microsoft 365 E5) ） | EDR阻止模式时，如果Microsoft Defender 防病毒不是设备上的主要防病毒产品，则提供额外保护。 EDR模式扫描会修正在EDR扫描过程中发现的非 Microsoft 主防病毒解决方案可能错过的项目。 当为以 Microsoft Defender 防病毒 作为主要防病毒解决方案的设备启用时，EDR模式提供自动修正在EDR扫描期间标识的项目的附加优势。 <br/><br/>若要了解更多信息，请参阅EDR[阻止模式。](edr-in-block-mode.md)|
| 攻击面减少规则 | Microsoft Defender for Endpoint Plan 1 或 Plan 2 (Standalone 或包含在计划（如 Microsoft 365 E3 或 E5)  | 减少攻击面与减少组织的终结点易受网络攻击的位置和方式有关。 攻击面减少规则是可配置以帮助阻止恶意软件的智能规则。 某些规则要求启用云保护才能完全运行。 这些规则包括： <br/>- 阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件 <br/>- 使用高级防护抵御勒索软件 <br/>- 阻止不受信任的程序从可移动驱动器运行 <br/><br/>若要了解更多信息，请参阅使用 [攻击面减少规则来防止恶意软件感染](attack-surface-reduction.md)。  |
| ICS (泄露)  | Microsoft Defender for Endpoint Plan 2 (独立版或包含在计划（如 Microsoft 365 E5) ） | Defender for Endpoint 中的 IoCs 可以配置为定义实体的检测、防护和排除。 例如，"允许"指示器可用于在 Defender for Endpoint 中定义Microsoft Defender 防病毒扫描和修正操作。 另一个示例是，"警报和阻止"指示器可用于阻止文件或进程执行，并跟踪这些活动以及可在 Microsoft 365 Defender 门户中查看的警报。 <br/><br/>若要了解更多信息，请参阅 [创建指示器](manage-indicators.md)。    |

> [!TIP]
> 若要详细了解 Defender for Endpoint 计划，请参阅适用于终结点计划的 [Microsoft Defender 计划 1 和计划 2](defender-endpoint-plan-1-2.md)。

## <a name="next-steps"></a>后续步骤

至此，你已大致了解云保护及其在Microsoft Defender 防病毒中的角色，下面介绍了一些下一步：

1. **[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)**。 你可以启用云保护，Microsoft Endpoint Manager (现在包括 Microsoft Endpoint Configuration Manager 和 Microsoft Intune) 、组策略或 PowerShell cmdlet。

2. **[指定云保护级别](specify-cloud-protection-level-microsoft-defender-antivirus.md)**。 可以使用组策略或组策略指定云Microsoft Endpoint Manager级别。 保护级别将影响与云共享的信息量以及阻止新文件的级别。

3. **[配置并验证 Microsoft Defender 防病毒](configure-network-connections-microsoft-defender-antivirus.md)**。 你的网络和终结点必须能够连接到某些 Microsoft URL，云保护才能有效工作。 本文列出了防火墙或网络筛选规则应允许的 URL，以及用于确认网络在云保护中正确注册的说明。

4. **[配置"首次看到时阻止"功能](configure-block-at-first-sight-microsoft-defender-antivirus.md)**。 "首次看到时阻止"功能可以在数秒钟内阻止新恶意软件，而无需等待数小时即可获得传统安全智能。 可以使用组策略或组策略Microsoft Endpoint Manager和配置它。

5. **[配置云阻止超时时段](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)**。 Microsoft Defender 防病毒查询云保护服务时阻止可疑文件运行。 可以使用组策略或组策略配置阻止文件Microsoft Endpoint Manager的时间。
