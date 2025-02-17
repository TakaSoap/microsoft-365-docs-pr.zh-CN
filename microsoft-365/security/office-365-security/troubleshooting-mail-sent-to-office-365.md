---
title: 有关发送到 Microsoft 365 的邮件的疑难解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 本文提供有关将电子邮件发送到收件箱的问题的疑难解答信息，Microsoft 365 &客户进行批量邮件Microsoft 365最佳实践。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f5fe128989b66f110899e6af08180e830319b739
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61121395"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a>有关发送到 Microsoft 365 的邮件的疑难解答

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)

本文提供有关发件人在尝试向 Microsoft 365 中的收件箱发送电子邮件时遇到问题的发件人的疑难解答信息，以及批量发邮件给客户的最佳实践。

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>您是否正在管理您的 IP 和域的发送信誉？

EOP 筛选技术旨在为电子邮件和其他 Microsoft 产品Microsoft 365反垃圾邮件Exchange Server。 我们还使用 SPF、DKIM 和 DMARC;电子邮件身份验证技术，通过验证发送电子邮件的域是否有权这样做，帮助解决欺骗和网络钓鱼问题。 EOP 筛选受许多与发送 IP、域、身份验证、列表准确性、投诉率、内容等相关的因素影响。 其中，拉低发件人信誉和传送电子邮件能力的关键因素之一是他们的垃圾邮件投诉率。

## <a name="are-you-sending-email-from-new-ip-addresses"></a>您是否正从新的 IP 地址发送电子邮件？

如果您之前没有使用这个 IP 地址发送电子邮件，那么通常在我们的系统里不会为其建立任何信誉。因此，来自新 IP 的电子邮件更有可能遇到传送问题。一旦 IP 建立了非发送垃圾邮件的信誉，EOP 通常会允许更好的电子邮件传送体验。

添加到域（在现有 SPF 记录下验证的）的新 IP 通常继承了一些域的发送信誉的额外优势。如果您的域有良好的发送信誉，那么新 IP 可能会有更快的加速时间体验。一个新的 IP 可以在几周内或更快的时间内完全加速，这取决于容量、列表精度和垃圾邮件投诉率。

## <a name="confirm-that-your-dns-is-set-up-correctly"></a>确认您的 DNS 设置正确

有关如何创建和维护 DNS 记录的说明，包括邮件路由所需的 MX 记录，您将需要联系您的 DNS 托管提供者。

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>确保您没有将自己标识为不可路由的 IP

我们可能不接受来自反向 DNS 查找失败的发件人的电子邮件。在某些情况下，当合法发件人在尝试打开一个 EOP 的连接时，他们错误地将自己标识为非面向 Internet 的可路由的 IP。为专用（不可路由的）网保留的 IP 地址包括：

- 192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)
- 10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)
- 172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>在邮件中向用户 (NDR) 未送达报告Office 365

出现一些传送问题是因为发件人的 IP 地址被 Microsoft 阻止或用户账户由于以前的垃圾邮件活动被标识为已禁止的发件人。如果您认为您错误地收到了 NDR，首先按照在 NDR 邮件中解决此问题的说明进行操作。

