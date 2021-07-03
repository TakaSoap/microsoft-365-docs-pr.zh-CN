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
description: 监视发送到或发送自对业务影响较高的帐户的失败和延迟的电子邮件。
ms.openlocfilehash: 86e01e591823c94d8279f975ed7de24cc65776dc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286137"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="af548-103">管理和监视优先级帐户</span><span class="sxs-lookup"><span data-stu-id="af548-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="af548-104">在Microsoft 365组织中，都会有一些至关重要的人，如主管人员、领导、经理或其他有权访问敏感、专有或高优先级信息的用户。</span><span class="sxs-lookup"><span data-stu-id="af548-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="af548-105">为了帮助你的组织保护这些帐户，你现在可以将特定用户指定为优先帐户，并利用特定于应用的功能，这些功能可以提供额外的保护。</span><span class="sxs-lookup"><span data-stu-id="af548-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="af548-106">将来，更多应用和功能将支持优先帐户，首先，我们宣布有两项功能：优先级帐户保护和高级邮件 **流监视**。 </span><span class="sxs-lookup"><span data-stu-id="af548-106">In the future, more apps and features will support priority accounts, and to start with, we've announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="af548-107">**优先级帐户** 保护 - 适用于Office 365 (高级威胁Office 365的 Microsoft Defender) 支持将优先级帐户作为标记，这些标记可在警报、报告和调查的筛选器中使用。</span><span class="sxs-lookup"><span data-stu-id="af548-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="af548-108">有关详细信息，请查看 Microsoft [Defender 中的用户标记Office 365。](../../security/office-365-security/user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="af548-108">For more information, check out [User tags in Microsoft Defender for Office 365](../../security/office-365-security/user-tags.md).</span></span>

  <span data-ttu-id="af548-109">一个自然问题是，"不是所有用户都成为优先任务吗？</span><span class="sxs-lookup"><span data-stu-id="af548-109">A natural question is, "Aren't all users a priority?</span></span> <span data-ttu-id="af548-110">为什么不将所有用户指定为优先级帐户？</span><span class="sxs-lookup"><span data-stu-id="af548-110">Why not designate all users as priority accounts?"</span></span> <span data-ttu-id="af548-111">是的，所有用户都是优先级，但优先级帐户保护提供了以下附加优势：</span><span class="sxs-lookup"><span data-stu-id="af548-111">Yes, all users are a priority, but priority account protection offers the following additional benefits:</span></span>

  - <span data-ttu-id="af548-112">**其他启发：** 我们对 Microsoft 数据中心中的邮件流的分析表明，公司主管的邮件流模式不同于普通员工。</span><span class="sxs-lookup"><span data-stu-id="af548-112">**Additional heuristics**: Our analysis of mail flow in the Microsoft datacenters indicates that mail flow patterns for company executives are different than the average employee.</span></span> <span data-ttu-id="af548-113">优先级帐户保护提供了专为公司主管定制的其他启发，不会使普通员工受益。</span><span class="sxs-lookup"><span data-stu-id="af548-113">Priority account protection offers additional heuristics that are specifically tailored to company executives that wouldn't benefit a regular employee.</span></span>
  - <span data-ttu-id="af548-114">**报告的其他** 可见性：实际上，警报、报告和 (中已提供了所有) 或所有受影响的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="af548-114">**Additional visibility in reporting**: In effect, information for all users (or all affected users) is already available in alerts, reports, and investigations.</span></span> <span data-ttu-id="af548-115">作为筛选器的优先级帐户标记允许你专门定向调查。</span><span class="sxs-lookup"><span data-stu-id="af548-115">The priority accounts tag as a filter allows you to specifically target your investigations.</span></span>

