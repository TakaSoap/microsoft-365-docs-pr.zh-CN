---
title: 创建、编辑或删除安全Microsoft 365 管理中心
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
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: 了解如何创建、编辑或删除安全组。
ms.openlocfilehash: 525acc45b293563f58bb9aa12c40bec1438cb055
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393951"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="46ce0-103">创建、编辑或删除安全Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="46ce0-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="46ce0-104">在Microsoft 365 **组**"页上，可以创建用户帐户组，这些用户帐户组可用于在 SharePoint Online 和 CRM Online 中分配相同的权限。</span><span class="sxs-lookup"><span data-stu-id="46ce0-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="46ce0-105">例如，管理员可以创建一个安全组，以向特定用户组授予对 SharePoint 网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="46ce0-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="46ce0-106">只有全局管理员和"用户管理"管理员拥有创建、编辑或删除安全组的权限；有关管理员角色的详细信息，请参阅[分配管理员角色](../add-users/assign-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="46ce0-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="46ce0-107">也存在您可以用于向用户组发送电子邮件或分配权限的 [Exchange Online 和 SharePoint Online 中的组](#groups-in-exchange-online-and-sharepoint-online)和向用户授权对网站和网站集的权限和访问权限的 [Exchange Online 和 SharePoint Online 中的组](#groups-in-exchange-online-and-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="46ce0-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="46ce0-108">计划使用网站邮箱？</span><span class="sxs-lookup"><span data-stu-id="46ce0-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="46ce0-109">通过安全组添加到 SharePoint 网站而不是单独添加的所有用户只能从 SharePoint 使用网站邮箱。</span><span class="sxs-lookup"><span data-stu-id="46ce0-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="46ce0-110">这些用户将无法从 Outlook 访问网站邮箱。</span><span class="sxs-lookup"><span data-stu-id="46ce0-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="46ce0-111">有关详细信息，请参阅 Use [Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)。</span><span class="sxs-lookup"><span data-stu-id="46ce0-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="46ce0-112">管理管理中心中的安全组</span><span class="sxs-lookup"><span data-stu-id="46ce0-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="46ce0-113">添加安全组</span><span class="sxs-lookup"><span data-stu-id="46ce0-113">Add a security group</span></span>

1. <span data-ttu-id="46ce0-114">In the Microsoft 365 管理中心， go to the **Groups**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span><span class="sxs-lookup"><span data-stu-id="46ce0-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="46ce0-115">在"**组"** 页上，选择 **"添加组"。**</span><span class="sxs-lookup"><span data-stu-id="46ce0-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="46ce0-116">在"**选择组类型"页上，** 选择"安全性 **"。**</span><span class="sxs-lookup"><span data-stu-id="46ce0-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="46ce0-117">按照步骤完成组的创建。</span><span class="sxs-lookup"><span data-stu-id="46ce0-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="46ce0-118">向安全组添加成员</span><span class="sxs-lookup"><span data-stu-id="46ce0-118">Add members to a security group</span></span>
    
1. <span data-ttu-id="46ce0-119">在"组"页上 **选择安全组** 名称，在"成员 **"选项卡上**，选择"**查看所有和管理成员"。**</span><span class="sxs-lookup"><span data-stu-id="46ce0-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="46ce0-120">在组窗格中，选择"**添加** 成员"，然后从列表中选择人员，或在"搜索"框中键入要添加的人的姓名，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="46ce0-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="46ce0-121">若要删除成员，请选择其名称旁边的 X。</span><span class="sxs-lookup"><span data-stu-id="46ce0-121">To remove members, select the X next to their name.</span></span> 
  
### <a name="edit-a-security-group"></a><span data-ttu-id="46ce0-122">编辑安全组</span><span class="sxs-lookup"><span data-stu-id="46ce0-122">Edit a security group</span></span>

1. <span data-ttu-id="46ce0-123">在管理中心，转到组 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>页面。</span><span class="sxs-lookup"><span data-stu-id="46ce0-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="46ce0-124">在 **"组** "页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="46ce0-124">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="46ce0-125">在设置窗格中，选择"常规 **"** 选项卡或" **成员** "选项卡以编辑组详细信息或成员。</span><span class="sxs-lookup"><span data-stu-id="46ce0-125">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

### <a name="delete-a-security-group"></a><span data-ttu-id="46ce0-126">删除安全组</span><span class="sxs-lookup"><span data-stu-id="46ce0-126">Delete a security group</span></span>

1. <span data-ttu-id="46ce0-127">在管理中心，转到组  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>页面。</span><span class="sxs-lookup"><span data-stu-id="46ce0-127">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="46ce0-128">在 **"组** "页上，选择组的名称。</span><span class="sxs-lookup"><span data-stu-id="46ce0-128">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="46ce0-129">选择 **"删除 (** wasetbin"图标) ，然后选择"删除 **"进行确认**。</span><span class="sxs-lookup"><span data-stu-id="46ce0-129">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="46ce0-130">选择 **"删除** 组后关闭"。</span><span class="sxs-lookup"><span data-stu-id="46ce0-130">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="46ce0-131">Exchange Online 和 SharePoint Online 中的组</span><span class="sxs-lookup"><span data-stu-id="46ce0-131">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="46ce0-132">如果要创建用户组，以便可以同时向所有用户发送电子邮件，可以在 Exchange 管理中心中通过访问"管理员 \>  \> **"Exchange"** \> **收件人组"。**</span><span class="sxs-lookup"><span data-stu-id="46ce0-132">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="46ce0-133">接下来，**选择"新建** ![ 添加 ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) "，然后选择要创建的组类型：</span><span class="sxs-lookup"><span data-stu-id="46ce0-133">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="46ce0-134">**通讯组**：用于将邮件分发给一组用户。</span><span class="sxs-lookup"><span data-stu-id="46ce0-134">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="46ce0-135">它也称为启用邮件的  *通讯组* 或 通讯  *组列表*。</span><span class="sxs-lookup"><span data-stu-id="46ce0-135">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="46ce0-136">有关详细信息，请参阅管理 [通讯组](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)。</span><span class="sxs-lookup"><span data-stu-id="46ce0-136">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="46ce0-137">**安全组**：可用于将邮件分发给一组用户，或授予对资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="46ce0-137">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="46ce0-138">此组也称为启用 *邮件的安全组*。</span><span class="sxs-lookup"><span data-stu-id="46ce0-138">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="46ce0-139">有关详细信息，请参阅[管理启用邮件的安全组](/Exchange/recipients/mail-enabled-security-groups)。</span><span class="sxs-lookup"><span data-stu-id="46ce0-139">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="46ce0-140">**动态通讯组**：一种通讯组类型，每当您基于定义的筛选器和条件发送邮件时，将重新计算收件人列表。</span><span class="sxs-lookup"><span data-stu-id="46ce0-140">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="46ce0-141">有关详细信息，请参阅 [管理动态通讯组](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)。</span><span class="sxs-lookup"><span data-stu-id="46ce0-141">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="46ce0-142">在管理中心内创建通讯组和启用邮件的安全Exchange，其名称和用户列表将显示在"安全组 **"** 页上。</span><span class="sxs-lookup"><span data-stu-id="46ce0-142">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="46ce0-143">您可以在这两个位置删除这些组，但是只能在 Exchange 管理中心编辑它们。</span><span class="sxs-lookup"><span data-stu-id="46ce0-143">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="46ce0-144">动态通讯组不会显示在"安全组 **"** 页上。</span><span class="sxs-lookup"><span data-stu-id="46ce0-144">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="46ce0-145">SharePoint 组是在您创建网站集时自动创建的。</span><span class="sxs-lookup"><span data-stu-id="46ce0-145">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="46ce0-146">默认组使用 SharePoint 中的默认权限级别（有时称为 SharePoint 角色）向用户授予权限和访问权限。</span><span class="sxs-lookup"><span data-stu-id="46ce0-146">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="46ce0-147">有关详细信息，请参阅[Default SharePoint groups in SharePoint Online。](/sharepoint/default-sharepoint-groups)</span><span class="sxs-lookup"><span data-stu-id="46ce0-147">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="46ce0-148">安全组与我在安全组中创建的安全组SharePoint？</span><span class="sxs-lookup"><span data-stu-id="46ce0-148">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="46ce0-149">安全组可以与 SharePoint、Exchange MDM、Windows 等一同使用。</span><span class="sxs-lookup"><span data-stu-id="46ce0-149">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="46ce0-150">仅在网站集中SharePoint安全组SharePoint识别。</span><span class="sxs-lookup"><span data-stu-id="46ce0-150">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="46ce0-151">是否必须使用安全组以确保我的组织的安全？</span><span class="sxs-lookup"><span data-stu-id="46ce0-151">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="46ce0-152">不正确。</span><span class="sxs-lookup"><span data-stu-id="46ce0-152">No.</span></span> <span data-ttu-id="46ce0-153">这只是您可以为组织管理安全性的另外一种方法。</span><span class="sxs-lookup"><span data-stu-id="46ce0-153">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="46ce0-154">您始终可以单独授予用户权限和网站访问权限。</span><span class="sxs-lookup"><span data-stu-id="46ce0-154">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="46ce0-155">但是，使用安全组，可以轻松管理更大的用户组。</span><span class="sxs-lookup"><span data-stu-id="46ce0-155">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="46ce0-156">我能否向安全组发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="46ce0-156">Can I send email to a security group?</span></span>

