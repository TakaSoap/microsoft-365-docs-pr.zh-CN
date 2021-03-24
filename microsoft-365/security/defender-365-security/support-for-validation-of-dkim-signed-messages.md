---
title: 对验证已识别的域密钥的邮件 (DKIM) 签名邮件的支持
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
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055504"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="eabe9-103">支持 DKIM 签名邮件验证</span><span class="sxs-lookup"><span data-stu-id="eabe9-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eabe9-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="eabe9-104">**Applies to**</span></span>
- [<span data-ttu-id="eabe9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="eabe9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="eabe9-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="eabe9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eabe9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eabe9-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="eabe9-108">Exchange Online Protection (EOP) 和 Exchange Online 都支持对 [DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt) 邮件的域密钥识别 (入站) 验证。</span><span class="sxs-lookup"><span data-stu-id="eabe9-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="eabe9-109">DKIM 验证电子邮件是否被其他人欺骗，并且发送自它所 *声称的域*。</span><span class="sxs-lookup"><span data-stu-id="eabe9-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="eabe9-110">它将电子邮件与发送它的组织链接在一起。</span><span class="sxs-lookup"><span data-stu-id="eabe9-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="eabe9-111">DKIM 验证将自动用于使用 IPv6 发送的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="eabe9-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="eabe9-112">通过 IPv4 发送邮件时，Microsoft 365 还支持 DKIM。</span><span class="sxs-lookup"><span data-stu-id="eabe9-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="eabe9-113"> (有关 IPv6 支持的信息，请参阅支持通过 [IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).) </span><span class="sxs-lookup"><span data-stu-id="eabe9-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="eabe9-114">DKIM 验证显示在邮件头的 DKIM-Signature 标头中的数字签名邮件。</span><span class="sxs-lookup"><span data-stu-id="eabe9-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="eabe9-115">验证结果DKIM-Signature标记在Authentication-Results标头中。</span><span class="sxs-lookup"><span data-stu-id="eabe9-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="eabe9-116">邮件标头文本将如下所示（其中 contoso.com 是发件人）：</span><span class="sxs-lookup"><span data-stu-id="eabe9-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="eabe9-117">有关邮件头Authentication-Results，请参阅 RFC 7001 [ (Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)。</span><span class="sxs-lookup"><span data-stu-id="eabe9-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="eabe9-118">Microsoft 的 DKIM 实现符合此 RFC。</span><span class="sxs-lookup"><span data-stu-id="eabe9-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="eabe9-119">管理员可以创建 Exchange [邮件流规则， (](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) DKIM 验证结果) 传输规则。</span><span class="sxs-lookup"><span data-stu-id="eabe9-119">Admins can create Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="eabe9-120">这些邮件流规则将允许管理员根据需要筛选或路由邮件。</span><span class="sxs-lookup"><span data-stu-id="eabe9-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>