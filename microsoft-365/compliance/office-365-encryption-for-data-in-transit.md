---
title: 加密传输中的数据
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 在本文中，我们将简单说明 Microsoft 如何在传输过程中加密 Microsoft 365 客户数据。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7ee869308549398a9df00ed42975b4aeedb666a4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033600"
---
# <a name="encryption-for-data-in-transit"></a>加密传输中的数据

除了保护静态客户数据之外，Microsoft 还使用加密技术来保护传输中的客户数据。 

数据在传输中：

- 当客户端计算机与 Microsoft 服务器通信时;
- 当 Microsoft 服务器与另一台 Microsoft 服务器通信时;并
- 当 Microsoft 服务器与非 Microsoft 服务器通信时（例如，Exchange Online 将电子邮件传递到第三方电子邮件服务器）。

Microsoft 服务器之间的数据中心之间的通信通过 TLS 或 IPsec 进行，所有面向客户的服务器都使用 TLS 与客户端计算机协商安全会话（例如，Exchange Online 使用带256位密码强度的 TLS 1.2 （FIPS 140-2 级别2验证）。 （有关 Office 365 支持的 TLS 密码套件列表的[加密的技术参考详细信息](technical-reference-details-about-encryption.md)，请参阅。）这适用于客户端（如 Outlook、Skype for Business、Microsoft 团队和 web 上的 Outlook）使用的协议（例如，HTTP、POP3 等）。

公共证书由 Microsoft IT SSL 使用 SSLAdmin （一个内部 Microsoft 工具）颁发，以保护传输信息的机密性。 Microsoft 颁发的所有证书的长度都至少为2048位，并且 Webtrust 合规性要求 SSLAdmin 确保仅将证书颁发给 Microsoft 拥有的公用 IP 地址。 任何无法满足此条件的 IP 地址都将通过异常过程进行路由。

所有实现详细信息（如使用的 TLS 版本、是否已启用向前保密（FS））都可公开使用密码套件等的顺序。 查看这些详细信息的一种方法是使用第三方网站，如[QUALYS SSL 实验室](https://www.ssllabs.com)。 以下是来自 Qualys 的自动测试页面的链接，这些页面显示以下服务的信息：

- [Office 365 门户](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [Skype for Business （SIP）](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [Skype for Business （Web）](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

对于 Exchange Online Protection，Url 会因租户名称而异;但是，所有客户都可以使用**microsoft-com.mail.protection.outlook.com**测试 Microsoft 365。
