---
title: 反垃圾邮件保护常见问题解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以在 Exchange Online Protection 邮箱中查看有关反垃圾邮件保护的常见问题 (解) 。
ms.openlocfilehash: ed871990cf5f8fc4e15995987312fc6814ab8296
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825169"
---
# <a name="anti-spam-protection-faq"></a>反垃圾邮件保护常见问题解答

本主题提供了有关 Exchange Online 邮箱的 Microsoft 365 组织的反恶意软件保护或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织的反恶意软件保护的常见问题和解答。

有关隔离的问题和解答，请参阅[隔离常见问题解答](quarantine-faq.md)。

有关反恶意软件保护的问题和解答，请参阅"[反恶意软件保护常见问题解答"。](anti-malware-protection-faq-eop.md)

有关反欺骗保护的问题和解答，请参阅反 [欺骗保护常见问题解答](anti-spoofing-protection-faq.md)。

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>默认情况下，检测到垃圾邮件的邮件会发生什么情况？

**对于入站邮件：** 大部分垃圾邮件都是通过基于源电子邮件服务器的 IP 地址的连接筛选删除的。 反垃圾邮件策略 (也称为垃圾邮件筛选策略或内容筛选策略，) 邮件检查并被分类为垃圾邮件、批量或网络钓鱼。 默认情况下，分类为垃圾邮件或批量邮件的邮件会传递到收件人的垃圾邮件文件夹，同时将隔离分类为网络钓鱼的邮件。 可以修改默认的反垃圾邮件策略 (所有收件人) ，或为特定用户组创建具有更严格设置的自定义反垃圾邮件 (策略，例如，可以隔离发送到高管) 的垃圾邮件。 有关详细信息，请参阅配置反[垃圾邮件策略和建议](configure-your-spam-filter-policies.md)[的反垃圾邮件策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。

> [!IMPORTANT]
> 在 EOP 保护本地邮箱的混合部署中，需要在本地 Exchange 组织中配置两个 Exchange 邮件流规则 (（也称为传输规则) ）来检测添加到邮件的 EOP 垃圾邮件筛选头。 有关详细信息，请参阅[在混合环境中将独立 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

 **对于出站邮件：** 邮件要通过高风险传送池进行路由[high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md)，或者返回到未送达报告 (也称为 NDR 或退回邮件传送邮件的) 。 有关出站垃圾邮件保护的详细信息，请参阅出 [站垃圾邮件控制](outbound-spam-controls.md)。

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>什么是零日垃圾邮件变体，该服务将如何处理它？

在我们的反垃圾邮件分析中，我们的反垃圾邮件筛选器尚未提供任何信息进行检测，这是第一代、以前未知的垃圾邮件变体，因此我们的反垃圾邮件筛选器对其没有任何检测信息。 （注意： 如果您收到一个包含一个零日垃圾邮件的邮件，为了帮助我们改进服务，请使用以下方法进行分析：

**注意：** 如果收到一封可能是零日垃圾邮件变体的邮件，为了帮助我们改进服务，请使用"向 Microsoft 报告邮件和文件"中所述[的方法之一将邮件提交给 Microsoft。](report-junk-email-messages-to-microsoft.md)

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>我是否需要配置该服务来提供反垃圾邮件保护？

注册服务并添加域之后，将自动启用垃圾邮件筛选功能。 默认情况下，扫描垃圾邮件筛选以保护您，除混合环境中独立 EOP 独立客户外的其他配置 (除外) 。 作为管理员，你可以编辑默认垃圾邮件筛选设置，以最好满足组织需求。 您还可以创建反垃圾邮件策略以及应用于组织中特定用户、组或域的出站反垃圾邮件策略。 虽然自定义策略的优先级始终高于默认策略，但可以更改自定义策略的优先级（即运行顺序）。

有关详细信息，请参阅下列主题：

[EOP 和 Office 365 ATP 安全的建议设置](recommended-settings-for-eop-and-office365-atp.md)

[在 EOP 中配置连接筛选](configure-the-connection-filter-policy.md)

[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)

[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>如果我对一个反垃圾邮件策略进行了更改，更改保存之后需要多长时间才能生效？

可能需要 1 小时，更改才能生效。

## <a name="is-bulk-email-filtering-automatically-enabled"></a>批量电子邮件筛选是否已自动启用？

是。 有关批量电子邮件的详细信息，请参阅垃圾邮件和批量邮件[之间有什么差异？](what-s-the-difference-between-junk-email-and-bulk-email.md)

## <a name="does-the-service-provide-url-filtering"></a>此服务是否提供 URL 筛选？

可以，该服务具有可检查邮件中的 URL 的 URL 筛选器。 如果检测到与已知垃圾邮件或恶意内容相关联的 URL，则将该邮件标记为垃圾邮件。

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>如何使用此服务服务的客户将非垃圾邮件 (误) 报问题和非垃圾邮件 () 给 Microsoft？

可以通过几种方式将垃圾邮件和非垃圾邮件提交给 Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="can-i-get-spam-reports"></a>我可以获取垃圾邮件报告吗？

例如，您可以在 Microsoft 365 管理中心中获取垃圾邮件检测报告。 此报告将垃圾邮件卷显示为唯一邮件的计数。 有关报告的详细信息，请参阅以下链接：

Exchange Online 客户 [：Exchange Online 中的监视、报告和邮件跟踪](https://docs.microsoft.com/exchange/monitoring/monitoring)

独立 EOP 客户：Exchange [Online Protection 中的报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>某人发送一封邮件，但是我找不到它。 我会对检测到它可能被检测为垃圾邮件。 是否有了可以使用的工具来了解？

存在，邮件跟踪工具让您能够跟踪通过该服务传递的电子邮件，以了解他们发生了什么情况。 有关如何使用邮件跟踪工具找到将邮件标记为垃圾邮件的原因的详细信息，请参阅 [邮件被标记为垃圾邮件吗？](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>服务是否会限制 (出) 是否) 发送出站垃圾邮件的邮件？

如果在特定时间范围内通过服务发送的超过一半的邮件 (例如) 按小时确定为 EOP 发送垃圾邮件，则该用户将被阻止发送邮件。 在大多数情况下，如果出站邮件确定为垃圾邮件，将会通过高风险传送池进行路由，这会降低正常出站 IP 池添加到阻止列表的可能性。

当发件人被阻止发送出站垃圾邮件时，您可以发送通知到一个特定的电子邮件地址。 有关此设置的详细信息，请参阅[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)。

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>是否可以与 Exchange Online 一起使用第三方反垃圾邮件和反恶意软件提供程序？

是。 尽管我们建议将你的 MX 记录指向 Microsoft，但我们意意表示有合法的商业理由将您的电子邮件首先路由到 Microsoft 以外的地工作。

- **入站**：将您的 MX 记录更改为指向第三方提供程序，然后将邮件重定向到 EOP 以进行额外处理。 有关详细信息，请参阅 [Exchange Online 中连接器的增强筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)功能。

- **出站**：配置从 Microsoft 365 到目标第三方提供程序的智能主机路由。

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>Microsoft 是否拥有任何有关如何保护自己免受网络钓鱼诈骗之害的文档？

是。 有关详细信息，请参阅" [在 Internet 上保护你的隐私"](https://support.microsoft.com/help/4091455)

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>正在调查垃圾邮件和恶意邮件，是要将其发送到诉讼的、还是被转移到诉讼实施实体？

该服务将重点放在垃圾邮件和恶意软件检测与删除，但是我们有时可能会调查其他危险或失真的垃圾邮件或攻击活动并购买外围设备。 这可能会涉及涉及与我们的法律和数字统计单元合作，使垃圾邮件制造者通过免费的自动程序机器机密网而受到阻止，如果正在使用 (发送出站电子邮件) ，阻止其使用 (服务，并将相关信息传递至法律运算以进行致力承诺。

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>确保我的邮件已发送的一组最佳出站邮件实践是什么？

下文中介绍的这些准则是发送出站电子邮件的最佳做法。

- **源电子邮件域应在 DNS 中解析。**

  例如，如果发件人为 user@fabrikam，则 fabrikam 域将解析为 IP 地址 192.0.43.10。
  
  如果发送域在 DNS 中没有 A 记录和 MX 记录，则无论邮件内容是否为垃圾邮件，服务都将会通过高风险传送池路由邮件。 有关高风险传送池的详细信息，请参阅 [出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)。

- **出站邮件电子邮件服务器应具有一个反向 DNS (PTR) 条目。**

  例如，如果电子邮件源 IP 地址是 192.0.43.10，则反向 DNS 条目将 `43-10.any.icann.org` 为 .'

- **HELO/EHLO 和 MAIL FROM 命令需要保持一致，并且不是以 IP 地址形式呈现，而是以域名形式呈现。**

  HELO/EHLO 命令需要配置成与发送 IP 地址的反向 DNS 相匹配，使域在邮件头的各个部分保持相同。

- **确保在 DNS 中设置了正确的 SPF。**

  SPF 记录是一种机制，用于验证从域发出的邮件是否确实来自域并且不带有欺骗性质。 有关 SPF 记录的详细信息，请参阅下列链接：

  [设置 SPF 以帮助防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [关于域的常见问题](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- **使用 DKIM 对电子邮件签名，用较宽松的规范签名。**

  如果发件人希望使用域名密钥识别邮件标准 (DKIM) 对邮件签名，并想通过服务发送出站电子邮件，需要使用较宽松的标头规范化算法签名。 用严格的标头规范签名可能导致签名通过服务时变得无效。

- **域所有者在 WHOIS 数据库中需要有正确的信息。**

  这标识了域所有者以及如何通过稳定的父公司、联系点和名称服务器联系他们。

- **对于邮件群发程序，发件人： 名字需要反映发送邮件的人，而邮件的主题行应该是对邮件内容的简短摘要。**

  邮件正文应该对提供内容、服务或产品有一个清楚的说明。 例如，如果发件人为 Contoso 公司发送一个群发邮件，电子邮件的"发件人"以及"主题"应与以下内容类似：

  > 发件人： marketing@contoso.com <br/> 主题： 圣诞季的新更新目录！

  以下是不能执行的操作的一个示例，因为该示例是非描述性的：

  > 发件人： user@hotmail.com <br/> 主题： 目录

- **如果将群发邮件发送给很多个收件人，并且邮件是新闻稿的格式，那么在邮件底部应该存在取消订阅的方法。**

  取消订阅的选项应该与以下内容相似：

  > 该邮件由 sender@fabrikam.com 发送给 example@contoso.com。 更新配置文件/电子邮件地址 |通过**SafeUnsubscribe 即时删除** &trade; |隐私策略

- **如果发送群发邮件，需使用双重选择执行列表获取。如果您是一个邮件群发者，双重选择是行业的最佳做法。**

  双重加入是要求用户采取以下两种操作注册市场邮件的做法。

  1. 第一次在用户单击一个之前未选中的复选框（其中他们选择接收营销人员发送的其他促销或电子邮件）时选择。

  2. 第二次在营销人员向用户提供的电子邮件地址发送确认邮件，要求用户在时间敏感型链接上单击时选择。

  使用双重选择为群发邮件发件人构建良好的信誉。

- **群发邮件发件人应创建透明内容，以便他们负起责任：**

  1. 收件人将发件人添加到通讯簿上的冗长请求应清楚地表明这些操作无法保证邮件传送的安全性。

  2. 当在邮件正文构建重定向时，使用一致的链接样式。

  3. 请不要发送大容量图片或附件，或仅含一张图片的邮件。

  4. 当采用跟踪像素（网络臭虫或信号），清楚地说明公开隐私或 P3P 设置。

- **设置出站退回邮件的格式。**

  当生成送达状态通知消息 (也称为未送达报告、NDR 或退回邮件) 时，发件人应按照 [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt)中指定的退回格式。

- **清除退回的不存在用户的电子邮件地址。**

  如果您接收到一个指示不再使用某电子邮件地址的 NDR，请从列表中清除不存在的电子邮件别名。 电子邮件地址会随时间发生变化，大家有时会丢弃这些地址。

- **使用 Hotmail 的智能网络数据服务 (SNDS) 程序。**

  Hotmail 使用名为智能网络数据服务的程序，使发件人可以检查最终用户提交的抱怨。 SNDS 是疑难解答 Hotmail 传送问题的初始门户。
