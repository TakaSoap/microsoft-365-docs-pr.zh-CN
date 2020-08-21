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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解在 Exchange Online Protection 和 EOP 应用程序中允许入站邮件的可用 () 选项。
ms.openlocfilehash: f182027b153ee73e33131b39066e512c9303fcbd
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827107"
---
# <a name="create-safe-sender-lists-in-eop"></a>在 EOP 中创建安全发件人列表

如果你是具有 Exchange Online 邮箱的 Microsoft 365 客户，或者没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 客户，EOP 提供了多种方法来确保用户将收到来自受信任发件人的邮件。 这些选项包括 Exchange 邮件流规则 (也称为传输规则) 、Outlook 安全发件人、IP 允许列表 (连接筛选) ，以及反垃圾邮件策略中的允许发件人列表或允许的域列表。 总的来说，可以将这些选项视为安全 _发件人列表_。

以下列表中的可用安全发件人列表按建议从推荐最不推荐到最不推荐的顺序进行介绍：

1. 邮件流规则
2. Outlook 安全发件人
3. IP 允许 (筛选) 
4. 反垃圾邮件策略的允许发件人列表或允许的 (域) 

邮件流规则使灵活性最高的可确保只允许正确的邮件。 反垃圾邮件策略中的允许发件人和允许的域列表不如 IP 允许列表一起使用，因为发件人的电子邮件域易受到欺骗性的原因。 但是，IP 允许列表还会带来风险，因为来自任何域_any_并来自该 IP 地址的电子邮件都将不进行垃圾邮件筛选。

