---
title: EOP 和 Office 365 的配置最佳实践 ATP 安全性、最佳做法、设置、建议、发件人策略框架、基于域的邮件报告和符合性、域密钥识别的邮件、步骤、工作方式、
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Exchange Online Protection （EOP）和高级威胁防护（ATP）安全设置的最佳实践是什么？ 建议的功能 应主动使用什么？ 此外，如果您还使用高级威胁防护（ATP），还可以获得什么额外内容？
ms.openlocfilehash: fb6a39756c54e46f5ac8208c9c92af30bc144a57
ms.sourcegitcommit: d4aa94716b33e6c270ae7adfbdc4c19cf4a0087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "37387146"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp-security"></a>用于配置 EOP 和 Office 365 ATP 安全性的最佳实践

Exchange Online Protection （EOP）是 E3 Office 365 订阅的安全性的核心。 它是可选的，甚至鼓励我们的 E3 客户购买 Office 365 高级威胁防护（ATP）（ex）订阅。 ATP Plan 1 或 ATP 计划2，以便利用在 E5 Office 365 订阅中提供的附加安全性。

我们将讨论两个安全级别（称为 "建议" 和 "EOP"），其中包含有关如何在两个安全级别使用功能的注释。 这些部分的开始是电子邮件验证和身份验证，它涉及 Office 365 之外的一些 tinkering 在 DNS 中，并保护出站邮件，使租户的公民成为他们所邮件的资源。 这些设置最好保护你的订阅。


## <a name="email-authentication"></a>电子邮件身份验证

SPF、DKIM 和 DMARC 是发件人策略框架、域密钥标识的邮件和基于域的邮件身份验证、报告和一致性（相当于 mouthful）的首字母缩写词，并且是电子邮件身份验证和验证的基础。

