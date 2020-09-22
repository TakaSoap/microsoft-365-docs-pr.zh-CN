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
ms.openlocfilehash: be226bf9814b0fcfadaaeb5b4bdda0ff133dd0c8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202145"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="4469b-103">在 Microsoft 365 中添加对通过 IPv6 的匿名入站电子邮件的支持</span><span class="sxs-lookup"><span data-stu-id="4469b-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4469b-104">使用 Exchange Online 邮箱和独立 Exchange Online Protection 的 Microsoft 365 组织 (EOP) 不带 Exchange Online 邮箱的组织都支持通过 IPv6 的匿名入站电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4469b-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="4469b-105">源 IPv6 电子邮件服务器必须满足以下两项要求：</span><span class="sxs-lookup"><span data-stu-id="4469b-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="4469b-106">源 IPv6 地址必须具有有效的反向 DNS 查找 (PTR) 记录允许目标从 IPv6 地址查找域名。</span><span class="sxs-lookup"><span data-stu-id="4469b-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="4469b-107">发件人必须通过 SPF 验证（在 [RFC 7208](https://tools.ietf.org/html/rfc7208) 中定义）或 [DKIM 验证](http://dkim.org/)（在 [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) 中定义）。</span><span class="sxs-lookup"><span data-stu-id="4469b-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="4469b-108">在您的组织可以通过 IPv6 接收匿名入站电子邮件之前，管理员需要联系 Microsoft 支持部门并要求提供此电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4469b-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="4469b-109">有关如何打开支持请求的说明，请参阅 [联系支持人员以获取商业产品-管理员帮助](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="4469b-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="4469b-110">在组织中启用匿名入站 IPv6 邮件支持后，邮件将通过服务提供的常规邮件筛选功能。</span><span class="sxs-lookup"><span data-stu-id="4469b-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="4469b-111">故障排除</span><span class="sxs-lookup"><span data-stu-id="4469b-111">Troubleshooting</span></span>

- <span data-ttu-id="4469b-112">如果源电子邮件服务器没有 IPv6 反向 DNS 查找记录，则邮件将被拒绝，并出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="4469b-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="4469b-113">450 4.7.25 服务不可用，发送 IPv6 地址 [2a01：111： f200：2004：： 240] 必须有反向 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="4469b-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="4469b-114">如果发件人未通过 SPF 或 DKIM 验证，则邮件将被拒绝，并出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="4469b-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="4469b-115">450 4.7.26 服务不可用，通过 IPv6 发送的邮件 [2a01：111： f200：2004：： 240] 必须通过 SPF 或 DKIM 验证。</span><span class="sxs-lookup"><span data-stu-id="4469b-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="4469b-116">如果您在选择加入之前尝试接收匿名 IPv6 邮件，则邮件将被拒绝，并显示以下错误：</span><span class="sxs-lookup"><span data-stu-id="4469b-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="4469b-117">550 5.2.1 服务不可用，[contoso.com] 不接受通过 IPv6 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4469b-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4469b-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="4469b-118">Related topics</span></span>

[<span data-ttu-id="4469b-119">支持 DKIM 签名邮件验证</span><span class="sxs-lookup"><span data-stu-id="4469b-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
