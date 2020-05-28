---
title: 在 Microsoft 365 管理中心中创建、编辑或删除安全组
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: 了解如何创建、编辑或删除安全组。
ms.openlocfilehash: 283f1eca7500bfb1d8172657639bbc7cff76906f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400084"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="40b7a-103">在 Microsoft 365 管理中心中创建、编辑或删除安全组</span><span class="sxs-lookup"><span data-stu-id="40b7a-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="40b7a-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="40b7a-104">The admin center is changing.</span></span> <span data-ttu-id="40b7a-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="40b7a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="40b7a-106">在 "Microsoft 365**组**" 页上，您可以创建可用于在 SharePoint ONLINE 和 CRM online 中为其分配相同权限的用户帐户组。</span><span class="sxs-lookup"><span data-stu-id="40b7a-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="40b7a-107">例如，管理员可以创建一个安全组，以向特定用户组授予对 SharePoint 网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="40b7a-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="40b7a-108">只有全局管理员和"用户管理"管理员拥有创建、编辑或删除安全组的权限；有关管理员角色的详细信息，请参阅[分配管理员角色](../add-users/assign-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="40b7a-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="40b7a-109">也存在您可以用于向用户组发送电子邮件或分配权限的 [Exchange Online 和 SharePoint Online 中的组](#groups-in-exchange-online-and-sharepoint-online)和向用户授权对网站和网站集的权限和访问权限的 [Exchange Online 和 SharePoint Online 中的组](#groups-in-exchange-online-and-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="40b7a-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="40b7a-110">计划使用网站邮箱？</span><span class="sxs-lookup"><span data-stu-id="40b7a-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="40b7a-111">通过安全组添加到 SharePoint 网站而不是单独添加的所有用户只能从 SharePoint 使用网站邮箱。</span><span class="sxs-lookup"><span data-stu-id="40b7a-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="40b7a-112">这些用户将无法从 Outlook 访问网站邮箱。</span><span class="sxs-lookup"><span data-stu-id="40b7a-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="40b7a-113">有关详细信息，请参阅[使用 Microsoft 365 组而不是站点邮箱](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="40b7a-113">For more information, see [Use Microsoft 365 groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="40b7a-114">管理中心中的安全组</span><span class="sxs-lookup"><span data-stu-id="40b7a-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="40b7a-115">添加安全组</span><span class="sxs-lookup"><span data-stu-id="40b7a-115">Add a security group</span></span>

1. <span data-ttu-id="40b7a-116">在 Microsoft 365 管理中心，转到 "**组**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="40b7a-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="40b7a-117">在 "**组**" 页上，选择 "**添加组**"。</span><span class="sxs-lookup"><span data-stu-id="40b7a-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="40b7a-118">在 "**选择组类型**" 页上，选择 "**安全性**"。</span><span class="sxs-lookup"><span data-stu-id="40b7a-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="40b7a-119">按照步骤完成组的创建。</span><span class="sxs-lookup"><span data-stu-id="40b7a-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="40b7a-120">将成员添加到安全组</span><span class="sxs-lookup"><span data-stu-id="40b7a-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="40b7a-121">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="40b7a-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="40b7a-122">在 "**组**" 页上选择安全组名称，然后在 "**成员**" 选项卡上选择 "**查看所有和管理成员**"。</span><span class="sxs-lookup"><span data-stu-id="40b7a-122">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="40b7a-123">在 "组" 窗格中，选择 "**添加成员**"，然后从列表中选择人员，或在**搜索**框中键入要添加的人员的姓名，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="40b7a-123">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="40b7a-124">若要删除成员，请选择其名称旁边的 X。</span><span class="sxs-lookup"><span data-stu-id="40b7a-124">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="40b7a-125">在 "**组**" 页上选择安全组名称，然后选择 "**成员**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="40b7a-125">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="40b7a-126">在 "组" 窗格中，选择 "**添加成员**"，然后从列表中选择人员，或在**搜索**框中键入要添加的人员的姓名，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="40b7a-126">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="40b7a-127">若要删除成员，请选择其名称旁边的 X。</span><span class="sxs-lookup"><span data-stu-id="40b7a-127">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="40b7a-128">在 "**组**" 页上选择安全组名称，然后选择 "**成员**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="40b7a-128">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="40b7a-129">在 "组" 窗格中，选择 "**添加成员**"，然后从列表中选择人员，或在**搜索**框中键入要添加的人员的姓名，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="40b7a-129">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="40b7a-130">若要删除成员，请选择其名称旁边的 X。</span><span class="sxs-lookup"><span data-stu-id="40b7a-130">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="40b7a-131">编辑安全组</span><span class="sxs-lookup"><span data-stu-id="40b7a-131">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="40b7a-132">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="40b7a-132">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="40b7a-133">在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="40b7a-133">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="40b7a-134">在 "**组**" 页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="40b7a-134">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="40b7a-135">在 "设置" 窗格中，选择 "**常规**" 选项卡或 "**成员**" 选项卡以编辑组的详细信息或成员。</span><span class="sxs-lookup"><span data-stu-id="40b7a-135">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="40b7a-136">在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="40b7a-136">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="40b7a-137">在 "**组**" 页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="40b7a-137">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="40b7a-138">在 "安全组" 窗格中，选择 "**名称**" 或 "**成员**" 选项卡旁边的 "**编辑**" 以编辑组的详细信息或成员。</span><span class="sxs-lookup"><span data-stu-id="40b7a-138">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="40b7a-139">完成更改后，选择 "**保存**" " \> **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="40b7a-139">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="40b7a-140">在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="40b7a-140">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="40b7a-141">在 "**组**" 页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="40b7a-141">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="40b7a-142">在 "安全组" 窗格中，选择 "**名称**" 或 "**成员**" 选项卡旁边的 "**编辑**" 以编辑组的详细信息或成员。</span><span class="sxs-lookup"><span data-stu-id="40b7a-142">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="40b7a-143">完成更改后，选择 "**保存**" " > **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="40b7a-143">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="40b7a-144">删除安全组</span><span class="sxs-lookup"><span data-stu-id="40b7a-144">Delete a security group</span></span>

1. <span data-ttu-id="40b7a-145">在 "管理中心" 中，转到 "**组**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="40b7a-145">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="40b7a-146">在 "**组**" 页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="40b7a-146">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="40b7a-147">选择 "**删除组**" （wasetbin 图标），然后选择 "**删除**" 进行确认。</span><span class="sxs-lookup"><span data-stu-id="40b7a-147">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="40b7a-148">删除组后，选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="40b7a-148">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="40b7a-149">Exchange Online 和 SharePoint Online 中的组</span><span class="sxs-lookup"><span data-stu-id="40b7a-149">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="40b7a-150">如果要创建用户组，以便可以同时向其发送电子邮件，您可以通过转到 "**管理员** \> **Exchange** \> **收件人** \> **组**" 在 Exchange 管理中心中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="40b7a-150">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="40b7a-151">接下来，选择 "**新建** ![ 添加 ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) "，然后选择要创建的组类型：</span><span class="sxs-lookup"><span data-stu-id="40b7a-151">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="40b7a-152">**通讯组**：用于将邮件分发给一组用户。</span><span class="sxs-lookup"><span data-stu-id="40b7a-152">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="40b7a-153">它也称为*启用邮件的通讯组*或*通讯组列表*。</span><span class="sxs-lookup"><span data-stu-id="40b7a-153">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="40b7a-154">有关详细信息，请参阅[管理通讯组](https://technet.microsoft.com/library/bb124513.aspx)。</span><span class="sxs-lookup"><span data-stu-id="40b7a-154">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="40b7a-155">**安全组**：可用于将邮件分发给一组用户，或授予对资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="40b7a-155">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="40b7a-156">该组也称为*启用邮件的安全组*。</span><span class="sxs-lookup"><span data-stu-id="40b7a-156">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="40b7a-157">有关详细信息，请参阅[管理启用邮件的安全组](https://technet.microsoft.com/library/bb123521.aspx)。</span><span class="sxs-lookup"><span data-stu-id="40b7a-157">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="40b7a-158">**动态通讯组**：一种通讯组类型，每当您基于定义的筛选器和条件发送邮件时，将重新计算收件人列表。</span><span class="sxs-lookup"><span data-stu-id="40b7a-158">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="40b7a-159">有关详细信息，请参阅 [管理动态通讯组](https://technet.microsoft.com/library/bb123722.aspx)。</span><span class="sxs-lookup"><span data-stu-id="40b7a-159">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="40b7a-160">在 Exchange 管理中心中创建通讯组和已启用邮件的安全组之后，其名称和用户列表将显示在 "**安全组**" 页面上。</span><span class="sxs-lookup"><span data-stu-id="40b7a-160">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="40b7a-161">您可以在这两个位置删除这些组，但是只能在 Exchange 管理中心编辑它们。</span><span class="sxs-lookup"><span data-stu-id="40b7a-161">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="40b7a-162">"**安全组**" 页上未显示动态通讯组。</span><span class="sxs-lookup"><span data-stu-id="40b7a-162">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="40b7a-163">SharePoint 组是在您创建网站集时自动创建的。</span><span class="sxs-lookup"><span data-stu-id="40b7a-163">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="40b7a-164">默认组使用 SharePoint 中的默认权限级别（有时称为 SharePoint 角色）向用户授予权限和访问权限。</span><span class="sxs-lookup"><span data-stu-id="40b7a-164">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="40b7a-165">有关详细信息，请参阅[Sharepoint Online 中的默认 SharePoint 组](https://docs.microsoft.com/sharepoint/default-sharepoint-groups)。</span><span class="sxs-lookup"><span data-stu-id="40b7a-165">For more information, see [Default SharePoint groups in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="40b7a-166">在 SharePoint 中，安全组与我在 SharePoint 中创建的安全组有何不同？</span><span class="sxs-lookup"><span data-stu-id="40b7a-166">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="40b7a-167">安全组可与 SharePoint、Exchange、MDM、Windows 等一起使用。</span><span class="sxs-lookup"><span data-stu-id="40b7a-167">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="40b7a-168">在 SharePoint 中创建的安全组只能由该 SharePoint 网站集识别。</span><span class="sxs-lookup"><span data-stu-id="40b7a-168">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="40b7a-169">我是否需要使用安全组来保护组织的安全？</span><span class="sxs-lookup"><span data-stu-id="40b7a-169">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="40b7a-170">否。</span><span class="sxs-lookup"><span data-stu-id="40b7a-170">No.</span></span> <span data-ttu-id="40b7a-171">这只是管理组织安全性的一种更好的方法。</span><span class="sxs-lookup"><span data-stu-id="40b7a-171">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="40b7a-172">您可以始终授予用户权限并单独访问网站。</span><span class="sxs-lookup"><span data-stu-id="40b7a-172">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="40b7a-173">但使用安全组，您可以轻松地管理更多的用户组。</span><span class="sxs-lookup"><span data-stu-id="40b7a-173">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="40b7a-174">我是否可以向安全组发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="40b7a-174">Can I send email to a security group?</span></span>

<span data-ttu-id="40b7a-175">正确。</span><span class="sxs-lookup"><span data-stu-id="40b7a-175">Yes.</span></span> <span data-ttu-id="40b7a-176">但是，如果您想要使用组进行电子邮件和协作，我们建议您改为[创建 Microsoft 365 组](../create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="40b7a-176">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
