---
title: Microsoft for EOP and Defender for Office 365 安全设置、建议、发件人策略框架、基于域的邮件报告和合规性、域密钥识别的邮件、步骤、工作原理、安全性基线、EOP 的基线、Office 365 365 的 defender for office 365、configure EOP、security configuration
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Exchange Online Protection (EOP) 和 Defender for Office 365 安全设置的最佳实践是什么？ 有关标准保护的当前建议是什么？ 如果您想要更加严格，应使用什么？ 如果你还使用适用于 Office 365 的 Defender，你还会获得什么额外内容？
ms.openlocfilehash: af741e1af412d535c53beb83c36c0cbe3fcd617b
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357117"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>EOP 和 Microsoft Defender for Office 365 安全性的建议设置

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Exchange Online Protection (EOP)** 是 Microsoft 365 订阅的安全性的核心，可帮助防止恶意电子邮件到达你的员工的收件箱。 但对于每天都会涌现的新的更复杂的攻击，通常需要改进的保护。 **Microsoft Defender For Office 365** 计划1或计划2包含额外的功能，可为管理员提供更多的安全、控制和调查层次。

尽管我们为安全管理员提供了自定义安全设置，但我们建议的 EOP 和 Microsoft Defender for Office 365 中有两个安全级别： **标准** 和 **严格**。 每个客户的环境和需求各不相同，但我们认为这些级别的筛选将有助于防止不需要的邮件在大多数情况下到达员工的收件箱。

若要自动将标准或严格设置应用于用户，请参阅 [EOP And Microsoft Defender For Office 365 中的预设安全策略](preset-security-policies.md)。

