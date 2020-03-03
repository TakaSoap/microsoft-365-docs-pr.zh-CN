---
title: 在 Office 365 中设置标准发布或定向发布选项
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
ms.openlocfilehash: d6c2eab340f4401fb31e4d9e814fbd326573569a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361797"
---
# <a name="set-up-the-standard-or-targeted-release-options-in-office-365"></a><span data-ttu-id="3e390-103">在 Office 365 中设置标准发布或定向发布选项</span><span class="sxs-lookup"><span data-stu-id="3e390-103">Set up the Standard or Targeted release options in Office 365</span></span>

<span data-ttu-id="3e390-p101">选择 Office 365，一旦有新的产品更新和功能推出，你就可以立即收到，不必每隔几年进行一次代价高昂的更新。你可以管理组织接收这些更新的方式。例如，你可以注册抢先体验新发布版本，保证组织能够第一时间接收到更新。你可以指定只有某几个人接收更新。或者，你可以保留默认的发布计划，稍后接收更新。本文介绍不同的发布选项，以及如何为你的组织使用这些选项。</span><span class="sxs-lookup"><span data-stu-id="3e390-p101">With Office 365, you receive new product updates and features as they become available instead of doing costly updates every few years. You can manage how your organization receives these updates. For example, you can sign up for an early release so that your organization receives updates first. You can designate that only certain individuals receive the updates. Or, you can remain on the default release schedule and receive the updates later. This article explain the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3e390-p102">本文所述的 Office 365 更新适用于 Office 365、SharePoint Online 和 Exchange Online。这些更新不适用于 Skype for Business 及相关服务。这些发布选项均为有针对性、尽力而为的 Office 365 变更发布方法，但不能保证始终如此或对于所有更新皆是如此。</span><span class="sxs-lookup"><span data-stu-id="3e390-p102">The Office 365 updates described in this article apply to Office 365, SharePoint Online, and Exchange Online. They do not apply to Skype for Business and related services. These release options are targeted, best effort ways to release changes to Office 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="3e390-113">工作原理 - 发布验证</span><span class="sxs-lookup"><span data-stu-id="3e390-113">How it works - release validation</span></span>

<span data-ttu-id="3e390-114">任何新版本都会先由功能团队进行测试和验证，然后由整个 Office 365 功能团队进行测试，然后再访问所有 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="3e390-114">Any new release is first tested and validated by the feature team, then by the entire Office 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="3e390-115">内部测试和验证后，下一步是向选择加入的客户" **定向发布**"（以前称为首次发布）。</span><span class="sxs-lookup"><span data-stu-id="3e390-115">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="3e390-116">在每个发布环节，Microsoft 都会收集反馈，通过监视关键的使用情况指标验证质量。</span><span class="sxs-lookup"><span data-stu-id="3e390-116">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="3e390-117">采取逐步进行的一系列验证，确保全球范围内发布的版本尽可能的稳定。</span><span class="sxs-lookup"><span data-stu-id="3e390-117">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="3e390-118">发布环节如下图所示。</span><span class="sxs-lookup"><span data-stu-id="3e390-118">The releases are pictured in the following figure.</span></span> 
  
