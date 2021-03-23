---
title: 设置标准或定向发布选项
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: 了解如何在 Microsoft 365 管理中心中设置新产品和功能更新的发布选项。
ms.openlocfilehash: e909cdf35ba9dd8282540783f7c362e5ae49212e
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034075"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="78a14-103">设置标准或定向发布选项</span><span class="sxs-lookup"><span data-stu-id="78a14-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="78a14-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="78a14-104">The admin center is changing.</span></span> <span data-ttu-id="78a14-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="78a14-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

> [!IMPORTANT]
> <span data-ttu-id="78a14-106">本文中所述的 Microsoft 365 更新适用于 Microsoft 365、SharePoint Online 和 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="78a14-106">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="78a14-107">这些发布选项是发布 Microsoft 365 更改的有针对性的最佳方法，但不能保证任何时间或所有更新。</span><span class="sxs-lookup"><span data-stu-id="78a14-107">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="78a14-108">它们不适用于 Microsoft 365 应用版、Skype for Business、Microsoft Teams 和相关服务。</span><span class="sxs-lookup"><span data-stu-id="78a14-108">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="78a14-109">有关 Microsoft 365 应用版发布选项的信息，请参阅 [Microsoft 365 应用版更新频道概述](/deployoffice/overview-update-channels)。</span><span class="sxs-lookup"><span data-stu-id="78a14-109">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="78a14-110">使用 Microsoft 365，你可在新产品更新和功能可用时收到它们，而不是每隔几年进行一次代价高昂的更新。</span><span class="sxs-lookup"><span data-stu-id="78a14-110">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="78a14-111">你可以管理组织接收这些更新的方式。</span><span class="sxs-lookup"><span data-stu-id="78a14-111">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="78a14-112">例如，你可以注册抢先体验新发布版本，保证组织能够第一时间接收到更新。</span><span class="sxs-lookup"><span data-stu-id="78a14-112">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="78a14-113">你可以指定只有某几个人接收更新。</span><span class="sxs-lookup"><span data-stu-id="78a14-113">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="78a14-114">或者，你可以保留默认的发布计划，稍后接收更新。</span><span class="sxs-lookup"><span data-stu-id="78a14-114">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="78a14-115">本文介绍了不同的发布选项以及如何为组织使用它们。</span><span class="sxs-lookup"><span data-stu-id="78a14-115">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="78a14-116">工作原理 - 发布验证</span><span class="sxs-lookup"><span data-stu-id="78a14-116">How it works - release validation</span></span>

<span data-ttu-id="78a14-117">任何新版本首先由功能团队进行测试和验证，然后由整个 Microsoft 365 功能团队进行测试和验证，然后由所有 Microsoft 进行测试和验证。</span><span class="sxs-lookup"><span data-stu-id="78a14-117">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="78a14-118">内部测试和验证后，下一步是向选择加入的客户" **定向发布**"（以前称为首次发布）。</span><span class="sxs-lookup"><span data-stu-id="78a14-118">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="78a14-119">在每个发布环节，Microsoft 都会收集反馈，通过监视关键的使用情况指标验证质量。</span><span class="sxs-lookup"><span data-stu-id="78a14-119">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="78a14-120">采取逐步进行的一系列验证，确保全球范围内发布的版本尽可能的稳定。</span><span class="sxs-lookup"><span data-stu-id="78a14-120">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="78a14-121">发布环节如下图所示。</span><span class="sxs-lookup"><span data-stu-id="78a14-121">The releases are pictured in the following figure.</span></span> 
  
