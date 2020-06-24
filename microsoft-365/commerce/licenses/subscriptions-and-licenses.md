---
title: 了解 Microsoft 365 for business 中的订阅和许可证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7ac93507-0e38-4398-8bfe-9c1d123cb387
description: '了解 Microsoft 365 for business 中的订阅和许可证，并了解谁可以分配许可证以及在将许可证分配给某人时，会发生什么情况。 '
ms.custom:
- okr_SMB
- AdminSurgePortfolio
ms.openlocfilehash: f83b2069bd1b4c86e2198252a54ed2e8e5c55a04
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844676"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a><span data-ttu-id="f7e71-103">了解 Microsoft 365 for business 中的订阅和许可证</span><span class="sxs-lookup"><span data-stu-id="f7e71-103">Understand subscriptions and licenses in Microsoft 365 for business</span></span>

<span data-ttu-id="f7e71-104">本文介绍了订阅和许可证之间的关系，并提供了有关[可分配许可证的人员](#find-out-who-can-assign-licenses)的详细信息，[了解在向某人分配许可证时会发生什么](#understand-what-happens-when-you-assign-a-license-to-someone)，以及[用户可以在哪些设备上安装 Office](#how-many-devices-can-people-install-office-on)。</span><span class="sxs-lookup"><span data-stu-id="f7e71-104">This article explains the relationship between subscriptions and licenses, and provides additional information about [who can assign licenses](#find-out-who-can-assign-licenses), [understanding what happens when you assign a license to someone](#understand-what-happens-when-you-assign-a-license-to-someone), and [how many devices can people install Office on](#how-many-devices-can-people-install-office-on).</span></span> <span data-ttu-id="f7e71-105">它还包括[了解非用户邮箱的许可证的](#understand-licenses-for-non-user-mailboxes)链接，以及[有关管理许可证的文章](#articles-about-managing-licenses)。</span><span class="sxs-lookup"><span data-stu-id="f7e71-105">It also includes links to [understanding licenses for non-user mailboxes](#understand-licenses-for-non-user-mailboxes), and [Articles about managing licenses](#articles-about-managing-licenses).</span></span>
  
<span data-ttu-id="f7e71-106">当你购买 Microsoft 365 for business 订阅时，你需要注册一组应用程序和服务，这些应用程序和服务按月或按年的频率付费。</span><span class="sxs-lookup"><span data-stu-id="f7e71-106">When you buy a subscription to Microsoft 365 for business, you sign up for a set of applications and services that you pay for on a either a monthly or an annual basis.</span></span> <span data-ttu-id="f7e71-107">作为订阅的一部分收到的应用程序和服务取决于所购买的产品，如 Microsoft 365 应用程序或 Microsoft 365 商业标准。</span><span class="sxs-lookup"><span data-stu-id="f7e71-107">The applications and services that you receive as part of your subscription depend on which product you purchased, such as Microsoft 365 Apps for business or Microsoft 365 Business Standard.</span></span> <span data-ttu-id="f7e71-108">您可以查看[购买 Microsoft 365 页面](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)上的每个产品所附带的功能。</span><span class="sxs-lookup"><span data-stu-id="f7e71-108">You can review what comes with each product on the [Buy Microsoft 365 page](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1).</span></span> 

<span data-ttu-id="f7e71-109">你可以在 Microsoft 365 中查看适用于中小型[企业的](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/licensing-microsoft-365-in-smb)不同许可选项</span><span class="sxs-lookup"><span data-stu-id="f7e71-109">You can review different Licensing options available in [Microsoft 365 for small and medium-sized businesses](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/licensing-microsoft-365-in-smb)</span></span>

<span data-ttu-id="f7e71-110">购买订阅时，根据组织中的人数指定所需的许可证数。</span><span class="sxs-lookup"><span data-stu-id="f7e71-110">When you buy a subscription, you specify the number of licenses that you need, based on how many people you have in your organization.</span></span> <span data-ttu-id="f7e71-111">完成购买后，为这些人员创建帐户，然后将许可证分配给每个人。</span><span class="sxs-lookup"><span data-stu-id="f7e71-111">After your purchase is complete, you create accounts for people, and then assign a license to each person.</span></span> <span data-ttu-id="f7e71-112">当您的组织需求发生变化时，您可以购买更多许可证以适应新人员，或在某人离开你的组织时将许可证重新分配给其他用户。</span><span class="sxs-lookup"><span data-stu-id="f7e71-112">As your organizational needs change, you can buy more licenses to accommodate new people, or reassign licenses to other users when someone leaves your organization.</span></span> 

<span data-ttu-id="f7e71-113">如果有一个以上的订阅，则可以针对每个订阅将许可证分配给不同人员。</span><span class="sxs-lookup"><span data-stu-id="f7e71-113">If you have more than one subscription, you can assign licenses to different people for each subscription.</span></span> <span data-ttu-id="f7e71-114">例如，您的所有用户都可以作为 Microsoft 365 业务标准订阅的一部分分配给所有 Microsoft 365 应用程序和服务，而用户的子集也可以通过单独的 Visio 订阅分配给 Visio Online。</span><span class="sxs-lookup"><span data-stu-id="f7e71-114">For example, all of your users could be assigned to all Microsoft 365 applications and services as part of an Microsoft 365 Business Standard subscription, while a subset of users could also be assigned to Visio Online through a separate Visio subscription.</span></span> 

  
## <a name="find-out-who-can-assign-licenses"></a><span data-ttu-id="f7e71-115">了解谁可以分配许可证</span><span class="sxs-lookup"><span data-stu-id="f7e71-115">Find out who can assign licenses</span></span>

<span data-ttu-id="f7e71-116">Different types of admins can work with licenses in different ways, depending on their roles.</span><span class="sxs-lookup"><span data-stu-id="f7e71-116">Different types of admins can work with licenses in different ways, depending on their roles.</span></span> <span data-ttu-id="f7e71-117">The following table lists the most common options.</span><span class="sxs-lookup"><span data-stu-id="f7e71-117">The following table lists the most common options.</span></span> <span data-ttu-id="f7e71-118">For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f7e71-118">For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  
|<span data-ttu-id="f7e71-119">**管理员角色**</span><span class="sxs-lookup"><span data-stu-id="f7e71-119">**Admin role**</span></span>|<span data-ttu-id="f7e71-120">**分配许可证**</span><span class="sxs-lookup"><span data-stu-id="f7e71-120">**Assign a license**</span></span>|<span data-ttu-id="f7e71-121">**删除许可证**</span><span class="sxs-lookup"><span data-stu-id="f7e71-121">**Remove a license**</span></span>|<span data-ttu-id="f7e71-122">**购买更多许可证**</span><span class="sxs-lookup"><span data-stu-id="f7e71-122">**Purchase more licenses**</span></span>|<span data-ttu-id="f7e71-123">**删除帐户**</span><span class="sxs-lookup"><span data-stu-id="f7e71-123">**Delete an account**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f7e71-124">全局管理员</span><span class="sxs-lookup"><span data-stu-id="f7e71-124">Global admin</span></span>  <br/> |<span data-ttu-id="f7e71-125">是</span><span class="sxs-lookup"><span data-stu-id="f7e71-125">Yes</span></span>  <br/> |<span data-ttu-id="f7e71-126">是</span><span class="sxs-lookup"><span data-stu-id="f7e71-126">Yes</span></span>  <br/> |<span data-ttu-id="f7e71-127">是</span><span class="sxs-lookup"><span data-stu-id="f7e71-127">Yes</span></span>  <br/> |<span data-ttu-id="f7e71-128">是</span><span class="sxs-lookup"><span data-stu-id="f7e71-128">Yes</span></span>  <br/> |
|<span data-ttu-id="f7e71-129">帐务管理员</span><span class="sxs-lookup"><span data-stu-id="f7e71-129">Billing admin</span></span>  <br/> |<span data-ttu-id="f7e71-130">否</span><span class="sxs-lookup"><span data-stu-id="f7e71-130">No</span></span>  <br/> |<span data-ttu-id="f7e71-131">否</span><span class="sxs-lookup"><span data-stu-id="f7e71-131">No</span></span>  <br/> |<span data-ttu-id="f7e71-132">必需</span><span class="sxs-lookup"><span data-stu-id="f7e71-132">Yes</span></span>  <br/> |<span data-ttu-id="f7e71-133">否</span><span class="sxs-lookup"><span data-stu-id="f7e71-133">No</span></span>  <br/> |
|<span data-ttu-id="f7e71-134">用户管理管理员</span><span class="sxs-lookup"><span data-stu-id="f7e71-134">User management admin</span></span>  <br/> |<span data-ttu-id="f7e71-135">是</span><span class="sxs-lookup"><span data-stu-id="f7e71-135">Yes</span></span>  <br/> |<span data-ttu-id="f7e71-136">是</span><span class="sxs-lookup"><span data-stu-id="f7e71-136">Yes</span></span>  <br/> |<span data-ttu-id="f7e71-137">否</span><span class="sxs-lookup"><span data-stu-id="f7e71-137">No</span></span>  <br/> |<span data-ttu-id="f7e71-138">可访问</span><span class="sxs-lookup"><span data-stu-id="f7e71-138">Yes</span></span>  <br/> |
|<span data-ttu-id="f7e71-139">服务管理员</span><span class="sxs-lookup"><span data-stu-id="f7e71-139">Service admin</span></span>  <br/> |<span data-ttu-id="f7e71-140">否</span><span class="sxs-lookup"><span data-stu-id="f7e71-140">No</span></span>  <br/> |<span data-ttu-id="f7e71-141">否</span><span class="sxs-lookup"><span data-stu-id="f7e71-141">No</span></span>  <br/> |<span data-ttu-id="f7e71-142">否</span><span class="sxs-lookup"><span data-stu-id="f7e71-142">No</span></span>  <br/> |<span data-ttu-id="f7e71-143">否</span><span class="sxs-lookup"><span data-stu-id="f7e71-143">No</span></span>  <br/> |
|<span data-ttu-id="f7e71-144">密码管理员</span><span class="sxs-lookup"><span data-stu-id="f7e71-144">Password admin</span></span>  <br/> |<span data-ttu-id="f7e71-145">否</span><span class="sxs-lookup"><span data-stu-id="f7e71-145">No</span></span>  <br/> |<span data-ttu-id="f7e71-146">否</span><span class="sxs-lookup"><span data-stu-id="f7e71-146">No</span></span>  <br/> |<span data-ttu-id="f7e71-147">否</span><span class="sxs-lookup"><span data-stu-id="f7e71-147">No</span></span>  <br/> |<span data-ttu-id="f7e71-148">否</span><span class="sxs-lookup"><span data-stu-id="f7e71-148">No</span></span>  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a><span data-ttu-id="f7e71-149">了解为某人分配许可证时会发生的情况</span><span class="sxs-lookup"><span data-stu-id="f7e71-149">Understand what happens when you assign a license to someone</span></span>

<span data-ttu-id="f7e71-150">下表列出了在为某人分配许可证时会自动发生的情况：</span><span class="sxs-lookup"><span data-stu-id="f7e71-150">The following table lists what automatically happens when you assign a license to someone:</span></span>
  
|<span data-ttu-id="f7e71-151">**如果订阅中有此服务**</span><span class="sxs-lookup"><span data-stu-id="f7e71-151">**If the subscription has this service**</span></span>|<span data-ttu-id="f7e71-152">**将会自动发生该情况**</span><span class="sxs-lookup"><span data-stu-id="f7e71-152">**This automatically happens**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f7e71-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f7e71-153">Exchange Online</span></span>  <br/> |<span data-ttu-id="f7e71-154">将为该人员创建一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="f7e71-154">A mailbox is created for that person.</span></span>  <br/> <span data-ttu-id="f7e71-155">若要了解此任务的完成 SLA，请参阅["设置 ..."Microsoft 365 管理中心中的邮件](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="f7e71-155">To learn about the SLA for this task to be completed, see ["Setting up..." messages in the Microsoft 365 admin center](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center).</span></span> |
|<span data-ttu-id="f7e71-156">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f7e71-156">SharePoint Online</span></span>  <br/> |<span data-ttu-id="f7e71-157">将为该人员分配默认 SharePoint Online 团队网站的编辑权限。</span><span class="sxs-lookup"><span data-stu-id="f7e71-157">Edit permissions to the default SharePoint Online team site are assigned to that person.</span></span>  <br/> |
|<span data-ttu-id="f7e71-158">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f7e71-158">Skype for Business Online</span></span>  <br/> |<span data-ttu-id="f7e71-159">该人员将拥有与许可证关联的功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="f7e71-159">The person will have access to the features associated with the license.</span></span>  <br/> |
|<span data-ttu-id="f7e71-160">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="f7e71-160">Microsoft 365 Apps for enterprise</span></span>  <br/> |<span data-ttu-id="f7e71-161">此人将能够将 Microsoft Office 下载到多达 5 台的 Mac 或电脑、5 台平板电脑和 5 部智能手机上。</span><span class="sxs-lookup"><span data-stu-id="f7e71-161">The person will be able to download Microsoft Office on up to 5 Macs or PCs, 5 tablets, and 5 smartphones.</span></span>  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a><span data-ttu-id="f7e71-162">可以在多少台设备上安装 Office？</span><span class="sxs-lookup"><span data-stu-id="f7e71-162">How many devices can people install Office on?</span></span>

<span data-ttu-id="f7e71-163">如果订阅中包含以下任何产品，则每个人都可以将 Office 安装到多达 5 台的 Mac 或电脑、5 台平板电脑和 5 部手机上。</span><span class="sxs-lookup"><span data-stu-id="f7e71-163">If your subscription includes any of the following products, each person can install Office on up to 5 PCs or Mac, 5 tablets, and 5 phones.</span></span>
  
- <span data-ttu-id="f7e71-164">Microsoft 365 商业应用版</span><span class="sxs-lookup"><span data-stu-id="f7e71-164">Microsoft 365 Apps for business</span></span>
    
- <span data-ttu-id="f7e71-165">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="f7e71-165">Microsoft 365 Business Standard</span></span>
    
- <span data-ttu-id="f7e71-166">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="f7e71-166">Microsoft 365 Apps for enterprise</span></span>
    
- <span data-ttu-id="f7e71-167">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="f7e71-167">Office 365 Enterprise E3</span></span>
    
- <span data-ttu-id="f7e71-168">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="f7e71-168">Office 365 Enterprise E5</span></span>
    
## <a name="understand-licenses-for-non-user-mailboxes"></a><span data-ttu-id="f7e71-169">了解非用户邮箱的许可证</span><span class="sxs-lookup"><span data-stu-id="f7e71-169">Understand licenses for non-user mailboxes</span></span>

<span data-ttu-id="f7e71-170">You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="f7e71-170">You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB).</span></span> <span data-ttu-id="f7e71-171">For more about non-user mailboxes, see the following articles:</span><span class="sxs-lookup"><span data-stu-id="f7e71-171">For more about non-user mailboxes, see the following articles:</span></span>
  
