---
title: 迁移到 Microsoft Defender，Office 365阶段 1：准备
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
ms.custom: migrationguides
description: 从第三方保护服务或设备迁移到 Microsoft Defender 进行保护的先决条件Office 365步骤。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f6785e96829256ffe0763eb0f3e84059973d6379
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785794"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-1-prepare"></a>迁移到 Microsoft Defender for Office 365 - 第 1 阶段：准备

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)

<br>

|![阶段 1：准备。](../../media/phase-diagrams/prepare.png) <br> 阶段 1：准备|[![阶段 2：设置](../../media/phase-diagrams/setup.png)](migrate-to-defender-for-office-365-setup.md) <br> [阶段 2：设置](migrate-to-defender-for-office-365-setup.md)|[![阶段 3：开始使用](../../media/phase-diagrams/onboard.png)](migrate-to-defender-for-office-365-onboard.md) <br> [阶段 3：开始使用](migrate-to-defender-for-office-365-onboard.md)|
|---|---|---|
|*你在这里！*|||

欢迎使用 **阶段 1：准备****[迁移到 Microsoft Defender for Office 365](migrate-to-defender-for-office-365.md#the-migration-process)**！ 此迁移阶段包括以下步骤。 应首先清点现有保护服务中的设置，然后再进行更改。 否则，您可以按任意顺序执行其余步骤：

1. [清点现有保护服务中的设置](#inventory-the-settings-at-your-existing-protection-service)
2. [检查现有保护配置Microsoft 365](#check-your-existing-protection-configuration-in-microsoft-365)
3. [检查邮件路由配置](#check-your-mail-routing-configuration)
4. [将修改邮件的功能移动到Microsoft 365](#move-features-that-modify-messages-into-microsoft-365)
5. [定义垃圾邮件和批量用户体验](#define-spam-and-bulk-user-experiences)
6. [标识和指定优先级帐户](#identify-and-designate-priority-accounts)

## <a name="inventory-the-settings-at-your-existing-protection-service"></a>清点现有保护服务中的设置

从现有保护服务获取设置、规则、例外等的完整清单是一个不错的主意，因为在取消订阅后你很可能无法访问信息。

**但是，在 Defender for Office 365 中，不要自动或任意重新创建所有现有自定义Office 365。** 您最好引入不再需要、相关或功能性的设置。 更糟糕的是，以前的一些自定义设置可能会实际在 Defender for Office 365。

你测试并观察 Defender for Office 365 的本机功能和行为将最终确定你所需的替代和设置。 您可能会发现，将现有保护服务中的设置分为以下类别会很有帮助：

- **连接或内容筛选**：你会发现，在 Defender for Office 365 中，你无需大部分自定义。
- **业务路由**：需要重新创建的大多数自定义项可能属于此类别。 例如，您可以将这些设置重新创建为Microsoft 365规则Exchange邮件流规则 (传输规则) 、连接器和欺骗智能的例外。

建议采用一种包含用户成员资格不断增加的试验阶段和基于观察的调整（基于平衡安全注意事项与组织业务需求）的瀑布式方法，而不是将旧设置完全移动到 Microsoft 365 中。

## <a name="check-your-existing-protection-configuration-in-microsoft-365"></a>检查现有保护配置Microsoft 365

正如我们之前所述，不可能完全关闭传递到 Microsoft 365 的邮件的所有保护功能，即使您使用第三方保护服务。 因此，组织至少配置Microsoft 365一些电子邮件保护功能并不少见。 例如：

- 过去，你未将第三方保护服务与 Microsoft 365。 你可能已使用和配置了当前Microsoft 365中的一些保护功能。 但是，当你"打开拨号盘"以在拨号盘中启用保护功能时，这些设置Microsoft 365。
- 您可能具有 Microsoft 365 保护中的误报 (通过现有保护服务) 或 (错误邮件) 错误邮件。

查看现有保护功能Microsoft 365并考虑删除或简化不再需要的设置。 多年来所需的规则或策略设置可能会使组织面临风险，并造成意外的保护差距。

## <a name="check-your-mail-routing-configuration"></a>检查邮件路由配置

- 如果您使用的是任何复杂的路由规则，例如 [ (邮件传输](/exchange/transport-options)) ，则应考虑简化您的路由并详细记录它。 外部跃点（尤其是在Microsoft 365消息后）会使配置和故障排除变得复杂。

- 本文未介绍出站和中继邮件流。 但是，请注意，您可能需要执行下列一个或多个步骤：
  - 验证用于发送电子邮件的所有域是否具有正确的 SPF 记录。 如需了解更多信息，请参阅[设置 SPF以帮助防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。
  - 我们强烈建议你设置 DKIM 登录Microsoft 365。 有关详细信息，请参阅使用 [DKIM 验证出站电子邮件](use-dkim-to-validate-outbound-email.md)。
  - 如果您不是直接从邮件路由Microsoft 365，则需要通过删除或更改出站连接器来更改该路由。

- 使用 Microsoft 365中继来自本地电子邮件服务器的电子邮件本身可能是一个复杂的项目。 一个简单示例是，少数应用或设备将其大部分邮件发送给内部收件人，并且不用于大量邮件。 有关详细信息 [，请参阅](/exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-microsoft-365-or-office-365) 本指南。 更广泛的环境将需要更加周到。 不允许营销电子邮件和收件人可能被视为垃圾邮件的邮件。

- Defender for Office 365 没有聚合 DMARC 报告的功能。 访问[Microsoft Intelligent Security Association (MISA) 目录](https://www.microsoft.com/misapartnercatalog)，查看提供针对 MICROSOFT 365 的 DMARC 报告的第三方Microsoft 365。

## <a name="move-features-that-modify-messages-into-microsoft-365"></a>将修改邮件的功能移动到Microsoft 365

您需要将以任何方式修改邮件的任何自定义项或功能转移到Microsoft 365。 例如，现有的保护服务向来自外部发件人的邮件的主题或邮件正文添加一个 **External** 标记。

如果未禁用现有保护服务中的此功能，则会导致以下负面影响Microsoft 365：

- DKIM 将中断。
- [欺骗智能](anti-spoofing-protection.md) 将无法正常工作。
- 你可能会收到大量误报， (标记为错误邮件) 。

若要在Microsoft 365中重新创建此功能，可以使用以下选项：

- The [Outlook external sender call-out feature](https://techcommunity.microsoft.com/t5/exchange-team-blog/native-external-sender-callouts-on-email-in-outlook/ba-p/2250098)， with first contact safety [tips](set-up-anti-phishing-policies.md#first-contact-safety-tip).
- 邮件流规则 (也称为传输规则) 。 有关详细信息，请参阅组织范围内的邮件免责声明、[签名](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)、页脚或邮件头Exchange Online。

## <a name="account-for-any-active-phishing-simulations"></a>考虑任何活动的网络钓鱼模拟

如果你有活动的第三方网络钓鱼模拟，则需要防止 Defender 将邮件、链接和附件标识为网络钓鱼Office 365。 有关详细信息，请参阅在高级传递策略中配置第三 [方网络钓鱼模拟](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy)。

## <a name="define-spam-and-bulk-user-experiences"></a>定义垃圾邮件和批量用户体验

- **隔离与发送到垃圾邮件文件夹**：恶意邮件和肯定存在风险的邮件的自然响应和推荐响应是隔离邮件。 但是，您希望用户如何处理不太有害的邮件（如垃圾邮件）和批量邮件 (也称为灰色 *邮件) 。* 这些类型的邮件应传递到用户垃圾邮件文件夹吗？

  使用标准安全设置，我们通常将这些风险较少的邮件类型发送到"垃圾邮件"文件夹。 此行为类似于许多消费者电子邮件产品/服务，其中用户可以检查其"垃圾邮件"文件夹是否缺少邮件，并可以自行验证这些邮件。 或者，如果用户有意注册新闻稿或营销邮件，他们可以选择取消订阅或阻止自己的邮箱的发件人。

  但是，许多企业用户很少 ("垃圾邮件) 中发送任何邮件。 相反，这些企业用户用于检查其丢失邮件的隔离。 隔离引入了隔离通知、通知频率以及查看和释放邮件所需的权限的问题。

  - 域密钥识别邮件 (DKIM) 将中断。
  - [欺骗智能](anti-spoofing-protection.md) 将无法正常工作。
  - 你可能会收到大量误报， (标记为错误邮件) 。

  最后，如果想阻止将电子邮件送达垃圾邮件文件夹，以选择隔离邮件，则由你决定。 但是，有一点很确定：如果 Defender for Office 365体验不同于用户习惯使用的体验，则需要通知他们并提供基本培训。 整合从试点中学习，并确保用户为电子邮件传递的任何新行为做好准备。

- **需要批量邮件与不需要的批量邮件**：许多保护系统允许用户自行允许或阻止批量电子邮件。 这些设置无法轻松迁移到Microsoft 365，因此应考虑与 ISP 及其员工合作，以在 MICROSOFT 365 中重新创建其现有Microsoft 365。

  现在，Microsoft 365考虑一些批量邮件 (例如，新闻稿) 邮件源的安全。 来自这些"安全"源的邮件当前未标记为批量 (批量投诉级别或 BCL 为 0 或 1) ，因此难以全局阻止来自这些源的邮件。 对于大多数用户，解决方案是要求他们单独取消订阅这些批量邮件或使用 Outlook阻止发件人。 但是，某些用户不会喜欢阻止或取消订阅批量邮件本身。

  当 VIP 用户不希望自己管理批量电子邮件时，筛选批量电子邮件的邮件流规则可能会很有帮助。 有关详细信息，请参阅使用 [邮件流规则筛选批量电子邮件](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-filter-bulk-mail)。

## <a name="identify-and-designate-priority-accounts"></a>标识和指定优先级帐户

如果此功能可供你使用，优先级帐户和用户标记可以帮助识别重要的Microsoft 365用户，以便他们在报告中脱颖而出。 有关详细信息，请参阅 Microsoft Defender for Office 365中的用户[标记以及](user-tags.md)[管理和监视优先级帐户](/microsoft-365/admin/setup/priority-accounts)。

## <a name="next-step"></a>后续步骤

**恭喜！** 你已完成迁移到 Microsoft Defender **的"** 准备"[阶段Office 365！](migrate-to-defender-for-office-365.md#the-migration-process)

- 继续执行阶段 [2：设置](migrate-to-defender-for-office-365-setup.md)。
