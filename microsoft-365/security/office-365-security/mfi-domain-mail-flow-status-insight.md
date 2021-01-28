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
description: 管理员可以 &了解如何使用安全与合规中心的邮件流仪表板中的"顶级域邮件流状态"见解来排查与 MX 记录相关的邮件流问题。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 457675e7f32cd513f5593ede53a64aaef9d54904
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029902"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="bced3-103">安全与合规中心内热门域&状态见解</span><span class="sxs-lookup"><span data-stu-id="bced3-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="bced3-104">安全 **与合规** 中心的邮件流仪表板中的"[](mail-flow-insights-v2.md)热门域邮件流状态 [](https://protection.office.com)"&可为你提供组织的当前邮件流状态。</span><span class="sxs-lookup"><span data-stu-id="bced3-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="bced3-105">此见解可帮助你识别遇到 *_*_\* 邮件流 _ 问题的域并排除故障。</span><span class="sxs-lookup"><span data-stu-id="bced3-105">This insight helps you identify and troubleshoot domains that are experiencing \**_mail flow_* _ issues.</span></span> <span data-ttu-id="bced3-106">例如，域无法接收外部电子邮件，因为该域已过期或域的 MX 记录不正确。</span><span class="sxs-lookup"><span data-stu-id="bced3-106">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![安全与合规中心的邮件流仪表板中的"&流状态"小组件](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="bced3-108">在小组件中单击" _ *查看* 详细信息\* "时，将显示"域状态"飞出控件，其中显示每个域状态的更多详细信息：</span><span class="sxs-lookup"><span data-stu-id="bced3-108">When you click _ *View details*\* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="bced3-109">**域**</span><span class="sxs-lookup"><span data-stu-id="bced3-109">**Domain**</span></span>
- <span data-ttu-id="bced3-110">**以前的 MX 记录**</span><span class="sxs-lookup"><span data-stu-id="bced3-110">**Previous MX record**</span></span>
- <span data-ttu-id="bced3-111">**当前 MX 记录**</span><span class="sxs-lookup"><span data-stu-id="bced3-111">**Current MX record**</span></span>
- <span data-ttu-id="bced3-112">**电子邮件接收状态**</span><span class="sxs-lookup"><span data-stu-id="bced3-112">**Email receiving status**</span></span>
- <span data-ttu-id="bced3-113">域状态：绿色选中标记表示单击小组件) 时当前的 MX 记录 (与记录的值匹配，并且域在过去两小时内已收到电子邮件。</span><span class="sxs-lookup"><span data-stu-id="bced3-113">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="bced3-114">红色 X 表示 MX 记录已更改，并且域在过去 6 小时内未收到任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="bced3-114">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="bced3-115">这很可能表示你的域已过期，或者 MX 记录更新不正确。</span><span class="sxs-lookup"><span data-stu-id="bced3-115">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="bced3-116">请与域注册机构或 DNS 托管服务联系，以查看域是否已过期，或者域的 MX 记录是否不正确。</span><span class="sxs-lookup"><span data-stu-id="bced3-116">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="bced3-117">可以单击 **"查看更多"** 查看更多域的相同信息。</span><span class="sxs-lookup"><span data-stu-id="bced3-117">You can click **View more** to see the same information for more domains.</span></span>

![顶部域邮件流状态见解中的详细信息飞出](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="bced3-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bced3-119">See also</span></span>

<span data-ttu-id="bced3-120">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="bced3-120">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
