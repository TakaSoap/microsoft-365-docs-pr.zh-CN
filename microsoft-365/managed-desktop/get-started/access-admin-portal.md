---
title: 访问管理门户
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
description: 如何查找和使用管理门户，包括控制对管理门户的访问。
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: c2a5b7f837d6c43369301820019732ca3aef83bf
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053843"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="ed9c1-104">访问管理门户</span><span class="sxs-lookup"><span data-stu-id="ed9c1-104">Access the admin portal</span></span>

<span data-ttu-id="ed9c1-105">Microsoft 托管桌面服务的网关是[Microsoft Endpoint Manager。](https://endpoint.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="ed9c1-105">Your gateway to the Microsoft Managed Desktop service is [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).</span></span> <span data-ttu-id="ed9c1-106">如果你不熟悉此门户的设备管理功能，请参阅 [Microsoft Endpoint Manager 文档](https://docs.microsoft.com/mem/)。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-106">If you are unfamiliar with the capabilities of this portal for device management, see the [Microsoft Endpoint Manager documentation](https://docs.microsoft.com/mem/).</span></span>

> [!NOTE]
> <span data-ttu-id="ed9c1-107">在 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 中，支持以下浏览器：</span><span class="sxs-lookup"><span data-stu-id="ed9c1-107">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) the following browsers are supported:</span></span>
> - <span data-ttu-id="ed9c1-108">Microsoft Edge (最新版本) </span><span class="sxs-lookup"><span data-stu-id="ed9c1-108">Microsoft Edge (latest version)</span></span>
> - <span data-ttu-id="ed9c1-109">Microsoft Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="ed9c1-109">Microsoft Internet Explorer 11</span></span>
> - <span data-ttu-id="ed9c1-110">Safari (最新版本，仅 Mac) </span><span class="sxs-lookup"><span data-stu-id="ed9c1-110">Safari (latest version, Mac only)</span></span>
> - <span data-ttu-id="ed9c1-111">Chrome (最新版本) </span><span class="sxs-lookup"><span data-stu-id="ed9c1-111">Chrome (latest version)</span></span>
> - <span data-ttu-id="ed9c1-112">Firefox (最新版本) </span><span class="sxs-lookup"><span data-stu-id="ed9c1-112">Firefox (latest version)</span></span>

<span data-ttu-id="ed9c1-113">管理帐户需要特定权限才能访问 Azure 门户或 Microsoft Endpoint Manager 中的 Microsoft 托管桌面管理功能。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-113">Your administrative account needs specific permissions in order to access the Microsoft Managed Desktop administrative features in either Azure portal or Microsoft Endpoint Manager.</span></span> <span data-ttu-id="ed9c1-114">您可以使用基于角色的访问控制或 RBAC (管理对组织中这些功能的管理员) 。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-114">You can manage admin access to these features within your organization by using Role-based Access Control (RBAC).</span></span> <span data-ttu-id="ed9c1-115">多个 Azure Active Directory (Azure AD) 管理员角色和内置自定义角色可用于为 Microsoft 托管桌面管理门户中的不同功能提供更精细的控制。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-115">Several Azure Active Directory (Azure AD) administrator roles and built-in custom roles are available to provide more granular control to different features within the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="ed9c1-116">有关 Azure Active Directory 角色详细信息，请参阅 [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-116">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="ed9c1-117">与应用于各种 Microsoft 产品和服务的 Azure AD 管理员角色不同，自定义角色特定于 Microsoft 托管桌面，并且仅保证访问此服务的管理员功能。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-117">Unlike Azure AD administrator roles that apply to various Microsoft products and services, custom roles are specific to Microsoft Managed Desktop and will only guarantee access to the Admin features for this service.</span></span> <span data-ttu-id="ed9c1-118">管理员可以单独或结合 Azure AD 管理员角色向用户分配自定义角色，以向现有管理员帐户添加 Microsoft 托管桌面权限。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-118">Admins can assign custom roles to users individually or in combination with Azure AD administrator roles to add Microsoft Managed Desktop permissions to existing admin accounts.</span></span>