> [!NOTE]
> 需要在邮箱上启用垃圾邮件规则，以便筛选正常工作。 默认情况下已启用，但如果筛选似乎不起作用，则应进行检查。 有关详细信息，请参阅[在 Office 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

本文介绍了默认设置，以及建议的标准和严格设置，以帮助保护您的用户。

> [!TIP]
> Office 365 高级威胁防护建议的 Configuration Analyzer (ORCA) module for PowerShell 可帮助您 (管理员) 查找这些设置的当前值。 具体来说， **ORCAReport** cmdlet 会生成反垃圾邮件、反网络钓鱼和其他邮件清洁设置的评估。 您可以在中下载 ORCA 模块 <https://www.powershellgallery.com/packages/ORCA/> 。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP 中的反垃圾邮件、反恶意软件和反网络钓鱼防护

反垃圾邮件、反恶意软件和反网络钓鱼是可由管理员配置的 EOP 功能。 建议采用以下标准或严格配置。

### <a name="eop-anti-spam-policy-settings"></a>EOP 反垃圾邮件策略设置

若要创建和配置反垃圾邮件策略，请参阅 [在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

****

|安全功能名称|默认|标准版|全|评论|
|---|:---:|:---:|:---:|---|
|**垃圾邮件** 检测操作 <p> _SpamAction_|**将邮件移动到 "垃圾邮件" 文件夹** <p> `MoveToJmf`|**将邮件移动到 "垃圾邮件" 文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**高可信度垃圾邮件** 检测操作 <p> _HighConfidenceSpamAction_|**将邮件移动到 "垃圾邮件" 文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**网络钓鱼电子邮件** 检测操作 <p> _PhishSpamAction_|**将邮件移动到 "垃圾邮件" 文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**高可信度网络钓鱼电子邮件** 检测操作 <p> _HighConfidencePhishAction_|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**批量电子邮件** 检测操作 <p> _BulkSpamAction_|**将邮件移动到 "垃圾邮件" 文件夹** <p> `MoveToJmf`|**将邮件移动到 "垃圾邮件" 文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|批量电子邮件阈值 <p> _BulkThreshold_|7 |6 |4 |有关详细信息，请参阅 [Office 365 中的批量投诉级别 (BCL) ](bulk-complaint-level-values.md)。|
|隔离保留期 <p> _QuarantineRetentionPeriod_|15 天|30 天|30 天||
|**安全提示** <p> _InlineSafetyTipsEnabled_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|允许的发件人 <p> _AllowedSenders_|无|无|无||
|允许的发件人域 <p> _AllowedSenderDomains_|无|无|无|将域添加到允许的发件人列表是一个非常糟糕的想法。 攻击者能够向您发送电子邮件，否则将被筛选掉。 <p> 在 "**反垃圾邮件设置**" 页上的安全性 & 合规性中心中使用 [欺骗智能](learn-about-spoof-intelligence.md)，以查看在组织的电子邮件域或外部域中的欺骗发件人电子邮件地址中的所有人都是哄骗发件人的电子邮件地址。|
|阻止的发件人 <p> _BlockedSenders_|无|无|无||
|阻止的发件人域 <p> _BlockedSenderDomains_|无|无|无||
|**启用最终用户垃圾邮件通知**   选中此复选框以启用此策略的最终用户垃圾邮件通知。 <p> _EnableEndUserSpamNotifications_|已禁用 <p> `$false`|已启用 <p> `$true`|已启用 <p> `$true`||
|**每 (天发送最终用户垃圾邮件通知)** <p> _EndUserSpamNotificationFrequency_|3 天|3 天|3 天||
|**垃圾邮件 ZAP** <p> _SpamZapEnabled_|已启用 <p> `$true`|已启用 <p> `$true`|已启用 <p> `$true`||
|**网络钓鱼 ZAP** <p> _PhishZapEnabled_|已启用 <p> `$true`|已启用 <p> `$true`|已启用 <p> `$true`||
|_MarkAsSpamBulkMail_|打开|打开|打开|此设置仅在 PowerShell 中可用。|
|

在反垃圾邮件策略中，有几个其他高级垃圾邮件筛选器 (ASF) 设置处于弃用的过程中。 有关这些功能的折旧时限的详细信息，请在本文之外进行交流。

我们建议您为 **标准** 和 **严格** 级别 **关闭这些** ASF 设置。 有关 ASF 设置的详细信息，请参阅 [Office 365 中的高级垃圾邮件筛选器 (ASF) 设置](advanced-spam-filtering-asf-options.md)。

****

|安全功能名称|评论|
|---|---|
|**指向远程网站** (_IncreaseScoreWithImageLinks_) 的图像链接||
|URL (_IncreaseScoreWithNumericIps_ **中的数字 IP 地址**) ||
|**UL 重定向到其他端口** (_IncreaseScoreWithRedirectToOtherPort_) ||
|**.Biz 或. info 网站的 URL** (_IncreaseScoreWithBizOrInfoUrls_) ||
| (_MarkAsSpamEmptyMessages_) 中的 **空邮件**||
|**在 HTML (MarkAsSpamJavaScriptInHtml 中的 JavaScript 或 VBScript**) _MarkAsSpamJavaScriptInHtml_||
|HTML (_MarkAsSpamFramesInHtml_ **中的 Frame 或 IFrame 标记**) ||
|HTML (_MarkAsSpamObjectTagsInHtml_) **中的对象标记**||
|在 HTML (_MarkAsSpamEmbedTagsInHtml_) **中嵌入标记**||
|HTML (_MarkAsSpamFormTagsInHtml_) **中的表单标记**||
|HTML (_MarkAsSpamWebBugsInHtml_) **中的 Web 错误**||
|**将敏感单词列表应用** (_MarkAsSpamSensitiveWordList_) ||
|**SPF 记录： hard fail** (_MarkAsSpamSpfRecordHardFail_) ||
|**条件发件人 ID 筛选：硬失败** (_MarkAsSpamFromAddressAuthFail_) ||
|**NDR 退信** (_MarkAsSpamNdrBackscatter_) ||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 出站垃圾邮件策略设置

若要创建和配置出站垃圾邮件策略，请参阅 [在 Office 365 中配置出站垃圾邮件筛选](configure-the-outbound-spam-policy.md)。

有关服务中的默认发送限制的详细信息，请参阅 [发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

****

|安全功能名称|默认|标准版|全|评论|
|---|:---:|:---:|:---:|---|
|**每个用户的最大收件人数：外部每小时限制** <p> _RecipientLimitExternalPerHour_|0|500|400|默认值0表示使用服务默认设置。|
|**每个用户的最大收件人数：每小时的内部限制** <p> _RecipientLimitInternalPerHour_|0|1000|800|默认值0表示使用服务默认设置。|
|**每个用户的最大收件人数：每日限制** <p> _RecipientLimitPerDay_|0|1000|800|默认值0表示使用服务默认设置。|
|**用户超出限制时的操作** <p> _ActionWhenThresholdReached_|**限制用户在以下日期之前发送邮件** <p> `BlockUserForToday`|**限制用户发送邮件** <p> `BlockUser`|**限制用户发送邮件** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP 反恶意软件策略设置

若要创建和配置反恶意软件策略，请参阅 [在 Office 365 中配置反恶意软件策略](configure-anti-malware-policies.md)。

****

|安全功能名称|默认|标准版|全|评论|
|---|:---:|:---:|:---:|---|
|**是否要在邮件被隔离时通知收件人？** <p> _操作_|否 <p> _DeleteMessage_|否 <p> _DeleteMessage_|否 <p> _DeleteMessage_|如果在电子邮件附件中检测到恶意软件，则会隔离邮件，并且只能由管理员进行发布。|
|**常见附件类型筛选器** <p> _EnableFileFilter_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`|此设置隔离基于文件类型的包含可执行附件的邮件，而不考虑附件内容。|
|**恶意软件零小时自动清除** <p> _ZapEnabled_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|**通知内部发件人** 未送达邮件 <p> _EnableInternalSenderNotifications_|禁用 <p> `$false`|禁用 <p> `$false`|禁用 <p> `$false`||
|**通知外部发件人** 未送达的邮件 <p> _EnableExternalSenderNotifications_|禁用 <p> `$false`|禁用 <p> `$false`|禁用 <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP 默认的反网络钓鱼策略设置

有关这些设置的详细信息，请参阅 [欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。 若要配置这些设置，请参阅 [在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。

****

|安全功能名称|默认|标准版|全|评论|
|---|:---:|:---:|:---:|---|
|**启用反欺骗保护** <p> _EnableAntispoofEnforcement_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|**启用未经验证的发件人** <p> _EnableUnauthenticatedSender_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`|在 Outlook 中向发件人的照片添加问号 ( ) ，以查找未识别的欺骗性发件人。 有关详细信息，请参阅 [反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md)。|
|**如果电子邮件由不允许欺骗您的域的人发送** <p> _AuthenticationFailAction_|**将邮件移到收件人的 "垃圾邮件" 文件夹** <p> `MoveToJmf`|**将邮件移到收件人的 "垃圾邮件" 文件夹** <p> `MoveToJmf`|**隔离邮件** <p> `Quarantine`|此设置适用于 [欺骗智能](learn-about-spoof-intelligence.md)中阻止的发件人。|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender for Office 365 安全

Microsoft Defender for Office 365 订阅提供了其他安全优势。 有关最新的新闻和信息，可以查看 [在 Office 365 中的新增功能](whats-new-in-office-365-atp.md)。

> [!IMPORTANT]
>
> - Microsoft Defender for Office 365 中的默认反网络钓鱼策略为所有收件人提供 [欺骗保护](set-up-anti-phishing-policies.md#spoof-settings) 和邮箱智能。 但是，未在默认策略中配置或启用其他可用的 [模拟保护](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 功能和 [高级设置](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 。 若要启用所有保护功能，请修改默认的反网络钓鱼策略或创建其他反网络钓鱼策略。
>
> - 没有可自动保护组织中所有收件人的默认安全链接策略或安全附件策略。 若要获取保护，您需要至少创建一个安全链接策略和安全附件策略。
>
> - [SharePoint、OneDrive 和 Microsoft 团队](atp-for-spo-odb-and-teams.md) 保护和 [安全文档](safe-docs.md) 保护的 ATP 对安全链接策略没有任何依赖关系。

如果你的订阅包括 Microsoft Defender for Office 365，或者你已购买适用于 Office 365 的 Defender 作为加载项，请设置以下标准或严格配置。

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的反网络钓鱼策略设置

EOP 客户将获取前面所述的基本反网络钓鱼，但 Microsoft Defender for Office 365 包含更多的功能和控制，可帮助预防、检测和补救攻击。 若要创建和配置这些策略，请参阅 [在 Office 365 的 Defender 中配置反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的反网络钓鱼策略中的模拟设置

有关这些设置的详细信息，请参阅 [Microsoft Defender For Office 365 中的模拟设置中的反网络钓鱼策略](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。 若要配置这些设置，请参阅 [在 Office 365 的 Defender 中配置反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。

****

|安全功能名称|默认|标准版|全|评论|
|---|:---:|:---:|:---:|---|
|受保护的用户： **添加要保护的用户** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|关闭 <p> `$false` <p> 无|打开 <p> `$true` <p> \<list of users\>|打开 <p> `$true` <p> \<list of users\>|根据你的组织，我们建议在关键角色中向用户添加 (邮件发件人) 。 在内部，受保护的发件人可能是 CEO、CFO 和其他高级领导者。 外部，受保护的发件人可以包括理事会成员或董事会。|
|受保护的域： **自动包括我拥有的域** <p> _EnableOrganizationDomainsProtection_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|受保护的域： **包含自定义域** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|关闭 <p> `$false` <p> 无|打开 <p> `$true` <p> \<list of domains\>|打开 <p> `$true` <p> \<list of domains\>|根据您的组织，我们建议您在不拥有的情况下添加域 (发件人域) ，但经常与您进行交互。|
|受保护的用户： **如果模拟用户发送电子邮件** <p> _TargetedUserProtectionAction_|**不应用任何操作** <p> `NoAction`|**隔离邮件** <p> `Quarantine`|**隔离邮件** <p> `Quarantine`||
|受保护的域： **如果模拟域发送电子邮件** <p> _TargetedDomainProtectionAction_|**不应用任何操作** <p> `NoAction`|**隔离邮件** <p> `Quarantine`|**隔离邮件** <p> `Quarantine`||
|**为模拟用户显示提示** <p> _EnableSimilarUsersSafetyTips_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**显示模拟域的提示** <p> _EnableSimilarDomainsSafetyTips_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**显示不正常字符的提示** <p> _EnableUnusualCharactersSafetyTips_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**是否启用邮箱智能？** <p> _EnableMailboxIntelligence_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|**是否启用基于邮箱智能的模拟保护？** <p> _EnableMailboxIntelligenceProtection_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**如果由邮箱智能保护的模拟用户发送电子邮件** <p> _MailboxIntelligenceProtectionAction_|**不应用任何操作** <p> `NoAction`|**将邮件移到收件人的 "垃圾邮件" 文件夹** <p> `MoveToJmf`|**隔离邮件** <p> `Quarantine`||
|**受信任的发件人** <p> _ExcludedSenders_|无|无|无|根据你的组织，我们建议添加因仅模拟而不是其他筛选器而错误地将其标记为网络钓鱼的用户。|
|**受信任域** <p> _ExcludedDomains_|无|无|无|根据您的组织，我们建议添加由于仅模拟而不是其他筛选器而被错误地标记为网络钓鱼的域。|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的反网络钓鱼策略中的欺骗设置

请注意，这些设置与 [EOP 中的反垃圾邮件策略设置](#eop-anti-spam-policy-settings)中提供的设置相同。

****

|安全功能名称|默认|标准版|全|评论|
|---|---|---|---|---|
|**启用反欺骗保护** <p> _EnableAntispoofEnforcement_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|**启用未经验证的发件人** <p> _EnableUnauthenticatedSender_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`|在 Outlook 中向发件人的照片添加问号 ( ) ，以查找未识别的欺骗性发件人。 有关详细信息，请参阅 [反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md)。|
|**如果电子邮件由不允许欺骗您的域的人发送** <p> _AuthenticationFailAction_|**将邮件移到收件人的 "垃圾邮件" 文件夹** <p> `MoveToJmf`|**将邮件移到收件人的 "垃圾邮件" 文件夹** <p> `MoveToJmf`|**隔离邮件** <p> `Quarantine`|此设置适用于 [欺骗智能](learn-about-spoof-intelligence.md)中阻止的发件人。|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的反网络钓鱼策略中的高级设置

有关此设置的详细信息，请参阅 [Microsoft Defender For Office 365 中的反网络钓鱼策略中的高级网络钓鱼阈值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。 若要配置此设置，请参阅 [在 Office 365 的 Defender 中配置反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。

****

|安全功能名称|默认|标准版|全|评论|
|---|:---:|:---:|:---:|---|
|**高级网络钓鱼阈值** <p> _PhishThresholdLevel_|**1-标准** <p> `1`|**2-主动** <p> `2`|**3-更主动** <p> `3`||
|

### <a name="safe-links-settings"></a>安全链接设置

Defender for Office 365 中的安全链接包括适用于活动安全链接策略中包含的所有用户的全局设置，以及特定于每个安全链接策略的设置。 有关详细信息，请参阅 [适用于 Office 365 的 Defender 中的安全链接](atp-safe-links.md)。

#### <a name="global-settings-for-safe-links"></a>安全链接的全局设置

若要配置这些设置，请参阅为 [Office 365 中的安全链接配置全局设置](configure-global-settings-for-safe-links.md)。

在 PowerShell 中，可对这些设置使用 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) cmdlet。

****

|安全功能名称|默认|标准版|全|评论|
|---|:---:|:---:|:---:|---|
|**使用中的安全链接： Office 365 应用程序** <p> _EnableSafeLinksForO365Clients_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`|使用受支持的 Office 365 desktop 和 mobile (iOS 和 Android) 应用中的安全链接。 有关详细信息，请参阅 [Office 365 应用程序的安全链接设置](atp-safe-links.md#safe-links-settings-for-office-365-apps)。|
|**用户单击安全链接时不进行跟踪** <p> _TrackClicks_|开 <p> `$false`|关 <p> `$true`|关闭 <p> `$true`|关闭此设置 (将 _TrackClicks_ 设置为 `$true`) 在受支持的 Office 365 应用程序中跟踪用户单击。|
|**不要让用户通过指向原始 URL 的安全链接进行单击** <p> _AllowClickThrough_|打开 <p> `$false`|打开 <p> `$false`|打开 <p> `$false`|打开此设置 (将 _AllowClickThrough_ 设置为 `$false`) 会阻止在受支持的 Office 365 应用程序中单击 "转至原始 URL"。|
|

#### <a name="safe-links-policy-settings"></a>安全链接策略设置

若要配置这些设置，请参阅 [在 Microsoft Defender For Office 365 中设置安全链接策略](set-up-atp-safe-links-policies.md)。

在 PowerShell 中，可对这些设置使用 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) 和 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) cmdlet。

> [!NOTE]
> 如前文所述，没有默认的安全链接策略。 "默认" 列中的值是您创建的新安全链接策略中的默认值。

****

|安全功能名称|默认|标准版|全|评论|
|---|:---:|:---:|:---:|---|
|**选择邮件中未知的潜在恶意 Url 的操作** <p> _IsEnabled_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**为 Microsoft 团队中的未知或可能存在的恶意 Url 选择操作** <p> _EnableSafeLinksForTeams_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**对指向文件的可疑链接和链接应用实时 URL 扫描** <p> _ScanUrls_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**等待 URL 扫描完成后再传递邮件** <p> _DeliverMessageAfterScan_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**将安全链接应用于在组织内发送的电子邮件** <p> _EnableForInternalSenders_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**不跟踪用户点击** <p> _DoNotTrackUserClicks_|关闭 <p> `$false`|关闭 <p> `$false`|关闭 <p> `$false`|关闭此设置 (将 _DoNotTrackUserClicks_ 设置为 `$false`) 跟踪用户单击。|
|**不允许用户单击到原始 URL** <p> _DoNotAllowClickThrough_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`|打开此设置 (将 " _DoNotAllowClickThrough_ " 设置为 `$true` ") " 将阻止单击原始 URL。|
|

### <a name="safe-attachments-settings"></a>安全附件设置

Microsoft Defender for Office 365 中的安全附件包括与安全附件策略无关系的全局设置，以及特定于每个安全链接策略的设置。 有关详细信息，请参阅 [适用于 Office 365 的 Defender 中的安全附件](atp-safe-attachments.md)。

#### <a name="global-settings-for-safe-attachments"></a>安全附件的全局设置

若要配置这些设置，请参阅在[microsoft 365 E5 中](safe-docs.md)[打开 SharePoint、OneDrive 和 Microsoft 团队](turn-on-atp-for-spo-odb-and-teams.md)和安全文档的 ATP。

在 PowerShell 中，可对这些设置使用 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) cmdlet。

****

|安全功能名称|默认|标准版|全|评论|
|---|:---:|:---:|:---:|---|
|**启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP** <p> _EnableATPForSPOTeamsODB_|打开 <p> `$true`|打开 <p> `$true`||
|**打开 Office 客户端的安全文档**<bt/><br/> _EnableSafeDocs_|打开 <p> `$true`|打开 <p> `$true`|此设置仅适用于 Microsoft 365 E5 或 Microsoft 365 E5 安全许可证。 有关详细信息，请参阅 [Microsoft Defender For Office 365 中的安全文档](safe-docs.md)。|
|**允许用户在受保护的视图中单击，即使安全文档识别为恶意文件也是如此**<bt/><br/> _AllowSafeDocsOpen_|关闭 <p> `$false`|关闭 <p> `$false`|此设置与安全文档相关。|
|

#### <a name="safe-attachments-policy-settings"></a>安全附件策略设置

若要配置这些设置，请参阅 [在 Defender For Office 365 中设置安全附件策略](set-up-atp-safe-attachments-policies.md)。

在 PowerShell 中，可对这些设置使用 [SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) 和 [SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) cmdlet。

> [!NOTE]
> 如前文所述，没有默认的安全附件策略。 "默认" 列中的值是您创建的新安全附件策略中的默认值。

****

|安全功能名称|默认|标准版|全|评论|
|---|:---:|:---:|:---:|---|
|**安全附件未知的恶意软件响应** <p> _操作_|阻止 <p> `Block`|阻止 <p> `Block`|阻止 <p> `Block`||
|**在检测时重定向附件** ： **启用重定向** <p> _重定向_ <p> _RedirectAddress_|关闭，且未指定电子邮件地址。 <p> `$true` <p> 无|，并指定电子邮件地址。 <p> `$true` <p> 电子邮件地址|，并指定电子邮件地址。 <p> `$true` <p> 电子邮件地址|将邮件重定向到安全管理员进行审阅。|
|**如果恶意软件扫描附件超时或发生错误，则应用上面的选择。** <p> _ActionOnError_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|

## <a name="related-articles"></a>相关文章

- 您是否正在寻找 **Exchange 邮件流规则的最佳实践 (也称为传输规则**) ？ [有关在 Exchange Online 中配置邮件流规则的最佳实践，](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)请参阅。

- 管理员和用户可以提交误报 (正常的电子邮件，并将其标记为错误) 和漏报 (错误的电子邮件) Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

- 使用以下链接可了解有关如何 **设置** [EOP 服务](set-up-your-eop-service.md)的信息，以及如何 **配置** [Microsoft Defender for Office 365](office-365-atp.md)。 不要忘记 "防御[Office 365 中的威胁](protect-against-threats.md)" 中的有用说明。

- 可以在以下位置找到 **适用于 Windows 的安全基准**：[在哪里可以获取安全基准？](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)对于 GPO/内部部署选项，并 [使用安全基准在 intune 中](https://docs.microsoft.com/intune/protect/security-baselines)为基于 Intune 的安全性配置 Windows 10 设备。 最后，比较 microsoft defender [For endpoint 和 Windows intune 安全基准](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)可在 microsoft Intune for Endpoint 和 microsoft intune 安全基准之间进行比较。
