---
title: 设置标准或目标发布选项
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: 了解如何为 Microsoft 365 管理中心中的新产品和功能更新设置发布选项。
ms.openlocfilehash: 3a7a0562edef527718816bba6e67ea948cfad6b5
ms.sourcegitcommit: 708857a82eab3d37da1dec027399b09bd306a5dd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "44249880"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="95869-103">设置标准或目标发布选项</span><span class="sxs-lookup"><span data-stu-id="95869-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="95869-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="95869-104">The admin center is changing.</span></span> <span data-ttu-id="95869-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="95869-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="95869-106">在 Microsoft 365 中，你将收到新的产品更新和功能，因为它们变为可用，而不是每几年进行一次成本更新。</span><span class="sxs-lookup"><span data-stu-id="95869-106">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="95869-107">你可以管理组织接收这些更新的方式。</span><span class="sxs-lookup"><span data-stu-id="95869-107">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="95869-108">例如，你可以注册抢先体验新发布版本，保证组织能够第一时间接收到更新。</span><span class="sxs-lookup"><span data-stu-id="95869-108">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="95869-109">你可以指定只有某几个人接收更新。</span><span class="sxs-lookup"><span data-stu-id="95869-109">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="95869-110">或者，你可以保留默认的发布计划，稍后接收更新。</span><span class="sxs-lookup"><span data-stu-id="95869-110">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="95869-111">本文介绍不同的发布选项，以及如何将它们用于您的组织。</span><span class="sxs-lookup"><span data-stu-id="95869-111">This article explains the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="95869-112">本文中所述的 Microsoft 365 更新适用于 Microsoft 365、SharePoint Online 和 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="95869-112">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="95869-113">这些更新不适用于 Skype for Business 及相关服务。</span><span class="sxs-lookup"><span data-stu-id="95869-113">They do not apply to Skype for Business and related services.</span></span> <span data-ttu-id="95869-114">这些发布选项的目标是，将更改发布到 Microsoft 365 的最佳方法是，但不能始终保证，也不能保证所有更新。</span><span class="sxs-lookup"><span data-stu-id="95869-114">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="95869-115">工作原理 - 发布验证</span><span class="sxs-lookup"><span data-stu-id="95869-115">How it works - release validation</span></span>

<span data-ttu-id="95869-116">任何新版本都会先由功能团队进行测试和验证，然后由整个 Microsoft 365 功能团队进行测试，然后再访问所有 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="95869-116">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="95869-117">内部测试和验证后，下一步是向选择加入的客户" **定向发布**"（以前称为首次发布）。</span><span class="sxs-lookup"><span data-stu-id="95869-117">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="95869-118">在每个发布环节，Microsoft 都会收集反馈，通过监视关键的使用情况指标验证质量。</span><span class="sxs-lookup"><span data-stu-id="95869-118">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="95869-119">采取逐步进行的一系列验证，确保全球范围内发布的版本尽可能的稳定。</span><span class="sxs-lookup"><span data-stu-id="95869-119">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="95869-120">发布环节如下图所示。</span><span class="sxs-lookup"><span data-stu-id="95869-120">The releases are pictured in the following figure.</span></span> 
  
