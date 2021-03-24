---
title: Microsoft 针对 EOP 和 Defender for Office 365 安全设置的建议
keywords: Office 365 安全建议， 发件人策略框架， 基于域的邮件报告和一致性， 域密钥标识的邮件， 步骤， 如何工作， 安全基线， EOP 基线， 适用于 Office 365 的 Defender 基线， 设置 Defender for Office 365， 设置 EOP， 配置 Office 365 Defender， 配置 EOP， 安全配置
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 什么是 Exchange Online Protection (EOP) 和 Defender for Office 365 安全设置的最佳实践？ 标准保护的当前建议是什么？ 如果要更加严格，应该使用什么？ 如果你还使用 Office 365 的 Defender，你会获得哪些额外功能？
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8ba88f9b9ebcc34e0ea146a74c01dea8f200ee0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056181"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>用于配置 EOP 和 Defender for Office 365 安全性的建议设置

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** 是 Microsoft 365 订阅的核心安全，有助于阻止恶意电子邮件到达员工的收件箱。 但是，随着每天出现更复杂的新攻击，通常需要改进的保护。 **Microsoft Defender for Office 365** 计划 1 或计划 2 包含其他功能，为管理员提供了多层安全、控制和调查。

尽管我们支持安全管理员自定义其安全设置，但我们建议的 EOP 和 Microsoft Defender for Office 365 有两个安全级别： **标准** 级别 **和严格级别**。 每个客户的环境和需求各不相同，但我们认为，这些筛选级别将有助于防止不需要的邮件在大多数情况下到达员工的收件箱。

若要自动将标准或严格设置应用于用户，请参阅在 EOP 和 [Microsoft Defender for Office 365](preset-security-policies.md)中预设安全策略。

