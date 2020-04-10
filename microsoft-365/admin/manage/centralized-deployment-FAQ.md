---
title: 集中部署常见问题
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
description: 查看有关从 Microsoft 365 管理中心进行集中部署的常见问题解答。
ms.openlocfilehash: 39df2ec5a1671f800572bc845581bdbe2716d209
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43209660"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="4aec1-103">集中部署常见问题</span><span class="sxs-lookup"><span data-stu-id="4aec1-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="4aec1-104">通过集中部署，Office 365 管理员可以将 Office 外接程序（Word、Excel、PowerPoint 和 Outlook）部署到组织内的用户和组，前提是组织满足本文中所述的使用集中部署的所有要求。</span><span class="sxs-lookup"><span data-stu-id="4aec1-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="4aec1-105">如何知道我的组织是否设置了集中式部署？</span><span class="sxs-lookup"><span data-stu-id="4aec1-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="4aec1-106">集中部署加载项需要用户使用 Office 365 专业增强版（并使用组织的登录凭据登录到 Office）并拥有 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="4aec1-106">Centralized deployment of add-ins requires that users are using Office 365 ProPlus (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="4aec1-107">你的订阅目录必须在 Azure Active Directory 中或联合到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="4aec1-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="4aec1-108">仅联机邮箱支持集中部署。</span><span class="sxs-lookup"><span data-stu-id="4aec1-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="4aec1-109">它不支持部署到本地 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="4aec1-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>
 
<span data-ttu-id="4aec1-110">您可以使用[Office 365 集中部署兼容性检查器](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker) 来确定您的订阅是否符合条件。</span><span class="sxs-lookup"><span data-stu-id="4aec1-110">You can use the [Office 365 Centralized Deployment Compatibility Checker](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="4aec1-111">如何将加载项用户分配与集中部署进行定位？</span><span class="sxs-lookup"><span data-stu-id="4aec1-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="4aec1-112">集中部署支持对租户中的单个用户、组和每个人的工作分配。</span><span class="sxs-lookup"><span data-stu-id="4aec1-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="4aec1-113">集中部署可用于顶级组或没有父组的组中的用户，但不能用于具有父组的嵌套组或组中的用户。</span><span class="sxs-lookup"><span data-stu-id="4aec1-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="4aec1-114">集中部署也是大多数 Azure Active Directory 组（包括 Office 365 组、通讯组列表和安全组）的一部分。</span><span class="sxs-lookup"><span data-stu-id="4aec1-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="4aec1-115">最好使用组分配（而不是单个用户分配）来简化管理。</span><span class="sxs-lookup"><span data-stu-id="4aec1-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="4aec1-116">有关更多详细信息，请参阅[User And Group 赋值](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments)。</span><span class="sxs-lookup"><span data-stu-id="4aec1-116">For more details, see [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="4aec1-117">为所有用户显示外接程序需要多长时间？</span><span class="sxs-lookup"><span data-stu-id="4aec1-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="4aec1-118">加载项最长可能需要24小时才能显示给所有用户。</span><span class="sxs-lookup"><span data-stu-id="4aec1-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="4aec1-119">加载项更新、打开或关闭更改或外接程序的更改可能需要相同的时间量。</span><span class="sxs-lookup"><span data-stu-id="4aec1-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="4aec1-120">作为管理员，如何管理用户对我的组织的外接程序的访问？</span><span class="sxs-lookup"><span data-stu-id="4aec1-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="4aec1-121">为了方便地将外接程序部署到用户、组或整个组织，我们建议管理员使用集中部署。</span><span class="sxs-lookup"><span data-stu-id="4aec1-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="4aec1-122">有关管理用户访问的详细信息，请参阅</span><span class="sxs-lookup"><span data-stu-id="4aec1-122">For more information about managing user access, see</span></span> </br><span data-ttu-id="4aec1-123">[通过在所有客户端（Outlook 除外）中关闭 Office 应用商店来阻止外接程序下载](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)</span><span class="sxs-lookup"><span data-stu-id="4aec1-123">[Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) and</span></span> </br><span data-ttu-id="4aec1-124">[指定可以安装和管理适用于 Outlook 的外接程序的管理员和用户](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN)。</span><span class="sxs-lookup"><span data-stu-id="4aec1-124">[Specify the administrators and users who can install and manage add-ins for Outlook](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN).</span></span>

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="4aec1-125">集中部署是否为管理员提供了选择 Outlook 外接程序的部署方法的灵活性？</span><span class="sxs-lookup"><span data-stu-id="4aec1-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="4aec1-126">正确。</span><span class="sxs-lookup"><span data-stu-id="4aec1-126">Yes.</span></span> <span data-ttu-id="4aec1-127">集中部署为管理员提供了在加载项部署过程中选择 Outlook 外接程序的三种部署方法之一的灵活性：</span><span class="sxs-lookup"><span data-stu-id="4aec1-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="4aec1-128">**固定（默认值）**  外接将自动部署到分配的用户，并且无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="4aec1-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="4aec1-129">**可用**用户可以通过选择 "家庭 > 获取更多加载项 > 管理员管理" 来在 Outlook 中安装外接程序。</span><span class="sxs-lookup"><span data-stu-id="4aec1-129">**Available** Users can install the add-in in Outlook by choosing Home > Get More add-ins > Admin-managed.</span></span>   
 
<span data-ttu-id="4aec1-130">**可选**加载项将自动部署到分配的用户，但可以选择将其删除。</span><span class="sxs-lookup"><span data-stu-id="4aec1-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="4aec1-131">管理员是否可以更新业务线（LOB）加载项？</span><span class="sxs-lookup"><span data-stu-id="4aec1-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="4aec1-132">正确。</span><span class="sxs-lookup"><span data-stu-id="4aec1-132">Yes.</span></span> <span data-ttu-id="4aec1-133">管理员可以上传新的清单文件，以支持管理员部署的 LOB 外接程序的元数据更改。下次 Office 应用程序启动时，外接程序会更新。</span><span class="sxs-lookup"><span data-stu-id="4aec1-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="4aec1-134">Web 应用程序可以随时更改。</span><span class="sxs-lookup"><span data-stu-id="4aec1-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="4aec1-135">有关详细信息，请参阅[业务线外接程序](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="4aec1-135">For more information, see [line-of-business add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="4aec1-136">管理员是否可以关闭外接程序？</span><span class="sxs-lookup"><span data-stu-id="4aec1-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="4aec1-137">正确。</span><span class="sxs-lookup"><span data-stu-id="4aec1-137">Yes.</span></span> <span data-ttu-id="4aec1-138">管理员可以打开或关闭他们为 Microsoft 管理中心中的所有用户部署的外接程序。</span><span class="sxs-lookup"><span data-stu-id="4aec1-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="4aec1-139">有关详细信息，请参阅[外接程序状态](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states)。</span><span class="sxs-lookup"><span data-stu-id="4aec1-139">For more information, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="4aec1-140">是否可以管理员删除或删除加载项？</span><span class="sxs-lookup"><span data-stu-id="4aec1-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="4aec1-141">正确。</span><span class="sxs-lookup"><span data-stu-id="4aec1-141">Yes.</span></span> <span data-ttu-id="4aec1-142">管理员可以从 Microsoft 管理中心删除为所有用户部署的外接程序。</span><span class="sxs-lookup"><span data-stu-id="4aec1-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="4aec1-143">有关详细信息，请参阅[删除外接程序](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in)。</span><span class="sxs-lookup"><span data-stu-id="4aec1-143">For more information, see [Delete the add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="4aec1-144">管理员是否可以使用集中部署从 Office 应用商店部署付费的外接程序？</span><span class="sxs-lookup"><span data-stu-id="4aec1-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="4aec1-145">不是。</span><span class="sxs-lookup"><span data-stu-id="4aec1-145">No.</span></span> <span data-ttu-id="4aec1-146">此时无法使用集中部署从 Office 应用商店中部署付费的外接程序。</span><span class="sxs-lookup"><span data-stu-id="4aec1-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="4aec1-147">建议与付费外接程序的 ISV 开发人员联系，以请求清单文件或 URL。</span><span class="sxs-lookup"><span data-stu-id="4aec1-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="4aec1-148">然后，租户管理员可以使用集中部署将加载项部署为 LOB 加载项。</span><span class="sxs-lookup"><span data-stu-id="4aec1-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="4aec1-149">我需要哪些管理员角色来管理组织的外接程序？</span><span class="sxs-lookup"><span data-stu-id="4aec1-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="4aec1-150">您必须具有全局管理员角色才能管理外接程序。如果你是购买 Microsoft 365 for business 订阅的人员，则表示你是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="4aec1-150">You must have the Global admin role to manage add-ins. If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="4aec1-151">您的订阅附带有一组管理员角色，您可以将其分配给组织中的其他用户。</span><span class="sxs-lookup"><span data-stu-id="4aec1-151">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="4aec1-152">每个管理员角色都映射到常用业务功能，并向组织中的人员授予在 Microsoft 365 管理中心中执行特定任务的权限。</span><span class="sxs-lookup"><span data-stu-id="4aec1-152">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="4aec1-153">有关详细信息，请参阅[分配管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="4aec1-153">For more information, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>  