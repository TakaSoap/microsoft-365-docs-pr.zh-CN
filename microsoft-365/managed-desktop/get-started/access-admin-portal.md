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
ms.openlocfilehash: 7293c8ced43332f84ced56908ea5203ba867e600
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925900"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="9066b-104">访问管理门户</span><span class="sxs-lookup"><span data-stu-id="9066b-104">Access the admin portal</span></span>

<span data-ttu-id="9066b-105">Microsoft 托管桌面服务的网关是 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="9066b-105">Your gateway to the Microsoft Managed Desktop service is [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).</span></span> <span data-ttu-id="9066b-106">如果你不熟悉此门户的设备管理功能，请参阅 [Microsoft Endpoint Manager 文档](/mem/)。</span><span class="sxs-lookup"><span data-stu-id="9066b-106">If you are unfamiliar with the capabilities of this portal for device management, see the [Microsoft Endpoint Manager documentation](/mem/).</span></span>

> [!NOTE]
> <span data-ttu-id="9066b-107">在 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 中，支持以下浏览器：</span><span class="sxs-lookup"><span data-stu-id="9066b-107">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) the following browsers are supported:</span></span>
> - <span data-ttu-id="9066b-108">Microsoft Edge (最新版本) </span><span class="sxs-lookup"><span data-stu-id="9066b-108">Microsoft Edge (latest version)</span></span>
> - <span data-ttu-id="9066b-109">Microsoft Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="9066b-109">Microsoft Internet Explorer 11</span></span>
> - <span data-ttu-id="9066b-110">Safari (最新版本，仅 Mac) </span><span class="sxs-lookup"><span data-stu-id="9066b-110">Safari (latest version, Mac only)</span></span>
> - <span data-ttu-id="9066b-111">Chrome (最新版本) </span><span class="sxs-lookup"><span data-stu-id="9066b-111">Chrome (latest version)</span></span>
> - <span data-ttu-id="9066b-112">Firefox (最新版本) </span><span class="sxs-lookup"><span data-stu-id="9066b-112">Firefox (latest version)</span></span>

<span data-ttu-id="9066b-113">管理帐户将需要特定权限才能访问 Microsoft Endpoint Manager 中的 Microsoft 托管桌面管理功能。</span><span class="sxs-lookup"><span data-stu-id="9066b-113">Your administrative account will need specific permissions in order to access the Microsoft Managed Desktop administrative features in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="9066b-114">可以使用基于角色的访问控制在组织中管理对这些功能的管理员访问权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-114">You can manage admin access to these features within your organization by using role-based access control.</span></span> <span data-ttu-id="9066b-115">可以使用多个 Azure Active Directory (Azure AD) 管理员角色和内置 Microsoft 托管桌面角色，以便更精细地控制 Microsoft 托管桌面管理门户中的不同功能。</span><span class="sxs-lookup"><span data-stu-id="9066b-115">Several Azure Active Directory (Azure AD) administrator roles and built-in Microsoft Managed Desktop roles are available to provide more granular control to different features within the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="9066b-116">有关 Azure Active Directory 角色详细信息，请参阅 [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)中的管理员角色权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-116">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="9066b-117">与应用于各种 Microsoft 产品和服务的 Azure AD 管理员角色不同，内置角色特定于 Microsoft 托管桌面，并且仅保证访问此服务的管理员功能。</span><span class="sxs-lookup"><span data-stu-id="9066b-117">Unlike Azure AD administrator roles that apply to various Microsoft products and services, the built-in roles are specific to Microsoft Managed Desktop and will only guarantee access to the Admin features for this service.</span></span> <span data-ttu-id="9066b-118">管理员可以单独或结合 Azure AD 管理员角色向用户分配内置角色，以向现有管理员帐户添加 Microsoft 托管桌面权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-118">Admins can assign built-in roles to users individually or in combination with Azure AD administrator roles to add Microsoft Managed Desktop permissions to existing admin accounts.</span></span>

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a><span data-ttu-id="9066b-119">具有 Microsoft 托管桌面访问权限的 Azure Active Directory 角色</span><span class="sxs-lookup"><span data-stu-id="9066b-119">Azure Active Directory roles with Microsoft Managed Desktop access</span></span>

