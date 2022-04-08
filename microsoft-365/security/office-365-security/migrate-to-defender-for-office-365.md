---
title: 从第三方保护服务迁移到Pertahanan Microsoft untuk Office 365
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
description: 了解从第三方保护服务或设备（如 Google Postini、Barracuda 垃圾邮件和病毒防火墙或 Cisco IronPort）迁移到Pertahanan Microsoft untuk Office 365保护的正确方法。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b00051effd6ee77fd29ba0a5a07ee27c9113a439
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2022
ms.locfileid: "64704814"
---
# <a name="migrate-from-a-third-party-protection-service-or-device-to-microsoft-defender-for-office-365"></a>从第三方保护服务或设备迁移到Pertahanan Microsoft untuk Office 365

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)

如果已有位于Microsoft 365前的第三方保护服务或设备，则可以使用本指南将保护迁移到Pertahanan Microsoft untuk Office 365，以获得合并管理体验的优势、使用已为) 付费的产品 (可能降低成本，以及使用成熟产品 集成安全保护。 有关详细信息，请参阅 [Microsoft Defender for Office](https://www.microsoft.com/security/business/threat-protection/office-365-defender)。

本指南为迁移提供具体且可操作的步骤，并假定以下事实：

- 你已有Microsoft 365邮箱，但目前使用的是第三方服务或设备以进行电子邮件保护。 在将保护服务传送到Microsoft 365组织之前，来自 Internet 的邮件会流经保护服务，Microsoft 365保护尽可能低， (它永远不会完全关闭;例如，恶意软件保护始终) 强制实施。

  :::image type="content" source="../../media/mdo-migration-before.png" alt-text="邮件从 Internet 流经第三方保护服务或设备，然后传递到Microsoft 365" lightbox="../../media/mdo-migration-before.png":::

- 你超出了调查和考虑阶段，无法通过Defender pre Office 365进行保护。 如果需要评估Defender pre Office 365以确定它是否适合你的组织，建议考虑 [Try Pertahanan Microsoft untuk Office 365](try-microsoft-defender-for-office-365.md) 中所述的选项。

- 你已购买Defender pre Office 365许可证。

- 需要停用现有的第三方保护服务，这意味着最终需要将电子邮件域的 MX 记录指向Microsoft 365。 完成后，来自 Internet 的邮件将直接流入Microsoft 365，并仅受Exchange Online Protection (EOP) 和Defender pre Office 365的保护。

  :::image type="content" source="../../media/mdo-migration-after.png" alt-text="邮件从 Internet 流向Microsoft 365" lightbox="../../media/mdo-migration-after.png":::

取消现有的保护服务以支持Defender pre Office 365是一个重要步骤，不应掉以轻心，也不应急于进行更改。 本迁移指南中的指南将帮助你有条不紊地过渡保护，同时尽量减少对用户的干扰。

下图说明了非常高级别的迁移步骤。 在本文后面的名为 ["迁移过程"](#the-migration-process) 的部分中列出了实际步骤。

:::image type="content" source="../../media/mdo-migration-overview.png" alt-text="从第三方保护解决方案或设备迁移到Defender pre Office 365的过程" lightbox="../../media/mdo-migration-overview.png":::

## <a name="why-use-the-steps-in-this-guide"></a>为什么要使用本指南中的步骤？

在 IT 行业，惊喜通常很糟糕。 只需将 MX 记录翻转到指向Microsoft 365而不经过预先和周到的测试，就会产生许多惊喜。 例如：

- 你或你的前置人员可能花了很多时间和精力自定义现有的保护服务，以获得最佳邮件传递 (换句话说，阻止需要阻止的内容，并允许) 。 几乎可以肯定的是，Defender pre Office 365中不需要当前保护服务中的每个自定义项。 Defender pre Office 365也很有可能会引入新问题， (允许或阻止当前保护服务中未发生或不需要的) 。
- 你的技术支持人员和安全人员需要知道在Defender pre Office 365中该做什么。 例如，如果用户抱怨缺少消息，你的技术支持人员是否知道在何处或如何查找它？ 它们可能会验证是否熟悉现有保护服务中的工具，但Defender pre Office 365中的工具又如何呢？

相比之下，如果按照本迁移指南中的步骤操作，则迁移将获得以下有形优势：

- 对用户的中断最小。
- 在报告迁移到管理的进度和成功时，可以使用Defender pre Office 365的客观数据。
- 为技术支持人员和安全人员提供早期参与和指导。

你越是熟悉Defender pre Office 365将如何影响你的组织，转换对用户、技术支持人员、安全人员和管理就越有利。

本迁移指南提供逐步"转拨号"的计划，以便监视和测试Defender pre Office 365如何影响用户及其电子邮件，以便快速应对遇到的任何问题。

## <a name="the-migration-process"></a>迁移过程

从第三方保护服务迁移到Defender pre Office 365的过程可以分为三个阶段，如下表所述：

:::image type="content" source="../../media/phase-diagrams/migration-phases.png" alt-text="迁移到Defender pre Office 365的过程" lightbox="../../media/phase-diagrams/migration-phases.png":::

|阶段|说明|
|---|---|
|[为迁移做准备](migrate-to-defender-for-office-365-prepare.md)|<ol><li>[清点现有保护服务中的设置](migrate-to-defender-for-office-365-prepare.md#inventory-the-settings-at-your-existing-protection-service)</li><li>[在Microsoft 365中检查现有的保护配置](migrate-to-defender-for-office-365-prepare.md#check-your-existing-protection-configuration-in-microsoft-365)</li><li>[检查邮件路由配置](migrate-to-defender-for-office-365-prepare.md#check-your-mail-routing-configuration)</li><li>[将修改消息的功能移动到Microsoft 365](migrate-to-defender-for-office-365-prepare.md#move-features-that-modify-messages-into-microsoft-365)</li><li>[定义垃圾邮件和批量用户体验](migrate-to-defender-for-office-365-prepare.md#define-spam-and-bulk-user-experiences)</li><li>[标识和指定优先级帐户](migrate-to-defender-for-office-365-prepare.md#identify-and-designate-priority-accounts)</li></ol>|
|[设置Defender pre Office 365](migrate-to-defender-for-office-365-setup.md)|<ol><li>[为试点用户创建通讯组](migrate-to-defender-for-office-365-setup.md#step-1-create-distribution-groups-for-pilot-users)</li><li>[为用户消息报告配置用户提交](migrate-to-defender-for-office-365-setup.md#step-2-configure-user-submission-for-user-message-reporting)</li><li>[维护或创建 SCL=-1 邮件流规则](migrate-to-defender-for-office-365-setup.md#step-3-maintain-or-create-the-scl-1-mail-flow-rule)</li><li>[为连接器配置增强筛选](migrate-to-defender-for-office-365-setup.md#step-4-configure-enhanced-filtering-for-connectors)</li><li>[创建试点保护策略](migrate-to-defender-for-office-365-setup.md#step-5-create-pilot-protection-policies)</li></ol>|
|[加入到Defender pre Office 365](migrate-to-defender-for-office-365-onboard.md)|<ol><li>[开始载入安全Teams](migrate-to-defender-for-office-365-onboard.md#step-1-begin-onboarding-security-teams)</li><li>[ (可选) 通过现有保护服务免除试点用户的筛选](migrate-to-defender-for-office-365-onboard.md#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)</li><li>[优化欺骗智能](migrate-to-defender-for-office-365-onboard.md#step-3-tune-spoof-intelligence)</li><li>[优化模拟保护和邮箱智能](migrate-to-defender-for-office-365-onboard.md#step-4-tune-impersonation-protection-and-mailbox-intelligence)</li><li>[使用用户提交中的数据来度量和调整](migrate-to-defender-for-office-365-onboard.md#step-5-use-data-from-user-submissions-to-measure-and-adjust)</li><li>[ (可选) 向试点添加更多用户并循环访问](migrate-to-defender-for-office-365-onboard.md#step-6-optional-add-more-users-to-your-pilot-and-iterate)</li><li>[将Microsoft 365保护扩展到所有用户，并关闭 SCL=-1 邮件流规则](migrate-to-defender-for-office-365-onboard.md#step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule)</li><li>[切换 MX 记录](migrate-to-defender-for-office-365-onboard.md#step-8-switch-your-mx-records)</li></ol>|

## <a name="next-step"></a>后续步骤

- 继续执行 [阶段 1：准备](migrate-to-defender-for-office-365-prepare.md)。
