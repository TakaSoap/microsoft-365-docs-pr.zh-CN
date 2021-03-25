---
title: 将非 Microsoft 终结点解决方案切换到 Microsoft Defender for Endpoint
description: 转换到 Microsoft Defender for Endpoint。 阅读本文，了解概述。
keywords: 迁移， windows defender 高级终结点保护， 适用于终结点， edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365solution-migratetomdatp
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 02/11/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 2c6029a1aada8f5f5fb27723c868f28c3de6f8aa
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218648"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>将非 Microsoft 终结点解决方案切换到 Microsoft Defender for Endpoint

如果你计划从非 Microsoft 终结点保护解决方案切换到 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint) ，你的位置正确。 使用本文作为指南。

:::image type="content" source="images/nonms-mde-migration.png" alt-text="迁移到 Defender for Endpoint 的概述":::

当你切换到适用于终结点的 Defender 时，你首先在活动模式下使用非 Microsoft 解决方案，在被动模式下为终结点配置 Defender，载入到适用于终结点的 Defender，然后将 Defender for Endpoint 设置为活动模式并删除非 Microsoft 解决方案。

> [!TIP]
> - 如果你当前正在使用 McAfee Endpoint Security (McAfee) ，请参阅从 [McAfee](mcafee-to-microsoft-defender-migration.md)迁移到 Microsoft Defender for Endpoint 。
> - 如果你当前正在使用 Symantec Endpoint Protection (Symantec) ，请参阅从 [Symantec](symantec-to-microsoft-defender-endpoint-migration.md)迁移到 Microsoft Defender for Endpoint 。

## <a name="the-migration-process"></a>迁移过程

当你切换到 Microsoft Defender for Endpoint 时，你将按照一个可以分为三个阶段的过程操作，如下表所述：

![迁移阶段 - 准备、设置、载入](images/phase-diagrams/migration-phases.png)

|阶段 |说明 |
|--|--|
|[准备迁移](switch-to-microsoft-defender-prepare.md) |在 [**"准备**"](switch-to-microsoft-defender-prepare.md)阶段，更新组织设备、获取 Microsoft Defender for Endpoint、规划角色和权限，并授予对 Microsoft Defender 安全中心的访问权限。 还可以配置设备代理和 Internet 设置，以启用组织设备与适用于终结点的 Microsoft Defender 之间的通信。 |
|[设置 Microsoft Defender for Endpoint](switch-to-microsoft-defender-setup.md) |在[设置阶段](switch-to-microsoft-defender-setup.md)，启用 Microsoft Defender 防病毒并确保它处于被动模式，并配置 Microsoft Defender 防病毒、Microsoft Defender for Endpoint 和现有终结点保护解决方案的设置 & 排除项。 还可以创建设备组、集合和组织单位。 最后，配置反恶意软件策略和实时保护设置。|
|[载入到 Microsoft Defender for Endpoint](switch-to-microsoft-defender-onboard.md) |在 [**载入** 阶段](switch-to-microsoft-defender-onboard.md)，将你的设备载入到 Microsoft Defender for Endpoint 并验证这些设备是否正在与 Microsoft Defender for Endpoint 通信。 最后，卸载现有终结点保护解决方案，并确保通过 Microsoft Defender 防病毒& Microsoft Defender for Endpoint 的保护处于活动状态。 |

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

- 继续为 [迁移做准备](switch-to-microsoft-defender-prepare.md)。