- <span data-ttu-id="af548-116">**高级版邮件** Flow监视 - 正常邮件流对于业务成功至关重要，传递延迟或失败会对业务产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="af548-116">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="af548-117">您可以选择失败或延迟电子邮件的阈值，在超出该阈值时接收警报，并查看优先级帐户的电子邮件问题报告。</span><span class="sxs-lookup"><span data-stu-id="af548-117">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="af548-118">有关详细信息，请查看新式 EAC 中的优先级帐户电子邮件 [问题报告](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="af548-118">For more information, check out [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="af548-119">有关优先级帐户的安全最佳做法，请参阅安全 [建议优先级帐户](../../security/office-365-security/security-recommendations-for-priority-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="af548-119">For security best practices for priority accounts, see [Security recommendations for priority accounts](../../security/office-365-security/security-recommendations-for-priority-accounts.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="af548-120">开始之前</span><span class="sxs-lookup"><span data-stu-id="af548-120">Before you begin</span></span>

<span data-ttu-id="af548-121">本主题 **中所述** 的优先级帐户保护功能仅适用于满足以下要求的组织：</span><span class="sxs-lookup"><span data-stu-id="af548-121">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="af548-122">Microsoft Defender for Office 365 计划 2，包括Office 365 E3、Office 365 E5、Microsoft 365 E5或Microsoft 365 E5 安全性。</span><span class="sxs-lookup"><span data-stu-id="af548-122">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="af548-123">本主题 **高级版的邮件** Flow监视功能仅适用于满足以下要求的组织：</span><span class="sxs-lookup"><span data-stu-id="af548-123">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="af548-124">贵组织的许可证数量至少需要为 5，000（来自以下产品之一）或以下产品的组合：Office 365 E3、Microsoft 365 E3、Office 365 E5 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="af548-124">Your organization needs to have a license count of at least 5,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="af548-125">例如，你的组织可以具有 3,000 个 Office 365 E3 许可证，2,500 个 Microsoft 365 E5，即总计拥有 5,500 个合格产品许可证。</span><span class="sxs-lookup"><span data-stu-id="af548-125">For example, your organization can have 3,000 Office 365 E3 licenses and 2,500 Microsoft 365 E5, for a total of 5,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="af548-126">你的组织需要拥有至少50 个 Exchange Online 月活跃用户。</span><span class="sxs-lookup"><span data-stu-id="af548-126">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="af548-127">你可以监视最多 250 个优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="af548-127">You can monitor up to 250 priority accounts.</span></span>

<span data-ttu-id="af548-128">将优先级帐户保护应用于邮箱时，还应将优先级帐户保护应用于有权访问邮箱 (例如 CEO 和管理 CEO 日历管理员的 CEO 行政助理) 。</span><span class="sxs-lookup"><span data-stu-id="af548-128">When you apply priority account protection to a mailbox, you should also apply priority account protection to users who have access to the mailbox (for example, the CEO and the CEO's executive assistant who manages the CEO's calendar).</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="af548-129">从"设置"页添加优先级帐户</span><span class="sxs-lookup"><span data-stu-id="af548-129">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="af548-130">从设置页面 **添加优先级帐户**。</span><span class="sxs-lookup"><span data-stu-id="af548-130">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="af548-131">转到 上 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="af548-131">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="af548-132">转到"**设置**  >  **组织知识"，** 然后选择"监视最重要的帐户 **"下的"查看"。**</span><span class="sxs-lookup"><span data-stu-id="af548-132">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="af548-133">选择 **"入门"** 或"**管理"。**</span><span class="sxs-lookup"><span data-stu-id="af548-133">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="af548-134">在 **"添加优先级帐户"** 页上的搜索字段中，键入要添加到优先级帐户列表的人的姓名或电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="af548-134">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="af548-135">还可以为失败或延迟的电子邮件设置电子邮件阈值，并获取优先级帐户的每周问题报告。</span><span class="sxs-lookup"><span data-stu-id="af548-135">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="af548-136">选择用户，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="af548-136">Select the user and choose **Save**.</span></span>

<span data-ttu-id="af548-137">您还可以从"活动用户"页面添加优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="af548-137">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="af548-138">"从活动用户添加优先级帐户"页</span><span class="sxs-lookup"><span data-stu-id="af548-138">Add priority accounts from Active users page</span></span>

<span data-ttu-id="af548-139">从"活动用户"页面添加优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="af548-139">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="af548-140">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="af548-140">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="af548-141">转到"**用户**  >  **""** 活动用户"， (三个点) 页面顶部的其他操作。</span><span class="sxs-lookup"><span data-stu-id="af548-141">Go to **Users** > **Active users** and select the three dots (more actions) at the top of the page.</span></span> <span data-ttu-id="af548-142">选择 **管理优先级帐户**。</span><span class="sxs-lookup"><span data-stu-id="af548-142">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="af548-143">选择 **"添加帐户**"，在" **添加优先级** 帐户"页上的搜索字段中，键入要添加到优先级帐户列表的人的姓名。</span><span class="sxs-lookup"><span data-stu-id="af548-143">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="af548-144">选择用户，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="af548-144">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="af548-145">从优先级帐户列表中删除用户</span><span class="sxs-lookup"><span data-stu-id="af548-145">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="af548-146">转到 上 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="af548-146">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="af548-147">转到"**设置**  >  **组织知识"，** 然后选择"监视最重要的帐户 **"下的"查看"。**</span><span class="sxs-lookup"><span data-stu-id="af548-147">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="af548-148">在"**监视你的大多数帐户"页面上**，选择"管理 **此功能"下的\*\*\*\*"优先级帐户"。**</span><span class="sxs-lookup"><span data-stu-id="af548-148">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="af548-149">在"**优先级帐户**"页上，选择要从列表中删除的一个或多个用户，然后选择"**删除帐户"。**</span><span class="sxs-lookup"><span data-stu-id="af548-149">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="af548-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="af548-150">Related topics</span></span>

[<span data-ttu-id="af548-151">Using Priority Accounts in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="af548-151">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