![Microsoft 365 的发布验证环](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="95869-122">对于重要更新， [Microsoft 365 路线图](https://products.office.com/business/office-365-roadmap)最初会通知客户。</span><span class="sxs-lookup"><span data-stu-id="95869-122">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="95869-123">随着更新越接近，将通过[Microsoft 365 消息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)进行传递。</span><span class="sxs-lookup"><span data-stu-id="95869-123">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="95869-124">你需要 Microsoft 365 或 Azure AD 帐户，才能通过[管理中心](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)访问你的消息中心。</span><span class="sxs-lookup"><span data-stu-id="95869-124">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="95869-125">Microsoft 365 家庭版计划用户没有管理中心。</span><span class="sxs-lookup"><span data-stu-id="95869-125">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="95869-126">标准发布</span><span class="sxs-lookup"><span data-stu-id="95869-126">Standard release</span></span>

<span data-ttu-id="95869-127">这是默认选项，当你和你的用户广泛发布到所有客户时，你和你的用户将收到最新的更新。</span><span class="sxs-lookup"><span data-stu-id="95869-127">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="95869-128">一种很好的做法是将大多数用户留在**标准版的版本**中，将 IT 专业人员和高级用户保留在**目标版本**中，以评估新功能并准备团队以支持业务用户和执行官。</span><span class="sxs-lookup"><span data-stu-id="95869-128">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="95869-129">如果你从定向发布切换回标准发布计划，你的用户可能无法再次访问那些尚未进入标准发布的功能。</span><span class="sxs-lookup"><span data-stu-id="95869-129">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="95869-130">定向发布</span><span class="sxs-lookup"><span data-stu-id="95869-130">Targeted release</span></span>

<span data-ttu-id="95869-p107">使用此选项，你和你的用户可以抢先体验最新更新，并通过提供早期反馈帮助改进产品。你可以选择让某几个人或整个组织先接收更新。</span><span class="sxs-lookup"><span data-stu-id="95869-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="95869-p108">大型或复杂更新所需的时间可能比其他更新所需的周期时间更长，以确保不会有任何用户受到负面影响。 我们不保证确切的发布时间线。</span><span class="sxs-lookup"><span data-stu-id="95869-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="95869-135">针对整个组织的定向发布</span><span class="sxs-lookup"><span data-stu-id="95869-135">Targeted release for entire organization</span></span>

<span data-ttu-id="95869-136">如果在管理中心为此选项设置了 "[发布" 选项](#set-up-the-release-option-in-the-admin-center)，则所有用户都将获得目标发布体验。</span><span class="sxs-lookup"><span data-stu-id="95869-136">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="95869-137">对于拥有 300 名用户以上的组织，我们建议使用此选项的测试订阅。</span><span class="sxs-lookup"><span data-stu-id="95869-137">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="95869-138">有关测试订阅信息，请联系你的 Microsoft 联系人。</span><span class="sxs-lookup"><span data-stu-id="95869-138">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="95869-139">针对选定用户的定向发布</span><span class="sxs-lookup"><span data-stu-id="95869-139">Targeted release for selected users</span></span>

<span data-ttu-id="95869-140">如果在[管理中心中设置](#set-up-the-release-option-in-the-admin-center)了 "发布" 选项，则可以定义特定用户（通常为高级用户），以接收对功能和功能的早期访问权限。</span><span class="sxs-lookup"><span data-stu-id="95869-140">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="95869-141">定向发布的优势</span><span class="sxs-lookup"><span data-stu-id="95869-141">Benefits of Targeted release</span></span>

<span data-ttu-id="95869-142">目标发布允许管理员、变更管理者或任何其他人负责 Microsoft 365 更新，以准备即将进行的更改，具体方法是让他们：</span><span class="sxs-lookup"><span data-stu-id="95869-142">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="95869-143">在新的更新面向组织中的所有用户发布之前，测试并验证这些更新。</span><span class="sxs-lookup"><span data-stu-id="95869-143">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="95869-144">在全球范围内发布更新前准备好用户通知和文档。</span><span class="sxs-lookup"><span data-stu-id="95869-144">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="95869-145">为即将到来的更新准备好内部技术支持。</span><span class="sxs-lookup"><span data-stu-id="95869-145">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="95869-146">仔细检查合规性和安全性审查。</span><span class="sxs-lookup"><span data-stu-id="95869-146">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="95869-147">在适用的位置使用功能控件，控制向最终用户发布的更新。</span><span class="sxs-lookup"><span data-stu-id="95869-147">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="95869-148">在管理中心中设置 "发布" 选项</span><span class="sxs-lookup"><span data-stu-id="95869-148">Set up the release option in the admin center</span></span>

<span data-ttu-id="95869-149">您可以按照以下步骤更改您的组织接收 Microsoft 365 更新的方式。</span><span class="sxs-lookup"><span data-stu-id="95869-149">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="95869-150">您必须是 Microsoft 365 中的全局管理员才能自愿加入。</span><span class="sxs-lookup"><span data-stu-id="95869-150">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="95869-151">可能需要长达24小时才能使以下更改在 Microsoft 365 中生效。</span><span class="sxs-lookup"><span data-stu-id="95869-151">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="95869-152">如果你在启用定向发布之后选择退出，你的用户可能无法再次访问那些尚未进入发布计划的功能。</span><span class="sxs-lookup"><span data-stu-id="95869-152">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="95869-153">在管理中心中，转到 "**设置**"  >  **设置**，在 "**组织配置文件**" 选项卡下，选择 "**发布首选项**"。</span><span class="sxs-lookup"><span data-stu-id="95869-153">In the admin center, go to the **Settings** > **Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="95869-154">若要禁用目标发布，请选择 "**标准发布**"，然后选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="95869-154">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="95869-155">若要为组织中的所有用户启用目标版本，请为 "所有人" 选择 "**目标版本**"，然后选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="95869-155">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="95869-156">若要为组织中的某些人员启用目标发布，请选择 "选择**的用户的目标发布**"，然后选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="95869-156">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="95869-157">选择 "**选择用户**" 可一次添加一个用户，或**上传用户**以批量添加用户。</span><span class="sxs-lookup"><span data-stu-id="95869-157">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="95869-158">添加完用户后，请选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="95869-158">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="95869-159">了解更多</span><span class="sxs-lookup"><span data-stu-id="95869-159">Learn more</span></span>

<span data-ttu-id="95869-160">了解如何管理[Microsoft 365 消息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)中的[邮件](https://docs.microsoft.com/office365/admin/manage/message-center)，以获取有关即将推出的 Microsoft 365 更新和版本的通知。</span><span class="sxs-lookup"><span data-stu-id="95869-160">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
