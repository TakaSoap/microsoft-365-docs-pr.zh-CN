---
title: 用于加密的 S/MIME Exchange Online - Office 365
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
description: 管理员可以了解如何使用 S/MIME (安全/多用途 Internet 邮件扩展) Exchange Online 加密电子邮件并对其进行数字签名。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d189bf7f52dd6f9fb11dc360c17d5fe15729c9fa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203575"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>用于邮件签名和加密的 S/MIME Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (安全/多用途 Internet 邮件扩展) 是一种广泛使用的方法 (更确切地说是一种协议) ，用于发送数字签名和加密邮件。 S/MIME 允许你加密电子邮件，并对它们进行数字签名。 当您将 S/MIME 与电子邮件一同使用时，它可以帮助接收该邮件的人确定其收件箱中显示的邮件与发件人一起启动的确切邮件。 它还可以帮助接收邮件的人确保邮件来自特定发件人，而不是冒充发件人的人。 为此，S/MIME 提供了加密安全服务，例如身份验证、邮件完整性和防发送方抵赖（使用数字签名）。 它还有助于增强使用加密技术 (电子邮件) 隐私和数据安全性。 有关电子邮件上下文中 S/MIME 的历史记录和体系结构的更多完整背景，请参阅[了解 S/MIMEE](/previous-versions/tn-archive/aa995740(v=exchg.65))。

作为Exchange Online管理员，您可以为组织中邮箱启用基于 S/MIME 的安全性。 使用此处链接的主题中的指南以及 Exchange Online PowerShell 设置 S/MIME。 若要在受支持的电子邮件客户端中使用 S/MIME，组织中用户必须具有颁发用于签名和加密目的的证书，以及发布到本地 Active Directory 域服务 (AD DS) 的数据。 AD DS 必须位于你控制的物理位置的计算机上，而不是位于 Internet 上的远程设施或基于云的服务上。 有关 AD DS 详细信息，请参阅 [Active Directory 域服务概述](/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)。

## <a name="supported-scenarios-and-technical-considerations"></a>支持的方案和技术注意事项

可以将 S/MIME 设置为用于以下任一终结点：

- Outlook 2010 或更高版本
- Web 上的 Outlook（以前称为 Outlook Web App）
- Exchange ActiveSync (EAS)

使用上述每个结束点设置 S/MIME 的步骤略有不同。 通常，您需要执行以下步骤：

1. 安装基于Windows证书颁发机构 (CA) 并设置公钥基础结构以颁发 S/MIME 证书。 还支持第三方证书提供商颁发的证书。 有关详细信息，请参阅 [Active Directory 证书服务概述](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))。

   **注意**：

   - 由第三方 CA 颁发的证书具有自动受所有客户端和设备信任的优势。 客户端和设备不会自动信任由内部私有 CA 颁发的证书，并且并非所有设备 (例如，可以将电话) 配置为信任专用证书。

   - 请考虑使用中间证书而不是根证书向用户颁发证书。 这样，如果需要撤销和重新颁发证书，根证书将保持不变。

2. 在 **UserSMIMECertificate** 和/或 **UserCertificate** 属性中的本地 AD DS 帐户中发布用户证书。

3. 对于Exchange Online组织，使用适当版本的 Azure AD Azure Active Directory将用户证书从 AD DS 同步连接。 然后，这些证书将Azure Active Directory到Exchange Online，并且将在加密发送给收件人的邮件时使用。

4. 设置虚拟证书集合以验证 S/MIME。此信息供 Web 上的 Outlook 用于验证电子邮件的签名并确保它是由可信证书签名的。

5. 将 Outlook 或 EAS 终结点设置为使用 S/MIME。

> [!NOTE]
> 你不能在 Mac、iOS、Android 或其他非 Outlook 设备上的 Web 设备上安装 S/MIME Windows控件。 有关详细信息，请参阅在 Web 上[使用 S/MIME 加密Outlook邮件](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)。

## <a name="set-up-smime-with-outlook-on-the-web"></a>设置 Web 上的 Outlook 的 S/MIME

为 Web 上的Exchange Online设置 S/MIME Outlook涉及以下关键步骤：

1. [配置 Outlook 网页版的 S/MIME 设置](configure-s-mime-settings-for-outlook-web-app.md)
2. [设置虚拟证书集合以验证 S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [出于 S/MIME 目的将用户证书同步到 Office 365](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>相关邮件加密技术

随着邮件安全变得更加重要，管理员需要了解安全邮件的原则和概念。 这种了解尤为重要，因为可用的保护相关技术 (S/MIME) 也不断增加。 若要了解有关 S/MIME 及其在电子邮件上下文中的工作方式的更多信息，请参阅[了解 S/MIME。](/previous-versions/tn-archive/aa995740(v=exchg.65)) 各种加密技术协同工作，为处于静态和传输状态的邮件提供保护。 S/MIME 可以同时与以下技术一起工作，但不依赖于这些技术：

- **传输层 (TLS**) 加密电子邮件服务器之间的隧道或路由，以帮助防止窃听和窃听。

- **安全套接字层 (SSL)** 加密电子邮件客户端与 Microsoft 365 服务器之间的连接。

- **BitLocker** 对数据中心中硬盘驱动器上的数据进行加密，以便如果有人获得未经授权的访问，他们无法读取数据。

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME 与Office 365 邮件加密

S/MIME 需要证书和发布基础结构，通常用于企业到企业和企业到消费者的情况。 用户控制 S/MIME 中的加密密钥，并且可以选择是否为他们发送的每封邮件使用密钥。 Outlook 等电子邮件程序搜索可信任根证书颁发机构位置，以执行数字签名和签名验证。 Office 365 邮件加密是一种基于策略的加密服务，管理员（而不是单个用户）可配置该服务，以加密发送到组织内部或外部的任何人员的邮件。 它是基于 Azure 权限管理 (RMS) 构建的联机服务，不依赖于公钥基础结构。 Office 365 邮件加密还提供其他功能，例如使用组织品牌自定义邮件的功能。 有关加密Office 365 邮件加密，请参阅加密[Office 365。](../../compliance/encryption.md)

## <a name="more-information"></a>详细信息

[Outlook 网页版](/exchange/exchange-admin-center)

[Secure Mail (2000) ](/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))