<span data-ttu-id="ed9c1-119">可以分配以下每个角色以提供不同级别的访问：</span><span class="sxs-lookup"><span data-stu-id="ed9c1-119">Each of the roles below can be assigned to provide different levels of access:</span></span>

|<span data-ttu-id="ed9c1-120">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="ed9c1-120">Azure AD role</span></span>  |<span data-ttu-id="ed9c1-121">Microsoft 托管桌面权限</span><span class="sxs-lookup"><span data-stu-id="ed9c1-121">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="ed9c1-122">全局管理员</span><span class="sxs-lookup"><span data-stu-id="ed9c1-122">Global Administrator</span></span>     | <span data-ttu-id="ed9c1-123">具有此角色的 **管理员将拥有** 对 Microsoft 托管桌面管理门户中所有功能的读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-123">Admins with this role will have **read and write permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="ed9c1-124">全局读取者</span><span class="sxs-lookup"><span data-stu-id="ed9c1-124">Global Reader</span></span>     | <span data-ttu-id="ed9c1-125">具有此角色的 **管理员将具有** 对 Microsoft 托管桌面管理门户中所有功能的只读权限。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-125">Admins with this role will have **read-only permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="ed9c1-126">Intune 服务管理员</span><span class="sxs-lookup"><span data-stu-id="ed9c1-126">Intune Service Administrator</span></span>     |  <span data-ttu-id="ed9c1-127">具有此角色的管理员将拥有对 Microsoft 托管桌面管理门户中与安全不相关的功能的读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-127">Admins with this role will have **read and write permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="ed9c1-128">服务支持管理员</span><span class="sxs-lookup"><span data-stu-id="ed9c1-128">Service Support Administrator</span></span>     | <span data-ttu-id="ed9c1-129">具有此角色的管理员将具有对与安全不相关的功能的只读权限，并且具有在Microsoft 托管桌面管理门户中管理支持请求的写入权限。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-129">Admins with this role will have **read-only permissions to features not related to security** and **write permissions to manage support requests** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="ed9c1-130">安全管理员</span><span class="sxs-lookup"><span data-stu-id="ed9c1-130">Security Admin</span></span> | <span data-ttu-id="ed9c1-131">具有此角色的管理员将拥有针对所有功能的只读权限，并拥有在管理门户中对 Microsoft 托管桌面中与安全相关的功能的写入权限。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-131">Admins with this role will have **read-only permissions to all features** and **write permissions for security related features** in Microsoft Managed Desktop in the Admin portal.</span></span> |
|<span data-ttu-id="ed9c1-132">安全读取者</span><span class="sxs-lookup"><span data-stu-id="ed9c1-132">Security Reader</span></span> |<span data-ttu-id="ed9c1-133">具有此角色的 **管理员将具有** 对 Microsoft 托管桌面管理门户中所有功能的只读权限。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-133">Admins with this role will have **read-only permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="ed9c1-134">只有全局管理员角色才具有在 Microsoft 托管桌面中注册组织所需的权限。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-134">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="ed9c1-135">请注意，Azure Active Directory 角色将为用户帐户提供跨各种 Microsoft 服务的权限。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-135">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="ed9c1-136">完成 Microsoft 托管桌面的注册后，应始终使用具有完成其他任务所需的最低权限的角色。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-136">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

 
|<span data-ttu-id="ed9c1-137">自定义角色</span><span class="sxs-lookup"><span data-stu-id="ed9c1-137">Custom role</span></span>  |<span data-ttu-id="ed9c1-138">Microsoft 托管桌面权限</span><span class="sxs-lookup"><span data-stu-id="ed9c1-138">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="ed9c1-139">Microsoft 托管桌面服务管理员</span><span class="sxs-lookup"><span data-stu-id="ed9c1-139">Microsoft Managed Desktop Service Administrator</span></span>  | <span data-ttu-id="ed9c1-140">分配给用户时，此角色授予管理员对 Microsoft托管桌面管理门户中与安全不相关的功能的读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-140">When assigned to a user, this role gives the admin **read and write permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span>  |
|<span data-ttu-id="ed9c1-141">Microsoft Managed Desktop Service Reader</span><span class="sxs-lookup"><span data-stu-id="ed9c1-141">Microsoft Managed Desktop Service Reader</span></span> | <span data-ttu-id="ed9c1-142">分配给用户时，此角色授予管理员对 Microsoft托管桌面管理门户中与安全不相关的功能的只读权限。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-142">When assigned to a user, this role gives the admin **read-only permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span> |
|<span data-ttu-id="ed9c1-143">Microsoft 托管桌面安全管理器</span><span class="sxs-lookup"><span data-stu-id="ed9c1-143">Microsoft Managed Desktop Security Manager</span></span> |<span data-ttu-id="ed9c1-144">分配给用户时，此角色仅授予管理员对 Microsoft托管桌面管理门户中与安全相关的功能的读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-144">When assigned to a user, this role gives that admin **read and write permissions only for security related features** in the Microsoft Managed Desktop Admin portal.</span></span>   |

