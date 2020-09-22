---
title: 创建阻止发件人列表
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 管理员可以了解可用的首选选项以阻止入站邮件在 Exchange Online Protection (EOP) 中。
ms.openlocfilehash: 7894a6cfe665539fa8c00f5911c4a588b9cf7ebc
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203187"
---
# <a name="create-blocked-sender-lists-in-eop"></a>在 EOP 中创建阻止的发件人列表

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Exchange Online 或独立 Exchange online 保护的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，EOP 提供了阻止来自不需要的发件人的电子邮件的多种方式。 这些选项包括 Outlook 阻止的发件人列表，阻止的发件人列表或阻止的域列表在反垃圾邮件策略中，Exchange 邮件流规则 (也称为传输规则) ，以及 IP 阻止列表 (连接筛选) 。 你可以将这些选项统称为阻止的 _发件人列表_。

阻止发件人的最佳方法因影响范围而异。 对于单个用户，正确的解决方案可能是 Outlook 阻止的发件人。 对于很多用户而言，其他选项中的一种更合适。 下面的选项按影响范围和广度进行排序。 列表从窄到范围，但阅读完整建议的 *细节* 。

1. Outlook 阻止的发件人 (存储在每个邮箱中的阻止发件人列表) 

2.  (反垃圾邮件策略阻止的发件人列表或阻止的域列表) 

3. 邮件流规则

4.  (连接筛选的 IP 阻止列表) 

> [!NOTE]
> 虽然您可以使用组织范围内的阻止设置来解决丢失垃圾邮件) 的漏报 (，但还应将这些邮件提交给 Microsoft 进行分析。 使用阻止列表管理漏报会显著增加管理开销。 如果使用阻止列表转移丢失的垃圾邮件，则需要将主题 [报告邮件和文件](report-junk-email-messages-to-microsoft.md) 保留在 Microsoft 准备就绪。

相比之下，您还可以使用多个选项始终允许使用 _安全发件人列表_从特定来源发送电子邮件。 有关详细信息，请参阅[创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

## <a name="email-message-basics"></a>电子邮件基础知识

标准 SMTP 电子邮件由*邮件信封*和邮件内容组成。 邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。 邮件内容包含邮件头字段（统称为*邮件头*）和邮件正文。 RFC 5321 中介绍了邮件信封，并且 RFC 5322 中介绍了邮件头。 收件人从不会看到实际邮件信封，因为它是由邮件传输进程生成的，并且实际上并不是邮件的一部分。

- 该 `5321.MailFrom` 地址 (也称为 " **发** 件人地址"、"P1 发件人" 或 "信封发件人") 是在邮件的 SMTP 传输中使用的电子邮件地址。 此电子邮件地址通常记录在邮件标头的 " **返回路径** 标头" 字段中 (尽管可以将不同的 **返回路径** 电子邮件地址指定) 。 如果无法传递邮件，则表示未送达报告 (的收件人也称为 "NDR" 或 "退回邮件") 。

- "发件人 `5322.From` 地址" **From**或 "P2 发件人") 的 (也称为 **"发**件人" 头字段中的电子邮件地址，它是电子邮件客户端中显示的发件人的电子邮件地址。

通常， `5321.MailFrom` 和 `5322.From` 地址 (个人到人员通信) 相同。 但是，如果代表其他人发送电子邮件，则地址可能会不同。

EOP 中的反垃圾邮件策略中阻止的发件人列表和阻止的域列表将检查 `5321.MailFrom` 和 `5322.From` 地址。 Outlook 阻止的发件人仅使用该 `5322.From` 地址。

## <a name="use-outlook-blocked-senders"></a>使用 Outlook 阻止的发件人

当只有少量用户收到不需要的电子邮件时，用户或管理员可以将发件人电子邮件地址添加到邮箱中阻止的发件人列表中。 有关说明，请参阅 [在 Exchange Online 邮箱上配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

当邮件由于用户的阻止发件人列表而成功被阻止时， **X-Forefront-反垃圾邮件报告** 的标头字段将包含该值 `SFV:BLK` 。

> [!NOTE]
> 如果不需要的邮件是来自可信且可识别的来源的新闻快递，则取消对该电子邮件的订阅是阻止用户接收邮件的另一种方法。

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>使用阻止的发件人列表或阻止的域列表

当多个用户受到影响时，范围将变宽，因此下一个最佳选项是在反垃圾邮件策略中阻止发件人列表或阻止的域列表。 来自列表中发件人的邮件被标记为 **垃圾**邮件，而您为 **垃圾邮件** 筛选器判定配置的操作将在邮件上执行。 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

这些列表的最大限制约为1000个条目。

## <a name="use-mail-flow-rules"></a>使用邮件流规则

如果需要阻止发送到特定用户或整个组织中的邮件，则可以使用邮件流规则。 邮件流规则比阻止发件人列表或阻止的发件人域列表更灵活，因为它们还可以查找不需要的邮件中的关键字或其他属性。

无论您用于标识邮件的条件或例外情况如何，都可以将操作配置为将邮件的垃圾邮件可信度级别 (SCL) 设置为9，这会将邮件标记为 **高可信度垃圾**邮件。 有关详细信息，请参阅 [使用邮件流规则设置邮件中的 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

> [!IMPORTANT]
> 很容易创建规则 *过于* 积极的规则，因此，只需使用非常具体的条件来确定要阻止的邮件，这一点非常重要。 此外，请务必对规则启用审核并测试规则的结果，以确保一切按预期工作。

## <a name="use-the-ip-block-list"></a>使用 IP 阻止列表

如果不能使用其他选项之一来阻止发件人，则 *只有* 在连接筛选器策略中使用 IP 阻止列表。 有关详细信息，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。 一定要将阻止的 Ip 的数量保持为最小值，以便 *不* 建议阻止整个 IP 地址范围。

您应该 *特别* 避免添加属于消费服务 (的 IP 地址范围，例如 outlook.com) 或共享基础结构，还应确保在定期维护过程中查看阻止的 IP 地址的列表。
