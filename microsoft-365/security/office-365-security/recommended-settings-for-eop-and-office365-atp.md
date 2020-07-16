---
title: Microsoft for EOP and Office 365 的相关建议和 Office ATP 安全设置、建议、发件人策略框架、基于域的邮件报告和符合性、域密钥识别的邮件、步骤、工作原理、设置 ATP、设置 EOP、配置 ATP、配置 EOP、安全配置
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 12/12/2019
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Exchange Online Protection （EOP）和高级威胁防护（ATP）安全设置的最佳实践是什么？ 有关标准保护的当前建议是什么？ 如果您想要更加严格，应使用什么？ 此外，如果您还使用高级威胁防护（ATP），还可以获得什么额外内容？
ms.openlocfilehash: e6ed4e204ef3cdf66fb065af4621f176bb33cad9
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146238"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>EOP 和 Office 365 ATP 安全性的建议设置

**Exchange Online Protection （EOP）** 是 Microsoft 365 订阅的安全性的核心，可帮助防止恶意电子邮件到达你的员工的收件箱。 但对于每天都会涌现的新的更复杂的攻击，通常需要改进的保护。 **Office 365 高级威胁防护（ATP）** ATP Plan 1 或 ATP 计划2包含额外的功能，可为管理员提供更多的安全、控制和调查层次。

尽管我们为安全管理员提供了自定义安全设置，但我们建议的 EOP 和 Office 365 ATP 中有两个安全级别：**标准**和**严格**。 每个客户的环境和需求各不相同，但我们认为这些级别的邮件筛选配置将有助于防止不需要的邮件在大多数情况下到达员工的收件箱。

