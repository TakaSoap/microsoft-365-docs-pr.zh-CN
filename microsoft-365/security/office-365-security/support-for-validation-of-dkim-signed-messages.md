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
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="7f18b-103">支持 DKIM 签名邮件验证</span><span class="sxs-lookup"><span data-stu-id="7f18b-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7f18b-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="7f18b-104">**Applies to**</span></span>
- [<span data-ttu-id="7f18b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7f18b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7f18b-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="7f18b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="7f18b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f18b-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="7f18b-108">Exchange Online Protection (EOP) 和 Exchange Online 都支持对标识为 [DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt) 邮件的域密钥 (邮件) 验证。</span><span class="sxs-lookup"><span data-stu-id="7f18b-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="7f18b-109">DKIM 验证电子邮件不是由其他人欺骗的，并且发送自它所声称的域。 </span><span class="sxs-lookup"><span data-stu-id="7f18b-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="7f18b-110">它将电子邮件与发送它的组织链接在一起。</span><span class="sxs-lookup"><span data-stu-id="7f18b-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="7f18b-111">DKIM 验证将自动用于使用 IPv6 发送的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="7f18b-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="7f18b-112">通过 IPv4 发送邮件时，Microsoft 365 还支持 DKIM。</span><span class="sxs-lookup"><span data-stu-id="7f18b-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="7f18b-113"> (有关 IPv6 支持详细信息，请参阅通过 [IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).) </span><span class="sxs-lookup"><span data-stu-id="7f18b-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="7f18b-114">DKIM 验证出现在邮件头的DKIM-Signature数字签名邮件。</span><span class="sxs-lookup"><span data-stu-id="7f18b-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="7f18b-115">验证结果DKIM-Signature标记在Authentication-Results标头中。</span><span class="sxs-lookup"><span data-stu-id="7f18b-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="7f18b-116">邮件标头文本将如下所示（其中 contoso.com 是发件人）：</span><span class="sxs-lookup"><span data-stu-id="7f18b-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="7f18b-117">有关邮件头Authentication-Results，请参阅 RFC 7001 ([Message Header Field for Indicating Message Authentication Status.](https://www.rfc-editor.org/rfc/rfc7001.txt)</span><span class="sxs-lookup"><span data-stu-id="7f18b-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="7f18b-118">Microsoft 的 DKIM 实现符合此 RFC。</span><span class="sxs-lookup"><span data-stu-id="7f18b-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="7f18b-119">管理员可以创建 Exchange [邮件流规则 (](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) DKIM 验证结果) 传输规则。</span><span class="sxs-lookup"><span data-stu-id="7f18b-119">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="7f18b-120">这些邮件流规则将允许管理员根据需要筛选或路由邮件。</span><span class="sxs-lookup"><span data-stu-id="7f18b-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>
