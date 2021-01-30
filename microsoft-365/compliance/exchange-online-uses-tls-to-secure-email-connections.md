---
title: Exchange Online 如何使用 TLS 保护电子邮件连接
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 了解 Exchange Online 和 Microsoft 365 如何使用传输层安全性 (TLS) 和转发保密 (FS) 保护电子邮件通信。 此外，还获取有关 Microsoft for Exchange Online 颁发的证书的信息。
ms.openlocfilehash: 507a152130113868293d8d08441f298e5f5ae512
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058455"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Exchange Online 如何使用 TLS 保护电子邮件连接

了解 Exchange Online 和 Microsoft 365 如何使用传输层安全性 (TLS) 和转发保密 (FS) 保护电子邮件通信。 此外，还提供有关 Microsoft 为 Exchange Online 颁发的证书的信息。
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>Microsoft 365 和 Exchange Online 的 TLS 基础知识

传输层安全性 (TLS) 和 TLS 之前的 SSL 都是一种加密协议，通过使用安全证书加密计算机之间的连接来保护网络通信的安全。 TLS 取代了安全套接字层 (SSL)，并常被称为 SSL 3.1。 对于 Exchange Online，我们使用 TLS 来加密 Exchange 服务器之间的连接以及 Exchange 服务器与其他服务器（如内部部署 Exchange 服务器或收件人的邮件服务器）之间的连接。 加密连接后，所有通过该连接发送的数据都将通过加密通道进行发送。 然而，如果你要转发通过 TLS 加密的连接发送的邮件，则该邮件不一定是加密的。 这是因为，简单来说，TLS 不会加密邮件，而只是加密连接。
  
如果您想要加密邮件，您需要使用一种加密技术对邮件内容进行加密，例如 Office 邮件加密。 有关 Office 365 中邮件加密选项的信息，请参阅 [Email encryption in Office 365](email-encryption.md)和 [Office 365 Message Encryption (OME)](ome.md)。 
  
我们建议在您希望在 Microsoft 和内部部署组织或其他组织（如合作伙伴）之间设置安全通信通道的情况下使用 TLS。 Exchange Online 始终尝试首先使用 TLS 保护您的电子邮件，但如果另一方没有提供 TLS 安全，则无法始终这么做。 请继续阅读，了解如何使用连接器保护发送到内部部署服务器或重要合作伙伴  *的所有邮件*。 

为了为客户提供一流的加密，Microsoft 在 [Office 365 和 Office 365](tls-1.0-and-1.1-deprecation-for-office-365.md) GCC 中已弃用传输层安全性 (TLS) 1.0 版和 [1.1](tls-1-2-in-office-365-gcc.md)版。 但是，您可以继续使用不带任何 TLS 的未加密 SMPT 连接。 建议不要在没有任何加密的情况下传输电子邮件。  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Exchange Online 如何在 Exchange Online 客户之间使用 TLS

Exchange Online 服务器始终通过 TLS 1.2 加密到我们数据中心其他 Exchange Online 服务器的连接。 当您向组织内部的收件人发送邮件时，该电子邮件将自动通过使用 TLS 加密的连接发送。 此外，您发送给其他客户的所有电子邮件都通过使用 TLS 加密且使用"向前保密"进行保护的连接发送。
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Microsoft 365 如何在 Microsoft 365 和外部受信任合作伙伴之间使用 TLS

默认情况下，Exchange Online 始终使用操作 TLS。 这意味着 Exchange Online 会始终尝试首先通过最安全的 TLS 版本加密连接，而后沿着 TLS 密码列表一直往下，直到找到一个双方都同意的版本进行加密。 除非您已配置 Exchange Online 以确保发送给该收件人的邮件仅通过安全连接发送，否则默认情况下，如果收件人组织不支持 TLS 加密，则邮件将发送未加密。 操作 TLS 对于多数企业已够用。 但是，对于具有合规性要求（如医疗、银行或政府组织）的企业，可以将 Exchange Online 配置为要求或强制使用 TLS。 有关说明，请参阅 [使用 Office 365 中的连接器配置邮件流](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)。
  
如果您决定在您的组织和受信任合作伙伴组织之间配置 TLS，Exchange Online 可以使用强制 TLS 创建受信任的通信通道。 “强制 TLS”要求您的合作伙伴组织使用安全证书对 Exchange Online 进行身份验证，以便向您发送邮件。 若要这么做，您的合作伙伴将需要管理其自己的证书。 在 Exchange Online 中，我们使用连接器保护您发送的邮件在到达收件人的电子邮件提供商之前免受未经授权的访问。 有关使用连接器配置邮件流的信息，请参阅使用 [Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)中的连接器配置邮件流。
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS 和混合 Exchange Server 部署