<span data-ttu-id="46ce0-157">是。</span><span class="sxs-lookup"><span data-stu-id="46ce0-157">Yes.</span></span> <span data-ttu-id="46ce0-158">但是，如果你想要将组用于电子邮件和协作，我们建议你改为创建Microsoft 365[组](../create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="46ce0-158">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 

## <a name="related-content"></a><span data-ttu-id="46ce0-159">相关内容</span><span class="sxs-lookup"><span data-stu-id="46ce0-159">Related content</span></span>

<span data-ttu-id="46ce0-160">[在本文Microsoft 365 管理中心 (](../create-groups/create-groups.md)创建) </span><span class="sxs-lookup"><span data-stu-id="46ce0-160">[Create a group in the Microsoft 365 admin center](../create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="46ce0-161">[向Microsoft 365解释组 (](../create-groups/explain-groups-knowledge-worker.md)文章) </span><span class="sxs-lookup"><span data-stu-id="46ce0-161">[Explaining Microsoft 365 Groups to your users](../create-groups/explain-groups-knowledge-worker.md) (article)</span></span>\
<span data-ttu-id="46ce0-162">[在管理组Microsoft 365 管理中心 (](../create-groups/manage-groups.md)管理) </span><span class="sxs-lookup"><span data-stu-id="46ce0-162">[Manage a group in the Microsoft 365 admin center](../create-groups/manage-groups.md) (article)</span></span>