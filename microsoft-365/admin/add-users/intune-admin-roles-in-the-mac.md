---
title: 关于 Microsoft 365 管理中心中的 Intune 管理员角色
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: 管理员角色映射到业务功能，并授予在管理中心执行特定任务的权限。 例如，服务管理员可打开 Microsoft 的支持票证。
ms.openlocfilehash: 48bb0f3d1a3a239025017fda261945094a3eda79
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126077"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a><span data-ttu-id="dde82-104">Microsoft 365 管理中心中的 Intune 管理员角色</span><span class="sxs-lookup"><span data-stu-id="dde82-104">Intune admin roles in the Microsoft 365 admin center</span></span>

<span data-ttu-id="dde82-105">你的 Microsoft 365 或 Office 365 订阅附带了一组管理员角色，可使用 Microsoft 365 管理中心将这些角色分配给组织中的用户。</span><span class="sxs-lookup"><span data-stu-id="dde82-105">Your Microsoft 365 or Office 365 subscription comes with a set of admin roles that you can assign to users in your organization using the Microsoft 365 admin center.</span></span> <span data-ttu-id="dde82-106">每个管理员角色都映射到常用的业务功能，并授予这些用户在管理中心执行特定任务的权限。</span><span class="sxs-lookup"><span data-stu-id="dde82-106">Each admin role maps to common business functions and gives people in your organization permissions to do specific tasks in the admin centers.</span></span>

<span data-ttu-id="dde82-107">Microsoft 365 管理中心可用于管理一些 Microsoft Intune 角色。</span><span class="sxs-lookup"><span data-stu-id="dde82-107">The Microsoft 365 admin center lets you manage some Microsoft Intune roles.</span></span> <span data-ttu-id="dde82-108">然而，这些角色是 Intune 管理中心中可用角色的子集。</span><span class="sxs-lookup"><span data-stu-id="dde82-108">However, these roles are a subset of the roles available in the Intune admin center.</span></span> <span data-ttu-id="dde82-109">是否在查找 Microsoft Intune 的详细角色说明？</span><span class="sxs-lookup"><span data-stu-id="dde82-109">Looking for the detailed role descriptions for Microsoft Intune?</span></span> <span data-ttu-id="dde82-110">查看 [Microsoft Intune 中的基于角色的访问控制 (RBAC)](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)。</span><span class="sxs-lookup"><span data-stu-id="dde82-110">Check out [Role-based access control (RBAC) with Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).</span></span>

