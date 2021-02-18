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
description: 了解 Exchange Online Protection 和 Exchange Online 中 DKIM 签名邮件的验证
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9da41cc7918b36e1aa6a4a8cc48aea6cd2a865c6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290257"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>支持 DKIM 签名邮件验证

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online Protection (EOP) 和 Exchange Online 都支持对标识为 [DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt) 邮件的域密钥 (邮件) 验证。

DKIM 验证电子邮件不是由其他人欺骗的，并且发送自它所声称的域。  它将电子邮件与发送它的组织链接在一起。 DKIM 验证将自动用于使用 IPv6 发送的所有邮件。 通过 IPv4 发送邮件时，Microsoft 365 还支持 DKIM。  (有关 IPv6 支持详细信息，请参阅通过 [IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).) 

DKIM 验证出现在邮件头的DKIM-Signature数字签名邮件。 验证结果DKIM-Signature标记在Authentication-Results标头中。 邮件标头文本将如下所示（其中 contoso.com 是发件人）：

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> 有关邮件头Authentication-Results，请参阅 RFC 7001 ([Message Header Field for Indicating Message Authentication Status.](https://www.rfc-editor.org/rfc/rfc7001.txt) Microsoft 的 DKIM 实现符合此 RFC。

管理员可以创建 Exchange [邮件流规则 (](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) DKIM 验证结果) 传输规则。 这些邮件流规则将允许管理员根据需要筛选或路由邮件。
