---
title: DANE 中基于 SMTP DNS 的命名 (身份验证) 保护电子邮件通信
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
description: 了解 DANE (基于 SMTP DNS 的身份验证) 保护邮件服务器之间的电子邮件通信。
ms.openlocfilehash: 596e1b04576edc025eda8b3486b42c5e7e0b29bc
ms.sourcegitcommit: 986ea76ecaceb5fe6b9616e553003e3c5b0df2e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2022
ms.locfileid: "62214256"
---
# <a name="how-smtp-dns-based-authentication-of-named-entities-dane-works"></a>DANE 中基于 SMTP DNS 的命名实体身份验证 (DANE) 工作

SMTP 协议是在邮件服务器之间传输邮件的主要协议，默认情况下不安全。 传输层安全性 (TLS) 协议是多年来引入的，以支持通过 SMTP 加密传输邮件。 它通常以机会方式使用，而不是作为要求使用，以纯文本格式保留许多电子邮件流量，容易被不法的主角拦截。 此外，SMTP 通过公用 DNS 基础结构确定目标服务器的 IP 地址，该基础结构易受欺骗和中间人 (MITM) 攻击。 这导致创建了许多新标准以提高发送和接收电子邮件的安全性，其中一个标准是基于 DNS 的命名实体身份验证 (DANE) 。
  