有关收到的错误的详细信息，请参阅电子邮件未送达报告中的错误代码列表[Exchange Online。](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

 例如，如果您收到以下 NDR，则表明发送 IP 地址已被 Microsoft 阻止：

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

若要请求从此列表中删除，可以使用除名门户将自己从阻止 [的发件人名单中删除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a>我的电子邮件已登陆到收件人的"垃圾邮件"文件夹

如果某封邮件被 EOP 错误地标识为垃圾邮件，您可以与收件人一起将此误报邮件提交给 Microsoft 垃圾邮件分析团队，他们将对该邮件进行评估和分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>来自我的 IP 地址的流量被 EOP 限制

如果您收到来自 EOP 的 NDR，则表明您的 IP 地址被 EOP 限制，例如：

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

您收到了 NDR，因为从 IP 地址检测出可疑活动，且该地址在接受进一步评估时已暂时受限。如果通过评估后该怀疑被解除，则该限制将很快取消。

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a>我无法从邮件中的发件人Microsoft 365

 为了从我们的用户接收邮件，请确保您的网络允许来自 EOP 在我们的数据中心使用的 IP 地址的连接。 有关详细信息，请参阅Exchange Online Protection [IP 地址](../../enterprise/urls-and-ip-address-ranges.md)。

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a>向用户发送批量电子邮件Microsoft 365最佳实践

如果你经常向用户进行批量电子邮件Microsoft 365，并且希望确保你的电子邮件以安全且及时的方式到达，请按照本部分中的提示操作。

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>确保"发送者"名称反映发送邮件的人

邮件主题应是邮件内容的简要概括，且邮件正文应清楚并简洁地表明优惠、服务或产品的相关内容。 例如：

正确：

> 来源：marketing@shoppershandbag.com <br> 主题：更新了 Christmas christmas 的目录！

不正确：

> 来源：someone@outlook.com <br> 主题： 目录

越容易让人知道您是谁、在做什么，您在通过大部分垃圾邮件筛选器传送邮件时遇到的困难就会越少。

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>始终在营销邮件中包含“取消订阅”选项

营销邮件，尤其是新闻稿，应始终包含取消订阅未来邮件的方法。例如：

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

一些发件人通过要求收件人发送一封主题包含"取消订阅"的电子邮件到特定别名的方法包含此选项。与上面一键单击的示例相比较，此方法并不可取。如果您一定要选择要求收件人发送邮件，请确保当他们单击链接时，所有要求的字段都已被预设。

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>为营销电子邮件或新闻稿注册使用双重加入方案。

如果您的公司要求或鼓励用户注册他们的联系信息以访问您的产品或服务，则推荐本行业的最佳做法。一些公司是在注册阶段自动注册他们的用户，用于营销电子邮件或电子新闻稿，但是这在世界范围内的电子邮件筛选中，被认为是可疑的市场营销活动。

在注册过程中，如果"是，请向我发送您的新闻稿"或"是，请向我发送您的优惠"复选框在默认情况下处于选中状态，没有仔细查看的用户可能会无意中注册他们并不想接收的营销邮件或新闻稿。

 Microsoft 建议改为选择双重加入选项，这意味着营销电子邮件或新闻稿的复选框在默认情况下未选中。 此外，用户一旦提交了注册表，就会收到一封带有 URL 的验证电子邮件，允许他们确认是否决定接收营销电子邮件。

 这将有助于确保只有想要接收营销电子邮件的用户注册电子邮件，随后清除任何可疑的电子邮件营销活动的发送公司。

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>确保电子邮件消息内容透明且可跟踪。

与发送电子邮件的方法同样重要的，是邮件包含的内容。在创建电子邮件的内容时，使用以下最佳做法确保您的电子邮件不会被电子邮件筛选服务标记。

- 当电子邮件要求收件人将发件人添加到通讯簿时，应清楚地表明此操作无法保证邮件传送。

- 包含在邮件正文中的重定向应当是相似且一致的，不能是多样的和各不相同的。本文中的重定向不指向邮件，例如链接和文档。如果您有大量广告或"取消订阅"链接或"更新配置文件"链接，它们应全部指向同一个域。例如：

  正确 (所有域都是同一) ：

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  所有 (域不同时错误) ：

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- 请避免包含大容量图片和附件的内容，或仅含一张图片的邮件。

- 您的公开隐私或 P3P 设置应清楚地说明跟踪像素（Web bug 或信号）的状态。

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>从您的数据库中删除不正确的电子邮件别名

在您的数据库中创建跳回的任何电子邮件别名都是不必要的，它将使您的出站邮件面临风险 - 会受到电子邮件筛选服务的进一步审查。请确保您的电子邮件数据库是最新的。