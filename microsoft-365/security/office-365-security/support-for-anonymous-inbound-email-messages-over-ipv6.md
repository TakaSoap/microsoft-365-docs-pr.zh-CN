---
title: 添加对通过 IPv6 发送的匿名入站电子邮件的支持
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在 Exchange Online 和 Exchange Online Protection 中配置来自 IPv6 源的匿名入站电子邮件支持。
ms.openlocfilehash: f2e14fe2e8e46d6085fc3764d3a41382f15049e9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950290"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>在 Microsoft 365 中添加对通过 IPv6 的匿名入站电子邮件的支持

使用 Exchange Online 邮箱和独立 Exchange Online Protection 的 Microsoft 365 组织 (EOP) 不带 Exchange Online 邮箱的组织都支持通过 IPv6 的匿名入站电子邮件。 源 IPv6 电子邮件服务器必须满足以下两项要求：

- 源 IPv6 地址必须具有有效的反向 DNS 查找 (PTR) 记录允许目标从 IPv6 地址查找域名。

- 发件人必须通过 SPF 验证（在 [RFC 7208](https://tools.ietf.org/html/rfc7208) 中定义）或 [DKIM 验证](http://dkim.org/)（在 [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) 中定义）。

在您的组织可以通过 IPv6 接收匿名入站电子邮件之前，管理员需要联系 Microsoft 支持部门并要求提供此电子邮件。 有关如何打开支持请求的说明，请参阅 [联系支持人员以获取商业产品-管理员帮助](../../admin/contact-support-for-business-products.md)。

在组织中启用匿名入站 IPv6 邮件支持后，邮件将通过服务提供的常规邮件筛选功能。

## <a name="troubleshooting"></a>故障排除

- 如果源电子邮件服务器没有 IPv6 反向 DNS 查找记录，则邮件将被拒绝，并出现以下错误：

  > 450 4.7.25 服务不可用，发送 IPv6 地址 [2a01：111： f200：2004：： 240] 必须有反向 DNS 记录。

- 如果发件人未通过 SPF 或 DKIM 验证，则邮件将被拒绝，并出现以下错误：

  > 450 4.7.26 服务不可用，通过 IPv6 发送的邮件 [2a01：111： f200：2004：： 240] 必须通过 SPF 或 DKIM 验证。

- 如果您在选择加入之前尝试接收匿名 IPv6 邮件，则邮件将被拒绝，并显示以下错误：

  > 550 5.2.1 服务不可用，[contoso.com] 不接受通过 IPv6 的电子邮件。

## <a name="related-topics"></a>相关主题

[支持 DKIM 签名邮件验证](support-for-validation-of-dkim-signed-messages.md)