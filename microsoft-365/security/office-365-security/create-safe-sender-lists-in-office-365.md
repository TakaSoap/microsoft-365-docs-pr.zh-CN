---
title: 创建安全发件人列表
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解在 EOP 服务中允许入站邮件的可用Exchange Online Protection (首选) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b1edcbba31075e9880b8ea2034f4ffde50bb71e9
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465720"
---
# <a name="create-safe-sender-lists-in-eop"></a>在 EOP 中创建安全发件人列表

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

如果你是在 Exchange Online 中拥有邮箱的 Microsoft 365 客户或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 客户，EOP 提供了多种方式确保用户将接收来自受信任发件人的电子邮件。 这些选项包括 Exchange 邮件流规则 (也称为传输规则) 、Outlook 保险箱 发件人、IP 允许列表 (连接筛选) 以及反垃圾邮件策略中允许的发件人列表或允许的域列表。 您一起可以将这些选项视为安全 _发件人列表_。

以下列表中介绍了可用安全发件人列表，从最推荐到最不推荐的顺序：

1. 邮件流规则
2. Outlook 保险箱发件人
3. IP 允许列表 (连接筛选) 
4. 允许的发件人列表或允许的域 (反垃圾邮件策略) 

邮件流规则允许最灵活地确保仅允许正确的邮件。 反垃圾邮件策略中允许的发件人和允许的域列表没有 IP 允许列表安全，因为发件人的电子邮件域很容易被欺骗。 但是，IP 允许列表也带来风险，因为从该 IP 地址发送的任何域的电子邮件将绕过垃圾邮件筛选。

