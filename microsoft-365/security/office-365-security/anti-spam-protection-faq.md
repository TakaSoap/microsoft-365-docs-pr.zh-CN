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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以在 Exchange Online Protection (EOP) 中查看有关反垃圾邮件保护的常见问题和解答。
ms.openlocfilehash: d2505eea572e512b306cf26c7a57d1dc1b705c0b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844460"
---
# <a name="anti-spam-protection-faq"></a>反垃圾邮件保护常见问题解答

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


本主题提供了有关使用 Exchange Online 中的邮箱的 Microsoft 365 组织的反恶意软件保护的常见问题和解答，或者独立 Exchange Online Protection (EOP) 组织（没有 Exchange Online 邮箱）。

有关隔离的问题和解答，请参阅[隔离常见问题解答](quarantine-faq.md)。

有关反恶意软件保护的问题和解答，请参阅 [反恶意软件保护常见问题解答](anti-malware-protection-faq-eop.md)。

有关反欺骗保护的问题和解答，请参阅 [反欺骗保护常见问题解答](anti-spoofing-protection-faq.md)。

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>默认情况下，检测到垃圾邮件会发生什么情况？

**对于入站邮件：** 大多数垃圾邮件是通过连接筛选删除的，后者基于源电子邮件服务器的 IP 地址。 反垃圾邮件策略 (也称为垃圾邮件筛选器策略或内容筛选器策略) 将邮件作为垃圾邮件、批量或网络钓鱼检查和分类。 默认情况下，归为垃圾邮件或批量的邮件将被传递到收件人的 "垃圾邮件" 文件夹中，而分类为 "仿冒" 的邮件将被隔离。 您可以修改 (适用于所有收件人) 的默认反垃圾邮件策略，也可以为特定用户组创建具有更严格设置的自定义反垃圾邮件策略 (例如，可以隔离发送给行政主管) 的垃圾邮件。 有关详细信息，请参阅 [配置反垃圾邮件策略](configure-your-spam-filter-policies.md) 和 [建议的反垃圾邮件策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。

> [!IMPORTANT]
> 在 EOP 保护本地邮箱的混合部署中，需要在内部部署 Exchange 组织中配置两个 Exchange 邮件流规则 (也称为传输规则) ，以检测添加到邮件中的 EOP 垃圾邮件筛选标头。 有关详细信息，请参阅[在混合环境中将独立 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

 **对于出站邮件：** 邮件通过 [高风险传递池](high-risk-delivery-pool-for-outbound-messages.md) 进行路由，或返回到未送达报告中的发件人 (也称为 "NDR" 或 "退回邮件") 。 有关出站垃圾邮件保护的详细信息，请参阅 [出站垃圾邮件控制](outbound-spam-controls.md)。

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>什么是零天垃圾邮件变种以及服务如何处理？

零天垃圾邮件变种是指第一代未知的垃圾邮件，即从未捕获或分析的垃圾邮件，因此我们的反垃圾邮件筛选器还没有可用于检测到它的任何信息。 由垃圾邮件分析员捕获并分析零天的垃圾邮件示例后，如果它符合垃圾邮件分类标准，我们的反垃圾邮件筛选器将进行更新以检测它，并且不再被视为 "零天"。

**注意：** 如果您收到一封电子邮件，该邮件可能是零天垃圾邮件变种，为了帮助我们改进服务，请使用 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)中所述的方法之一将邮件提交给 microsoft。

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>我是否需要将服务配置为提供反垃圾邮件保护？

注册服务并添加域后，垃圾邮件筛选功能将自动启用。 默认情况下，将对垃圾邮件筛选进行调整，以保护您无需任何其他配置 (，而无需任何其他配置在混合环境) 中的独立 EOP 独立客户的之前提到的例外。 作为管理员，您可以编辑默认垃圾邮件筛选设置，以最大限度地满足组织的需求。 为了获得更多的粒度，您还可以创建应用于组织中的指定用户、组或域的反垃圾邮件策略和出站反垃圾邮件策略。 虽然自定义策略的优先级始终高于默认策略，但可以更改自定义策略的优先级（即运行顺序）。

有关详细信息，请参阅下列主题：

[EOP 和 Microsoft Defender for Office 365 安全性的建议设置](recommended-settings-for-eop-and-office365-atp.md)

[在 EOP 中配置连接筛选](configure-the-connection-filter-policy.md)

[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)

[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>如果我对反垃圾邮件策略进行了更改，则保存所做的更改后需要多长时间才能生效？

可能需要长达1小时才能使更改生效。

## <a name="is-bulk-email-filtering-automatically-enabled"></a>批量电子邮件筛选是否自动启用？

是。 有关批量电子邮件的详细信息，请参阅 [垃圾邮件和批量电子邮件之间有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)。

## <a name="does-the-service-provide-url-filtering"></a>该服务是否提供 URL 筛选？

是的，该服务有一个 URL 筛选器，用于检查邮件中的 Url。 如果检测到与已知垃圾邮件或恶意内容相关联的 Url，则邮件将被标记为垃圾邮件。

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>使用服务的客户如何才能向 Microsoft 发送假负 (垃圾邮件) 和误报 (非垃圾邮件) 邮件？

可以通过几种方式将垃圾邮件和非垃圾邮件提交给 Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="can-i-get-spam-reports"></a>我是否可以获取垃圾邮件报告？

是的，例如，您可以在 Microsoft 365 管理中心中获取垃圾邮件检测报告。 此报告将垃圾邮件数量显示为唯一邮件的计数。 有关报告的详细信息，请参阅以下链接：

Exchange Online 客户： [Exchange online 中的监视、报告和邮件跟踪](https://docs.microsoft.com/exchange/monitoring/monitoring)

独立 EOP 客户： [在 Exchange Online Protection 中报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>某人向我发送了一封邮件，但找不到它。 我怀疑可能已将其检测为垃圾邮件。 是否有可用于查找的工具？

是的，通过邮件跟踪工具，您可以在电子邮件通过服务时进行跟踪，以找出他们遇到的问题。 若要详细了解如何使用邮件跟踪工具来找出邮件被标记为垃圾邮件的原因，请参阅 [是否已将邮件标记为垃圾邮件？](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>如果我的用户发送出站垃圾邮件，服务限制 (速率是否限制) 我的邮件？

如果在特定时间段内通过服务从用户发送的邮件超过一半 (例如，每小时) ，则会将该用户的 EOP 被阻止发送邮件。 在大多数情况下，如果将出站邮件确定为垃圾邮件，则会通过高风险传递池路由此邮件，这会降低将正常的出站 IP 池添加到阻止列表的可能性。

当发件人被阻止发送出站垃圾邮件时，您可以发送通知到一个特定的电子邮件地址。 有关此设置的详细信息，请参阅[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)。

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>是否可以将第三方反垃圾邮件和反恶意软件提供程序与 Exchange Online 结合使用？

是。 尽管我们建议您将 MX 记录指向 Microsoft，但我们意识到有合法的商业原因将电子邮件路由到 Microsoft 之前的某个位置。

- **入站** ：更改您的 MX 记录以指向第三方提供程序，然后将邮件重定向到 EOP 以进行其他处理。 有关详细信息，请参阅 [针对 Exchange Online 中的连接器增强筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- **出站** ：配置从 Microsoft 365 到目标第三方提供程序的智能主机路由。

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>Microsoft 是否拥有任何有关如何保护自己免受网络钓鱼诈骗之害的文档？

是。 有关详细信息，请参阅 [在 internet 上保护你的隐私](https://support.microsoft.com/help/4091455)

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>垃圾邮件和恶意软件邮件是由谁发送或转移到执法部门进行调查的？

该服务侧重于垃圾邮件和恶意软件检测和删除，尽管我们有时可能会调查垃圾邮件或受攻击的垃圾邮件或攻击活动并争取 perpetrators。 这可能包括与我们的法律和数字犯罪部门协作，以阻止垃圾邮件制造者僵尸网络，阻止垃圾邮件制造者使用服务 (如果他们正在使用它发送出站电子邮件) ，并将有关法律实施的信息传递给法律实施部门进行刑事起诉。

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>可确保传递邮件的最佳出站邮件实践是什么？

下面提供的准则是发送出站电子邮件的最佳实践。

- **源电子邮件域应在 DNS 中解析。**

  例如，如果发件人是 user@fabrikam 的，则域 fabrikam 解析为 IP 地址192.0.43.10。
  
  如果发送域在 DNS 中没有 A 记录和 MX 记录，则无论邮件内容是否为垃圾邮件，服务都将会通过高风险传送池路由邮件。 有关更高风险传递池的详细信息，请参阅 [出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)。

- **出站邮件 eserver 应具有反向 DNS (PTR) 条目。**

  例如，如果电子邮件源 IP 地址为192.0.43.10，则反向 DNS 条目为 `43-10.any.icann.org` 。

- **HELO/EHLO 和 MAIL FROM 命令需要保持一致，并且不是以 IP 地址形式呈现，而是以域名形式呈现。**

  HELO/EHLO 命令需要配置成与发送 IP 地址的反向 DNS 相匹配，使域在邮件头的各个部分保持相同。

- **确保在 DNS 中设置了正确的 SPF。**

  SPF 记录是一种机制，用于验证从域发出的邮件是否确实来自域并且不带有欺骗性质。 有关 SPF 记录的详细信息，请参阅下列链接：

  [设置 SPF 以防欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

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

  > 该邮件由 sender@fabrikam.com 发送给 example@contoso.com。 更新配置文件/电子邮件地址 |即时删除 with **SafeUnsubscribe** &trade; |隐私策略

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

  在生成传递状态通知邮件时 (也称为未送达报告、Ndr 或弹跳邮件) ，发件人应遵循 [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt)中指定的弹跳格式。

- **清除退回的不存在用户的电子邮件地址。**

  如果您接收到一个指示不再使用某电子邮件地址的 NDR，请从列表中清除不存在的电子邮件别名。 电子邮件地址会随时间发生变化，大家有时会丢弃这些地址。

- **使用 Hotmail 的智能网络数据服务 (SNDS) 程序。**

  Hotmail 使用名为智能网络数据服务的程序，使发件人可以检查最终用户提交的抱怨。 SNDS 是疑难解答 Hotmail 传送问题的初始门户。
