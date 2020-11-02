---
title: Microsoft 365 中的电子邮件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: 比较 Microsoft 365 加密选项，其中包括 Office 邮件加密 (OME)、S/MIME、信息权限管理 (IRM)，并了解传输层安全性 (TLS)。
ms.openlocfilehash: 81ce8ca567c2b696060a1dd41b9af06bfc7b94a7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769050"
---
# <a name="email-encryption"></a>电子邮件加密

本文比较了 Microsoft 365 中的加密选项，其中包括 Office 邮件加密 (OME)、S/MIME、信息权限管理 (IRM)，并介绍了传输层安全性 (TLS)。
  
Microsoft 365 delivers multiple encryption options to help you meet your business needs for email security. This article presents three ways to encrypt email in Office 365. If you want to learn more about all security features in Office 365, visit the [Office 365 Trust Center](https://go.microsoft.com/fwlink/p/?LinkID=282470). This article introduces the three types of encryption available for Microsoft 365 administrators to help secure email in Office 365:
  
- Office 邮件加密 (OME)。

- 安全/多用途 Internet 邮件扩展 (S/MIME)。

- 信息权限管理 (IRM)。

## <a name="email-encryption-and-how-microsoft-365-uses-it"></a>电子邮件加密以及 Microsoft 365 如何使用该功能

Encryption is the process by which information is encoded so that only an authorized recipient can decode and consume the information. Microsoft 365 uses encryption in two ways: in the service, and as a customer control. In the service, encryption is used in Microsoft 365 by default; you don't have to configure anything. For example, Microsoft 365 uses Transport Layer Security (TLS) to encrypt the connection, or session, between two servers. 
  
以下是电子邮件加密的一般工作原理：
  
- 邮件在发件人的计算机上或在传输过程中由中央服务器进行加密，或从纯文本转换成无法读取的已加密文本。

- 邮件在传输过程中始终处于加密状态，以防止其遭截获后被他人读取。

- 一旦收件人收到邮件，邮件将通过两种方式之一转换回可读的纯文本：

  - 收件人的计算机使用密钥解密邮件，或

  - 中央服务器在验证了收件人的身份后代表收件人对邮件进行解密。

有关 Microsoft 365 如何保护服务器之间的通信（例如，Microsoft 365 内的组织之间的通信，或者 Microsoft 365 与 Microsoft 365 外部受信任的业务合作伙伴之间的通信）安全的详细信息，请参阅 [Exchange Online 如何使用 TLS 保护 Office 365 中的电子邮件连接](exchange-online-uses-tls-to-secure-email-connections.md)。
  
观看此视频，了解关于 [Office 365 中的加密](https://www.youtube.com/watch?v=KmfxCd5ublI)的简介。
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Office 365 中的电子邮件加密选项比较

||![介绍 OME 的概念性插图](../media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![介绍 IRM 的概念性插图](../media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![介绍 SMIME 的概念性插图](../media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|这是什么？|Office 365 邮件加密 (OME) 是一项基于 Azure 权限管理 (Azure RMS) 构建的服务，允许您向组织内外发送经加密的电子邮件，而无需考虑目标电子邮件地址（Gmail、Yahoo!Mail、Outlook.com 等）。 <br/> 作为管理员，您可以设置定义加密条件的传输规则。当用户发送的邮件与规则匹配时，则自动应用加密。 <br/> To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Office 365. Recipients can also send encrypted replies. They don't need a Microsoft 365 subscription to view encrypted messages or send encrypted replies.|IRM 是一种加密解决方案，还可向电子邮件应用用法限制。它可以帮助防止未经授权的人员打印、转发或复制敏感信息。 <br/> Microsoft 365 中的 IRM 功能使用 Azure 权限管理 (Azure RMS)。|S/MIME is a certificate-based encryption solution that allows you to both encrypt and digitally sign a message. The message encryption helps ensure that only the intended recipient can open and read the message. A digital signature helps the recipient validate the identity of the sender. <br/> 数字签名和邮件加密都可通过使用包含用于验证数字签名和加密或解密邮件的密钥的唯一数字证书来实现。 <br/> To use S/MIME, you must have public keys on file for each recipient. Recipients have to maintain their own private keys, which must remain secure. If a recipient's private keys are compromised, the recipient needs to get a new private key and redistribute public keys to all potential senders.|
|它会做什么？|OME： <br/> 对发送到内部或外部收件人的邮件进行加密。 <br/>  允许用户将加密的邮件发送到任何电子邮件地址，包括 Outlook.com、Yahoo!Mail 和 Gmail。 <br/>  允许你作为管理员自定义电子邮件查看门户以反映你的组织的品牌。 <br/> Microsoft 以安全的方式管理和存储密钥，因此你不必如此做。 <br/> 只要加密邮件（作为 HTML 附件发送）可以在浏览器中打开，就无需特殊的客户端软件。|IRM： <br/> 使用加密和用法限制为电子邮件和附件提供联机和脱机保护。 <br/> 使您能够作为管理员设置传输规则或 Outlook 保护规则，以自动将 IRM 应用到选定邮件。 <br/> 允许用户手动应用 Outlook 或 Outlook 网页版（以前称为 Outlook Web App）中的模板。|S/MIME 通过数字签名对发件人进行身份验证，并通过加密实现邮件保密性。|
|它不会做什么？|OME doesn't let you apply usage restrictions to messages. For example, you can't use it to stop a recipient from forwarding or printing an encrypted message.|Some applications may not support IRM emails on all devices. For more information about these and other products that support IRM email, see [Client device capabilities](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities).|S/MIME 不允许对加密邮件进行恶意软件、垃圾邮件或策略扫描。|
|建议和示例场景|We recommend using OME when you want to send sensitive business information to people outside your organization, whether they're consumers or other businesses. For example:  <br/>  银行员工向客户发送信用卡对帐单  <br/>  诊所向患者发送病历  <br/>  律师向其他律师发送机密的法律信息|当您想要同时应用用法限制和加密时，我们建议使用 IRM。例如：  <br/>  经理在将有关新产品的机密详细信息发送至其团队时可应用“请勿转发”选项。  <br/>  高级管理人员需要与另一家公司共享投标方案，其中包括来自使用 Office 365 的合作伙伴的附件，并要求保护该电子邮件及其附件。|我们建议在你的组织或收件人的组织需要真正的对等加密时使用 S/MIME。  <br/>  S/MIME 最常用于以下场景：  <br/>  政府机构之间的通信  <br/>  企业与政府机构之间的通信|
||

如果同时使用 [Azure 信息保护](https://docs.microsoft.com/microsoft-365/compliance/protect-information)和电子邮件加密来保护数据，请考虑以下事项：
- 可将敏感度标签与 OME 和 IRM 加密配合使用。 有关详细信息，请参阅[通过敏感度标签应用加密，从而限制对内容的访问](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#what-happens-to-existing-encryption-when-a-labels-applied)。
- 可将敏感度标签应用于使用 S/MIME 进行数字签名的电子邮件。
- 无法将敏感度标签应用于使用 S/MIME 进行加密的电子邮件，因为受端到端加密保护的邮件并非由策略进行处理。

## <a name="encryption-options-available-for-my-microsoft-365-subscription"></a>可供我的 Microsoft 365 订阅使用的加密选项

有关 Microsoft 365 订阅的电子邮件加密选项的信息，请参阅 [Exchange Online 服务说明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)。 在此处，您可以查看有关以下加密功能的信息：

- Azure RMS，包括 IRM 功能和新的 OME 功能

- S/MIME

- TLS

- 静止数据的加密（通过 BitLocker）

还可将第三方加密工具与 Microsoft 365 结合使用，例如 PGP（优良保密协议）。 Microsoft 365 不支持 PGP/MIME，你只能使用 PGP/内联方式发送和接收 PGP 加密的电子邮件。

## <a name="what-about-encryption-for-data-at-rest"></a>静止数据的加密是怎么样的？

“静止数据”是指当前未处于传输中的数据。 在 Microsoft 365 中，静止电子邮件数据使用 BitLocker 驱动器加密进行加密。 BitLocker 对 Microsoft 数据中心中的硬盘进行加密，以更好地防止未经授权的访问。 若要了解详细信息，请参阅 [BitLocker 概述](https://go.microsoft.com/fwlink/p/?LinkId=394737)。
  
## <a name="more-information-about-email-encryption-options"></a>有关电子邮件加密选项的详细信息

有关本文提及的电子邮件加密选项和 TLS 的详细信息，请参阅以下文章：
  
**OME**
  
[Office 365 邮件加密 (OME)](ome.md)
  
**IRM**
  
[Exchange Online 中的信息权限管理](https://technet.microsoft.com/library/jj983436%28v=exchg.150%29.aspx)
  
[什么是 Azure 权限管理？](https://technet.microsoft.com/library/jj585026)
  
**S/MIME**
  
[将 S/MIME 用于邮件签名和加密](https://technet.microsoft.com/library/dn626158)
  
[了解 S/MIME](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[了解公钥加密](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
**TLS**
  
[使用连接器配置自定义邮件流](https://technet.microsoft.com/library/jj723138%28v=exchg.150%29.aspx)