> [!IMPORTANT]
>
> - 无论使用何种安全发件人列表选项，始终隔离标识为恶意软件或高可信度网络钓鱼的邮件。 有关详细信息，请参阅安全[默认Office 365](secure-by-default.md)。
>
> - 请务必密切监视 _使用_ 安全发件人列表对垃圾邮件筛选做出的任何例外。
>
> - 虽然您可以使用安全发件人列表帮助处理误报 (标记为错误) ，但您应考虑将安全发件人列表用作临时解决方案，如果可能，应避免使用安全发件人列表。 我们不建议使用安全发件人列表管理误报，因为垃圾邮件筛选的例外可能会让组织遭受欺骗和其他攻击。 如果您坚持使用安全发件人列表来管理误报，则需要保持谨慎，并随时将主题"向 [Microsoft](report-junk-email-messages-to-microsoft.md) 报告邮件和文件"。
>
> - 若要允许域发送未经身份验证的电子邮件 (绕过反欺骗保护) 但不绕过反垃圾邮件和其他保护，可以使用欺骗智能见解和租户允许[/阻止列表](tenant-allow-block-list.md)。[](learn-about-spoof-intelligence.md)
>
> - EOP 和 Outlook检查不同的邮件属性以确定邮件的发件人。 有关详细信息，请参阅本文稍后 [介绍的](#considerations-for-bulk-email) 批量电子邮件的注意事项部分。
>

相比之下，您还可以选择多个选项来阻止来自使用阻止发件人列表的特定 _来源的电子邮件_。 有关详细信息，请参阅[在 EOP 中创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。

## <a name="recommended-use-mail-flow-rules"></a> (推荐) 使用邮件流规则

> [!NOTE]
> 邮件头和邮件流规则不能将内部发件人指定为安全发件人。 本节中的过程仅适用于外部发件人。

邮件流规则Exchange Online和独立 EOP 中的邮件流规则使用条件和例外来标识邮件，以及用于指定应针对这些邮件执行哪些操作的操作。 有关详细信息，请参阅 mail [flow rules (transport rules) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。

以下示例假定你需要来自以下组织 contoso.com 跳过垃圾邮件筛选。 为此，请配置以下设置：

1. **条件****：发件人** \> **域 contoso.com**\>。

2. 配置以下任一设置：

   - **邮件流规则条件****：邮件头** \>  \>包含以下任何词语：邮件头 **名称：**`Authentication-Results` \> **邮件头值**： `dmarc=pass` 或 `dmarc=bestguesspass`。

     此条件会检查发送电子邮件域的电子邮件身份验证状态，以确保发送域未遭到欺骗。 有关电子邮件身份验证详细信息，请参阅 [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md) 和 [DMARC](use-dmarc-to-validate-email.md)。

   - **IP 允许列表**：在连接筛选器策略中指定源 IP 地址或地址范围。

     如果发送域不使用电子邮件身份验证，则使用此设置。 当涉及 IP 允许列表中的源 IP 地址时，请尽可能严格。 我们建议 IP 地址范围小于或小于 /24 (是更好的) 。 请勿使用属于使用者服务（例如， (或共享 outlook.com) IP 地址范围。

   > [!IMPORTANT]
   >
   > - 切勿将仅发件人 _域配置为_ 跳过垃圾邮件筛选的条件来配置邮件流规则。 这样做将显著增加攻击者欺骗发送域 (或模拟完整电子邮件地址) 、跳过所有垃圾邮件筛选并跳过发件人身份验证检查以便邮件到达收件人收件箱的可能性。
   >
   > - 请勿使用你拥有 (域，) 或热门 (，例如 microsoft.com) 规则中的条件。 这样做被视为高风险，因为它会为攻击者创造机会来发送电子邮件，否则会进行筛选。
   >
   > - 如果允许网络地址转换 (NAT) 网关后面的 IP 地址，则需要知道 NAT 池中涉及的服务器，才能知道 IP 允许列表的范围。 IP 地址和 NAT 参与者可以更改。 作为标准维护程序的一部分，您需要定期检查 IP 允许列表条目。

3. **可选条件**：
   -  \>发件人 **是内部/外部** \>**组织外部**：此条件是隐式的，但可以使用它来说明可能无法正确配置本地电子邮件服务器。
   - **主题或正文** \>**subject 或 body 包含以下任何词语** \>\<keywords\>：如果可以通过主题行或邮件正文中的关键字或短语进一步限制邮件，可以使用这些词作为条件。

4. **操作**：在规则中配置这两项操作：
   1. **修改邮件属性** \>**将垃圾邮件可信度设置为 (SCL)** \>**绕过垃圾邮件筛选**。
   2. **修改邮件属性** \>**设置邮件头****：将邮件头设置为** \<CustomHeaderName\> **值** \<CustomHeaderValue\>。

      例如，`X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`。 如果规则中具有多个域，可以根据需要自定义标头文本。

      当邮件由于邮件流 `SFV:SKN` 规则而跳过垃圾邮件筛选时，值值将标记在 **X-Forefront-Antispam-Report** 标头中。 如果邮件来自 IP 允许列表上的源，则也会添加 `IPV:CAL` 值。 这些值可以帮助你进行疑难解答。

      :::image type="content" source="../../media/1-AllowList-SkipFilteringFromContoso.png" alt-text="EAC 中用于绕过垃圾邮件筛选的邮件流规则设置" lightbox="../../media/1-AllowList-SkipFilteringFromContoso.png":::


## <a name="use-outlook-safe-senders"></a>使用Outlook 保险箱发件人

> [!CAUTION]
> 此方法会为攻击者将电子邮件成功发送到收件箱带来高风险，否则会进行筛选;但是，用户的"发件人保险箱或保险箱"列表不会阻止恶意软件或高可信度网络钓鱼邮件被筛选。

用户或管理员可以将发件人电子邮件地址添加到邮箱中的"发件人保险箱列表中，而不是组织设置。 有关说明，请参阅 [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md)。 在大多数情况下，这是不可取的，因为发件人将绕过筛选堆栈的某些部分。 尽管您信任发件人，但发件人仍然可能会遭到入侵并发送恶意内容。 最好让筛选器执行检查每封邮件所需的操作，然后在筛选器出错时向 Microsoft 报告误报 [/](report-junk-email-messages-to-microsoft.md) 负数。 绕过筛选堆栈也会干扰 [ZAP](zero-hour-auto-purge.md)。

当由于用户的 保险箱 发件人列表导致邮件跳过垃圾邮件筛选时，**X-Forefront-Antispam-Report** `SFV:SFE`头字段将包含值 ，该值指示已绕过对垃圾邮件、欺骗和网络钓鱼的筛选。

## <a name="use-the-ip-allow-list"></a>使用 IP 允许列表

如果您无法按前面所述使用邮件流规则，则下一个最佳选项是向连接筛选器策略中的 IP 允许列表添加源电子邮件服务器。 有关详细信息，请参阅在 [EOP 中配置连接筛选](configure-the-connection-filter-policy.md)。

**注意**：

- 将允许的 IP 地址数保持在最少，这一点很重要，因此尽可能避免使用整个 IP 地址范围。
- 请勿使用属于使用者服务（例如， (或共享 outlook.com) IP 地址范围。
- 定期查看 IP 允许列表中的条目并删除不再需要的条目。

> [!CAUTION]
> 如果不进行其他验证（如邮件流规则），来自 IP 允许列表中的源的电子邮件将跳过 SPF、DKIM、DMARC (垃圾邮件筛选和发件人身份验证) 检查。 这将为攻击者将电子邮件成功发送到收件箱带来高风险，否则会进行筛选;但是，IP 允许列表不会阻止对恶意软件或高可信度网络钓鱼邮件进行筛选。

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>使用允许的发件人列表或允许的域列表

最不可取的选项是在反垃圾邮件策略中使用允许的发件人列表或允许的域列表。 如果可能，应避免使用此选项，因为发件人通过 SPF、DKIM、DMARC (绕过所有垃圾邮件、欺骗和网络钓鱼) 。 此方法最好仅用于临时测试。 可以在在 [EOP 中配置反垃圾邮件策略主题中找到详细](configure-your-spam-filter-policies.md) 步骤。

这些列表的最大限制为大约 1000 个条目;但是，你只能向门户输入 30 个条目。 必须使用 PowerShell 添加 30 多个条目。

> [!CAUTION]
>
> - 此方法会为攻击者将电子邮件成功发送到收件箱带来高风险，否则会进行筛选;但是，允许的发件人或允许的域列表不会阻止对恶意软件或高可信度网络钓鱼邮件进行筛选。
>
> - 请勿使用你拥有 (的域，) 或热门 (，例如，microsoft.com) 允许的域列表中。

## <a name="considerations-for-bulk-email"></a>批量电子邮件的注意事项

标准 SMTP 电子邮件由 _邮件信封_ 和邮件内容组成。 邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。 邮件内容包含邮件头字段（统称为 _邮件头_）和邮件正文。 RFC 5321 中介绍了邮件信封，RFC 5322 中介绍了邮件头。 收件人永远不会看到实际的邮件信封，因为它是由邮件传输过程生成的，实际上并不是邮件的一部分。

- 地址 `5321.MailFrom` (**MAIL FROM** 地址、P1 发件人或信封发件人) 是在邮件的 SMTP 传输中使用的电子邮件地址。 虽然发件人可以指定不同的"返回路径"电子邮件地址，但此电子邮件地址通常记录在邮件头 (的"返回路径"标头字段中) 。 如果邮件无法传递，则它是未送达报告的收件人 (NDR 或退回邮件) 。
- The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field， and is the sender's email address that's displayed in email clients.

通常，和 `5321.MailFrom` `5322.From` 地址在个人 (通信中是相同的) 。 但是，代表其他人发送电子邮件时，地址可以不同。 这通常发生在批量电子邮件中。

例如，假设 Blue Yonder Airlines 已雇用 Margie 的 Travel 发送其电子邮件广告。 在收件箱中收到的邮件具有以下属性：

- 地址 `5321.MailFrom` 为 blueyonder.airlines@margiestravel.com。
- 地址`5322.From`是 blueyonder@news.blueyonderairlines.com，你将在邮件中Outlook。

保险箱 EOP `5322.From` 中的反垃圾邮件策略中的发件人列表和安全域列表仅检查这些地址，这Outlook 保险箱地址的发件人`5322.From`类似。

若要阻止筛选此邮件，可以执行以下步骤：

- 添加 blueyonder@news.blueyonderairlines.com (发件人`5322.From`) 地址Outlook 保险箱地址。
- [将邮件流规则](#recommended-use-mail-flow-rules) 与 `5322.From` `5321.MailFrom` 以下条件一同使用：从 blueyonder@news.blueyonderairlines.com (、blueyonder.airlines@margiestravel.com (或) 的邮件。