> [!NOTE]
> <span data-ttu-id="ed9c1-145">安全功能包括与安全相关的通信、安全联系人的管理、安全相关支持请求的管理以及安全相关报告的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-145">Security features include security-related communications, management of security contacts, management of security-related support requests, and access to security related reports.</span></span> 

## <a name="assigning-roles-to-administrators"></a><span data-ttu-id="ed9c1-146">向管理员分配角色</span><span class="sxs-lookup"><span data-stu-id="ed9c1-146">Assigning roles to administrators</span></span>

<span data-ttu-id="ed9c1-147">如果需要有关分配 Azure Active Directory 角色的帮助，请参阅 [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-147">If you need help with assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

<span data-ttu-id="ed9c1-148">为了便于管理内置角色，每个自定义角色都有一个安全组 (例如，"新式工作区角色 – 安全管理器") 。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-148">To make it easy to manage built-in roles, there is a security group for each custom role (for example, “Modern Workplace Roles – Security Manager”).</span></span> <span data-ttu-id="ed9c1-149">若要将用户分配到其中一个安全组，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ed9c1-149">To assign users to one of the security groups, follow these steps:</span></span>
1.  <span data-ttu-id="ed9c1-150">转到 Microsoft Endpoint Manager 门户。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-150">Go the Microsoft Endpoint Manager portal.</span></span>
2.  <span data-ttu-id="ed9c1-151">选择 **左侧** 的组。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-151">Select **Groups** on the left side.</span></span>
3.  <span data-ttu-id="ed9c1-152">搜索 **新式工作区角色**，然后选择与要分配的角色关联的组。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-152">Search for **Modern Workplace Roles**, and then select the group associated with the role you want to assign.</span></span> 
4.  <span data-ttu-id="ed9c1-153">选择 **左侧** 的成员，然后选择 **命令栏上的 +** 添加成员。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-153">Select **Members** on the left side, and then select **+ Add members** on the command bar.</span></span>
5.  <span data-ttu-id="ed9c1-154">输入要添加的人的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-154">Enter the email of the person being added.</span></span> <span data-ttu-id="ed9c1-155">如果他们是来宾，则必须先邀请他们，然后才能分配组。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-155">If they are a guest, you must invite them before you can assign the group.</span></span>
6.  <span data-ttu-id="ed9c1-156">选择 **底部的** "选择"。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-156">Select **Select** at the bottom.</span></span>

> [!NOTE]
> <span data-ttu-id="ed9c1-157">当前不支持嵌套角色分配组。</span><span class="sxs-lookup"><span data-stu-id="ed9c1-157">Nesting security groups for role assignment is not currently supported.</span></span> 
