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
localization_priority: Normal
search.appverid:
- MET150s
description: 管理员可以了解在 Exchange Online Protection (EOP) 中阻止入站邮件的可用和首选) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5c95b49db811807a0cb46dce5363b8ae2dbe5602
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287277"
---
# <a name="create-blocked-sender-lists-in-eop"></a>在 EOP 中创建阻止的发件人列表

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，EOP 提供了多种阻止来自不需要的发件人的电子邮件的方法。 这些选项包括 Outlook 阻止的发件人、反垃圾邮件策略中的阻止发件人列表或阻止的域列表、Exchange 邮件流规则 (也称为传输规则) 以及 IP 阻止列表 (连接筛选) 。 统一来说，你可以将这些选项视为 _阻止的发件人列表_。

阻止发件人的最佳方法因影响范围而异。 对于单个用户，正确的解决方案可能是 Outlook 阻止的发件人。 对于许多用户，其他选项之一将更合适。 以下选项按影响范围和广度进行排名。 列表从窄到宽，但请阅读 *完整* 建议的具体内容。

1. Outlook 阻止发件人 (存储在每个邮箱邮箱中的"阻止的发件人") 

2. 阻止的发件人列表或阻止的域列表 (反垃圾邮件策略) 

3. 邮件流规则

4. IP 阻止列表 (筛选) 

> [!NOTE]
> 虽然可以使用组织范围内的阻止设置来解决垃圾邮件 (漏报) ，但您还应将这些邮件提交给 Microsoft 进行分析。 使用阻止列表管理漏报会显著增加管理开销。 如果使用阻止列表来隔离错过的垃圾邮件，则需要将主题"将邮件和文件报告给 [Microsoft"](report-junk-email-messages-to-microsoft.md) 保持就绪状态。

相比之下，你还有若干选项可以始终允许来自使用安全发件人列表的特定 _来源的电子邮件_。 有关详细信息，请参阅[创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

## <a name="email-message-basics"></a>电子邮件基础知识

标准 SMTP 电子邮件由 *邮件信封* 和邮件内容组成。 邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。 邮件内容包含邮件头字段（统称为 *邮件头*）和邮件正文。 RFC 5321 中描述了邮件信封，RFC 5322 中描述了邮件头。 收件人永远不会看到实际的邮件信封，因为它由邮件传输进程生成，并且实际上不是邮件的一部分。

- 地址 (MAIL `5321.MailFrom` **FROM** 地址、P1 发件人或信封发件人) 是在邮件的 SMTP 传输中使用的电子邮件地址。 虽然发件人可以指定不同的返回路径电子邮件地址，但此电子邮件地址通常记录在邮件头 (的"返回路径"头字段中) 。  如果邮件无法传递，则它是未送达报告的收件人 (也称为 NDR 或退回邮件) 。

- 该 (也称为发件人地址或 P2 发件人) 是"发件人"头字段中的电子邮件地址，是电子邮件客户端中显示的发件人 `5322.From` 电子邮件地址。  

通常， `5321.MailFrom` 地址 `5322.From` 和地址 (人员之间的通信) 。 但是，当代表其他人发送电子邮件时，地址可能会有所不同。

EOP 中的反垃圾邮件策略中阻止的发件人列表和阻止的域列表同时检查地址 `5321.MailFrom` `5322.From` 和地址。 Outlook 阻止的发件人仅使用 `5322.From` 地址。

## <a name="use-outlook-blocked-senders"></a>使用 Outlook 阻止的发件人

当只有少量用户收到不需要的电子邮件时，用户或管理员可以将发件人电子邮件地址添加到邮箱中的阻止发件人列表中。 有关说明，请参阅 [在 Exchange Online 邮箱上配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

当用户的阻止发件人列表成功阻止邮件时 **，X-Forefront-Antispam-Report** 头字段将包含值 `SFV:BLK` 。

> [!NOTE]
> 如果不需要的邮件来自信誉良好且可识别的源中的新闻稿，则取消订阅电子邮件是阻止用户接收邮件的另一个选项。

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>使用阻止的发件人列表或阻止的域列表

当多个用户受到影响时，范围会更大，因此下一个最佳选项是在反垃圾邮件策略中阻止发件人列表或阻止的域列表。 来自列表上的发件人的邮件标记为"垃圾邮件"，并且对邮件执行为"垃圾邮件"筛选器裁定配置的操作。  有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

这些列表的最大限制为大约 1000 个条目。

## <a name="use-mail-flow-rules"></a>使用邮件流规则

如果需要阻止发送给特定用户或整个组织的邮件，可以使用邮件流规则。 邮件流规则比阻止发件人列表或阻止发件人域列表更灵活，因为它们还可以查找不需要的邮件中的关键字或其他属性。

无论用于标识邮件的条件或例外如何，您都将操作配置为将邮件的垃圾邮件可信度 (SCL) 设置为 9，这将邮件标记为高可信度 **垃圾邮件**。 有关详细信息，请参阅"使用[邮件流规则在邮件中设置 SCL"。](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

> [!IMPORTANT]
> 创建过于具有攻击性的规则很容易，因此，使用非常具体的条件仅标识要阻止的邮件非常重要。 此外，请务必对规则启用审核并测试规则的结果，以确保一切正常。

## <a name="use-the-ip-block-list"></a>使用 IP 阻止列表

当无法使用其他选项之一阻止发件人时，只有在连接筛选器策略中才应该使用 IP 阻止列表。 有关详细信息，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。 将阻止的 IP 数保持在最少，这一点很重要，因此不建议阻止整个 IP *地址范围。*

您尤其应避免添加属于使用者服务的 IP 地址范围 (例如 outlook.com) 或共享基础结构，还要确保在定期维护时查看阻止的 IP 地址列表。
