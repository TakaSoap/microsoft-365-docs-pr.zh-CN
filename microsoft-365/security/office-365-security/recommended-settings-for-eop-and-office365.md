---
title: 针对 EOP 和 Defender for Office 365安全设置的 Microsoft 建议
keywords: Office 365 安全建议， 发件人策略框架， 基于域的邮件报告和一致性， 域密钥标识的邮件， 步骤， 如何工作， 安全基线， EOP 的基线， 适用于 Office 365 的 Defender 的基线， 为 Office 365 设置 Defender， 设置 EOP， 为 Office 365 配置 Defender， 配置 EOP， 安全配置
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
ms.openlocfilehash: 23013a2bab538763fd69eb787d7a84904517859b
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58258212"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>用于配置 EOP 和 Defender for Office 365 安全性的建议设置

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** 是 Microsoft 365 订阅的核心安全，有助于阻止恶意电子邮件到达员工的收件箱。 但是，随着每天出现更复杂的新攻击，通常需要改进的保护。 **Microsoft Defender for Office 365** 计划 1 或计划 2 包含其他功能，为管理员提供了多层安全、控制和调查。

尽管我们支持安全管理员自定义其安全设置，但 EOP 和 Microsoft Defender for Office 365建议采用两种安全级别：**标准** 级别和 **严格级别**。 每个客户的环境和需求各不相同，但我们认为，这些筛选级别将有助于防止不需要的邮件在大多数情况下到达员工的收件箱。

若要自动将标准或严格设置应用于用户，请参阅预设[EOP](preset-security-policies.md)中的安全策略和 Microsoft Defender for Office 365 。

