---
title: 邮件流仪表板中的主要域邮件流状态洞察力
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
description: 管理员可以了解如何使用安全 & 合规中心中的邮件流仪表板中的顶级域邮件流状态洞察力来解决与其电子邮件域中的 MX 记录相关的邮件流问题。
ms.openlocfilehash: 24922d6ae7d2ec50e3d9383631991cf46a818c05
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197521"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="dafcc-103">安全 & 合规中心中的主要域邮件流状态洞察力</span><span class="sxs-lookup"><span data-stu-id="dafcc-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="dafcc-104">[Security & 合规中心](https://protection.office.com)中的[邮件流仪表板](mail-flow-insights-v2.md)中的**顶级域邮件流状态**洞察力为您的组织的域提供了邮件流的当前状态。</span><span class="sxs-lookup"><span data-stu-id="dafcc-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="dafcc-105">此洞察力可帮助您识别和解决遇到 ***邮件流影响*** 问题的域 (例如，无法接收外部电子邮件) ，尤其是域过期或包含不正确的 MX 记录的域。</span><span class="sxs-lookup"><span data-stu-id="dafcc-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![安全 & 合规性中心的邮件流仪表板中的顶级域流状态构件](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="dafcc-107">当您单击小部件中的 " **查看详细信息** " 时，将显示一个 **域状态** 弹出控件，其中显示了有关每个域的状态的更多详细信息：</span><span class="sxs-lookup"><span data-stu-id="dafcc-107">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="dafcc-108">**域**</span><span class="sxs-lookup"><span data-stu-id="dafcc-108">**Domain**</span></span>
- <span data-ttu-id="dafcc-109">**以前的 MX 记录**</span><span class="sxs-lookup"><span data-stu-id="dafcc-109">**Previous MX record**</span></span>
- <span data-ttu-id="dafcc-110">**当前 MX 记录**</span><span class="sxs-lookup"><span data-stu-id="dafcc-110">**Current MX record**</span></span>
- <span data-ttu-id="dafcc-111">**电子邮件接收状态**</span><span class="sxs-lookup"><span data-stu-id="dafcc-111">**Email receiving status**</span></span>
- <span data-ttu-id="dafcc-112">**域状态**：绿色复选标记表示当前的 MX 记录 (您单击小组件时，) 与我们记录的值相匹配，并且在过去的两个小时内，该域已收到电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dafcc-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="dafcc-113">红色的 X 表示 MX 记录已更改，并且在过去6小时内没有收到任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dafcc-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="dafcc-114">这可能表明你的域已过期，或者 MX 记录已被错误更新。</span><span class="sxs-lookup"><span data-stu-id="dafcc-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="dafcc-115">请与你的域注册机构或 DNS 托管服务核实域是否已过期，或者域的 MX 记录是否不正确。</span><span class="sxs-lookup"><span data-stu-id="dafcc-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="dafcc-116">您可以单击 " **查看更多** " 查看更多域的相同信息。</span><span class="sxs-lookup"><span data-stu-id="dafcc-116">You can click **View more** to see the same information for more domains.</span></span>

!["详细信息" 浮出在顶级域邮件流状态洞察力](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="dafcc-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="dafcc-118">Related topics</span></span>

<span data-ttu-id="dafcc-119">有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="dafcc-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
