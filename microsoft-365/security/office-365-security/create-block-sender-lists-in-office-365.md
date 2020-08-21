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
description: 管理员可以了解在创建 EOP 域中阻止入站邮件的可用 (选项) 。
ms.openlocfilehash: 9b676f96ccdff8be1fa49841a9e0ce44bb59964c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827309"
---
# <a name="create-blocked-sender-lists-in-eop"></a>在 EOP 中创建阻止发件人列表

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 提供了多种阻止来自不需要发件人的电子邮件的方法。 这些选项包括 Outlook 阻止发件人、阻止发件人列表或阻止的域名列表、Exchange 邮件流规则 (也称为传输规则) ，以及 IP 阻止列表 (连接筛选) 。 总的来说，您可以将这些选项视为 _阻止的发件人名片_。

阻止发件人的最佳方法因影响范围而异。 对于单个用户，正确的解决方案可能是 Outlook 阻止发件人。 对于许多用户来说，其他选项可能更合适。 下列选项按影响范围和大范围内的影响进行排名。 该列表从窄到广泛， *但为了提供完整建议* ，请阅读其细分。

1. Outlook 阻止 (存储在每个邮箱中的阻止发件人) 

2. 反垃圾邮件策略的阻止发件人 (阻止的) 

3. 邮件流规则

4. 连接筛选策略 (IP) 

> [!NOTE]
> 尽管您可以使用组织范围内阻止设置解决漏报问题 (报垃圾邮件) ，但您还应将这些邮件提交给 Microsoft 进行分析。 使用阻止列表管理误报将大大增加管理开销。 如果您使用阻止列表以防弃使用垃圾邮件，则需要在准备就 [绪时将主题"向 Microsoft 报告](report-junk-email-messages-to-microsoft.md) 邮件和文件"。

相比之下，您也可以通过多种选择始终允许使用安全发件人列表发送来自特定 _源的电子邮件_。 有关详细信息，请参阅[创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

## <a name="email-message-basics"></a>电子邮件消息基础知识

标准 SMTP 电子邮件由*邮件信封*和邮件内容组成。 邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。 邮件内容包含邮件头字段（统称为*邮件头*）和邮件正文。 RFC 5321 中介绍了邮件信封，RFC 5322 中介绍了邮件头。 收件人从不会看到实际邮件信封，因为它是由邮件传输进程生成的，实际上并不是邮件的一部分。

- 地址 `5321.MailFrom` (也称为 **"MAIL FROM** 地址、P1 发件人"或"信封发件人) "的电子邮件地址是邮件 SMTP 传输中使用的电子邮件地址。 通常，此电子邮件地址记录在邮件头 (中的 **"返回** 路径"标头字段中，尽管发件人可以指定不同的 **返回** 路径电子邮件地址) 。 如果邮件无法送达，则其其人是未送达报告 (的收件人，也称为 NDR 或退回) 。

- `5322.From` (也称为发件人地址**From**或 P2 发件人) 是"发件人"标头**字段**中的电子邮件地址，也是电子邮件客户端中显示的发件人电子邮件地址。

通常，与 `5321.MailFrom` 个人 `5322.From` 间的通信 (相同，这些与) 。 但是，当代表其他人发送电子邮件时，地址可能会有所不同。

EOP 中反垃圾邮件策略中的阻止发件人列表和阻止的域列表检查和 `5321.MailFrom` `5322.From` 地址。 Outlook 阻止发件人仅使用 `5322.From` 该地址。

## <a name="use-outlook-blocked-senders"></a>使用 Outlook 阻止发件人

仅少量用户收到不需要的电子邮件时，用户或管理员可以将发件人电子邮件地址添加到邮箱中"阻止的发件人"列表中。 有关说明，请参阅 [在 Exchange Online 邮箱上配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

当由于用户阻止的发件人名单而导致邮件成功阻止时 **，X-Forefront-Antispam-Report** 标头字段将包含该值 `SFV:BLK` 。

> [!NOTE]
> 如果不需要的邮件是来自可信源且可识别的新闻稿，则无法从电子邮件中取消订阅是阻止用户接收邮件的另一个选项。

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>使用阻止发件人列表或阻止的域列表

如果多个用户受到影响，作用域更广，则下一个最佳选项是阻止反垃圾邮件策略中的发件人列表或阻止的域列表。 来自列表上的发件人的邮件被标记为 **"垃圾邮件"，** 您配置的 **适用于垃圾邮件** 筛选器验证词语的操作会在邮件上执行。 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

这些列表的最大限制是大约 1000 个条目。

## <a name="use-mail-flow-rules"></a>使用邮件流规则

如果需要阻止发送到特定用户或跨整个组织的邮件，可以使用邮件流规则。 邮件流规则比阻止发件人列表或阻止发件人域列表灵活，因为它们还可以查找不需要的邮件中的关键字或其他属性。

无论使用哪种条件或例外来标识邮件，您应将操作配置为将邮件的垃圾邮件可信度 (SCL) 设置为 9，以将邮件的"**高可信度垃圾邮件"标记为"高可信度"。** 有关详细信息，请参阅"[使用邮件流规则"在邮件中设置 SCL。](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

> [!IMPORTANT]
> 创建非常周于很容易，因此*overly*务必要仅识别要使用非常具体的条件阻止的邮件。 此外，请确保启用规则审核并测试规则的结果，以确保一切按预期方式工作。

## <a name="use-the-ip-block-list"></a>使用 IP 阻止列表

如果不能使用其他选项之一阻止发件人，应 *只应* 在连接筛选器策略中使用 IP 阻止列表。 有关详细信息，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。 请务必将阻止的 IP 数数保持为最少，因此不建议阻止整个 IP *地址* 范围。

应 *特别避免* 添加属于使用者服务 (例如 outlook.com) 或共享基础架构）的 IP 地址范围，同时确保在常规维护时查看被阻止的 IP 地址的列表。
