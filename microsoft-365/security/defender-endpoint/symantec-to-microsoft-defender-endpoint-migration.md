---
title: 从 Symantec 迁移到 Microsoft Defender for Endpoint
description: 大致了解如何从 Symantec 切换到 Microsoft Defender for Endpoint
keywords: migration， Microsoft Defender for Endpoint， edr
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
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 62a916fcf89432a512ada1b85002cce401e4dd23
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530894"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>从 Symantec 迁移到 Microsoft Defender for Endpoint
如果你计划从 Symantec Endpoint Protection (Symantec) 切换到适用于 Endpoint (的[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)) ，你的位置正确。 使用本文作为指南。

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
|[准备迁移](symantec-to-microsoft-defender-atp-prepare.md) |在 **"准备**"阶段，更新组织设备、获取 Microsoft Defender for Endpoint、规划角色和权限，并授予对 Microsoft Defender 安全中心。 还可以配置设备代理和 Internet 设置，以启用组织设备与适用于终结点的 Defender 之间的通信。 |
|[设置 Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-setup.md) |在 **设置阶段**，启用Microsoft Defender 防病毒并设置为被动模式。 还可以为 & 和 Symantec Microsoft Defender 防病毒配置设置Endpoint Protection。 然后，创建设备组、集合和组织单位。 最后，配置反恶意软件策略和实时保护设置。|
|[载入到 Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-onboard.md) |在载入 **阶段，** 将设备载入到 Microsoft Defender for Endpoint，确认 Microsfot Defender 防病毒正在被动模式下运行，并验证终结点是否正在与 Defender for Endpoint 通信。 然后，卸载 Symantec 并确保 Defender for Endpoint 正常工作。 |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 中包含哪些内容？

在此迁移指南中，我们重点介绍下[](microsoft-defender-antivirus-in-windows-10.md)一代保护和终结点检测和[](overview-endpoint-detection-response.md)响应功能，作为迁移到 Microsoft Defender for Endpoint 的起点。 但是，Microsoft Defender for Endpoint 包括的不仅仅是防病毒和终结点保护。 Microsoft Defender for Endpoint 是一个统一的平台，可用于预防性保护、入侵后检测、自动调查和响应。 下表总结了 Microsoft Defender for Endpoint 中的特性和功能。 

| 功能 | 说明 |
|---|---|
| [威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md) | 威胁& 漏洞管理功能有助于识别、评估和修正跨终结点（如 (设备）中的) 。 |
| [减少攻击面](overview-attack-surface-reduction.md) | 攻击面减少规则有助于保护组织的设备和应用程序免受网络威胁和攻击。 |
| [下一代保护](microsoft-defender-antivirus-in-windows-10.md) | 下一代保护包括Microsoft Defender 防病毒帮助阻止威胁和恶意软件。 |
| [终结点检测和响应](overview-endpoint-detection-response.md) | 终结点检测和响应功能可检测、调查和响应入侵尝试和主动泄露。  |
| [高级搜寻](advanced-hunting-overview.md) | 高级搜寻功能使安全运营团队能够找到已知或潜在威胁的指示器和实体。 |
| [行为阻止和控制](behavioral-blocking-containment.md) | 行为阻止和包含功能有助于根据威胁的行为和进程树识别和停止威胁，即使威胁已开始执行。 |
| [自动调查和修正](automated-investigations.md) | 自动调查和响应功能可检查警报，并立即采取修正措施来解决违规问题。 |
| [威胁搜寻服务](microsoft-threat-experts.md) (Microsoft 威胁专家)  | 威胁搜寻服务为安全运营团队提供专家级别的监视和分析，并帮助确保不会错过关键威胁。 |

**想要了解更多信息？请参阅 [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)。**

## <a name="next-step"></a>后续步骤

- 继续为 [迁移做准备](symantec-to-microsoft-defender-atp-prepare.md)。
