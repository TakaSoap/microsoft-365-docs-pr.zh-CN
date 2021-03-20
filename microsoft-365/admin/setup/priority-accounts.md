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
ms.openlocfilehash: b31cbf79b5b1b8f882c4c7bc8926779410baefe3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914050"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="781cd-103">管理和监视优先级帐户</span><span class="sxs-lookup"><span data-stu-id="781cd-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="781cd-104">每个 Microsoft 365 组织中都有一些必要的人员，如主管人员、领导、经理或其他有权访问敏感、专有或高优先级信息的用户。</span><span class="sxs-lookup"><span data-stu-id="781cd-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="781cd-105">为了帮助你的组织保护这些帐户，你现在可以将特定用户指定为优先帐户，并利用特定于应用的功能，这些功能可以提供额外的保护。</span><span class="sxs-lookup"><span data-stu-id="781cd-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="781cd-106">将来，更多应用和功能将支持优先帐户，首先，我们宣布有两项功能：优先级帐户保护和高级邮件 **流监视**。 </span><span class="sxs-lookup"><span data-stu-id="781cd-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="781cd-107">优先级帐户保护 **-** Microsoft Defender for Office 365 (以前是 Office 365 高级威胁防护) 支持将优先级帐户作为标记，这些标记可用于警报、报告和调查的筛选器。</span><span class="sxs-lookup"><span data-stu-id="781cd-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="781cd-108">有关详细信息，请查看 Microsoft [Defender for Office 365](../../security/office-365-security/user-tags.md)中的用户标记。</span><span class="sxs-lookup"><span data-stu-id="781cd-108">For more information, check out [User tags in Microsoft Defender for Office 365](../../security/office-365-security/user-tags.md).</span></span>
- <span data-ttu-id="781cd-109">**高级邮件流监视** - 正常邮件流对于业务成功至关重要，传递延迟或失败会对业务产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="781cd-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="781cd-110">您可以选择失败或延迟电子邮件的阈值，在超出该阈值时接收警报，并查看优先级帐户的电子邮件问题报告。</span><span class="sxs-lookup"><span data-stu-id="781cd-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="781cd-111">有关详细信息，请查看新式 EAC 中的优先级帐户电子邮件 [问题报告](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="781cd-111">For more information, check out [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="781cd-112">有关优先级帐户的安全最佳做法，请参阅安全 [建议优先级帐户](../../security/office-365-security/security-recommendations-for-priority-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="781cd-112">For security best practices for priority accounts, see [Security recommendations for priority accounts](../../security/office-365-security/security-recommendations-for-priority-accounts.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="781cd-113">开始之前</span><span class="sxs-lookup"><span data-stu-id="781cd-113">Before you begin</span></span>

<span data-ttu-id="781cd-114">本主题 **中所述** 的优先级帐户保护功能仅适用于满足以下要求的组织：</span><span class="sxs-lookup"><span data-stu-id="781cd-114">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="781cd-115">Microsoft Defender for Office 365 计划 2，包括 Office 365 E3、Office 365 E5、Microsoft 365 E5 或 Microsoft 365 E5 安全中心。</span><span class="sxs-lookup"><span data-stu-id="781cd-115">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="781cd-116">本主题 **中所述** 的高级邮件流监视功能仅适用于满足以下要求的组织：</span><span class="sxs-lookup"><span data-stu-id="781cd-116">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="781cd-117">贵组织的许可证计数至少需要为 10，000（来自以下产品之一）或以下产品的组合：Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="781cd-117">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="781cd-118">例如，你的组织可以拥有 3000 个 Office 365 E3 许可证和 8500 个 Microsoft 365 E5，总共 11，500 个许可证来自符合条件的产品。</span><span class="sxs-lookup"><span data-stu-id="781cd-118">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="781cd-119">你的组织需要拥有至少50 个 Exchange Online 月活跃用户。</span><span class="sxs-lookup"><span data-stu-id="781cd-119">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="781cd-120">你可以监视最多 250 个优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="781cd-120">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="781cd-121">从"设置"页添加优先级帐户</span><span class="sxs-lookup"><span data-stu-id="781cd-121">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="781cd-122">从设置页面 **添加优先级帐户**。</span><span class="sxs-lookup"><span data-stu-id="781cd-122">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="781cd-123">转到 Microsoft 365 管理中心，位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="781cd-123">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="781cd-124">转到"**设置**  >  **组织知识"，** 然后选择"监视最重要的帐户 **"下的"查看"。**</span><span class="sxs-lookup"><span data-stu-id="781cd-124">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="781cd-125">选择 **"入门"** 或"**管理"。**</span><span class="sxs-lookup"><span data-stu-id="781cd-125">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="781cd-126">在 **"添加优先级帐户"** 页上的搜索字段中，键入要添加到优先级帐户列表的人的姓名或电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="781cd-126">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="781cd-127">还可以为失败或延迟的电子邮件设置电子邮件阈值，并获取优先级帐户的每周问题报告。</span><span class="sxs-lookup"><span data-stu-id="781cd-127">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="781cd-128">选择用户，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="781cd-128">Select the user and choose **Save**.</span></span>

<span data-ttu-id="781cd-129">您还可以从"活动用户"页面添加优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="781cd-129">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="781cd-130">"从活动用户添加优先级帐户"页</span><span class="sxs-lookup"><span data-stu-id="781cd-130">Add priority accounts from Active users page</span></span>

<span data-ttu-id="781cd-131">从"活动用户"页面添加优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="781cd-131">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="781cd-132">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="781cd-132">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="781cd-133">转到 **"用户**  >  **""** 活动用户"，然后选择页面顶部的"..."。</span><span class="sxs-lookup"><span data-stu-id="781cd-133">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="781cd-134">选择 **管理优先级帐户**。</span><span class="sxs-lookup"><span data-stu-id="781cd-134">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="781cd-135">选择 **"添加帐户**"，在" **添加优先级** 帐户"页上的搜索字段中，键入要添加到优先级帐户列表的人的姓名。</span><span class="sxs-lookup"><span data-stu-id="781cd-135">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="781cd-136">选择用户，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="781cd-136">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="781cd-137">从优先级帐户列表中删除用户</span><span class="sxs-lookup"><span data-stu-id="781cd-137">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="781cd-138">转到 Microsoft 365 管理中心，位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="781cd-138">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="781cd-139">转到"**设置**  >  **组织知识"，** 然后选择"监视最重要的帐户 **"下的"查看"。**</span><span class="sxs-lookup"><span data-stu-id="781cd-139">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="781cd-140">在"**监视你的大多数帐户"页面上**，选择"管理 **此功能"下的\*\*\*\*"优先级帐户"。**</span><span class="sxs-lookup"><span data-stu-id="781cd-140">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="781cd-141">在"**优先级帐户**"页上，选择要从列表中删除的一个或多个用户，然后选择"**删除帐户"。**</span><span class="sxs-lookup"><span data-stu-id="781cd-141">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="781cd-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="781cd-142">Related topics</span></span>

[<span data-ttu-id="781cd-143">在 Microsoft 365 中使用优先级帐户</span><span class="sxs-lookup"><span data-stu-id="781cd-143">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)