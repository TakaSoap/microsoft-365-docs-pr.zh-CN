---
title: 将管理员角色分配给 Microsoft 365 管理中心
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: get-started-article
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: 了解如何向用户或业务中的多个用户分配管理员角色，以便他们可以在管理中心执行特定任务。
ms.openlocfilehash: 9c10ef7d6dade3d826c9c291e58b3e8e2a58f2a6
ms.sourcegitcommit: 311bbd6f168225ede166d29696126a1e003eee0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2020
ms.locfileid: "43151365"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="2d48d-103">分配管理员角色</span><span class="sxs-lookup"><span data-stu-id="2d48d-103">Assign admin roles</span></span>

<span data-ttu-id="2d48d-104">如果你是购买 Microsoft 商业订阅的人员，则是全局管理员。这意味着您对订阅中的产品具有无限制的控制，并且您可以访问大多数数据。</span><span class="sxs-lookup"><span data-stu-id="2d48d-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="2d48d-105">有关详细信息，请参阅[关于管理员角色](about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="2d48d-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="2d48d-106">当您添加新用户时，如果您不向他们分配管理员角色，则他们处于*用户角色*中，并且对任何 Microsoft 管理中心都没有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="2d48d-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="2d48d-107">但是，如果您需要帮助完成操作，则可以向用户分配管理员角色。</span><span class="sxs-lookup"><span data-stu-id="2d48d-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="2d48d-108">例如，如果您需要某人帮助重置密码，则不应为他们分配全局管理员角色，应为他们分配密码管理员角色。</span><span class="sxs-lookup"><span data-stu-id="2d48d-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="2d48d-109">拥有过多的全局管理员（对数据和联机业务的无限制访问权限）是一种安全风险。</span><span class="sxs-lookup"><span data-stu-id="2d48d-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

<span data-ttu-id="2d48d-110">观看有关添加管理员的简短视频。</span><span class="sxs-lookup"><span data-stu-id="2d48d-110">Watch a short video about adding an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="2d48d-111">如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="2d48d-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="2d48d-112">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="2d48d-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

