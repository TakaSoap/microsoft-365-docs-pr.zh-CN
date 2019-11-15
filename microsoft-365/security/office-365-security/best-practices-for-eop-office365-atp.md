---
title: EOP 和 Office 365 的最佳实践 ATP 安全设置、建议、发件人策略框架、基于域的邮件报告和符合性、域密钥识别的邮件、步骤、工作原理等
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/23/2019
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
ms.openlocfilehash: 6f9d38f7f6200083983f42d74a54163566585a90
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640791"
---
# <a name="best-practices-for-eop-and-office-365-atp-security"></a>EOP 和 Office 365 ATP 安全性的最佳实践

**Exchange Online Protection （EOP）** 是 Office 365 订阅的安全性的核心，可帮助防止恶意电子邮件到达你的员工的收件箱。 但对于每天都会涌现的新的更复杂的攻击，通常需要改进的保护。 **Office 365 高级威胁防护（ATP）** ATP Plan 1 或 ATP 计划2包含额外的功能，可为管理员提供更多的安全、控制和调查层次。 

尽管我们为安全管理员提供了自定义安全设置，但我们建议的 EOP 和 Office 365 ATP 中有两个安全级别：**标准**和**严格**。 每个客户的环境和需求各不相同，但我们认为这些级别的邮件筛选配置将有助于防止不需要的邮件在大多数情况下到达员工的收件箱。 

本主题介绍了这些 Microsoft 推荐的设置，以帮助保护 Office 365 用户。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP 中的反垃圾邮件、反恶意软件和反网络钓鱼防护
反垃圾邮件、反恶意软件和反网络钓鱼是可由管理员配置的 EOP 功能。 建议采用以下配置。

### <a name="anti-spam-policy"></a>反垃圾邮件策略

|安全功能名称|标准|全|评论|
|---------|---------|---------|---------|
|垃圾邮件检测操作|将邮件移动到 "垃圾邮件" 文件夹|隔离邮件||
|高可信度垃圾邮件检测操作|隔离邮件|隔离邮件||
|网络钓鱼电子邮件检测操作|隔离邮件|隔离邮件||
|高可信度网络钓鱼电子邮件检测操作|隔离邮件|隔离邮件||
|批量电子邮件检测操作|将邮件移动到 "垃圾邮件" 文件夹|隔离邮件||
|将批量电子邮件阈值设置为|型|4||
|隔离保留期|30 天|30 天||
|安全提示|打开|打开||
|允许的发件人|无|无||
|允许的发件人域|无|无|不需要将您拥有的域（也称为 "_接受的域_"）添加到允许的发件人列表中。 事实上，它被认为是高风险，因为它会给不良参与者带来机会，以向您发送邮件，否则将被筛选掉。在 "**反垃圾邮件设置**" 页上的安全性 & 合规性中心中使用[欺骗智能](learn-about-spoof-intelligence.md)，以查看所有哄骗的发件人是组织中的域，还是哄骗外部域。|
|阻止的发件人|无|无||
|阻止的发件人域|无|无||
|最终用户垃圾邮件通知频率|已启用|已启用|3 天|
|零小时自动清除|打开|打开|对于垃圾邮件和网络钓鱼 ZAP|
|MarkAsSpamBulkMail|打开|打开|此设置仅在 PowerShell 中可用|

#### <a name="outbound-spam-filter-policy"></a>出站垃圾邮件筛选器策略

|安全功能名称|标准|全|评论|
|---------|---------|---------|---------|
|出站垃圾邮件策略收件人限制-外部每小时限制|400|500||
|出站垃圾邮件策略收件人限制-内部每小时限制|800|1000||
|出站垃圾邮件策略收件人限制-每日限制|800|1000||
|用户超出限制时的操作|限制用户发送邮件|限制用户发送邮件||

### <a name="anti-malware-policy"></a>反恶意软件策略

|安全功能名称|标准|全|评论|
|---------|---------|---------|---------|
|恶意软件检测响应|否|否|如果在电子邮件附件中检测到恶意软件，邮件将被隔离，并且只能由管理员释放。|
|用于阻止可疑文件类型的 "常见附件类型筛选器"|打开|打开||
|恶意软件零小时自动清除|打开|打开||
|通知内部发件人未送达邮件|Disabled|Disabled||
|通知外部发件人未送达的邮件|Disabled|Disabled||

### <a name="anti-phishing-policy"></a>反网络钓鱼策略

|安全功能名称|标准|全|评论|
|---------|---------|---------|---------|
|启用 antispoofing 保护|打开|打开||
|启用未经身份验证的发件人（标记）|打开|打开||
|如果电子邮件由不允许欺骗您的域的人发送|将邮件移到收件人的 "垃圾邮件" 文件夹|隔离邮件||

## <a name="office-365-advanced-threat-protection-atp-security"></a>Office 365 高级威胁防护（ATP）安全性
Office 365 高级威胁防护订阅附带了其他安全优势。 有关最新的新闻和信息，可以查看[Office 365 ATP 中的新增功能](whats-new-in-office-365-atp.md)。 

Office 365 ATP 包括安全附件和安全链接策略，以防止电子邮件发送潜在的恶意附件，并防止用户单击可能不安全的 Url。

> [!IMPORTANT]
> 高级反网络钓鱼是 Office 365 ATP 订阅的好处之一。 默认情况下，***必须***先使用策略配置反网络钓鱼，然后才能开始筛选邮件。 忘记配置反网络钓鱼策略可能会使用户暴露风险的电子邮件。 在添加 Office 365 ATP 订阅后，请务必配置您的反网络钓鱼策略。