![发布 Microsoft 365 验证圈](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="78a14-123">对于重大更新，最初会通过 [Microsoft 365](https://products.office.com/business/office-365-roadmap)路线图通知客户。</span><span class="sxs-lookup"><span data-stu-id="78a14-123">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="78a14-124">随着更新的推出越来越接近，它将通过 [Microsoft 365 消息中心进行通信](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)。</span><span class="sxs-lookup"><span data-stu-id="78a14-124">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="78a14-125">你需要 Microsoft 365 或 Azure AD 帐户才能通过管理中心访问 [消息中心](/office365/admin/admin-overview/about-the-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="78a14-125">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="78a14-126">Microsoft 365 家庭版计划用户没有管理中心。</span><span class="sxs-lookup"><span data-stu-id="78a14-126">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="78a14-127">标准发布</span><span class="sxs-lookup"><span data-stu-id="78a14-127">Standard release</span></span>

<span data-ttu-id="78a14-128">这是默认选项，在将最新更新广泛发布给所有客户时，你和用户会收到这些更新。</span><span class="sxs-lookup"><span data-stu-id="78a14-128">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="78a14-129">最佳做法是让大多数用户留在标准版中，让IT 专业人员和高级用户在定向发布中评估新功能，并准备团队以支持业务用户和主管人员。</span><span class="sxs-lookup"><span data-stu-id="78a14-129">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="78a14-130">如果你从定向发布切换回标准发布计划，你的用户可能无法再次访问那些尚未进入标准发布的功能。</span><span class="sxs-lookup"><span data-stu-id="78a14-130">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="78a14-131">定向发布</span><span class="sxs-lookup"><span data-stu-id="78a14-131">Targeted release</span></span>

<span data-ttu-id="78a14-p107">使用此选项，你和你的用户可以抢先体验最新更新，并通过提供早期反馈帮助改进产品。你可以选择让某几个人或整个组织先接收更新。</span><span class="sxs-lookup"><span data-stu-id="78a14-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="78a14-p108">大型或复杂更新所需的时间可能比其他更新所需的周期时间更长，以确保不会有任何用户受到负面影响。 我们不保证确切的发布时间线。</span><span class="sxs-lookup"><span data-stu-id="78a14-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="78a14-136">针对整个组织的定向发布</span><span class="sxs-lookup"><span data-stu-id="78a14-136">Targeted release for entire organization</span></span>

<span data-ttu-id="78a14-137">如果你在 [管理中心中](#set-up-the-release-option-in-the-admin-center) 设置此选项的发布选项，你的所有用户都将获得定向发布体验。</span><span class="sxs-lookup"><span data-stu-id="78a14-137">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="78a14-138">对于拥有 300 名用户以上的组织，我们建议使用此选项的测试订阅。</span><span class="sxs-lookup"><span data-stu-id="78a14-138">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="78a14-139">有关测试订阅信息，请联系你的 Microsoft 联系人。</span><span class="sxs-lookup"><span data-stu-id="78a14-139">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="78a14-140">针对选定用户的定向发布</span><span class="sxs-lookup"><span data-stu-id="78a14-140">Targeted release for selected users</span></span>

<span data-ttu-id="78a14-141">如果在 [管理中心](#set-up-the-release-option-in-the-admin-center) 中设置此选项的发布选项，你可以定义特定用户（通常是高级用户）以接收对特性和功能的早期访问。</span><span class="sxs-lookup"><span data-stu-id="78a14-141">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="78a14-142">定向发布的优势</span><span class="sxs-lookup"><span data-stu-id="78a14-142">Benefits of Targeted release</span></span>

<span data-ttu-id="78a14-143">定向发布允许管理员、变更经理或负责 Microsoft 365 更新的其他人通过允许他们：为即将进行的更改做好准备：</span><span class="sxs-lookup"><span data-stu-id="78a14-143">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="78a14-144">在新的更新面向组织中的所有用户发布之前，测试并验证这些更新。</span><span class="sxs-lookup"><span data-stu-id="78a14-144">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="78a14-145">在全球范围内发布更新前准备好用户通知和文档。</span><span class="sxs-lookup"><span data-stu-id="78a14-145">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="78a14-146">为即将到来的更新准备好内部技术支持。</span><span class="sxs-lookup"><span data-stu-id="78a14-146">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="78a14-147">仔细检查合规性和安全性审查。</span><span class="sxs-lookup"><span data-stu-id="78a14-147">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="78a14-148">在适用的位置使用功能控件，控制向最终用户发布的更新。</span><span class="sxs-lookup"><span data-stu-id="78a14-148">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="78a14-149">在管理中心设置发布选项</span><span class="sxs-lookup"><span data-stu-id="78a14-149">Set up the release option in the admin center</span></span>

<span data-ttu-id="78a14-150">你可以按照以下步骤更改你的组织接收 Microsoft 365 更新。</span><span class="sxs-lookup"><span data-stu-id="78a14-150">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="78a14-151">你必须是 Microsoft 365 中的全局管理员才能选择加入。</span><span class="sxs-lookup"><span data-stu-id="78a14-151">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="78a14-152">以下更改可能需要 24 小时才能在 Microsoft 365 中生效。</span><span class="sxs-lookup"><span data-stu-id="78a14-152">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="78a14-153">如果你在启用定向发布之后选择退出，你的用户可能无法再次访问那些尚未进入发布计划的功能。</span><span class="sxs-lookup"><span data-stu-id="78a14-153">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="78a14-154">在管理中心中，转到 **"设置**  >  **""组织** 设置"，在"组织 **配置文件**"选项卡下，选择"**发布首选项"。**</span><span class="sxs-lookup"><span data-stu-id="78a14-154">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="78a14-155">若要禁用定向发布，请选择"**标准发布"，** 然后选择"**保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="78a14-155">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="78a14-156">若要为组织中所有用户启用定向发布，请选择"面向所有人的发布"，然后选择"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="78a14-156">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="78a14-157">若要为组织中某些人员启用定向发布，请选择所选用户的定向发布，然后选择保存 **更改**。</span><span class="sxs-lookup"><span data-stu-id="78a14-157">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="78a14-158">选择 **"选择** 用户"以一次添加一个用户，或选择" **上载用户** "批量添加用户。</span><span class="sxs-lookup"><span data-stu-id="78a14-158">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="78a14-159">添加完用户后，请选择"**保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="78a14-159">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="78a14-160">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="78a14-160">Learn more</span></span>

<span data-ttu-id="78a14-161">了解如何[在](/office365/admin/manage/message-center)[Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)消息中心管理邮件，以获取有关即将推出的 Microsoft 365 更新和发布的通知。</span><span class="sxs-lookup"><span data-stu-id="78a14-161">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>

## <a name="related-articles"></a><span data-ttu-id="78a14-162">相关文章</span><span class="sxs-lookup"><span data-stu-id="78a14-162">Related Articles</span></span>

[<span data-ttu-id="78a14-163">Office 预览体验成员</span><span class="sxs-lookup"><span data-stu-id="78a14-163">Office Insider</span></span>](https://insider.office.com/join/windows)
