---
title: 基于 SMTP DNS 的命名实体身份验证 (DANE) 如何工作来保护电子邮件通信
f1.keywords:
- NOCSH
ms.author: v-mathavale
author: v-mathavale
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 了解基于 SMTP DNS 的命名实体身份验证 (DANE) 如何工作来保护邮件服务器之间的电子邮件通信。
ms.openlocfilehash: 2af2a166ff73bbe7888ed9265ec8733105eb2007
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759426"
---
# <a name="how-smtp-dns-based-authentication-of-named-entities-dane-works"></a>已命名实体的基于 SMTP DNS 的身份验证 (DANE) 的工作原理

SMTP 协议是用于在邮件服务器之间传输邮件的主要协议，默认情况下不安全。 传输层安全 (TLS) 协议是几年前推出的，用于支持通过 SMTP 加密传输消息。 它通常被机会性地使用，而不是作为一个要求，留下许多电子邮件流量在清晰的文本，容易被邪恶的参与者拦截。 此外，SMTP 还通过公共 DNS 基础结构确定目标服务器的 IP 地址，这些基础结构容易受到欺骗和中间人 (MITM) 攻击。 这导致了许多新标准的创建，以提高发送和接收电子邮件的安全性，其中之一是基于 DNS 的身份验证命名实体 (DANE) 。