> [!IMPORTANT]
>
> - 请注意，应使用安全发件人列表 *密* 大监控垃圾邮件筛选的异常。
>
> - 虽然可以使用安全发件人列表来帮助 (误报 (标记为垃圾邮件) 的电子邮件，但应考虑使用安全发件人列表作为临时解决方案，应尽可能避免使用该解决方案。 我们不建议使用安全发件人列表管理误报，因为垃圾邮件筛选的例外会让您的组织将其投入欺骗和其他攻击。 如果您对使用安全发件人列表管理误报感到了解，则你必须是理智之，并且准备就绪时将主题[报告给 Microsoft。](report-junk-email-messages-to-microsoft.md)
>
> - 要允许域发送未经身份验证的电子邮件 (请绕过反欺骗保护) 而无需绕过反垃圾邮件和反恶意软件检查，您可以将其添加到 [AllowedToSpoof 安全发件人列表](walkthrough-spoof-intelligence-insight.md)
>
> - EOP 和 Outlook 检查不同的邮件属性，以确定邮件的发件人。 有关详细信息，请参阅本主题 [后面的批量电子邮件注意](#considerations-for-bulk-email) 事项部分。

相比之下，还可以通过多个选项来阻止来自使用阻止发件人列表的特定 _源的电子邮件_。 有关详细信息，请参阅[在 EOP 中创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。

## <a name="recommended-use-mail-flow-rules"></a> (建议) 使用邮件流规则

Exchange Online 和独立 EOP 中的邮件流规则使用条件和例外来标识邮件，并采取操作来指定邮件应执行的操作。 有关详细信息，请参阅 [邮件流规则 (Exchange Online) 传输规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。

以下示例假设需要电子邮件从报表中contoso.com垃圾邮件筛选跳过垃圾邮件筛选。 为此，请配置以下设置：

1. **条件**：**发件人** \> **域为contoso.com。** \>

2. 配置以下任一设置：

   - **邮件流规则条件**： **邮件头包括** \> **下列任何词头名称** \> **：** `Authentication-Results` \> **标头值**： `dmarc=pass` 或 `dmarc=bestguesspass` 。

     此条件检查发送电子邮件域的发件人身份验证状态，以确保发送域未被欺骗。 有关电子邮件身份验证的详细信息，请参阅[SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [、DKIM](use-dkim-to-validate-outbound-email.md)和[DMARC。](use-dmarc-to-validate-email.md)

   - **IP 允许列表**：指定连接筛选器策略中的源 IP 地址或地址范围。
  
     如果发送域没有身份验证，则使用此设置。 如果它是 IP 允许列表中的源 IP 地址，则尽可能具有限制性。 建议的 IP 地址范围为 /24 或更小 (更好地为) 。 请勿使用属于使用者服务（例如，工作流或 (）outlook.com) IP 地址范围。

   > [!IMPORTANT]
   >
   > - 从不将仅使用发件人域 *配置* 邮件流规则作为条件以跳过垃圾邮件筛选。 这样会 *显著提高* 攻击者可以欺骗发送域 (或模拟完整电子邮件地址) 、跳过所有垃圾邮件筛选，并跳过发件人身份验证检查，以便该邮件到达收件人的收件箱。
   >
   > - 不要使用你自己的域 (你自己的域（亦称为"接受的) 或 (受欢的microsoft.com) 例如，microsoft.com) 作为邮件流规则的条件。 这样做被视为高风险，因为它为攻击者带来了发送本来会被筛选的电子邮件的机会。
   >
   > - 如果您允许网络地址转换 (NAT) 网关之后的 IP 地址，则需要知道 NAT 池中涉及的服务器，才能知道 IP 允许列表的作用域。 IP 地址和 NAT 参与者可以更改。 作为标准维护过程的一部分，您需要定期检查 IP 允许列表条目。

3. **可选条件**：

   - **发件人** \>**为内部/外部** \>**组织外部**：此条件是隐式的，但可以用它来说明可能未正确配置的本地电子邮件服务器。

   - **主题或正文** \>**主题或正文包含以下任何词语** \>\<keywords\>：如果可以在主题行或邮件正文中按关键字或短语进一步限制邮件，则可以使用这些词作为条件。

4. **操作**：在该规则中配置以下两项操作：

   a. **修改邮件属性** \>**设置 SCL 外部 (可信度) ** \>**绕过垃圾邮件筛选**。

   b. **邮件头** \>**包含以下任何词语** \>**标头名称**： \<CustomHeaderName\> **标头值** \<CustomHeaderValue\> ：.

      例如，`X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`。 如果规则中有多个域，您可以根据需要自定义头文本。

      当邮件由于邮件流规则而跳过垃圾邮件筛选时，会在 `SFV:SKN` **X-Forefront-Antispam-Report 标头中标记该值** 。 如果邮件来自 IP 允许列表上的源，则也会 `IPV:CAL` 添加该值。 这些值可帮助进行疑难解答。

![将不传递垃圾邮件筛选的 EAC 中的邮件流规则设置。](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>使用 Outlook 安全发件人

用户或管理员可以将发件人电子邮件地址添加到邮箱的"安全发件人"列表中，而不是组织设置。 有关说明，请参阅在 [Office 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。 在大多数情况下都不需要这样的操作，因为发件人将绕过筛选堆栈的一部分。 虽然您信任发件人，但发件人仍会受到安全影响，并可能发送恶意内容。 最好让筛选器执行检查每封邮件所需的操作，如果筛选器出问题，则会向 [Microsoft](report-junk-email-messages-to-microsoft.md) 报告误报/否。 绕过筛选堆栈也会干扰[ZAP。](zero-hour-auto-purge.md)

如果邮件由于用户的安全发件人列表，导致邮件跳过垃圾邮件筛选 **，X-Forefront-Antispam-Report** 标头字段将包含值，该值指示已绕过垃圾邮件、欺骗和网络钓 `SFV:SFE` 鱼筛选。

## <a name="use-the-ip-allow-list"></a>使用 IP 允许列表

如果无法按上文所述使用邮件流规则，下一个最佳选择是将源电子邮件服务器添加到连接筛选器策略中的 IP 允许列表。 有关详细信息，请参阅 [在 EOP 中配置连接筛选](configure-the-connection-filter-policy.md)。

**注意**：

- 请务必将允许的 IP 地址数保持在最少数，因此尽可能避免使用整个 IP 地址范围。

- 请勿使用属于使用者服务（例如，工作流或 (）outlook.com) IP 地址范围。

- 定期查看 IP 允许列表中的条目并删除不再需要的条目。

> [!CAUTION]
> 无需像邮件流规则一样执行其他验证，来自 IP 允许列表中的来源的电子邮件将跳过垃圾邮件筛选和发件人 (SPF、DKIM、DMARC) 检查。 这会造为攻击者成功将电子邮件传递到收件箱（否则会进行筛选）带来高风险。

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>使用允许发件人列表或允许的域列表

最不希望的选择是使用反垃圾邮件策略中包含的允许发件人列表或允许的域列表。 只应尽可能 *避免此选项，* 因为发件人绕过所有垃圾邮件、欺骗和网络钓鱼保护，以及发件人 (SPF、DKIM 和 DMARC) 。 此方法最适合仅用于临时测试。 详细步骤可以在 EOP 中" [配置反垃圾邮件策略"](configure-your-spam-filter-policies.md) 主题中找到。

这些列表的最大限制是大约 1000 个条目;虽然您只能在门户中输入 30 个条目。 必须使用 PowerShell 添加超过 30 个条目。

> [!CAUTION]
>
> - 此方法可使攻击者将电子邮件成功送达到收件箱（否则会进行筛选）带来高风险。
>
> - 请勿使用你自己的域 (你自己的接受域) 或受（ (例如，microsoft.com) 允许的域列表中）。

## <a name="considerations-for-bulk-email"></a>批量电子邮件的注意事项

标准 SMTP 电子邮件由*邮件信封*和邮件内容组成。 邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。 邮件内容包含邮件头字段（统称为*邮件头*）和邮件正文。 RFC 5321 中介绍了邮件信封，RFC 5322 中介绍了邮件头。 收件人从不会看到实际邮件信封，因为它是由邮件传输进程生成的，实际上并不是邮件的一部分。

- 地址 `5321.MailFrom` (也称为 **"MAIL FROM** 地址、P1 发件人"或"信封发件人) "的电子邮件地址是邮件 SMTP 传输中使用的电子邮件地址。 通常，此电子邮件地址记录在邮件头 (中的 **"返回** 路径"标头字段中，尽管发件人可以指定不同的 **返回** 路径电子邮件地址) 。 如果邮件无法送达，则其其人是未送达报告 (的收件人，也称为 NDR 或退回) 。

- `5322.From` (也称为发件人地址**From**或 P2 发件人) 是 **"发件人"标头字段**中的电子邮件地址，也是电子邮件客户端中显示的发件人电子邮件地址。

通常，与 `5321.MailFrom` 个人 `5322.From` 间的通信 (相同) ， 但是，当代表其他人发送电子邮件时，地址可能会有所不同。 这是批量电子邮件最常造的情况。

例如，假设 Blue Yonder Airlines 已采用百分之一流，可以发送电子邮件广告。 在收件箱中收到的邮件包含以下属性：

- 地址 `5321.MailFrom` 不是blueyonder.airlines@margiestravel.com。

- 地址 `5322.From` 是blueyonder@news.blueyonderairlines.com显示的，你将在 Outlook 中看到该地址。

EOP 中反垃圾邮件策略中的安全发件人列表和安全域列表仅检查 `5322.From` 这些地址，这类似于使用该地址的 Outlook 安全 `5322.From` 发件人。

若要防止对此邮件进行筛选，可以执行以下步骤：

- 将blueyonder@news.blueyonderairlines.com (`5322.From` 地址) 为 Outlook 安全发件人。

- [Use a mail flow rule](#recommended-use-mail-flow-rules) with a condition that looks for messages from blueyonder@news.blueyonderairlines.com (the `5322.From` address, blueyonder.airlines@margiestravel.com (the `5321.MailFrom`) , or both.

有关详细信息，请参阅"[在 EOP 中创建安全发件人列表"。](create-safe-sender-lists-in-office-365.md)