<span data-ttu-id="dde82-111">有关在 Microsoft 365 管理中心分配角色的详细信息，请参阅[分配管理员角色](assign-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="dde82-111">For more information on assigning roles in the Microsoft 365 admin center, see [Assign admin roles](assign-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="dde82-112">在 Microsoft 365 管理中心，你可以转到“**角色**”，然后选择任何角色以打开其详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="dde82-112">In the Microsoft 365 admin center, you can go to **Roles**, and then select any role to open its detail pane.</span></span> <span data-ttu-id="dde82-113">选择“**权限**”选项卡，以查看分配有该角色的管理员有权执行的操作的详细列表。</span><span class="sxs-lookup"><span data-stu-id="dde82-113">Select the **Permissions** tab to view the detailed list of what admins assigned that role have permissions to do.</span></span> <span data-ttu-id="dde82-114">选择“**已分配**”或“**已分配管理员**”选项卡，以向角色添加用户。</span><span class="sxs-lookup"><span data-stu-id="dde82-114">Select the **Assigned** or **Assigned admins** tab to add users to roles.</span></span>

::: moniker-end

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a><span data-ttu-id="dde82-115">Microsoft 365 管理中心提供的 Microsoft Intune 角色</span><span class="sxs-lookup"><span data-stu-id="dde82-115">Microsoft Intune Roles available in the Microsoft 365 admin center</span></span>

|<span data-ttu-id="dde82-116">管理员角色</span><span class="sxs-lookup"><span data-stu-id="dde82-116">Admin role</span></span>     |<span data-ttu-id="dde82-117">应该为谁分配此角色？</span><span class="sxs-lookup"><span data-stu-id="dde82-117">Who should be assigned this role?</span></span>  |
|---------|---------|
|<span data-ttu-id="dde82-118">应用程序管理员</span><span class="sxs-lookup"><span data-stu-id="dde82-118">Application manager</span></span>     |   <span data-ttu-id="dde82-119">将应用程序管理员角色分配给管理移动应用的应用程序生命周期、配置策略管理的应用以及查看设备信息和配置文件的用户。</span><span class="sxs-lookup"><span data-stu-id="dde82-119">Assign the Application manager role to users who mangage the application lifecycle for mobile apps, configures policy-managed apps and views device info and configuration profiles.</span></span>  |
|<span data-ttu-id="dde82-120">技术支持操作员</span><span class="sxs-lookup"><span data-stu-id="dde82-120">Help desk operator</span></span>     |   <span data-ttu-id="dde82-121">将技术支持操作员角色分配给向用户和设备分配应用程序和策略的用户。</span><span class="sxs-lookup"><span data-stu-id="dde82-121">Assign the help desk operator role to users who assign apps and policies to users and devices.</span></span> |
|<span data-ttu-id="dde82-122">Intune 角色管理员</span><span class="sxs-lookup"><span data-stu-id="dde82-122">Intune role administrator</span></span>    |   <span data-ttu-id="dde82-123">将 Intune 角色管理员分配给可以向其他管理员分配 Intune 权限，并且可以管理自定义和内置 Intune 角色的用户。</span><span class="sxs-lookup"><span data-stu-id="dde82-123">Assign the Intune role administrator to users who can assign Intune permissions to other admins and can manage custom and built in Intune roles.</span></span>   |
|<span data-ttu-id="dde82-124">策略和个人资料管理员</span><span class="sxs-lookup"><span data-stu-id="dde82-124">Policy and profile manager</span></span>     |   <span data-ttu-id="dde82-125">将策略和个人资料管理员角色分配给用户管理合规性策略、配置文件和 Apple 注册的用户。</span><span class="sxs-lookup"><span data-stu-id="dde82-125">Assign the policy and profile manager role to users manage compliance policy, configuration profiles and Apple enrollment.</span></span>   |
|<span data-ttu-id="dde82-126">只读操作员</span><span class="sxs-lookup"><span data-stu-id="dde82-126">Read only operator</span></span>     |   <span data-ttu-id="dde82-127">将只读操作员角色分配给仅可查看用户、设备、注册详细信息和配置的用户。</span><span class="sxs-lookup"><span data-stu-id="dde82-127">Assign the read only operator role to users who can only view users, devices, enrollment details and configurations.</span></span>   |
|<span data-ttu-id="dde82-128">学校管理员</span><span class="sxs-lookup"><span data-stu-id="dde82-128">School administrator</span></span>     |   <span data-ttu-id="dde82-129">将学校管理员角色分配给用户，以获取在 Intune 教育版中管理 Windows 10 和 iOS 设备、应用和配置的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="dde82-129">Assign the school administrator role to users for full access to manage Windows 10 and iOS devices, apps and configurations in Intune for Education.</span></span>   |

## <a name="delegated-administration-for-microsoft-partners"></a><span data-ttu-id="dde82-130">Microsoft 合作伙伴的委派管理</span><span class="sxs-lookup"><span data-stu-id="dde82-130">Delegated administration for Microsoft Partners</span></span>

<span data-ttu-id="dde82-131">如果你正与 Microsoft 合作伙伴协作，可向其分配管理员角色。</span><span class="sxs-lookup"><span data-stu-id="dde82-131">If you're working with a Microsoft partner, you can assign them admin roles.</span></span> <span data-ttu-id="dde82-132">他们又可以为你的公司（或其公司）内的用户分配管理员角色。</span><span class="sxs-lookup"><span data-stu-id="dde82-132">They, in turn, can assign users in your company - or their company - admin roles.</span></span> <span data-ttu-id="dde82-133">你可能希望他们执行此操作，例如，如果是由对方为你设置和管理联机组织的情况。</span><span class="sxs-lookup"><span data-stu-id="dde82-133">You might want them to do this, for example, if they are setting up and managing your online organization for you.</span></span>
  
<span data-ttu-id="dde82-134">合作伙伴可以分配以下角色：</span><span class="sxs-lookup"><span data-stu-id="dde82-134">A partner can assign these roles:</span></span>
  
- <span data-ttu-id="dde82-135">完全管理，其权限等同于全局管理员，但通过合作伙伴中心管理多重身份验证除外。</span><span class="sxs-lookup"><span data-stu-id="dde82-135">Full administration, which has privileges equivalent to a global admin, with the exception of managing multi-factor authentication through the Partner Center.</span></span>

- <span data-ttu-id="dde82-136">有限管理，其权限等同于支持管理员。</span><span class="sxs-lookup"><span data-stu-id="dde82-136">Limited administration, which has privileges equivalent to a helpdesk admin.</span></span>

<span data-ttu-id="dde82-137">在合作伙伴将这些角色分配给用户之前，必须先将合作伙伴作为委派管理员添加到你的帐户中。</span><span class="sxs-lookup"><span data-stu-id="dde82-137">Before the partner can assign these roles to users, you must add the partner as a delegated admin to your account.</span></span> <span data-ttu-id="dde82-138">此过程由授权合作伙伴发起。</span><span class="sxs-lookup"><span data-stu-id="dde82-138">This process is initiated by an authorized partner.</span></span> <span data-ttu-id="dde82-139">合作伙伴将向你发送一封电子邮件，询问你是否要授予其作为委派管理员的权限。有关说明，请参阅[授权或删除合作伙伴关系](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)。</span><span class="sxs-lookup"><span data-stu-id="dde82-139">The partner sends you an email to ask you if you want to give them permission to act as a delegated admin. For instructions, see [Authorize or remove partner relationships](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="dde82-140">相关文章</span><span class="sxs-lookup"><span data-stu-id="dde82-140">Related articles</span></span>

[<span data-ttu-id="dde82-141">关于 Microsoft 365 管理员角色</span><span class="sxs-lookup"><span data-stu-id="dde82-141">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

[<span data-ttu-id="dde82-142">分配管理员角色</span><span class="sxs-lookup"><span data-stu-id="dde82-142">Assign admin roles</span></span>](assign-admin-roles.md)

[<span data-ttu-id="dde82-143">Microsoft 365 管理中心中的活动报告</span><span class="sxs-lookup"><span data-stu-id="dde82-143">Activity reports in the Microsoft 365 admin center</span></span>](../activity-reports/activity-reports.md)