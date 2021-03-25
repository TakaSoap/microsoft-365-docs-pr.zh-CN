---
title: 从 Symantec 迁移到 Microsoft Defender for Endpoint
description: 大致了解如何从 Symantec 切换到 Microsoft Defender for Endpoint
keywords: 迁移， windows defender 高级威胁防护， atp， edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 6517359c805bb449d075e401283a79a791461630
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218776"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>从 Symantec 迁移到 Microsoft Defender for Endpoint
如果你计划从 Symantec Endpoint Protection (Symantec) 切换到适用于 Endpoint (的 [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) for Endpoint) ，你的位置正确。 使用本文作为指南。

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="从 Symantec 迁移到 Defender for Endpoint 的概述":::

当你从 Symantec 切换到适用于终结点的 Defender 时，你将从主动模式下的 Symantec 解决方案开始，在被动模式下配置适用于终结点的 Defender，载入到适用于终结点的 Defender，然后将适用于终结点的 Defender 设置为活动模式并删除 Symantec。

## <a name="the-migration-process"></a>迁移过程

从 Symantec 切换到 Microsoft Defender for Endpoint 时，将按照一个可以分为三个阶段的过程操作，如下表所述：

![迁移阶段 - 准备、设置、载入](images/phase-diagrams/migration-phases.png)

|阶段 |说明 |
|--|--|
|[准备迁移](symantec-to-microsoft-defender-atp-prepare.md) |在 **"准备** "阶段，获取适用于终结点的 Microsoft Defender，规划角色和权限，并授予对 Microsoft Defender 安全中心的访问权限。 还可以配置设备代理和 Internet 设置，以启用组织设备与适用于终结点的 Microsoft Defender 之间的通信。 |
|[设置 Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-setup.md) |在安装 **阶段** ，配置 Microsoft Defender 防病毒、适用于终结点的 Microsoft Defender 和 Symantec Endpoint Protection 的设置和排除项。 还可以创建设备组、集合和组织单位。 最后，配置反恶意软件策略和实时保护设置。|
|[载入到 Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-onboard.md) |在 **载入** 阶段，将你的设备载入到 Microsoft Defender for Endpoint 并验证这些设备是否正在与 Microsoft Defender for Endpoint 通信。 最后，卸载 Symantec 并确保通过 Microsoft Defender for Endpoint 的保护处于活动状态。 |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 中包含哪些内容？

在此迁移指南中，我们重点介绍下[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)一代保护和终结点检测和[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)响应功能，作为迁移到 Microsoft Defender for Endpoint 的起点。 但是，Microsoft Defender for Endpoint 包括的不仅仅是防病毒和终结点保护。 Microsoft Defender for Endpoint 是一个统一的平台，可用于预防性保护、入侵后检测、自动调查和响应。 下表总结了 Microsoft Defender for Endpoint 中的特性和功能。 

| 功能 | 说明 |
|---|---|
| [威胁&漏洞管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | 威胁&漏洞管理功能有助于识别、评估和修正终结点（如 (设备）中的) 。 |
| [攻击面减少](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | 攻击面减少规则有助于保护组织的设备和应用程序免受网络威胁和攻击。 |
| [下一代保护](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | 下一代保护包括可帮助阻止威胁和恶意软件的 Microsoft Defender 防病毒。 |
| [终结点检测和响应](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | 终结点检测和响应功能可检测、调查和响应入侵尝试和主动泄露。  |
| [高级搜寻](advanced-hunting-overview.md) | 高级搜寻功能使安全运营团队能够找到已知或潜在威胁的指示器和实体。 |
| [行为阻止和抑制](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | 行为阻止和包含功能有助于根据威胁的行为和进程树识别和停止威胁，即使威胁已开始执行。 |
| [自动调查和修复](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | 自动调查和响应功能可检查警报，并立即采取修正措施来解决违规问题。 |
| Microsoft[威胁专家](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (威胁搜寻)  | 威胁搜寻服务为安全运营团队提供专家级别的监视和分析，并帮助确保不会错过关键威胁。 |

**想要了解更多信息？请参阅 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection)。**

## <a name="next-step"></a>后续步骤

- 继续为 [迁移做准备](symantec-to-microsoft-defender-atp-prepare.md)。