如果要管理混合 Exchange 部署，本地 Exchange 服务器需要使用安全证书向 Microsoft 365 进行身份验证，以便向邮箱仅位于 Office 365 中的收件人发送邮件。 因此，您需要为内部部署 Exchange 服务器管理您自己的安全证书。 您还必须以安全的方式存储并维护这些服务器证书。 有关在混合部署中管理证书详细信息，请参阅混合 [部署的证书要求](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx)。
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>如何在 Office 365 中为 Exchange Online 设置强制 TLS

对于 Exchange Online 客户，为了启用强制 TLS 以保护所有您发送和接收的电子邮件，您需要设置多个要求 TLS 的连接器。 其中一个连接器适用于发送至您的用户邮箱的电子邮件，另一个连接器适用于来自您的用户邮箱的电子邮件。 在 Office 365 中的 Exchange 管理中心内创建这些连接器。 有关说明，请参阅 [使用 Office 365 中的连接器配置邮件流](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)。
  
## <a name="tls-certificate-information-for-exchange-online"></a>Exchange Online 的 TLS 证书信息

下表中介绍了 Exchange Online 所用的证书信息。 如果您的业务合作伙伴在其电子邮件服务器上设置强制 TLS，则您需要将此信息提供给他们。 请注意，出于安全考虑，我们的证书会随时更改。 我们已推出对数据中心内证书的更新。 新证书的有效期为 2018 年 9 月 3 日。
  
 **当前证书信息自 2018 年 9 月 3 起有效**
  
|**属性**|**值**|
|:-----|:-----|
|证书颁发机构根颁发者  <br/> |GlobalSign 根 CA – R1 <br/> |
|证书名称  <br/> |mail.protection.outlook.com  <br/> |
|组织  <br/> |Microsoft Corporation  <br/> |
|组织单位  <br/> |  <br/> |
|证书的密钥长度  <br/> |2048  <br/> |
   
 **弃用证书信息在 2018 年 9 月 3 日之前有效**
  
为了帮助确保顺利过渡，我们将在一段时间内继续提供旧的证书信息供你参考，不过，你应从现在开始使用当前证书信息。
  
****

|**属性**|**值**|
|:-----|:-----|
|证书颁发机构根颁发者  <br/> |Baltimore CyberTrust 根  <br/> |
|证书名称  <br/> |mail.protection.outlook.com  <br/> |
|组织  <br/> |Microsoft Corporation  <br/> |
|组织单位  <br/> |Microsoft Corporation  <br/> |
|证书的密钥长度  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>准备新的 Exchange Online 证书

新证书由不同于 Exchange Online 使用的 (CA) 颁发机构颁发。 因此，您可能需要执行一些操作才能使用新证书。

作为验证证书的一部分，新证书需要连接到新 CA 的终结点。 如果不这样做，可能会导致邮件流受到负面影响。 如果使用仅允许邮件服务器连接到特定目的地的防火墙保护邮件服务器，则需要检查服务器能否验证新证书。 若要确认服务器可以使用新证书，请完成以下步骤：

1. 使用 Exchange Server 连接到本地Windows PowerShell，然后运行以下命令：  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. 在出现的窗口中，选择"检索 **"。**
3. 当实用工具完成检查时，它将返回一个状态。 如果状态显示为 **"确定**"，则您的邮件服务器可以成功验证新证书。 如果没有，则需要确定导致连接失败的原因。 很可能需要更新防火墙的设置。 需要访问的终结点的完整列表包括：
    - ocsp.globalsign.com
     - crl.globalsign.com
     - secure.globalsign.com   

正常情况下，你通过 Windows 更新自动接收根证书更新。 但是，某些部署具有防止自动发生这些更新的其他安全性。 在这些锁定的部署中，Windows 更新无法自动更新根证书，您需要通过完成以下步骤来确保安装了正确的根 CA 证书：
1.  使用 Exchange Server 连接到本地Windows PowerShell，然后运行以下命令：  
  `certmgr.msc`
2. 在 **"受信任的根证书颁发机构/证书**"下，确认新证书已列出。

## <a name="get-more-information-about-tls-and-microsoft-365"></a>获取有关 TLS 和 Microsoft 365 详细信息

有关受支持的密码套件的列表，请参阅有关 [加密的技术参考详细信息](technical-reference-details-about-encryption.md)。
  
[将连接器设置为确保与合作伙伴组织之间实现安全的邮件流](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[电子邮件安全性已提高的连接器](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Microsoft 365 中的加密](encryption.md)
  