如果你已将 Office 365 ATP 订阅添加到你的 EOP，请设置以下配置。

### <a name="office-atp-anti-phishing-policy"></a>Office ATP 反网络钓鱼策略
EOP 客户获取基本的反网络钓鱼策略集，但在 Office 365 ATP 中，管理员可以获得更多的功能和控制，以帮助预防、检测和 remidiate 攻击。

|模拟安全功能名称|标准|全|评论|
|---------|---------|---------|---------|
|（编辑模拟策略）添加要保护的用户|打开|打开|取决于您的组织，但我们建议在关键角色中添加用户。 在内部，这些可能是 CEO、CFO 和其他高级领导者。 在外部，这些可以包括理事会成员或董事会。|
|（编辑模拟策略）自动包括我自己的域|打开|打开||
|（编辑模拟策略）包含自定义域|打开|打开|取决于您的组织，但我们建议添加与您不拥有的大多数进行交互的域。|
|如果由指定的模拟用户发送电子邮件|隔离邮件|隔离邮件||
|如果你指定的模拟域发送了电子邮件|隔离邮件|隔离邮件||
|为模拟用户显示提示|打开|打开||
|显示模拟域的提示|打开|打开||
|显示不正常字符的提示|打开|打开||
|启用邮箱智能|打开|打开||
|启用基于邮箱智能的模拟保护|打开|打开||
|如果由邮箱智能保护的模拟用户发送电子邮件|将邮件移到收件人的 "垃圾邮件" 文件夹|隔离邮件||
|（编辑模拟策略）添加受信任的发件人和域|无|无|取决于您的组织，但我们建议您添加由于仅模拟而不是其他筛选器而错误地将其标记为网络钓鱼的用户或域。|

|欺骗安全功能名称|标准|全|评论|
|---------|---------|---------|---------|
|启用 antispoofing 保护|打开|打开||
|启用未经身份验证的发件人（标记）|打开|打开||
|如果电子邮件由不允许欺骗您的域的人发送|将邮件移到收件人的 "垃圾邮件" 文件夹|隔离邮件||
|EnableAuthenticationSafetyTip|True|True|此设置仅在 PowerShell 中可用|
|EnableAuthenticationSoftPassSafetyTip|False|True|此设置仅在 PowerShell 中可用|
|EnableSuspiciousSafetyTip|False|True|此设置仅在 PowerShell 中可用|
|TreatSoftPassAsAuthenticated|True|False|此设置仅在 PowerShell 中可用|

|高级设置安全功能名称|标准|全|评论|
|---------|---------|---------|---------|
|高级网络钓鱼阈值|2-主动|3-更主动||

### <a name="safe-links-settings"></a>安全链接设置

|安全功能名称|标准|全|评论|
|---------|---------|---------|---------|
|在 Office 365 应用中使用 ATP 安全链接，Office for iOS 和 Android|已启用|已启用|这属于适用于整个组织的 ATP 安全链接策略|
用户单击安全链接时不进行跟踪|Disabled|Disabled|这属于适用于整个组织的 ATP 安全链接策略|
|不要让用户通过指向原始 URL 的安全链接进行单击|已启用|已启用|这属于适用于整个组织的 ATP 安全链接策略|
|邮件中未知的潜在恶意 Url 的操作|打开|打开||
|对指向文件的可疑链接和链接应用实时 URL 扫描|已启用|已启用||
|等待 URL 扫描完成后再传递邮件|已启用|已启用||
|将安全链接应用于在组织内发送的电子邮件|已启用|已启用||

### <a name="safe-attachments"></a>安全附件

|安全功能名称|标准|全|评论|
|---------|---------|---------|---------|
|启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP|已启用|已启用||
|ATP 安全附件未知的恶意软件响应|阻止|阻止||
|在检测时重定向附件|已启用|已启用|重定向到安全管理员的电子邮件地址，该管理员知道如何确定附件是否为恶意软件|
|如果恶意软件扫描附件超时或发生错误，则 ATP 安全附件响应|已启用|已启用||

## <a name="miscellaneous-settings-for-eop-or-office-365-atp"></a>EOP 或 Office 365 ATP 的杂项设置

这些设置涵盖了一系列不一定符合上述特定类别的功能。 某些设置在安全 & 合规中心之外。

安全功能名称|标准|全|评论|
|---------|---------|---------|---------|
|[在 Office 365 中设置 SPF 以防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|是|是||
|[使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)|是|是||
|[使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)|是|是|对 Standard 使用 action = 隔离，对 Strict 执行 action = 拒绝。|
|部署报告邮件加载项以改进最终用户报告可疑电子邮件的情况|是|是||
|安排恶意软件和垃圾邮件报告|是|是||
|自动转发到外部域应为 "允许" 或 "受监视"|是|是||
|应启用统一审核|是|是||
|IMAP 到邮箱的连接|Disabled|Disabled||
|到邮箱的 POP 连接|Disabled|Disabled||
|对邮箱的 SMTP 已验证的提交|Disabled|Disabled||
|到邮箱的 EWS 连接|Disabled|Disabled||
|PowerShell 连接|Disabled|Disabled||
|尽可能使用欺骗智能白名单发件人|是|是||
|基于目录的边缘阻止（DBEB）|已启用|已启用|域类型 = 权威|
|[为所有管理员帐户设置多重身份验证](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|已启用|已启用||
