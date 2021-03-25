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
ms.openlocfilehash: ff3c889f3e4d6779b08584ba6537da36d6f2660e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203273"
---
# <a name="eop-features"></a>EOP 功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
-  [独立 Exchange Online Protection](exchange-online-protection-overview.md)

下表提供了 Exchange Online Protection (EOP) 托管的电子邮件筛选服务中可用的功能列表。

> [!TIP]
> [Microsoft 365 商业版路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)是一个很好的资源，用于查找有关即将推出的新功能的信息。 有关不同 EOP 订阅计划中的可用功能的更全面介绍，请参阅 [Exchange Online Protection 服务说明](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

****

|功能|说明|
|---|---|
|**反垃圾邮件保护**||
|入站垃圾邮件检测|有关详细信息，请参阅 [Microsoft 365](anti-spam-protection.md)中的反垃圾邮件保护。 <p> 在 EOP 保护本地 Exchange 邮箱的独立 EOP 环境中，需要在本地 Exchange 中配置邮件流规则（亦称为“传输规则”），以转换 EOP 垃圾邮件筛选裁定，这样垃圾邮件规则才能将邮件移动到“垃圾邮件”文件夹。 有关详细信息，请参阅 [配置独立 EOP 以将垃圾邮件发送到混合环境中垃圾邮件文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)|
|出站垃圾邮件检测|如果您使用出站反垃圾邮件保护服务发送出站邮件，则始终启用。 有关详细信息，请参阅出 [站垃圾邮件保护](outbound-spam-controls.md)。|
|退退保护|有关详细信息，请参阅[退市和 EOP。](backscatter-messages-and-eop.md)|
|批量邮件筛选|EOP 使用 BCL (批量) 批量电子邮件标记为垃圾邮件。 有关详细信息，请参阅下列主题： <p> [垃圾邮件和批量邮件之间有什么差异？](what-s-the-difference-between-junk-email-and-bulk-email.md) <p> [EOP 中的批量 (BCL) 级别](bulk-complaint-level-values.md) <p> [配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
|恶意 URL 阻止列表|EOP 使用多个 URL 阻止列表，帮助检测邮件中的已知恶意链接。|
|防钓鱼保护|EOP 包括 750,000 个已知垃圾邮件制造者的域。|
|防欺骗保护|有关详细信息，请参阅 [反欺骗保护](anti-spoofing-protection.md)。|
|**垃圾邮件管理**||
|配置安全发件人和阻止发件人|有关详细信息，请参阅创建[安全发件人列表和](create-safe-sender-lists-in-office-365.md)[创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。|
|创建自定义反垃圾邮件策略|更精细地说明，您可以创建自定义反垃圾邮件策略，并应用于组织中指定的用户、组或域。 虽然自定义策略的优先级始终高于默认策略，但可以更改自定义策略的优先级（即运行顺序）。 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。|
|配置对垃圾邮件筛选邮件的操作|例如，您可以删除内容筛选的邮件或将其发送到"垃圾邮件"文件夹或隔离区。 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。|
|国际垃圾邮件筛选|您可以配置反垃圾邮件筛选，以筛选以特定语言编写或来自特定国家/地区的邮件。 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。|
|通过 Outlook 或 Web 上的 Outlook 管理 (以前称为"Outlook Web App) |管理员和最终用户可以创建安全发件人列表和阻止发件人列表。 有关详细信息，请参阅关于 [Outlook 中的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook)。 <p> 如果使用 EOP 帮助保护内部部署邮箱，请务必使用目录同步来帮助确保将这些设置同步到服务。 有关如何设置目录同步的详细信息，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)中的"使用目录同步管理邮件用户"。|
|向 Microsoft 报告误报和漏报。|有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。|
|最终用户垃圾邮件隔离通知|有关详细信息，请参阅最终用户垃圾邮件[通知和](use-spam-notifications-to-release-and-report-quarantined-messages.md)[配置最终用户垃圾邮件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)。|
|在隔离门户中查看、查找和管理邮件。|有关详细信息，请参阅在 [EOP](manage-quarantined-messages-and-files.md) 中以管理员角色管理隔离的邮件和文件或以用户角色查找并 [释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。|
|查看垃圾邮件隔离邮件头|在隔离中查看邮件头后，还可以将邮件头文本复制并粘贴到邮件头分析器[](https://mha.azurewebsites.net/)中，以找出邮件发生了什么。|
|**反恶意软件保护**||
|多引擎反恶意软件保护|多引擎反恶意软件保护可始终自动保护我们的客户。|
|禁用恶意软件筛选的能力|无法禁用恶意软件筛选。 我们相信，为我们的所有客户提供一致且严格的保护级别是深度防御策略的关键部分，该策略是保护电子邮件环境所必需的。 因此，对所有客户自动启用恶意软件筛选。|
|邮件正文和附件的恶意软件检查|服务可检测邮件正文中的活动有效负载和所有邮件附件是否存在恶意软件。|
|默认或自定义恶意软件警报通知|你可以向发件人或管理员发送通知邮件。 有关详细信息，请参阅配置 [反恶意软件策略](configure-anti-malware-policies.md)。|
|收件人通知|以静默方式隔离邮件或隔离邮件，同时传递邮件时，所有附件都替换为包含标准或自定义文本的单个文本文件。 有关详细信息，请参阅配置 [反恶意软件策略](configure-anti-malware-policies.md)。|
|常见附件筛选|你可以启用和自定义始终被认为是恶意软件的文件类型列表。 有关详细信息，请参阅 EOP 中的反 [恶意软件保护](anti-malware-protection.md)。|
|反间谍软件保护|反恶意软件保护包括反病毒保护和反间谍软件保护。|
|创建自定义恶意软件筛选器策略|更精确地讲，您可以创建自定义恶意软件筛选策略，并将其应用到组织中的特定用户、组或域。 自定义策略的优先级总是高于默认策略，但您可以更改自定义策略的优先级（即运行顺序）。 有关详细信息，请参阅配置 [反恶意软件策略](configure-anti-malware-policies.md)。|
|**邮件路由与连接器**||
|有条件的邮件路由|有关详细信息，请参阅[方案： Exchange Online 中的条件邮件路由](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)。|
|机会型或强制 TLS|机会型或强制 TLS 在连接器中可用。 机会型 TLS 尝试建立 TLS 连接，当 TLS 连接失败时，则使用 SMTP 连接。 强制 TLS 强制建立 TLS 连接，这意味着当 TLS 连接失败时，邮件将被拒绝。 有关 TLS、安全性以及连接器的详细信息，请参阅[Set up connectors for secure mail flow with a partner organization](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)。|
|区域路由（将邮件流限制到指定区域）|有关详细信息，请参阅 [Exchange Online Protection 概述](exchange-online-protection-overview.md)中的"EOP 数据中心"部分。|
|SMTP 连接检查程序工具|有关使用此工具测试邮件流的信息，请参阅通过验证 Microsoft [365](/exchange/mail-flow-best-practices/test-mail-flow)连接器测试邮件流。|
|Match subdomains|有关启用发送到接受域的子域和从这些子域发送邮件流的信息，请参阅 Mail [flow in EOP](mail-flow-in-eop.md)。|
|**邮件流规则**||
|基于策略的筛选和操作|自定义策略基于 Exchange 邮件流规则 (也称为传输规则) 。 您可以通过域、关键字、文件名、文件类型、主题行、邮件正文、发件人、收件人、邮件头和 IP 地址进行筛选。 有关详细信息，请参阅 Mail [flow rules (transport rules) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md)。|
|按文本模式进行筛选|邮件流规则可以使用数组或正则表达式来匹配文本。 您也可以使用一个字符串或字符串数组匹配多个邮件属性，例如地址、主题、正文或附件名称。 有关详细信息，请参阅 Mail [flow rules (transport rules) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md)|
|自定义词典|邮件流规则可以包含文本和关键字的长列表，提供与自定义词典相同的功能。|
|每个域策略规则|可以自定义邮件流规则的范围，以匹配发件人或收件人域名、IP 地址范围、地址关键字或模式、组成员身份和其他条件。|
|附件扫描|可以创建规则，以扫描附件的文件名、扩展名和内容。|
|向发件人发送策略规则通知|可以通过"拒绝包含说明的邮件"或"拒绝包含增强状态代码的邮件"操作拒绝邮件，并将未送达报告 (也称为 NDR 或退回邮件) **发送给发件人。** 有关详细信息，请参阅 Mail [flow rule actions in Exchange Online。](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|重定向或复制邮件|邮件流规则可以重定向收件人、按抄送或密件抄送添加收件人、仅添加收件人和其他选项。 有关详细信息，请参阅 Mail [flow rule actions in Exchange Online。](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|跨多个规则调整规则优先级|使用 Exchange 管理中心更改规则的处理顺序。|
|筛选邮件，然后更改邮件的路由或属性|您可以根据多种条件筛选邮件，然后对每个邮件应用一系列操作。 有关详细信息，请参阅 Mail [flow rules (transport rules) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md)。|
|按规则更改 (SCL) 邮件的垃圾邮件可信度。|您可以检测传输中的邮件并根据您选择条件，向其分配垃圾邮件可信度。 有关详细信息，请参阅使用邮件 [流规则在邮件中设置 (SCL) 垃圾邮件可信度](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。|
|检查邮件附件|您可以检查附件内容或附加文件的特性，并根据结果定义要采取的操作。 有关详细信息，请参阅 [使用邮件流规则检查 Exchange Online 中的邮件附件](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)。|
|**管理**||
|基于 Web 的管理|管理员可以在 Exchange 管理中心管理服务 (EAC) ，支持 60 种语言。 有关详细信息，请参阅独立 [EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。|
|目录同步|目录同步通过 Azure Active Directory 同步工具提供。有关详细信息，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)中的"使用目录同步管理邮件用户"部分。  |
|基于目录的边缘阻止 (DBEB)|通过 DBEB 功能，您可以在服务网络外围拒绝发送至无效收件人的邮件。 DBEB 允许管理员将启用邮件的收件人添加到 Microsoft 365，并阻止发送到 Microsoft 365 中不存在的电子邮件地址的所有邮件。 有关配置 DBEB 的信息，请参阅使用基于目录的边缘阻止拒绝 [发送给无效收件人的邮件](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。|
|PowerShell|独立 EOP PowerShell 中提供完整的 EOP 功能。 有关详细信息，请参阅 [Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell)。|
|**报告和日志记录**||
|邮件跟踪|管理员可以在通过服务时关注电子邮件。 您可以确定目标电子邮件是接收、拒绝、延迟还是由服务传递。 这使得您可以有效回答用户的问题，解决邮件流问题，验证策略更改，并减少联系技术支持寻求帮助的需要。 有关详细信息，请参阅“[安全与合规中心中的邮件跟踪](message-trace-scc.md)”。|
|基于 Web 的报告|安全与合规中心内的邮件&提供邮件数据。 例如，您可以监视检测到多少垃圾邮件和恶意软件或匹配邮件流规则多久。 通过这些交互式报告，您可以快速获取摘要数据的可视报告，并进一步了解每封邮件的详细信息（可回溯 90 天）。 有关详细信息，请参阅使用 [邮件保护报告查看有关恶意软件、垃圾邮件和规则检测的数据](/exchange/monitoring/use-mail-protection-reports)。|
|审核日志记录|向 EOP 管理员提供管理员角色组报告和管理员审核日志。有关详细信息，请参阅[EOP 中的审核报告](auditing-reports-in-eop.md)。  |
|**服务级别协议 (SLA) 及支持**||
|垃圾邮件有效性 SLA|\> 99%|
|误报率 SLA|\< 1:250,000|
|病毒检测和阻止 SLA|100% 的已知病毒|
|每月运行时间 SLA|99.999%|
|24 小时全天候电话和网络技术支持|有关 EOP 帮助和支持选项的详细信息，请参阅 [EOP 帮助与支持](help-and-support-for-eop.md)。|
|**其他功能**||
|服务器的地理位置冗余全局网络|EOP 在数据中心的全球网络中运行，旨在提供最好的可用性。有关详细信息，请参阅 [Exchange Online Protection 概述](exchange-online-protection-overview.md)中的"EOP 数据中心"一节。  |
|内部部署服务器无法接受邮件时的邮件队列|延期的邮件将在我们的队列中保留一天。 重试发送邮件的依据为从收件人的邮件系统返回的错误。 邮件一般每 5 分钟重试发送一次。 有关详细信息，请参阅 [EOP 排队、延迟以及退回邮件的常见问题](eop-queued-deferred-and-bounced-messages-faq.md)。|
|Office 365 邮件加密可作为附加服务使用|有关详细信息，请参阅 [Office 365 中的加密](../../compliance/encryption.md)。|
|