用于 SMTP [RFC 7672](https://tools.ietf.org/html/rfc7672) 的 DANE 使用域的 DNS 记录集存在传输层安全身份验证 (TLSA) 记录，以指示域及其邮件服务器 (支持 DANE) 。 如果不存在 TLSA 记录，则无需尝试任何 DANE 检查，邮件流的 DNS 解析将照常工作。 TLSA 记录可安全地向 TLS 支持发出信号，并发布域的 DANE 策略。 因此，发送邮件服务器可以使用 SMTP DANE 成功地对合法接收邮件服务器进行身份验证。 这使得它无法降级和 MITM 攻击。 DANE 对 DNSSEC 有直接依赖关系，DNSSEC 使用公钥加密对 DNS 查找记录进行数字签名。 DNSSEC 检查发生在递归 DNS 解析程序上，即对客户端进行 DNS 查询的 DNS 服务器。 DNSSEC 可确保 DNS 记录不被篡改且真实可信。  

一旦将域的 MX、A/AAAA 和 DNSSEC 相关资源记录作为 DNSSEC 验证返回给 DNS 递归解析程序，发送邮件服务器将请求与 MX 主机条目对应的 TLSA 记录。 如果 TLSA 记录存在且已证明使用另一个 DNSSEC 检查是可信的，则 DNS 递归解析程序将 TLSA 记录返回到发送邮件服务器。 

收到可信的 TLSA 记录后，发送邮件服务器将建立到与可信 TLSA 记录关联的 MX 主机的 SMTP 连接。 发送邮件服务器将尝试设置 TLS 并将服务器的 TLS 证书与 TLSA 记录中的数据进行比较，以验证连接到发件人的目标邮件服务器是合法接收邮件服务器。 如果身份验证成功，邮件 (TLS) 传输。 当身份验证失败或目标服务器不支持 TLS 时，Exchange Online 将重试整个验证过程，从 15 分钟后对同一目标域的 DNS 查询开始，之后 15 分钟重试，然后每隔 24 小时重试一次。 如果在重试 24 小时后身份验证仍失败，邮件将过期，并生成包含错误详细信息的 NDR 并发送给发件人。 

## <a name="what-are-the-components-of-dane"></a>DANE 的组件是什么？

### <a name="tlsa-resource-record"></a>TLSA 资源记录

TLS 身份验证 (TLSA) 记录用于将服务器的 X.509 证书或公钥值与包含记录的域名关联。 只有在域中启用了 DNSSEC 时，才能信任 TLSA 记录。 如果使用 DNS 提供程序托管域，这可能是在使用 DNS 提供程序配置域时提供的设置。 若要了解有关 DNSSEC 区域签名的更多信息，请访问此链接 [：DNSSEC |Microsoft Docs](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj200221(v=ws.11))。 
  
示例 TLSA 记录：
  
:::image type="content" source="../media/compliance-trial/example-TLSA-record.png" alt-text="示例 TLSA 记录" lightbox="../media/compliance-trial/example-TLSA-record.png":::

TLSA 记录类型有四个唯一的可配置字段： 

**证书使用字段**：指定发送电子邮件服务器如何验证目标电子邮件服务器的证书。

|值  |首字母缩略词  |说明 |
|---------|---------|---------|
|0<sup>1</sup>     |PKIX-TA          |使用的证书是 X.509 信任链中的信任定位公共 CA。          |
|1<sup>1</sup>     |PKIX-企业版         |已检查证书是目标服务器;DNSSEC 检查必须验证其真实性。          |
|2     |DANE-TA         |使用 X.509 树中的服务器私钥，该密钥必须由信任链中的信任定位标记进行验证。 TLSA 记录指定用于验证域的 TLS 证书的信任定位标记。         |
|3     |DANE-企业版         |仅与目标服务器的证书匹配。           |

<sup>1</sup>Exchange Online RFC 实现指南，在使用 SMTP 实现 DANE 时，不应使用证书使用字段值 0 或 1。   当证书使用字段值为 0 或 1 的 TLSA 记录返回到 Exchange Online 时，Exchange Online会认为它不可使用。 如果发现所有 TLSA 记录都不可用，Exchange Online发送电子邮件时，不会执行 0 或 1 的 DANE 验证步骤。 相反，由于 TLSA 记录存在，Exchange Online 将强制使用 TLS 发送电子邮件，如果目标电子邮件服务器支持 TLS 或丢弃电子邮件，并生成 NDR（如果目标电子邮件服务器不支持 TLS）。     

在示例 TLSA 记录中，证书使用字段设置为"3"，因此证书关联数据 ("abc123..."。xyz789') 仅与目标服务器的证书匹配。

**选择器** 字段：指示应检查目标服务器证书的哪些部分。 

|值  |首字母缩略词  |说明  |
|---------|---------|---------|
|0     |证书         |使用完整证书。         |
|1     |SPKI (主题公钥信息)           |使用证书的公钥和标识公钥使用的算法。          |

在示例 TLSA 记录中，选择器字段设置为"1"，以便使用目标服务器证书的公钥和标识公钥使用的算法来匹配证书关联数据。

**匹配类型字段**：指示证书将在 TLSA 记录中表示的格式。 

|值  |首字母缩略词  |说明  |
|---------|---------|---------|
|0     |完整         |TSLA 记录中的数据是完整证书或 SPKI。          |
|1     |SHA-256         |TSLA 记录中的数据是证书或 SPKI 的 SHA-256 哈希。          |
|2     |SHA-512         |TSLA 记录中的数据是证书或 SPKI 的 SHA-512 哈希。         |

在 TLSA 记录示例中，匹配类型字段设置为"1"，因此证书关联数据是目标服务器证书中主题公钥信息的 SHA-256 哈希

**证书关联数据**：指定用于与目标服务器证书匹配的证书数据。 此数据取决于选择器字段值和匹配类型值。

在 TLSA 记录示例中，证书关联数据设置为"abc123..."。xyz789'. 由于示例中的选择器字段值设置为"1"，因此它将引用目标服务器证书的公钥以及标识用于该证书的算法。 由于示例中的"匹配类型"字段值设置为"1"，因此它会从目标服务器证书引用主题公钥信息的 SHA-256 哈希。

## <a name="how-can-exchange-online-customers-use-smtp-dane-outbound"></a>客户如何使用Exchange Online SMTP DANE 出站？

作为Exchange Online客户，无需执行任何措施来为出站电子邮件配置此增强的电子邮件安全性。 这是我们为用户构建的一个功能，默认情况下，它将针对所有Exchange Online客户打开，在目标域公布对 DANE 的支持时使用。 若要从通过 DNSSEC 和 DANE 检查发送电子邮件中获益，请与交换电子邮件的业务合作伙伴通信，告知他们实施 DNSSEC 和 DANE 所需的电子邮件，以便他们可以使用这些标准接收电子邮件。 

## <a name="how-can-exchange-online-customers-use-smtp-dane-inbound"></a>客户如何使用Exchange Online SMTP DANE 入站？

目前，入站 SMTP DANE 不受 Exchange Online。 支持预计于 2022 年底发布。 

## <a name="what-is-the-recommended-tlsa-record-configuration"></a>建议的 TLSA 记录配置是什么？

根据 SMTP DANE 的 RFC 实现指南，建议使用由"证书使用"字段设置为 3、选择器字段设置为 1 和"匹配类型"字段设置为 1 的 TLSA 记录。 

## <a name="exchange-online-mail-flow-with-smtp-dane"></a>Exchange Online SMTP DANE Flow邮件传输 

使用 SMTP DANE 的 Exchange Online 的邮件流过程（如下流程图所示）通过 DNSSEC 验证域和资源记录安全性，在目标邮件服务器上提供 TLS 支持，以及目标邮件服务器的证书是否与其关联的 TLSA 记录的预期匹配。 

只有两种情况，SMTP DANE 失败会导致电子邮件被阻止：

- 目标域发出 DNSSEC 信号支持，但一个或多个记录以非身份验证返回。 

- 目标域的所有 MX 记录都有 TLSA 记录，并且任何目标服务器的证书均与 TSLA 记录数据的预期结果不匹配，或者目标服务器不支持 TLS 连接。

:::image type="content" source="../media/compliance-trial/mail-flow-smtp-dane.png" alt-text="Exchange SMTP DANE 处理联机邮件流" lightbox="../media/compliance-trial/mail-flow-smtp-dane.png":::

## <a name="related-technologies"></a>相关技术 

|技术  |其他信息  |
|---------|---------|
|邮件传输代理 – 严格传输安全 **(MTA-STS)** 通过提供一种用于设置域策略的机制来帮助防止降级和中间人攻击，该机制指定目标电子邮件服务器是否支持 TLS 以及无法协商 TLS 时要执行哪些操作，例如停止传输。     |有关即将Exchange Online的入站和出站 MTA-STS 支持的信息，将今年晚些时候发布。     [Exchange Online Microsoft Ignite 2020 中的传输新闻 - Microsoft 技术Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-online-transport-news-from-microsoft-ignite-2020/ba-p/1687699)<br /><br />[rfc8461 (ietf.org) ](https://datatracker.ietf.org/doc/html/rfc8461) |
|**发件人策略框架 (SPF)** 使用 IP 信息，以确保目标电子邮件系统信任从自定义域发送的邮件。    |   [发件人策略框架 (SPF) 防止欺骗 - Office 365 - Microsoft Docs](/microsoft-365/security/office-365-security/how-office-365-uses-spf-to-prevent-spoofing)      |
|**域密钥识别 (DKIM**) 使用 X.509 证书信息，以确保目标电子邮件系统信任从自定义域出站发送的邮件。      | [如何对自定义域中的电子邮件使用 DKIM - Office 365 - Microsoft Docs](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email)        |
|基于域的邮件身份验证、报告和一致性 **(DMARC)** 与发件人策略框架和域密钥识别邮件一起对邮件发件人进行身份验证，并确保目标电子邮件系统信任从你的域发送的邮件。      |  [使用 DMARC 验证电子邮件、设置步骤 - Office 365 - Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)       |

## <a name="troubleshooting-sending-emails-with-smtp-dane"></a>使用 SMTP DANE 发送电子邮件疑难解答

目前，在使用 DANE 发送电子邮件时，DANE 有四Exchange Online。 Microsoft 正在积极更新此错误代码列表。 这些错误将在以下部分可见：
1.  The Exchange Admin Center portal through the Message Trace Details view.
2.  由于 DANE 或 DNSSEC 故障而未发送邮件时生成的 NDDR。
3.  远程连接分析器工具 [Microsoft Remote Connectivity Analyzer](https://testconnectivity.microsoft.com/tests/o365)。

|NDR 代码  |说明  |
|---------|---------|
|5.7.321     |starttls-not-supported：目标邮件服务器必须支持 TLS 来接收邮件。          |
|5.7.322     |证书已过期：目标邮件服务器的证书已过期。          |
|5.7.323     |tlsa-invalid：域未通过 DANE 验证。          |
|5.7.324     |dnssec-invalid：目标域返回无效的 DNSSEC 记录。         |

### <a name="troubleshooting-57321-starttls-not-supported"></a>5.7.321 starttls 不支持疑难解答

这通常表示目标邮件服务器存在问题。 收到邮件后：
1.  检查目标电子邮件地址输入是否正确。
2.  提醒目标电子邮件管理员你收到了此错误代码，以便他们可以确定目标服务器是否被正确配置为使用 TLS 接收邮件。 
3.  重试发送电子邮件，并查看"管理中心"门户中Exchange邮件跟踪详细信息。

### <a name="troubleshooting-57322-certificate-expired"></a>5.7.322 证书过期疑难解答

必须将尚未过期的有效 X.509 证书呈现给发送电子邮件服务器。 X.509 证书必须在过期后续订，通常每年续订一次。 收到邮件后：

1.  提醒目标电子邮件管理员你收到了此错误代码并提供错误代码字符串。
2.  允许续订目标服务器证书，并更新 TLSA 记录以引用新证书。 然后，重试发送电子邮件，然后在管理中心门户中查看邮件Exchange详细信息。

### <a name="troubleshooting-57323-tlsa-invalid"></a>5.7.323 tlsa 无效疑难解答

此错误代码与 TLSA 记录配置错误有关，并且只能在返回 DNSSEC 验证 TLSA 记录后生成。 在 DANE 验证期间，在返回记录后会出现许多可能导致生成代码的情况。 Microsoft 正在积极处理此错误代码涵盖的方案，以便每个方案都有特定的代码。 目前，其中一个或多个方案可能导致生成错误代码：

1.  目标邮件服务器的证书与根据可信 TLSA 记录的预期结果不匹配。
2.  错误配置了身份验证 TLSA 记录。
3.  目标域受到攻击。
4.  任何其他 DANE 失败。

收到邮件后：

1. 通知目标电子邮件管理员你收到了此错误代码，并提供了错误代码字符串。
2. 允许目标电子邮件管理员查看其 DANE 配置和电子邮件服务器证书的有效性。 然后，重试发送电子邮件，然后在管理中心门户中查看邮件Exchange详细信息。

### <a name="troubleshooting-57324-dnssec-invalid"></a>5.7.324 dnssec 无效疑难解答

当目标域指示它是 DNSSEC-authentic，但无法Exchange Online DNSSEC-authentic 时，将生成此错误代码。 

收到邮件后：

1. 通知目标电子邮件管理员你收到了此错误代码，并提供了错误代码字符串。
2. 允许目标电子邮件管理员查看其域的 DNSSEC 配置。 然后，重试发送电子邮件，然后在管理中心门户中查看邮件Exchange详细信息。

## <a name="troubleshooting-receiving-emails-with-smtp-dane"></a>使用 SMTP DANE 接收电子邮件疑难解答

目前，接收域的管理员可以使用两种方法验证其 DNSSEC 和 DANE 配置并排除其故障，以使用这些标准从 Exchange Online接收电子邮件。 

1. 采用[RFC8460](https://datatracker.ietf.org/doc/html/rfc8460)中 (SMTP TLS-RPT) 传输层安全报告 
2. 使用远程连接分析器工具 [Microsoft Remote Connectivity Analyzer](https://testconnectivity.microsoft.com/tests/o365)

TLS-RPT 是一种报告机制，供发件人向目标域管理员提供有关这些目标域的 DANE 和 [https://datatracker.ietf.org/doc/html/rfc8460](https://datatracker.ietf.org/doc/html/rfc8460) MTA-STS 成功和失败的详细信息。 若要接收 TLS-RPT 报告，只需在域的 DNS 记录中添加 TXT 记录，其中包括希望报告发送到的电子邮件地址或 URI。 Exchange Online JSON 格式发送 TLS-RPT 报告。 

示例记录：

:::image type="content" source="../media/compliance-trial/example-record.png" alt-text="示例记录" lightbox="../media/compliance-trial/example-record.png":::

第二个方法是使用远程连接分析器[Microsoft Remote Connectivity Analyzer，](https://testconnectivity.microsoft.com/tests/o365)它可以针对 DNS 配置执行相同的 DNSSEC 和 DANE 检查，Exchange Online在服务外发送电子邮件时执行相同的 DNS 配置。 这是排查配置错误以使用这些标准从用户Exchange Online最直接的方法。 

进行故障排除时，可能会生成以下错误代码：

|NDR 代码  |说明 |
|---------|---------|
|4/5.7.321     |starttls-not-supported：目标邮件服务器必须支持 TLS 来接收邮件。          |
|4/5.7.322     |证书已过期：目标邮件服务器的证书已过期。          |
|4/5.7.323    |tlsa-invalid：域未通过 DANE 验证。         |
|4/5.7.324     |dnssec-invalid：目标域返回无效的 DNSSEC 记录。         |

### <a name="troubleshooting-57321-starttls-not-supported"></a>5.7.321 starttls 不支持疑难解答

> [!NOTE]
> 这些步骤适用于电子邮件管理员使用 SMTP DANE 解决从 Exchange Online接收电子邮件的问题。

这通常表示目标邮件服务器存在问题。 远程连接分析器正在测试连接的邮件服务器。 通常有两种生成此代码的方案： 

1.  目标邮件服务器完全不支持安全通信，必须使用纯非加密通信。 
2.  未正确配置目标服务器并忽略 STARTTLS 命令。
    
收到邮件后：

1. 检查电子邮件地址。
2. 找到与错误语句关联的 IP 地址，以便标识与语句关联的邮件服务器。
3. 检查邮件服务器的设置以确保其配置为侦听通常端口 25 和 587 (SMTP) 。
4. 请等待几分钟，然后使用远程连接分析器工具重试测试。
5. 如果仍然失败，请尝试删除 TLSA 记录，然后再次使用远程连接分析器工具运行测试。
6. 如果没有失败，这可能表示用于接收邮件的邮件服务器不支持 STARTTLS，并且可能需要升级到使用 DANE 的邮件服务器。 

### <a name="troubleshooting-57322-certificate-expired"></a>5.7.322 证书过期疑难解答

> [!NOTE]
> 这些步骤适用于电子邮件管理员使用 SMTP DANE 解决从 Exchange Online接收电子邮件的问题。

必须将尚未过期的有效 X.509 证书呈现给发送电子邮件服务器。 X.509 证书必须在过期后续订，通常每年续订一次。 收到邮件后：

1. 检查与错误语句关联的 IP，以便标识与其关联的邮件服务器。 找到您标识的电子邮件服务器上已过期的证书。
2. 登录到证书提供商的网站。
3. 选择过期的证书并按照说明续订并支付续订费用。
4. 在你的提供商验证购买后，你可以下载新证书。
5. 将续订的证书安装到其关联的邮件服务器。
6. 使用新证书的数据更新邮件服务器的关联 TLSA 记录。 
7. 等待一定时间后，使用远程连接分析器工具重试测试。

### <a name="troubleshooting-57323-tlsa-invalid"></a>5.7.323 tlsa 无效疑难解答

> [!NOTE]
> 这些步骤适用于电子邮件管理员使用 SMTP DANE 解决从 Exchange Online接收电子邮件的问题。

此错误代码与 TLSA 记录配置错误有关，并且只能在返回 DNSSEC 可信 TSLA 记录后生成。 但是，在 DANE 验证期间，在返回记录后会出现许多可能导致生成代码的情况。 Microsoft 正在积极处理此错误代码涵盖的方案，以便每个方案都有特定的代码。 目前，其中一个或多个方案可能导致生成错误代码：

1. 错误配置了身份验证 TLSA 记录。
2. 证书尚未为将来的时间窗口有效/配置。 
3. 目标域受到攻击。
4. 任何其他 DANE 失败。

收到邮件后：

1. 检查与错误语句关联的 IP，以标识与其关联的邮件服务器。 
2. 标识与标识的邮件服务器关联的 TLSA 记录。 
3. 验证 TLSA 记录的配置，以确保它指示发件人执行首选的 DANE 检查，并且 TLSA 记录中已包含正确的证书数据。 
    1. 如果您需要对记录进行任何差异更新，请等待几分钟，然后使用远程连接分析器工具重新运行测试。 
4. 在标识的邮件服务器上找到证书。
5. 检查证书有效的时间窗口。 如果设置为在未来日期开始生效，需要续订当前日期。
    1. 登录到证书提供商的网站。
    2. 选择过期的证书并按照说明续订并支付续订费用。
    3. 在你的提供商验证购买后，你可以下载新证书。
    4. 将续订的证书安装到其关联的邮件服务器。

### <a name="troubleshooting-57324-dnssec-invalid"></a>5.7.324 dnssec 无效疑难解答

> [!NOTE]
> 这些步骤适用于电子邮件管理员使用 SMTP DANE 解决从 Exchange Online接收电子邮件的问题。

当目标域指示它是 DNSSEC-authentic，Exchange Online无法验证其为 DNSSEC-authentic 时，将生成此错误代码。 本节不会全面解决 DNSSEC 问题，而是重点介绍域以前通过 DNSSEC 身份验证但当前未通过 DNSSEC 身份验证的方案。 

收到邮件后：

1. 如果你使用的是 DNS 提供程序（例如 GoDaddy），请提醒 DNS 提供商该错误，以便他们可以处理疑难解答和配置更改。 
2. 如果您管理自己的 DNSSEC 基础结构，则很多 DNSSEC 配置错误可能会生成此错误消息。 检查区域之前是否通过 DNSSEC 身份验证的一些常见问题：
    1. 断开的信任链，当父区域保存一组指向子区域中不存在的 DS 记录时。 这导致通过验证解析程序将子区域标记为假想。 
        - 通过查看子域 RRSIG 密钥 ID 并确保它们与父区域中发布的 DS 记录中的关键 ID 相匹配来解析。 
    2. 域的 RRSIG 资源记录无效，或者已到期或其有效期尚未开始。 
        - 通过使用有效时间跨度生成域的新签名来解析。 

## <a name="frequently-asked-questions"></a>常见问题

### <a name="as-an-exchange-online-customer-can-i-opt-out-of-using-dnssec-andor-dane"></a>作为Exchange Online，我可以选择退出使用 DNSSEC 和/或 DANE 吗？

我们强烈建议 DNSSEC 和 DANE 将显著增加服务的安全位置，并受益于我们的客户。 在过去一年，我们一直在努力降低此部署对 M365 客户的潜在影响的风险和严重性。 我们将主动监视和跟踪部署，以确保在部署推出时将负面影响降至最低。因此，租户级别的例外或选择退出将不可用。
如果您遇到与启用 DNSSEC 和/或 DANE 相关的任何问题，则本文档中记录的不同故障调查方法将帮助您确定错误的来源。 在大多数情况下，问题将出在外部目标方，你需要与这些业务合作伙伴沟通，他们需要正确配置 DNSSEC 和 DANE，以便使用这些标准从 Exchange Online 接收电子邮件。

### <a name="how-does-dnssec-relate-to-dane"></a>DNSSEC 与 DANE 如何关联？

DNSSEC 利用公钥基础结构将信任层添加到 DNS 解析中，以确保响应 DNS 查询时返回的记录真实可信。 DANE 确保接收邮件服务器是真实 MX 记录的合法和预期邮件服务器。 

### <a name="what-is-the-difference-between-mta-sts-and-dane-for-smtp"></a>MTA-STS 和 DANE for SMTP 之间有什么区别？

DANE 和 MTA-STS 的用途相同，但 DANE 需要 DNSSEC 进行 DNS 身份验证，而 MTA-STS 依赖于证书颁发机构。 

### <a name="why-isnt-opportunistic-tls-sufficient"></a>为什么机会型 TLS 不够充分？

如果两个终结点都同意支持，机会型 TLS 将加密两个终结点之间的通信。 但是，即使 TLS 对传输进行加密，域在 DNS 解析过程中可能也具有欺骗性，因此它指向恶意参与者的终结点，而不是域的真实终结点。 这是电子邮件安全性的一个缺陷，通过 DNSSEC 实现 MTA-STS 和/或 SMTP DANE 解决了这一问题。  

### <a name="why-isnt-dnssec-sufficient"></a>为什么 DNSSEC 不够用？

DNSSEC 无法完全抵御中间人攻击，并且从 TLS (降级为清除邮件流) 文本和攻击。 添加 MTA-STS 和 DANE 以及 DNSSEC 可提供全面的安全方法来阻止 MITM 和降级攻击。

## <a name="additional-links"></a>其他链接 

[查找并修复添加域或 DNS 记录之后出现的问题](/microsoft-365/admin/get-help-with-domains/find-and-fix-issues)

[DNSSEC |Microsoft Docs ](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj200221(v=ws.11))

[使用 DMARC 验证电子邮件、设置步骤 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)

[如何对自定义域中的电子邮件使用 DKIM - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email)

[发件人策略框架 (SPF) 防止欺骗 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/how-office-365-uses-spf-to-prevent-spoofing)

[Exchange Online Microsoft Ignite 2020 中的传输新闻 - Microsoft 技术Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-online-transport-news-from-microsoft-ignite-2020/ba-p/1687699)

[rfc8461 (ietf.org) ](https://datatracker.ietf.org/doc/html/rfc8461)