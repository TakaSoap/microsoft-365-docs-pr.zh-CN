---
title: 在 EOP 中管理角色组
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 管理员可以了解如何在 Exchange Online Protection 中的 Exchange 管理中心 (EAC) 权限。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce272985f195f44c57848e6861cefb64431698b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289921"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="9e569-103">在独立 EOP 中管理角色组</span><span class="sxs-lookup"><span data-stu-id="9e569-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9e569-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="9e569-104">**Applies to**</span></span>
-  [<span data-ttu-id="9e569-105">独立 Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9e569-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="9e569-106">在独立 Exchange Online Protection (EOP) 组织中，可以使用 Exchange 管理中心 (EAC) 将用户添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="9e569-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="9e569-107">向角色组添加用户会授予用户执行特定管理任务的权限。</span><span class="sxs-lookup"><span data-stu-id="9e569-107">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="9e569-108">还可以从角色组中删除用户。</span><span class="sxs-lookup"><span data-stu-id="9e569-108">You can also remove users from role groups.</span></span>

<span data-ttu-id="9e569-109">有关角色和角色组的信息，请参阅独立 [EOP 中的权限](feature-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="9e569-109">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9e569-110">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="9e569-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9e569-111">若要打开 Exchange 管理中心 (EAC) ，请参阅独立 [EOP](exchange-admin-center-in-exchange-online-protection-eop.md)中的 Exchange 管理中心。</span><span class="sxs-lookup"><span data-stu-id="9e569-111">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="9e569-112">若要打开独立 EOP PowerShell，请参阅["连接到 Exchange Online Protection PowerShell"。](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="9e569-112">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9e569-113">您需要在 Exchange Online Protection 中分配权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="9e569-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="9e569-114">具体而言，您需要角色 **管理** 角色，默认情况下，角色管理角色分配给 **组织管理** 角色组。</span><span class="sxs-lookup"><span data-stu-id="9e569-114">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="9e569-115">有关详细信息，请参阅独立 [EOP 中](feature-permissions-in-eop.md) 的权限和使用 [EAC 修改角色组的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="9e569-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="9e569-116">有关可能适用于本文中的过程的键盘快捷方式的信息，请参阅 Exchange Online 中 [Exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="9e569-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="9e569-117">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="9e569-117">Having problems?</span></span> <span data-ttu-id="9e569-118">请在 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="9e569-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="9e569-119">使用 EAC 管理角色组</span><span class="sxs-lookup"><span data-stu-id="9e569-119">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="9e569-120">使用 EAC 查看角色组</span><span class="sxs-lookup"><span data-stu-id="9e569-120">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="9e569-121">在 EAC 中，转到 **"权限** \> **管理员"角色**。</span><span class="sxs-lookup"><span data-stu-id="9e569-121">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="9e569-122">这里列出了你组织中的所有角色组。</span><span class="sxs-lookup"><span data-stu-id="9e569-122">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="9e569-123">选择角色组。</span><span class="sxs-lookup"><span data-stu-id="9e569-123">Select a role group.</span></span> <span data-ttu-id="9e569-124">"详细信息"窗格显示 **角色组的名称**、说明、分配的角色和管理。 </span><span class="sxs-lookup"><span data-stu-id="9e569-124">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="9e569-125">您还可以通过单击"编辑编辑" **图标来查看** ![ 此信息 ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-125">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="9e569-126">使用 EAC 创建角色组</span><span class="sxs-lookup"><span data-stu-id="9e569-126">Use the EAC to create role groups</span></span>

<span data-ttu-id="9e569-127">创建新的角色组时，可以在组创建期间或 (配置所有设置) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-127">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="9e569-128">或者，您可以复制并修改现有角色组。</span><span class="sxs-lookup"><span data-stu-id="9e569-128">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="9e569-129">在 EAC 中，转到 **"权限** \> **管理员**"角色，然后执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="9e569-129">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="9e569-130">**手动创建新角色组**：单击 **"添加"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-130">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="9e569-131">**复制现有角色组**：选择要复制的角色组，然后单击"复制 **复制"** ![ 图标 ](../../media/ITPro-EAC-CopyIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-131">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="9e569-132">在 **出现的"新建角色组** "窗口中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="9e569-132">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="9e569-133">**名称**：输入角色组的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="9e569-133">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="9e569-134">**说明**：输入角色组的可选说明。</span><span class="sxs-lookup"><span data-stu-id="9e569-134">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="9e569-135">**角色**：单击 **"添加** ![ "图标或"删除删除"图标以选择或修改分配给角色 ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 组的角色。</span><span class="sxs-lookup"><span data-stu-id="9e569-135">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="9e569-136">**成员**：单击 **"** ![ 添加" ](../../media/ITPro-EAC-AddIcon.png) 图标 **或"** 删除 ![ 删除"图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 以修改角色组成员身份。</span><span class="sxs-lookup"><span data-stu-id="9e569-136">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="9e569-137">完成后，单击"保存"以创建角色组。</span><span class="sxs-lookup"><span data-stu-id="9e569-137">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="9e569-138">使用 EAC 修改角色组</span><span class="sxs-lookup"><span data-stu-id="9e569-138">Use the EAC to modify role groups</span></span>

<span data-ttu-id="9e569-139">在 EAC 中，转到 **"权限** 管理员角色"，选择要修改的角色组， \> 然后单击"编辑 **编辑"** ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-139">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="9e569-140">修改角色组时可用的选项与创建角色组时相同。</span><span class="sxs-lookup"><span data-stu-id="9e569-140">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="9e569-141">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9e569-141">You can:</span></span>

- <span data-ttu-id="9e569-142">更改名称和说明。</span><span class="sxs-lookup"><span data-stu-id="9e569-142">Change the name and description.</span></span>

- <span data-ttu-id="9e569-143">添加和删除管理 (角色分配) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-143">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="9e569-144">添加和删除成员。</span><span class="sxs-lookup"><span data-stu-id="9e569-144">Add and remove members.</span></span>

<span data-ttu-id="9e569-145">**注意**：某些角色 (例如，组织) 限制可以从组中删除的角色。</span><span class="sxs-lookup"><span data-stu-id="9e569-145">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="9e569-146">使用 EAC 修改角色组的成员列表</span><span class="sxs-lookup"><span data-stu-id="9e569-146">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="9e569-147">在 EAC 中，转到 **"权限** 管理员角色"，选择要修改的角色组， \> 然后单击"编辑 ![ 编辑"图标 ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-147">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="9e569-148">在打开的角色组属性页的 **"成员** "部分中，执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="9e569-148">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="9e569-149">单击 **"添加** ![ "图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-149">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="9e569-150">在出现的页面中，找到要添加的用户，然后单击"添加 **>。**</span><span class="sxs-lookup"><span data-stu-id="9e569-150">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="9e569-151">选择 **用户并根据需要** >多次添加 ->。</span><span class="sxs-lookup"><span data-stu-id="9e569-151">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="9e569-152">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="9e569-152">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="9e569-153">选择要删除的用户，然后单击"删除 **"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-153">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="9e569-154">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="9e569-154">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9e569-155">在角色组中添加或删除成员后，用户可能必须先注销，然后重新登录才会看到其管理权限的更改。</span><span class="sxs-lookup"><span data-stu-id="9e569-155">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="9e569-156">使用 EAC 删除角色组</span><span class="sxs-lookup"><span data-stu-id="9e569-156">Use the EAC to remove role groups</span></span>

<span data-ttu-id="9e569-157">不能删除内置角色组，但可以删除已创建的自定义角色组。</span><span class="sxs-lookup"><span data-stu-id="9e569-157">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="9e569-158">在 EAC 中，转到 **"权限** \> **管理员"角色**。</span><span class="sxs-lookup"><span data-stu-id="9e569-158">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="9e569-159">选择要删除的角色组，然后单击" **删除"** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-159">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="9e569-160">在 **出现的** 确认窗口中单击"是"。</span><span class="sxs-lookup"><span data-stu-id="9e569-160">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="9e569-161">使用 PowerShell 管理角色组</span><span class="sxs-lookup"><span data-stu-id="9e569-161">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="9e569-162">使用独立 EOP PowerShell 查看角色组</span><span class="sxs-lookup"><span data-stu-id="9e569-162">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="9e569-163">若要查看角色组，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="9e569-163">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="9e569-164">此示例返回所有角色组的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="9e569-164">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="9e569-165">此示例返回名为"收件人管理员"的角色组的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9e569-165">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="9e569-166">本示例返回用户 Julia 是成员的所有角色组。</span><span class="sxs-lookup"><span data-stu-id="9e569-166">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="9e569-167">需要为 Julia 使用 DistinguishedName (DN) 值，可通过运行以下命令找到该值 `Get-User -Identity Julia | Format-List DistinguishedName` ：</span><span class="sxs-lookup"><span data-stu-id="9e569-167">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="9e569-168">有关详细的语法和参数信息，请参阅 [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)。</span><span class="sxs-lookup"><span data-stu-id="9e569-168">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="9e569-169">使用独立 EOP PowerShell 创建角色组</span><span class="sxs-lookup"><span data-stu-id="9e569-169">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="9e569-170">创建新的角色组时，可以在组创建期间或 (配置所有设置) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-170">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="9e569-171">或者，您可以复制并修改现有角色组。</span><span class="sxs-lookup"><span data-stu-id="9e569-171">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="9e569-172">若要手动创建新角色组，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="9e569-172">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="9e569-173">_Roles_ 参数通过以下语法指定要分配给角色组的管理角色 `"Role1","Role1",..."RoleN"` 。</span><span class="sxs-lookup"><span data-stu-id="9e569-173">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="9e569-174">可以使用 **Get-ManagementRole** cmdlet 查看可用角色。</span><span class="sxs-lookup"><span data-stu-id="9e569-174">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="9e569-175">_Members_ 参数使用以下语法指定角色组 `"Member1","Member2",..."MemberN"` 的成员：</span><span class="sxs-lookup"><span data-stu-id="9e569-175">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="9e569-176">可以指定用户、启用邮件的通用安全组 (USG) 或其他角色组 (安全) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-176">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="9e569-177">此示例创建一个名为"有限收件人管理"的新角色组，该角色组具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="9e569-177">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="9e569-178">将为角色组分配 Mail Recipients 角色。</span><span class="sxs-lookup"><span data-stu-id="9e569-178">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="9e569-179">用户 Kim 和 Martin 将添加为成员。</span><span class="sxs-lookup"><span data-stu-id="9e569-179">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="9e569-180">若要复制现有角色组，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="9e569-180">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="9e569-181">请使用以下语法将想要复制的角色组存储在变量中：</span><span class="sxs-lookup"><span data-stu-id="9e569-181">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="9e569-182">使用以下语法创建新的角色组：</span><span class="sxs-lookup"><span data-stu-id="9e569-182">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="9e569-183">_Members_ 参数使用以下语法指定角色组 `"Member1","Member2",..."MemberN"` 的成员：</span><span class="sxs-lookup"><span data-stu-id="9e569-183">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="9e569-184">可以指定用户、启用邮件的通用安全组 (USG) 或其他角色组 (安全) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-184">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="9e569-185">本示例将组织管理角色组复制到名为"Limited Organization Management"的新角色组。</span><span class="sxs-lookup"><span data-stu-id="9e569-185">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="9e569-186">角色组的成员是 Isab、Carter 和 Lukas。</span><span class="sxs-lookup"><span data-stu-id="9e569-186">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="9e569-187">有关语法和参数的详细信息，[请参阅 New-RoleGroup。](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="9e569-187">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="9e569-188">使用独立的 EOP PowerShell 修改角色组的成员列表</span><span class="sxs-lookup"><span data-stu-id="9e569-188">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="9e569-189">**Add-RoleGroupMember** 和 **Remove-RoleGroupMember** cmdlet 一次添加或删除一个成员。</span><span class="sxs-lookup"><span data-stu-id="9e569-189">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="9e569-190">**Update-RoleGroupMember** cmdlet 可以替换或修改现有成员列表。</span><span class="sxs-lookup"><span data-stu-id="9e569-190">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="9e569-191">角色组的成员可以是用户、启用邮件的通用安全组 (USG) 或其他角色组 (安全) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-191">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="9e569-192">若要修改角色组的成员，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="9e569-192">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="9e569-193">若要 _将_ 现有的成员列表替换为您指定的值，请使用以下 `"Member1","Member2",..."MemberN"` 语法：</span><span class="sxs-lookup"><span data-stu-id="9e569-193">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="9e569-194">若要 _有选择地修改_ 现有成员列表，请使用以下 `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` 语法：</span><span class="sxs-lookup"><span data-stu-id="9e569-194">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="9e569-195">本示例将技术支持角色组的所有当前成员替换为指定的用户。</span><span class="sxs-lookup"><span data-stu-id="9e569-195">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="9e569-196">此示例将添加一个一代，并从 Help Desk 角色组的成员列表中删除一个。</span><span class="sxs-lookup"><span data-stu-id="9e569-196">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="9e569-197">有关语法和参数的详细信息，请参阅 [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="9e569-197">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="9e569-198">使用独立 EOP PowerShell 删除角色组</span><span class="sxs-lookup"><span data-stu-id="9e569-198">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="9e569-199">不能删除内置角色组，但可以删除已创建的自定义角色组。</span><span class="sxs-lookup"><span data-stu-id="9e569-199">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="9e569-200">若要删除自定义角色组，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="9e569-200">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="9e569-201">本示例将删除 Training Administrators 角色组。</span><span class="sxs-lookup"><span data-stu-id="9e569-201">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="9e569-202">有关语法和参数的详细信息，请参阅 [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)。</span><span class="sxs-lookup"><span data-stu-id="9e569-202">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9e569-203">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="9e569-203">How do you know these procedures worked?</span></span>

<span data-ttu-id="9e569-204">若要验证是否成功复制了角色组，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="9e569-204">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="9e569-205">在 EAC 中，转到 **"权限** 管理员"角色，并验证角色组是否 (\> 列出) 。</span><span class="sxs-lookup"><span data-stu-id="9e569-205">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="9e569-206">选择角色组，然后验证"详细信息"窗格中的设置 **或单击"** 编辑编辑"图标 ![ ](../../media/ITPro-EAC-EditIcon.png) 以验证设置。</span><span class="sxs-lookup"><span data-stu-id="9e569-206">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="9e569-207">在 Exchange Online PowerShell 中，替换为角色组的名称，并运行以下命令来验证角色组是否存在 (或不存在) 验证 \<Role Group Name\> 设置：</span><span class="sxs-lookup"><span data-stu-id="9e569-207">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
