---
title: EOP 功能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: 下表提供了 Exchange Online Protection (EOP) 托管的电子邮件筛选服务中可用的功能列表。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 62530a7c5da7ab0b7fd0e8415c8c366a1caafdda
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696450"
---
# <a name="eop-features"></a>EOP 功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)

下表提供了 EOP 电子邮件筛选服务中Exchange Online Protection (功能) 列表。

> [!TIP]
> 业务[Microsoft 365指南](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)是一个很好的资源，用于查找有关即将推出的新功能的信息。 有关不同 EOP 订阅计划中的可用功能的更全面介绍，请参阅 [Exchange Online Protection 服务说明](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

<br>

****

|功能|说明|
|---|---|
|**反恶意软件保护**||
|多引擎反恶意软件保护|多引擎反恶意软件保护可始终自动保护我们的客户。|
|始终打开恶意软件筛选|无法禁用恶意软件筛选。 我们相信，为我们的所有客户提供一致且严格的保护级别是深度防御策略的关键部分，该策略是保护电子邮件环境所必需的。 因此，对所有客户自动启用恶意软件筛选。|
|邮件正文和附件的恶意软件检查|服务可检测邮件正文中的活动有效负载和所有邮件附件是否存在恶意软件。|
|反间谍软件保护|反恶意软件保护包括反病毒保护和反间谍软件保护。|
|恶意软件筛选器策略|每个组织都有适用于所有收件人的默认反垃圾邮件策略。 更精细地来说，您可以创建适用于组织中特定用户、组或域的自定义反恶意软件策略。 自定义策略始终在默认策略之前应用，但可以更改自定义策略的应用顺序。 <p> 可以在反恶意软件策略中配置以下设置： <ul><li>**常见附件筛选**：启用始终被认为是恶意软件的文件类型的自定义列表。</li><li>**恶意软件的 ZAP：** 主动隔离传递的恶意软件邮件。 有关详细信息，请参阅 EXCHANGE ONLINE 中的零[时差自动清除 (ZAP) 。](zero-hour-auto-purge.md)</li><li>**收件人通知**：以静默方式隔离邮件或隔离邮件，并传递邮件，所有附件都替换为包含标准或自定义文本的单个文本文件。</li><li>**发件人通知**：通知发件人其邮件被检测为恶意软件。</li><li>**管理员通知**：当来自内部或外部发件人的邮件被检测为恶意软件时通知管理员。</li></ul> <p> 有关详细信息，请参阅配置 [反恶意软件策略](configure-anti-malware-policies.md)。|
|**防网络钓鱼钓鱼保护**||
|防钓鱼保护|EOP 使用已知垃圾邮件制造者使用的域列表。|
|防欺骗保护|EOP 中的防钓鱼保护包括反欺骗保护。 有关详细信息，请参阅 [反欺骗保护](anti-spoofing-protection.md)。 <p> Microsoft Defender for Office 365 中的防钓鱼保护还包括模拟保护。 有关详细信息，请参阅 [Microsoft Defender for Office 365 中反钓鱼策略中的“独占”设置](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。|
|**反垃圾邮件保护**||
|入站垃圾邮件检测|有关详细信息，请参阅反[垃圾邮件保护Microsoft 365。](anti-spam-protection.md) <p> 有关混合环境中所需的其他步骤，请参阅配置 EOP 以将垃圾邮件发送到混合环境中 [垃圾邮件文件夹](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。|
|退退保护|有关详细信息，请参阅[退市和 EOP。](backscatter-messages-and-eop.md)|
|批量邮件筛选|EOP 使用反垃圾邮件 (BCL) 批量投诉阈值将批量电子邮件标记为垃圾邮件。 有关详细信息，请参阅下列主题： <ul><li>[垃圾邮件和批量邮件之间有什么差异？](what-s-the-difference-between-junk-email-and-bulk-email.md)</li><li>[EOP 中的批量 (BCL) 级别](bulk-complaint-level-values.md)</li><li>[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)</li></ul>|
|恶意 URL 阻止列表|EOP 使用多个 URL 阻止列表，帮助检测邮件中的已知恶意链接。|
|**出站垃圾邮件保护**||
|出站垃圾邮件检测|如果您使用出站反垃圾邮件保护服务发送出站邮件，则始终启用。 有关详细信息，请参阅出 [站垃圾邮件保护](outbound-spam-controls.md)。|
|出站垃圾邮件策略|每个组织都有适用于所有收件人的默认出站垃圾邮件策略。 更精细地来说，您可以创建适用于组织中特定用户、组或域的自定义反垃圾邮件策略。 自定义策略始终在默认策略之前应用，但可以更改自定义策略的应用顺序。 <p> 可以在反垃圾邮件策略中配置以下设置： <ul><li>**管理 limt：** 可以设置低于每小时外部收件人服务默认值、每小时内部 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)收件人数和每天最大收件人数 **的限制**</li><li>**对超过限制的用户要** 采取的操作：将用户限制为 24 小时、限制用户直到发布或仅发出警报。</li><li>**启用或禁用自动外部电子邮件转发**： [了解更多信息](external-email-forwarding.md)</li><li>**向管理员通知或发送邮件副本**</li></ul> <p> 有关详细信息，请参阅在 [EOP 中配置出站垃圾邮件筛选](configure-the-outbound-spam-policy.md)。|
|**连接筛选**||
|连接筛选器策略|为组织配置 IP 允许列表和 IP 阻止列表。 有关详细信息，请参阅配置 [连接筛选](configure-the-connection-filter-policy.md)|
|**垃圾邮件管理**||
|反垃圾邮件策略|每个组织都有适用于所有收件人的默认反垃圾邮件策略。 更精细地来说，您可以创建适用于组织中特定用户、组或域的自定义反垃圾邮件策略。 自定义策略始终在默认策略之前应用，但可以更改自定义策略的应用顺序。 <p> 可以在反垃圾邮件策略中配置以下设置： <ul><li>**垃圾邮件** 筛选器裁定操作：当检测到邮件时，你可以根据该裁定将 (删除、移动到垃圾邮件文件夹、隔离等) 操作。</li><li>**高级垃圾邮件筛选器 (ASF) 设置**：这些设置在 EOP 中的高级垃圾邮件筛选器 [ (ASF) 设置中介绍](advanced-spam-filtering-asf-options.md)</li><li>**适用于网络钓鱼和垃圾邮件的 ZAP：** 主动隔离或将已送达邮件移动到"垃圾邮件"文件夹。 有关详细信息，请参阅 EXCHANGE ONLINE 中的零[时差自动清除 (ZAP) 。](zero-hour-auto-purge.md)</li><li>**启用最终用户垃圾邮件通知**：[了解有关最终用户垃圾邮件通知 (use-spam-notifications-to-release-and-report-quarantined-messages.md) </li>**允许和阻止的发件人和域**：若要了解如何安全使用这些列表，请参阅创建 [安全](create-safe-sender-lists-in-office-365.md) 发件人列表和 [创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)</li><li>**国际垃圾邮件设置**：基于语言或源国家/地区阻止邮件。</li></ul> <p> 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。|
|通过 Web Outlook或Outlook管理垃圾邮件 (以前称为Outlook Web App) |用户和管理员可以在邮箱中创建个人安全发件人列表和阻止Exchange Online列表。 有关详细信息，请参阅关于垃圾邮件[设置Outlook。](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook) <p> 如果使用 EOP 帮助保护本地 Exchange 邮箱，请务必使用目录同步来帮助确保将这些设置同步到服务。 有关详细信息，请参阅“[使用目录同步管理邮件用户](/exchange/standalone-eop/manage-mail-users-in-eop#synchronize-directories-with-azure-active-directory-connect-aad-connect)”。|
|向 Microsoft 报告误报和漏报。|有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。|
|在隔离门户中查看、查找和管理邮件。|有关详细信息，请参阅在 [EOP](manage-quarantined-messages-and-files.md) 中以管理员角色管理隔离的邮件和文件或以用户角色查找并 [释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。|
|查看垃圾邮件隔离邮件头|在隔离中查看邮件头后，还可以将邮件头文本复制并粘贴到邮件头分析器[](https://mha.azurewebsites.net/)中，以找出邮件发生了什么。|
|**邮件路由与连接器**||
|
|有条件的邮件路由|有关详细信息，请参阅[方案： Exchange Online 中的条件邮件路由](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)。|
|机会型或强制 TLS|<ul><li>机会型 TLS 尝试建立 TLS 连接，当 TLS 连接失败时，则使用 SMTP 连接。</li><li>强制 TLS 强制执行 TLS 连接，这意味着如果 TLS 连接失败，邮件将被拒绝。</li></ul> <p> 有关 TLS、安全性以及连接器的详细信息，请参阅[Set up connectors for secure mail flow with a partner organization](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)。|
|区域路由（将邮件流限制到指定区域）|有关详细信息，请参阅 [EOP 数据中心](exchange-online-protection-overview.md#eop-datacenters)。|
|SMTP 连接检查程序工具|有关使用此工具测试邮件流的信息，请参阅通过验证您的邮件Microsoft 365[流](/exchange/mail-flow-best-practices/test-mail-flow)。|
|Match subdomains|有关启用发送到接受域的子域和从这些子域发送邮件流的信息，请参阅 Mail [flow in EOP](mail-flow-in-eop.md)。|
|**邮件流规则**||
|EOP 中的邮件流规则|邮件流规则 (中可用的几乎所有条件、例外和操作（也称为 Exchange Online 中的传输规则) ）在没有 Exchange Online 邮箱的独立 EOP 组织中也可用。 有关邮件流规则详细信息，请参阅下列主题： <ul><li>[邮件流规则](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</li><li>[邮件流规则条件和例外](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</li><li>[邮件流规则操作](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</li></ul>|
|邮件流规则方案|许多方案都使用传输规则。 例如： <ul><li>**基于策略的筛选和操作**：可以按域、关键字、文件名、文件类型、主题行、邮件正文、发件人、收件人、头和 IP 地址进行筛选。</li><li>**按文本模式筛选**：邮件流规则可以使用数组或正则表达式来匹配文本。 您也可以使用一个字符串或字符串数组匹配多个邮件属性，例如地址、主题、正文或附件名称。</li><li>**自定义词典**：邮件流规则可以包含文本和关键字的长列表，提供与自定义词典相同的功能。</li><li>**每域策略规则**：您可以自定义邮件流规则的范围，以匹配发件人或收件人域名、IP 地址范围、地址关键字或模式、组成员身份和其他条件。</li><li>**附件扫描**：可以创建邮件流规则以扫描电子邮件附件的文件名、扩展名和内容。</li><li>向发件人发送策略规则通知：可以通过"拒绝包含说明的邮件"或"拒绝包含增强状态代码的邮件"操作拒绝邮件，并将未送达报告 (也称为 NDR 或退回邮件) **发送给发件人。**</li><li>**重定向或复制邮件**：邮件流规则可以重定向、按抄送或密件抄送添加收件人、仅添加收件人和其他选项。</li><li>**筛选邮件并更改邮件属性或路由**：可以基于各种条件筛选邮件，然后对每封邮件应用一系列操作。</li><li>**更改传输中 (邮件 (SCL) 的垃圾邮件可信度**</li></ul> <p> 有关特定邮件流规则方案的文章，请参阅 [邮件流规则过程](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)。|
|**管理**||
|基于 Web 的管理|可使用以下管理中心管理 EOP： <ul><li>安全[Microsoft 365中心](/microsoft-365/security/defender/overview-security-center)</li><li>管理[Exchange中心](/exchange/exchange-admin-center)</li><li>管理[Microsoft 365中心](/microsoft-365/admin/admin-overview/about-the-admin-center)</li></ul>|
|PowerShell|如果您的组织具有Exchange Online，您可以在 PowerShell 中管理 Exchange Online [EOP 功能](/powershell/exchange/exchange-online-powershell)。 如果您的组织没有邮箱Exchange Online，您可以在[PowerShell 中Exchange Online Protection EOP 功能](/powershell/exchange/exchange-online-protection-powershell)。|
|**报告和日志记录**||
|邮件跟踪|管理员可以在通过服务时关注电子邮件。 您可以确定目标电子邮件是接收、拒绝、延迟还是由服务传递。 这使得您可以有效回答用户的问题，解决邮件流问题，验证策略更改，并减少联系技术支持寻求帮助的需要。 有关详细信息，请参阅“[安全与合规中心中的邮件跟踪](message-trace-scc.md)”。|
|基于 Web 的报告|安全与合规中心内的邮件&提供邮件数据。 例如，您可以监视检测到多少垃圾邮件和恶意软件或匹配邮件流规则多久。 通过这些交互式报告，您可以快速获取摘要数据的可视报告，并进一步了解每封邮件的详细信息（可回溯 90 天）。 有关详细信息，请参阅使用 [邮件保护报告查看有关恶意软件、垃圾邮件和规则检测的数据](/exchange/monitoring/use-mail-protection-reports)。|
|审核日志记录|有关详细信息，请参阅审核[报告中Exchange Online。](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|**服务级别协议 (SLA) 及支持**||
|垃圾邮件有效性 SLA|\> 99%|
|误报率 SLA|\< 1:250,000|
|病毒检测和阻止 SLA|100% 的已知病毒|
|每月运行时间 SLA|99.999%|
|24 小时全天候电话和网络技术支持|有关 EOP 帮助和支持选项的详细信息，请参阅 [EOP 帮助与支持](help-and-support-for-eop.md)。|
|**其他功能**||
|服务器的地理位置冗余全局网络|EOP 在数据中心的全球网络中运行，旨在提供最好的可用性。有关详细信息，请参阅 [Exchange Online Protection 概述](exchange-online-protection-overview.md)中的"EOP 数据中心"一节。  |
|内部部署服务器无法接受邮件时的邮件队列|延期的邮件将在我们的队列中保留一天。 重试发送邮件的依据为从收件人的邮件系统返回的错误。 邮件一般每 5 分钟重试发送一次。 有关详细信息，请参阅 [EOP 排队、延迟以及退回邮件的常见问题](eop-queued-deferred-and-bounced-messages-faq.yml)。|
|Office 365 邮件加密可作为附加服务使用|有关详细信息，请参阅 [Office 365 中的加密](../../compliance/encryption.md)。|
|