## <a name="assign-admin-roles"></a><span data-ttu-id="2d48d-113">分配管理员角色</span><span class="sxs-lookup"><span data-stu-id="2d48d-113">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="2d48d-114">您可以通过两种不同的方式为用户分配角色：</span><span class="sxs-lookup"><span data-stu-id="2d48d-114">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="2d48d-115">您可以转到用户的详细信息并**管理角色**以向用户分配角色。</span><span class="sxs-lookup"><span data-stu-id="2d48d-115">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="2d48d-116">或者，您可以转到 "**角色**" 并选择角色，然后向其中添加多个用户。</span><span class="sxs-lookup"><span data-stu-id="2d48d-116">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="2d48d-117">使用角色为用户分配管理员角色</span><span class="sxs-lookup"><span data-stu-id="2d48d-117">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="2d48d-118">在管理中心中，转到**角色** > **角色**以查看适用于您的组织的所有管理员角色。</span><span class="sxs-lookup"><span data-stu-id="2d48d-118">In the admin center, go to **Roles** > **Roles** to view all of the admin roles available for your organization.</span></span>
2. <span data-ttu-id="2d48d-119">选择要向其分配用户的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="2d48d-119">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="2d48d-120">选择 "**分配的管理员** > **添加**"。</span><span class="sxs-lookup"><span data-stu-id="2d48d-120">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="2d48d-121">键入用户的**显示名称**或**用户名**，然后从建议列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="2d48d-121">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="2d48d-122">在完成之前，请添加多个用户。</span><span class="sxs-lookup"><span data-stu-id="2d48d-122">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="2d48d-123">选择 "**保存**"，然后将用户添加到分配的管理员列表中。</span><span class="sxs-lookup"><span data-stu-id="2d48d-123">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="2d48d-124">将用户分配给活动用户的管理员角色</span><span class="sxs-lookup"><span data-stu-id="2d48d-124">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="2d48d-125">在管理中心，转到 "**用户** > [活动用户](https://go.microsoft.com/fwlink/p/?linkid=834822)" 页。</span><span class="sxs-lookup"><span data-stu-id="2d48d-125">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="2d48d-126">在 "**活动用户**" 页上，选择要更改其管理员角色的用户。</span><span class="sxs-lookup"><span data-stu-id="2d48d-126">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="2d48d-127">在浮出控件窗格中，在 "**角色**" 旁边，选择 "**管理角色**"。</span><span class="sxs-lookup"><span data-stu-id="2d48d-127">In the flyout pane, next to **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="2d48d-128">选择要分配给用户的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="2d48d-128">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="2d48d-129">如果看不到您要查找的角色，请选择列表底部的 "**全部显示**"。</span><span class="sxs-lookup"><span data-stu-id="2d48d-129">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="2d48d-130">在管理中心，转到“**用户**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="2d48d-130">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="2d48d-131">在 "**活动用户**" 页上，选择要更改其管理员角色的用户。</span><span class="sxs-lookup"><span data-stu-id="2d48d-131">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="2d48d-132">在浮出控件窗格中，单击 "**角色**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="2d48d-132">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="2d48d-133">如果看不到 "**编辑**" 选项，则无权编辑，也不能将管理员角色分配给其他人。</span><span class="sxs-lookup"><span data-stu-id="2d48d-133">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="2d48d-134">请求企业中的全局管理员为您分配角色。</span><span class="sxs-lookup"><span data-stu-id="2d48d-134">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="2d48d-135">在小型企业中，企业所有者（购买订阅的人员）是全局管理员。在大型企业中，IT 部门的关键人员是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="2d48d-135">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="2d48d-136">选择 "**自定义管理员**" 查看我们为你自定义的角色的列表。</span><span class="sxs-lookup"><span data-stu-id="2d48d-136">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="2d48d-137">有关每个角色的说明，请参阅[关于管理员角色。](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="2d48d-137">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="2d48d-138">在管理中心，转到“**用户**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="2d48d-138">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="2d48d-139">在 "**活动用户**" 页上，选择要更改其管理员角色的用户。</span><span class="sxs-lookup"><span data-stu-id="2d48d-139">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="2d48d-140">在浮出控件窗格中，单击 "**角色**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="2d48d-140">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="2d48d-141">如果看不到 "**编辑**" 选项，则无权编辑，也不能将管理员角色分配给其他人。</span><span class="sxs-lookup"><span data-stu-id="2d48d-141">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="2d48d-142">请求企业中的全局管理员为您分配角色。</span><span class="sxs-lookup"><span data-stu-id="2d48d-142">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="2d48d-143">在小型企业中，企业所有者（购买订阅的人员）是全局管理员。在大型企业中，IT 部门的关键人员是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="2d48d-143">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="2d48d-144">选择 "**自定义管理员**" 查看我们为你自定义的角色的列表。</span><span class="sxs-lookup"><span data-stu-id="2d48d-144">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="2d48d-145">有关每个角色的说明，请参阅[关于管理员角色。](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="2d48d-145">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end


## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="2d48d-146">向多个用户分配管理员角色</span><span class="sxs-lookup"><span data-stu-id="2d48d-146">Assign admin roles to multiple users</span></span>

<span data-ttu-id="2d48d-147">如果你知道 PowerShell，请参阅[使用 powershell 向用户帐户分配角色](https://go.microsoft.com/fwlink/?linkid=854257)。</span><span class="sxs-lookup"><span data-stu-id="2d48d-147">If you know PowerShell, see [Assign roles to user accounts with PowerShell](https://go.microsoft.com/fwlink/?linkid=854257).</span></span> <span data-ttu-id="2d48d-148">它非常适合为数百个用户分配角色。</span><span class="sxs-lookup"><span data-stu-id="2d48d-148">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="2d48d-149">请按照以下说明向数十个用户分配角色。</span><span class="sxs-lookup"><span data-stu-id="2d48d-149">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"


## <a name="didnt-work-for-you"></a><span data-ttu-id="2d48d-150">不起作用？</span><span class="sxs-lookup"><span data-stu-id="2d48d-150">Didn't work for you?</span></span>

<span data-ttu-id="2d48d-151">您可能没有适当的权限，因此您没有权限将管理员角色分配给其他用户。</span><span class="sxs-lookup"><span data-stu-id="2d48d-151">You might not have the correct permissions and so you don't have access to assign admin roles to other users.</span></span> <span data-ttu-id="2d48d-152">请其他管理员为你分配角色。</span><span class="sxs-lookup"><span data-stu-id="2d48d-152">Ask another admin to assign roles for you.</span></span>

::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="2d48d-153">相关文章</span><span class="sxs-lookup"><span data-stu-id="2d48d-153">Related articles</span></span>

[<span data-ttu-id="2d48d-154">使用 PowerShell 向用户帐户分配角色</span><span class="sxs-lookup"><span data-stu-id="2d48d-154">Assign roles to user accounts with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/assign-roles-to-user-accounts-with-office-365-powershell)

[<span data-ttu-id="2d48d-155">授权或删除合作伙伴关系</span><span class="sxs-lookup"><span data-stu-id="2d48d-155">Authorize or remove partner relationships</span></span>](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)

[<span data-ttu-id="2d48d-156">使用 Exchange 管理中心添加备选电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="2d48d-156">Add an alternative email address using the Exchange admin center</span></span>](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/email-addresses?view=exchserver-2019#add-an-email-address-to-a-user-mailbox)

