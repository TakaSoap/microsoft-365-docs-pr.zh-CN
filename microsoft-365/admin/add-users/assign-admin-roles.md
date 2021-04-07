---
title: 在 Microsoft 365 管理中心分配管理员角色
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
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: 了解如何将管理员角色分配给企业中的一个或多个用户，以便他们可以在管理中心执行特定任务。
ms.openlocfilehash: 5c40199823c93968be97302efc8e2d404f3cfed1
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604329"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="3c77b-103">分配管理员角色</span><span class="sxs-lookup"><span data-stu-id="3c77b-103">Assign admin roles</span></span>

<span data-ttu-id="3c77b-104">如果你是购买 Microsoft 商业版订阅的人，你是全局管理员。这意味着你可以无限制地控制订阅中的产品，并且可以访问大部分数据。</span><span class="sxs-lookup"><span data-stu-id="3c77b-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="3c77b-105">有关详细信息，请参阅[关于管理员角色](about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="3c77b-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="3c77b-106">添加新用户时，如果你没有为其分配管理员角色，则他们担任用户角色，并且没有任何 Microsoft管理中心的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="3c77b-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="3c77b-107">但是，如果你需要有关完成工作的帮助，你可以将管理员角色分配给用户。</span><span class="sxs-lookup"><span data-stu-id="3c77b-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="3c77b-108">例如，如果需要某人来帮助重置密码，则不应为其分配全局管理员角色，而应为其分配密码管理员角色。</span><span class="sxs-lookup"><span data-stu-id="3c77b-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="3c77b-109">拥有过多的全局管理员（对数据和联机业务具有无限制的访问权限）是一种安全风险。</span><span class="sxs-lookup"><span data-stu-id="3c77b-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

