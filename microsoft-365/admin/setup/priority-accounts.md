---
title: 管理和监视优先级帐户
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: 监视发送到或来自具有高业务影响的帐户的电子邮件失败和延迟。
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477609"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="1e8a2-103">管理和监视优先级帐户</span><span class="sxs-lookup"><span data-stu-id="1e8a2-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="1e8a2-104">在每个 Microsoft 365 组织中，有必要的人，如主管、领导、经理或其他对敏感、专有或高优先级信息具有访问权限的用户。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="1e8a2-105">为了帮助您的组织保护这些帐户，您现在可以将特定用户指定为优先级帐户，并利用特定于应用程序的功能为他们提供额外的保护。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="1e8a2-106">在将来，更多的应用和功能将支持优先级帐户，开始时，我们已宣布了两个功能： **优先级帐户保护** 和 **高级邮件流监控**。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="1e8a2-107">**优先级帐户保护** -Microsoft Defender for office 365 (以前的 Office 365 高级威胁防护) 支持将优先级帐户用作可在警报、报告和调查的筛选器中使用的标记。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="1e8a2-108">有关详细信息，请参阅 [Microsoft Defender For Office 365 中的用户标记](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="1e8a2-109">**高级邮件流监控** -正常的邮件流可能对业务成功非常关键，且传递延迟或故障可能对业务产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="1e8a2-110">您可以为失败或延迟的电子邮件选择阈值，在超过该阈值时接收通知，并查看优先级帐户的电子邮件问题报告。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="1e8a2-111">有关详细信息，请参阅 [新式 EAC 中的优先级帐户报告的电子邮件问题](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1e8a2-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="1e8a2-112">Before you begin</span></span>

<span data-ttu-id="1e8a2-113">本主题中所述的 **优先级帐户保护** 功能仅适用于满足以下要求的组织：</span><span class="sxs-lookup"><span data-stu-id="1e8a2-113">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="1e8a2-114">Microsoft Defender for Office 365 计划2，包括具有 Office 365 E3、Office 365 E5、Microsoft 365 E5 或 Microsoft 365 E5 安全性的 Office Defender。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-114">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="1e8a2-115">本主题中介绍的 " **高级邮件流监控** " 功能仅适用于满足以下要求的组织：</span><span class="sxs-lookup"><span data-stu-id="1e8a2-115">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="1e8a2-116">您的组织需要的许可证计数至少为10000，或者是以下产品的一种或以下产品的组合： Office 365 E3，Microsoft 365 E3，Office 365 E5，Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-116">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="1e8a2-117">例如，您的组织可以拥有3000个 Office 365 E3 许可证并 8500 Microsoft 365 E5，以提供符合条件的产品的全部11500许可证。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-117">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="1e8a2-118">您的组织需要至少50个每月活动 Exchange Online 用户。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-118">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="1e8a2-119">您可以监控最高为250的优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-119">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="1e8a2-120">从 "设置" 页面添加优先级帐户</span><span class="sxs-lookup"><span data-stu-id="1e8a2-120">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="1e8a2-121">从 " **设置" 页面** 添加优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-121">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="1e8a2-122">转到 Microsoft 365 管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-122">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="1e8a2-123">转到 "**设置**  >  **组织知识**"，然后选择 "**监视最重要的帐户**" 下的 "**查看**"。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-123">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="1e8a2-124">选择 " **开始** " 或 " **管理**"。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-124">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="1e8a2-125">在 " **添加优先级帐户** " 页上的 "搜索" 字段中，键入要添加到 "优先级帐户" 列表中的人员的姓名或电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-125">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="1e8a2-126">您还可以为失败或延迟的电子邮件设置电子邮件阈值，并获取优先级帐户的每周问题报告。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-126">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="1e8a2-127">选择用户并选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-127">Select the user and choose **Save**.</span></span>

<span data-ttu-id="1e8a2-128">您还可以从 "活动用户" 页面添加优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-128">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="1e8a2-129">从活动用户添加优先级帐户页面</span><span class="sxs-lookup"><span data-stu-id="1e8a2-129">Add priority accounts from Active users page</span></span>

<span data-ttu-id="1e8a2-130">从 "活动用户" 页面添加优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-130">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="1e8a2-131">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="1e8a2-132">转到 "**用户**  >  **活动用户**" **...** ，然后选择页面顶部的 "..."。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-132">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="1e8a2-133">选择 " **管理优先级帐户**"。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-133">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="1e8a2-134">选择 " **添加帐户**"，并在 " **添加优先级帐户** " 页上的 "搜索" 字段中，键入要添加到 "优先级帐户" 列表中的人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-134">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="1e8a2-135">选择用户并选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-135">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="1e8a2-136">从 "优先级帐户" 列表中删除用户</span><span class="sxs-lookup"><span data-stu-id="1e8a2-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="1e8a2-137">转到 Microsoft 365 管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="1e8a2-138">转到 "**设置**  >  **组织知识**"，然后选择 "**监视最重要的帐户**" 下的 "**查看**"。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="1e8a2-139">在 "**监视你的大多数帐户**" 页上，选择 "**管理此功能**" 下的 "**优先级帐户**"。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="1e8a2-140">在 " **优先级帐户** " 页上，选择要从列表中删除的一个或一组用户，然后选择 " **删除帐户**"。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1e8a2-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="1e8a2-141">Related topics</span></span>

[<span data-ttu-id="1e8a2-142">在 Microsoft 365 中使用优先级帐户</span><span class="sxs-lookup"><span data-stu-id="1e8a2-142">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)