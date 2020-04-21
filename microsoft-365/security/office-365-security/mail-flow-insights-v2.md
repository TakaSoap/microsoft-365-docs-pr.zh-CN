---
title: 安全与合规中心内的邮件流见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 管理员可以了解安全 & 合规中心中的邮件流仪表板。
ms.openlocfilehash: 64bf1f2af967f841cd4c21be19fce914df136815
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630463"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="349ac-103">安全与合规中心内的邮件流见解</span><span class="sxs-lookup"><span data-stu-id="349ac-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="349ac-104">管理员可以使用安全 & 合规中心中的邮件流仪表板来发现趋势、见解并采取措施解决与组织中的邮件流相关的问题。</span><span class="sxs-lookup"><span data-stu-id="349ac-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their organization.</span></span>

<span data-ttu-id="349ac-105">邮件流仪表板中提供的见解、报告和小部件为：</span><span class="sxs-lookup"><span data-stu-id="349ac-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="349ac-106">邮件流地图报表</span><span class="sxs-lookup"><span data-stu-id="349ac-106">Mail flow map report</span></span>](mfi-mail-flow-map-report.md)

- [<span data-ttu-id="349ac-107">域邮件流状态洞察力</span><span class="sxs-lookup"><span data-stu-id="349ac-107">Domain mail flow status insight</span></span>](mfi-domain-mail-flow-status-insight.md)

- [<span data-ttu-id="349ac-108">SMTP 身份验证客户端报表</span><span class="sxs-lookup"><span data-stu-id="349ac-108">SMTP Auth clients report</span></span>](mfi-smtp-auth-clients-report.md)

- [<span data-ttu-id="349ac-109">发件人域洞察力</span><span class="sxs-lookup"><span data-stu-id="349ac-109">Sender domain insight</span></span>](mfi-sender-domain-insight.md)

- [<span data-ttu-id="349ac-110">未送达报告</span><span class="sxs-lookup"><span data-stu-id="349ac-110">Non-delivery report</span></span>](mfi-non-delivery-report.md)

- [<span data-ttu-id="349ac-111">非接受域报告</span><span class="sxs-lookup"><span data-stu-id="349ac-111">Non-accepted domain report</span></span>](mfi-non-accepted-domain-report.md)

- [<span data-ttu-id="349ac-112">入站和出站邮件流</span><span class="sxs-lookup"><span data-stu-id="349ac-112">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="349ac-113">队列警报和队列</span><span class="sxs-lookup"><span data-stu-id="349ac-113">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="349ac-114">自动转发的消息报告</span><span class="sxs-lookup"><span data-stu-id="349ac-114">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="349ac-115">邮件循环见解</span><span class="sxs-lookup"><span data-stu-id="349ac-115">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="349ac-116">慢邮件流规则见解</span><span class="sxs-lookup"><span data-stu-id="349ac-116">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="349ac-117">查看邮件流仪表板所需的权限</span><span class="sxs-lookup"><span data-stu-id="349ac-117">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="349ac-118">邮件流仪表板可用于：</span><span class="sxs-lookup"><span data-stu-id="349ac-118">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="349ac-119">**全局管理员**角色的成员。</span><span class="sxs-lookup"><span data-stu-id="349ac-119">Members of the **global administrator** role.</span></span>

- <span data-ttu-id="349ac-120">**Exchange 管理员**角色的成员。</span><span class="sxs-lookup"><span data-stu-id="349ac-120">Members of **Exchange administrator** role.</span></span>

- <span data-ttu-id="349ac-121">Security & 合规中心中的**邮件流管理员角色**的成员。</span><span class="sxs-lookup"><span data-stu-id="349ac-121">Members of the **Mail flow administrator role** in the Security & Compliance Center.</span></span> <span data-ttu-id="349ac-122">如果此角色被明确分配给不是全局管理员或 Exchange 管理员角色成员的用户：</span><span class="sxs-lookup"><span data-stu-id="349ac-122">If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="349ac-123">用户必须直接在[https://protection.office.com](https://protection.office.com)中直接登录到安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="349ac-123">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="349ac-124">用户将只具有对邮件流仪表板的只读权限。</span><span class="sxs-lookup"><span data-stu-id="349ac-124">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="349ac-125">用户将无法访问 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="349ac-125">The user won't have access to the Microsoft 365 admin center.</span></span>

<span data-ttu-id="349ac-126">有关全局管理员角色的详细信息，请参阅[关于 Microsoft 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="349ac-126">For more information about the global administrator role, see [About Microsoft 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="349ac-127">有关为用户分配安全 & 合规性中心角色的信息，请参阅[为用户提供对安全 & 合规性中心的访问权限](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="349ac-127">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="349ac-128">在何处查找邮件流仪表板</span><span class="sxs-lookup"><span data-stu-id="349ac-128">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="349ac-129">转到上[https://protection.office.com](https://protection.office.com)的安全性 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="349ac-129">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="349ac-130">展开 "**邮件流**"，然后选择 "**仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="349ac-130">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![安全 & 合规性中心中的邮件流仪表板](../../media/mail-flow-dashboard-v2.png)