用于 SMTP [RFC 7672](https://tools.ietf.org/html/rfc7672) 的 DANE 使用域的 DNS 记录集中存在传输层安全身份验证 (TLSA) 记录来指示域及其邮件服务器 (支持 DANE 的) 。 如果没有 TLSA 记录，则邮件流的 DNS 解析将照常工作，无需尝试任何 DANE 检查。 TLSA 记录安全地指示 TLS 支持，并发布域的 DANE 策略。 因此，发送邮件服务器可以使用 SMTP DANE 成功对合法接收邮件服务器进行身份验证。 这使得它能够抵御降级和 MITM 攻击。 DANE 直接依赖 DNSSEC，它通过使用公钥加密对 DNS 查找记录进行数字签名。 DNSSEC 检查针对递归 DNS 解析程序（为客户端进行 DNS 查询的 DNS 服务器）进行。 DNSSEC 可确保 DNS 记录不会被篡改且真实。

将域的 MX、A/AAAA 和 DNSSEC 相关的资源记录以 DNSSEC 身份返回到 DNS 递归解析程序后，发送邮件服务器将请求与 MX 主机条目或条目对应的 TLSA 记录。 如果 TLSA 记录存在并使用另一个 DNSSEC 检查证明为正宗，则 DNS 递归解析程序会将 TLSA 记录返回到发送邮件服务器。

收到正宗 TLSA 记录后，发送邮件服务器将建立与正宗 TLSA 记录关联的 MX 主机的 SMTP 连接。 发送邮件服务器将尝试设置 TLS 并将服务器的 TLS 证书与 TLSA 记录中的数据进行比较，以验证连接到发件人的目标邮件服务器是否合法接收邮件服务器。 如果身份验证成功，则将使用 TLS)  (传输消息。 当身份验证失败或目标服务器不支持 TLS 时，Exchange Online将重试整个验证过程，从 15 分钟后、15 分钟后、之后 15 分钟的 DNS 查询开始，然后在接下来的 24 小时内每小时重试一次。 如果身份验证在重试 24 小时后继续失败，则消息将过期，并且将生成包含错误详细信息的 NDR 并将其发送到发件人。

## <a name="what-are-the-components-of-dane"></a>DANE 的组件是什么？

### <a name="tlsa-resource-record"></a>TLSA 资源记录

TLS 身份验证 (TLSA) 记录用于将服务器的 X.509 证书或公钥值与包含记录的域名相关联。 只有在域上启用 DNSSEC 时，才能信任 TLSA 记录。 如果使用 DNS 提供程序来托管域，这可能是在使用它们配置域时提供的设置。 若要了解有关 DNSSEC 区域签名的详细信息，请访问此链接：[DNSSEC |概述Microsoft Docs](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj200221(v=ws.11))。

示例 TLSA 记录：

:::image type="content" source="../media/compliance-trial/example-TLSA-record.png" alt-text="示例 TLSA 记录" lightbox="../media/compliance-trial/example-TLSA-record.png":::

TLSA 记录类型唯一的四个可配置字段：

**证书使用情况字段**：指定发送电子邮件服务器应如何验证目标电子邮件服务器的证书。

|值|首字母缩略词|说明|
|---|---|---|
|01<sup></sup>|PKIX-TA|使用的证书是 X.509 信任链中的信任定位公共 CA。|
|11<sup></sup>|PKIX-企业版|检查的证书是目标服务器;DNSSEC 检查必须验证其真实性。|
|2|DANE-TA|使用 X.509 树中的服务器私钥，该树必须由信任链中的信任定位点进行验证。 TLSA 记录指定用于验证域的 TLS 证书的信任定位点。|
|3|DANE-企业版|仅与目标服务器的证书匹配。|

<sup>1</sup> Exchange Online遵循 RFC 实现指南，即当使用 SMTP 实现 DANE 时，不应使用证书使用字段值 0 或 1。 将证书使用字段值为 0 或 1 的 TLSA 记录返回到Exchange Online时，Exchange Online会将其视为不可用。 如果发现所有 TLSA 记录都不可用，则在发送电子邮件时，Exchange Online不会执行 0 或 1 的 DANE 验证步骤。 相反，由于存在 TLSA 记录，Exchange Online将强制使用 TLS 发送电子邮件，如果目标电子邮件服务器支持 TLS，则发送电子邮件;如果目标电子邮件服务器不支持 TLS，则删除电子邮件并生成 NDR。

在示例 TLSA 记录中，证书使用情况字段设置为“3”，因此证书关联数据 ('abc123...xyz789 的) 将仅与目标服务器的证书匹配。

**选择器字段**：指示应检查目标服务器证书的哪些部分。

|值|首字母缩略词|说明|
|---|---|---|
|0|证书|使用完整证书。|
|1|SPKI (使用者公钥信息) |使用证书的公钥和标识要使用的公钥的算法。|

在示例 TLSA 记录中，选择器字段设置为“1”，以便使用目标服务器证书的公钥和标识公钥的算法来匹配证书关联数据。

**匹配类型字段**：指示证书将在 TLSA 记录中表示的格式。

|值|首字母缩略词|说明|
|---|---|---|
|0|完整|TSLA 记录中的数据是完整的证书或 SPKI。|
|1|SHA-256|TSLA 记录中的数据是证书或 SPKI 的 SHA-256 哈希。|
|2|SHA-512|TSLA 记录中的数据是证书或 SPKI 的 SHA-512 哈希。|

在示例 TLSA 记录中，匹配类型字段设置为“1”，因此证书关联数据是目标服务器证书中使用者公钥信息的 SHA-256 哈希

**证书关联数据**：指定用于与目标服务器证书匹配的证书数据。 此数据取决于选择器字段值和匹配类型值。

在示例 TLSA 记录中，证书关联数据设置为“abc123”。xyz789'. 由于示例中的选择器字段值设置为“1”，因此它将引用目标服务器证书的公钥以及标识为与之一起使用的算法。 由于示例中的匹配类型字段值设置为“1”，因此它将从目标服务器证书中引用使用者公钥信息的 SHA-256 哈希。

## <a name="how-can-exchange-online-customers-use-smtp-dane-outbound"></a>Exchange Online客户如何使用 SMTP DANE 出站？

作为Exchange Online客户，无需执行任何操作即可为出站电子邮件配置此增强的电子邮件安全性。 这是我们为你构建的，默认情况下，它适用于所有Exchange Online客户，并在目标域播发对 DANE 的支持时使用。 若要获得通过 DNSSEC 和 DANE 检查发送电子邮件的好处，请与您与之交换电子邮件的业务合作伙伴通信，这些合作伙伴需要实现 DNSSEC 和 DANE，以便他们可以使用这些标准接收电子邮件。

## <a name="how-can-exchange-online-customers-use-smtp-dane-inbound"></a>Exchange Online客户如何使用 SMTP DANE 入站？

目前，入站 SMTP DANE 不支持Exchange Online。 预计支持将于 2022 年底发布。

## <a name="what-is-the-recommended-tlsa-record-configuration"></a>建议的 TLSA 记录配置是什么？

根据 SMTP DANE 的 RFC 实现指南，建议使用由证书使用情况字段设置为 3 的 TLSA 记录，选择器字段设置为 1，并将匹配类型字段设置为 1。

## <a name="exchange-online-mail-flow-with-smtp-dane"></a>使用 SMTP DANE Exchange Online邮件Flow

使用 SMTP DANE 进行Exchange Online的邮件流过程（如下图所示）通过 DNSSEC 验证域和资源记录安全性、目标邮件服务器上的 TLS 支持，以及目标邮件服务器的证书是否与其关联的 TLSA 记录匹配预期。

只有两种情况下，SMTP DANE 失败将导致电子邮件被阻止：

- 目标域表示 DNSSEC 支持，但一个或多个记录返回为不真实。

- 目标域的所有 MX 记录都具有 TLSA 记录，并且目标服务器的证书与根据 TSLA 记录数据的预期内容不匹配，或者目标服务器不支持 TLS 连接。

:::image type="content" source="../media/compliance-trial/mail-flow-smtp-dane.png" alt-text="使用 SMTP DANE Exchange联机邮件流" lightbox="../media/compliance-trial/mail-flow-smtp-dane.png":::

## <a name="related-technologies"></a>相关技术

|技术|其他信息|
|---|---|
|**邮件传输代理 - 严格传输安全 (MTA-STS)** 通过提供一种机制来设置域策略，该机制指定目标电子邮件服务器是否支持 TLS 以及无法协商 TLS 时应执行的操作，例如停止传输，从而有助于阻止降级和中间人攻击。|有关Exchange Online即将对入站和出站 MTA-STS 的支持的详细信息将于今年晚些时候发布。 <br/><br/> [Exchange Online Microsoft Ignite 2020 - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-online-transport-news-from-microsoft-ignite-2020/ba-p/1687699) <br/><br/> [rfc8461 (ietf.org) ](https://datatracker.ietf.org/doc/html/rfc8461)|
|**发件人策略框架 (SPF)** 使用 IP 信息来确保目标电子邮件系统信任从自定义域发送的消息。|[发件人策略框架 (SPF) 如何防止欺骗 - Office 365 - Microsoft Docs](/microsoft-365/security/office-365-security/how-office-365-uses-spf-to-prevent-spoofing)|
|**DomainKeys 标识的邮件 (DKIM)** 使用 X.509 证书信息来确保目标电子邮件系统信任从自定义域出站发送的消息。|[如何在自定义域中将 DKIM 用于电子邮件 - Office 365 - Microsoft Docs](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email)|
|**基于域的消息身份验证、报告和符合性 (DMARC)** 与发件人策略框架和域密钥识别邮件配合使用，以对邮件发件人进行身份验证，并确保目标电子邮件系统信任从域发送的消息。|[使用 DMARC 验证电子邮件、设置步骤 - Office 365 - Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)|

## <a name="troubleshooting-sending-emails-with-smtp-dane"></a>使用 SMTP DANE 发送电子邮件的疑难解答

目前，在发送带有Exchange Online的电子邮件时，DANE 有四个错误代码。 Microsoft 正在积极更新此错误代码列表。 错误将显示在以下位置：

1. 通过“消息跟踪详细信息”视图Exchange管理中心门户。
2. 由于 DANE 或 DNSSEC 故障而未发送消息时生成的 NDR。
3. 远程连接分析器工具 [Microsoft 远程连接分析器](https://testconnectivity.microsoft.com/tests/o365)。

|NDR 代码|说明|
|---|---|
|5.7.321|starttls-不支持：目标邮件服务器必须支持 TLS 接收邮件。|
|5.7.322|证书过期：目标邮件服务器的证书已过期。|
|5.7.323|tlsa-invalid：域未通过 DANE 验证。|
|5.7.324|dnssec-invalid：目标域返回无效的 DNSSEC 记录。|

### <a name="troubleshooting-57321-starttls-not-supported"></a>排查 5.7.321 starttls-不支持的问题

这通常表示目标邮件服务器出现问题。 收到消息后：

1. 检查是否正确输入了目标电子邮件地址。
2. 向收到此错误代码的目标电子邮件管理员发出警报，以便他们能够确定是否正确配置了目标服务器以使用 TLS 接收消息。
3. 重试发送电子邮件，并在Exchange管理中心门户中查看邮件的邮件跟踪详细信息。

### <a name="troubleshooting-57322-certificate-expired"></a>5.7.322 证书过期疑难解答

尚未过期的有效 X.509 证书必须呈现给发送电子邮件服务器。 X.509 证书必须在过期后续订，通常每年续订一次。 收到消息后：

1. 通知你收到此错误代码的目标电子邮件管理员并提供错误代码字符串。
2. 为更新目标服务器证书和更新 TLSA 记录以引用新证书留出时间。 然后，重试发送电子邮件，并在Exchange管理中心门户中查看邮件的邮件跟踪详细信息。

### <a name="troubleshooting-57323-tlsa-invalid"></a>排查 5.7.323 tlsa-invalid 问题

此错误代码与 TLSA 记录配置错误有关，只能在返回 DNSSEC-authentic TLSA 记录后生成。 在 DANE 验证期间，许多方案在返回记录后发生，可能导致生成代码。 Microsoft 正在积极处理此错误代码所涵盖的方案，以便每个方案都有特定的代码。 目前，其中一个或多个方案可能导致生成错误代码：

1. 目标邮件服务器的证书与每个身份验证 TLSA 记录的预期证书不匹配。
2. 错误配置了身份验证 TLSA 记录。
3. 目标域受到攻击。
4. 任何其他 DANE 失败。

收到消息后：

1. 通知你收到此错误代码的目标电子邮件管理员，并向他们提供错误代码字符串。
2. 允许目标电子邮件管理员查看其 DANE 配置和电子邮件服务器证书有效性的时间。 然后，重试发送电子邮件，并在Exchange管理中心门户中查看邮件的邮件跟踪详细信息。

### <a name="troubleshooting-57324-dnssec-invalid"></a>排查 5.7.324 dnssec-invalid 问题

当目标域指示它是 DNSSEC-authentic，但Exchange Online无法将其验证为 DNSSEC-authentic 时，会生成此错误代码。

收到消息后：

1. 通知你收到此错误代码的目标电子邮件管理员，并向他们提供错误代码字符串。
2. 为目标电子邮件管理员查看其域的 DNSSEC 配置留出时间。 然后，重试发送电子邮件，并在Exchange管理中心门户中查看邮件的邮件跟踪详细信息。

## <a name="troubleshooting-receiving-emails-with-smtp-dane"></a>使用 SMTP DANE 对接收电子邮件进行故障排除

目前，接收域的管理员可以使用两种方法来验证其 DNSSEC 和 DANE 配置并对其进行故障排除，以使用这些标准从Exchange Online接收电子邮件。

1. 采用 [RFC8460](https://datatracker.ietf.org/doc/html/rfc8460) 中引入的 SMTP TLS-RPT (传输层安全报告) 
2. 使用远程连接分析器工具 [Microsoft 远程连接分析器](https://testconnectivity.microsoft.com/tests/o365)

TLS-RPT [https://datatracker.ietf.org/doc/html/rfc8460](https://datatracker.ietf.org/doc/html/rfc8460) 是一种报告机制，使发件人能够向目标域管理员提供有关这些目标域的 DANE 和 MTA-STS 成功和失败的详细信息。 若要接收 TLS-RPT 报告，只需在域的 DNS 记录中添加 TXT 记录，其中包含希望将报表发送到的电子邮件地址或 URI。 Exchange Online将以 JSON 格式发送 TLS-RPT 报表。

示例记录：

:::image type="content" source="../media/compliance-trial/example-record.png" alt-text="示例记录" lightbox="../media/compliance-trial/example-record.png":::

第二种方法是使用远程连接分析器 [Microsoft 远程连接分析器](https://testconnectivity.microsoft.com/tests/o365)，它可以针对 DNS 配置执行相同的 DNSSEC 和 DANE 检查，Exchange Online在服务外部发送电子邮件时执行的检查。 这是排查配置中的错误以使用这些标准从Exchange Online接收电子邮件的最直接方法。

进行故障排除时，可能会生成以下错误代码：

|NDR 代码|说明|
|---|---|
|4/5.7.321|starttls-不支持：目标邮件服务器必须支持 TLS 接收邮件。|
|4/5.7.322|证书已过期：目标邮件服务器的证书已过期。|
|4/5.7.323|tlsa-invalid：域未通过 DANE 验证。|
|4/5.7.324|dnssec-invalid：目标域返回无效的 DNSSEC 记录。|

### <a name="troubleshooting-57321-starttls-not-supported"></a>排查 5.7.321 starttls-不支持的问题

> [!NOTE]
> 这些步骤适用于使用 SMTP DANE 从Exchange Online接收电子邮件的电子邮件管理员疑难解答。

这通常表示目标邮件服务器出现问题。 远程连接分析器正在测试连接的邮件服务器。 通常有两种生成此代码的方案：

1.  目标邮件服务器根本不支持安全通信，必须使用纯非加密通信。
2.  目标服务器配置不当，并忽略 STARTTLS 命令。

收到消息后：

1. 检查电子邮件地址。
2. 找到与错误语句关联的 IP 地址，以便你可以标识与该语句关联的邮件服务器。
3. 检查邮件服务器的设置，确保已将其配置为侦听通常端口 25 和 587)  (SMTP 流量。
4. 等待几分钟，然后使用远程连接分析器工具重试测试。
5. 如果仍失败，请尝试删除 TLSA 记录，然后再次使用远程连接分析器工具运行测试。
6. 如果没有故障，这可能表示用于接收邮件的邮件服务器不支持 STARTTLS，可能需要升级到使用 DANE 的邮件服务器。

### <a name="troubleshooting-57322-certificate-expired"></a>5.7.322 证书过期疑难解答

> [!NOTE]
> 这些步骤适用于使用 SMTP DANE 从Exchange Online接收电子邮件的电子邮件管理员疑难解答。

尚未过期的有效 X.509 证书必须呈现给发送电子邮件服务器。 X.509 证书必须在过期后续订，通常每年续订一次。 收到消息后：

1. 检查与错误语句关联的 IP，以便识别与之关联的邮件服务器。 在标识的电子邮件服务器上找到过期的证书。
2. 登录到证书提供程序的网站。
3. 选择过期的证书，并按照说明进行续订并支付续订费用。
4. 提供商验证购买后，可以下载新证书。
5. 将续订的证书安装到其关联的邮件服务器中。
6. 使用新证书的数据更新邮件服务器关联的 TLSA 记录。
7. 等待适当时间后，使用远程连接分析器工具重试测试。

### <a name="troubleshooting-57323-tlsa-invalid"></a>排查 5.7.323 tlsa-invalid 问题

> [!NOTE]
> 这些步骤适用于使用 SMTP DANE 从Exchange Online接收电子邮件的电子邮件管理员疑难解答。

此错误代码与 TLSA 记录配置错误有关，只能在返回 DNSSEC-authentic TSLA 记录后生成。 但是，在 DANE 验证期间，许多方案在返回记录后发生，可能导致生成代码。 Microsoft 正在积极处理此错误代码所涵盖的方案，以便每个方案都有特定的代码。 目前，其中一个或多个方案可能导致生成错误代码：

1. 错误配置了身份验证 TLSA 记录。
2. 对于将来的时间窗口，证书尚无效/配置时间。
3. 目标域受到攻击。
4. 任何其他 DANE 失败。

收到消息后：

1. 检查与错误语句关联的 IP，以确定与之关联的邮件服务器。
2. 标识与标识的邮件服务器关联的 TLSA 记录。
3. 验证 TLSA 记录的配置，以确保它指示发件人执行首选的 DANE 检查，并且 TLSA 记录中包含正确的证书数据。
    1. 如果必须对记录进行任何更新以实现差异，请等待几分钟，然后使用远程连接分析器工具重新运行测试。
4. 在标识的邮件服务器上找到证书。
5. 检查证书有效的时间窗口。 如果设置为在将来的日期开始有效，则需要在当前日期续订。
    1. 登录到证书提供程序的网站。
    2. 选择过期的证书，并按照说明进行续订并支付续订费用。
    3. 提供商验证购买后，可以下载新证书。
    4. 将续订的证书安装到其关联的邮件服务器中。

### <a name="troubleshooting-57324-dnssec-invalid"></a>排查 5.7.324 dnssec-invalid 问题

> [!NOTE]
> 这些步骤适用于使用 SMTP DANE 从Exchange Online接收电子邮件的电子邮件管理员疑难解答。

当目标域指示它为 DNSSEC-authentic，但Exchange Online无法将其验证为 DNSSEC-authentic 时，将生成此错误代码。 本部分对 DNSSEC 问题进行故障排除并不全面，并侧重于域以前通过 DNSSEC 身份验证但现在未通过的情况。

收到消息后：

1. 如果使用的是 DNS 提供程序（例如 GoDaddy），请向 DNS 提供程序发出错误警报，以便他们能够进行故障排除和配置更改。
2. 如果要管理自己的 DNSSEC 基础结构，则有许多 DNSSEC 错误配置可能会生成此错误消息。 检查区域以前是否通过 DNSSEC 身份验证的一些常见问题：
    1. 当父区域保存一组 DS 记录，这些记录指向子区域中不存在的内容时，信任链断开。 这会导致子区域通过验证解析程序标记为假。
        - 通过查看子域 RRSIG 密钥 ID 并确保它们与父区域中发布的 DS 记录中的密钥 ID 匹配来解决此问题。
    2. 域的 RRSIG 资源记录无效、已过期或有效期尚未开始。
        - 通过使用有效时间跨度为域生成新签名来解决此问题。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="as-an-exchange-online-customer-can-i-opt-out-of-using-dnssec-andor-dane"></a>作为Exchange Online客户，是否可以选择不使用 DNSSEC 和/或 DANE？

我们坚信 DNSSEC 和 DANE 将显著提高服务的安全地位，并使所有客户受益。 在过去的一年里，我们一直在努力降低此部署可能对 M365 客户产生的潜在影响的风险和严重性。 我们将积极监视和跟踪部署，以确保在部署推出时最大程度地减少负面影响。因此，租户级异常或选择退出将不可用。
如果遇到与启用 DNSSEC 和/或 DANE 相关的任何问题，本文档中记录的不同调查失败方法将帮助你确定错误的根源。 在大多数情况下，问题出在外部目标方，你需要与这些业务合作伙伴沟通，他们需要正确配置 DNSSEC 和 DANE，以便使用这些标准从Exchange Online接收电子邮件。

### <a name="how-does-dnssec-relate-to-dane"></a>DNSSEC 与 DANE 有何关系？

DNSSEC 利用公钥基础结构，将信任层添加到 DNS 解析中，以确保响应 DNS 查询时返回的记录是真实的。 DANE 确保接收邮件服务器是正宗 MX 记录的合法且预期的邮件服务器。

### <a name="what-is-the-difference-between-mta-sts-and-dane-for-smtp"></a>MTA-STS 和 DANE for SMTP 之间的区别是什么？

DANE 和 MTA-STS 具有相同的用途，但 DANE 需要 DNSSEC 进行 DNS 身份验证，而 MTA-STS 依赖于证书颁发机构。

### <a name="why-isnt-opportunistic-tls-sufficient"></a>为什么机会主义 TLS 不够？

如果两个终结点都同意支持，机会性 TLS 将加密两个终结点之间的通信。 但是，即使 TLS 加密传输，域也可能在 DNS 解析过程中被欺骗，以便指向恶意执行组件的终结点，而不是域的真正终结点。 这是通过使用 DNSSEC 实现 MTA-STS 和/或 SMTP DANE 来解决的电子邮件安全性的差距。

### <a name="why-isnt-dnssec-sufficient"></a>为什么 DNSSEC 不够？

DNSSEC 不完全抵御中间人攻击，从 TLS 降级 (，以清除邮件流方案的文本) 攻击。 添加 MTA-STS 和 DANE 以及 DNSSEC 提供了一种全面的安全方法来阻止 MITM 和降级攻击。

## <a name="additional-links"></a>其他链接

[查找并修复添加域或 DNS 记录之后出现的问题](/microsoft-365/admin/get-help-with-domains/find-and-fix-issues)

[DNSSEC |概述Microsoft Docs](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj200221(v=ws.11))

[使用 DMARC 验证电子邮件、设置步骤 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)

[如何在自定义域中将 DKIM 用于电子邮件 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email)

[发件人策略框架 (SPF) 如何防止欺骗 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/how-office-365-uses-spf-to-prevent-spoofing)

[Exchange Online Microsoft Ignite 2020 - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-online-transport-news-from-microsoft-ignite-2020/ba-p/1687699)

[rfc8461 (ietf.org) ](https://datatracker.ietf.org/doc/html/rfc8461)
