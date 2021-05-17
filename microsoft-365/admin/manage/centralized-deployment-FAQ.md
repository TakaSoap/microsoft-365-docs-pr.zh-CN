---
title: 集中部署常见问题解答
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 从管理中心查看有关集中部署的Microsoft 365解答。
ms.openlocfilehash: 60d7a91da738803976b6823009450124d7b57814
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579298"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="49bf6-103">集中部署常见问题解答</span><span class="sxs-lookup"><span data-stu-id="49bf6-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="49bf6-104">建议 Office 365 管理员通过集中部署将 Office 加载项 (Word、Excel、PowerPoint 和 Outlook) 部署到组织内部的用户和组，只要组织满足本文所述的使用集中部署的所有要求。</span><span class="sxs-lookup"><span data-stu-id="49bf6-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="49bf6-105">我如何知道我的组织是否设置为集中部署？</span><span class="sxs-lookup"><span data-stu-id="49bf6-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="49bf6-106">外接程序的集中部署要求用户使用 Microsoft 365 企业应用版 (，并且使用其组织登录凭据登录 Office 并拥有) 邮箱Exchange Online登录。</span><span class="sxs-lookup"><span data-stu-id="49bf6-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="49bf6-107">订阅目录必须位于订阅目录中，或已联合Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="49bf6-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="49bf6-108">仅联机邮箱支持集中部署。</span><span class="sxs-lookup"><span data-stu-id="49bf6-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="49bf6-109">它不支持部署到内部部署Exchange邮箱。</span><span class="sxs-lookup"><span data-stu-id="49bf6-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="49bf6-110">可以使用集中[部署兼容性检查器](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   来确定你的订阅是否符合条件。</span><span class="sxs-lookup"><span data-stu-id="49bf6-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="49bf6-111">如何使用集中部署将外接程序用户分配作为目标？</span><span class="sxs-lookup"><span data-stu-id="49bf6-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="49bf6-112">集中部署支持向租户中的单个用户、组和每个人分配工作。</span><span class="sxs-lookup"><span data-stu-id="49bf6-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="49bf6-113">集中部署可用于顶级组或没有父组的组的用户，但不能用于嵌套组或具有父组的组的用户。</span><span class="sxs-lookup"><span data-stu-id="49bf6-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="49bf6-114">集中部署也是大多数组Azure Active Directory的一部分，Office 365组、通讯组列表和安全组。</span><span class="sxs-lookup"><span data-stu-id="49bf6-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="49bf6-115">为了便于管理，最好使用组分配而不是单个用户分配。</span><span class="sxs-lookup"><span data-stu-id="49bf6-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="49bf6-116">有关详细信息，请参阅用户 [和组分配](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments)。</span><span class="sxs-lookup"><span data-stu-id="49bf6-116">For more details, see [User and Group assignments](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="49bf6-117">加载项向所有用户显示需要多久？</span><span class="sxs-lookup"><span data-stu-id="49bf6-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="49bf6-118">外接程序最多可能需要 24 小时才能显示给所有用户。</span><span class="sxs-lookup"><span data-stu-id="49bf6-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="49bf6-119">外接程序更新、打开或关闭的更改或者外接程序删除可能需要相同的时间。</span><span class="sxs-lookup"><span data-stu-id="49bf6-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="49bf6-120">作为管理员，如何管理用户对组织的外接程序的访问权限？</span><span class="sxs-lookup"><span data-stu-id="49bf6-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="49bf6-121">为了便于将加载项部署到用户、组或整个组织，我们建议管理员使用集中部署。</span><span class="sxs-lookup"><span data-stu-id="49bf6-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="49bf6-122">有关管理用户访问权的信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="49bf6-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="49bf6-123">通过在所有客户端上关闭 Office Store 来阻止外接程序 (除Outlook) </span><span class="sxs-lookup"><span data-stu-id="49bf6-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="49bf6-124">指定可安装和管理 Outlook 加载项的管理员和用户</span><span class="sxs-lookup"><span data-stu-id="49bf6-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="49bf6-125">集中部署是否使管理员能够灵活地选择外接程序Outlook部署方法？</span><span class="sxs-lookup"><span data-stu-id="49bf6-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="49bf6-126">是的。</span><span class="sxs-lookup"><span data-stu-id="49bf6-126">Yes.</span></span> <span data-ttu-id="49bf6-127">集中部署使管理员能够灵活地选择外接程序部署期间Outlook外接程序的三种部署方法之一：</span><span class="sxs-lookup"><span data-stu-id="49bf6-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="49bf6-128">**修复 (默认值)**  外接程序将自动部署到已分配的用户，并且他们无法删除它。</span><span class="sxs-lookup"><span data-stu-id="49bf6-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="49bf6-129">**可用** 用户可以通过选择"主页"Outlook管理员管理的">"获取>外接程序"来 **安装外接程序**。</span><span class="sxs-lookup"><span data-stu-id="49bf6-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="49bf6-130">**可选** 外接程序将自动部署到分配的用户，但他们可以选择将其删除。</span><span class="sxs-lookup"><span data-stu-id="49bf6-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="49bf6-131">管理员能否在外接程序中 (业务) LOB) ？</span><span class="sxs-lookup"><span data-stu-id="49bf6-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="49bf6-132">是的。</span><span class="sxs-lookup"><span data-stu-id="49bf6-132">Yes.</span></span> <span data-ttu-id="49bf6-133">管理员可以上载新的清单文件以支持管理员部署的 LOB 加载项的元数据更改。加载项在应用程序下次启动时Office更新。</span><span class="sxs-lookup"><span data-stu-id="49bf6-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="49bf6-134">Web 应用程序可以随时更改。</span><span class="sxs-lookup"><span data-stu-id="49bf6-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="49bf6-135">有关详细信息，请参阅 [业务线加载项](./manage-addins-in-the-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="49bf6-135">For more information, see [line-of-business add-in](./manage-addins-in-the-admin-center.md).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="49bf6-136">管理员可以关闭加载项吗？</span><span class="sxs-lookup"><span data-stu-id="49bf6-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="49bf6-137">是的。</span><span class="sxs-lookup"><span data-stu-id="49bf6-137">Yes.</span></span> <span data-ttu-id="49bf6-138">管理员可以从 Microsoft 管理中心为所有用户打开或关闭他们部署的外接程序。</span><span class="sxs-lookup"><span data-stu-id="49bf6-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="49bf6-139">有关详细信息，请参阅 [加载项状态](./manage-addins-in-the-admin-center.md#add-in-states)。</span><span class="sxs-lookup"><span data-stu-id="49bf6-139">For more information, see [Add-in states](./manage-addins-in-the-admin-center.md#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="49bf6-140">管理员能否删除或删除加载项？</span><span class="sxs-lookup"><span data-stu-id="49bf6-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="49bf6-141">是的。</span><span class="sxs-lookup"><span data-stu-id="49bf6-141">Yes.</span></span> <span data-ttu-id="49bf6-142">管理员可以从 Microsoft 管理中心删除为所有用户部署的外接程序。</span><span class="sxs-lookup"><span data-stu-id="49bf6-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="49bf6-143">有关详细信息，请参阅 [删除加载项](./manage-addins-in-the-admin-center.md#delete-an-add-in)。</span><span class="sxs-lookup"><span data-stu-id="49bf6-143">For more information, see [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="49bf6-144">管理员能否使用集中部署从 Office 应用商店部署付费加载项？</span><span class="sxs-lookup"><span data-stu-id="49bf6-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="49bf6-145">否。</span><span class="sxs-lookup"><span data-stu-id="49bf6-145">No.</span></span> <span data-ttu-id="49bf6-146">目前，你无法使用集中部署从 Office 应用商店部署付费加载项。</span><span class="sxs-lookup"><span data-stu-id="49bf6-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="49bf6-147">我们建议向 ISV 开发人员联系付费加载项，以请求清单文件或 URL。</span><span class="sxs-lookup"><span data-stu-id="49bf6-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="49bf6-148">然后，租户管理员可以使用集中部署将加载项部署为 LOB 加载项。</span><span class="sxs-lookup"><span data-stu-id="49bf6-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="49bf6-149">我需要哪个管理员角色来管理我的组织的外接程序？</span><span class="sxs-lookup"><span data-stu-id="49bf6-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="49bf6-150">全局管理员是建议的角色，具有对加载项管理生命周期的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="49bf6-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="49bf6-151">其他管理员角色对外接程序部署生命周期的访问权限有限。</span><span class="sxs-lookup"><span data-stu-id="49bf6-151">Other Admin roles have a limited access to add-in deployment lifecycle.</span></span> <span data-ttu-id="49bf6-152">如果你是购买了企业版订阅Microsoft 365，则你是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="49bf6-152">If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="49bf6-153">你的订阅附带了一组管理员角色，你可以将其分配给你组织中其他用户。</span><span class="sxs-lookup"><span data-stu-id="49bf6-153">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="49bf6-154">每个管理员角色映射到常见的业务功能，并授予组织成员在管理中心内执行Microsoft 365任务的权限。</span><span class="sxs-lookup"><span data-stu-id="49bf6-154">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="49bf6-155">有关详细信息，请参阅分配 [管理员角色](../add-users/assign-admin-roles.md?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="49bf6-155">For more information, see [Assign admin roles](../add-users/assign-admin-roles.md?view=o365-worldwide).</span></span> 