这些方法处理来自 Office 365 的出站电子邮件，并帮助目标系统信任来自您的域的电子邮件是有效的。 它们是我们覆盖的最佳实践，其中包含在您的 DNS 中的 Office 365*之外*进行的配置。 有关具体的配置步骤，请参阅安全性和合规性目录中的[电子邮件验证和身份验证](https://docs.microsoft.com/en-us/office365/securitycompliance/how-office-365-uses-spf-to-prevent-spoofing)部分。


|安全功能名称  |建议 |积极  |Comment  |
|---------|---------|---------|---------|
|[创建 SPF 记录](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)    | Y        |    Y     |   -      |
|[配置域的 DKIM 签名](https://docs.microsoft.com/en-us/office365/securitycompliance/use-dkim-to-validate-outbound-email)     |  Y       |    Y     |  -       |
|[使用拒绝或隔离操作实现 DMARC](https://docs.microsoft.com/en-us/office365/securitycompliance/use-dmarc-to-validate-email)     |   Y      |     Y    |   使用 action = 无建议，操作 = 拒绝主动。     |

> [!IMPORTANT]
> 若要使用安全角色和权限，请确保您在 Office 365 或安全与合规中心中具有正确的角色。 如果你是 Azure Active Directory 中的*安全管理员*、Office 365 中的*全局管理员*或 Exchange Online/exchange Online Powershell 中的*exchange online 组织管理器*，则可以继续。

## <a name="anti-spam-anti-malware-and-anti-phishing"></a>反垃圾邮件、反恶意软件和反网络钓鱼

反垃圾邮件和反恶意软件都是 EOP 的功能。 垃圾邮件筛选功能，默认情况下在 Office 365 中扫描所有邮件，并为每个邮件分配垃圾邮件可信度（SCL）号码值。 简单地说，它的用途是列举筛选器是邮件是（或不是）垃圾邮件的置信度。 低值，如-1 是来自安全发件人和用户收件箱中的非垃圾邮件。 高分数（如7、8或9）可能是极具怀疑的，也可能是用户的垃圾邮件的已知垃圾邮件制造者和人，或者是管理员可访问的隔离。

默认情况下，Office 365 中的恶意软件筛选也是打开的。 与反垃圾邮件筛选一样，反恶意软件筛选器同时适用于入站和出站邮件。 在这两种情况下，可以通过管理员更好地配置此保护。

默认情况下，Office 365 中的网络钓鱼筛选器是打开的，但应将其配置为更好地进行配置。 下面是我们建议的 EOP 中的反网络钓鱼的建议。

### <a name="anti-spam"></a>反垃圾邮件

|安全功能名称  |建议 |积极  |Comment  |
|---------|---------|---------|---------|
|隔离保留期    |   Y      |     Y    |   30 天   |
|最终用户垃圾邮件通知频率   |   Y      |     Y    |   3 天   |
|应启用零小时 Autopurge   |   Y      |     Y    |   True  |
|应将垃圾邮件检测操作发送到 | JMF | 隔离 | - |
|应将高可信度垃圾邮件检测操作发送到 | 隔离 | 隔离| - |
|批量检测操作应设置为 | JMF | 隔离 | - |
|将批量电子邮件阈值设置为 | 型 | 4 | - |
|应启用安全提示| True | True | - |
|启用最终用户垃圾邮件通知| True | False | - |
|允许的发件人 | 无 | 无 | - |
|允许的发件人域 | 无 | 无 | - |
|阻止的发件人 | 无 | 无 | - |
|阻止的发件人域 | 无 | 无 | - |
|出站垃圾邮件策略 RRL | 500 | 500 | - |

建议在建议和严格级别中**禁用**：

|安全功能名称  |
|---------|
|IncreaseScoreWithImageLinks|
|IncreaseScoreWithNumericIps|
|IncreaseScoreWithRedirectToOtherPort|
|IncreaseScoreWithBizOrInfoUrls|
|MarkAsSpamEmptyMessages|
|MarkAsSpamJavaScriptInHtml|
|MarkAsSpamFramesInHtml|
|MarkAsSpamObjectTagsInHtml|
|MarkAsSpamEmbedTagsInHtml|
|MarkAsSpamFormTagsInHtml|
|MarkAsSpamWebBugsInHtml|
|MarkAsSpamSensitiveWordList|
|MarkAsSpamFromAddressAuthFail|
|MarkAsSpamNdrBackscatter|

建议在建议和严格级别**上启用**：

|安全功能名称  |
|---------|
|MarkAsSpamSpfRecordHardFail|
|MarkAsSpamBulkMail|

### <a name="anti-malware"></a>反恶意软件

|安全功能名称  |建议 |积极  |Comment  |
|---------|---------|---------|---------|
|为内部源配置恶意软件通知 |是 |是 |- |
|禁用通知外部发件人的恶意软件检测 |是 |是 |- |
|使用 "常见附件类型筛选器" 阻止可疑文件类型 | 是 |是 |- |
|恶意软件 ZAP |True |True |- |
|恶意软件操作 |阻止 |阻止 |- |

### <a name="anti-phishing"></a>反网络钓鱼

|安全功能名称  |建议 |积极  |Comment  |
|---------|---------|---------|---------|
|应启用零小时 Autopurge-网络钓鱼| True | True | - | 
|网络钓鱼检测操作应设置为 | 隔离-请求 | 隔离-管理员 | - |
|高可信度网络钓鱼检测操作应设置为 | 隔离-管理员 | 隔离-管理员 | - |
|EnableMailboxIntelligence | True | True | - |
|EnableSimilarUsersSafetyTips | True | True | - |
|EnableSimilarDomainsSafetyTips | True | True | - |
|EnableUnusualCharactersSafetyTips | True | True | - |
|TargetedUserProtectionAction |NoAction |阻止 | - |
|MailboxIntelligenceProtectionAction |NoAction |阻止 | - |
|TargetedDomainProtectionAction |NoAction |阻止 | - |
|AuthenticationFailAction |MoveToJmf |隔离 | - |
|AntiSpoofEnforcementType |高 |高 | - |
|EnableAuthenticationSafetyTip |False |True | - |
|EnableAntiSpoofEnforcement |True |True | - |
|EnableUnauthenticatedSender |True |True | - |
|EnableAuthenticationSoftPassSafetyTip |False |True | - |
|TreatSoftPassAsAuthenticated |True |False | - |
|EnableSuspiciousSafetyTip |True |True | - |

## <a name="office-365-advanced-threat-protection-atp-security"></a>Office 365 高级威胁防护（ATP）安全性

以前，我说我们鼓励我们为 E3 订阅添加 Office 365 ATP 计划1或更完全实现的 ATP 计划2。 高级反网络钓鱼是原因之一。 默认情况下启用，***必须***将防网络钓鱼配置为使用策略进行操作。 忘记配置反网络钓鱼策略会向用户带来风险，请确保在添加 ATP 订阅之后，执行第2步。

> [!IMPORTANT]
>  如果你有一个 E5 订阅，则你当前有[ATP 计划 2](https://products.office.com/en-us/exchange/advance-threat-protection)。 如果您想要了解[ATP 中的新增功能](https://review.docs.microsoft.com/en-us/microsoft-365/security/office-365-security/whats-new-in-office-365-atp?branch=oatp-newstuff)，请选中此链接。

### <a name="advanced-anti-phishing"></a>高级反网络钓鱼

网络钓鱼是企图伪装为著名的公司或个人以窃取个人信息，如信用卡号或计算机或设备 pin 或密码。 网络钓鱼可能涉及：

- **哄骗**，spoofers 尝试代表域中的特定目标发送邮件（例如，ellar@2020contoso.com 尝试为 ellar@2020litware.com 发送邮件（方案电子邮件身份验证方法可以帮助阻止）。 

- **模拟**：收到的邮件的发件人在视觉上类似（或看起来）到目标域或用户名的邮件。 这里有坏的演员，模拟特定的用户名，或假装为从目标域发送邮件。 下面是一个 pretense 域： ellar @ 2020 | itware，并且这里是一个 pretense 用户： ellαr @ 2020litware .com （在这些示例中仔细查看域和用户名，以捕获域和用户模拟）。

如果您已向您的 EOP 添加了 Office 365 ATP 订阅，请务必设置以下配置。

|安全功能名称  |建议 |积极  |Comment  |
|---------|---------|---------|---------|
|将高级网络钓鱼阈值设置为 | 双面 | 4 | - |
|启用反模拟保护 | 是 | 是 | - |
|在反模拟策略中启用邮箱智能 | 是 | 是 | - |
|启用基于邮箱智能的模拟保护 | 是 | 是 | - |
|域模拟操作应 | JMF | 隔离 | - |
|用户模拟操作应 | JMF | Qurantine | - |
|基于邮箱智能的模拟保护操作应 |尖  |JMF | - |

### <a name="safe-links-and-safe-attachments"></a>安全链接和安全附件

 ATP 包括安全附件和安全链接策略，以防止电子邮件发送可能有害的附件，并防止用户单击和旅行到可能不安全的 Url。

#### <a name="safe-links"></a>安全链接

|安全功能名称  |建议 |积极  |Comment  |
|---------|---------|---------|---------|
|ATP 安全链接应跟踪用户单击以进行响应 |是 |是 |- |
|应为 Office 应用程序启用 ATP 安全链接 |是 |是 |- |
|应为域内启用 ATP 安全链接 |是 |是 |- |
|ATP 安全链接应将实时 URL 扫描应用于指向文件的可疑链接和链接。 |是 |是 |- |
|ATP 安全链接应等待 URL 扫描完成，然后才能传递邮件。 |是 |是 |- |
<!--
|URLs to block | | | |
|URLs not to wrap | | | |-->

#### <a name="safe-attachments"></a>安全附件

|安全功能名称  |建议 |积极  |Comment  |
|---------|---------|---------|---------|
|ATP 安全附件策略操作应 |隔离 |隔离 |- |
|应为 OneDrive、SharePoint 和团队启用 ATP 保护 |是 |是 |- |
<!--
|Allowed file hashes | | | |
|Blocked file hashes | | | |
-->

## <a name="miscellaneous-settings"></a>其他设置

这些设置涵盖了一系列不一定符合上述特定类别的功能。 你也可以在此处找到一些设置为 1-关。

安全功能名称  |建议 |积极  |Comment  |
|---------|---------|---------|---------|
|创建 SPF 记录 |是 |是 |- |
|配置域的 DKIM 签名 |是 |是 |- |
|使用拒绝或隔离操作实现基于域的邮件报告和合规性（DMARC） |操作 = 无 |操作 = 拒绝 | |
|部署报告邮件加载项以改进最终用户报告可疑电子邮件的情况 |是 |是 |- |
|安排恶意软件和垃圾邮件报告 |是 |是 |- |
|应禁止或监视外部域的自动 fowarding |- |是 |- |
|应启用统一审核 |是 |是 |- |
|应在不需要的情况下禁用 IMAP |- |禁用 |- |
|应在不需要时禁用 POP |- |禁用 |- |
|在应用程序不需要时，应关闭 SMTP 验证的提交 |- |禁用 |- |
|应禁用 EWS |- |禁用 |- |
|PowerShell |- |禁用 |- |
|将发件人策略框架配置为硬失败 |-all |-all |- |
|尽可能使用欺骗智能白名单发件人 |是 |是 |- |
|基于目录的边缘阻止（DBEB） |已启用 |已启用 |域类型 = 权威 |
