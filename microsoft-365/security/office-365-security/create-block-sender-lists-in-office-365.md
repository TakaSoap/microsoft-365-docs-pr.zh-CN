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
ms.localizationpriority: medium
search.appverid:
- MET150s
description: 管理员可以了解在 EOP 服务中阻止入站邮件的Exchange Online Protection (首选) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 051926aa3232efb1913fdbf0a2d7022e99bab0f1
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61937492"
---
# <a name="create-blocked-sender-lists-in-eop"></a>在 EOP 中创建阻止的发件人列表

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在Microsoft 365邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中Exchange Online，EOP 提供了多种阻止来自不需要的发件人的电子邮件的方法。 这些选项包括Outlook垃圾邮件策略中的阻止发件人、阻止的发件人列表或阻止的域列表、Exchange 邮件流规则 (也称为传输规则) 以及 IP 阻止列表 (连接筛选) 。 您一起可以将这些选项视为 _阻止的发件人列表_。

阻止发件人的最佳方法因影响范围而异。 对于单个用户，正确的解决方案可能是Outlook发件人。 对于许多用户，其他选项之一更为合适。 以下选项按影响范围和广度进行排名。 该列表从窄到宽，但请阅读具体 *内容* ，了解完整建议。

1. Outlook每个邮箱 (中存储的"阻止的发件人"列表中的"阻止的发件人) 

2. 阻止的发件人列表或阻止的域 (反垃圾邮件策略) 

3. 邮件流规则

4. IP 阻止列表 (筛选) 

> [!NOTE]
> 虽然您可以使用组织范围的阻止设置来解决漏报垃圾邮件 (错误) ，但您还应将那些邮件提交给 Microsoft 进行分析。 使用阻止列表管理漏报会显著增加管理开销。 如果使用阻止列表来阻止错过的垃圾邮件，则需要将主题"将邮件和文件报告给 [Microsoft"](report-junk-email-messages-to-microsoft.md) 保持就绪状态。

相比之下，你还有若干选项可以始终允许来自使用安全发件人列表的特定 _来源的电子邮件_。 有关详细信息，请参阅[创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

## <a name="email-message-basics"></a>电子邮件基础知识

标准 SMTP 电子邮件由 *邮件信封* 和邮件内容组成。 邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。 邮件内容包含邮件头字段（统称为 *邮件头*）和邮件正文。 RFC 5321 中介绍了邮件信封，RFC 5322 中介绍了邮件头。 收件人永远不会看到实际的邮件信封，因为它是由邮件传输过程生成的，实际上并不是邮件的一部分。

- `5321.MailFrom`地址 (**MAIL FROM** 地址、P1 发件人或信封发件人) 是在邮件的 SMTP 传输中使用的电子邮件地址。 虽然发件人可以指定不同的"返回路径"电子邮件地址，但此电子邮件地址通常记录在邮件头 (的 **"** 返回路径"头字段中) 。 如果邮件无法传递，则它是未送达报告的收件人 (NDR 或退回邮件) 。

- The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field， and is the sender's email address that's displayed in email clients.

通常， `5321.MailFrom` 和 `5322.From` 地址在个人 (通信之间) 。 但是，代表其他人发送电子邮件时，地址可以不同。

EOP 中的反垃圾邮件策略中阻止的发件人列表和阻止的域列表将检查 `5321.MailFrom` 和 `5322.From` 地址。 Outlook阻止的发件人仅使用 `5322.From` 地址。

## <a name="use-outlook-blocked-senders"></a>使用Outlook阻止的发件人

当只有少量用户收到不需要的电子邮件时，用户或管理员可以将发件人电子邮件地址添加到邮箱中的"阻止的发件人"列表中。 有关说明，请参阅[在邮箱上配置Exchange Online设置](configure-junk-email-settings-on-exo-mailboxes.md)。

当用户的阻止的发件人名单成功阻止邮件时 **，X-Forefront-Antispam-Report** 头字段将包含值 `SFV:BLK` 。

> [!NOTE]
> 如果不需要的邮件来自信誉良好且可识别的来源，则取消订阅电子邮件是阻止用户接收邮件的另一个选项。

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>使用阻止的发件人列表或阻止的域列表

当多个用户受到影响时，范围会更大，因此反垃圾邮件策略中的下一个最佳选项是阻止发件人列表或阻止的域列表。 来自列表上发件人的邮件标记为 **"高** 可信度垃圾邮件"，并且对邮件执行为"高可信度垃圾邮件筛选器"裁定配置的操作。 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

这些列表的最大限制为大约 1000 个条目。

## <a name="use-mail-flow-rules"></a>使用邮件流规则

如果需要阻止发送给特定用户或整个组织的邮件，可以使用邮件流规则。 邮件流规则比阻止发件人列表或阻止发件人域列表更灵活，因为它们还可以在不需要的邮件中查找关键字或其他属性。

不论您用于标识邮件的条件或例外如何，您都将操作配置为将邮件的垃圾邮件可信度 (SCL) 设置为 9，从而将邮件标记为高 **可信度垃圾邮件**。 有关详细信息，请参阅使用[邮件流规则设置邮件中的 SCL。](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)

> [!IMPORTANT]
> 创建过度攻击的规则很容易，因此，使用非常具体的条件仅标识要阻止的邮件非常重要。 此外，请务必对规则启用审核并测试规则结果，以确保一切正常。

## <a name="use-the-ip-block-list"></a>使用 IP 阻止列表

当无法使用其他选项之一阻止发件人时，只有在连接筛选器策略中才应该使用 IP 阻止列表。 有关详细信息，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。 将阻止的 IP 数量保持在最少很重要，因此不建议阻止整个 IP *地址范围。*

您尤其应避免添加属于消费者服务 (（例如 outlook.com) 或共享基础结构）的 IP 地址范围，并确保在常规维护中查看阻止的 IP 地址列表。