|<span data-ttu-id="9066b-120">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="9066b-120">Azure AD role</span></span>  |<span data-ttu-id="9066b-121">Microsoft 托管桌面权限</span><span class="sxs-lookup"><span data-stu-id="9066b-121">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="9066b-122">全局管理员</span><span class="sxs-lookup"><span data-stu-id="9066b-122">Global Administrator</span></span>     | <span data-ttu-id="9066b-123">具有此角色的管理员将拥有对 Microsoft 托管桌面管理门户中所有 **功能的** 读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-123">Admins with this role will have **read and write permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="9066b-124">全局读取者</span><span class="sxs-lookup"><span data-stu-id="9066b-124">Global Reader</span></span>     | <span data-ttu-id="9066b-125">具有此角色的 **管理员将拥有** 对 Microsoft 托管桌面管理门户中所有功能的只读权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-125">Admins with this role will have **read-only permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="9066b-126">Intune 服务管理员</span><span class="sxs-lookup"><span data-stu-id="9066b-126">Intune Service Administrator</span></span>     |  <span data-ttu-id="9066b-127">具有此角色的 **管理员将拥有** 对 Microsoft 托管桌面管理门户中与安全不相关的功能的读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-127">Admins with this role will have **read and write permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="9066b-128">服务支持管理员</span><span class="sxs-lookup"><span data-stu-id="9066b-128">Service Support Administrator</span></span>     | <span data-ttu-id="9066b-129">具有此角色的 **管理员将具有** 对与安全不相关的功能的只读权限，并且具有在Microsoft 托管桌面管理门户中管理支持请求的写入权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-129">Admins with this role will have **read-only permissions to features not related to security** and **write permissions to manage support requests** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="9066b-130">安全管理员</span><span class="sxs-lookup"><span data-stu-id="9066b-130">Security Admin</span></span> | <span data-ttu-id="9066b-131">具有此角色的 **管理员将拥有** 针对所有功能的只读权限，以及管理门户中 Microsoft 托管桌面中与安全相关的功能的写入权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-131">Admins with this role will have **read-only permissions to all features** and **write permissions for security related features** in Microsoft Managed Desktop in the Admin portal.</span></span> |
|<span data-ttu-id="9066b-132">安全读取者</span><span class="sxs-lookup"><span data-stu-id="9066b-132">Security Reader</span></span> |<span data-ttu-id="9066b-133">具有此角色的 **管理员将拥有** 对 Microsoft 托管桌面管理门户中所有功能的只读权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-133">Admins with this role will have **read-only permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>|

<span data-ttu-id="9066b-134">如果需要有关分配 Azure Active Directory 角色的帮助，请参阅 [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)中的管理员角色权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-134">If you need help with assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9066b-135">只有全局管理员角色才具有在 Microsoft 托管桌面 *中注册组织* 所需的权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-135">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="9066b-136">请注意，Azure Active Directory 角色将为用户帐户提供跨各种 Microsoft 服务的权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-136">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="9066b-137">完成 Microsoft 托管桌面的注册后，应始终使用具有完成其他任务所需的最小特权的角色。</span><span class="sxs-lookup"><span data-stu-id="9066b-137">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a><span data-ttu-id="9066b-138">Microsoft 托管桌面提供的内置角色</span><span class="sxs-lookup"><span data-stu-id="9066b-138">Built-in roles provided by Microsoft Managed Desktop</span></span>


|<span data-ttu-id="9066b-139">内置角色</span><span class="sxs-lookup"><span data-stu-id="9066b-139">Built-in role</span></span>  |<span data-ttu-id="9066b-140">Microsoft 托管桌面权限</span><span class="sxs-lookup"><span data-stu-id="9066b-140">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="9066b-141">Microsoft 托管桌面服务管理员</span><span class="sxs-lookup"><span data-stu-id="9066b-141">Microsoft Managed Desktop Service Administrator</span></span>  | <span data-ttu-id="9066b-142">分配给用户时，此角色授予管理员对 Microsoft托管桌面管理门户中与安全不相关的功能的读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-142">When assigned to a user, this role gives the admin **read and write permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span>  |
|<span data-ttu-id="9066b-143">Microsoft Managed Desktop Service Reader</span><span class="sxs-lookup"><span data-stu-id="9066b-143">Microsoft Managed Desktop Service Reader</span></span> | <span data-ttu-id="9066b-144">分配给用户时，此角色授予管理员对 Microsoft托管桌面管理门户中与安全不相关的功能的只读权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-144">When assigned to a user, this role gives the admin **read-only permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span> |
|<span data-ttu-id="9066b-145">Microsoft 托管桌面安全管理器</span><span class="sxs-lookup"><span data-stu-id="9066b-145">Microsoft Managed Desktop Security Manager</span></span> |<span data-ttu-id="9066b-146">分配给用户时，此角色仅向管理员授予对 Microsoft 托管桌面管理门户中与安全相关的 **功能的** 读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-146">When assigned to a user, this role gives that admin **read and write permissions only for security related features** in the Microsoft Managed Desktop Admin portal.</span></span>   |

> [!NOTE]
> <span data-ttu-id="9066b-147">安全功能包括与安全相关的通信、安全联系人的管理、安全相关支持请求的管理以及安全相关报告的访问权限。</span><span class="sxs-lookup"><span data-stu-id="9066b-147">Security features include security-related communications, management of security contacts, management of security-related support requests, and access to security related reports.</span></span> 

