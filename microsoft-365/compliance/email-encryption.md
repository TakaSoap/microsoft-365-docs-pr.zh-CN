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
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: 比较 Microsoft 365 加密选项，其中包括 Office 邮件加密 (OME)、S/MIME、信息权限管理 (IRM)，并了解传输层安全性 (TLS)。
ms.openlocfilehash: 1d6ad4f595652b39ff6e984afe096272a7920c4d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60167266"
---
# <a name="email-encryption"></a>电子邮件加密

本文比较了 Microsoft 365 中的加密选项，其中包括 Office 365 邮件加密 (OME)、S/MIME、信息权限管理 (IRM)，并介绍了传输层安全性 (TLS)。
  
Microsoft 365 提供了多个加密选项，可帮助你满足电子邮件安全性的业务需求。 本文介绍了在 Office 365 中加密电子邮件的三种方法。 如果想要了解有关 Office 365 中所有安全功能的详细信息，请访问 [Office 365 信任中心](https://go.microsoft.com/fwlink/p/?LinkID=282470)。 本文介绍了三类可供 Microsoft 365 管理员使用的加密方式，以帮助其保护 Office 365 中的电子邮件：
  
- Office 邮件加密 (OME)。

- 安全/多用途 Internet 邮件扩展 (S/MIME)。

- 信息权限管理 (IRM)。

## <a name="how-microsoft-365-uses-email-encryption"></a>电子邮件加密以及 Microsoft 365 如何使用该功能

加密是将信息进行编码以便只有经过授权的收件人可以解码和使用信息的过程。Microsoft 365 使用两种方式加密：一种是在服务中实施加密，另一种是将其作为客户控件。在服务中，Microsoft 365 默认使用加密，你无需进行任何配置。例如，Microsoft 365 使用传输层安全性 (TLS) 加密两个服务器之间的连接或会话。 
  
以下是电子邮件加密的一般工作原理：
  
- 邮件在发件人的计算机上或在传输过程中由中央服务器进行加密，或从纯文本转换成无法读取的已加密文本。

- 邮件在传输过程中始终处于加密状态，以防止其遭截获后被他人读取。

- 一旦收件人收到邮件，邮件将通过两种方式之一转换回可读的纯文本：

  - 收件人的计算机使用密钥解密邮件，或

  - 中央服务器在验证了收件人的身份后代表收件人对邮件进行解密。

有关 Microsoft 365 如何保护服务器之间的通信（例如，Microsoft 365 内的组织之间的通信，或者 Microsoft 365 与 Microsoft 365 外部受信任的业务合作伙伴之间的通信）安全的详细信息，请参阅 [Exchange Online 如何使用 TLS 保护 Office 365 中的电子邮件连接](exchange-online-uses-tls-to-secure-email-connections.md)。
    
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Office 365 中的电子邮件加密选项比较

|电子邮件加密|![介绍 OME 的概念性插图。](../media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![介绍 IRM 的概念性插图](../media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![介绍 SMIME 的概念性插图](../media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|这是什么？|Office 365 邮件加密 (OME) 是一项基于 Azure 权限管理 (Azure RMS) 构建的服务，允许您向组织内外发送经加密的电子邮件，而无需考虑目标电子邮件地址（Gmail、Yahoo!Mail、Outlook.com 等）。 <br/> 作为管理员，您可以设置定义加密条件的传输规则。当用户发送的邮件与规则匹配时，则自动应用加密。 <br/> 若要查看加密邮件，收件人可以使用一次性密码、通过 Microsoft 帐户登录或使用与 Office 365 关联的工作或学校帐户登录。此外，收件人也可发送加密回复。他们无需 Microsoft 365 订阅就可以查看加密邮件或发送加密回复。|IRM 是一种加密解决方案，还可向电子邮件应用用法限制。它可以帮助防止未经授权的人员打印、转发或复制敏感信息。 <br/> Microsoft 365 中的 IRM 功能使用 Azure 权限管理 (Azure RMS)。|S/MIME 是一种基于证书的加密解决方案，其允许你对邮件进行加密和数字签名。邮件加密有助于确保只有预期收件人可以打开并阅读该邮件。数字签名帮助收件人验证发件人的身份。 <br/> 数字签名和邮件加密都可通过使用包含用于验证数字签名和加密或解密邮件的密钥的唯一数字证书来实现。 <br/> 若要使用 S/MIME，你必须在文件上具有各个收件人的公钥。收件人必须维护其自己的私钥，必须保持安全。如果收件人的私钥损坏，收件人需要获取新的私钥并将公钥重新分发到所有潜在的发件人。|
|它会做什么？|OME： <br/> 对发送到内部或外部收件人的邮件进行加密。 <br/>  允许用户将加密的邮件发送到任何电子邮件地址，包括 Outlook.com、Yahoo!Mail 和 Gmail。 <br/>  允许你作为管理员自定义电子邮件查看门户以反映你的组织的品牌。 <br/> Microsoft 以安全的方式管理和存储密钥，因此你不必如此做。 <br/> 只要加密邮件（作为 HTML 附件发送）可以在浏览器中打开，就无需特殊的客户端软件。|IRM： <br/> 使用加密和用法限制为电子邮件和附件提供联机和脱机保护。 <br/> 使您能够作为管理员设置传输规则或 Outlook 保护规则，以自动将 IRM 应用到选定邮件。 <br/> 允许用户手动应用 Outlook 或 Outlook 网页版（以前称为 Outlook Web App）中的模板。|S/MIME 通过数字签名对发件人进行身份验证，并通过加密实现邮件保密性。|
|它不会做什么？|OME 不允许你将用法限制应用于邮件。例如，你不能使用它来阻止收件人转发或打印加密邮件。|某些应用程序可能并不是在所有设备上都支持 IRM 电子邮件。 有关支持 IRM 电子邮件的这些和其他产品的详细信息，请参阅[客户端设备功能](/azure/information-protection/requirements#BKMK_ClientCapabilities)。|S/MIME 不允许对加密邮件进行恶意软件、垃圾邮件或策略扫描。|
|建议和示例场景|当你想要将敏感业务信息发送到组织之外的人员时，无论他们是消费者还是其他企业，我们建议使用 OME。例如：  <br/>  银行员工向客户发送信用卡对帐单  <br/>  诊所向患者发送病历  <br/>  律师向其他律师发送机密的法律信息|当您想要同时应用用法限制和加密时，我们建议使用 IRM。例如：  <br/>  经理在将有关新产品的机密详细信息发送至其团队时可应用“请勿转发”选项。  <br/>  高级管理人员需要与另一家公司共享投标方案，其中包括来自使用 Office 365 的合作伙伴的附件，并要求保护该电子邮件及其附件。|我们建议在你的组织或收件人的组织需要真正的对等加密时使用 S/MIME。  <br/>  S/MIME 最常用于以下场景：  <br/>  政府机构之间的通信  <br/>  企业与政府机构之间的通信|
||

## <a name="what-encryption-options-are-available-for-my-microsoft-365-subscription"></a>可供我的 Microsoft 365 订阅使用的加密选项有哪些？

有关 Microsoft 365 订阅的电子邮件加密选项的信息，请参阅 [Exchange Online 服务说明](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)。 在此处，您可以查看有关以下加密功能的信息：
  
- Azure RMS，包括 IRM 功能和 OME 功能

- S/MIME

- TLS

- 静止数据的加密（通过 BitLocker）

还可将第三方加密工具与 Microsoft 365 结合使用，例如 PGP（优良保密协议）。 Microsoft 365 不支持 PGP/MIME，你只能使用 PGP/内联方式发送和接收 PGP 加密的电子邮件。

## <a name="what-about-encryption-for-data-at-rest"></a>静止数据的加密是怎么样的？

“静止数据”是指当前未处于传输中的数据。 在 Microsoft 365 中，静止电子邮件数据使用 BitLocker 驱动器加密进行加密。 BitLocker 对 Microsoft 数据中心中的硬盘进行加密，以更好地防止未经授权的访问。 若要了解详细信息，请参阅 [BitLocker 概述](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831713(v=ws.11))。
  
## <a name="more-information-about-email-encryption-options"></a>有关电子邮件加密选项的详细信息

有关本文提及的电子邮件加密选项和 TLS 的详细信息，请参阅以下文章：
  
**OME**
  
[Office 365 邮件加密 (OME)](ome.md)
  
**IRM**
  
[Exchange Online 中的信息权限管理](./information-rights-management-in-exchange-online.md)
  
[什么是 Azure 权限管理？](/azure/information-protection/what-is-azure-rms)
  
**S/MIME**
  
[将 S/MIME 用于邮件签名和加密](/Exchange/policy-and-compliance/smime/smime)
  
[了解 S/MIME](/previous-versions/tn-archive/aa995740(v=exchg.65))
  
[了解公钥加密](/previous-versions/tn-archive/aa998077(v=exchg.65))
  
**TLS**
  
[使用连接器配置自定义邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