![Office 365 的发布验证环](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="3e390-120">对于重要更新，Office 客户最初由[Microsoft 365 路线图](https://products.office.com/business/office-365-roadmap)通知。</span><span class="sxs-lookup"><span data-stu-id="3e390-120">For significant updates, Office customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="3e390-121">随着更新越接近，将通过[Office 365 消息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)进行传递。</span><span class="sxs-lookup"><span data-stu-id="3e390-121">As an update gets closer to rolling out, it is communicated through your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="3e390-122">你需要 Office 365 或 Azure AD 帐户通过[管理中心](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)访问你的消息中心。</span><span class="sxs-lookup"><span data-stu-id="3e390-122">You need an Office 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="3e390-123">Office 365 家庭版计划用户没有管理中心。</span><span class="sxs-lookup"><span data-stu-id="3e390-123">Office 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="3e390-124">标准发布</span><span class="sxs-lookup"><span data-stu-id="3e390-124">Standard release</span></span>

<span data-ttu-id="3e390-125">这是默认选项，当你和你的用户广泛发布到所有客户时，你和你的用户将收到最新的更新。</span><span class="sxs-lookup"><span data-stu-id="3e390-125">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="3e390-126">一种很好的做法是将大多数用户留在**标准版的版本**中，将 IT 专业人员和高级用户保留在**目标版本**中，以评估新功能并准备团队以支持业务用户和执行官。</span><span class="sxs-lookup"><span data-stu-id="3e390-126">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3e390-127">如果你从定向发布切换回标准发布计划，你的用户可能无法再次访问那些尚未进入标准发布的功能。</span><span class="sxs-lookup"><span data-stu-id="3e390-127">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="3e390-128">定向发布</span><span class="sxs-lookup"><span data-stu-id="3e390-128">Targeted release</span></span>

<span data-ttu-id="3e390-p106">使用此选项，你和你的用户可以抢先体验最新更新，并通过提供早期反馈帮助改进产品。你可以选择让某几个人或整个组织先接收更新。</span><span class="sxs-lookup"><span data-stu-id="3e390-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3e390-p107">大型或复杂更新所需的时间可能比其他更新所需的周期时间更长，以确保不会有任何用户受到负面影响。 我们不保证确切的发布时间线。</span><span class="sxs-lookup"><span data-stu-id="3e390-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="3e390-133">针对整个组织的定向发布</span><span class="sxs-lookup"><span data-stu-id="3e390-133">Targeted release for entire organization</span></span>

<span data-ttu-id="3e390-134">如果在管理中心为此选项设置了 "[发布" 选项](#set-up-the-release-option-in-the-admin-center)，则所有用户都将获得目标发布体验。</span><span class="sxs-lookup"><span data-stu-id="3e390-134">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="3e390-135">对于拥有 300 名用户以上的组织，我们建议使用此选项的测试订阅。</span><span class="sxs-lookup"><span data-stu-id="3e390-135">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="3e390-136">有关测试订阅信息，请联系你的 Microsoft 联系人。</span><span class="sxs-lookup"><span data-stu-id="3e390-136">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="3e390-137">针对选定用户的定向发布</span><span class="sxs-lookup"><span data-stu-id="3e390-137">Targeted release for selected users</span></span>

<span data-ttu-id="3e390-138">如果在[管理中心中设置](#set-up-the-release-option-in-the-admin-center)了 "发布" 选项，则可以定义特定用户（通常为高级用户），以接收对功能和功能的早期访问权限。</span><span class="sxs-lookup"><span data-stu-id="3e390-138">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="3e390-139">定向发布的优势</span><span class="sxs-lookup"><span data-stu-id="3e390-139">Benefits of Targeted release</span></span>

<span data-ttu-id="3e390-140">定向发布可让管理员、更改管理者或负责 Office 365 更新的其他任何人执行以下操作，准备好即将到来的更新：</span><span class="sxs-lookup"><span data-stu-id="3e390-140">Targeted release allows admins, change managers, or anyone else responsible for Office 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="3e390-141">在新的更新面向组织中的所有用户发布之前，测试并验证这些更新。</span><span class="sxs-lookup"><span data-stu-id="3e390-141">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="3e390-142">在全球范围内发布更新前准备好用户通知和文档。</span><span class="sxs-lookup"><span data-stu-id="3e390-142">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="3e390-143">为即将到来的更新准备好内部技术支持。</span><span class="sxs-lookup"><span data-stu-id="3e390-143">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="3e390-144">仔细检查合规性和安全性审查。</span><span class="sxs-lookup"><span data-stu-id="3e390-144">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="3e390-145">在适用的位置使用功能控件，控制向最终用户发布的更新。</span><span class="sxs-lookup"><span data-stu-id="3e390-145">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="3e390-146">在管理中心中设置 "发布" 选项</span><span class="sxs-lookup"><span data-stu-id="3e390-146">Set up the release option in the admin center</span></span>

<span data-ttu-id="3e390-p109">你可以按照以下步骤操作，更改你的组织接收 Office 365 更新的方式。必须成为 Office 365 中的全局管理员才能选择加入。</span><span class="sxs-lookup"><span data-stu-id="3e390-p109">You can change how your organization receives Office 365 updates by following these steps. You have to be a global admin in Office 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3e390-p110">以下更改最长可能要 24 小时才能在 Office 365 中生效。如果你在启用定向发布之后选择退出，你的用户可能无法再次访问那些尚未进入发布计划的功能。</span><span class="sxs-lookup"><span data-stu-id="3e390-p110">It can take up to 24 hours for the below changes to take effect in Office 365. If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="3e390-151">在管理中心中，转到 "**设置** > "**设置**，在 "**组织配置文件**" 选项卡下，选择 "**发布首选项**"。</span><span class="sxs-lookup"><span data-stu-id="3e390-151">In the admin center, go to the **Settings** > **Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="3e390-152">若要禁用目标发布，请选择 "**标准发布**"，然后选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="3e390-152">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="3e390-153">若要为组织中的所有用户启用目标版本，请为 "所有人" 选择 "**目标版本**"，然后选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="3e390-153">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="3e390-154">若要为组织中的某些人员启用目标发布，请选择 "选择**的用户的目标发布**"，然后选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="3e390-154">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="3e390-155">选择 "**选择用户**" 可一次添加一个用户，或**上传用户**以批量添加用户。</span><span class="sxs-lookup"><span data-stu-id="3e390-155">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="3e390-156">添加完用户后，请选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="3e390-156">When you're done adding users, select **Save changes**.</span></span>



## <a name="get-the-targeted-release-version-of-office"></a><span data-ttu-id="3e390-157">获取 Office 的目标发行版</span><span class="sxs-lookup"><span data-stu-id="3e390-157">Get the Targeted release version of Office</span></span>

<span data-ttu-id="3e390-p111">若要安装 Office 的定向发布版本，[请按这些步骤进行操作](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead)。这可以让你率先访问 Windows 桌面版 Office 2016 的新功能。</span><span class="sxs-lookup"><span data-stu-id="3e390-p111">To install a targeted release build of Office, [follow these steps](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). This gives you early access to the new features of Office 2016 for Windows desktops.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="3e390-160">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="3e390-160">Learn more</span></span>

<span data-ttu-id="3e390-161">了解如何管理[Office 365 消息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)中的[邮件](https://docs.microsoft.com/office365/admin/manage/message-center)，以获取有关即将推出的 Office 365 更新和版本的通知。</span><span class="sxs-lookup"><span data-stu-id="3e390-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Office 365 updates and releases.</span></span>
