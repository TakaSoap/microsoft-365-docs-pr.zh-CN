---
title: S/MIME for encryption in Exchange Online - Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 管理员可以了解如何在 Exchange Online 中使用 S/MIME (安全/多用途 Internet 邮件扩展) 加密电子邮件并对其进行数字签名。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 35266b4ceefe161b907ddbc955fd234b716792a6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288569"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>Exchange Online 中邮件签名和加密的 S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (安全/多用途 Internet 邮件扩展) 是一种普遍接受的方法 (或更精确地说，是一种用于发送数字签名和加密邮件的协议) 。 S/MIME 允许你加密电子邮件，并对它们进行数字签名。 当您将 S/MIME 与电子邮件一同使用时，它可帮助接收该邮件的人确定他们在收件箱中看到的内容与发件人所启动的确切邮件一样。 它还可帮助接收邮件的人确保邮件来自特定发件人，而不是冒充发件人的人。 为此，S/MIME 提供了加密安全服务，例如身份验证、邮件完整性和防发送方抵赖（使用数字签名）。 它还有助于增强使用加密技术 (电子) 的隐私和数据安全性。 有关电子邮件上下文中 S/MIME 的历史记录和体系结构的更多完整背景，请参阅[了解 S/MIMEE](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))。

作为 Exchange Online 管理员，您可以为组织中邮箱启用基于 S/MIME 的安全性。 使用此处链接的主题中的指南以及 Exchange Online PowerShell 设置 S/MIME。 若要在受支持的电子邮件客户端中使用 S/MIME，组织中用户必须具有颁发用于签名和加密目的的证书，并且数据必须发布到本地 Active Directory 域服务 (AD DS) 。 AD DS 必须位于您控制的物理位置的计算机上，而不是位于 Internet 上的远程设施或基于云的服务。 有关 AD DS 详细信息，请参阅 [Active Directory 域服务概述](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)。

## <a name="supported-scenarios-and-technical-considerations"></a>支持的方案和技术注意事项

可以将 S/MIME 设置为用于以下任一终结点：

- Outlook 2010 或更高版本
- Web 上的 Outlook（以前称为 Outlook Web App）
- Exchange ActiveSync (EAS)

使用其中每个结束点设置 S/MIME 的步骤略有不同。 通常，需要执行以下步骤：

1. 安装基于 Windows 的证书颁发 (CA) 并设置公钥基础结构以颁发 S/MIME 证书。 还支持由第三方证书提供商颁发的证书。 有关详细信息，请参阅 [Active Directory 证书服务概述](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))。

   **注意**：

   - 由第三方 CA 颁发的证书具有所有客户端和设备自动信任的优势。 客户端和设备不会自动信任由内部私有 CA 颁发的证书，并且并非所有设备 (例如，可以将电话) 配置为信任专用证书。

   - 请考虑使用中间证书而不是根证书向用户颁发证书。 这样，如果你需要撤销和重新颁发证书，根证书仍然保持不变。

2. 在 **UserSMIMECertificate** 和/或 **UserCertificate** 属性中的本地 AD DS 帐户中发布用户证书。

3. 对于 Exchange Online 组织，使用适当版本的 Azure AD Connect 将用户证书从 AD DS 同步到 Azure Active Directory。 然后，这些证书将从 Azure Active Directory 同步到 Exchange Online 目录，并且将在加密发送给收件人的邮件时使用。

4. 设置虚拟证书集合以验证 S/MIME。此信息供 Web 上的 Outlook 用于验证电子邮件的签名并确保它是由可信证书签名的。

5. 将 Outlook 或 EAS 终结点设置为使用 S/MIME。

> [!NOTE]
> 你不能在 Mac、iOS、Android 或其他非 Windows 设备上的 Outlook 网页版中安装 S/MIME 控件。 有关详细信息，请参阅 Outlook 网页中的 [S/MIME 加密邮件](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)。

## <a name="set-up-smime-with-outlook-on-the-web"></a>设置 Web 上的 Outlook 的 S/MIME

使用 Outlook 网页版为 Exchange Online 设置 S/MIME 涉及以下关键步骤：

1. [配置 Outlook 网页版的 S/MIME 设置](configure-s-mime-settings-for-outlook-web-app.md)
2. [设置虚拟证书集合以验证 S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [出于 S/MIME 目的将用户证书同步到 Office 365](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>相关邮件加密技术

随着邮件安全变得更加重要，管理员需要了解安全邮件的原则和概念。 这种了解尤其重要，因为可用的保护相关技术 (包括 S/MIME) 。 若要了解有关 S/MIME 及其在电子邮件上下文中的工作方式，请参阅"了解[S/MIME"。](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)) 各种加密技术协同工作，为静态和传输中的邮件提供保护。 S/MIME 可以同时使用下列技术，但不依赖于这些技术：

- **传输层安全性 (TLS)** 加密电子邮件服务器之间的隧道或路由，以帮助防止窃听和窃听。

- **安全套接字层 (SSL)** 加密电子邮件客户端和 Microsoft 365 服务器之间的连接。

- **BitLocker** 对数据中心中硬盘驱动器上的数据进行加密，以便如果有人获得未经授权的访问，他们无法读取数据。

### <a name="smime-compared-with-office-365-message-encryption"></a>与 Office 365 邮件加密相比的 S/MIME

S/MIME 需要证书和发布基础结构，通常用于企业到企业和企业到消费者的情况。 用户控制 S/MIME 中的加密密钥，并且可以选择是否为他们发送的每封邮件使用密钥。 Outlook 等电子邮件程序搜索可信任根证书颁发机构位置，以执行数字签名和签名验证。 Office 365 邮件加密是一种基于策略的加密服务，管理员可以配置该服务，而不是单个用户，以加密发送到组织内部或外部的任何人的邮件。 它是基于 Azure 权限管理 (RMS) 构建的联机服务，不依赖于公钥基础结构。 Office 365 邮件加密还提供其他功能，例如使用组织品牌自定义邮件的功能。 有关 Office 365 邮件加密的信息，请参阅 [Office 365 中的加密](../../compliance/encryption.md)。

## <a name="more-information"></a>更多信息

[Outlook 网页版](https://docs.microsoft.com/exchange/exchange-admin-center)

[Secure Mail (2000) ](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
