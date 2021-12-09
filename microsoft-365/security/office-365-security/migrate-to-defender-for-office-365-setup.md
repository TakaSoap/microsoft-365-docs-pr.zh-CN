---
title: 迁移到 Microsoft Defender，Office 365阶段 2：设置
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
description: 执行这些步骤以开始从第三方保护服务或设备迁移到 Microsoft Defender，Office 365保护。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a89924fbd30631c42c9a39be7384e642c2755746
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61370652"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-2-setup"></a>迁移到 Microsoft Defender for Office 365 - 第 2 阶段：设置

**适用于：**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)

<br>

|[![阶段 1：准备。](../../media/phase-diagrams/prepare.png)](migrate-to-defender-for-office-365-prepare.md) <br> [阶段 1：准备](migrate-to-defender-for-office-365-prepare.md)|![阶段 2：设置。](../../media/phase-diagrams/setup.png) <br> 阶段 2：设置|[![阶段 3：载入。](../../media/phase-diagrams/onboard.png)](migrate-to-defender-for-office-365-onboard.md) <br> [阶段 3：开始使用](migrate-to-defender-for-office-365-onboard.md)|
|---|---|---|
||*你在这里！*||

欢迎使用 **阶段 2：设置** 迁移到 **[Microsoft Defender for Office 365](migrate-to-defender-for-office-365.md#the-migration-process)**！ 此迁移阶段包括以下步骤：

1. [为试点用户创建通讯组](#step-1-create-distribution-groups-for-pilot-users)
2. [为用户邮件报告配置用户提交](#step-2-configure-user-submission-for-user-message-reporting)
3. [维护或创建 SCL=-1 邮件流规则](#step-3-maintain-or-create-the-scl-1-mail-flow-rule)
4. [配置连接器的增强筛选](#step-4-configure-enhanced-filtering-for-connectors)
5. [创建试点保护策略](#step-5-create-pilot-protection-policies)

## <a name="step-1-create-distribution-groups-for-pilot-users"></a>步骤 1：为试点用户创建通讯组

迁移的以下方面Microsoft 365需要通讯组：

- **SCL=-1** 邮件流规则的例外：希望试点用户能够完全使用 Defender for Office 365 保护，因此需要 Defender 扫描其传入邮件Office 365。 为此，您可以在 Microsoft 365 中相应通讯组中定义试点用户，并配置这些组作为 SCL=-1 邮件流规则的例外。

  如 Onboard [Step 2： (Optional) Exempt pilot users from filtering by your existing protection service](migrate-to-defender-for-office-365-onboard.md#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)中所述，应考虑使这些相同的试点用户免受现有保护服务的扫描。 消除现有保护服务筛选和仅依赖 Defender for Office 365 的可能性是迁移完成后将发生的情况的最佳且最接近的表示形式。

- **测试特定 Defender Office 365** 保护功能：即使对于试点用户，也不想一次启用所有功能。 对对试点用户生效的保护功能使用分步方法可以更轻松地进行疑难解答和调整。 请记住此方法，我们建议使用下列通讯组：
  - **附件保险箱** 组：例如 **，MDOPilot \_ SafeAttachments**
  - **一保险箱链接试点组**：例如 **，MDOPilot \_ SafeLinks**
  - **标准反垃圾邮件** 和防钓鱼策略设置的试点组：例如 **，MDOPilot \_ SpamPhish \_ Standard**
  - **严格反垃圾邮件和** 反网络钓鱼策略设置的试点组：例如 **，MDOPilot \_ SpamPhish \_ Strict**

为清楚起见，我们将在整个文章中使用这些特定的组名称，但你可以随意使用自己的命名约定。

准备好开始测试时，将这些组作为例外添加到 [SCL=-1 邮件流规则 中](#step-3-maintain-or-create-the-scl-1-mail-flow-rule)。 当你在 Defender for Office 365 中为各种保护功能创建策略时，你将使用这些组作为条件来定义策略的适用对象。

**注意**：

- The terms Standard and Strict come from our [recommended security settings](recommended-settings-for-eop-and-office365.md)， which are also used in preset security [policies](preset-security-policies.md). 理想情况下，我们将告诉你在"标准"和"严格"预设安全策略中定义试点用户，但无法这样做。 为什么？ 因为无法自定义预设安全策略中的设置 (，特别是对邮件采取的操作或模拟保护设置的) 。 在迁移测试期间，你将希望查看 Defender for Office 365 对邮件会执行哪些操作，验证这是你想要发生的操作，并可能调整策略配置以允许或阻止这些结果。

  因此，你将使用与"标准"和"严格"预设安全策略的设置非常类似的设置手动创建自定义策略，而不是使用预设安全策略。但在某些情况下，这些设置不同于"标准"和"严格"预设安全策略的设置。

- 如果要试验与标准或严格建议值明显不同的设置，则应考虑在这些方案中为试点用户创建和使用其他和特定的通讯组。 可以使用配置分析器查看设置的安全。 有关说明，请参阅[Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365](configuration-analyzer-for-security-policies.md)。

  对于大多数组织来说，最佳方法是从与我们建议的标准设置紧密一致的策略开始。 在可用时间帧中能够执行尽可能多的观察和反馈后，你可以稍后移动到更主动的设置。 模拟保护和发送到垃圾邮件文件夹与发送到隔离邮箱可能需要自定义。

  如果使用自定义策略，只需确保先应用自定义策略，然后再应用包含我们推荐的迁移设置的策略。 如果在同一类型的多个策略中标识用户 (例如，防钓鱼) ，则根据策略) 的优先级值，只有一个该类型的策略应用于用户 (。 有关详细信息，请参阅电子邮件 [保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

## <a name="step-2-configure-user-submission-for-user-message-reporting"></a>步骤 2：为用户邮件报告配置用户提交

用户识别 Defender for Office 365误报或漏报的能力是迁移的重要部分。

可以指定一个Exchange Online邮箱，以接收用户报告为恶意或不恶意的邮件。 有关更多说明，请参阅 [用户报告的邮件设置](user-submission.md)。 此邮箱可以接收用户提交到 Microsoft 的邮件副本，或者该邮箱可以截获邮件，而无需将其报告给 Microsoft (安全团队可以手动分析和提交邮件) 。 但是，这种拦截方法不允许服务自动调整和学习。

还应确认试点中的所有用户都安装了支持的邮件报告Outlook与用户提交兼容。 这些应用包括：

- [报告邮件外接程序](enable-the-report-message-add-in.md)
- [报告网络钓鱼外接程序](enable-the-report-phish-add-in.md)
- 支持的第三方报告工具， [如下所述](user-submission.md#third-party-reporting-tools)。

不要为此步骤的重要性而不喜欢。 来自用户提交的数据将给予你反馈循环，你需要在迁移前后验证良好、一致的最终用户体验。 此反馈可帮助你做出明智的策略配置决策，以及向管理层提供数据支持的报告，以确保迁移顺利进行。

不是依赖于整个组织的体验所支持的数据，而是通过多个迁移产生基于单个负面用户体验的情绪情绪。 此外，如果您一直在运行网络钓鱼模拟，您可以使用用户的反馈，在用户看到可能需要调查的风险时通知您。

## <a name="step-3-maintain-or-create-the-scl-1-mail-flow-rule"></a>步骤 3：维护或创建 SCL=-1 邮件流规则

由于入站电子邮件通过位于 Microsoft 365 前面的另一个保护服务进行路由，因此在 Exchange Online 中，您可能已有一个邮件流规则 (也称为传输规则) ，它将所有传入邮件的垃圾邮件可信度 (SCL) 都设置为值 -1 (会绕过垃圾邮件筛选) 。 大多数第三方保护服务都鼓励希望使用其Microsoft 365客户使用此 SCL=-1 邮件流规则。

如果您使用其他一些机制替代 Microsoft 筛选堆栈 (例如，IP 允许列表) 我们建议您切换到使用 SCL=-1 邮件流规则，只要传入 Microsoft 365 的所有入站 Internet邮件都来自第三方保护服务 (则没有直接从 Internet 流向 Microsoft 365) 的邮件。

SCL=-1 邮件流规则在迁移过程中非常重要，原因如下：

- 可以使用威胁[资源管理器](email-security-in-microsoft-defender.md)查看 Microsoft 堆栈中的哪些功能会作用于邮件，而不会影响现有保护服务的结果。
- 通过配置 SCL=-1 邮件流规则的例外，可以逐渐Microsoft 365筛选堆栈保护的收件人。 例外情况是，我们稍后在本文中推荐试用通讯组的成员。

  在将 MX 记录切换为 Microsoft 365 之前或期间，将禁用此规则，为组织的所有收件人启用对 Microsoft 365 保护堆栈的完全保护。

有关详细信息，请参阅使用邮件流规则将垃圾邮件可信度设置为 (中的) [SCL Exchange Online。](https://docs.microsoft.comexchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)

**注意**：

- 如果计划允许 Internet 邮件同时通过现有保护服务并直接流入 Microsoft 365，则需要将绕过垃圾邮件筛选) 的 SCL=-1 邮件流规则 (限制为仅通过现有保护服务的邮件。 您不希望未筛选的 Internet 邮件登录 Microsoft 365。

  若要正确标识已由现有保护服务扫描的邮件，您可以向 SCL=-1 邮件流规则添加条件。 例如：

  - **对于基于云的保护服务**：可以使用组织独有的标头和标头值。 具有标头的邮件不会由邮件Microsoft 365。 没有标头的邮件由邮件Microsoft 365
  - **对于本地保护服务或设备**：可以使用源 IP 地址。 来自源 IP 地址的邮件不会由源 IP 地址Microsoft 365。 不来自源 IP 地址的邮件由用户扫描Microsoft 365。

- 不要完全依赖 MX 记录来控制邮件是否经过筛选。 发件人可以轻松忽略 MX 记录，并将电子邮件直接发送到Microsoft 365。

## <a name="step-4-configure-enhanced-filtering-for-connectors"></a>步骤 4：配置连接器的增强筛选

首先要执行的第一个操作是配置连接器的增强[筛选 (也称为](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)跳过连接器上用于从现有保护服务流向) 的邮件流上的 Microsoft 365。 可以使用入站 [邮件报告来帮助](/exchange/monitoring/mail-flow-reports/mfr-inbound-messages-and-outbound-messages-reports) 标识连接器。

Defender 要求增强连接器筛选功能，Office 365 Internet 邮件实际来自何处。 增强的连接器筛选功能显著提高了 Microsoft 筛选堆栈 (特别是欺骗智能，[](anti-spoofing-protection.md)以及威胁资源管理器和自动调查 & 响应 ([](threat-explorer.md) AIR) 中的攻破后[功能](automated-investigation-response-office.md)的准确性。

若要正确启用连接器的 \* \* **\* \*** 增强筛选，您需要添加将入站邮件路由到连接器的所有第三方服务和/或本地电子邮件系统主机Microsoft 365。

若要确认连接器的增强筛选功能正常工作，请验证传入邮件是否包含以下一个或两个邮件头：

- `X-MS-Exchange-SkipListedInternetSender`
- `X-MS-Exchange-ExternalOriginalInternetSender`

## <a name="step-5-create-pilot-protection-policies"></a>步骤 5：创建试点保护策略

通过创建生产策略（即使它们未应用于所有用户）可以测试泄露后功能（如威胁资源管理器）并测试将[](threat-explorer.md)Office 365 的 Defender 集成到安全响应团队的流程。

> [!IMPORTANT]
> 策略的范围可以包括用户、组或域。 我们不建议在一个策略中混合使用这三个策略，因为只有匹配这三个策略的用户才属于该策略的作用域。 对于试点策略，建议使用组或用户。 对于生产策略，建议使用域。 必须了解，只有用户的主电子邮件域才能确定用户是否位于策略范围内。 因此，如果切换用户辅助域的 MX 记录，请确保策略也涵盖其主域。

### <a name="create-pilot-safe-attachments-policies"></a>创建试点保险箱附件策略

[保险箱附件](safe-attachments.md)是在切换 MX 记录Office 365启用和测试的最简单 Defender。 保险箱附件具有以下优点：

- 最低配置。
- 误报的可能性非常低。
- 类似于反恶意软件保护的行为，它始终打开且不受 SCL=-1 邮件流规则的影响。

为保险箱用户创建"附件"策略。

有关建议设置，请参阅建议保险箱[附件策略设置。](recommended-settings-for-eop-and-office365.md#safe-attachments-policy-settings) 请注意，"标准"和"严格"建议是相同的。 若要创建策略，请参阅设置[保险箱附件策略。](set-up-safe-attachments-policies.md) 请务必将 **MDOPilot \_ SafeAttachments** 组用作策略应用于 (策略的策略) 。

> [!IMPORTANT]
> 目前，没有默认的"附件保险箱策略。 在切换任何 MX 记录之前，建议采用保险箱附件策略来保护整个组织。

### <a name="create-pilot-safe-links-policies"></a>创建试点保险箱链接策略

> [!NOTE]
> 我们不支持换行或重写已封装或重写的链接。 如果当前保护服务已经封装或重写电子邮件中的链接，则需要为试点用户关闭此功能。 确保不会发生此情况的方法之一是，在"链接"策略中排除其他保险箱域。
>
> 保险箱支持的应用的链接Office是适用于所有许可用户的全局设置。 可以全局打开或关闭它，而不是为特定用户打开或关闭它。 有关详细信息，请参阅为应用[配置保险箱链接Office 365保护](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal)。

为保险箱用户创建链接策略。 在"链接"中保险箱误报的可能性也相当低，但应考虑在较少数量的试点用户上测试此功能，而不是保险箱附件"。 由于该功能会影响用户体验，因此应考虑制定计划来培训用户。

有关推荐设置，请参阅推荐保险箱[链接策略设置](recommended-settings-for-eop-and-office365.md#safe-links-settings)。 请注意，"标准"和"严格"建议是相同的。 若要创建策略，请参阅设置保险箱[链接策略。](set-up-safe-links-policies.md) 请务必将 **MDOPilot \_ SafeLinks** 组用作策略应用于 (策略的条件) 。

> [!IMPORTANT]
> 目前，没有默认的"链接保险箱策略。 在切换任何 MX 记录之前，建议采用保险箱链接策略来保护整个组织。

### <a name="create-pilot-anti-spam-policies"></a>创建试点反垃圾邮件策略

为试点用户创建两个反垃圾邮件策略：

- 使用标准设置的策略。 使用组 **MDOPilot \_ SpamPhish \_ Standard** 作为策略 (策略应用于其策略) 。
- 使用严格设置的策略。 使用组 **MDOPilot \_ SpamPhish \_ Strict** 作为策略 (应用于策略的策略的条件) 。 此策略的优先级应高于 (标准) 策略的优先级。

有关推荐的"标准"和"严格"设置，请参阅推荐的 [反垃圾邮件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。 若要创建策略，请参阅 [配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

### <a name="create-pilot-anti-phishing-policies"></a>创建试点防钓鱼策略

为试点用户创建两个防钓鱼策略：

- 使用标准设置的策略，模拟检测操作除外，如下所述。 使用组 **MDOPilot \_ SpamPhish \_ Standard** 作为策略 (策略应用于其策略) 。
- 使用严格设置的策略，模拟检测操作除外，如下所述。 使用组 **MDOPilot \_ SpamPhish \_ Strict** 作为策略 (应用于策略的策略的条件) 。 此策略的优先级应高于 (标准) 策略的优先级。

对于欺骗检测，建议的标准操作是将邮件移动到收件人的垃圾邮件文件夹，推荐的严格操作是隔离 **邮件**。 使用欺骗智能见解来观察结果。 替代将下一节介绍。 有关详细信息，请参阅[在 EOP 中配置欺骗智能见解](learn-about-spoof-intelligence.md)。

对于模拟检测，请忽略试点策略的建议 Standard 和 Strict 操作。 请改为使用 **值"不对以下设置** 应用任何操作"：

- **如果邮件被检测为模拟用户**
- **如果邮件被检测为模拟域**
- **如果邮箱智能检测到模拟用户**

使用模拟见解观察结果。 有关详细信息，请参阅 Defender for Office 365 中的[模拟见解](impersonation-insight.md)。

根据标准或严格 (，你可以调整欺骗保护 (允许并阻止) 并启用每个模拟保护操作来隔离邮件或将邮件移动到垃圾邮件文件夹 () 。 你可以观察结果并根据需要调整其设置。

有关详细信息，请参阅下列主题：

- [防欺骗保护](anti-spoofing-protection.md)
- [防钓鱼策略中的模拟设置](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [在 Defender 中为用户配置Office 365。](configure-mdo-anti-phishing-policies.md)

## <a name="next-step"></a>后续步骤

**恭喜！** 你已完成迁移到 Microsoft Defender **for** Office 365 的 [安装阶段](migrate-to-defender-for-office-365.md#the-migration-process)！

- 继续执行阶段 [3：载入](migrate-to-defender-for-office-365-onboard.md)。
