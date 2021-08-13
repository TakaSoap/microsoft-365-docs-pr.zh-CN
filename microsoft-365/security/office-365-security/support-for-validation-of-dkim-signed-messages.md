---
title: 支持验证已签名邮件的域密钥 (DKIM) 邮件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: 了解在邮件和邮件中验证 DKIM Exchange Online Protection Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1986ebee428f047d02388e1c30a76a54fa32517208744b2c9fea6cbf327f024
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "56790490"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>支持 DKIM 签名邮件验证

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) 和 Exchange Online 都支持对[DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)邮件中标识的域密钥 (进行) 验证。

DKIM 验证电子邮件是否被其他人欺骗，并且发送自它所 *声称的域*。 它将电子邮件与发送它的组织链接在一起。 DKIM 验证将自动用于使用 IPv6 发送的所有邮件。 Microsoft 365通过 IPv4 发送邮件时，还支持 DKIM。  (有关 IPv6 支持的信息，请参阅支持通过 [IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).) 

DKIM 验证显示在邮件头的 DKIM-Signature 头中的数字签名邮件。 验证结果DKIM-Signature标记在Authentication-Results标头中。 邮件标头文本将如下所示（其中 contoso.com 是发件人）：

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> 有关邮件头Authentication-Results，请参阅 RFC 7001 [ (Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)。 Microsoft 的 DKIM 实现符合此 RFC。

管理员可以创建Exchange[邮件](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (规则，也称为) DKIM 验证结果的传输规则。 这些邮件流规则将允许管理员根据需要筛选或路由邮件。