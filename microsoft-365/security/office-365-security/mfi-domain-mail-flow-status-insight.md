---
title: 邮件流仪表板中的顶级域邮件流状态见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可了解如何使用安全 & 合规中心"邮件流"仪表板中的"首要域邮件流"状态见解，来解决与其电子邮件域中的 MX 记录相关的邮件流问题。
ms.openlocfilehash: 9640d5e37932efeb7c0c8f8c56d0a15bc7f07e5b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827011"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="83b05-103">安全与合规中心内的顶级域邮件流 &状态见解</span><span class="sxs-lookup"><span data-stu-id="83b05-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

<span data-ttu-id="83b05-104">安全 & **合规** 中心内邮件流仪表板的 [顶级域](mail-flow-insights-v2.md) 邮件流状态见解可从邮件流邮件流为你提供组织域的当前状态。</span><span class="sxs-lookup"><span data-stu-id="83b05-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="83b05-105">该见解可帮助您标识遇到邮件流影响问题 (例如，无法接收外部电子邮件) （尤其***mail flow impacting***是域过期或具有不正确 MX 记录的域）的域，并对这些域进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="83b05-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![安全与合规中心内"邮件流"仪表板中的顶&"&示例](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="83b05-107">在单击小 **部件中** 的详细信息时，会显示 **一个"域** 状态"浮出控件，显示每个域状态的更多详细信息：</span><span class="sxs-lookup"><span data-stu-id="83b05-107">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="83b05-108">**域**</span><span class="sxs-lookup"><span data-stu-id="83b05-108">**Domain**</span></span>
- <span data-ttu-id="83b05-109">**Previous MX Record**</span><span class="sxs-lookup"><span data-stu-id="83b05-109">**Previous MX record**</span></span>
- <span data-ttu-id="83b05-110">**Current MX 记录**</span><span class="sxs-lookup"><span data-stu-id="83b05-110">**Current MX record**</span></span>
- <span data-ttu-id="83b05-111">**电子邮件接收状态**</span><span class="sxs-lookup"><span data-stu-id="83b05-111">**Email receiving status**</span></span>
- <span data-ttu-id="83b05-112">**域状态**：绿色复选标记指示在小部件) 上单击时的当前 MX 记录 (与我们记录上提供的值相匹配，且域已在过去两小时内收到电子邮件。</span><span class="sxs-lookup"><span data-stu-id="83b05-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="83b05-113">红色 X 表示 MX 记录已更改，且过去 6 小时内域未收到任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="83b05-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="83b05-114">这可能表示您的域已过期或 MX 记录更新不正确。</span><span class="sxs-lookup"><span data-stu-id="83b05-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="83b05-115">请与您的域注册机构或 DNS 托管服务一起检查，以确定域是否已过期，或域的 MX 记录是否正确。</span><span class="sxs-lookup"><span data-stu-id="83b05-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="83b05-116">您可以单击" **查看更多** "查看多个域的相同信息。</span><span class="sxs-lookup"><span data-stu-id="83b05-116">You can click **View more** to see the same information for more domains.</span></span>

!["顶级域"邮件流状态见解中的详细信息浮出控件](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="83b05-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="83b05-118">Related topics</span></span>

<span data-ttu-id="83b05-119">有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="83b05-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
