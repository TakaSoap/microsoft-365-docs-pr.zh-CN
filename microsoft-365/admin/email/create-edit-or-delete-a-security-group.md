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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: 了解如何创建、编辑或删除安全组。
ms.openlocfilehash: f51c21261a83e1a0034a67f9f1580dd297a3d583
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362277"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e10fb-103">在 Microsoft 365 管理中心中创建、编辑或删除安全组</span><span class="sxs-lookup"><span data-stu-id="e10fb-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="e10fb-104">在 "Office 365**组**" 页上，您可以创建可用于在 SharePoint ONLINE 和 CRM online 中为其分配相同权限的用户帐户组。</span><span class="sxs-lookup"><span data-stu-id="e10fb-104">On the Office 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="e10fb-105">例如，管理员可以创建一个安全组，以向特定用户组授予对 SharePoint 网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e10fb-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="e10fb-106">只有全局管理员和"用户管理"管理员拥有创建、编辑或删除安全组的权限；有关管理员角色的详细信息，请参阅[分配管理员角色](../add-users/assign-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="e10fb-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="e10fb-107">也存在您可以用于向用户组发送电子邮件或分配权限的 [Exchange Online 和 SharePoint Online 中的组](#groups-in-exchange-online-and-sharepoint-online)和向用户授权对网站和网站集的权限和访问权限的 [Exchange Online 和 SharePoint Online 中的组](#groups-in-exchange-online-and-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="e10fb-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="e10fb-108">计划使用网站邮箱？</span><span class="sxs-lookup"><span data-stu-id="e10fb-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="e10fb-109">通过安全组添加到 SharePoint 网站而不是单独添加的所有用户只能从 SharePoint 使用网站邮箱。</span><span class="sxs-lookup"><span data-stu-id="e10fb-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="e10fb-110">这些用户将无法从 Outlook 访问网站邮箱。</span><span class="sxs-lookup"><span data-stu-id="e10fb-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="e10fb-111">有关详细信息，请参阅[使用 Office 365 组而不是网站邮箱](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e10fb-111">For more information, see [Use Office 365 Groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="e10fb-112">管理中心中的安全组</span><span class="sxs-lookup"><span data-stu-id="e10fb-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="e10fb-113">添加安全组</span><span class="sxs-lookup"><span data-stu-id="e10fb-113">Add a security group</span></span>

1. <span data-ttu-id="e10fb-114">在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="e10fb-114">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="e10fb-115">在 "**组**" 页上，选择 "**添加组**"。</span><span class="sxs-lookup"><span data-stu-id="e10fb-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="e10fb-116">在 "**选择组类型**" 页上，选择 "**安全性**"。</span><span class="sxs-lookup"><span data-stu-id="e10fb-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="e10fb-117">按照步骤完成组的创建。</span><span class="sxs-lookup"><span data-stu-id="e10fb-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="e10fb-118">将成员添加到安全组</span><span class="sxs-lookup"><span data-stu-id="e10fb-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e10fb-119">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="e10fb-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="e10fb-120">在 "**组**" 页上选择安全组名称，然后在 "**成员**" 选项卡上选择 "**查看所有和管理成员**"。</span><span class="sxs-lookup"><span data-stu-id="e10fb-120">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="e10fb-121">在 "组" 窗格中，选择 "**添加成员**"，然后从列表中选择人员，或在**搜索**框中键入要添加的人员的姓名，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="e10fb-121">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="e10fb-122">若要删除成员，请选择其名称旁边的 X。</span><span class="sxs-lookup"><span data-stu-id="e10fb-122">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e10fb-123">在 "**组**" 页上选择安全组名称，然后选择 "**成员**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="e10fb-123">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="e10fb-124">在 "组" 窗格中，选择 "**添加成员**"，然后从列表中选择人员，或在**搜索**框中键入要添加的人员的姓名，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="e10fb-124">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="e10fb-125">若要删除成员，请选择其名称旁边的 X。</span><span class="sxs-lookup"><span data-stu-id="e10fb-125">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="e10fb-126">在 "**组**" 页上选择安全组名称，然后选择 "**成员**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="e10fb-126">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="e10fb-127">在 "组" 窗格中，选择 "**添加成员**"，然后从列表中选择人员，或在**搜索**框中键入要添加的人员的姓名，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="e10fb-127">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="e10fb-128">若要删除成员，请选择其名称旁边的 X。</span><span class="sxs-lookup"><span data-stu-id="e10fb-128">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="e10fb-129">编辑安全组</span><span class="sxs-lookup"><span data-stu-id="e10fb-129">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e10fb-130">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="e10fb-130">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="e10fb-131">在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="e10fb-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="e10fb-132">在 "**组**" 页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="e10fb-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="e10fb-133">在 "设置" 窗格中，选择 "**常规**" 选项卡或 "**成员**" 选项卡以编辑组的详细信息或成员。</span><span class="sxs-lookup"><span data-stu-id="e10fb-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e10fb-134">在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="e10fb-134">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="e10fb-135">在 "**组**" 页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="e10fb-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="e10fb-136">在 "安全组" 窗格中，选择 "**名称**" 或 "**成员**" 选项卡旁边的 "**编辑**" 以编辑组的详细信息或成员。</span><span class="sxs-lookup"><span data-stu-id="e10fb-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="e10fb-137">完成更改后，选择 "**保存** \> " "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="e10fb-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e10fb-138">在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="e10fb-138">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="e10fb-139">在 "**组**" 页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="e10fb-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="e10fb-140">在 "安全组" 窗格中，选择 "**名称**" 或 "**成员**" 选项卡旁边的 "**编辑**" 以编辑组的详细信息或成员。</span><span class="sxs-lookup"><span data-stu-id="e10fb-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="e10fb-141">完成更改后，选择 "**保存** \> " "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="e10fb-141">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="e10fb-142">删除安全组</span><span class="sxs-lookup"><span data-stu-id="e10fb-142">Delete a security group</span></span>

1. <span data-ttu-id="e10fb-143">在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="e10fb-143">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="e10fb-144">在 "**组**" 页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="e10fb-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="e10fb-145">选择 "**删除组**" （wasetbin 图标），然后选择 "**删除**" 进行确认。</span><span class="sxs-lookup"><span data-stu-id="e10fb-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="e10fb-146">删除组后，选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="e10fb-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="e10fb-147">Exchange Online 和 SharePoint Online 中的组</span><span class="sxs-lookup"><span data-stu-id="e10fb-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="e10fb-148">如果要创建用户组，以便可以同时向其发送电子邮件，您可以通过转到 "**管理员** \> **Exchange** \> **收件人** \> **组**" 在 Exchange 管理中心中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e10fb-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="e10fb-149">接下来， \*\*\*\*![选择 "](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)新建添加"，然后选择要创建的组类型：</span><span class="sxs-lookup"><span data-stu-id="e10fb-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="e10fb-150">**通讯组**：用于将邮件分发给一组用户。</span><span class="sxs-lookup"><span data-stu-id="e10fb-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="e10fb-151">它也称为*启用邮件的通讯组*，或者在 Office 365 中为*通讯组列表*。</span><span class="sxs-lookup"><span data-stu-id="e10fb-151">It's also called a  *mail-enabled distribution group*, or, in Office 365, a  *distribution list*.</span></span> <span data-ttu-id="e10fb-152">有关详细信息，请参阅[管理通讯组](https://technet.microsoft.com/library/bb124513.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e10fb-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="e10fb-153">**安全组**：可用于将邮件分发给一组用户，或授予对资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e10fb-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="e10fb-154">该组也称为*启用邮件的安全组*。</span><span class="sxs-lookup"><span data-stu-id="e10fb-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="e10fb-155">有关详细信息，请参阅[管理启用邮件的安全组](https://technet.microsoft.com/library/bb123521.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e10fb-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="e10fb-156">**动态通讯组**：一种通讯组类型，每当您基于定义的筛选器和条件发送邮件时，将重新计算收件人列表。</span><span class="sxs-lookup"><span data-stu-id="e10fb-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="e10fb-157">有关详细信息，请参阅 [管理动态通讯组](https://technet.microsoft.com/library/bb123722.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e10fb-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="e10fb-p107">当您在 Exchange 管理中心中创建通讯组和启用邮件的安全组之后，其名称和用户列表将显示在 Office 365" **安全组**"页面上。您可以在这两个位置删除这些组，但是只能在 Exchange 管理中心编辑它们。动态通讯组不显示在 Office 365" **安全组**"页面上。</span><span class="sxs-lookup"><span data-stu-id="e10fb-p107">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the Office 365 **Security groups** page. You can delete these groups in both locations, but you can edit them only in the Exchange admin center. Dynamic distribution groups don't show up on the Office 365 **Security groups** page.</span></span> 
  
 <span data-ttu-id="e10fb-161">SharePoint 组是在您创建网站集时自动创建的。</span><span class="sxs-lookup"><span data-stu-id="e10fb-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="e10fb-162">默认组使用 SharePoint 中的默认权限级别（有时称为 SharePoint 角色）向用户授予权限和访问权限。</span><span class="sxs-lookup"><span data-stu-id="e10fb-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="e10fb-163">有关详细信息，请参阅[Sharepoint Online 中的默认 SharePoint 组](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e10fb-163">For more information, see [Default SharePoint groups in SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="e10fb-164">在 SharePoint 中，安全组与我在 SharePoint 中创建的安全组有何不同？</span><span class="sxs-lookup"><span data-stu-id="e10fb-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="e10fb-165">安全组可与 SharePoint、Exchange、MDM、Windows 等一起使用。</span><span class="sxs-lookup"><span data-stu-id="e10fb-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="e10fb-166">在 SharePoint 中创建的安全组只能由该 SharePoint 网站集识别。</span><span class="sxs-lookup"><span data-stu-id="e10fb-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="e10fb-167">我是否需要使用安全组来保护组织的安全？</span><span class="sxs-lookup"><span data-stu-id="e10fb-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="e10fb-168">否。</span><span class="sxs-lookup"><span data-stu-id="e10fb-168">No.</span></span> <span data-ttu-id="e10fb-169">这只是管理组织安全性的一种更好的方法。</span><span class="sxs-lookup"><span data-stu-id="e10fb-169">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="e10fb-170">您可以始终授予用户权限并单独访问网站。</span><span class="sxs-lookup"><span data-stu-id="e10fb-170">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="e10fb-171">但使用安全组，您可以轻松地管理更多的用户组。</span><span class="sxs-lookup"><span data-stu-id="e10fb-171">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="e10fb-172">我是否可以向安全组发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="e10fb-172">Can I send email to a security group?</span></span>

<span data-ttu-id="e10fb-173">是。</span><span class="sxs-lookup"><span data-stu-id="e10fb-173">Yes.</span></span> <span data-ttu-id="e10fb-174">但是，如果您想要使用组进行电子邮件和协作，我们建议您改为[创建 Office 365 组](../create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="e10fb-174">But if you want to use groups for email and collaboration, we recommend that you [create an Office 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