> [!NOTE]
> 需要在邮箱上启用垃圾邮件规则，以便筛选正常工作。 默认情况下会启用此功能，但如果筛选似乎未正常工作，应检查它。 有关详细信息，请参阅[配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

本文介绍了默认设置以及建议的标准和严格设置，以帮助保护用户。 这些表包含 Microsoft 365 Defender 门户和 PowerShell (Exchange Online PowerShell 中的设置，或适用于没有 Exchange Online Protection 邮箱的组织的独立 Exchange Online PowerShell) 。

> [!TIP]
> PowerShell Office 365高级威胁防护建议配置分析器 (ORCA) 模块可帮助你 (管理员) 查找这些设置的当前值。 具体来说 **，Get-ORCAReport** cmdlet 可生成对反垃圾邮件、防钓鱼和其他邮件安全设置的评估。 可以在 下载 ORCA 模块 <https://www.powershellgallery.com/packages/ORCA/> 。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP 中的反垃圾邮件、反恶意软件和防钓鱼保护

反垃圾邮件、反恶意软件和防钓鱼是 EOP 功能，管理员可配置这些功能。 建议采用以下标准或严格配置。

### <a name="eop-anti-spam-policy-settings"></a>EOP 反垃圾邮件策略设置

若要创建和配置反垃圾邮件策略，请参阅在 EOP 中配置 [反垃圾邮件策略](configure-your-spam-filter-policies.md)。

<br>

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**批量电子邮件阈值&垃圾邮件属性**||||
|**批量电子邮件阈值** <p> _BulkThreshold_|7 |6 |4 |有关详细信息，请参阅 [批量投诉级别 (BCL) EOP](bulk-complaint-level-values.md)中。|
|_MarkAsSpamBulkMail_|`On`|`On`|`On`|此设置仅在 PowerShell 中可用。|
|**增加垃圾邮件得分** 设置|关闭|关闭|关闭|所有这些设置都是 ASF 高级垃圾邮件筛选器 (部分) 。 有关详细信息，请参阅本文中的反垃圾邮件策略中的 [ASF](#asf-settings-in-anti-spam-policies) 设置部分。|
|**标记为垃圾邮件** 设置|关闭|关闭|关闭|这些设置中的大多数都是 ASF 的一部分。 有关详细信息，请参阅本文中的反垃圾邮件策略中的 [ASF](#asf-settings-in-anti-spam-policies) 设置部分。|
|**包含特定语言** <p> _EnableLanguageBlockList_ <p> _LanguageBlockList_|**关闭** <p> `$false` <p> 空白|**关闭** <p> `$false` <p> 空白|**关闭** <p> `$false` <p> 空白|我们对此设置没有具体的建议。 您可以基于业务需求阻止特定语言的邮件。|
|**来自以下国家/地区** <p> _EnableRegionBlockList_ <p> _RegionBlockList_|**关闭** <p> `$false` <p> 空白|**关闭** <p> `$false` <p> 空白|**关闭** <p> `$false` <p> 空白|我们对此设置没有具体的建议。 您可以根据业务需求阻止来自特定国家/地区的邮件。|
| _TestModeAction_ (测试) |**无**|**无**|**无**|此设置是 ASF 的一部分。 有关详细信息，请参阅本文中的反垃圾邮件策略中的 [ASF](#asf-settings-in-anti-spam-policies) 设置部分。|
|**Actions**|||||
|**垃圾邮件** 检测操作 <p> _SpamAction_|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**高可信度垃圾邮件** 检测操作 <p> _HighConfidenceSpamAction_|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**网络钓鱼检测** 操作 <p> _PhishSpamAction_|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**高可信度网络钓鱼** 检测操作 <p> _HighConfidencePhishAction_|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**批量** 检测操作 <p> _BulkSpamAction_|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|**将邮件移动到"垃圾邮件"文件夹** <p> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <p> `Quarantine`||
|**将垃圾邮件在隔离中保留此天数** <p> _QuarantineRetentionPeriod_|15 天|30 天|30 天||
|**启用垃圾邮件安全提示** <p> _InlineSafetyTipsEnabled_|已选中 <p> `$true`|已选中 <p> `$true`|已选中 <p> `$true`||
|为网络钓鱼邮件启用零时 (ZAP) 清除 <p> _PhishZapEnabled_|已选中 <p> `$true`|已选中 <p> `$true`|已选中 <p> `$true`||
|为垃圾邮件启用 ZAP <p> _SpamZapEnabled_|已选中 <p> `$true`|已选中 <p> `$true`|已选中 <p> `$true`||
|**启用最终用户垃圾邮件通知**   选中此复选框以启用此策略的最终用户垃圾邮件通知。 <p> _EnableEndUserSpamNotifications_|未选定 <p> `$false`|已选中 <p> `$true`|已选中 <p> `$true`||
|**每两天发送一次最终用户 (垃圾邮件)** <p> _EndUserSpamNotificationFrequency_|3 天|3 天|3 天||
|**允许&阻止列表**|||||
|允许的发件人 <p> _AllowedSenders_|无|无|无||
|允许的发件人域 <p> _AllowedSenderDomains_|无|无|无|将域添加到允许的发件人列表不是一个好主意。 攻击者可以向您发送其他将被筛选掉的电子邮件。 <p> 使用 [欺骗智能见解](learn-about-spoof-intelligence.md) 和租户 [允许/](tenant-allow-block-list.md) 阻止列表查看在组织的电子邮件域中欺骗发件人电子邮件地址或外部域中欺骗发件人电子邮件地址的所有发件人。|
|阻止发件人 <p> _BlockedSenders_|无|无|无||
|阻止的发件人域 <p> _BlockedSenderDomains_|无|无|无||
|

#### <a name="asf-settings-in-anti-spam-policies"></a>反垃圾邮件策略中的 ASF 设置

反垃圾邮件策略中 (ASF) 很多高级垃圾邮件筛选器设置，这些设置正在被弃用。 有关这些功能的折旧时间线详细信息将在本文之外进行介绍。

对于"标准"和"严格"级别，我们建议您将以下ASF 设置 **保持关闭** 状态。 有关 ASF 设置详细信息，请参阅 EOP 中的高级垃圾邮件筛选器 [ (ASF) 设置](advanced-spam-filtering-asf-options.md)。

<br>

****

|安全功能名称|评论|
|---|---|
|**指向远程站点的图像链接 (** _IncreaseScoreWithImageLinks)_||
|**URL 中的数字 IP** 地址 (_IncreaseScoreWithNumericIps)_||
|**指向** _IncreaseScoreWithRedirectToOtherPort_ (的其他端口的 URL) ||
|指向 _IncreaseScoreWithBizOrInfoUrls_ (**.biz** 或 .info 网站) ||
| _MarkAsSpamEmptyMessages_ (中的空) ||
|**在 HTML 应用程序中嵌入标记** (_MarkAsSpamEmbedTagsInHtml_) ||
|**Html 格式的 JavaScript 或 VBScript** (_MarkAsSpamJavaScriptInHtml_) ||
|**HTML 格式的表单标记 (** _MarkAsSpamFormTagsInHtml_) ||
|_MarkAsSpamFramesInHtml_ (HTML 格式的框架或 **iframe**) ||
| _MarkAsSpamWebBugsInHtml_ (HTML 中的 Web) ||
|**HTML 格式的对象标记 (** _MarkAsSpamObjectTagsInHtml_) ||
| _MarkAsSpamSensitiveWordList_ (敏感) ||
|**SPF 记录**：MarkAsSpamSpfRecordHardFail (硬 _失败)_||
|**发件人 ID 筛选硬失败 (** _MarkAsSpamFromAddressAuthFail_) ||
|**退 (** _MarkAsSpamNdrBackscatter)_||
| _TestModeAction_ (测试) |对于支持"测试为操作"的 ASF 设置，可以将测试模式操作配置为"无"、添加默认 **X** 标头文本或"发送 `None` (、或 `AddXHeader` `BccMessage`) " 。 有关详细信息，请参阅启用 [、禁用或测试 ASF 设置](advanced-spam-filtering-asf-options.md#enable-disable-or-test-asf-settings)。|
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 出站垃圾邮件策略设置

若要创建和配置出站垃圾邮件策略，请参阅在 EOP 中配置出 [站垃圾邮件筛选](configure-the-outbound-spam-policy.md)。

有关服务中的默认发送限制详细信息，请参阅 [发送限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

<br>

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**设置外部邮件限制** <p> _RecipientLimitExternalPerHour_|0|500|400|默认值 0 表示使用服务默认值。|
|**设置内部邮件限制** <p> _RecipientLimitInternalPerHour_|0|1000|800|默认值 0 表示使用服务默认值。|
|**设置每日邮件限制** <p> _RecipientLimitPerDay_|0|1000|800|默认值 0 表示使用服务默认值。|
|**对达到邮件限制的用户施加的限制** <p> _ActionWhenThresholdReached_|**限制用户于第二天之前发送邮件** <p> `BlockUserForToday`|**限制用户发送邮件** <p> `BlockUser`|**限制用户发送邮件** <p> `BlockUser`||
|**自动转发规则** <p> _AutoForwardingMode_|**自动 - 系统控制** <p> `Automatic`|**自动 - 系统控制** <p> `Automatic`|**自动 - 系统控制** <p> `Automatic`|
|**向这些用户和组发送超过这些限制的出站邮件的副本** <p> _BccSuspiciousOutboundMail_ <p> _BccSuspiciousOutboundAdditionalRecipients_|未选定 <p> `$false` <p> 空白|未选定 <p> `$false` <p> 空白|未选定 <p> `$false` <p> 空白|我们对此设置没有具体的建议。 <p> 此设置仅适用于默认出站垃圾邮件策略。 它不能用于您创建的自定义出站垃圾邮件策略。|
|**如果发件人因发送出站垃圾邮件被阻止，则通知这些用户和组** <p> _NotifyOutboundSpam_ <p> _NotifyOutboundSpamRecipients_|未选定 <p> `$false` <p> 空白|未选定 <p> `$false` <p> 空白|未选定 <p> `$false` <p> 空白|名为"[](../../compliance/alert-policies.md)限制发送电子邮件的用户"的默认警报 **策略已在用户** 因超出策略限制被阻止 **时向****TenantAdmins** (全局管理员) 组的成员发送电子邮件通知。 **强烈建议使用警报** 策略，而不是出站垃圾邮件策略中的此设置来通知管理员和其他用户。 有关说明，请参阅 [验证受限用户的警报设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。|
|

### <a name="eop-anti-malware-policy-settings"></a>EOP 反恶意软件策略设置

若要创建和配置反恶意软件策略，请参阅 [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。

<br>

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**保护设置**|||||
|**启用常见附件筛选器** <p> _EnableFileFilter_|未选定 <p> `$false`|已选中 <p> `$true`|已选中 <p> `$true`|此设置根据文件类型隔离包含可执行附件的邮件，而不考虑附件内容。|
|**启用恶意软件的零时差自动清除** <p> _ZapEnabled_|已选中 <p> `$true`|已选中 <p> `$true`|已选中 <p> `$true`||
|**收件人通知**|||||
|**当邮件被隔离为恶意软件时通知收件人** <p> _Action_|未选定 <p> _DeleteMessage_|未选定 <p> _DeleteMessage_|未选定 <p> _DeleteMessage_|如果在电子邮件附件中检测到恶意软件，邮件将被隔离，并且只有管理员才能释放。|
|**发件人通知**|||||
|**将邮件隔离为恶意软件时通知内部发件人** <p> _EnableInternalSenderNotifications_|未选定 <p> `$false`|未选定 <p> `$false`|未选定 <p> `$false`||
|**当邮件被隔离为恶意软件时通知外部发件人** <p> _EnableExternalSenderNotifications_|未选定 <p> `$false`|未选定 <p> `$false`|未选定 <p> `$false`||
|**管理员通知**|||||
|**通知管理员有关来自内部发件人的未送达邮件** <p> _EnableInternalSenderAdminNotifications_ <p> _InternalSenderAdminAddress_|未选定 <p> `$false`|未选定 <p> `$false`|未选定 <p> `$false`|我们对此设置没有具体的建议。|
|**通知管理员来自外部发件人的未送达邮件** <p> _EnableExternalSenderAdminNotifications_ <p> _ExternalSenderAdminAddress_|未选定 <p> `$false`|未选定 <p> `$false`|未选定 <p> `$false`|我们对此设置没有具体的建议。|
|**自定义通知**||||我们对于这些设置没有具体的建议。|
|**使用自定义通知文本** <p> _CustomNotifications_|未选定 <p> `$false`|未选定 <p> `$false`|未选定 <p> `$false`||
|**From name** <p> _CustomFromName_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**发件人地址** <p> _CustomFromAddress_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**自定义来自内部发件人的邮件的通知**||||只有在选择"将邮件隔离 **为恶意软件时** 通知内部发件人"或"通知管理员有关来自内部发件人的未送达邮件"时，才 **使用** 这些设置。|
|**Subject** <p> _CustomInternalSubject_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**消息** <p> _CustomInternalBody_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**自定义来自外部发件人的邮件的通知**||||只有在选择"将邮件隔离为恶意软件时通知外部发件人"或"通知管理员有关来自外部发件人的未送达邮件"时，才使用这些设置。|
|**Subject** <p> _CustomExternalSubject_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**消息** <p> _CustomExternalBody_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|

### <a name="eop-anti-phishing-policy-settings"></a>EOP 防钓鱼策略设置

有关这些设置详细信息，请参阅欺骗 [设置](set-up-anti-phishing-policies.md#spoof-settings)。 若要配置这些设置，请参阅在 EOP 中配置防 [钓鱼策略](configure-anti-phishing-policies-eop.md)。

<br>

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**网络钓鱼阈值&保护**|||||
|**启用欺骗智能** <p> _EnableSpoofIntelligence_|已选中 <p> `$true`|已选中 <p> `$true`|已选中 <p> `$true`||
|**Actions**|||||
|**如果邮件被检测为欺骗邮件** <p> _AuthenticationFailAction_|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**隔离邮件** <p> `Quarantine`|此设置适用于欺骗性发件人，这些发件人被自动阻止，如欺骗智能见解中所示，[](learn-about-spoof-intelligence.md)或在租户允许/阻止列表中手动[阻止](tenant-allow-block-list.md)。|
|**显示第一个联系人安全提示** <p> _EnableFirstContactSafetyTips_|未选定 <p> `$false`|已选中 <p> `$true`|已选中 <p> `$true`|有关详细信息，请参阅第[一个联系人安全提示。](set-up-anti-phishing-policies.md#first-contact-safety-tip)|
|**显示 () 欺骗的未经身份验证的发件人的发件人身份** <p> _EnableUnauthenticatedSender_|已选中 <p> `$true`|已选中 <p> `$true`|已选中 <p> `$true`|为无法识别 () 发件人在发件人的照片Outlook问号。 有关详细信息，请参阅未经 [身份验证的发件人](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|**显示"via"标记** <p> _EnableViaTag_|已选中 <p> `$true`|已选中 <p> `$true`|已选中 <p> `$true`|如果 via 标记 (chris@contoso.com 地址 fabrikam.com) DKIM 签名或 MAIL FROM 地址中的域不同，则通过 fabrikam.com) 添加到 **"** 收件人"地址。 <p> 有关详细信息，请参阅未经 [身份验证的发件人](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender Office 365安全

Microsoft Defender for Office 365订阅提供了其他安全优势。 有关最新新闻和信息，请参阅 Defender for Office 365 中的[新增Office 365。](whats-new-in-defender-for-office-365.md)

> [!IMPORTANT]
>
> - Microsoft Defender for Office 365[中的默认](set-up-anti-phishing-policies.md#spoof-settings)防钓鱼策略可为所有收件人提供欺骗保护和邮箱智能。 但是，其他 [可用的模拟保护](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 功能和 [高级](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 设置未在默认策略中配置或启用。 若要启用所有保护功能，请修改默认的防钓鱼策略或创建其他防钓鱼策略。
>
> - 没有可自动保险箱组织中所有收件人的默认保险箱链接策略或附件策略。 若要获取保护，需要创建至少一个"链接保险箱策略保险箱附件"策略。
>
> - [保险箱、SharePoint、OneDrive](mdo-for-spo-odb-and-teams.md)和 Microsoft Teams[文档](safe-docs.md)保护保险箱附件不依赖于"链接保险箱策略。

如果你的订阅包含 Microsoft Defender for Office 365或者如果你已购买 Defender for Office 365 作为加载项，请设置以下标准或严格配置。

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略Office 365

如前文所述，EOP 客户会获得基本的防钓鱼功能，但 defender for Office 365 包括更多功能和控制，以帮助防止、检测和修正攻击。 若要创建和配置这些策略，请参阅在 Defender for Office 365 中[配置防钓鱼Office 365。](configure-mdo-anti-phishing-policies.md)

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的反网络钓鱼策略中的高级Office 365

有关此设置详细信息，请参阅 Microsoft Defender for Office 365 中的反网络钓鱼策略[中的高级网络钓鱼Office 365。](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 若要配置此设置，请参阅在 Defender for [Office 365 中配置防钓鱼Office 365。](configure-mdo-anti-phishing-policies.md)

<br>

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**网络钓鱼电子邮件阈值** <p> _PhishThresholdLevel_|**1 - 标准** <p> `1`|**2 - 主动** <p> `2`|**3 - 更主动** <p> `3`||
|

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略中的模拟Office 365

有关这些设置详细信息，请参阅 Microsoft Defender for Office 365 中的防钓鱼[策略中的模拟Office 365。](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 若要配置这些设置，请参阅在 Defender for [Office 365 中配置防钓鱼Office 365。](configure-mdo-anti-phishing-policies.md)

<br>

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**网络钓鱼阈值&保护**|||||
|**使用户能够保护 (** 的用户保护) <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|未选定 <p> `$false` <p> 无|已选中 <p> `$true` <p> \<list of users\>|已选中 <p> `$true` <p> \<list of users\>|我们建议添加用户 (角色中的) 发件人。 在内部，受保护的发件人可能是 CEO、CFO 和其他高级领导。 在外部，受保护的发件人可能包括会员或你的委员会。|
|**启用域以保护 (** 的域保护) |未选定|已选中|已选中||
|**包含我拥有域** <p> _EnableOrganizationDomainsProtection_|关闭 <p> `$false`|已选中 <p> `$true`|已选中 <p> `$true`||
|**包括自定义域** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|关闭 <p> `$false` <p> 无|已选中 <p> `$true` <p> \<list of domains\>|已选中 <p> `$true` <p> \<list of domains\>|我们建议在 (但) 但经常交互的发件人域中添加域。|
|**添加受信任的发件人和域** <p> _ExcludedSenders_ <p> _ExcludedDomains_|无|无|无|根据您的组织，我们建议添加被错误地标识为模拟尝试的发件人或域。|
|**启用邮箱智能** <p> _EnableMailboxIntelligence_|已选中 <p> `$true`|已选中 <p> `$true`|已选中 <p> `$true`||
|**启用模拟保护的智能** <p> _EnableMailboxIntelligenceProtection_|关闭 <p> `$false`|已选中 <p> `$true`|已选中 <p> `$true`|此设置允许通过邮箱智能对模拟检测执行指定的操作。|
|**Actions**|||||
|**如果邮件被检测为模拟用户** <p> _TargetedUserProtectionAction_|**不应用任何操作** <p> `NoAction`|**隔离邮件** <p> `Quarantine`|**隔离邮件** <p> `Quarantine`||
|**如果邮件被检测为模拟域** <p> _TargetedDomainProtectionAction_|**不应用任何操作** <p> `NoAction`|**隔离邮件** <p> `Quarantine`|**隔离邮件** <p> `Quarantine`||
|**如果邮箱智能检测到并模拟用户** <p> _MailboxIntelligenceProtectionAction_|**不应用任何操作** <p> `NoAction`|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**隔离邮件** <p> `Quarantine`||
|**显示用户模拟安全提示** <p> _EnableSimilarUsersSafetyTips_|关闭 <p> `$false`|已选中 <p> `$true`|已选中 <p> `$true`||
|**显示域模拟安全提示** <p> _EnableSimilarDomainsSafetyTips_|关闭 <p> `$false`|已选中 <p> `$true`|已选中 <p> `$true`||
|**显示用户模拟异常字符安全提示** <p> _EnableUnusualCharactersSafetyTips_|关闭 <p> `$false`|已选中 <p> `$true`|已选中 <p> `$true`||
|

#### <a name="eop-anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的 EOP 防钓鱼策略Office 365

这些设置与 EOP 中的反垃圾邮件 [策略设置中的设置相同](#eop-anti-spam-policy-settings)。

欺骗设置相互关联，但"显示第一 **个联系人安全提示** 设置不依赖于欺骗设置。

<br>

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**网络钓鱼阈值&保护**|||||
|**启用欺骗智能** <p> _EnableSpoofIntelligence_|已选中 <p> `$true`|已选中 <p> `$true`|已选中 <p> `$true`||
|**Actions**|||||
|**如果邮件被检测为欺骗邮件** <p> _AuthenticationFailAction_|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**将邮件移动到收件人的"垃圾邮件"文件夹** <p> `MoveToJmf`|**隔离邮件** <p> `Quarantine`|此设置适用于欺骗性发件人，这些发件人被自动阻止，如欺骗智能见解中所示，[](learn-about-spoof-intelligence.md)或在租户允许/阻止列表中手动[阻止](tenant-allow-block-list.md)。|
|**显示第一个联系人安全提示** <p> _EnableFirstContactSafetyTips_|未选定 <p> `$false`|已选中 <p> `$true`|已选中 <p> `$true`|有关详细信息，请参阅第[一个联系人安全提示。](set-up-anti-phishing-policies.md#first-contact-safety-tip)|
|**显示 () 欺骗的未经身份验证的发件人的发件人身份** <p> _EnableUnauthenticatedSender_|已选中 <p> `$true`|已选中 <p> `$true`|已选中 <p> `$true`|为无法识别 () 发件人在发件人的照片Outlook问号。 有关详细信息，请参阅未经 [身份验证的发件人](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|**显示"via"标记** <p> _EnableViaTag_|已选中 <p> `$true`|已选中 <p> `$true`|已选中 <p> `$true`|如果 via 标记 (chris@contoso.com 地址 fabrikam.com) DKIM 签名或 **MAIL FROM** 地址中的域不同，则通过 fabrikam.com) 将 标签添加到"收件人"地址。 <p> 有关详细信息，请参阅未经 [身份验证的发件人](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|

### <a name="safe-attachments-settings"></a>保险箱附件设置

保险箱Microsoft Defender for Office 365 中的附件包括与"附件"策略保险箱没有任何关系的全局设置，以及特定于每个"保险箱策略"的设置。 有关详细信息，请参阅 defender 中的保险箱[附件Office 365。](safe-attachments.md)

#### <a name="global-settings-for-safe-attachments"></a>附件的全局保险箱设置

若要配置这些设置，请参阅在 Microsoft 365 E5 中打开[保险箱、OneDrive](turn-on-mdo-for-spo-odb-and-teams.md)和 Microsoft Teams 保险箱[Documents 的](safe-docs.md)SharePoint 附件Microsoft 365 E5。

在 PowerShell 中，对这些设置使用 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) cmdlet。

<br>

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Defender for Office 365** <p> _EnableATPForSPOTeamsODB_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`||
|**打开 保险箱 客户端Office文档** <p> _EnableSafeDocs_|关 <p> `$false`|开 <p> `$true`|打开 <p> `$true`|此功能仅在许可证或许可证Microsoft 365 E5 Microsoft 365 E5 安全性有意义。 有关详细信息，请参阅 保险箱[Documents in Microsoft Defender for Office 365](safe-docs.md)。|
|**允许用户单击"受保护的视图"，即使保险箱文件被标识为恶意文件** <p> _AllowSafeDocsOpen_|关闭 <p> `$false`|关闭 <p> `$false`|关闭 <p> `$false`|此设置与文档保险箱相关。|
|

#### <a name="safe-attachments-policy-settings"></a>保险箱附件策略设置

若要配置这些设置，请参阅在 Defender [for 保险箱 中设置附件Office 365。](set-up-safe-attachments-policies.md)

在 PowerShell 中，将 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) 和 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) cmdlet 用于这些设置。

> [!NOTE]
> 如前面所述，附件策略保险箱默认策略。 "默认"列中的值是新建的"附件保险箱中的默认值。

<br>

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**保险箱附件未知恶意软件响应** <p> _启用__和操作_|**关闭** <p> `-Enable $false` 和 `-Action Block`|**阻止** <p> `-Enable $true` 和 `-Action Block`|**阻止** <p> `-Enable $true` 和 `-Action Block`|当 _Enable_ 参数$false时 _，Action_ 参数的值无关紧要。|
|**重定向包含检测到的附件的附件** ： **启用重定向** <p> _重定向_ <p> _RedirectAddress_|未选中，并且未指定电子邮件地址。 <p> `-Redirect $false` <p> _RedirectAddress_ 为空 `$null` () |选中并指定电子邮件地址。 <p> `$true` <p> 电子邮件地址|选中并指定电子邮件地址。 <p> `$true` <p> 电子邮件地址|将邮件重定向到安全管理员进行审阅。|
|**如果扫描保险箱超时或错误无法完成， (附件检测响应)** <p> _ActionOnError_|已选中 <p> `$true`|已选中 <p> `$true`|已选中 <p> `$true`||
|

### <a name="safe-links-settings"></a>保险箱链接设置

保险箱Defender for Office 365 中的链接包括应用于活动 保险箱 链接策略中包含的所有用户的全局设置，以及特定于每个 保险箱 链接策略的设置。 有关详细信息，请参阅 defender for[保险箱 中的链接Office 365。](safe-links.md)

#### <a name="global-settings-for-safe-links"></a>链接的保险箱设置

若要配置这些设置，请参阅在 Defender 中为 保险箱[链接配置全局Office 365。](configure-global-settings-for-safe-links.md)

在 PowerShell 中，对这些设置使用 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) cmdlet。

<br>

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**阻止以下 URL** <p> _ExcludedUrls_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`|我们对此设置没有具体的建议。 <p> 有关详细信息，请参阅链接[的"阻止以下 URL"保险箱列表](safe-links.md#block-the-following-urls-list-for-safe-links)。
|**在保险箱应用中使用Office 365链接** <p> _EnableSafeLinksForO365Clients_|打开 <p> `$true`|打开 <p> `$true`|打开 <p> `$true`|使用 保险箱 iOS 和 Android) 应用中支持Office 365移动 (链接。 有关详细信息，请参阅保险箱[应用的链接Office 365设置](safe-links.md#safe-links-settings-for-office-365-apps)。|
|**不跟踪用户在应用中单击受保护链接Office 365时间** <p> _TrackClicks_|开 <p> `$false`|关 <p> `$true`|关闭 <p> `$true`|关闭此设置 (_将 TrackClicks_ 设置为) 在受支持的应用中跟踪Office 365 `$true` 单击。|
|**不允许用户在应用中单击以访问Office 365 URL** <p> _AllowClickThrough_|打开 <p> `$false`|打开 <p> `$false`|打开 <p> `$false`|打开此设置 (将 _AllowClickThrough_ 设置为) 阻止在受支持的应用中单击到 `$false` Office 365 URL。|
|

#### <a name="safe-links-policy-settings"></a>保险箱链接策略设置

若要配置这些设置，请参阅在[Microsoft Defender 保险箱设置链接策略Office 365。](set-up-safe-links-policies.md)

在 PowerShell 中，将 [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) 和 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) cmdlet 用于这些设置。

> [!NOTE]
> 如前面所述，链接策略保险箱默认策略。 "默认"列中的值是新建链接策略保险箱中的默认值。

<br>

****

|安全功能名称|默认|标准|Strict|评论|
|---|:---:|:---:|:---:|---|
|**保护设置**|||||
|**为邮件中的未知潜在恶意 URL 选择操作** <p> _IsEnabled_|**关闭** <p> `$false`|**On** <p> `$true`|**On** <p> `$true`||
|**选择针对网站内未知或潜在恶意 URL Microsoft Teams** <p> _EnableSafeLinksForTeams_|**关闭** <p> `$false`|**On** <p> `$true`|**On** <p> `$true`|自 2020 年 3 月起，此功能在预览版中提供，或仅适用于 Microsoft Teams Technology Adoption Program (TAP) 。|
|**对指向文件的可疑链接应用实时 URL 扫描** <p> _ScanUrls_|未选定 <p> `$false`|已选中 <p> `$true`|已选中 <p> `$true`||
|**等待 URL 扫描完成，然后再传递邮件** <p> _DeliverMessageAfterScan_|未选定 <p> `$false`|已选中 <p> `$true`|已选中 <p> `$true`||
|**Apply 保险箱 Links to email messages sent within the organization** <p> _EnableForInternalSenders_|未选定 <p> `$false`|已选中 <p> `$true`|已选中 <p> `$true`||
|**不跟踪用户单击** <p> _DoNotTrackUserClicks_|未选定 <p> `$false`|未选定 <p> `$false`|未选定 <p> `$false`|关闭此设置 (_DoNotTrackUserClicks_ 设置为) `$false` 用户单击。|
|**不允许用户单击访问原始 URL** <p> _DoNotAllowClickThrough_|未选定 <p> `$false`|已选中 <p> `$true`|已选中 <p> `$true`|打开此设置 (_DoNotAllowClickThrough_ 设置为) 阻止单击 `$true` 到原始 URL。|
|**在通知和警告页面上显示组织品牌** <p> _EnableOrganizationBranding_|未选定 <p> `$false`|未选定 <p> `$false`|未选定 <p> `$false`|我们对此设置没有具体的建议。 <p> 在启用此设置之前，需要按照自定义组织的 Microsoft 365[主题](../../admin/setup/customize-your-organization-theme.md)中的说明上载公司徽标。|
|**不重写以下 URL** <p> _DoNotRewriteUrls_|未选定 <p> 空白|未选定 <p> 空白|未选定 <p> 空白|我们对此设置没有具体的建议。 有关详细信息，请参阅链接策略中的"不重写[保险箱 URL"](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)列表。|
|**通知**|||||
|**如何通知用户？**|**使用默认通知文本**|**使用默认通知文本**|**使用默认通知文本**|我们对此设置没有具体的建议。 <p> You can select **Use custom notification text (** _CustomNotificationText_) to enter customized notification text to use. You can also select **Use Microsoft 翻译工具 for automatic localization** (_UseTranslatedNotificationText_) to translate the custom notification text into the user's language.
|

## <a name="related-articles"></a>相关文章

- 您是否正在查找有关邮件流规则Exchange **也称为** (传输规则) ？ 请参阅[Best practices for configuring mail flow rules in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)。

- 管理员和用户可以提交误报 (标记为错误电子邮件) 误报 (错误电子邮件) Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

- 使用这些链接获取有关如何设置[EOP](/exchange/standalone-eop/set-up-your-eop-service)服务的信息，并配置[Microsoft Defender Office 365。](defender-for-office-365.md)  不要忘记'抵御威胁中的有用[Office 365'。](protect-against-threats.md)

- 可在此处找到 **Windows** 的安全基线：在哪里可以获取 GPO/本地选项的安全基线 [？](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)以及使用安全基线在 Intune 中配置 Windows 10 设备，以获得基于 [Intune](/intune/protect/security-baselines)的安全性。 最后，比较适用于终结点的 Microsoft Defender Microsoft Intune安全基线之间的比较可在比较 Microsoft Defender for Endpoint 和 Windows [Intune 安全基线中获得](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)。
