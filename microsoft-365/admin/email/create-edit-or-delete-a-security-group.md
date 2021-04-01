---
title: 在 Microsoft 365 管理中心创建、编辑或删除安全组
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
ms.openlocfilehash: 4ea97683e47f7f0ef8f196db32df8e22f9b1a0b9
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470973"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="0ef40-103">在 Microsoft 365 管理中心创建、编辑或删除安全组</span><span class="sxs-lookup"><span data-stu-id="0ef40-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="0ef40-104">在"Microsoft 365 组"页上，可以创建用户帐户组，这些用户帐户可用于在 SharePoint Online 和 CRM Online 中分配相同的权限。</span><span class="sxs-lookup"><span data-stu-id="0ef40-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="0ef40-105">例如，管理员可以创建一个安全组，以向特定用户组授予对 SharePoint 网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0ef40-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="0ef40-106">只有全局管理员和"用户管理"管理员拥有创建、编辑或删除安全组的权限；有关管理员角色的详细信息，请参阅[分配管理员角色](../add-users/assign-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="0ef40-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="0ef40-107">也存在您可以用于向用户组发送电子邮件或分配权限的 [Exchange Online 和 SharePoint Online 中的组](#groups-in-exchange-online-and-sharepoint-online)和向用户授权对网站和网站集的权限和访问权限的 [Exchange Online 和 SharePoint Online 中的组](#groups-in-exchange-online-and-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="0ef40-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="0ef40-108">计划使用网站邮箱？</span><span class="sxs-lookup"><span data-stu-id="0ef40-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="0ef40-109">通过安全组添加到 SharePoint 网站而不是单独添加的所有用户只能从 SharePoint 使用网站邮箱。</span><span class="sxs-lookup"><span data-stu-id="0ef40-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="0ef40-110">这些用户将无法从 Outlook 访问网站邮箱。</span><span class="sxs-lookup"><span data-stu-id="0ef40-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="0ef40-111">有关详细信息，请参阅使用 [Microsoft 365 组而不是网站邮箱](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)。</span><span class="sxs-lookup"><span data-stu-id="0ef40-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="0ef40-112">管理管理中心中的安全组</span><span class="sxs-lookup"><span data-stu-id="0ef40-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="0ef40-113">添加安全组</span><span class="sxs-lookup"><span data-stu-id="0ef40-113">Add a security group</span></span>

1. <span data-ttu-id="0ef40-114">在 Microsoft 365 管理中心中，转到组  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>页面。</span><span class="sxs-lookup"><span data-stu-id="0ef40-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="0ef40-115">在"**组"** 页上，选择 **"添加组"。**</span><span class="sxs-lookup"><span data-stu-id="0ef40-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="0ef40-116">在"**选择组类型"页上，** 选择"安全性 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ef40-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="0ef40-117">按照步骤完成组的创建。</span><span class="sxs-lookup"><span data-stu-id="0ef40-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="0ef40-118">向安全组添加成员</span><span class="sxs-lookup"><span data-stu-id="0ef40-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="0ef40-119">在"组"页上 **选择安全组** 名称，在"成员 **"选项卡上**，选择"**查看所有和管理成员"。**</span><span class="sxs-lookup"><span data-stu-id="0ef40-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="0ef40-120">在组窗格中，选择"**添加** 成员"，然后从列表中选择人员，或在"搜索"框中键入要添加的人的姓名，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ef40-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="0ef40-121">若要删除成员，请选择其名称旁边的 X。</span><span class="sxs-lookup"><span data-stu-id="0ef40-121">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0ef40-122">在"组"页上 **选择安全组** 名称，**然后选择"成员**"旁边的"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ef40-122">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="0ef40-123">在组窗格中，选择"**添加** 成员"，然后从列表中选择人员，或在"搜索"框中键入要添加的人的姓名，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ef40-123">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="0ef40-124">若要删除成员，请选择其名称旁边的 X。</span><span class="sxs-lookup"><span data-stu-id="0ef40-124">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="0ef40-125">在"组"页上 **选择安全组** 名称，**然后选择"成员**"旁边的"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ef40-125">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="0ef40-126">在组窗格中，选择"**添加** 成员"，然后从列表中选择人员，或在"搜索"框中键入要添加的人的姓名，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ef40-126">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="0ef40-127">若要删除成员，请选择其名称旁边的 X。</span><span class="sxs-lookup"><span data-stu-id="0ef40-127">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="0ef40-128">编辑安全组</span><span class="sxs-lookup"><span data-stu-id="0ef40-128">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0ef40-129">在管理中心，转到组 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>页面。</span><span class="sxs-lookup"><span data-stu-id="0ef40-129">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="0ef40-130">在 **"组** "页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="0ef40-130">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0ef40-131">在设置窗格中，选择"常规 **"** 选项卡或" **成员** "选项卡以编辑组详细信息或成员。</span><span class="sxs-lookup"><span data-stu-id="0ef40-131">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0ef40-132">在管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">中心</a>中，转到组 \> **组** 页面。</span><span class="sxs-lookup"><span data-stu-id="0ef40-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="0ef40-133">在 **"组** "页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="0ef40-133">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0ef40-134">在安全组窗格中，选择"名称"或"成员"选项卡旁边的"编辑"以编辑组详细信息或成员。 </span><span class="sxs-lookup"><span data-stu-id="0ef40-134">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="0ef40-135">进行更改后，选择"保存"" \> **关闭"。**</span><span class="sxs-lookup"><span data-stu-id="0ef40-135">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0ef40-136">在管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">中心</a>中，转到组 \> **组** 页面。</span><span class="sxs-lookup"><span data-stu-id="0ef40-136">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="0ef40-137">在 **"组** "页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="0ef40-137">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0ef40-138">在安全组窗格中，选择"名称"或"成员"选项卡旁边的"编辑"以编辑组详细信息或成员。 </span><span class="sxs-lookup"><span data-stu-id="0ef40-138">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="0ef40-139">进行更改后，选择"保存"" > **关闭"。**</span><span class="sxs-lookup"><span data-stu-id="0ef40-139">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="0ef40-140">删除安全组</span><span class="sxs-lookup"><span data-stu-id="0ef40-140">Delete a security group</span></span>

1. <span data-ttu-id="0ef40-141">在管理中心，转到组  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>页面。</span><span class="sxs-lookup"><span data-stu-id="0ef40-141">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="0ef40-142">在 **"组** "页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="0ef40-142">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0ef40-143">选择 **"删除 (** wasetbin"图标) ，然后选择"删除 **"进行确认**。</span><span class="sxs-lookup"><span data-stu-id="0ef40-143">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="0ef40-144">选择 **"删除** 组后关闭"。</span><span class="sxs-lookup"><span data-stu-id="0ef40-144">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="0ef40-145">Exchange Online 和 SharePoint Online 中的组</span><span class="sxs-lookup"><span data-stu-id="0ef40-145">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="0ef40-146">如果要创建用户组，以便可以同时向所有用户发送电子邮件，可以在 Exchange 管理中心中通过访问"管理 \> **Exchange** \> **收件人** 组 \> **"来这样做**。</span><span class="sxs-lookup"><span data-stu-id="0ef40-146">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="0ef40-147">接下来，**选择"新建** ![ 添加 ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) "，然后选择要创建的组类型：</span><span class="sxs-lookup"><span data-stu-id="0ef40-147">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="0ef40-148">**通讯组**：用于将邮件分发给一组用户。</span><span class="sxs-lookup"><span data-stu-id="0ef40-148">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="0ef40-149">它也称为启用邮件的  *通讯组* 或 通讯  *组列表*。</span><span class="sxs-lookup"><span data-stu-id="0ef40-149">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="0ef40-150">有关详细信息，请参阅管理 [通讯组](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)。</span><span class="sxs-lookup"><span data-stu-id="0ef40-150">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="0ef40-151">**安全组**：可用于将邮件分发给一组用户，或授予对资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0ef40-151">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="0ef40-152">此组也称为启用 *邮件的安全组*。</span><span class="sxs-lookup"><span data-stu-id="0ef40-152">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="0ef40-153">有关详细信息，请参阅[管理启用邮件的安全组](/Exchange/recipients/mail-enabled-security-groups)。</span><span class="sxs-lookup"><span data-stu-id="0ef40-153">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="0ef40-154">**动态通讯组**：一种通讯组类型，每当您基于定义的筛选器和条件发送邮件时，将重新计算收件人列表。</span><span class="sxs-lookup"><span data-stu-id="0ef40-154">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="0ef40-155">有关详细信息，请参阅 [管理动态通讯组](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)。</span><span class="sxs-lookup"><span data-stu-id="0ef40-155">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="0ef40-156">在 Exchange 管理中心创建通讯组和启用邮件的安全组后，其名称和用户列表将显示在" **安全组"** 页上。</span><span class="sxs-lookup"><span data-stu-id="0ef40-156">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="0ef40-157">您可以在这两个位置删除这些组，但是只能在 Exchange 管理中心编辑它们。</span><span class="sxs-lookup"><span data-stu-id="0ef40-157">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="0ef40-158">动态通讯组不会显示在"安全组 **"** 页上。</span><span class="sxs-lookup"><span data-stu-id="0ef40-158">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="0ef40-159">SharePoint 组是在您创建网站集时自动创建的。</span><span class="sxs-lookup"><span data-stu-id="0ef40-159">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="0ef40-160">默认组使用 SharePoint 中的默认权限级别（有时称为 SharePoint 角色）向用户授予权限和访问权限。</span><span class="sxs-lookup"><span data-stu-id="0ef40-160">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="0ef40-161">有关详细信息，请参阅 [SharePoint Online 中的默认 SharePoint 组](/sharepoint/default-sharepoint-groups)。</span><span class="sxs-lookup"><span data-stu-id="0ef40-161">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="0ef40-162">安全组与我在 SharePoint 中创建的安全组如何不同？</span><span class="sxs-lookup"><span data-stu-id="0ef40-162">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="0ef40-163">安全组可以与 SharePoint、Exchange、MDM、Windows 等一同使用。</span><span class="sxs-lookup"><span data-stu-id="0ef40-163">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="0ef40-164">在 SharePoint 中创建的安全组仅被该 SharePoint 网站集识别。</span><span class="sxs-lookup"><span data-stu-id="0ef40-164">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="0ef40-165">是否必须使用安全组以确保我的组织的安全？</span><span class="sxs-lookup"><span data-stu-id="0ef40-165">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="0ef40-166">不正确。</span><span class="sxs-lookup"><span data-stu-id="0ef40-166">No.</span></span> <span data-ttu-id="0ef40-167">这只是您可以为组织管理安全性的另外一种方法。</span><span class="sxs-lookup"><span data-stu-id="0ef40-167">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="0ef40-168">您始终可以单独授予用户权限和网站访问权限。</span><span class="sxs-lookup"><span data-stu-id="0ef40-168">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="0ef40-169">但是，使用安全组，可以轻松管理更大的用户组。</span><span class="sxs-lookup"><span data-stu-id="0ef40-169">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="0ef40-170">我能否向安全组发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="0ef40-170">Can I send email to a security group?</span></span>

<span data-ttu-id="0ef40-171">是。</span><span class="sxs-lookup"><span data-stu-id="0ef40-171">Yes.</span></span> <span data-ttu-id="0ef40-172">但是，如果你想要将组用于电子邮件和协作，我们建议你改为创建 [一个 Microsoft 365](../create-groups/create-groups.md) 组。</span><span class="sxs-lookup"><span data-stu-id="0ef40-172">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
