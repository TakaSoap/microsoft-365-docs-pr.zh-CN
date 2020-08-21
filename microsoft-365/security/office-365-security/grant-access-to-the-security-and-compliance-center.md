---
title: 向用户授予对安全与合规中心的访问权限
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 用户必须先在 Microsoft 365 安全 & 合规中心内分配权限，然后才能管理其任何安全或合规性功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d21fef9458c02bd09d6d5ce2129b95571e0f8371
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826597"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="d1c67-103">向用户授予对安全与合规中心的访问权限</span><span class="sxs-lookup"><span data-stu-id="d1c67-103">Give users access to the Security & Compliance Center</span></span>

<span data-ttu-id="d1c67-104">用户必须先在安全 & 合规中心内分配权限，然后才能管理其任何安全或合规性功能。</span><span class="sxs-lookup"><span data-stu-id="d1c67-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="d1c67-105">作为安全与合规中心内的 OrganizationManagement 角色组的成员 &，你可以向用户授予这些权限。</span><span class="sxs-lookup"><span data-stu-id="d1c67-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="d1c67-106">用户将只能管理你授权他们访问的安全或合规性功能。</span><span class="sxs-lookup"><span data-stu-id="d1c67-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="d1c67-107">有关您可以在安全 & 合规中心向用户授予的不同权限的详细信息，请在安全与合规[中心&查看" 权限"。](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="d1c67-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d1c67-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="d1c67-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d1c67-109">若要完成本文中的步骤，需要是全局管理员，或是安全 & 合规中心中的 OrganizationManagement 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="d1c67-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="d1c67-110">安全与合规中心&可能与 Exchange Online 中的角色组名称类似，区分不同。</span><span class="sxs-lookup"><span data-stu-id="d1c67-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="d1c67-111">Exchange Online 和安全合规性中心之间不共享&成员身份。</span><span class="sxs-lookup"><span data-stu-id="d1c67-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="d1c67-112">具有"代表 (的"管理) 的 DAP (和 DAP) 委派访问权限无法访问安全与&合规中心。</span><span class="sxs-lookup"><span data-stu-id="d1c67-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="d1c67-113">使用管理中心授予其他用户对安全合规中心&访问权限</span><span class="sxs-lookup"><span data-stu-id="d1c67-113">Use the admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="d1c67-114">[登录并转到管理中心](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="d1c67-114">[Sign in and go to the admin center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span>

2. <span data-ttu-id="d1c67-115">在 Microsoft 365 管理中心内，**打开管理中心，然后单击**"安全与 **&合规"。**</span><span class="sxs-lookup"><span data-stu-id="d1c67-115">In the Microsoft 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="d1c67-116">在安全与合 &规中心内，转到"权限 **"。**</span><span class="sxs-lookup"><span data-stu-id="d1c67-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="d1c67-117">从列表中，选择您想要向其添加用户的角色组，然后单击"编辑 **"** ![ 图标 ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="d1c67-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="d1c67-118">在"成员"下面的角色组**属性页的\*\*\*\*"添加** ![ 图标 ](../../media/ITPro-EAC-AddIcon.gif) "下，单击"添加图标"， (或要) 的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="d1c67-118">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="d1c67-119">当已选中所有想要添加到角色组的用户时，请单击"\*\*添加"， \> \*\*然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="d1c67-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="d1c67-120">单击“保存”\*\*\*\* 以保存对角色组的更改。</span><span class="sxs-lookup"><span data-stu-id="d1c67-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d1c67-121">您如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="d1c67-121">How do you know this worked?</span></span>

1. <span data-ttu-id="d1c67-122">在安全与合 &规中心内，转到"权限 **"。**</span><span class="sxs-lookup"><span data-stu-id="d1c67-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="d1c67-123">从列表中，选择要查看成员的角色组。</span><span class="sxs-lookup"><span data-stu-id="d1c67-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="d1c67-124">在右侧的角色组详细信息中，可以查看角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="d1c67-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="d1c67-125">使用 PowerShell 授予另一个用户对安全与&访问权限</span><span class="sxs-lookup"><span data-stu-id="d1c67-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="d1c67-126">[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d1c67-126">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="d1c67-127">使用 **Add-rolegroupmember** 命令将用户添加到组织管理角色，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="d1c67-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="d1c67-128">**参数**：</span><span class="sxs-lookup"><span data-stu-id="d1c67-128">**Parameters**:</span></span>

   - <span data-ttu-id="d1c67-129">_标识_ 是要向其添加成员的角色组。</span><span class="sxs-lookup"><span data-stu-id="d1c67-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="d1c67-130">_成员_ 是要添加到角色组 (，) 通用安全组"权限或计算机。</span><span class="sxs-lookup"><span data-stu-id="d1c67-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="d1c67-131">每次只能指定一个成员。</span><span class="sxs-lookup"><span data-stu-id="d1c67-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="d1c67-132">有关语法和参数的详细信息，请参阅[Add-RoleGroupMember。](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="d1c67-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d1c67-133">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="d1c67-133">How do you know this worked?</span></span>

<span data-ttu-id="d1c67-134">若要验证您已授予用户对安全 & 合规中心的访问权限，请使用 **Get-RoleGroupMember** cmdlet 查看组织管理角色组中的成员，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="d1c67-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="d1c67-135">有关语法和参数的详细信息，请参阅 [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="d1c67-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