### <a name="assigning-built-in-roles-to-user"></a><span data-ttu-id="9066b-148">向用户分配内置角色</span><span class="sxs-lookup"><span data-stu-id="9066b-148">Assigning built-in roles to user</span></span>

<span data-ttu-id="9066b-149">为了轻松管理内置角色，每个自定义角色都有一个安全组，名称为"新式工作区角色 _-_ 角色名称" (例如，"新式工作区角色 – 安全管理器") 。</span><span class="sxs-lookup"><span data-stu-id="9066b-149">For easy management of built-in roles, there is a security group for each custom role with the name "Modern Workplace Roles - _Role Name_"(for example, “Modern Workplace Roles – Security Manager”).</span></span> <span data-ttu-id="9066b-150">若要将用户分配到其中一个安全组，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="9066b-150">To assign users to one of these security groups, follow these steps:</span></span>
1.  <span data-ttu-id="9066b-151">转到 Microsoft Endpoint Manager 门户。</span><span class="sxs-lookup"><span data-stu-id="9066b-151">Go the Microsoft Endpoint Manager portal.</span></span>
2.  <span data-ttu-id="9066b-152">选择 **左侧** 的"组"。</span><span class="sxs-lookup"><span data-stu-id="9066b-152">Select **Groups** on the left side.</span></span>
3.  <span data-ttu-id="9066b-153">搜索 **"现代工作区角色**"，然后选择与要分配的角色关联的组。</span><span class="sxs-lookup"><span data-stu-id="9066b-153">Search for **Modern Workplace Roles**, and then select the group associated with the role you want to assign.</span></span> 
4.  <span data-ttu-id="9066b-154">选择 **左侧** 的"成员"，然后在命令 **栏上选择"+** 添加成员"。</span><span class="sxs-lookup"><span data-stu-id="9066b-154">Select **Members** on the left side, and then select **+ Add members** on the command bar.</span></span>
5.  <span data-ttu-id="9066b-155">输入要添加的人的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9066b-155">Enter the email of the person being added.</span></span> <span data-ttu-id="9066b-156">如果他们是来宾，必须先邀请他们，然后才能分配组。</span><span class="sxs-lookup"><span data-stu-id="9066b-156">If they are a guest, you must invite them before you can assign the group.</span></span>
6.  <span data-ttu-id="9066b-157">选择 **底部的** "选择"。</span><span class="sxs-lookup"><span data-stu-id="9066b-157">Select **Select** at the bottom.</span></span>

> [!NOTE]
> <span data-ttu-id="9066b-158">当前不支持嵌套角色分配组。</span><span class="sxs-lookup"><span data-stu-id="9066b-158">Nesting security groups for role assignment is not currently supported.</span></span> 

### <a name="assigning-built-in-roles-to-groups"></a><span data-ttu-id="9066b-159">向组分配内置角色</span><span class="sxs-lookup"><span data-stu-id="9066b-159">Assigning built-in roles to groups</span></span>

<span data-ttu-id="9066b-160">如果需要将一个或多个内置角色分配给现有组，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="9066b-160">If you need to assign one or more of the built-in roles to a existing group, follow these steps:</span></span>
1. <span data-ttu-id="9066b-161">转到["portal.azure.com"。](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="9066b-161">Go to [portal.azure.com](https://portal.azure.com/).</span></span>
2. <span data-ttu-id="9066b-162">搜索并打开 **企业应用程序**。</span><span class="sxs-lookup"><span data-stu-id="9066b-162">Search for and open **Enterprise applications**.</span></span>
3. <span data-ttu-id="9066b-163">将"**应用程序类型"** 筛选器更改为 _"Microsoft 应用程序"，_ 然后选择"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="9066b-163">Change the **Application type** filter to _Microsoft Applications_ and, then select **Apply**.</span></span>
4. <span data-ttu-id="9066b-164">搜索并选择"_现代工作场所客户 API"。_</span><span class="sxs-lookup"><span data-stu-id="9066b-164">Search for and select _Modern Workplace Customer APIs_.</span></span>
5. <span data-ttu-id="9066b-165">从 **左侧窗格中** 选择"用户和组"，然后选择 **"+ 添加用户/组"。**</span><span class="sxs-lookup"><span data-stu-id="9066b-165">Select **Users and groups** from the pane on the left side, and then select **+ Add user/group**.</span></span>
6. <span data-ttu-id="9066b-166">从用户和组搜索 **你需要的组**。</span><span class="sxs-lookup"><span data-stu-id="9066b-166">Search for the group you want from **Users and groups**.</span></span>
7. <span data-ttu-id="9066b-167">从"选择角色" **中搜索适用的角色**，然后选择它。</span><span class="sxs-lookup"><span data-stu-id="9066b-167">Search for the applicable role from **Select a role**, and then select it.</span></span>
8. <span data-ttu-id="9066b-168">选择 **分配**。</span><span class="sxs-lookup"><span data-stu-id="9066b-168">Select **Assign**.</span></span>
