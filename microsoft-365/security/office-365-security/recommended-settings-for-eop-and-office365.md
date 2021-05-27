---
title: 针对 EOP 和 Defender for Office 365安全设置的 Microsoft 建议
keywords: Office 365 安全建议， 发件人策略框架， 基于域的邮件报告和一致性， 域密钥标识的邮件， 步骤， 如何工作， 安全基线， EOP 基线， 适用于 Office 365 的 Defender 的基线， 为 Office 365 设置 Defender， 设置 EOP， 为 Office 365 配置 Defender， 配置 EOP， 安全配置
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
description: 什么是适用于 EOP Exchange Online Protection (和 Defender) 安全设置Office 365最佳实践？ 标准保护的当前建议是什么？ 如果要更加严格，应该使用什么？ 如果你还使用 Defender for Office 365？
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 10fac8cb7241faa652bbcb4726610abef741e70c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683267"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>用于配置 EOP 和 Defender for Office 365 安全性的建议设置

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** 是 Microsoft 365 订阅的核心安全，有助于阻止恶意电子邮件到达员工的收件箱。 但是，随着每天出现更复杂的新攻击，通常需要改进的保护。 **Microsoft Defender for Office 365** 计划 1 或计划 2 包含其他功能，为管理员提供了多层安全、控制和调查。

尽管我们使安全管理员能够自定义其安全设置，但 EOP 和 Microsoft Defender for Office 365建议采用两种安全级别：**标准** 级别和 **严格级别**。 每个客户的环境和需求各不相同，但我们认为，这些筛选级别将有助于防止不需要的邮件在大多数情况下到达员工的收件箱。

若要自动将"标准"或"严格"设置应用于用户，请参阅 Preset [security policies in EOP and Microsoft Defender for Office 365。](preset-security-policies.md)

