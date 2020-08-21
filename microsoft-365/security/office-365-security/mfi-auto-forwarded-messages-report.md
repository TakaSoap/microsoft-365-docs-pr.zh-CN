---
title: 自动转发的邮件见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 管理员可以在安全与合规中心的"邮件流"仪表板中了解"自动转发&"报告。
ms.openlocfilehash: 8d1a3ffe5ffc16a7793826b98b130121b8e68599
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827023"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="35070-103">安全与合规中心自动转发的&消息见解</span><span class="sxs-lookup"><span data-stu-id="35070-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

<span data-ttu-id="35070-104">"安全 &**合规**中心""邮件流"仪表板的[Mail flow dashboard](mail-flow-insights-v2.md)"自动转发的邮件"见解显示有关自动从组织转发到外部域中的收件人的邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="35070-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![安全与合规中心内的"自动转发&"小部件](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="35070-106">自动转发的消息详细信息</span><span class="sxs-lookup"><span data-stu-id="35070-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="35070-107">当您单击小部件中的消息数量时，会显示一个浮出控件窗格，显示有关自动转发邮件的更多信息：</span><span class="sxs-lookup"><span data-stu-id="35070-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="35070-108">**通过转发方法自动转发的消息**：</span><span class="sxs-lookup"><span data-stu-id="35070-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="35070-109">**按邮件流规则**</span><span class="sxs-lookup"><span data-stu-id="35070-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="35070-110">**按收件箱规则**</span><span class="sxs-lookup"><span data-stu-id="35070-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="35070-111">**通过 SMTP 转发**</span><span class="sxs-lookup"><span data-stu-id="35070-111">**By SMTP forwarding**</span></span>
  - <span data-ttu-id="35070-112">指向更多详细信息的 [转发报告](view-mail-flow-reports.md#forwarding-report) 的链接。</span><span class="sxs-lookup"><span data-stu-id="35070-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="35070-113">**按域和用户自动转发的邮件**：</span><span class="sxs-lookup"><span data-stu-id="35070-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="35070-114">**转发到的前 5 个主要域**</span><span class="sxs-lookup"><span data-stu-id="35070-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="35070-115">\*\*最后一周 (新) \*\*</span><span class="sxs-lookup"><span data-stu-id="35070-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="35070-116">**前 5 个转发用户**</span><span class="sxs-lookup"><span data-stu-id="35070-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="35070-117">\*\*上一 (新) \*\*</span><span class="sxs-lookup"><span data-stu-id="35070-117">**New users (last week)**</span></span>
  - <span data-ttu-id="35070-118">指向更多 [详细信息的转发修改报告](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 的链接。</span><span class="sxs-lookup"><span data-stu-id="35070-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![安全与合规中心中的"自动转发邮件"报告的详细信息&浮出控件](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="35070-120">见解</span><span class="sxs-lookup"><span data-stu-id="35070-120">Insights</span></span>

<span data-ttu-id="35070-121">此报告数据生成两个见解：</span><span class="sxs-lookup"><span data-stu-id="35070-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="35070-122">新用户转发电子邮件</span><span class="sxs-lookup"><span data-stu-id="35070-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="35070-123">转发的新域</span><span class="sxs-lookup"><span data-stu-id="35070-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="35070-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35070-124">See also</span></span>

<span data-ttu-id="35070-125">有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="35070-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
