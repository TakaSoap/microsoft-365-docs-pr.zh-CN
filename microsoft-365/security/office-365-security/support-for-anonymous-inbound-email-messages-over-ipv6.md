---
title: 添加对通过 IPv6 发送的匿名入站电子邮件的支持
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何配置对来自 iPv6 源的匿名入站电子邮件的支持，Exchange Online Exchange Online Protection。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ba52efb6ad18bc0515084b3aee4a8bbdd6c7312
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203863"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>在电子邮件中添加对通过 IPv6 的匿名入站Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365邮箱和独立 Exchange Online EOP Exchange Online Protection (组织) 没有 Exchange Online 邮箱的组织支持通过 IPv6 发送的匿名入站电子邮件。 源 IPv6 电子邮件服务器必须满足以下两个要求：

- 源 IPv6 地址必须具有有效的反向 DNS (PTR) 记录，该记录允许目标从 IPv6 地址查找域名。

- 发件人必须通过 SPF 验证（在 [RFC 7208](https://tools.ietf.org/html/rfc7208) 中定义）或 [DKIM 验证](http://dkim.org/)（在 [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) 中定义）。

在组织可以通过 IPv6 接收匿名入站电子邮件之前，管理员需要联系 Microsoft 支持人员并请求获取。 有关如何打开支持请求的说明，请参阅联系商业产品支持 [人员 - 管理员帮助](../../business-video/get-help-support.md)。

在组织中启用匿名入站 IPv6 邮件支持后，邮件将经过该服务提供的正常邮件筛选。

## <a name="troubleshooting"></a>疑难解答

- 如果源电子邮件服务器没有 IPv6 反向 DNS 查找记录，邮件将被拒绝，并出现以下错误：

  > 450 4.7.25 服务不可用，发送 IPv6 地址 [2a01：111：f200：2004：：240] 必须具有反向 DNS 记录。

- 如果发件人未通过 SPF 或 DKIM 验证，邮件将被拒绝，并出现以下错误：

  > 450 4.7.26 服务不可用，通过 IPv6 发送的邮件 [2a01：111：f200：2004：：240] 必须通过 SPF 或 DKIM 验证。

- 如果在选择加入之前尝试接收匿名 IPv6 邮件，邮件将被拒绝，并出现以下错误：

  > 550 5.2.1 服务不可用，[contoso.com] 不接受通过 IPv6 的电子邮件。

## <a name="related-topics"></a>相关主题

[支持 DKIM 签名邮件验证](support-for-validation-of-dkim-signed-messages.md)