## <a name="watch-add-an-adminbrbr"></a><span data-ttu-id="3c77b-110">观看：添加管理员。</span><span class="sxs-lookup"><span data-stu-id="3c77b-110">Watch: Add an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="3c77b-111">如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="3c77b-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="assign-admin-roles"></a><span data-ttu-id="3c77b-112">分配管理员角色</span><span class="sxs-lookup"><span data-stu-id="3c77b-112">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="3c77b-113">可以通过两种不同的方式将用户分配给角色：</span><span class="sxs-lookup"><span data-stu-id="3c77b-113">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="3c77b-114">可以转到用户的详细信息和管理 **角色以** 向用户分配角色。</span><span class="sxs-lookup"><span data-stu-id="3c77b-114">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="3c77b-115">或者，你可以转到 **角色** 并选择角色，然后向该角色添加多个用户。</span><span class="sxs-lookup"><span data-stu-id="3c77b-115">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="3c77b-116">使用角色向用户分配管理员角色</span><span class="sxs-lookup"><span data-stu-id="3c77b-116">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="3c77b-117">在管理中心， **转到角色**。</span><span class="sxs-lookup"><span data-stu-id="3c77b-117">In the admin center, go to **Roles**.</span></span> <span data-ttu-id="3c77b-118">选择 **Azure AD 或** **Intune** 选项卡以查看适用于你的组织的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="3c77b-118">Choose the **Azure AD** or **Intune** tabs to view the admin roles available for your organization.</span></span>
2. <span data-ttu-id="3c77b-119">选择要为其分配用户的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="3c77b-119">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="3c77b-120">选择 **分配管理员添加** > 。</span><span class="sxs-lookup"><span data-stu-id="3c77b-120">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="3c77b-121">键入用户的 **显示名称\*\*\*\*或用户名**，然后从建议列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="3c77b-121">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="3c77b-122">添加多个用户，直到完成。</span><span class="sxs-lookup"><span data-stu-id="3c77b-122">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="3c77b-123">选择 **"** 保存"，然后将用户添加到分配的管理员列表中。</span><span class="sxs-lookup"><span data-stu-id="3c77b-123">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="3c77b-124">从活动用户向管理员角色分配用户</span><span class="sxs-lookup"><span data-stu-id="3c77b-124">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="3c77b-125">在管理中心，转到"用户 > [""活动用户"](https://go.microsoft.com/fwlink/p/?linkid=834822)页面。</span><span class="sxs-lookup"><span data-stu-id="3c77b-125">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="3c77b-126">在 **"活动用户"** 页上，选择要更改其管理员角色的用户。</span><span class="sxs-lookup"><span data-stu-id="3c77b-126">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="3c77b-127">在飞出窗格中的"角色 **"下**，选择"**管理角色"。**</span><span class="sxs-lookup"><span data-stu-id="3c77b-127">In the flyout pane, under **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="3c77b-128">选择要分配给用户的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="3c77b-128">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="3c77b-129">如果看不到要查找的角色，请选择列表底部的"全部显示"。 </span><span class="sxs-lookup"><span data-stu-id="3c77b-129">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3c77b-130">在管理中心，转到“**用户**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="3c77b-130">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="3c77b-131">在 **"活动用户"** 页上，选择要更改其管理员角色的用户。</span><span class="sxs-lookup"><span data-stu-id="3c77b-131">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="3c77b-132">在飞出窗格中的"角色"**旁边**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="3c77b-132">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="3c77b-133">如果看不到"编辑"选项，则你没有编辑权限，并且无法将管理员角色分配给其他人。</span><span class="sxs-lookup"><span data-stu-id="3c77b-133">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="3c77b-134">让企业中的全局管理员为分配角色。</span><span class="sxs-lookup"><span data-stu-id="3c77b-134">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="3c77b-135">在小型企业中，企业所有者 (购买订阅的用户) 全局管理员。在大型企业中，IT 部门的关键人员是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="3c77b-135">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="3c77b-136">选择 **"自定义** 管理员"以查看我们为您自定义的角色列表。</span><span class="sxs-lookup"><span data-stu-id="3c77b-136">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="3c77b-137">有关每个角色的说明，请参阅关于 [管理员角色。](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="3c77b-137">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3c77b-138">在管理中心，转到“**用户**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="3c77b-138">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="3c77b-139">在 **"活动用户"** 页上，选择要更改其管理员角色的用户。</span><span class="sxs-lookup"><span data-stu-id="3c77b-139">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="3c77b-140">在飞出窗格中的"角色"**旁边**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="3c77b-140">In the flyout pane, next to **Roles**, select **Edit**.</span></span>

    <span data-ttu-id="3c77b-141">如果看不到"编辑"选项，则你没有编辑权限，并且无法将管理员角色分配给其他人。</span><span class="sxs-lookup"><span data-stu-id="3c77b-141">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="3c77b-142">让企业中的全局管理员为分配角色。</span><span class="sxs-lookup"><span data-stu-id="3c77b-142">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="3c77b-143">在小型企业中，企业所有者 (购买订阅的用户) 全局管理员。在大型企业中，IT 部门的关键人员是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="3c77b-143">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="3c77b-144">选择 **"自定义** 管理员"以查看我们为您自定义的角色列表。</span><span class="sxs-lookup"><span data-stu-id="3c77b-144">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="3c77b-145">有关每个角色的说明，请参阅关于 [管理员角色。](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="3c77b-145">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="3c77b-146">向多个用户分配管理员角色</span><span class="sxs-lookup"><span data-stu-id="3c77b-146">Assign admin roles to multiple users</span></span>

<span data-ttu-id="3c77b-147">如果您知道 PowerShell，请参阅 [使用 PowerShell 向用户帐户分配角色](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="3c77b-147">If you know PowerShell, see [Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md).</span></span> <span data-ttu-id="3c77b-148">它非常适合为数百个用户分配角色。</span><span class="sxs-lookup"><span data-stu-id="3c77b-148">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="3c77b-149">请按照以下说明向数十个用户分配角色。</span><span class="sxs-lookup"><span data-stu-id="3c77b-149">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a><span data-ttu-id="3c77b-150">检查贵组织的管理员角色</span><span class="sxs-lookup"><span data-stu-id="3c77b-150">Check admin roles in your organization</span></span>

<span data-ttu-id="3c77b-151">您可能没有将管理员角色分配给其他用户的正确权限。</span><span class="sxs-lookup"><span data-stu-id="3c77b-151">You might not have the correct permissions to assign admin roles to other users.</span></span> <span data-ttu-id="3c77b-152">检查以确保你拥有正确的权限，或要求其他管理员为你分配角色。</span><span class="sxs-lookup"><span data-stu-id="3c77b-152">Check to make sure you have the correct permissions or ask another admin to assign roles for you.</span></span>

<span data-ttu-id="3c77b-153">可以通过两种不同的方式检查管理员角色权限：</span><span class="sxs-lookup"><span data-stu-id="3c77b-153">You can check admin role permissions in 2 different ways:</span></span>

- <span data-ttu-id="3c77b-154">你可以转到用户的详细信息，然后查看 **"帐户"** 页面上 **的角色下。**</span><span class="sxs-lookup"><span data-stu-id="3c77b-154">You can go to the user's details and look under **Roles** on the **Account** page.</span></span>
- <span data-ttu-id="3c77b-155">或者，你可以转到 **角色** 并选择管理员角色，然后选择分配的管理员以查看分配了哪些用户。</span><span class="sxs-lookup"><span data-stu-id="3c77b-155">Or you can go to **Roles** and select the admin role, and select assigned admins to see which users are assigned.</span></span>

::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="3c77b-156">相关文章</span><span class="sxs-lookup"><span data-stu-id="3c77b-156">Related articles</span></span>

[<span data-ttu-id="3c77b-157">关于 Microsoft 365 管理员角色</span><span class="sxs-lookup"><span data-stu-id="3c77b-157">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

[<span data-ttu-id="3c77b-158">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="3c77b-158">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)

[<span data-ttu-id="3c77b-159">使用 PowerShell 向用户帐户分配角色</span><span class="sxs-lookup"><span data-stu-id="3c77b-159">Assign roles to user accounts with PowerShell</span></span>](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)

[<span data-ttu-id="3c77b-160">授权或删除合作伙伴关系</span><span class="sxs-lookup"><span data-stu-id="3c77b-160">Authorize or remove partner relationships</span></span>](../misc/add-partner.md)