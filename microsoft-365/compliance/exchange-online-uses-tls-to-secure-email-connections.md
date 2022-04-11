---
title: Exchange Online如何使用传输层安全 (TLS) 来保护电子邮件连接
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/08/2021
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 了解Exchange Online和Microsoft 365如何使用传输层安全 (TLS) 和转发保密 (FS) 来保护电子邮件通信。 另请获取有关 Microsoft 为Exchange Online颁发的证书的信息。
ms.openlocfilehash: 7f6d4cb20299e98fc186409977c8ef7b36d329ca
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760814"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Exchange Online 如何使用 TLS 保护电子邮件连接

了解Exchange Online和Microsoft 365如何使用传输层安全 (TLS) 和转发保密 (FS) 来保护电子邮件通信。 还提供有关 Microsoft 为Exchange Online颁发的证书的信息。
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>Microsoft 365和Exchange Online的 TLS 基础知识

传输层安全性 (TLS) 和 TLS 之前的 SSL 都是一种加密协议，通过使用安全证书加密计算机之间的连接来保护网络通信的安全。 TLS 取代了安全套接字层 (SSL)，并常被称为 SSL 3.1。 Exchange Online使用 TLS 加密Exchange服务器与Exchange服务器与其他服务器（例如本地Exchange服务器或收件人邮件服务器）之间的连接。 加密连接后，所有通过该连接发送的数据都将通过加密通道进行发送。 然而，如果你要转发通过 TLS 加密的连接发送的邮件，则该邮件不一定是加密的。 TLS 不会对消息进行加密，只是对连接进行加密。
  
如果要加密消息，请使用加密消息内容的技术。 例如，可以使用Office消息加密或 S/MIME。 有关[Office 365中](email-encryption.md)消息加密的信息，请参阅Office 365和[Office 365邮件加密 (OME) ](ome.md)中的电子邮件加密。
  
在想要在 Microsoft 与本地组织或其他组织（例如合作伙伴）之间设置安全通信通道的情况下使用 TLS。 Exchange Online始终尝试先使用 TLS 来保护电子邮件，但如果另一方不提供 TLS 安全性，则无法。 请继续阅读，以了解您如何通过使用 *连接器* 保护所有发送到您本地服务器或重要合作伙伴的邮件。

为了向客户提供一流的加密，Microsoft 在 Office 365 和 Office 365 GCC 中弃用了传输层安全 (TLS [) ](tls-1.0-and-1.1-deprecation-for-office-365.md)版本 1.0 [和](tls-1-2-in-office-365-gcc.md) 1.1。 但是，可以在没有任何 TLS 的情况下继续使用未加密的 SMTP 连接。 不建议在不进行任何加密的情况下进行电子邮件传输。  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Exchange Online 如何在 Exchange Online 客户之间使用 TLS

Exchange Online服务器始终使用 TLS 1.2 加密到数据中心中其他Exchange Online服务器的连接。 向组织内的收件人发送消息时，Exchange Online使用 TLS 通过加密的连接自动发送消息。 Exchange Online还会使用使用“转发保密”保护的 TLS 通过加密连接向其他客户发送电子邮件。
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Microsoft 365如何在Microsoft 365和外部受信任的合作伙伴之间使用 TLS

默认情况下，Exchange Online 始终使用 *操作 TLS*。 机会主义 TLS 意味着Exchange Online始终先尝试使用最安全的 TLS 版本加密连接，然后在 TLS 密码列表下方工作，直到找到双方可以同意的连接。 除非已配置Exchange Online以确保发送给该收件人的邮件必须使用安全连接，否则默认情况下，如果收件人组织不支持 TLS 加密，则将不加密发送该消息。 操作 TLS 对于多数企业已够用。 然而，对于具有合规性要求的企业（如医疗、银行或政府机构），你可以配置 Exchange Online 以要求或强制执行 TLS。 有关说明，请参阅[Office 365中使用连接器配置邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。
  
如果您决定在您的组织和受信任合作伙伴组织之间配置 TLS，Exchange Online 可以使用 *强制 TLS* 创建受信任的通信通道。 强制 TLS 要求合作伙伴组织使用安全证书对Exchange Online进行身份验证，以便向你发送邮件。 合作伙伴需要管理自己的证书。 Exchange Online使用连接器来保护你发送的邮件在到达收件人的电子邮件提供程序之前不受授权的访问。 有关使用连接器配置邮件流的信息，请参阅[Office 365中使用连接器配置邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS 和混合 Exchange Server 部署

如果要管理混合Exchange部署，则本地Exchange服务器需要使用安全证书向邮箱仅在Office 365中的收件人发送邮件Microsoft 365进行身份验证。 因此，需要为本地Exchange服务器管理自己的安全证书。 您还必须以安全的方式存储并维护这些服务器证书。 有关在混合部署中管理证书的详细信息，请参阅 [混合部署的证书要求](/exchange/certificate-requirements)。
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>如何在 Office 365 中为 Exchange Online 设置强制 TLS

对于 Exchange Online 客户，为了启用强制 TLS 以保护所有您发送和接收的电子邮件，您需要设置多个要求 TLS 的连接器。 需要一个连接器，用于发送到用户邮箱的消息，另一个连接器用于从用户邮箱发送的消息。 在 Office 365 中的 Exchange 管理中心内创建这些连接器。 有关说明，请参阅[Office 365中使用连接器配置邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

## <a name="tls-certificate-information-for-exchange-online"></a>Exchange Online 的 TLS 证书信息

下表中介绍了 Exchange Online 所用的证书信息。 如果你的业务合作伙伴正在其电子邮件服务器上设置强制 TLS，则需要向他们提供此信息。 出于安全原因，我们的证书会不时更改。 当前证书自 2020 年 9 月 24 日起有效。

### <a name="current-certificate-information-valid-from-september-24-2020"></a>当前证书信息自 2020 年 9 月 24 日起有效
  
| 属性 | 值 |
|:-----|:-----|
|证书颁发机构根颁发者|DigiCert CA - 1|
|证书名称|mail.protection.outlook.com|
|组织|Microsoft Corporation|
|组织单位|www.digicert.com|
|证书的密钥长度|2048|

## <a name="get-more-information-about-tls-certificates-and-microsoft-365-and-download-certificates"></a>获取有关 TLS、证书以及Microsoft 365和下载证书的详细信息

[Microsoft 365加密链和证书下载](encryption-office-365-certificate-chains.md)

[Microsoft 365加密链和证书下载 - DOD 和高GCC](encryption-office-365-certificate-chains-itar.md)

有关支持的密码套件的列表，请参阅 [有关加密的技术参考详细信息](technical-reference-details-about-encryption.md)。
  
[将连接器设置为确保与合作伙伴组织之间实现安全的邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)
  
[电子邮件安全性已提高的连接器](/previous-versions/exchange-server/exchange-150/dn942516(v=exchg.150))
  
[Microsoft 365 中的加密](encryption.md)