> [!IMPORTANT]
> 需要在邮箱上启用垃圾邮件规则，以便筛选正常工作。 默认情况下已启用，但如果筛选似乎不起作用，则应进行检查。 有关详细信息，请参阅[在 Office 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

本主题介绍了这些 Microsoft 推荐的设置，以帮助保护您的用户。

> [!TIP]
> 有一个新的 PowerShell 模块可供下载，称为 "Office 365 高级威胁防护建议配置分析器（ORCA）"，可帮助确定其中一些设置。 在租户中以管理员身份运行时，ORCAReport 将帮助生成反垃圾邮件、反网络钓鱼和其他邮件清洁设置的评估。 您可以在中下载此模块 https://www.powershellgallery.com/packages/ORCA/ 。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP 中的反垃圾邮件、反恶意软件和反网络钓鱼防护

反垃圾邮件、反恶意软件和反网络钓鱼是可由管理员配置的 EOP 功能。 建议采用以下配置。

### <a name="eop-anti-spam-policy-settings"></a>EOP 反垃圾邮件策略设置

若要创建和配置反垃圾邮件策略，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

| 安全功能名称 | Standard | 全 | 评论 |
|---|---|---|---|
|**垃圾邮件**检测操作 <br/><br/> _SpamAction_|**将邮件移动到 "垃圾邮件" 文件夹** <br/><br/> `MoveToJmf`|“隔离邮件”****    发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`||
|**高可信度垃圾邮件**检测操作 <br/><br/> _HighConfidenceSpamAction_|“隔离邮件”****    发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`|“隔离邮件”****    发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`||
|**网络钓鱼电子邮件**检测操作 <br/><br/> _PhishSpamAction_|“隔离邮件”****    发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`|“隔离邮件”****    发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`||
|**高可信度网络钓鱼电子邮件**检测操作 <br/><br/> _HighConfidencePhishAction_|“隔离邮件”****    发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`|“隔离邮件”****    发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`||
|**批量电子邮件**检测操作 <br/><br/> _BulkSpamAction_|**将邮件移动到 "垃圾邮件" 文件夹** <br/><br/> `MoveToJmf`|“隔离邮件”****    发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`||
|批量电子邮件阈值 <br/><br/> _BulkThreshold_|6 |4 |默认值为7，但我们建议您将其更改为6。 有关详细信息，请参阅[Office 365 中的批量投诉级别（BCL）](bulk-complaint-level-values.md)。|
|隔离保留期 <br/><br/> _QuarantineRetentionPeriod_|30 天|30 天||
|**安全提示** <br/><br/> _InlineSafetyTipsEnabled_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|允许的发件人 <br/><br/> _AllowedSenders_|无|无||
|允许的发件人域 <br/><br/> _AllowedSenderDomains_|无|无|不需要将您拥有的域（也称为 "_接受的域_"）添加到允许的发件人列表中。 事实上，它被认为是高风险，因为它会给不良参与者带来机会，以向您发送邮件，否则将被筛选掉。在 "**反垃圾邮件设置**" 页上的安全性 & 合规性中心中使用[欺骗智能](learn-about-spoof-intelligence.md)，以查看在组织的电子邮件域或外部域中的欺骗发件人电子邮件地址中的所有人都是哄骗发件人的电子邮件地址。|
|阻止的发件人 <br/><br/> _BlockedSenders_|无|无||
|阻止的发件人域 <br/><br/> _BlockedSenderDomains_|无|无||
|**启用最终用户垃圾邮件通知**   选中此复选框以启用此策略的最终用户垃圾邮件通知。 <br/><br/> _EnableEndUserSpamNotifications_|已启用 <br/><br/> `$true`|已启用 <br/><br/> `$true`||
|**每隔（天）发送最终用户垃圾邮件通知** <br/><br/> _EndUserSpamNotificationFrequency_|3 天|3 天||
|**垃圾邮件 ZAP** <br/><br/> _SpamZapEnabled_|已启用 <br/><br/> `$true`|已启用 <br/><br/> `$true`||
|**网络钓鱼 ZAP** <br/><br/> _PhishZapEnabled_|已启用 <br/><br/> `$true`|已启用 <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|打开|打开|此设置仅在 PowerShell 中可用。|
|

反垃圾邮件策略中有几个其他高级垃圾邮件筛选器（ASF）设置处于不推荐使用的过程中。 有关这些功能的折旧时间线的详细信息，将在本主题之外进行传递。

我们建议您为**标准**和**严格**级别**关闭这些**ASF 设置。 有关 ASF 设置的详细信息，请参阅[Office 365 中的高级垃圾邮件筛选器（ASF）设置](advanced-spam-filtering-asf-options.md)。

| 安全功能名称 | 评论 |
|---|---|
|**指向远程网站**（_IncreaseScoreWithImageLinks_）的图像链接||
|**URL 中的数字 IP 地址**（_IncreaseScoreWithNumericIps_）||
|**UL 重定向到其他端口**（_IncreaseScoreWithRedirectToOtherPort_）||
|**.Biz 或. info 网站的 URL** （_IncreaseScoreWithBizOrInfoUrls_）||
|**空邮件**（_MarkAsSpamEmptyMessages_）||
|**HTML 中的 JavaScript 或 VBScript** （_MarkAsSpamJavaScriptInHtml_）||
|**HTML 中的 Frame 或 IFrame 标记**（_MarkAsSpamFramesInHtml_）||
|**HTML 中的对象标记**（_MarkAsSpamObjectTagsInHtml_）||
|**HTML 中的嵌入标记**（_MarkAsSpamEmbedTagsInHtml_）||
|**HTML 格式的表单标记**（_MarkAsSpamFormTagsInHtml_）||
|**HTML 中的 Web 错误**（_MarkAsSpamWebBugsInHtml_）||
|**应用敏感单词列表**（_MarkAsSpamSensitiveWordList_）||
|**SPF 记录：硬故障**（_MarkAsSpamSpfRecordHardFail_）||
|**条件发件人 ID 筛选：硬故障**（_MarkAsSpamFromAddressAuthFail_）||
|**NDR 退信**（_MarkAsSpamNdrBackscatter_）||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 出站垃圾邮件策略设置

若要创建和配置出站垃圾邮件策略，请参阅[在 Office 365 中配置出站垃圾邮件筛选](configure-the-outbound-spam-policy.md)。

有关服务中的默认发送限制的详细信息，请参阅[发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

| 安全功能名称 | Standard | 全 | 评论 |
|---|---|---|---|
|**每个用户的最大收件人数：外部每小时限制** <br/><br/> _RecipientLimitExternalPerHour_|500|400||
|**每个用户的最大收件人数：每小时的内部限制** <br/><br/> _RecipientLimitInternalPerHour_|1000|800||
|**每个用户的最大收件人数：每日限制** <br/><br/> _RecipientLimitPerDay_|1000|800||
|**用户超出限制时的操作** <br/><br/> _ActionWhenThresholdReached_|**限制用户发送邮件** <br/><br/> `BlockUser`|**限制用户发送邮件** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP 反恶意软件策略设置

若要创建和配置反恶意软件策略，请参阅[在 Office 365 中配置反恶意软件策略](configure-anti-malware-policies.md)。

| 安全功能名称 | Standard | 全 | 评论 |
|---|---|---|---|
|**是否要在邮件被隔离时通知收件人？** <br/><br/> _Action_|否 <br/><br/> _DeleteMessage_|否 <br/><br/> _DeleteMessage_|如果在电子邮件附件中检测到恶意软件，则会隔离邮件，并且只能由管理员进行发布。|
|**常见附件类型筛选器** <br/><br/> _EnableFileFilter_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`|此设置隔离基于文件类型的包含可执行附件的邮件，而不考虑附件内容。|
|**恶意软件零小时自动清除** <br/><br/> _ZapEnabled_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**通知内部发件人**未送达邮件 <br/><br/> _EnableInternalSenderNotifications_|禁用 <br/><br/> `$false`|禁用 <br/><br/> `$false`||
|**通知外部发件人**未送达的邮件 <br/><br/> _EnableExternalSenderNotifications_|禁用 <br/><br/> `$false`|禁用 <br/><br/> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP 默认的反网络钓鱼策略设置

有关这些设置的详细信息，请参阅[欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。 若要配置这些设置，请参阅[在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。

| 安全功能名称 | Standard | 全 | 评论 |
|---|---|---|---|
|**启用反欺骗保护** <br/><br/> _EnableAntispoofEnforcement_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**启用未经验证的发件人** <br/><br/> _EnableUnauthenticatedSender_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`|将问号（？）添加到 Outlook 中的发件人的照片中，以查找未识别的欺骗性发件人。 有关详细信息，请参阅[反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md)。|
|**如果电子邮件由不允许欺骗您的域的人发送** <br/><br/> _AuthenticationFailAction_|**将邮件移到收件人的 "垃圾邮件" 文件夹** <br/><br/> `MoveToJmf`|**隔离邮件** <br/><br/> `Quarantine`|这适用于[哄骗智能](learn-about-spoof-intelligence.md)中阻止的发件人。|
|

## <a name="office-365-advanced-threat-protection-security"></a>Office 365 高级威胁防护安全

Office 365 高级威胁防护（ATP）订阅带来了更多的安全优势。 有关最新的新闻和信息，可以查看[Office 365 ATP 中的新增功能](whats-new-in-office-365-atp.md)。

Office 365 ATP 包括安全附件和安全链接策略，以防止电子邮件发送潜在的恶意附件，并防止用户单击可能不安全的 Url。

> [!IMPORTANT]
> 高级反网络钓鱼是 Office 365 ATP 订阅的好处之一。 尽管它在默认情况下处于启用状态，但***必须***至少配置一个反网络钓鱼策略，然后它才能开始筛选邮件。 忘记配置反网络钓鱼策略可能会使用户暴露风险的电子邮件。 在添加 Office 365 ATP 订阅后，请务必配置您的反网络钓鱼策略。

如果你已将 Office 365 ATP 订阅添加到你的 EOP，请设置以下配置。

### <a name="office-atp-anti-phishing-policy-settings"></a>Office ATP 反网络钓鱼策略设置

EOP 客户将获得上文所述的基本反网络钓鱼，但 Office 365 ATP 包含更多的功能和控制，可帮助预防、检测和补救攻击。 若要创建和配置这些策略，请参阅[在 Office 365 中配置 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>ATP 反网络钓鱼策略中的模拟设置

有关这些设置的详细信息，请参阅[ATP 反网络钓鱼策略中的模拟设置](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)。 若要配置这些设置，请参阅[配置 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。

| 安全功能名称 | Standard | 全 | 评论 |
|---|---|---|---|
|受保护的用户：**添加要保护的用户** <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|打开 <br/><br/> `$true` <br/><br/> \<list of users\>|打开 <br/><br/> `$true` <br/><br/> \<list of users\>|取决于您的组织，但我们建议在关键角色中添加用户。 在内部，这些可能是 CEO、CFO 和其他高级领导者。 在外部，这些可以包括理事会成员或董事会。|
|受保护的域：**自动包括我拥有的域** <br/><br/> _EnableOrganizationDomainsProtection_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|受保护的域：**包含自定义域** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|打开 <br/><br/> `$true` <br/><br/> \<list of domains\>|打开 <br/><br/> `$true` <br/><br/> \<list of domains\>|取决于您的组织，但我们建议添加经常与您不拥有的域进行交互的域。|
|受保护的用户：**如果模拟用户发送电子邮件** <br/><br/> _TargetedUserProtectionAction_|**隔离邮件** <br/><br/> `Quarantine`|**隔离邮件** <br/><br/> `Quarantine`||
|受保护的域：**如果模拟域发送电子邮件** <br/><br/> _TargetedDomainProtectionAction_|**隔离邮件** <br/><br/> `Quarantine`|**隔离邮件** <br/><br/> `Quarantine`||
|**为模拟用户显示提示** <br/><br/> _EnableSimilarUsersSafetyTips_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**显示模拟域的提示** <br/><br/> _EnableSimilarDomainsSafetyTips_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**显示不正常字符的提示** <br/><br/> _EnableUnusualCharactersSafetyTips_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**是否启用邮箱智能？** <br/><br/> _EnableMailboxIntelligence_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**是否启用基于邮箱智能的模拟保护？** <br/><br/> _EnableMailboxIntelligenceProtection_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**如果由邮箱智能保护的模拟用户发送电子邮件** <br/><br/> _MailboxIntelligenceProtectionAction_|**将邮件移到收件人的 "垃圾邮件" 文件夹** <br/><br/> `MoveToJmf`|**隔离邮件** <br/><br/> `Quarantine`||
|**受信任的发件人** <br/><br/> _ExcludedSenders_|无|无|取决于您的组织，但我们建议添加由于仅模拟而不是其他筛选器而将错误标记为网络钓鱼的用户。|
|**受信任域** <br/><br/> _ExcludedDomains_|无|无|取决于您的组织，但我们建议添加一些域，这些域因仅模拟而不是其他筛选器而被错误地标记为网络钓鱼。|
|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>ATP 反网络钓鱼策略中的欺骗设置

请注意，这些设置与[EOP 中的反垃圾邮件策略设置](#eop-anti-spam-policy-settings)中提供的设置相同。

| 安全功能名称 | Standard | 全 | 评论 |
|---|---|---|---|
|**启用反欺骗保护** <br/><br/> _EnableAntispoofEnforcement_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**启用未经验证的发件人** <br/><br/> _EnableUnauthenticatedSender_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`|将问号（？）添加到 Outlook 中的发件人的照片中，以查找未识别的欺骗性发件人。 有关详细信息，请参阅[反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md)。|
|**如果电子邮件由不允许欺骗您的域的人发送** <br/><br/> _AuthenticationFailAction_|**将邮件移到收件人的 "垃圾邮件" 文件夹** <br/><br/> `MoveToJmf`|**隔离邮件** <br/><br/> `Quarantine`|这适用于[哄骗智能](learn-about-spoof-intelligence.md)中阻止的发件人。|
|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>ATP 反网络钓鱼策略中的高级设置

有关此设置的详细信息，请参阅[ATP 反网络钓鱼策略中的高级网络钓鱼阈值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)。 若要配置此设置，请参阅[配置 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。

| 安全功能名称 | Standard | 全 | 评论 |
|---|---|---|---|
|**高级网络钓鱼阈值** <br/><br/> _PhishThresholdLevel_|**2-主动** <br/><br/> `2`|**3-更主动** <br/><br/> `3`||

### <a name="atp-safe-links-policy-settings"></a>ATP 安全链接策略设置

若要配置这些设置，请参阅[设置 Office 365 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。

#### <a name="safe-links-policy-settings-in-the-default-policy-for-all-users"></a>所有用户的默认策略中的安全链接策略设置

**注意**：在 PowerShell 中，可对这些设置使用[AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) cmdlet。

| 安全功能名称 | Standard | 全 | 评论 |
|---|---|---|---|
|**使用中的安全链接： Office 365 应用程序** <br/><br/> _EnableSafeLinksForO365Clients_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`|在 Office 365 应用中使用 ATP 安全链接，Office for iOS 和 Android。|
|**用户单击安全链接时不进行跟踪** <br/><br/> _TrackClicks_|关闭 <br/><br/> `$true`|关闭 <br/><br/> `$true`||
|**不要让用户通过指向原始 URL 的安全链接进行单击** <br/><br/> _AllowClickThrough_|打开 <br/><br/> `$false`|打开 <br/><br/> `$false`||
|

#### <a name="safe-links-policy-settings-in-custom-policies-for-specific-users"></a>针对特定用户的自定义策略中的安全链接策略设置

**注意**：在 PowerShell 中，使用[SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)和 [Set-SafeLinksPolicy] （ https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicycmdlet 这些设置的 cmdlet。

| 安全功能名称 | Standard | 全 | 评论 |
|---|---|---|---|
|**选择邮件中未知的潜在恶意 Url 的操作** <br/><br/> _IsEnabled_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**为 Microsoft 团队中的未知或可能存在的恶意 Url 选择操作** <br/><br/> _EnableSafeLinksForTeams_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**对指向文件的可疑链接和链接应用实时 URL 扫描** <br/><br/> _ScanUrls_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**等待 URL 扫描完成后再传递邮件** <br/><br/> _DeliverMessageAfterScan_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**将安全链接应用于在组织内发送的电子邮件** <br/><br/> _EnableForInternalSenders_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**用户单击安全链接时不进行跟踪** <br/><br/> _DoNotTrackUserClicks_|关闭 <br/><br/> `$false`|关闭 <br/><br/> `$false`|
|**不要让用户通过指向原始 URL 的安全链接进行单击** <br/><br/> _DoNotAllowClickThrough_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|

### <a name="atp-safe-attachments-policy-settings"></a>ATP 安全附件策略设置

若要配置这些设置，请参阅[设置 Office 365 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)。

#### <a name="safe-attachments-policy-settings-in-the-default-policy-for-all-users"></a>所有用户的默认策略中的安全附件策略设置

**注意**：在 PowerShell 中，可对这些设置使用[AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) cmdlet。

| 安全功能名称 | Standard | 全 | 评论 |
|---|---|---|---|
|**启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP** <br/><br/> _EnableATPForSPOTeamsODB_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|**打开 Office 客户端的安全文档**<bt/><br/> _EnableSafeDocs_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||此设置仅适用于 Microsoft 365 E5 或 Microsoft 365 E5 安全许可证。 有关详细信息，请参阅[Office 365 高级威胁防护中的安全文档](safe-docs.md)。|
|**允许用户在受保护的视图中单击，即使安全文档识别为恶意文件也是如此**<bt/><br/> _AllowSafeDocsOpen_|关闭 <br/><br/> `$false`|关闭 <br/><br/> `$false`||
|

#### <a name="safe-attachments-policy-settings-in-custom-policies-for-specific-users"></a>针对特定用户的自定义策略中的安全附件策略设置

**注意**：在 PowerShell 中，对这些设置使用[SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)和[SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) cmdlet。

| 安全功能名称 | Standard | 全 | 评论 |
|---|---|---|---|
|**安全附件未知的恶意软件响应** <br/><br/> _Action_|阻止 <br/><br/> `Block`|阻止 <br/><br/> `Block`||
|**在检测时重定向附件**：**启用重定向** <br/><br/> _重定向_ <br/><br/> _RedirectAddress_|，并指定电子邮件地址。 <br/><br/> `$true` <br/><br/> 电子邮件地址|，并指定电子邮件地址。 <br/><br/> `$true` <br/><br/> 电子邮件地址|将邮件重定向到安全管理员进行审阅。|
|**如果恶意软件扫描附件超时或发生错误，则应用上面的选择。** <br/><br/> _ActionOnError_|打开 <br/><br/> `$true`|打开 <br/><br/> `$true`||
|

## <a name="related-topics"></a>相关主题

- 您是否正在寻找与**Exchange 邮件流/Exchange 传输规则**有关的最佳实践？ 有关详细信息，请参阅[本文](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop)。

- 管理员和用户可以将误报（好的电子邮件标记为坏）和漏报（允许的错误电子邮件）提交给 Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

- 使用这些链接可获取有关如何**设置** [EOP 服务](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)的信息，以及**配置** [Office 365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)。 （请不要忘记在 "防御[Office 365 中的威胁](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)" 中了解有用的说明。）

- 可在[此处](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)获取适用于 GPO/本地选项的**Windows 安全基准**，并在[此处](https://docs.microsoft.com/intune/protect/security-baselines)查找基于 Intune 的安全性。 最后，可以在[此处](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)找到 Microsoft Defender 高级威胁防护（ATP）和 Windows Intune 安全基准之间的比较。
