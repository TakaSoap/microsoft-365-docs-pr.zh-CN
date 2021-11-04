---
title: 迁移到 Microsoft Defender，Office 365阶段 3：载入
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
description: 完成从第三方保护服务或设备迁移到 Microsoft Defender 以Office 365的步骤。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a218aa1e86bd696079bb2c77b630bcf870bc0c25
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60779057"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-3-onboard"></a>迁移到 Microsoft Defender for Office 365 - 第 3 阶段：载入

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)

<br>

|[![阶段 1：准备。](../../media/phase-diagrams/prepare.png)](migrate-to-defender-for-office-365-prepare.md) <br> [阶段 1：准备](migrate-to-defender-for-office-365-prepare.md)|[![阶段 2：设置。](../../media/phase-diagrams/setup.png)](migrate-to-defender-for-office-365-setup.md) <br> [阶段 2：设置](migrate-to-defender-for-office-365-setup.md)|![阶段 3：载入。](../../media/phase-diagrams/onboard.png) <br> 阶段 3：开始使用|
|---|---|---|
|||*你在这里！*|

欢迎使用 **阶段 3：载入** 迁移到 **[Microsoft Defender for Office 365！](migrate-to-defender-for-office-365.md#the-migration-process)** 此迁移阶段包括以下步骤：

1. [开始载入安全Teams](#step-1-begin-onboarding-security-teams)
2. [ (可选) 允许试点用户通过现有保护服务进行筛选](#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)
3. [优化欺骗智能](#step-3-tune-spoof-intelligence)
4. [优化模拟保护和邮箱智能](#step-4-tune-impersonation-protection-and-mailbox-intelligence)
5. [使用来自用户提交的数据进行度量和调整](#step-5-use-data-from-user-submissions-to-measure-and-adjust)
6. [ (可选) 向试点添加更多用户并进行访问](#step-6-optional-add-more-users-to-your-pilot-and-iterate)
7. [将Microsoft 365保护扩展到所有用户，并关闭 SCL=-1 邮件流规则](#step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule)
8. [切换 MX 记录](#step-8-switch-your-mx-records)

## <a name="step-1-begin-onboarding-security-teams"></a>步骤 1：开始载入Teams

如果你的组织有一个安全响应团队，那么现在应该开始将 Microsoft Defender for Office 365集成到响应流程，包括票证系统。 这是整个主题本身，但有时会被忽略。 提前让安全响应团队参与将确保你的组织准备好在切换 MX 记录时处理威胁。 事件响应需要具备处理以下任务的能力：

- 了解新工具并将其集成到现有流中。 例如：
  - 管理隔离邮件非常重要。 有关说明，请参阅 [以管理员角色管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。
  - 邮件跟踪允许你查看邮件进入或离开邮件时Microsoft 365。 有关详细信息，请参阅 Exchange Online 中新式 Exchange[管理中心中](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)Exchange Online。
- 确定可能允许进入组织的风险。
- 调整和 [自定义组织](../../compliance/alert-policies.md) 流程的警报。
- 管理事件队列并修正潜在风险。

如果你的组织已购买 Microsoft Defender Office 365计划 2，他们应开始熟悉和使用威胁资源管理器、高级搜寻和事件等功能。 有关相关培训，请参阅 <https://aka.ms/mdoninja> 。

如果安全响应团队收集并分析未筛选的邮件，您可以配置 SecOps 邮箱以接收这些未筛选的邮件。 有关说明，请参阅 [在高级传递策略中配置 SecOps 邮箱](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy)。

### <a name="siemsoar"></a>SIEM/SOAR

有关与 SIEM/SOAR 集成的信息，请参阅以下文章：

- [Microsoft 365 Defender API 概述](/microsoft-365/security/defender/api-overview)
- [Streaming API](/microsoft-365/security/defender/streaming-api)
- [高级搜寻 API](/microsoft-365/security/defender/api-advanced-hunting)
- [事件 API](/microsoft-365/security/defender/api-incident)

如果你的组织没有安全响应团队或现有流程流，可以使用这一次熟悉 Defender for Office 365 中的基本搜寻和响应功能。 有关详细信息，请参阅威胁 [调查和响应](office-365-ti.md)。

### <a name="rbac-roles"></a>RBAC 角色

Defender for Office 365 中的权限基于基于角色的访问控制 (RBAC) ，在 Microsoft 365 Defender 门户中进行了[解释](permissions-microsoft-365-security-center.md)。 请记住以下几点：

- Azure AD角色授予对 Microsoft 365 中所有工作负荷Microsoft 365。 例如，如果在 Azure 门户中将用户添加到安全管理员，则他们具有任何地方的安全管理员权限。
- 电子邮件&门户中的Microsoft 365 Defender协作角色授予对 Microsoft 365 Defender 门户、Microsoft 365 合规中心 和旧安全&中心的权限。 例如，如果您在 Microsoft 365 Defender 门户中将用户添加到安全管理员，则他们只能在 Microsoft 365 Defender 门户、Microsoft 365 合规中心和安全与合规中心&安全管理员访问权限。
- Microsoft 365 Defender 门户中的许多功能都基于 Exchange Online PowerShell cmd (let，因此需要相应角色（从技术上说，角色组) 在 Exchange Online (中的角色组）中具有角色组成员身份，以访问相应的Exchange OnlinePowerShell cmdlet) 。
- Microsoft 365 Defender 门户中的电子邮件&协作角色与 Azure AD 角色不等效，并且对于安全操作（例如预览角色和搜索和清除角色 (）非常重要) 。

通常，只有一部分安全人员需要其他权限才能直接从用户邮箱下载邮件。 这需要安全读者默认情况下没有的其他权限。

## <a name="step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service"></a>步骤 2： (可选) 试点用户免受现有保护服务的筛选

尽管此步骤不是必需的，但应考虑将试点用户配置为绕过现有保护服务的筛选。 此操作允许 Defender for **Office 365处理试点** 用户的所有筛选和保护职责。 如果不将试点用户从现有保护服务中排除，则 Defender for Office 365 仅对其他服务中的未接邮件进行有效 (筛选已筛选邮件) 。

> [!NOTE]
> 如果你的当前保护服务提供链接换行，但你想要试用链接功能，则保险箱此步骤。 不支持链接的双换行。

## <a name="step-3-tune-spoof-intelligence"></a>步骤 3：优化欺骗智能

查看 [欺骗智能见解](learn-about-spoof-intelligence.md) ，查看允许或阻止欺骗，并确定是否需要替代欺骗的系统裁定。 某些业务关键电子邮件源在 DNS (SPF、DKIM 和 DMARC) 中配置的电子邮件身份验证记录可能不正确，并且你可能正在使用现有保护服务中的替代来掩盖其域问题。

欺骗智能可以欺骗域中的电子邮件，但 DNS 中未提供正确的电子邮件身份验证记录，但此功能有时需要帮助区分良好的欺骗和错误的欺骗。 重点关注以下类型的邮件源：

- 在增强的连接器筛选中定义的 IP 地址范围 [之外的邮件源](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。
- 邮件数量最高的邮件源。
- 对组织影响最大的邮件源。

反欺骗智能最终将在配置用户提交后自行调整，因此无需进行欺骗。

## <a name="step-4-tune-impersonation-protection-and-mailbox-intelligence"></a>步骤 4：优化模拟保护和邮箱智能

在"不应用任何操作模式"中有足够的时间观察模拟保护的结果后，可以分别启用反网络钓鱼策略中的每个模拟保护操作：

- 用户模拟保护： **隔离标准邮件和** 严格邮件。
- 域模拟保护：隔离标准邮件 **和** 严格邮件。
- 邮箱智能保护 **：将邮件移动到收件人的"标准"垃圾邮件** 文件夹; **隔离邮件以使用** Strict。

监视模拟保护结果而不对邮件操作的时间越长，必须标识允许或阻止可能需要的数据就越长。 请考虑在打开每个足以允许观察和调整的保护之间使用延迟。

> [!NOTE]
> 经常持续监视和调整这些保护非常重要。 如果您怀疑误报，请调查原因，并仅在必要时使用替代，并仅对需要它的检测功能使用替代。

### <a name="tune-mailbox-intelligence"></a>优化邮箱智能

尽管邮箱智能已配置为不对确定为模拟尝试的邮件执行任何操作[](impersonation-insight.md)，但它一直在运行，并且了解试点用户的电子邮件发送和接收模式。 如果外部用户与试点用户之一联系，则邮箱智能系统不会将来自该外部用户的邮件标识为模拟 (从而减少误报) 。

准备好后，请执行以下步骤以允许邮箱智能对被检测为模拟尝试的邮件执行操作：

- 在具有标准保护设置的防钓鱼策略中，更改"如果邮箱智能检测到模拟用户，将邮件移动到收件人的垃圾邮件文件夹 **"的值**。

- 在具有严格保护设置的防钓鱼策略中，将"如果邮箱智能检测到 **并** 模拟用户"的值更改为"隔离 **邮件"。**

若要修改策略，请参阅在 Defender for [Office 365 中配置防钓鱼Office 365。](configure-mdo-anti-phishing-policies.md)

观察结果并做出任何调整后，继续下一部分以隔离用户模拟检测到的邮件。

### <a name="tune-user-impersonation-protection"></a>优化用户模拟保护

在基于"标准"和"严格"设置的两个反网络钓鱼策略中，将"如果邮件被检测为模拟用户"的值更改为"**隔离邮件"。**

检查 [模拟见解](impersonation-insight.md) 以查看在用户模拟尝试时被阻止的是什么。

若要修改策略，请参阅在 Defender for [Office 365 中配置防钓鱼Office 365。](configure-mdo-anti-phishing-policies.md)

观察结果并做出任何调整后，继续执行下一部分以隔离域模拟检测到的邮件。

### <a name="tune-domain-impersonation-protection"></a>优化域模拟保护

在基于"标准"和"严格"设置的两个反网络钓鱼策略中，将"如果邮件被检测为模拟域"的值更改为"**隔离邮件"。**

检查 [模拟见解](impersonation-insight.md) ，以查看在尝试域模拟时被阻止的是什么。

若要修改策略，请参阅在 Defender for [Office 365 中配置防钓鱼Office 365。](configure-mdo-anti-phishing-policies.md)

观察结果并根据需要做出任何调整。

## <a name="step-5-use-data-from-user-submissions-to-measure-and-adjust"></a>步骤 5：使用来自用户提交的数据进行度量和调整

当试点用户报告误报和漏报时，邮件将显示在"提交"页上的Microsoft 365 Defender[门户中](admin-submission.md)。 你可以将错误标识的邮件报告给 Microsoft 进行分析，并根据需要使用该信息调整试点策略中的设置和例外。

使用以下功能监视和访问 Defender for Office 365：

- [隔离](manage-quarantined-messages-and-files.md)
- [威胁资源管理器](email-security-in-microsoft-defender.md)
- [电子邮件安全报告](view-email-security-reports.md)
- [Defender for Office 365 报告](view-reports-for-mdo.md)
- [邮件流见解](/exchange/monitoring/mail-flow-insights/mail-flow-insights)
- [邮件流报告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)

如果组织为用户报告使用第三方服务，可以将该数据集成到反馈循环中。

## <a name="step-6-optional-add-more-users-to-your-pilot-and-iterate"></a>步骤 6： (可选) 向试点添加更多用户并进行访问

找到并修复问题后，你可以向试点组添加更多用户 (并相应地使这些新的试点用户免于根据情况由现有保护服务) 。 现在执行的测试越少，你稍后需要处理的用户问题就越少。 这种"瀑布"方法允许针对组织的较大部分进行调整，并让你的安全团队有时间来适应新的工具和流程。

- Microsoft 365组织策略允许高可信度网络钓鱼邮件时生成警报。 若要标识这些邮件，可以使用以下选项：
  - 威胁防护状态 [报告中的覆盖](view-email-security-reports.md#threat-protection-status-report)。
  - 在威胁资源管理器中筛选以标识邮件。
  - 在高级搜寻中筛选以标识邮件。

  通过管理员提交尽早向 Microsoft 报告任何误报，使用租户允许 [/](tenant-allow-block-list.md) 阻止列表功能为这些误报配置安全替代。

- 此外，还建议检查不必要的替代。 换句话说，查看对邮件Microsoft 365裁定。 如果 Microsoft365 呈现了正确的裁定，则替代需求将大大降低或消除。

## <a name="step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule"></a>步骤 7：Microsoft 365保护所有用户并关闭 SCL=-1 邮件流规则

准备好切换 MX 记录以指向目标记录时，请执行Microsoft 365。

1. 将试点策略扩展到整个组织。 从根本上说，有不同方法可以这样做：
   - 使用 [预设安全策略](preset-security-policies.md) ，将用户划分到标准保护配置文件和严格保护配置文件 (确保所有用户都涵盖在) 。 预设安全策略在你创建的任何自定义策略或任何默认策略之前应用。 你可以关闭单个试点策略，而无需删除它们。

     预设安全策略的缺点是，创建安全策略后，你无法更改很多重要设置。

   - 更改在试点期间创建和调整的策略范围，以包括所有 (，例如，所有域中的所有收件人) 。 请记住，如果同一类型的 (的多个策略（例如，防钓鱼策略) 按组成员身份或电子邮件域) 分别应用于同一用户 (，则只会应用优先级最高的策略 (最低优先级数字) 的设置，并且该类型的策略的处理将停止。

2. 关闭 SCL=-1 邮件流规则 (在不删除邮件流规则的情况下将其) 。

3. 确认以前的更改已生效，并且现在Office 365为所有用户正确启用 Defender for Office 365。 此时，Defender for Office 365 的所有保护功能现在都允许作用于所有收件人的邮件，但该邮件已经过现有保护服务扫描。

可以在此阶段暂停，进行更大规模的数据记录和调整。

## <a name="step-8-switch-your-mx-records"></a>步骤 8：切换 MX 记录

> [!NOTE]
>
> - 为域切换 MX 记录时，更改可能需要 48 小时才能传遍整个 Internet。
>
> - 我们建议降低 DNS 记录的 TTL 值，以启用更快的响应和可能的回滚 (如果需要) 。 您可以在切换完成并验证后还原到原始 TTL 值。
>
> - 您应考虑从更改使用频率较少的域开始。 在移动到更大的域之前，可以暂停和监视。 但是，即使这样做，您仍应确保策略涵盖所有用户和域，因为辅助 SMTP 域在策略应用程序之前解析为主域。
>   
> - 从技术上说，单个域的多个 MX 记录将正常工作，允许您进行拆分路由，但您必须遵循本文中所有指南。 具体来说，应确保策略应用于所有用户，SCL=-1 邮件流规则仅应用于通过现有保护服务的邮件，如安装程序步骤 3：维护或创建 [SCL=-1](migrate-to-defender-for-office-365-setup.md#step-3-maintain-or-create-the-scl-1-mail-flow-rule)邮件流规则中所述。 但是，此配置引入的行为使疑难解答变得更加困难，因此我们通常不建议这样做，尤其是在很长一段时间。
>
> - 在切换 MX 记录之前，请验证以下设置未在入站连接器上从保护服务启用Microsoft 365。 通常，连接器将配置以下一个或多个设置：
>
>   - **并要求** 合作伙伴用于通过身份验证的证书上的Office 365名称与 *RestrictDomainsToCertificate* (匹配) 
>   - **如果电子邮件不是从** *RestrictDomainsToIPAddresses* (IP 地址范围内发送，则拒绝) 
>
>   如果连接器类型为 **Partner** 且其中任一设置已打开，那么在切换 MX 记录后，发送到您的域的所有邮件都将失败。 在继续之前，需要禁用这些设置。 如果连接器是用于混合部署本地连接器，则无需修改内部部署连接器。 但是，你仍然可以检查是否存在合作伙伴 **连接器** 。
>   
> - 如果当前邮件网关也提供收件人验证，您可能需要检查域是否配置为 Microsoft 365。 [](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 这可以防止不必要的退回邮件。

准备好后，请切换域的 MX 记录。 可以一次迁移所有域。 或者，可以先迁移使用频率较少的域，然后再迁移其余域。

随时随时暂停和评估。 但请记住：一旦关闭 SCL=-1 邮件流规则，用户可能会获得两种不同的检查误报的体验。 越早地提供单一的一致体验，用户和技术支持团队在必须解决缺失的消息时就越困难。

## <a name="next-steps"></a>后续步骤

恭喜！ 你已完成到[Microsoft Defender 的迁移，Office 365！](migrate-to-defender-for-office-365.md#the-migration-process) 由于你遵循了此迁移指南中的步骤，邮件直接传递到邮件Microsoft 365应该更加顺畅。

现在，你开始正常操作和维护 Defender for Office 365。 监视和观察与试点期间所遇到问题类似的问题，但范围更大。 欺骗 [智能见解](learn-about-spoof-intelligence.md) 和 [模拟见解](impersonation-insight.md) 将最有用，但请考虑定期进行以下活动：

- 查看用户提交，尤其是 [用户报告的网络钓鱼邮件](/microsoft-365/security/office-365-security/automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)。
- 查看威胁防护状态 [报告中的覆盖](view-email-security-reports.md#threat-protection-status-report)。
- 使用 [高级搜寻](/microsoft-365/security/defender/advanced-hunting-example.md) 查询查找调整机会和有风险的消息。
