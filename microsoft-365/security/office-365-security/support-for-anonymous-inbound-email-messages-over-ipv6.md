---
title: 添加对通过 IPv6 发送的匿名入站电子邮件的支持
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在 Exchange Online 和 Exchange Online Protection 中配置对来自 IPv6 源的匿名入站电子邮件的支持。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290269"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="31930-103">在 Microsoft 365 中添加对通过 IPv6 的匿名入站电子邮件的支持</span><span class="sxs-lookup"><span data-stu-id="31930-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="31930-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="31930-104">**Applies to**</span></span>
- [<span data-ttu-id="31930-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="31930-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="31930-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="31930-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="31930-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31930-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="31930-108">具有 Exchange Online 邮箱和独立 Exchange Online Protection (EOP) 组织（没有 Exchange Online 邮箱）的 Microsoft 365 组织支持通过 IPv6 发送的匿名入站电子邮件。</span><span class="sxs-lookup"><span data-stu-id="31930-108">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="31930-109">源 IPv6 电子邮件服务器必须满足以下两个要求：</span><span class="sxs-lookup"><span data-stu-id="31930-109">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="31930-110">源 IPv6 地址必须具有有效的反向 DNS (PTR) 记录，该记录允许目标从 IPv6 地址查找域名。</span><span class="sxs-lookup"><span data-stu-id="31930-110">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="31930-111">发件人必须通过 SPF 验证（在 [RFC 7208](https://tools.ietf.org/html/rfc7208) 中定义）或 [DKIM 验证](http://dkim.org/)（在 [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) 中定义）。</span><span class="sxs-lookup"><span data-stu-id="31930-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="31930-112">在组织可以通过 IPv6 接收匿名入站电子邮件之前，管理员需要联系 Microsoft 支持人员并请求它。</span><span class="sxs-lookup"><span data-stu-id="31930-112">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="31930-113">有关如何打开支持请求的说明，请参阅"联系商业产品支持[人员 - 管理员帮助"。](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="31930-113">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="31930-114">在组织中启用匿名入站 IPv6 邮件支持后，邮件将经过该服务提供的正常邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="31930-114">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="31930-115">疑难解答</span><span class="sxs-lookup"><span data-stu-id="31930-115">Troubleshooting</span></span>

- <span data-ttu-id="31930-116">如果源电子邮件服务器没有 IPv6 反向 DNS 查找记录，邮件将被拒绝，并出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="31930-116">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="31930-117">450 4.7.25 服务不可用，发送 IPv6 地址 [2a01：111：f200：2004：：240] 必须具有反向 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="31930-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="31930-118">如果发件人未通过 SPF 或 DKIM 验证，邮件将被拒绝，并出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="31930-118">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="31930-119">450 4.7.26 服务不可用，通过 IPv6 发送的邮件 [2a01：111：f200：2004：：240] 必须通过 SPF 或 DKIM 验证。</span><span class="sxs-lookup"><span data-stu-id="31930-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="31930-120">如果在选择加入之前尝试接收匿名 IPv6 邮件，邮件将被拒绝，并出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="31930-120">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="31930-121">550 5.2.1 服务不可用，[contoso.com] 不接受通过 IPv6 发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="31930-121">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="31930-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="31930-122">Related topics</span></span>

[<span data-ttu-id="31930-123">支持 DKIM 签名邮件验证</span><span class="sxs-lookup"><span data-stu-id="31930-123">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
