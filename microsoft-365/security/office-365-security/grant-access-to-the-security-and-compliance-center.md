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
description: 用户需要在 Microsoft 365 安全 & 合规性中心中分配权限，才能管理其任何安全性或合规性功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1bf8da85a0e090a9d74934ea5084f547d6a8794f
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616604"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="8e082-103">向用户授予对安全与合规中心的访问权限</span><span class="sxs-lookup"><span data-stu-id="8e082-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8e082-104">用户需要在安全 & 合规性中心中分配权限，然后才能管理其任何安全性或合规性功能。</span><span class="sxs-lookup"><span data-stu-id="8e082-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="8e082-105">作为 Security & 合规中心中的 OrganizationManagement 角色组的全局管理员或成员，您可以向用户授予这些权限。</span><span class="sxs-lookup"><span data-stu-id="8e082-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="8e082-106">用户将只能管理你授权他们访问的安全或合规性功能。</span><span class="sxs-lookup"><span data-stu-id="8e082-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="8e082-107">有关您可以向安全 & 合规中心中的用户授予的不同权限的详细信息，请查看 [安全 & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8e082-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8e082-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="8e082-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8e082-109">您必须是全局管理员，或者是 Security & 合规性中心中的 OrganizationManagement 角色组的成员，才能完成本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="8e082-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="8e082-110">Security & 合规中心的角色组可能与 Exchange Online 中的角色组具有相似的名称，但它们不是相同的。</span><span class="sxs-lookup"><span data-stu-id="8e082-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="8e082-111">角色组成员身份不在 Exchange Online 与 Security & 合规性中心之间共享。</span><span class="sxs-lookup"><span data-stu-id="8e082-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="8e082-112">委派访问权限 (通过代表 (AOBO 的管理) 合作伙伴。) 权限无法访问安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="8e082-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="8e082-113">使用安全 & 合规性中心向另一个用户授予对安全 & 合规性中心的访问权限</span><span class="sxs-lookup"><span data-stu-id="8e082-113">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="8e082-114">在上打开 "安全 & 合规中心" <https://protection.office.com> ，然后转到 " **权限**"。</span><span class="sxs-lookup"><span data-stu-id="8e082-114">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="8e082-115">若要直接转到 " **权限** " 选项卡，请打开 <https://protection.office.com/permissions> 。</span><span class="sxs-lookup"><span data-stu-id="8e082-115">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="8e082-116">从角色组列表中，选择角色组，然后单击 " **编辑** ![ 编辑图标" ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="8e082-116">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="8e082-117">在 "**成员**" 下的角色组的 "属性" 页中，单击 "**添加**" "添加 ![ " 图标， ](../../media/ITPro-EAC-AddIcon.gif) 然后选择要添加的用户的名称 (或用户) 。</span><span class="sxs-lookup"><span data-stu-id="8e082-117">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="8e082-118">在选择了要添加到角色组的所有用户后，单击 "**添加 \>** "，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="8e082-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="8e082-119">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="8e082-119">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="8e082-120">使用安全 & 合规性中心 PowerShell 向另一个用户授予对安全 & 合规性中心的访问权限</span><span class="sxs-lookup"><span data-stu-id="8e082-120">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="8e082-121">[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8e082-121">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="8e082-122">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8e082-122">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="8e082-123">有关语法和参数的详细信息，请参阅 [外接程序 add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="8e082-123">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8e082-124">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="8e082-124">How do you know this worked?</span></span>

<span data-ttu-id="8e082-125">若要验证是否已成功授予对安全 & 合规中心的访问权限，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="8e082-125">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="8e082-126">在安全 & 合规性中心中，转到 " **权限** "，然后选择角色组。</span><span class="sxs-lookup"><span data-stu-id="8e082-126">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="8e082-127">在打开的 "详细信息" 浮出控件中，验证角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="8e082-127">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="8e082-128">在安全 & 合规性中心 PowerShell 中，将替换 \<RoleGroupName\> 为角色组的名称，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8e082-128">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="8e082-129">有关语法和参数的详细信息，请参阅 [add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="8e082-129">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