> [!NOTE]
> 需要在邮箱上启用垃圾邮件规则，以便筛选正常工作。 默认情况下会启用此功能，但如果筛选似乎未正常工作，应检查它。 有关详细信息，请参阅[在 Office 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

本文介绍了默认设置以及建议的标准和严格设置，以帮助保护用户。

> [!TIP]
> PowerShell Office 365高级威胁防护建议配置分析器 (ORCA) 模块可帮助你 (管理员) 查找这些设置的当前值。 具体来说 **，Get-ORCAReport** cmdlet 可生成对反垃圾邮件、防钓鱼和其他邮件安全设置的评估。 可以在 下载 ORCA 模块 <https://www.powershellgallery.com/packages/ORCA/> 。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP 中的反垃圾邮件、反恶意软件和防钓鱼保护

反垃圾邮件、反恶意软件和防钓鱼是 EOP 功能，管理员可配置这些功能。 建议采用以下标准或严格配置。

### <a name="eop-anti-spam-policy-settings"></a>EOP 反垃圾邮件策略设置

若要创建和配置反垃圾邮件策略，请参阅在 Office 365[中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

<br>

****

|安全功能名称|默认值|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**垃圾邮件** 检测操作 <p> _SpamAction_|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**高可信度垃圾邮件** 检测操作 <p> _HighConfidenceSpamAction_|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**网络钓鱼电子邮件** 检测操作 <p> _PhishSpamAction_|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**高可信度钓鱼电子邮件** 检测操作 <p> _HighConfidencePhishAction_|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**批量电子邮件** 检测操作 <p> _BulkSpamAction_|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|批量电子邮件阈值 <p> _BulkThreshold_|7 |6 |4 |有关详细信息，请参阅批量[投诉级别 (BCL) 中的Office 365。](bulk-complaint-level-values.md)|
|隔离保留期 <p> _QuarantineRetentionPeriod_|15 天|30 天|30 天||
|**安全使用技巧** <p> _InlineSafetyTipsEnabled_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|允许的发件人 <p> _AllowedSenders_|无|无|无||
|允许的发件人域 <p> _AllowedSenderDomains_|无|无|无|将域添加到允许的发件人列表不是一个好主意。 攻击者可以向您发送其他将被筛选掉的电子邮件。 <p> 使用安全[](learn-about-spoof-intelligence.md)& 合规中心中的欺骗智能见解和租户允许[/](tenant-allow-block-list.md)阻止列表查看在组织的电子邮件域中欺骗发件人电子邮件地址或外部域中欺骗发件人电子邮件地址的所有发件人。|
|阻止的发件人 <p> _BlockedSenders_|无|无|无||
|阻止的发件人域 <p> _BlockedSenderDomains_|无|无|无||
|**启用最终用户垃圾邮件通知**   选中此复选框以启用此策略的最终用户垃圾邮件通知。 <p> _EnableEndUserSpamNotifications_|已禁用 <p> `$false`|已启用 <p> `$true`|已启用 <p> `$true`||
|**每两天发送一次最终用户 (垃圾邮件)** <p> _EndUserSpamNotificationFrequency_|3 天|3 天|3 天||
|**垃圾邮件 ZAP** <p> _SpamZapEnabled_|已启用 <p> `$true`|已启用 <p> `$true`|已启用 <p> `$true`||
|**钓鱼邮件 ZAP** <p> _PhishZapEnabled_|已启用 <p> `$true`|已启用 <p> `$true`|已启用 <p> `$true`||
|_MarkAsSpamBulkMail_|打开|打开|打开|此设置仅在 PowerShell 中可用。|
|

反垃圾邮件策略中还有一 (高级垃圾邮件筛选器) ASF 筛选器设置，这些设置正在被弃用。 有关这些功能的折旧时间线详细信息将在本文之外进行介绍。

对于"标准"和"严格"级别，我们建议你关闭这些 ASF **设置。** 有关 ASF 设置详细信息，请参阅邮件中的高级垃圾邮件筛选器[ (ASF) 设置Office 365。](advanced-spam-filtering-asf-options.md)

<br>

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

若要创建和配置出站垃圾邮件策略，请参阅配置出[站垃圾邮件筛选Office 365。](configure-the-outbound-spam-policy.md)

有关服务中的默认发送限制详细信息，请参阅发送 [限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

<br>

****

|安全功能名称|默认值|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**每个用户的最大收件人数：外部每小时限制** <p> _RecipientLimitExternalPerHour_|0|500|400|默认值 0 表示使用服务默认值。|
|**每个用户的最大收件人数：内部每小时限制** <p> _RecipientLimitInternalPerHour_|0|1000|800|默认值 0 表示使用服务默认值。|
|**每个用户的最大收件人数：每日限制** <p> _RecipientLimitPerDay_|0|1000|800|默认值 0 表示使用服务默认值。|
|**用户超出限制时的操作** <p> _ActionWhenThresholdReached_|**限制用户于第二天之前发送邮件** <p> `BlockUserForToday`|**限制用户发送邮件** <p> `BlockUser`|**限制用户发送邮件** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP 反恶意软件策略设置

若要创建和配置反恶意软件策略，请参阅在 Office 365[中配置反恶意软件策略](configure-anti-malware-policies.md)。

<br>

****

|安全功能名称|默认值|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**当邮件被隔离为恶意软件时通知收件人** <p> _Action_|否 <p> _DeleteMessage_|否 <p> _DeleteMessage_|否 <p> _DeleteMessage_|如果在电子邮件附件中检测到恶意软件，邮件将被隔离，并且只有管理员才能释放。|
|**启用常见附件筛选器** <p> _EnableFileFilter_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`|此设置根据文件类型隔离包含可执行附件的邮件，而不考虑附件内容。|
|**启用恶意软件的零时差自动清除** <p> _ZapEnabled_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|**将邮件隔离为恶意软件时通知内部发件人** <p> _EnableInternalSenderNotifications_|已禁用 <p> `$false`|已禁用 <p> `$false`|已禁用 <p> `$false`||
|**当邮件被隔离为恶意软件时通知外部发件人** <p> _EnableExternalSenderNotifications_|已禁用 <p> `$false`|已禁用 <p> `$false`|已禁用 <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP 默认防钓鱼策略设置

有关这些设置详细信息，请参阅欺骗 [设置](set-up-anti-phishing-policies.md#spoof-settings)。 若要配置这些设置，请参阅在 EOP 中配置防 [钓鱼策略](configure-anti-phishing-policies-eop.md)。

<br>

****

|安全功能名称|默认值|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**启用反欺骗保护** <p> _EnableSpoofIntelligence_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|**启用未经身份验证的发件人** <p> _EnableUnauthenticatedSender_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`|向发件人 () 发件人的照片添加一Outlook问号。 有关详细信息，请参阅[反钓鱼策略中的“欺骗”设置](set-up-anti-phishing-policies.md)。|
|**如果电子邮件是由不允许欺骗你的域的人发送的** <p> _AuthenticationFailAction_|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**隔离邮件** <p> `Quarantine`|此设置适用于欺骗性发件人，这些发件人被自动阻止，如欺骗智能见解中所示，[](learn-about-spoof-intelligence.md)或在租户允许/阻止列表中手动[阻止](tenant-allow-block-list.md)。|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender for Office 365 安全

Microsoft Defender for Office 365订阅提供了其他安全优势。 有关最新新闻和信息，请参阅 Defender for Office 365 中的[新增Office 365。](whats-new-in-defender-for-office-365.md)

> [!IMPORTANT]
>
> - Microsoft Defender for Office 365[中默认的](set-up-anti-phishing-policies.md#spoof-settings)防钓鱼策略可为所有收件人提供欺骗保护和邮箱智能。 但是，其他 [可用的模拟保护](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 功能和 [高级](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 设置未在默认策略中配置或启用。 若要启用所有保护功能，请修改默认的防钓鱼策略或创建其他防钓鱼策略。
>
> - 没有可自动保险箱组织中所有收件人的默认保险箱链接策略或附件策略。 若要获取保护，需要创建至少一个"链接策略保险箱和"保险箱附件"策略。
>
> - [保险箱、SharePoint、OneDrive](mdo-for-spo-odb-and-teams.md)和 Microsoft Teams 文档保险箱的附件不依赖于 保险箱 链接策略。 [](safe-docs.md)

如果你的订阅包括 Microsoft Defender for Office 365或者你已购买 Defender for Office 365作为加载项，请设置以下标准或严格配置。

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略Office 365

如前文所述，EOP 客户会获得基本的防钓鱼功能，但 microsoft Defender for Office 365 包括更多功能和控制，以帮助防止、检测和修正攻击。 若要创建和配置这些策略，请参阅在 Defender for [Office 365 中配置防钓鱼Office 365。](configure-atp-anti-phishing-policies.md)

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略中的模拟Office 365

有关这些设置详细信息，请参阅 Microsoft Defender for Office 365 中的防钓鱼[策略中的模拟Office 365。](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 若要配置这些设置，请参阅在 Defender for [Office 365 中配置防钓鱼Office 365。](configure-atp-anti-phishing-policies.md)

<br>

****

|安全功能名称|默认值|标准|Strict|评论|
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

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略中的欺骗Office 365

请注意，这些设置与 EOP 中的反垃圾邮件 [策略设置中的设置相同](#eop-anti-spam-policy-settings)。

<br>

****

|安全功能名称|默认值|标准|Strict|评论|
|---|---|---|---|---|
|**启用反欺骗保护** <p> _EnableSpoofIntelligence_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|**启用未经身份验证的发件人** <p> _EnableUnauthenticatedSender_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`|向发件人 () 发件人的照片添加一Outlook问号。 有关详细信息，请参阅[反钓鱼策略中的“欺骗”设置](set-up-anti-phishing-policies.md)。|
|**如果电子邮件是由不允许欺骗你的域的人发送的** <p> _AuthenticationFailAction_|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**隔离邮件** <p> `Quarantine`|此设置适用于欺骗性发件人，这些发件人被自动阻止，如欺骗智能见解中所示，[](learn-about-spoof-intelligence.md)或在租户允许/阻止列表中手动[阻止](tenant-allow-block-list.md)。|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的反网络钓鱼策略中的高级Office 365

有关此设置详细信息，请参阅 Microsoft Defender for Office 365 中的反网络钓鱼策略[中的高级网络钓鱼Office 365。](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 若要配置此设置，请参阅在 Defender for [Office 365 中配置防钓鱼Office 365。](configure-atp-anti-phishing-policies.md)

<br>

****

|安全功能名称|默认值|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**高级网络钓鱼阈值** <p> _PhishThresholdLevel_|**1 - 标准** <p> `1`|**2 - 主动** <p> `2`|**3 - 更主动** <p> `3`||
|

### <a name="safe-links-settings"></a>保险箱链接设置

保险箱Defender for Office 365 中的链接包括适用于活动 保险箱 链接策略中包含的所有用户的全局设置，以及特定于每个 保险箱 链接策略的设置。 有关详细信息，请参阅 defender for[保险箱 中的链接Office 365。](safe-links.md)

#### <a name="global-settings-for-safe-links"></a>链接的全局保险箱设置

若要配置这些设置，请参阅在 Defender [for 保险箱 中配置链接的全局Office 365。](configure-global-settings-for-safe-links.md)

在 PowerShell 中，对这些设置使用 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) cmdlet。

<br>

****

|安全功能名称|默认值|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**在保险箱应用程序中使用Office 365链接** <p> _EnableSafeLinksForO365Clients_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`|使用保险箱 iOS 和 Android Office 365 应用支持 (移动) 链接。 有关详细信息，请参阅保险箱[应用的链接Office 365设置](safe-links.md#safe-links-settings-for-office-365-apps)。|
|**不跟踪用户何时单击"保险箱链接"** <p> _TrackClicks_|开 <p> `$false`|关 <p> `$true`|关闭 <p> `$true`|关闭此设置 (_将 TrackClicks_ 设置为) 在受支持的应用中跟踪Office 365 `$true` 单击。|
|**不允许用户单击"指向保险箱 URL 的链接"** <p> _AllowClickThrough_|打开 <p> `$false`|打开 <p> `$false`|打开 <p> `$false`|打开此设置 (将 _AllowClickThrough_ 设置为) 阻止在受支持的应用中单击到 `$false` Office 365 URL。|
|

#### <a name="safe-links-policy-settings"></a>保险箱链接策略设置

若要配置这些设置，请参阅在[Microsoft Defender 保险箱设置链接策略Office 365。](set-up-safe-links-policies.md)

在 PowerShell 中，将 [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) 和 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) cmdlet 用于这些设置。

> [!NOTE]
> 如前面所述，链接策略保险箱默认策略。 "默认"列中的值是新建链接策略保险箱中的默认值。

<br>

****

|安全功能名称|默认值|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**选择邮件中未知潜在恶意 URL 的操作** <p> _IsEnabled_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**选择针对网站内未知或潜在恶意 URL Microsoft Teams** <p> _EnableSafeLinksForTeams_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**对指向文件的可疑链接应用实时 URL 扫描** <p> _ScanUrls_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**等待 URL 扫描完成，然后再传递邮件** <p> _DeliverMessageAfterScan_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**Apply 保险箱 Links to email messages sent within the organization** <p> _EnableForInternalSenders_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**不跟踪用户单击** <p> _DoNotTrackUserClicks_|关闭 <p> `$false`|关闭 <p> `$false`|关闭 <p> `$false`|关闭此设置后 (_DoNotTrackUserClicks_ 设置为) `$false` 用户单击。|
|**不允许用户单击至初始 URL** <p> _DoNotAllowClickThrough_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`|打开此设置 (_DoNotAllowClickThrough_ 设置为) `$true` 阻止单击访问原始 URL。|
|

### <a name="safe-attachments-settings"></a>保险箱附件设置

保险箱Microsoft Defender for Office 365 中的附件包括与"附件"策略保险箱没有任何关系的全局设置，以及特定于每个"保险箱策略"的设置。 有关详细信息，请参阅 defender 中的保险箱[附件Office 365。](safe-attachments.md)

#### <a name="global-settings-for-safe-attachments"></a>附件的全局保险箱设置

若要配置这些设置，请参阅在[](turn-on-mdo-for-spo-odb-and-teams.md)保险箱 中打开 SharePoint、OneDrive 和 Microsoft Teams 保险箱[文档](safe-docs.md)Microsoft 365 E5。

在 PowerShell 中，对这些设置使用 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) cmdlet。

<br>

****

|安全功能名称|默认值|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Defender for Office 365** <p> _EnableATPForSPOTeamsODB_|打开 <p> `$true`|打开 <p> `$true`||
|**打开 保险箱 客户端Office文档** <p> _EnableSafeDocs_|打开 <p> `$true`|打开 <p> `$true`|此设置仅适用于许可证Microsoft 365 E5 Microsoft 365 E5 安全性许可证。 有关详细信息，请参阅 microsoft [Defender 保险箱中的文档Office 365。](safe-docs.md)|
|**允许用户单击"受保护的视图"，即使保险箱文件被标识为恶意文件** <p> _AllowSafeDocsOpen_|关闭 <p> `$false`|关闭 <p> `$false`|此设置与文档保险箱相关。|
|

#### <a name="safe-attachments-policy-settings"></a>保险箱附件策略设置

若要配置这些设置，请参阅在 Defender [for 保险箱 中设置附件Office 365。](set-up-safe-attachments-policies.md)

在 PowerShell 中，将 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) 和 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) cmdlet 用于这些设置。

> [!NOTE]
> 如前面所述，附件策略保险箱默认策略。 "默认"列中的值是新建的"附件保险箱中的默认值。

<br>

****

|安全功能名称|默认值|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**保险箱附件未知恶意软件响应** <p> _Action_|阻止 <p> `Block`|阻止 <p> `Block`|阻止 <p> `Block`||
|**检测时重定向附件** ： **启用重定向** <p> _重定向_ <p> _RedirectAddress_|关闭，未指定电子邮件地址。 <p> `$true` <p> 无|打开，并指定电子邮件地址。 <p> `$true` <p> 电子邮件地址|打开，并指定电子邮件地址。 <p> `$true` <p> 电子邮件地址|将邮件重定向到安全管理员进行审阅。|
|**如果恶意软件扫描附件出现时间过或出现错误，则应用上述选择。** <p> _ActionOnError_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`||
|

## <a name="related-articles"></a>相关文章

- 您是否正在查找有关邮件流规则 **Exchange也称为** (传输规则) ？ 请参阅[Best practices for configuring mail flow rules in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)。

- 管理员和用户可以提交误报 (标记为错误) 误报 (错误电子邮件) Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

- 使用这些链接获取有关如何设置[EOP](/exchange/standalone-eop/set-up-your-eop-service)服务的信息，并配置[Microsoft Defender Office 365。](defender-for-office-365.md)  不要忘记'抵御威胁中的有用[Office 365'。](protect-against-threats.md)

- 有关 Windows 的安全基线，可以在此处找到：在哪里可以获取 GPO/本地选项的安全基线[？](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)以及使用安全基线在 Intune 中配置 Windows 10 设备，以获得基于[Intune](/intune/protect/security-baselines)的安全性。 最后，比较适用于终结点的 Microsoft Defender Microsoft Intune安全基线之间的比较可在比较 Microsoft Defender for Endpoint 和 Windows [Intune 安全基线中获得](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)。
