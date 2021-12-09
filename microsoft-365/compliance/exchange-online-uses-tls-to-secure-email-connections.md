---
title: 如何使用Exchange Online层安全性 (TLS) 保护电子邮件连接
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
description: 了解 Exchange Online 和 Microsoft 365 如何使用传输层安全性 (TLS) 和前 (FS) 保护电子邮件通信。 此外，还获取有关 Microsoft 颁发的证书的信息，以Exchange Online。
ms.openlocfilehash: 1caf4a8425f4a8e7c340e8a52d785027e99a1618
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61371492"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Exchange Online 如何使用 TLS 保护电子邮件连接

了解 Exchange Online 和 Microsoft 365 如何使用传输层安全性 (TLS) 和前 (FS) 保护电子邮件通信。 此外，还提供有关 Microsoft 颁发的证书的信息，Exchange Online。
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>Microsoft 365 和 Exchange Online 的 TLS 基础知识

传输层安全性 (TLS) 和 TLS 之前的 SSL 都是一种加密协议，通过使用安全证书加密计算机之间的连接来保护网络通信的安全。 TLS 取代了安全套接字层 (SSL)，并常被称为 SSL 3.1。 Exchange Online TLS 加密 Exchange 服务器之间的连接以及 Exchange 服务器与其他服务器（如本地 Exchange 服务器或收件人的邮件服务器）之间的连接。 加密连接后，所有通过该连接发送的数据都将通过加密通道进行发送。 然而，如果你要转发通过 TLS 加密的连接发送的邮件，则该邮件不一定是加密的。 TLS 不加密邮件，仅加密连接。
  
如果要加密邮件，请使用加密技术对邮件内容进行加密。 例如，您可以使用邮件加密Office S/MIME。 有关[OME Office 365中](email-encryption.md)Office 365 邮件加密 ([加密](ome.md)) Office 365请参阅电子邮件加密。
  
在您希望在 Microsoft 与内部部署组织或其他组织（如合作伙伴）之间设置安全的通信通道的情况下，使用 TLS。 Exchange Online尝试首先使用 TLS 保护您的电子邮件，但如果另一方不提供 TLS 安全性，则不能这样做。 请继续阅读，以了解您如何通过使用 *连接器* 保护所有发送到您本地服务器或重要合作伙伴的邮件。

为了为客户提供一流的加密，Microsoft 在 Office 365 和 Office 365 GCC 中已弃用传输层安全性 (TLS [) ](tls-1.0-and-1.1-deprecation-for-office-365.md) 1.0 版和 1.1 [Office 365 GCC。](tls-1-2-in-office-365-gcc.md) 但是，您可以继续使用不带任何 TLS 的未加密 SMTP 连接。 建议不要在没有任何加密的情况下进行电子邮件传输。  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Exchange Online 如何在 Exchange Online 客户之间使用 TLS

Exchange Online服务器始终使用 TLS 1.2 Exchange Online数据中心内的其他服务器加密连接。 向组织内部的收件人发送邮件时，Exchange Online TLS 通过加密连接自动发送邮件。 Exchange Online使用使用"向前保密"保护的 TLS 通过加密连接发送给其他客户的电子邮件。
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>如何Microsoft 365外部受信任Microsoft 365之间使用 TLS

默认情况下，Exchange Online 始终使用 *操作 TLS*。 机会型 TLS 意味着Exchange Online首先尝试用最安全的 TLS 版本加密连接，然后向下处理 TLS 密码列表，直到找到双方都同意的连接。 除非已配置Exchange Online以确保发送到该收件人的邮件必须使用安全连接，否则默认情况下，如果收件人组织不支持 TLS 加密，则邮件将发送而不加密。 操作 TLS 对于多数企业已够用。 然而，对于具有合规性要求的企业（如医疗、银行或政府机构），你可以配置 Exchange Online 以要求或强制执行 TLS。 有关说明，请参阅 Configure [mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。
  
如果您决定在您的组织和受信任合作伙伴组织之间配置 TLS，Exchange Online 可以使用 *强制 TLS* 创建受信任的通信通道。 强制 TLS 要求合作伙伴组织通过身份验证Exchange Online安全证书向您发送邮件。 合作伙伴需要管理自己的证书。 Exchange Online连接器保护您发送的邮件在到达收件人的电子邮件提供商之前受到未经授权的访问。 有关使用连接器配置邮件流的信息，请参阅 Configure [mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS 和混合 Exchange Server 部署

如果要管理混合 Exchange 部署，本地 Exchange 服务器需要使用安全证书向邮箱仅位于 Office 365 中的收件人发送邮件，以向 Microsoft 365 进行身份验证。 因此，您需要为内部部署服务器管理自己的安全Exchange证书。 您还必须以安全的方式存储并维护这些服务器证书。 有关在混合部署中管理证书的信息，请参阅混合 [部署的证书要求](/exchange/certificate-requirements)。
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>如何在 Office 365 中为 Exchange Online 设置强制 TLS

对于 Exchange Online 客户，为了启用强制 TLS 以保护所有您发送和接收的电子邮件，您需要设置多个要求 TLS 的连接器。 您需要一个连接器用于发送到用户邮箱的邮件，另一个连接器用于从用户邮箱发送的邮件。 在 Office 365 中的 Exchange 管理中心内创建这些连接器。 有关说明，请参阅 Configure [mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

## <a name="tls-certificate-information-for-exchange-online"></a>Exchange Online 的 TLS 证书信息

下表中介绍了 Exchange Online 所用的证书信息。 如果你的业务合作伙伴正在他们的电子邮件服务器上设置强制 TLS，你需要向它们提供此信息。 出于安全考虑，我们的证书会时而更改。 当前证书的有效期为 2020 年 9 月 24 日。

### <a name="current-certificate-information-valid-from-september-24-2020"></a>当前证书信息自 2020 年 9 月 24 起生效
  
| 属性 | 值 |
|:-----|:-----|
|证书颁发机构根颁发者|DigiCert CA – 1|
|证书名称|mail.protection.outlook.com|
|组织|Microsoft Corporation|
|组织单位|www.digicert.com|
|证书的密钥长度|2048|

## <a name="get-more-information-about-tls-certificates-and-microsoft-365-and-download-certificates"></a>获取有关 TLS、证书和证书Microsoft 365下载证书

[Microsoft 365加密链和证书下载](encryption-office-365-certificate-chains.md)

[Microsoft 365加密链和证书下载 - DOD 和 GCC High](encryption-office-365-certificate-chains-itar.md)

有关受支持的密码套件的列表，请参阅有关 [加密的技术参考详细信息](technical-reference-details-about-encryption.md)。
  
[将连接器设置为确保与合作伙伴组织之间实现安全的邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)
  
[电子邮件安全性已提高的连接器](/previous-versions/exchange-server/exchange-150/dn942516(v=exchg.150))
  
[Microsoft 365 中的加密](encryption.md)
