---
title: Exchange Online 加密的 S/MIME - Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 管理员可以了解在 Exchange Online 中使用 S/MIME 和 (Internet 邮件扩展) 来加密电子邮件并对其进行数字签名。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca865fa8ef658b4715d18e09fe9cbc1cffb201e6
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845916"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>用于 Exchange Online 中的邮件签名和加密的 S/MIME

S/MIME (/多用途 Internet 邮件扩展) 是一种被广泛接受的方法 (（更加精确）作为用于发送数字) 签名和加密邮件的协议接入。 S/MIME 允许你加密电子邮件，并对它们进行数字签名。 在电子邮件中使用 S/MIME 时，它有助于收到该邮件的人员确保在其收件箱中看到的内容与发件人一起使用。 还可以帮助收到邮件的人员，确保该邮件来自特定发件人，而不是由预先作为发件人的某个发件人发送。 为此，S/MIME 提供了加密安全服务，例如身份验证、邮件完整性和防发送方抵赖（使用数字签名）。 它还有助于通过为电 (加密增强隐私和数据) 性能。 有关电子邮件上下文中 S/MIME 的历史记录和体系结构的更多完整背景，请参阅[了解 S/MIMEE](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))。

作为 Exchange Online 管理员，您可以为您组织的邮箱启用基于 S/MIME 的安全。 使用此处链接主题与 Exchange Online PowerShell 链接的指南设置 S/MIME。 若要在受支持的电子邮件客户端中使用 S/MIME，您组织内部的用户必须具有颁发用于签名和加密用途的证书，并将数据发布到本地 Active Directory 域服务 (AD DS) 。 AD DS 必须位于你控制的物理位置的计算机上，而不是 Internet 上其他位置的远程设施或基于云的服务。 有关 AD DS 的详细信息，请参阅["Active Directory 域服务概述"。](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)

## <a name="supported-scenarios-and-technical-considerations"></a>支持的方案和技术注意事项

可以将 S/MIME 设置为用于以下任一终结点：

- Outlook 2010 或更高版本
- Web 上的 Outlook（以前称为 Outlook Web App）
- Exchange ActiveSync (EAS)

为这些端点设置 S/MIME 时需遵循的步骤可能略有不同。 通常，您需要执行以下步骤：

1. 安装基于 WA 证书颁发机构 (颁发) 设置公钥基础结构来颁发 S/MIME 证书。 另外，还支持由第三方证书提供商颁发的证书。 有关详细信息，请参阅 [Active Directory 证书服务概述](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))。

   **注意**：

   - 由第三方 CA 颁发的证书具有自动受到所有客户端和设备信任的优势。 由内部的专用 CA 颁发的证书不会被客户端和设备自动信任，并且并非所有 (例如，可以将电话) 配置为信任私人证书。

   - 可考虑使用中间证书代替根证书向用户颁发证书。 这样，在你需要吊销和重新颁发证书时，根证书仍然保持不变。

2. 在本地 AD DS 帐户中为 **UserSMIMECertificate** 和/或 **UserCertificate** 属性发布用户证书。

3. 对于 Exchange Online 组织，使用适合的 Azure AD Connect 版本将用户证书从 AD DS 同步到 Azure Active Directory。 然后，这些证书将从 Azure Active Directory 同步到 Exchange Online 目录，并在将邮件加密到收件人时使用。

4. 设置虚拟证书集合以验证 S/MIME。此信息供 Web 上的 Outlook 用于验证电子邮件的签名并确保它是由可信证书签名的。

5. 将 Outlook 或 EAS 终结点设置为使用 S/MIME。

> [!NOTE]
> 无法在 Mac、iOS、Android 版或其他非 Windows 设备上的 Outlook 网页版中安装 S/MIME 控件。 有关详细信息，请参阅使用 [Outlook 网页版中的 S/MIME 加密邮件](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)。

## <a name="setup-smime-with-outlook-on-the-web"></a>设置 Web 上的 Outlook 的 S/MIME

为具有 Web 上的 Outlook 的 Exchange Online 设置 S/MIME 涉及以下关键步骤：

1. [配置 Outlook 网页版的 S/MIME 设置](configure-s-mime-settings-for-outlook-web-app.md)
2. [设置虚拟证书集合以验证 S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [出于 S/MIME 目的将用户证书同步到 Office 365](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>相关邮件加密技术

随后邮件安全性变得更加重要，管理员需要了解安全邮件的原则和概念。 此理解对于不一定的原因在于产品有越来越多的保护相关技术 (包括可用的 S/) MIME 技术。 若要了解有关 S/MIME 以及它在电子邮件上下文中的工作原理的详细信息，请参阅["了解 S/MIME"。](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)) 各种加密技术协同工作，为静态邮件和正在传输的邮件提供保护。 S/MIME 可与以下技术一起使用，但不依赖于这些技术。

- **传输层安全性 (TLS **) 对电子邮件服务器之间的隧道或路由进行加密，以帮助防止 snooping 和 eavesdropping。

- **安全套接 (SSL) ** 安全套接字层会加密电子邮件客户端和 Microsoft 365 服务器之间的连接。

- **BitLocker** 对数据中心中硬盘驱动器上的数据进行加密，以使进行未授权访问的人无法读取数据。

### <a name="smime-compared-with-office-365-message-encryption"></a>与 Office 365 邮件加密比较的 S/MIME

S/MIME 需要证书和发布基础结构，通常用于企业到企业和企业到消费者的情况。 用户控制 S/MIME 中的加密密钥，并且可以选择是否为他们发送的每封邮件使用密钥。 Outlook 等电子邮件程序搜索可信任根证书颁发机构位置，以执行数字签名和签名验证。 Office 365 邮件加密是基于策略的加密服务，可以由管理员配置，而不是个人用户，用于加密发送到组织内外的任何人的邮件。 它是一种基于 Azure 权限管理 (RMS 工具构建) 且不依赖公钥基础结构的在线服务。 Office 365 邮件加密还提供其他功能，例如使用组织品牌自定义邮件的功能。 有关 Office 365 邮件加密的详细信息，请参阅 [Office 365 中的加密](https://docs.microsoft.com/microsoft-365/compliance/encryption)。

## <a name="more-information"></a>更多信息

[Outlook 网页版](https://docs.microsoft.com/exchange/exchange-admin-center)

[安全邮件 (2000) ](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
