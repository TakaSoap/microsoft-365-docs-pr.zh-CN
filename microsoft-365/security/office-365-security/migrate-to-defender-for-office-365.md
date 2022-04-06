---
title: 从第三方保护服务迁移到 Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: 了解从第三方保护服务或设备（如 Google Postini、Barracuda 垃圾邮件和病毒防火墙或 Cisco IronPort）迁移到 Microsoft Defender Office 365保护。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ba82621e76665ee94d2a182e777ad1d222ef8e56
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64477030"
---
# <a name="migrate-from-a-third-party-protection-service-or-device-to-microsoft-defender-for-office-365"></a>从第三方保护服务或设备迁移到 Microsoft Defender for Office 365

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)

如果你已有位于 Microsoft 365 前面的第三方保护服务或设备，可以使用本指南将保护迁移到 Microsoft Defender for Office 365，从而获得合并管理体验的好处，使用已支付) 的产品和具有集成安全保护的成熟产品，可能会降低 (的成本。 有关详细信息，请参阅 [Microsoft Defender for Office](https://www.microsoft.com/security/business/threat-protection/office-365-defender)。

本指南提供了迁移的具体可操作步骤，并假定以下事实：

- 你已Microsoft 365邮箱，但当前正在使用第三方服务或设备进行电子邮件保护。 来自 Internet 的邮件在传递至 Microsoft 365 组织之前流经保护服务，Microsoft 365 保护尽可能低 (它永远不会完全关闭;例如，始终在) 中强制执行恶意软件保护。

  :::image type="content" source="../../media/mdo-migration-before.png" alt-text="邮件通过第三方保护服务或设备从 Internet 流动，然后再Microsoft 365" lightbox="../../media/mdo-migration-before.png":::

- 你超出了 Defender for Office 365 保护调查和考虑阶段。 如果你需要评估 Defender Office 365以确定它是否适合你的组织，我们建议你考虑评估[模式](office-365-evaluation.md)。

- 你已购买 Defender for Office 365许可证。

- 你需要停用现有的第三方保护服务，这意味着你最终需要将电子邮件域的 MX 记录指向Microsoft 365。 完成后，来自 Internet 的邮件将直接流入 Microsoft 365并且将受 Exchange Online Protection (EOP) 和 Defender for Office 365。

  :::image type="content" source="../../media/mdo-migration-after.png" alt-text="邮件从 Internet 流向Microsoft 365" lightbox="../../media/mdo-migration-after.png":::

删除现有保护服务以支持 Defender for Office 365是一个大步骤，不应轻松执行，也不应太忙地做出更改。 此迁移指南中的指南将帮助你以有序方式转换保护，尽可能减少用户中断。

下图演示了非常高级的迁移步骤。 本文稍后将介绍迁移过程一节 [列出了](#the-migration-process) 实际步骤。

:::image type="content" source="../../media/mdo-migration-overview.png" alt-text="从第三方保护解决方案或设备迁移到 Defender for Office 365" lightbox="../../media/mdo-migration-overview.png":::

## <a name="why-use-the-steps-in-this-guide"></a>为什么使用本指南中的步骤？

在 IT 行业，意外通常比较严重。 只需翻转 MX 记录即可指向Microsoft 365事先经过周密的测试将导致许多意外。 例如：

- 你或你的前置任务可能花费大量时间和精力来自定义现有保护服务，以实现最佳邮件传递 (换句话说，阻止需要阻止的项，以及允许需要允许) 。 几乎可以保证，并非当前保护服务中的每个自定义都需要在 Defender for Office 365。 此外，Defender for Office 365 可能会引入新问题， (允许或阻止) 当前保护服务中未发生或不需要的一些问题。
- 技术支持和安全人员需要知道在 Defender for Office 365。 例如，如果用户抱怨缺少消息，你的技术支持是否知道在哪里或如何查找？ 他们可能会验证是否熟悉现有保护服务中的工具，但 Defender for Office 365？

相反，如果按照此迁移指南中的步骤操作，则迁移会获得以下切实的好处：

- 尽量减少用户中断。
- Defender for Office 365目标数据，可用于报告迁移到管理的进度和成功情况。
- 技术支持和安全人员的早期参与和指导。

你越熟悉 Defender for Office 365对组织的影响，用户、技术支持人员、安全人员和管理的转换就越好。

此迁移指南为你提供了逐步"打开拨号"的计划，以便你可以监视和测试 Defender for Office 365 如何影响你的用户及其电子邮件，以便你可以快速响应你遇到的任何问题。

## <a name="the-migration-process"></a>迁移过程

从第三方保护服务迁移到 Defender for Office 365的过程分为三个阶段，如下表所述：

:::image type="content" source="../../media/phase-diagrams/migration-phases.png" alt-text="迁移到 Defender for Office 365" lightbox="../../media/phase-diagrams/migration-phases.png":::

|阶段|说明|
|---|---|
|[准备迁移](migrate-to-defender-for-office-365-prepare.md)|<ol><li>[清点现有保护服务中的设置](migrate-to-defender-for-office-365-prepare.md#inventory-the-settings-at-your-existing-protection-service)</li><li>[检查现有保护配置Microsoft 365](migrate-to-defender-for-office-365-prepare.md#check-your-existing-protection-configuration-in-microsoft-365)</li><li>[检查邮件路由配置](migrate-to-defender-for-office-365-prepare.md#check-your-mail-routing-configuration)</li><li>[将修改邮件的功能移动到Microsoft 365](migrate-to-defender-for-office-365-prepare.md#move-features-that-modify-messages-into-microsoft-365)</li><li>[定义垃圾邮件和批量用户体验](migrate-to-defender-for-office-365-prepare.md#define-spam-and-bulk-user-experiences)</li><li>[标识和指定优先级帐户](migrate-to-defender-for-office-365-prepare.md#identify-and-designate-priority-accounts)</li></ol>|
|[设置 Defender for Office 365](migrate-to-defender-for-office-365-setup.md)|<ol><li>[为试点用户创建通讯组](migrate-to-defender-for-office-365-setup.md#step-1-create-distribution-groups-for-pilot-users)</li><li>[为用户邮件报告配置用户提交](migrate-to-defender-for-office-365-setup.md#step-2-configure-user-submission-for-user-message-reporting)</li><li>[维护或创建 SCL=-1 邮件流规则](migrate-to-defender-for-office-365-setup.md#step-3-maintain-or-create-the-scl-1-mail-flow-rule)</li><li>[配置连接器的增强筛选](migrate-to-defender-for-office-365-setup.md#step-4-configure-enhanced-filtering-for-connectors)</li><li>[创建试点保护策略](migrate-to-defender-for-office-365-setup.md#step-5-create-pilot-protection-policies)</li></ol>|
|[载入 Defender for Office 365](migrate-to-defender-for-office-365-onboard.md)|<ol><li>[开始载入安全Teams](migrate-to-defender-for-office-365-onboard.md#step-1-begin-onboarding-security-teams)</li><li>[ (可选) 允许试点用户通过现有保护服务进行筛选](migrate-to-defender-for-office-365-onboard.md#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)</li><li>[优化欺骗智能](migrate-to-defender-for-office-365-onboard.md#step-3-tune-spoof-intelligence)</li><li>[优化模拟保护和邮箱智能](migrate-to-defender-for-office-365-onboard.md#step-4-tune-impersonation-protection-and-mailbox-intelligence)</li><li>[使用来自用户提交的数据进行度量和调整](migrate-to-defender-for-office-365-onboard.md#step-5-use-data-from-user-submissions-to-measure-and-adjust)</li><li>[ (可选) 向试点添加更多用户并进行访问](migrate-to-defender-for-office-365-onboard.md#step-6-optional-add-more-users-to-your-pilot-and-iterate)</li><li>[将Microsoft 365保护扩展到所有用户，并关闭 SCL=-1 邮件流规则](migrate-to-defender-for-office-365-onboard.md#step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule)</li><li>[切换 MX 记录](migrate-to-defender-for-office-365-onboard.md#step-8-switch-your-mx-records)</li></ol>|

## <a name="next-step"></a>后续步骤

- 继续执行阶段 [1：准备](migrate-to-defender-for-office-365-prepare.md)。