- [<span data-ttu-id="f7e71-172">创建共享邮箱</span><span class="sxs-lookup"><span data-stu-id="f7e71-172">Create a shared mailbox</span></span>](../../admin/email/create-a-shared-mailbox.md)
    
- <span data-ttu-id="f7e71-173">[Exchange Online 中的共享邮箱](https://go.microsoft.com/fwlink/p/?linkid=847433)，用于所有其他 Microsoft 365 计划。</span><span class="sxs-lookup"><span data-stu-id="f7e71-173">[Shared Mailboxes in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=847433) for all other Microsoft 365 plans.</span></span> 
    
- [<span data-ttu-id="f7e71-174">创建和管理会议室邮箱</span><span class="sxs-lookup"><span data-stu-id="f7e71-174">Create and Manage Room Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- [<span data-ttu-id="f7e71-175">管理设备邮箱</span><span class="sxs-lookup"><span data-stu-id="f7e71-175">Manage Equipment Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847435)
    
## <a name="articles-about-managing-licenses"></a><span data-ttu-id="f7e71-176">有关管理许可证的文章</span><span class="sxs-lookup"><span data-stu-id="f7e71-176">Articles about managing licenses</span></span>

- [<span data-ttu-id="f7e71-177">向用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="f7e71-177">Assign licenses to users</span></span>](../../admin/manage/assign-licenses-to-users.md)
    
- [<span data-ttu-id="f7e71-178">删除用户许可证</span><span class="sxs-lookup"><span data-stu-id="f7e71-178">Remove licenses from users</span></span>](../../admin/manage/remove-licenses-from-users.md)
    
- [<span data-ttu-id="f7e71-179">购买订阅的许可证</span><span class="sxs-lookup"><span data-stu-id="f7e71-179">Buy licenses for your subscription</span></span>](buy-licenses.md)
    
- [<span data-ttu-id="f7e71-180">购买另一个订阅</span><span class="sxs-lookup"><span data-stu-id="f7e71-180">Buy another subscription</span></span>](../buy-another-subscription.md)
    
- [<span data-ttu-id="f7e71-181">购买或编辑附加设备</span><span class="sxs-lookup"><span data-stu-id="f7e71-181">Buy or edit an add-on</span></span>](../buy-or-edit-an-add-on.md)
    
- [<span data-ttu-id="f7e71-182">从订阅中删除许可证</span><span class="sxs-lookup"><span data-stu-id="f7e71-182">Remove licenses from your subscription</span></span>](remove-licenses-from-subscription.md)
    
- [<span data-ttu-id="f7e71-183">解决许可证冲突</span><span class="sxs-lookup"><span data-stu-id="f7e71-183">Resolve license conflicts</span></span>](../../admin/manage/resolve-license-conflicts.md)
    
- [<span data-ttu-id="f7e71-184">管理 Yammer 用户许可证</span><span class="sxs-lookup"><span data-stu-id="f7e71-184">Manage Yammer user licenses</span></span>](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
