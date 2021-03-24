---
title: 邮件流仪表板中的热门域邮件流状态见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何 &使用安全与合规中心内"邮件流"仪表板中的"热门域邮件流状态"见解，解决与 MX 记录相关的邮件流问题。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 850e72fa0ad7a3f41450a1d0a2c02dd3df4a0cb5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055211"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="c6cf2-103">安全与合规中心内热门域&状态见解</span><span class="sxs-lookup"><span data-stu-id="c6cf2-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c6cf2-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="c6cf2-104">**Applies to**</span></span>
- [<span data-ttu-id="c6cf2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c6cf2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c6cf2-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="c6cf2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c6cf2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6cf2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c6cf2-108">安全 **与合规** 中心内"邮件流"[](mail-flow-insights-v2.md)仪表板中的"热门域邮件流状态"&[可](https://protection.office.com)为你提供组织的当前邮件流状态。</span><span class="sxs-lookup"><span data-stu-id="c6cf2-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="c6cf2-109">此见解可帮助您识别和排查遇到邮件 ***流问题的域*** 。</span><span class="sxs-lookup"><span data-stu-id="c6cf2-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="c6cf2-110">例如，域无法接收外部电子邮件，因为该域已过期或域的 MX 记录不正确。</span><span class="sxs-lookup"><span data-stu-id="c6cf2-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![安全与合规中心内"邮件流"仪表板中的"&流状态"小组件](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="c6cf2-112">在小 **组件中** 单击"查看详细信息"时 **，将显示"** 域状态"飞出，其中显示每个域状态的更多详细信息：</span><span class="sxs-lookup"><span data-stu-id="c6cf2-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="c6cf2-113">**域**</span><span class="sxs-lookup"><span data-stu-id="c6cf2-113">**Domain**</span></span>
- <span data-ttu-id="c6cf2-114">**以前的 MX 记录**</span><span class="sxs-lookup"><span data-stu-id="c6cf2-114">**Previous MX record**</span></span>
- <span data-ttu-id="c6cf2-115">**当前 MX 记录**</span><span class="sxs-lookup"><span data-stu-id="c6cf2-115">**Current MX record**</span></span>
- <span data-ttu-id="c6cf2-116">**电子邮件接收状态**</span><span class="sxs-lookup"><span data-stu-id="c6cf2-116">**Email receiving status**</span></span>
- <span data-ttu-id="c6cf2-117">域状态：绿色选中标记表示单击小组件) 时当前的 MX 记录 (匹配我们记录的值，并且域在过去两小时内已收到电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c6cf2-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="c6cf2-118">红色 X 表示 MX 记录已更改，并且域在过去 6 小时内未收到任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c6cf2-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="c6cf2-119">这很可能表示您的域已过期，或者 MX 记录更新不正确。</span><span class="sxs-lookup"><span data-stu-id="c6cf2-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="c6cf2-120">请与域注册机构或 DNS 托管服务核实，以查看域是否已过期，或者域的 MX 记录不正确。</span><span class="sxs-lookup"><span data-stu-id="c6cf2-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="c6cf2-121">可以单击" **查看更多** "查看更多域的相同信息。</span><span class="sxs-lookup"><span data-stu-id="c6cf2-121">You can click **View more** to see the same information for more domains.</span></span>

!["热门域邮件流状态"见解中的"详细信息"飞出](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="c6cf2-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6cf2-123">See also</span></span>

<span data-ttu-id="c6cf2-124">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="c6cf2-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