> [!NOTE]
> 需要在邮箱上启用垃圾邮件规则，以便筛选正常工作。 默认情况下会启用此功能，但如果筛选似乎未正常工作，应检查它。 有关详细信息，请参阅[在 Office 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

本文介绍了默认设置以及建议的标准和严格设置，以帮助保护用户。

> [!TIP]
> 适用于 PowerShell 的 Office 365 高级威胁防护建议配置分析器 (ORCA) 模块可帮助你 (管理员) 查找这些设置的当前值。 具体来说 **，Get-ORCAReport** cmdlet 可生成对反垃圾邮件、防钓鱼和其他邮件安全设置的评估。 可以在 下载 ORCA 模块 <https://www.powershellgallery.com/packages/ORCA/> 。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP 中的反垃圾邮件、反恶意软件和防钓鱼保护

反垃圾邮件、反恶意软件和防钓鱼是 EOP 功能，管理员可配置这些功能。 建议采用以下标准或严格配置。

### <a name="eop-anti-spam-policy-settings"></a>EOP 反垃圾邮件策略设置

若要创建和配置反垃圾邮件策略，请参阅 [在 Office 365](configure-your-spam-filter-policies.md)中配置反垃圾邮件策略。

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**垃圾邮件** 检测操作 <p> _SpamAction_|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**高可信度垃圾邮件** 检测操作 <p> _HighConfidenceSpamAction_|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**网络钓鱼电子邮件** 检测操作 <p> _PhishSpamAction_|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**高可信度钓鱼电子邮件** 检测操作 <p> _HighConfidencePhishAction_|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**批量电子邮件** 检测操作 <p> _BulkSpamAction_|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|批量电子邮件阈值 <p> _BulkThreshold_|7 |6 |4 |有关详细信息，请参阅[批量投诉级别 (BCL) Office 365。](bulk-complaint-level-values.md)|
|隔离保留期 <p> _QuarantineRetentionPeriod_|15 天|30 天|30 天||
|**安全提示** <p> _InlineSafetyTipsEnabled_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|允许的发件人 <p> _AllowedSenders_|无|无|无||
|允许的发件人域 <p> _AllowedSenderDomains_|无|无|无|将域添加到允许的发件人列表不是一个好主意。 攻击者可以向您发送其他将被筛选掉的电子邮件。 <p> 在安全[&](learn-about-spoof-intelligence.md)合规中心的"反垃圾邮件设置"页面上使用欺骗智能，查看在组织的电子邮件域中欺骗发件人电子邮件地址或外部域中的欺骗发件人电子邮件地址的所有发件人。|
|阻止的发件人 <p> _BlockedSenders_|无|无|无||
|阻止的发件人域 <p> _BlockedSenderDomains_|无|无|无||
|**启用最终用户垃圾邮件通知**   选中此复选框以启用此策略的最终用户垃圾邮件通知。 <p> _EnableEndUserSpamNotifications_|已禁用 <p> `$false`|已启用 <p> `$true`|已启用 <p> `$true`||
|**每两天发送一次最终用户 (垃圾邮件)** <p> _EndUserSpamNotificationFrequency_|3 天|3 天|3 天||
|**垃圾邮件 ZAP** <p> _SpamZapEnabled_|已启用 <p> `$true`|已启用 <p> `$true`|已启用 <p> `$true`||
|**钓鱼邮件 ZAP** <p> _PhishZapEnabled_|已启用 <p> `$true`|已启用 <p> `$true`|已启用 <p> `$true`||
|_MarkAsSpamBulkMail_|打开|打开|打开|此设置仅在 PowerShell 中可用。|
|

反垃圾邮件策略中还有一 (高级垃圾邮件筛选器) ASF 筛选器设置，这些设置正在被弃用。 有关这些功能的折旧时间线详细信息将在本文之外进行介绍。

对于"标准"和"严格"级别，我们建议你关闭这些 ASF **设置。** 有关 ASF 设置详细信息，请参阅[Advanced Spam Filter (ASF) settings in Office 365。](advanced-spam-filtering-asf-options.md)

****

|安全功能名称|评论|
|---|---|
|**指向远程站点的图像链接 (** _IncreaseScoreWithImageLinks)_||
|**URL 中的数字 IP** 地址 (_IncreaseScoreWithNumericIps)_||
|**UL 重定向到** _IncreaseScoreWithRedirectToOtherPort_ (的其他端口) ||
|_IncreaseScoreWithBizOrInfoUrls_ **(.biz** 或 .info 网站的 URL) ||
| _MarkAsSpamEmptyMessages_ (空) ||
|**Html 格式的 JavaScript 或 VBScript** (_MarkAsSpamJavaScriptInHtml_) ||
|_MarkAsSpamFramesInHtml_ (HTML 格式的框架或 **IFrame**) ||
|**HTML 格式的对象标记 (** _MarkAsSpamObjectTagsInHtml_) ||
| _MarkAsSpamEmbedTagsInHtml (HTML 格式的嵌入_) ||
|**HTML 格式的表单** (_MarkAsSpamFormTagsInHtml_) ||
| _MarkAsSpamWebBugsInHtml_ (HTML 中的 Web) ||
|**将敏感词列表 (** _MarkAsSpamSensitiveWordList_) ||
|**SPF 记录** ：MarkAsSpamSpfRecordHardFail (硬 _失败_) ||
|**条件发件人 ID 筛选**：MarkAsSpamFromAddressAuthFail (_硬失败)_||
|**NDR 退 (** _MarkAsSpamNdrBackscatter)_||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 出站垃圾邮件策略设置

若要创建和配置出站垃圾邮件策略，请参阅在 [Office 365](configure-the-outbound-spam-policy.md)中配置出站垃圾邮件筛选。

有关服务中的默认发送限制详细信息，请参阅发送 [限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**每个用户的最大收件人数：外部每小时限制** <p> _RecipientLimitExternalPerHour_|0|500|400|默认值 0 表示使用服务默认值。|
|**每个用户的最大收件人数：内部每小时限制** <p> _RecipientLimitInternalPerHour_|0|1000|800|默认值 0 表示使用服务默认值。|
|**每个用户的最大收件人数：每日限制** <p> _RecipientLimitPerDay_|0|1000|800|默认值 0 表示使用服务默认值。|
|**用户超出限制时的操作** <p> _ActionWhenThresholdReached_|**限制用户于第二天之前发送邮件** <p> `BlockUserForToday`|**限制用户发送邮件** <p> `BlockUser`|**限制用户发送邮件** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP 反恶意软件策略设置

若要创建和配置反恶意软件策略，请参阅 [在 Office 365](configure-anti-malware-policies.md)中配置反恶意软件策略。

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**是否要在收件人的邮件被隔离时通知收件人？** <p> _操作_|否 <p> _DeleteMessage_|否 <p> _DeleteMessage_|否 <p> _DeleteMessage_|如果在电子邮件附件中检测到恶意软件，邮件将被隔离，并且只有管理员才能释放。|
|**常见附件类型筛选器** <p> _EnableFileFilter_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`|此设置根据文件类型隔离包含可执行附件的邮件，而不考虑附件内容。|
|**恶意软件零时差自动清除** <p> _ZapEnabled_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|**通知内部发件人** 未送达邮件 <p> _EnableInternalSenderNotifications_|Disabled <p> `$false`|Disabled <p> `$false`|Disabled <p> `$false`||
|**通知外部发件人** 未送达邮件 <p> _EnableExternalSenderNotifications_|Disabled <p> `$false`|Disabled <p> `$false`|Disabled <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP 默认防钓鱼策略设置

有关这些设置详细信息，请参阅欺骗 [设置](set-up-anti-phishing-policies.md#spoof-settings)。 若要配置这些设置，请参阅在 EOP 中配置防 [钓鱼策略](configure-anti-phishing-policies-eop.md)。

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**启用反欺骗保护** <p> _EnableSpoofIntelligence_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|**启用未经身份验证的发件人** <p> _EnableUnauthenticatedSender_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`|在 Outlook () 发件人的照片上添加一个问号。 有关详细信息，请参阅反网络钓鱼 [策略中的欺骗设置](set-up-anti-phishing-policies.md)。|
|**如果电子邮件是由不允许欺骗你的域的人发送的** <p> _AuthenticationFailAction_|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**隔离邮件** <p> `Quarantine`|此设置适用于欺骗智能中阻止 [的发件人](learn-about-spoof-intelligence.md)。|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender for Office 365 安全性

Microsoft Defender for Office 365 订阅还具有其他安全优势。 有关最新新闻和信息，请参阅 Defender [for Office 365 中的新增功能](whats-new-in-defender-for-office-365.md)。

> [!IMPORTANT]
>
> - Microsoft Defender for Office 365 中的默认防钓鱼 [策略可为所有](set-up-anti-phishing-policies.md#spoof-settings) 收件人提供欺骗保护和邮箱智能。 但是，其他 [可用的模拟保护](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 功能和 [高级](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 设置未在默认策略中配置或启用。 若要启用所有保护功能，请修改默认的防钓鱼策略或创建其他防钓鱼策略。
>
> - 没有可自动保护组织所有收件人的默认安全链接策略或安全附件策略。 若要获得保护，需要创建至少一个安全链接策略和安全附件策略。
>
> - [SharePoint、OneDrive 和 Microsoft Teams](mdo-for-spo-odb-and-teams.md) 保护和 [安全文档](safe-docs.md) 保护的安全附件不依赖于安全链接策略。

如果你的订阅包含适用于 Office 365 的 Microsoft Defender，或者你已购买 Defender for Office 365 作为加载项，请设置以下标准或严格配置。

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略设置

如前文所述，EOP 客户会获得基本的防钓鱼功能，但 Microsoft Defender for Office 365 包含了更多功能和控制，以帮助防止、检测和修正攻击。 若要创建和配置这些策略，请参阅 [在 Defender for Office 365](configure-atp-anti-phishing-policies.md)中配置防钓鱼策略。

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略中的模拟设置

有关这些设置详细信息，请参阅 Microsoft [Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)中的防钓鱼策略中的模拟设置。 若要配置这些设置，请参阅 [在 Defender for Office 365](configure-atp-anti-phishing-policies.md)中配置防钓鱼策略。

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|受保护的用户： **添加要保护的用户** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|关闭 <p> `$false` <p> 无|打开 <p> `$true` <p> \<list of users\>|打开 <p> `$true` <p> \<list of users\>|根据组织的不同，我们建议在 (角色) 用户。 在内部，受保护的发件人可能是 CEO、CFO 和其他高级领导。 从外部来说，受保护的发件人可以包含会员或你的委员会。|
|受保护的域 **：自动包含我拥有域** <p> _EnableOrganizationDomainsProtection_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|受保护的域： **包括自定义域** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|关闭 <p> `$false` <p> 无|打开 <p> `$true` <p> \<list of domains\>|打开 <p> `$true` <p> \<list of domains\>|根据你的组织，我们建议 (您) 但您经常交互的发件人域中添加域。|
|受保护的用户 **：如果电子邮件是由模拟用户发送的** <p> _TargetedUserProtectionAction_|**不应用任何操作** <p> `NoAction`|**隔离邮件** <p> `Quarantine`|**隔离邮件** <p> `Quarantine`||
|受保护的域 **：如果电子邮件由模拟的域发送** <p> _TargetedDomainProtectionAction_|**不应用任何操作** <p> `NoAction`|**隔离邮件** <p> `Quarantine`|**隔离邮件** <p> `Quarantine`||
|**为模拟用户显示提示** <p> _EnableSimilarUsersSafetyTips_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**显示模拟域的提示** <p> _EnableSimilarDomainsSafetyTips_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**显示异常字符的提示** <p> _EnableUnusualCharactersSafetyTips_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**启用邮箱智能？** <p> _EnableMailboxIntelligence_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|**启用基于邮箱智能的模拟保护？** <p> _EnableMailboxIntelligenceProtection_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**如果电子邮件由受邮箱智能保护的模拟用户发送** <p> _MailboxIntelligenceProtectionAction_|**不应用任何操作** <p> `NoAction`|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**隔离邮件** <p> `Quarantine`||
|**受信任的发件人** <p> _ExcludedSenders_|无|无|无|根据您的组织，我们建议添加仅由于模拟而非其他筛选器而错误地标记为网络钓鱼的用户。|
|**受信任的域** <p> _ExcludedDomains_|无|无|无|根据您的组织，我们建议添加仅由于模拟而非其他筛选器而错误地标记为网络钓鱼的域。|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略中的欺骗设置

请注意，这些设置与 EOP 中的反垃圾邮件 [策略设置中的设置相同](#eop-anti-spam-policy-settings)。

****

|安全功能名称|默认|标准|Strict|评论|
|---|---|---|---|---|
|**启用反欺骗保护** <p> _EnableSpoofIntelligence_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|**启用未经身份验证的发件人** <p> _EnableUnauthenticatedSender_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`|在 Outlook () 发件人的照片上添加一个问号。 有关详细信息，请参阅反网络钓鱼 [策略中的欺骗设置](set-up-anti-phishing-policies.md)。|
|**如果电子邮件是由不允许欺骗你的域的人发送的** <p> _AuthenticationFailAction_|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**隔离邮件** <p> `Quarantine`|此设置适用于欺骗智能中阻止 [的发件人](learn-about-spoof-intelligence.md)。|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略中的高级设置

有关此设置详细信息，请参阅 Microsoft [Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)中的反网络钓鱼策略中的高级网络钓鱼阈值。 若要配置此设置，请参阅 [在 Defender for Office 365](configure-atp-anti-phishing-policies.md)中配置防钓鱼策略。

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**高级网络钓鱼阈值** <p> _PhishThresholdLevel_|**1 - 标准** <p> `1`|**2 - 主动** <p> `2`|**3 - 更主动** <p> `3`||
|

### <a name="safe-links-settings"></a>安全链接设置

适用于 Office 365 的 Defender 中的安全链接包括适用于活动安全链接策略中包含的所有用户的全局设置，以及特定于每个安全链接策略的设置。 有关详细信息，请参阅适用于 [Office 365 的 Defender 中的安全链接](safe-links.md)。

#### <a name="global-settings-for-safe-links"></a>安全链接的全局设置

若要配置这些设置，请参阅 [在 Defender for Office 365](configure-global-settings-for-safe-links.md)中为安全链接配置全局设置。

在 PowerShell 中，对这些设置使用 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) cmdlet。

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**在 Office 365 应用程序中使用安全链接** <p> _EnableSafeLinksForO365Clients_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`|在受支持的 Office 365 桌面和移动版 iOS 和 Android (应用中使用安全) 链接。 有关详细信息，请参阅 Office [365 应用的安全链接设置](safe-links.md#safe-links-settings-for-office-365-apps)。|
|**不跟踪用户单击安全链接时** <p> _TrackClicks_|开 <p> `$false`|关 <p> `$true`|关闭 <p> `$true`|关闭此设置 (_将 TrackClicks_ 设置为 `$true`) 跟踪受支持的 Office 365 应用中的用户点击量。|
|**不允许用户单击"安全链接至原始 URL"** <p> _AllowClickThrough_|打开 <p> `$false`|打开 <p> `$false`|打开 <p> `$false`|打开此设置 (将 _AllowClickThrough_ 设置为) 阻止单击到受支持的 `$false` Office 365 应用中的原始 URL。|
|

#### <a name="safe-links-policy-settings"></a>安全链接策略设置

若要配置这些设置，请参阅在 [Microsoft Defender for Office 365](set-up-safe-links-policies.md)中设置安全链接策略。

在 PowerShell 中，将 [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) 和 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) cmdlet 用于这些设置。

> [!NOTE]
> 如前面所述，没有默认安全链接策略。 "默认"列中的值是新建的安全链接策略中的默认值。

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**选择邮件中未知潜在恶意 URL 的操作** <p> _IsEnabled_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**选择 Microsoft Teams 中未知或潜在恶意 URL 的操作** <p> _EnableSafeLinksForTeams_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**对指向文件的可疑链接应用实时 URL 扫描** <p> _ScanUrls_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**等待 URL 扫描完成，然后再传递邮件** <p> _DeliverMessageAfterScan_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**将安全链接应用于在组织内部发送的电子邮件** <p> _EnableForInternalSenders_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**不跟踪用户单击** <p> _DoNotTrackUserClicks_|关闭 <p> `$false`|关闭 <p> `$false`|关闭 <p> `$false`|关闭此设置后 (_DoNotTrackUserClicks_ 设置为) `$false` 用户单击。|
|**不允许用户单击至初始 URL** <p> _DoNotAllowClickThrough_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`|打开此设置 (_DoNotAllowClickThrough_ 设置为) `$true` 阻止单击访问原始 URL。|
|

### <a name="safe-attachments-settings"></a>安全附件设置

Microsoft Defender for Office 365 中的安全附件包括与安全附件策略没有任何关系的全局设置，以及特定于每个安全链接策略的设置。 有关详细信息，请参阅 Defender [for Office 365](safe-attachments.md)中的安全附件。

#### <a name="global-settings-for-safe-attachments"></a>安全附件的全局设置

若要配置这些设置，请参阅启用 [SharePoint、OneDrive](turn-on-mdo-for-spo-odb-and-teams.md) 和 Microsoft Teams 的安全附件以及 [Microsoft 365 E5 中的安全文档](safe-docs.md)。

在 PowerShell 中，对这些设置使用 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) cmdlet。

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Defender for Office 365** <p> _EnableATPForSPOTeamsODB_|打开 <p> `$true`|打开 <p> `$true`||
|**打开 Office 客户端的安全文档** <p> _EnableSafeDocs_|打开 <p> `$true`|打开 <p> `$true`|此设置仅适用于 Microsoft 365 E5 或 Microsoft 365 E5 安全许可证。 有关详细信息，请参阅 [Microsoft Defender for Office 365 中的安全文档](safe-docs.md)。|
|**即使安全文档将文件标识为恶意文件，也允许用户单击"受保护的视图"** <p> _AllowSafeDocsOpen_|关闭 <p> `$false`|关闭 <p> `$false`|此设置与安全文档相关。|
|

#### <a name="safe-attachments-policy-settings"></a>安全附件策略设置

若要配置这些设置，请参阅在 [Defender for Office 365](set-up-safe-attachments-policies.md)中设置安全附件策略。

在 PowerShell 中，将 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) 和 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) cmdlet 用于这些设置。

> [!NOTE]
> 如前面所述，没有默认安全附件策略。 "默认"列中的值是新建的安全附件策略中的默认值。

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**安全附件未知恶意软件响应** <p> _操作_|阻止 <p> `Block`|阻止 <p> `Block`|阻止 <p> `Block`||
|**检测时重定向附件** ： **启用重定向** <p> _重定向_ <p> _RedirectAddress_|关闭，未指定电子邮件地址。 <p> `$true` <p> 无|打开，并指定电子邮件地址。 <p> `$true` <p> 电子邮件地址|打开，并指定电子邮件地址。 <p> `$true` <p> 电子邮件地址|将邮件重定向到安全管理员进行审阅。|
|**如果恶意软件扫描附件出现时间过或出现错误，则应用上述选择。** <p> _ActionOnError_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|

## <a name="related-articles"></a>相关文章

- 您是否正在查找 Exchange **邮件流规则** （也称为传输 (传输规则）) ？ 请参阅 [在 Exchange Online 中配置邮件流规则的最佳实践](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)。

- 管理员和用户可以提交误报 (标记为错误) 误报 (错误电子邮件) Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

- 使用这些链接获取有关如何设置[EOP](set-up-your-eop-service.md)服务以及如何为[Office 365](defender-for-office-365.md)配置 Microsoft Defender 的信息。  不要忘记'防止[Office 365](protect-against-threats.md)中的威胁'中的有用说明。

- 可在此处找到 **Windows** 的安全基线：在哪里可以获取 GPO/本地选项的安全基线 [？](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)以及使用安全基线在 Intune 中为基于 Intune 的安全性配置 [Windows 10](/intune/protect/security-baselines)设备。 最后，比较适用于 Endpoint 的 Microsoft Defender 和 Microsoft Intune 安全基线中提供了比较 Microsoft Defender for Endpoint 和[Windows Intune 安全基线。](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)