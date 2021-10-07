---
title: 设置 SPF 以防欺骗
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何更新域名服务 (DNS) 记录，以便可以在 Office 365 中使用发件人策略框架 (SPF) 和自定义域。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c4369cafece2d0a7c7a27890cbedf35eca2b90a7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60157514"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>设置 SPF 以防欺骗

- [先决条件](#prerequisites)
- [创建或更新你的 SPF TXT 记录](#create-or-update-your-spf-txt-record)
- [如何处理子域？](#how-to-handle-subdomains)
- [SPF 疑难解答](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

本文介绍了如何更新域名服务 (DNS) 记录，以便可以在 Office 365 中结合使用发件人策略框架 (SPF) 电子邮件身份验证和自定义域。

SPF 帮助 *验证* 从你的自定义域发送的出站电子邮件（是否来自所其显示地址）。 这是建立完全推荐的 SPF、[DKIM](use-dkim-to-validate-outbound-email.md) 和 [DMARC](use-dmarc-to-validate-email.md) 电子邮件身份验证方法的第一步。

- [先决条件](#prerequisites)
- [创建或更新你的 SPF TXT 记录](#create-or-update-your-spf-txt-record)
  - [如何处理子域？](#how-to-handle-subdomains)
- [SPF 电子邮件身份验证实际上做什么？](#what-does-spf-email-authentication-actually-do)
  - [SPF 疑难解答](#troubleshooting-spf)
- [有关 SPF 的详细信息](#more-information-about-spf)

## <a name="prerequisites"></a>先决条件

> [!IMPORTANT]
> 如果你是 **小型企业**，或是不熟悉 IP 地址或 DNS 配置，请致电你的Internet 域注册机构（例如， GoDaddy、Bluehost、web.com）& 请求有关 *SPF 的 DNS 配置*（以及任何其他电子邮件身份验证方法）的帮助。 <p> **如果你不使用自定义 URL**（且用于 Office 365 的 URL 以 **onmicrosoft.com** 结尾），则系统已在 Office 365 服务中为你设置了 SPF。

让我们开始吧。

Office 365 的 SPF TXT 记录将在任何自定义域或子域的外部 DNS 中创建。 需要一些信息以创建记录。 收集此信息：

- 自定义域的 SPF TXT 记录（如果存在）。有关说明，请参阅 [收集创建 Office 365 DNS 记录所需的信息](../../admin/get-help-with-domains/information-for-dns-records.md)。

- 转到消息传递服务器并查找外部 IP 地址（需要来自所有本地消息服务器）。例如，**131.107.2.200**。

- 用于需要包含在 SPF TXT 记录中的所有第三方域的域名。一些批量邮件提供商已设置供其客户使用的子域。例如，MailChimp 公司已经设置了 **servers.mcsv.net**。

- 确定要对 SPF TXT 记录使用的强制规则。我们建议使用 **-all**。有关其他语法选项的详细信息，请参阅 [Office 365 的 SPF TXT 记录语法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)。

> [!IMPORTANT]
> 若要使用自定义域，Office 365 要求你将发件人策略框架 (SPF) TXT 记录添加到 DNS 记录中，这样做有助于防止欺骗发生。

## <a name="create-or-update-your-spf-txt-record"></a>创建或更新你的 SPF TXT 记录

1. 请务必熟悉下表中的 SPF 语法。

   ****

   |元素|如果您正在使用...|对于客户而言很常见？|添加以下内容...|
   |---|---|---|---|
   |1|所有电子邮件系统（必需）|常见。所有 SPF TXT 记录都以此值开头|`v=spf1`|
   |2|Exchange Online|常见|`include:spf.protection.outlook.com`|
   |3|Exchange Online 专用|不常见|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |4 |仅 Office 365 Germany、Microsoft Cloud Germany|不常见|`include:spf.protection.outlook.de`|
   |5|第三方电子邮件系统|不常见|`include:<domain_name>` <p> \<domain_name\> 是第三方电子邮件系统的域。|
   |6 |本地电子邮件系统。例如，Exchange Online Protection 和另一个电子邮件系统|不常见|为每个附加的邮件系统使用以下其中一个： <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> \<IP_address\> 和 \<domain_name\> 是代表你的域发送邮件的其他电子邮件系统的 IP 地址和域。|
   |7 |所有电子邮件系统（必需）|常见。所有 SPF TXT 记录都以此值结尾|`<enforcement rule>` <p> 这可以是多个值之一。我们建议使用 `-all`。|
   |

2. 如果尚未创建 SPF TXT 记录，请使用该表中的语法执行此操作。

   例如，如果完全托管在 Office 365 中（即没有本地邮件服务器），则 SPF TXT 记录包括行 1、2 和 7，如下所示：

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   **上面的示例是最常见的 SPF TXT 记录**。此记录几乎适用于每个人，无论你的 Microsoft 数据中心是位于美国还是欧洲（包括德国），或是其他地理位置。

   不过，如果购买了 Office 365 Germany（属于 Microsoft 云德国），则应使用第 4 行（而不是第 2 行）的 include 语句。例如，如果完全托管在 Office 365 Germany 中（即没有本地邮件服务器），则 SPF TXT 记录包括行 1、4 和 7，如下所示：

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   如果你已在 Office 365 中进行部署并已为自定义域设置 SPF TXT 记录，而当前正在向 Office 365 Germany 迁移，则需要更新 SPF TXT 记录。为此，请将 `include:spf.protection.outlook.com` 更改为 `include:spf.protection.outlook.de`。

3. 形成 SPF TXT 记录后，需要更新 DNS 中的记录。**一个域只能有一条 SPF TXT 记录**。如果存在 SPF TXT 记录，则需要更新现有记录，而不是添加新记录。转到 [为 Office 365 创建 DNS 记录](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)，然后选择 DNS 主机的链接。

4. 测试 SPF TXT 记录。

## <a name="how-to-handle-subdomains"></a>如何处理子域？

请务必注意，*你需要为每个子域创建单独的记录，因为子域不会继承其顶级域的 SPF 记录*。

每个域和子域都需要通配符 SPF 记录（`*.`），以防止攻击者发送声称来自不存在的子域的电子邮件。例如：

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a>SPF 疑难解答

是否遇到与 SPF TXT 记录相关的问题？阅读[故障排除：Office 365 中 SPF 的最佳实践](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。

## <a name="what-does-spf-email-authentication-actually-do"></a>SPF 电子邮件身份验证实际上做什么？

SPF 标识允许哪些邮件服务器代表你发送邮件。一般来说，SPF 以及 DKIM、DMARC 和 Office 365 支持的其他技术可有助于防止欺骗和钓鱼发生。以 TXT 记录的形式添加 SPF 后，DNS 可使用此记录来确定哪些邮件服务器可以代表你的自定义域发送邮件。收件人邮件系统可以参阅 SPF TXT 记录，从而确定从你的自定义域发送的邮件是否来自已获授权的邮件服务器。

例如，假设自定义域 contoso.com 使用 Office 365。你添加一个 SPF TXT 记录，将 Office 365 邮件服务器列为你的域的合法邮件服务器。当接收邮件服务器从 joe@contoso.com 收到一封邮件时，服务器会查找 contoso.com 的 SPF TXT 记录，并确定这封邮件是否有效。如果接收服务器确定这封邮件不是来自 SPF 记录中列出的 Office 365 邮件服务器，则可以选择将这封邮件作为垃圾邮件拒绝。

另外，如果自定义域没有 SPF TXT 记录，某些接收服务器可能会彻底拒绝邮件。这是因为接收服务器无法验证邮件是否来自已获授权的邮件服务器。

如果你已经为 Office 365 设置了邮件，则表明已经将 Microsoft 的邮件服务器作为 SPF TXT 记录添加在 DNS 中。不过，在某些情况下，可能需要在 DNS 中更新 SPF TXT 记录。例如：

- 以前，如果要使用 SharePoint Online，必须向自定义域添加不同的 SPF TXT 记录。现在，不再需要这样做。此更改应该会降低 SharePoint Online 通知邮件最终被转入垃圾电子邮件文件夹的风险。如果即将达到查找限制 10 次，且看到"超出了查找限制"和"跃点过多"的错误消息，请更新 SPF TXT 记录。

- 如果您拥有安装了 Office 365 和本地 Exchange 的混合环境。

- 打算设置 DKIM 和 DMARC（推荐）。

## <a name="more-information-about-spf"></a>有关 SPF 的详细信息

有关支持的 SPF 语法、欺骗、故障排除以及 Office 365 如何支持 SPF 的更加详细的探讨的高级示例，请参阅 [SPF 在 Office 365 中防止欺骗和钓鱼的工作原理](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。

## <a name="next-steps-dkim-and-dmarc"></a>后续步骤：DKIM 和 DMARC

 SPF 旨在帮助防骗，但有些骗术是 SPF 所无法防范的。 为了防范这些诈骗技术，设置 SPF 后，就应该为 Office 365 配置 DKIM 和 DMARC。

[**DKIM**](use-dkim-to-validate-outbound-email.md) 电子邮件身份验证的目标是证明邮件的内容没有被篡改。

[**DMARC**](use-dmarc-to-validate-email.md) 电子邮件身份验证的目标是确保 SPF 和 DKIM 信息与发件人地址匹配。

 有关支持的 SPF 语法的更加详细的探讨的高级示例，请参阅 [SPF 在 Office 365 中防止欺骗和钓鱼的工作原理](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。

*如对此文档有反馈，请在“反馈”下选择“此页”。*
