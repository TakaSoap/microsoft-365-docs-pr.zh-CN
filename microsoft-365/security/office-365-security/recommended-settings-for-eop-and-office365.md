---
title: Microsoft 针对 EOP 和 Defender for Office 365安全设置的建议
keywords: Office 365安全建议， 发件人策略框架， 基于域的邮件报告和一致性， 域密钥标识的邮件， 步骤， 如何工作， 安全基线， EOP 的基线， Defender for Office 365 的基线， 设置 Defender for Office 365 ， 设置 EOP， 配置Defender for Office 365，配置 EOP，安全配置
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 什么是 EOP Exchange Online Protection (和) Defender for Office 365最佳实践？ 标准保护的当前建议是什么？ 如果要更加严格，应该使用什么？ 此外，如果使用其他方法，还能获得Defender for Office 365？
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4b6c9df3b8c458aaf548ff9c8cfe8cc51fa5824
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507156"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>用于配置 EOP 和 Defender for Office 365 安全性的建议设置

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** 是 Microsoft 365 订阅的核心安全，有助于阻止恶意电子邮件到达员工的收件箱。 但是，随着每天出现更复杂的新攻击，通常需要改进的保护。 **Microsoft Defender for Office 365** 1 或计划 2 中包含其他功能，为管理员提供了多层安全、控制和调查。

尽管我们使安全管理员能够自定义其安全设置，但 EOP 和 Microsoft Defender for Office 365有两个安全级别：**Standard** 和 **Strict**。 虽然客户环境和需求不同，但在大多数情况下，这些筛选级别将有助于防止不需要的邮件到达员工的收件箱。

若要自动将"标准"或"严格"设置应用于用户，请参阅[在 EOP](preset-security-policies.md) 中预设Microsoft Defender for Office 365。

本文介绍了默认设置，以及建议的标准和严格设置，以帮助保护用户。 这些表包含 Microsoft 365 Defender 门户和 PowerShell (Exchange Online PowerShell 或独立 Exchange Online Protection PowerShell 中的设置，适用于Exchange Online邮箱) 。

> [!TIP]
> 你无法更改应用门户中建议的"标准"和"严格Microsoft 365 Defender设置。 若要更改建议的值（如"允许用户保护 **"，** 您需要使用 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。
>
> PowerShell Office 365高级威胁防护建议配置分析器 (ORCA) 模块可帮助你 (管理员) 查找这些设置的当前值。 具体来说， **Get-ORCAReport** cmdlet 可生成对反垃圾邮件、防钓鱼和其他邮件安全设置的评估。 可以在 下载 ORCA 模块 <https://www.powershellgallery.com/packages/ORCA/>。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP 中的反垃圾邮件、反恶意软件和防钓鱼保护

反垃圾邮件、反恶意软件和防钓鱼是 EOP 功能，管理员可配置这些功能。 建议采用以下标准或严格配置。

### <a name="eop-anti-spam-policy-settings"></a>EOP 反垃圾邮件策略设置

若要创建和配置反垃圾邮件策略，请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

