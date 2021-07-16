---
title: 将非 Microsoft 终结点保护切换到 Microsoft Defender for Endpoint
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
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 06/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: cff0810a4469d3c2d9ff2fe0fe5100b7a37408ae
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454741"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>将非 Microsoft 终结点保护切换到 Microsoft Defender for Endpoint

如果你正在考虑从非 Microsoft 终结点保护解决方案切换到 [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) ，你的位置正确。 使用本文作为指南。

:::image type="content" source="images/nonms-mde-migration.png" alt-text="迁移到 Defender for Endpoint 的概述":::

当你切换到 Defender for Endpoint 时，你首先在活动模式下运行非 Microsoft 解决方案。 然后，在被动模式下为终结点配置 Defender，然后将设备载入到 Defender for Endpoint。 接下来，将终结点的 Defender 设置为活动模式。 最后，删除非 Microsoft 解决方案。

## <a name="the-migration-process"></a>迁移过程

迁移到 Defender for Endpoint 的过程分为三个阶段，如下表所述：

![迁移阶段 - 准备、设置、载入](images/phase-diagrams/migration-phases.png)

|阶段 |说明 |
|--|--|
|[准备迁移](switch-to-microsoft-defender-prepare.md) |在 [" **准备"** 阶段](switch-to-microsoft-defender-prepare.md)： <p>1。更新组织的设备。 <p>2. 获取适用于终结点的 Defender。 <p>3. 规划角色和权限，并授予对 Microsoft 365 Defender 门户的访问权限。 <p>4. 配置设备代理和 Internet 设置，以启用组织设备与适用于终结点的 Defender 之间的通信。 |
|[设置适用于终结点的 Defender](switch-to-microsoft-defender-setup.md) |在 [设置 **阶段**：](switch-to-microsoft-defender-setup.md) <p>1. 启用/重新安装Microsoft Defender 防病毒。 <p>2. 为终结点配置 Defender。 <p>3. 将 Defender for Endpoint 添加到现有解决方案的排除列表中。 <p>4. 将现有解决方案添加到列表的排除Microsoft Defender 防病毒。 <p>5. 设置设备组、集合和组织单位。 <p>6. 配置反恶意软件策略和实时保护设置。|
|[载入到适用于终结点的 Defender](switch-to-microsoft-defender-onboard.md) |在 [载入 **阶段**](switch-to-microsoft-defender-onboard.md)： <p>1. 将设备载入到 Defender for Endpoint。 <p>2. 运行检测测试。 <p>3. 确认Microsoft Defender 防病毒被动模式下运行。 <p>4. 获取更新Microsoft Defender 防病毒。 <p>5. 卸载现有的终结点保护解决方案。 <p>6. 确保 Defender for Endpoint 正常工作。 |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 中包含哪些内容？

在此迁移指南中，我们重点介绍下[](microsoft-defender-antivirus-in-windows-10.md)一代保护和终结点检测和[](overview-endpoint-detection-response.md)响应功能，作为迁移到 Defender for Endpoint 的起点。 但是，Defender for Endpoint 包括的不仅仅是防病毒和终结点保护。 Defender for Endpoint 是一个统一的平台，用于预防性保护、攻破后检测、自动调查和响应。 下表总结了 Defender for Endpoint 中的特性和功能。 

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

**想要了解更多信息？请参阅 [Defender for Endpoint](microsoft-defender-endpoint.md)。**

## <a name="next-step"></a>下一步

- 继续为 [迁移做准备](switch-to-microsoft-defender-prepare.md)。