|安全功能名称|默认值|Standard|严格|评论|
|---|:---:|:---:|:---:|---|
|**批量电子邮件阈值&垃圾邮件属性**|||||
|**批量电子邮件阈值** <br/><br/> _BulkThreshold_|7 |6 |4|有关详细信息，请参阅 [批量投诉级别 (BCL) EOP](bulk-complaint-level-values.md) 中。|
|_MarkAsSpamBulkMail_|`On`|`On`|`On`|此设置仅在 PowerShell 中可用。|
|**增加垃圾邮件得分** 设置|关闭|关闭|关闭|所有这些设置都是 ASF 高级垃圾邮件筛选器 (部分) 。 有关详细信息，请参阅本文中的反垃圾邮件策略中的 [ASF](#asf-settings-in-anti-spam-policies) 设置部分。|
|**标记为垃圾邮件** 设置|关闭|关闭|关闭|这些设置中的大多数都是 ASF 的一部分。 有关详细信息，请参阅本文中的反垃圾邮件策略中的 [ASF](#asf-settings-in-anti-spam-policies) 设置部分。|
|**包含特定语言** <br/><br/> _EnableLanguageBlockList_ <br/><br/> _LanguageBlockList_|**关** <br/><br/> `$false` <br/><br/> 空白|**关闭** <br/><br/> `$false` <br/><br/> 空白|**关闭** <br/><br/> `$false` <br/><br/> 空白|我们对此设置没有具体的建议。 您可以基于业务需求阻止特定语言的邮件。|
|**来自以下国家/地区** <br/><br/> _EnableRegionBlockList_ <br/><br/> _RegionBlockList_|**关** <br/><br/> `$false` <br/><br/> 空白|**关** <br/><br/> `$false` <br/><br/> 空白|**关闭** <br/><br/> `$false` <br/><br/> 空白|我们对此设置没有具体的建议。 您可以根据业务需求阻止来自特定国家/地区的邮件。|
| _TestModeAction (测试_) |**无**|**无**|**无**|此设置是 ASF 的一部分。 有关详细信息，请参阅本文中的反垃圾邮件策略中的 [ASF](#asf-settings-in-anti-spam-policies) 设置部分。|
|**操作**||||无论您选择"隔离 **邮件"**，" **选择隔离策略"** 框都可用。 隔离策略定义允许用户对隔离邮件执行哪些操作。 <br/><br/> 创建新的反垃圾邮件策略时，空值表示默认隔离策略用于定义由该特定裁定隔离的邮件的历史功能 (AdminOnlyAccessPolicy 用于 **高** 可信度网络钓鱼;DefaultFullAccessPolicy，用于其他) 。 <br/><br/> 管理员可以创建和选择自定义隔离策略，这些策略为用户定义更严格的或更少的限制功能。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。|
|**垃圾邮件** 检测操作 <br/><br/> _SpamAction_|**将邮件移动到"垃圾邮件"文件夹** <br/><br/> `MoveToJmf`|**将邮件移动到"垃圾邮件"文件夹** <br/><br/> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`||
|**高可信度垃圾邮件** 检测操作 <br/><br/> _HighConfidenceSpamAction_|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`||
|**网络钓鱼检测** 操作 <br/><br/> _PhishSpamAction_|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`||
|**高可信度网络钓鱼** 检测操作 <br/><br/> _HighConfidencePhishAction_|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`||
|**批量** 检测操作 <br/><br/> _BulkSpamAction_|**将邮件移动到"垃圾邮件"文件夹** <br/><br/> `MoveToJmf`|**将邮件移动到"垃圾邮件"文件夹** <br/><br/> `MoveToJmf`|“隔离邮件”   发送邮件至隔离邮件而不是目标收件人。 <br/><br/> `Quarantine`||
|**将垃圾邮件在隔离中保留此天数** <br/><br/> _QuarantineRetentionPeriod_|15 天<sup>\*</sup>|30 天|30 天|<sup>\*</sup> 默认值为 15 天的默认反垃圾邮件策略和在 PowerShell 中创建的新反垃圾邮件策略。 在 Microsoft 365 Defender 门户中创建的新反垃圾邮件策略中的默认值为 30 天。 <br/><br/> 此值还会影响由反网络钓鱼策略隔离的邮件。 有关详细信息，请参阅 [EOP 中的隔离电子邮件](quarantine-email-messages.md)。|
|**启用垃圾邮件安全提示** <br/><br/> _InlineSafetyTipsEnabled_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|为网络钓鱼邮件启用零时 (ZAP) 清除 <br/><br/> _PhishZapEnabled_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|为垃圾邮件启用 ZAP <br/><br/> _SpamZapEnabled_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**允许&阻止列表**|||||
|允许的发件人 <br/><br/> _AllowedSenders_|无|无|无||
|允许的发件人域 <br/><br/> _AllowedSenderDomains_|无|无|无|将域添加到允许的发件人列表不是一个好主意。 攻击者可以向您发送其他将被筛选掉的电子邮件。 <br/><br/> 使用 [欺骗智能见解](learn-about-spoof-intelligence.md) 和租户 [允许/](tenant-allow-block-list.md) 阻止列表查看在组织的电子邮件域中欺骗发件人电子邮件地址或外部域中欺骗发件人电子邮件地址的所有发件人。|
|阻止发件人 <br/><br/> _BlockedSenders_|无|无|无||
|阻止的发件人域 <br/><br/> _BlockedSenderDomains_|无|无|无||

#### <a name="asf-settings-in-anti-spam-policies"></a>反垃圾邮件策略中的 ASF 设置

本节中的表介绍了反垃圾邮件策略 (ASF) 高级垃圾邮件筛选器和 ASF 设置。 对于"标准 **"和"** 严格"级别，**所有这些****设置都为"关**"。 有关 ASF 设置详细信息，请参阅 EOP 中的高级垃圾邮件筛选器 [ (ASF) 设置](advanced-spam-filtering-asf-options.md)。

|安全功能名称|评论|
|---|---|
|**指向远程站点的图像链接 (** _IncreaseScoreWithImageLinks)_||
|**URL 中的数字 IP** 地址 (_IncreaseScoreWithNumericIps)_||
|**URL 重定向到** _IncreaseScoreWithRedirectToOtherPort (的其他_ 端口) ||
|指向 _IncreaseScoreWithBizOrInfoUrls (.biz_ 或 **.info** 网站) ||
| _MarkAsSpamEmptyMessages_ (空) ||
|**在 HTML 应用程序中嵌入标记** (_MarkAsSpamEmbedTagsInHtml_) ||
|**Html 格式的 JavaScript 或 VBScript** (_MarkAsSpamJavaScriptInHtml_) ||
|**HTML 格式的表单** 标记 (_MarkAsSpamFormTagsInHtml_) ||
|_MarkAsSpamFramesInHtml_ (HTML 格式的框架或 **iframe**) ||
| _MarkAsSpamWebBugsInHtml (HTML 中的_ Web) ||
|**HTML 格式的对象标记 (** _MarkAsSpamObjectTagsInHtml_) ||
| _MarkAsSpamSensitiveWordList (敏感_) ||
|**SPF 记录：**_MarkAsSpamSpfRecordHardFail (硬失败)_||
|**发件人 ID 筛选硬失败 (** _MarkAsSpamFromAddressAuthFail)_||
|**退 (** _MarkAsSpamNdrBackscatter)_||
| _TestModeAction (测试_) |对于支持"测试为操作"的 ASF 设置，可以将测试模式操作配置为"无"、添加默认 **X 标头** 文本或"发送 **Bcc** `None` (、 `AddXHeader``BccMessage` 或) "。 有关详细信息，请参阅 [启用、禁用或测试 ASF 设置](advanced-spam-filtering-asf-options.md#enable-disable-or-test-asf-settings)。|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 出站垃圾邮件策略设置

若要创建和配置出站垃圾邮件策略，请参阅在 EOP 中配置出 [站垃圾邮件筛选](configure-the-outbound-spam-policy.md)。

有关服务中的默认发送限制详细信息，请参阅发送 [限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

> [!NOTE]
> 出站垃圾邮件策略不是标准或严格预设安全策略的一部分。 **Standard 和** **Strict** **值指示我们在** 默认出站垃圾邮件策略或您创建的自定义策略中推荐的值。

|安全功能名称|默认值|Standard|严格|评论|
|---|:---:|:---:|:---:|---|
|**设置外部邮件限制** <br/><br/> _RecipientLimitExternalPerHour_|0|500|400|默认值 0 表示使用服务默认值。|
|**设置内部邮件限制** <br/><br/> _RecipientLimitInternalPerHour_|0|1000|800|默认值 0 表示使用服务默认值。|
|**设置每日邮件限制** <br/><br/> _RecipientLimitPerDay_|0|1000|800|默认值 0 表示使用服务默认值。|
|**对达到邮件限制的用户施加的限制** <br/><br/> _ActionWhenThresholdReached_|**限制用户于第二天之前发送邮件** <br/><br/> `BlockUserForToday`|**限制用户发送邮件** <br/><br/> `BlockUser`|**限制用户发送邮件** <br/><br/> `BlockUser`||
|**自动转发规则** <br/><br/> _AutoForwardingMode_|**自动 - 系统控制** <br/><br/> `Automatic`|**自动 - 系统控制** <br/><br/> `Automatic`|**自动 - 系统控制** <br/><br/> `Automatic`|
|**向这些用户和组发送超过这些限制的出站邮件的副本** <br/><br/> _BccSuspiciousOutboundMail_ <br/><br/> _BccSuspiciousOutboundAdditionalRecipients_|未选定 <br/><br/> `$false` <br/><br/> 空白|未选定 <br/><br/> `$false` <br/><br/> 空白|未选定 <br/><br/> `$false` <br/><br/> 空白|我们对此设置没有具体的建议。 <br/><br/> 此设置仅适用于默认出站垃圾邮件策略。 它不能用于您创建的自定义出站垃圾邮件策略。|
|**如果发件人因发送出站垃圾邮件被阻止，则通知这些用户和组** <br/><br/> _NotifyOutboundSpam_ <br/><br/> _NotifyOutboundSpamRecipients_|未选定 <br/><br/> `$false` <br/><br/> 空白|未选定 <br/><br/> `$false` <br/><br/> 空白|未选定 <br/><br/> `$false` <br/><br/> 空白|名为"[](../../compliance/alert-policies.md)限制发送电子邮件的用户"的默认警报策略已在用户因超出策略限制被阻止 **时向** **TenantAdmins** (全局管理员) 组的成员发送电子邮件通知。 **强烈建议使用警报** 策略，而不是出站垃圾邮件策略中的此设置来通知管理员和其他用户。 有关说明，请参阅 [验证受限用户的警报设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。|

### <a name="eop-anti-malware-policy-settings"></a>EOP 反恶意软件策略设置

若要创建和配置反恶意软件策略，请参阅 [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。

|安全功能名称|默认值|Standard|严格|评论|
|---|:---:|:---:|:---:|---|
|**保护设置**|||||
|**启用常见附件筛选器** <br/><br/> _EnableFileFilter_|未选定 <br/><br/> `$false`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|此设置根据文件类型隔离包含可执行附件的邮件，而不考虑附件内容。|
|**启用恶意软件的零时差自动清除** <br/><br/> _ZapEnabled_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**隔离策略**|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|创建新的反恶意软件策略时，空值表示默认隔离策略用于定义被隔离为恶意软件的邮件的历史功能 (AdminOnlyAccessPolicy) 。 <br/><br/> 管理员可以创建和选择为用户定义更多功能的自定义隔离策略。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。|
|**收件人通知**|||||
|**当邮件被隔离为恶意软件时通知收件人** <br/><br/> _操作_|未选定 <br/><br/> _DeleteMessage_|未选定 <br/><br/> _DeleteMessage_|未选定 <br/><br/> _DeleteMessage_|如果在电子邮件附件中检测到恶意软件，邮件将被隔离，并且只有管理员才能释放。|
|**发件人通知**|||||
|**将邮件隔离为恶意软件时通知内部发件人** <br/><br/> _EnableInternalSenderNotifications_|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`||
|**当邮件被隔离为恶意软件时通知外部发件人** <br/><br/> _EnableExternalSenderNotifications_|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`||
|**管理员通知**|||||
|**通知管理员有关来自内部发件人的未送达邮件** <br/><br/> _EnableInternalSenderAdminNotifications_ <br/><br/> _InternalSenderAdminAddress_|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`|我们对此设置没有具体的建议。|
|**通知管理员来自外部发件人的未送达邮件** <br/><br/> _EnableExternalSenderAdminNotifications_ <br/><br/> _ExternalSenderAdminAddress_|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`|我们对此设置没有具体的建议。|
|**自定义通知**||||我们对于这些设置没有具体的建议。|
|**使用自定义通知文本** <br/><br/> _CustomNotifications_|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`||
|**From name** <br/><br/> _CustomFromName_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`||
|**发件人地址** <br/><br/> _CustomFromAddress_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`||
|**自定义来自内部发件人的邮件的通知**||||只有在选择"将邮件隔离 **为恶意软件时** 通知内部发件人"或"通知管理员有关来自内部发件人的未送达邮件"时，才 **使用** 这些设置。|
|**主题** <br/><br/> _CustomInternalSubject_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`||
|**消息** <br/><br/> _CustomInternalBody_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`||
|**自定义来自外部发件人的邮件的通知**||||只有在选择"将邮件隔离为恶意软件时通知外部发件人"或"通知管理员有关来自外部发件人的未送达邮件"时，才使用这些设置。|
|**主题** <br/><br/> _CustomExternalSubject_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`||
|**消息** <br/><br/> _CustomExternalBody_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`||

### <a name="eop-anti-phishing-policy-settings"></a>EOP 防钓鱼策略设置

有关这些设置详细信息，请参阅欺骗 [设置](set-up-anti-phishing-policies.md#spoof-settings)。 若要配置这些设置，请参阅在 [EOP 中配置防钓鱼策略](configure-anti-phishing-policies-eop.md)。

|安全功能名称|默认值|Standard|严格|评论|
|---|:---:|:---:|:---:|---|
|**网络钓鱼阈值&保护**|||||
|**启用欺骗智能** <br/><br/> _EnableSpoofIntelligence_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**操作**|||||
|**如果邮件被检测为欺骗邮件** <br/><br/> _AuthenticationFailAction_|**将邮件移动到收件人的"垃圾邮件"文件夹** <br/><br/> `MoveToJmf`|**将邮件移动到收件人的"垃圾邮件"文件夹** <br/><br/> `MoveToJmf`|**隔离邮件** <br/><br/> `Quarantine`|此设置适用于欺骗性发件人，这些发件人被自动阻止，如欺骗智能见解中所示或在[](learn-about-spoof-intelligence.md)租户允许/阻止列表中手动[阻止](tenant-allow-block-list.md)。 <br/><br/> 如果选择"**隔离邮件**"，则"应用隔离策略"框可用于选择隔离策略，该策略定义允许用户对被隔离为欺骗的邮件执行哪些操作。 创建新的防钓鱼策略时，空值表示默认隔离策略用于定义被隔离为欺骗邮件的历史功能 (DefaultFullAccessPolicy) 。 <br/><br/> 管理员可以创建和选择自定义隔离策略，这些策略为用户定义更严格的或更少的限制功能。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。|
|**显示第一个联系人安全提示** <br/><br/> _EnableFirstContactSafetyTips_|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`|有关详细信息，请参阅第[一个联系人安全提示](set-up-anti-phishing-policies.md#first-contact-safety-tip)。|
|**显示 () 欺骗的未经身份验证的发件人的发件人身份** <br/><br/> _EnableUnauthenticatedSender_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|向 () 发件人的照片添加问号Outlook欺骗发件人。 有关详细信息，请参阅未经 [身份验证的发件人](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|**显示"via"标记** <br/><br/> _EnableViaTag_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|如果通过 (chris@contoso.com 通过 fabrikam.com) 将通过标记添加到"收件人"地址（如果它不同于 DKIM 签名或 **MAIL FROM** 地址中的域）。 <br/><br/> 有关详细信息，请参阅未经 [身份验证的发件人](set-up-anti-phishing-policies.md#unauthenticated-sender)。|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender for Office 365安全性

订阅订阅还具有Microsoft Defender for Office 365优势。 有关最新新闻和信息，请参阅最近[更新Defender for Office 365](whats-new-in-defender-for-office-365.md)。

> [!IMPORTANT]
>
> - 电子邮件中默认的防钓鱼策略[Microsoft Defender for Office 365所有收件人](set-up-anti-phishing-policies.md#spoof-settings)提供欺骗保护和邮箱智能。 但是，其他 [可用的模拟保护](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 功能和 [高级](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 设置未在默认策略中配置或启用。 若要启用所有保护功能，请修改默认的防钓鱼策略或创建其他防钓鱼策略。
>
> - 尽管没有默认的 保险箱 附件策略或 保险箱 链接策略，但内置保护预设安全策略为未在自定义 保险箱  附件策略或 保险箱 链接策略) 中定义的所有收件人 (用户提供 保险箱 附件保护和 保险箱 链接保护。 有关详细信息，请参阅在 EOP 中预设安全策略[和Microsoft Defender for Office 365](preset-security-policies.md)。
>
> - [保险箱、](mdo-for-spo-odb-and-teams.md)SharePoint、OneDrive、Microsoft Teams 和 保险箱 [文档](safe-docs.md)保护的附件不依赖于 保险箱 链接策略。

如果你的订阅包含Microsoft Defender for Office 365或者你已购买Defender for Office 365加载项，请设置以下标准或严格配置。

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>邮件中的防钓鱼策略Microsoft Defender for Office 365

如前面所述，EOP 客户会获得基本的防钓鱼功能，Defender for Office 365功能和控制，以帮助防止、检测和修正攻击。 若要创建和配置这些策略，请参阅在 Defender for Office 365 [中配置防钓鱼Defender for Office 365](configure-mdo-anti-phishing-policies.md)。

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的反网络钓鱼策略中的高级Microsoft Defender for Office 365

有关此设置详细信息，请参阅 Microsoft Defender for Office 365 中的[反网络钓鱼策略中的高级网络钓鱼Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。 若要配置此设置，请参阅在 Defender for Office 365 [中配置防钓鱼Defender for Office 365](configure-mdo-anti-phishing-policies.md)。

|安全功能名称|默认值|Standard|严格|评论|
|---|:---:|:---:|:---:|---|
|**网络钓鱼电子邮件阈值** <br/><br/> _PhishThresholdLevel_|**1 - 标准** <br/><br/> `1`|**2 - 主动** <br/><br/> `2`|**3 - 更主动** <br/><br/> `3`||

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略中的模拟Microsoft Defender for Office 365

有关这些设置详细信息，请参阅 Microsoft Defender for Office 365 中的[防钓鱼策略中的模拟Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。 若要配置这些设置，请参阅在 Defender for Office 365 [中配置防钓鱼Defender for Office 365](configure-mdo-anti-phishing-policies.md)。

|安全功能名称|默认值|Standard|严格|评论|
|---|:---:|:---:|:---:|---|
|**网络钓鱼阈值&保护**|||||
|**允许用户保护 (** 的用户保护)  <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|未选定 <br/><br/> `$false` <br/><br/> 无|已选中 <br/><br/> `$true` <br/><br/> \<list of users\>|已选中 <br/><br/> `$true` <br/><br/> \<list of users\>|我们建议在主要角色 (用户) 发件人。 在内部，受保护的发件人可能是 CEO、CFO 和其他高级领导。 从外部来说，受保护的发件人可以包含会员或你的委员会。 <br/><br/> 在预设安全策略中，无法指定要保护的用户。 需要禁用预设的安全策略，并使用自定义防钓鱼策略添加关键角色中的用户（如建议）。|
|**启用域以保护 (** 的域保护) |未选定|已选中|已选中||
|**包含我拥有域** <br/><br/> _EnableOrganizationDomainsProtection_|关 <br/><br/> `$false`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**包括自定义域** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|关 <br/><br/> `$false` <br/><br/> 无|已选中 <br/><br/> `$true` <br/><br/> \<list of domains\>|已选中 <br/><br/> `$true` <br/><br/> \<list of domains\>|我们建议在 (但) 但经常交互的发件人域中添加域。 <br/><br/> 在预设安全策略中，不能指定要保护的 custm 域。 需要禁用预设的安全策略，并使用自定义防钓鱼策略添加要保护的自定义域（如建议）。|
|**添加受信任的发件人和域** <br/><br/> _ExcludedSenders_ <br/><br/> _ExcludedDomains_|无|无|无|根据您的组织，我们建议添加被错误地标识为模拟尝试的发件人或域。|
|**启用邮箱智能** <br/><br/> _EnableMailboxIntelligence_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**启用模拟保护的智能** <br/><br/> _EnableMailboxIntelligenceProtection_|关 <br/><br/> `$false`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|此设置允许通过邮箱智能对模拟检测执行指定的操作。|
|**操作**||||无论您选择"隔离 **邮件"，**" **选择隔离策略"** 框都可用。 隔离策略定义允许用户对隔离邮件执行哪些操作。 <br/><br/> 创建新的防钓鱼策略时，空值表示默认隔离策略用于定义该裁定 (DefaultFullAccessPolicy 中所有模拟检测类型) 隔离的邮件的历史功能。 <br/><br/> 管理员可以创建和选择自定义隔离策略，这些策略为用户定义限制性较低或限制更严格的功能。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。|
|**如果邮件被检测为模拟用户** <br/><br/> _TargetedUserProtectionAction_|**不应用任何操作** <br/><br/> `NoAction`|**隔离邮件** <br/><br/> `Quarantine`|**隔离邮件** <br/><br/> `Quarantine`|请记住，预设安全策略不允许指定要保护的用户，因此此设置在预设安全策略中实际上不起任何作用。|
|**如果邮件被检测为模拟域** <br/><br/> _TargetedDomainProtectionAction_|**不应用任何操作** <br/><br/> `NoAction`|**隔离邮件** <br/><br/> `Quarantine`|**隔离邮件** <br/><br/> `Quarantine`|请记住，预设安全策略不允许指定要保护的自定义域，因此此设置仅影响你拥有域，而不影响自定义域。|
|**如果邮箱智能检测到并模拟用户** <br/><br/> _MailboxIntelligenceProtectionAction_|**不应用任何操作** <br/><br/> `NoAction`|**将邮件移动到收件人的"垃圾邮件"文件夹** <br/><br/> `MoveToJmf`|**隔离邮件** <br/><br/> `Quarantine`||
|**显示用户模拟安全提示** <br/><br/> _EnableSimilarUsersSafetyTips_|关 <br/><br/> `$false`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**显示域模拟安全提示** <br/><br/> _EnableSimilarDomainsSafetyTips_|关 <br/><br/> `$false`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**显示用户模拟异常字符安全提示** <br/><br/> _EnableUnusualCharactersSafetyTips_|关闭 <br/><br/> `$false`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||

#### <a name="eop-anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>电子邮件中的 EOP 防钓鱼策略Microsoft Defender for Office 365

这些设置与 EOP 中的反垃圾邮件 [策略设置中的设置相同](#eop-anti-spam-policy-settings)。

欺骗设置相互关联，但"显示第一 **个联系人安全提示** 设置不依赖于欺骗设置。

|安全功能名称|默认值|Standard|严格|评论|
|---|:---:|:---:|:---:|---|
|**网络钓鱼阈值&保护**|||||
|**启用欺骗智能** <br/><br/> _EnableSpoofIntelligence_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**操作**|||||
|**如果邮件被检测为欺骗邮件** <br/><br/> _AuthenticationFailAction_|**将邮件移动到收件人的"垃圾邮件"文件夹** <br/><br/> `MoveToJmf`|**将邮件移动到收件人的"垃圾邮件"文件夹** <br/><br/> `MoveToJmf`|**隔离邮件** <br/><br/> `Quarantine`|此设置适用于欺骗性发件人，这些发件人被自动阻止，如欺骗智能见解中所示或在[](learn-about-spoof-intelligence.md)租户允许/阻止列表中手动[阻止](tenant-allow-block-list.md)。 <br/><br/> 如果选择"**隔离邮件"**，则"应用隔离策略"框可用于选择用于定义允许用户对隔离邮件执行哪些操作的隔离策略。 创建新的防钓鱼策略时，空值表示默认隔离策略用于定义欺骗隔离邮件的历史功能 (DefaultFullAccessPolicy) 。 <br/><br/> 管理员可以创建和选择自定义隔离策略，该策略定义允许哪些收件人对隔离邮件执行哪些操作。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。|
|**显示第一个联系人安全提示** <br/><br/> _EnableFirstContactSafetyTips_|未选定 <br/><br/> `$false`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|有关详细信息，请参阅第[一个联系人安全提示](set-up-anti-phishing-policies.md#first-contact-safety-tip)。|
|**显示 () 欺骗的未经身份验证的发件人的发件人身份** <br/><br/> _EnableUnauthenticatedSender_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|向 () 发件人的照片添加问号Outlook欺骗发件人。 有关详细信息，请参阅未经 [身份验证的发件人](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|**显示"via"标记** <br/><br/> _EnableViaTag_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|如果通过 (chris@contoso.com 通过 fabrikam.com) 将通过标记添加到"收件人"地址（如果它不同于 DKIM 签名或 **MAIL FROM** 地址中的域）。 <br/><br/> 有关详细信息，请参阅未经 [身份验证的发件人](set-up-anti-phishing-policies.md#unauthenticated-sender)。|

### <a name="safe-attachments-settings"></a>保险箱附件设置

保险箱附件Microsoft Defender for Office 365包括与"附件"策略保险箱没有任何关系的全局设置，以及特定于每个"链接"保险箱的设置。 有关详细信息，请参阅保险箱[附件Defender for Office 365](safe-attachments.md)。

尽管没有默认的"保险箱 附件"策略，但内置保护预设安全策略为未在自定义 保险箱 附件策略) 中定义的所有收件人 (提供 保险箱 (附件保护。 有关详细信息，请参阅在 EOP 中预设安全策略[和Microsoft Defender for Office 365](preset-security-policies.md)。

#### <a name="global-settings-for-safe-attachments"></a>附件的全局保险箱设置

> [!NOTE]
> 附件的全局设置保险箱内置保护预设安全策略设置，而不是标准或 **严格** 预设安全策略设置。 无论使用哪种方式，管理员都保险箱修改这些全局"附件"设置。
>
> "**默认**"列显示在内置保护预设安全策略存在之前的值。 **内置保护列** 显示由内置保护预设安全策略设置的值，也是我们建议的值。

若要配置这些设置，请参阅在 [](turn-on-mdo-for-spo-odb-and-teams.md) 保险箱 中打开 SharePoint、OneDrive 和 Microsoft Teams 保险箱 [文档](safe-docs.md)Microsoft 365 E5。

在 PowerShell 中，对这些设置使用 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) cmdlet。

|安全功能名称|默认值|内置保护|评论|
|---|:---:|:---:|---|
|**启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Defender for Office 365** <br/><br/> _EnableATPForSPOTeamsODB_|关 <br/><br/> `$false`|开 <br/><br/> `$true`|若要阻止用户下载恶意文件，请参阅使用 [SharePoint Online PowerShell 阻止用户下载恶意文件](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。|
|**打开保险箱客户端的 Office 文档** <br/><br/> _EnableSafeDocs_|关 <br/><br/> `$false`|开 <br/><br/> `$true`|此功能仅适用于未包含在许可证中的许可证，例如Defender for Office 365 (许可证Microsoft 365 E5或Microsoft 365 E5 安全性) 。 有关详细信息，请参阅 保险箱 [Documents in Microsoft 365 E5](safe-docs.md)。|
|**允许用户单击"受保护的视图"，即使保险箱文件是恶意文件** <br/><br/> _AllowSafeDocsOpen_|关闭 <br/><br/> `$false`|关闭 <br/><br/> `$false`|此设置与文档保险箱相关。|

#### <a name="safe-attachments-policy-settings"></a>保险箱附件策略设置

若要配置这些设置，请参阅在保险箱[中设置附件Defender for Office 365](set-up-safe-attachments-policies.md)。

在 PowerShell 中，将 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) 和 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) cmdlet 用于这些设置。

> [!NOTE]
> 如前面所述，没有默认的"保险箱"策略，但保险箱"内置保护"预设安全策略将"附件"保护分配给[所有收件人](preset-security-policies.md)。
>
> "**自定义中的默认值**"列引用新建的"附件保险箱中的默认值。 其余列 (，除非另有) 预设安全策略中配置的值。

|安全功能名称|自定义中的默认值|内置保护|Standard|严格|评论|
|---|:---:|:---:|:---:|:---:|---|
|**保险箱未知恶意软件响应的附件** <br/><br/> _启用__和操作_|**关** <br/><br/> `-Enable $false` 和 `-Action Block`|**阻止** <br/><br/> `-Enable $true` 和 `-Action Block`|**阻止** <br/><br/> `-Enable $true` 和 `-Action Block`|**阻止** <br/><br/> `-Enable $true` 和 `-Action Block`|当 _Enable_ 参数$false时， _Action_ 参数的值无关紧要。|
|**隔离策略 (** _QuarantineTag_) |AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|创建新的 保险箱 附件策略时，空值表示默认隔离策略用于定义由 保险箱 Attachments (AdminOnlyAccessPolicy) 隔离的邮件的历史功能。 <br/><br/> 管理员可以创建和选择为用户定义更多功能的自定义隔离策略。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。|
|**重定向包含检测到的附件的附件** ： **启用重定向** <br/><br/> _重定向_ <br/><br/> _RedirectAddress_|未选中，并且未指定电子邮件地址。 <br/><br/> `-Redirect $false` <br/><br/> _RedirectAddress_ 为空 () `$null`|未选中，并且未指定电子邮件地址。 <br/><br/> `-Redirect $false` <br/><br/> _RedirectAddress_ 为空 () `$null`|选中并指定电子邮件地址。 <br/><br/> `$true` <br/><br/> 电子邮件地址|选中并指定电子邮件地址。 <br/><br/> `$true` <br/><br/> 电子邮件地址|将邮件重定向到安全管理员进行审阅。 <br/><br/> **注意**：未在标准、严格或内置保护预设安全策略中配置此设置。 **Standard 和** **Strict** **值指示在** 新建的附件保险箱中我们的建议值。|
|**如果扫描保险箱超时或错误无法完成，请应用 (附件检测)** <br/><br/> _ActionOnError_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||

### <a name="safe-links-settings"></a>保险箱链接设置

保险箱链接Defender for Office 365包括应用于活动 保险箱 链接策略中包含的所有用户的全局设置，以及特定于每个 保险箱 链接策略的设置。 有关详细信息，请参阅 保险箱 [Links in Defender for Office 365](safe-links.md)。

尽管没有默认的 保险箱 链接策略，但内置保护预设安全策略为未在自定义 保险箱 链接策略) 中定义的所有收件人 (提供 保险箱 链接保护。 有关详细信息，请参阅在 EOP 中预设安全策略[和Microsoft Defender for Office 365](preset-security-policies.md)。

#### <a name="global-settings-for-safe-links"></a>链接的全局保险箱设置

> [!NOTE]
> 链接的全局保险箱由内置保护预设安全策略设置，而不是通过 **标准** 或 **严格** 预设安全策略设置。 无论使用哪种方式，管理员都保险箱修改这些全局链接设置。
>
> "**默认**"列显示在内置保护预设安全策略存在之前的值。 **内置保护列** 显示由内置保护预设安全策略设置的值，也是我们建议的值。

若要配置这些设置，请参阅配置 保险箱 [链接的全局Defender for Office 365](configure-global-settings-for-safe-links.md)。

在 PowerShell 中，对这些设置使用 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) cmdlet。

|安全功能名称|默认值|内置保护|评论|
|---|:---:|:---:|---|
|**阻止以下 URL** <br/><br/> _ExcludedUrls_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|我们对此设置没有具体的建议。 <br/><br/> 有关详细信息，请参阅[链接链接的"阻止保险箱 URL"](safe-links.md#block-the-following-urls-list-for-safe-links)。
|**在保险箱应用中使用Office 365链接** <br/><br/> _EnableSafeLinksForO365Clients_|打开 <br/><br/> `$true`|开 <br/><br/> `$true`|使用保险箱 iOS 和 Android (应用支持Office 365移动) 链接。 有关详细信息，请参阅保险箱[应用的链接Office 365设置](safe-links.md#safe-links-settings-for-office-365-apps)。|
|**不跟踪用户在应用中单击受保护链接Office 365时间** <br/><br/> _TrackClicks_|开 <br/><br/> `$false`|关 <br/><br/> `$true`|关闭此设置 (_将 TrackClicks_ `$true` 设置为) 在受支持的应用中跟踪Office 365单击。|
|**不允许用户在应用中单击以访问Office 365 URL** <br/><br/> _AllowClickThrough_|打开 <br/><br/> `$false`|打开 <br/><br/> `$false`|打开此设置 (将 _AllowClickThrough_ `$false` 设置为) 阻止在受支持的应用中单击到Office 365 URL。|

#### <a name="safe-links-policy-settings"></a>安全链接策略设置

若要配置这些设置，请参阅在 Microsoft Defender for Office 365 [中设置保险箱链接策略](set-up-safe-links-policies.md)。

在 PowerShell 中，将 [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) 和 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) cmdlet 用于这些设置。

> [!NOTE]
> 如上所述，没有默认链接保险箱，保险箱内置保护预设安全策略将链接保护分配给所有[收件人](preset-security-policies.md)。
>
> "**自定义中的默认值**"列引用您创建的新"链接保险箱中的默认值。 其余列 (，除非另有) 预设安全策略中配置的值。

|安全功能名称|自定义中的默认值|内置保护|Standard|严格|评论|
|---|:---:|:---:|:---:|:---:|---|
|**单击&设置的 URL**||||||
|**对电子邮件中潜在恶意 URL 的操作**||||||
|**打开：保险箱用户单击电子邮件中的链接时，链接将检查已知恶意链接的列表** <br/><br/> _EnableSafeLinksForEmail_|未选定 <br/><br/> `$false`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**Apply 保险箱 Links to email messages sent within the organization** <br/><br/> _EnableForInternalSenders_|未选定 <br/><br/> `$false`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**对指向文件的可疑链接应用实时 URL 扫描** <br/><br/> _ScanUrls_|未选定 <br/><br/> `$false`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**等待 URL 扫描完成，然后再传递邮件** <br/><br/> _DeliverMessageAfterScan_|未选定 <br/><br/> `$false`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**不要重写 URL，仅通过保险箱链接 API 进行检查** <br/><br/> _DisableURLRewrite_|未选定 <br/><br/> `$false`|已选中 <br/><br/> `$true`|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`||
|**请勿在电子邮件中重写以下 URL** <br/><br/> _DoNotRewriteUrls_|未选定 <br/><br/> 空白|未选定 <br/><br/> 空白|未选定 <br/><br/> 空白|未选定 <br/><br/> 空白|我们对此设置没有具体的建议。 有关详细信息，请参阅链接策略中的"不要重写[保险箱 URL"](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)列表。|
|**针对网站中潜在恶意 URL Microsoft Teams**||||||
|**打开：保险箱用户单击链接时，链接将检查已知恶意链接Microsoft Teams** <br/><br/> _EnableSafeLinksForTeams_|未选定 <br/><br/> `$false`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**单击保护设置**||||||
|**跟踪用户单击** <br/><br/> _TrackUserClicks_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`||
|**让用户单击以访问原始 URL** <br/><br/> _AllowClickThrough_|已选中 <br/><br/> `$true`|已选中 <br/><br/> `$true`|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`|关闭此设置 (_将 AllowClickThrough_ `$false` 设置为) 阻止单击到原始 URL。|
|**在通知和警告页面上显示组织品牌** <br/><br/> _EnableOrganizationBranding_|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`|未选定 <br/><br/> `$false`|我们对此设置没有具体的建议。 <br/><br/> 在启用此设置之前，需要按照自定义组织的 Microsoft 365 [主题](../../admin/setup/customize-your-organization-theme.md)中的说明上载公司徽标。|
|**通知**||||||
|**如何通知用户？**|**使用默认通知文本**|**使用默认通知文本**|**使用默认通知文本**|**使用默认通知文本**|我们对此设置没有具体的建议。 <br/><br/> You can select **Use custom notification text (** _CustomNotificationText_) to enter customized notification text to use. You can also select **Use Microsoft 翻译工具 for automatic localization** (_UseTranslatedNotificationText_) to translate the custom notification text into the user's language.

## <a name="related-articles"></a>相关文章

- 您是否正在查找有关邮件流规则 **Exchange也称为 (传输** 规则) ？ 请参阅 [Best practices for configuring mail flow rules in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)。

- 管理员和用户可以提交误报 (标记为错误电子邮件) 误报 (错误电子邮件) Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

- 使用这些链接获取有关如何设置 EOP **服务** 以及如何配置 [EOP](/exchange/standalone-eop/set-up-your-eop-service) 服务 **Microsoft Defender for Office 365**[](defender-for-office-365.md)。 不要忘记"防止威胁威胁"中的有用[Office 365](protect-against-threats.md)。

- 有关 Windows 的安全基线，可以在此处找到：在哪里可以获取 GPO/本地选项的安全基线[？](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)以及使用安全基线在 Intune 中配置 Windows 设备，以获得基于 [Intune](/intune/protect/security-baselines) 的安全性。 最后，比较安全Microsoft Defender for Endpoint Microsoft Intune比较比较安全Microsoft Defender for Endpoint[比较Windows Intune比较比较基准](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)。
