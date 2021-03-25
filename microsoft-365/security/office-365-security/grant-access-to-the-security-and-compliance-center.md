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
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 用户需要在 Microsoft 365 安全与合规中心&权限，然后才能管理其任何安全或合规性功能。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 16dbbe81d1131821dfdbf75caff5b5121f8cc45b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203791"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="984f2-103">向用户授予对安全与合规中心的访问权限</span><span class="sxs-lookup"><span data-stu-id="984f2-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="984f2-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="984f2-104">**Applies to**</span></span>
- [<span data-ttu-id="984f2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="984f2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="984f2-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="984f2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="984f2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="984f2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="984f2-108">用户需要在安全与合规中心&权限，然后才能管理其任何安全或合规性功能。</span><span class="sxs-lookup"><span data-stu-id="984f2-108">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="984f2-109">作为安全与合规中心中的全局管理员或 OrganizationManagement 角色组&，你可以向用户授予这些权限。</span><span class="sxs-lookup"><span data-stu-id="984f2-109">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="984f2-110">用户将只能管理你授权他们访问的安全或合规性功能。</span><span class="sxs-lookup"><span data-stu-id="984f2-110">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="984f2-111">有关可以在安全与合规中心向用户授予的不同权限&，请查看安全与合规中心&[权限。](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="984f2-111">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="984f2-112">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="984f2-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="984f2-113">你需要是全局管理员或安全与合规中心中 OrganizationManagement 角色组&才能完成本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="984f2-113">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="984f2-114">安全与合规中心&组的名称可能类似于 Exchange Online 中的角色组，但它们不同。</span><span class="sxs-lookup"><span data-stu-id="984f2-114">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="984f2-115">角色组成员身份不会在 Exchange Online 和安全与合规中心&共享。</span><span class="sxs-lookup"><span data-stu-id="984f2-115">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="984f2-116">委派访问权限 (DAP) AOBO (AOBO) 权限无法访问安全与合规&管理。</span><span class="sxs-lookup"><span data-stu-id="984f2-116">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="984f2-117">使用安全&中心向其他用户授予对安全与合规&的访问权限</span><span class="sxs-lookup"><span data-stu-id="984f2-117">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="984f2-118">打开安全&合规中心 <https://protection.office.com> ，然后转到"**权限"。**</span><span class="sxs-lookup"><span data-stu-id="984f2-118">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="984f2-119">若要直接转到" **权限"选项卡** ，请打开 <https://protection.office.com/permissions> 。</span><span class="sxs-lookup"><span data-stu-id="984f2-119">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="984f2-120">从角色组列表中，选择角色组，然后单击"编辑 **编辑"** ![ 图标 ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="984f2-120">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="984f2-121">在角色组的属性页的"成员"下，单击"添加添加图标"，然后选择要添加 (或) ![ ](../../media/ITPro-EAC-AddIcon.gif) 用户的名称。</span><span class="sxs-lookup"><span data-stu-id="984f2-121">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="984f2-122">选择要添加到角色组的所有用户后，单击"**\> 添加**"，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="984f2-122">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="984f2-123">完成后，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="984f2-123">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="984f2-124">使用安全&合规中心 PowerShell 向其他用户授予对安全与合规&的访问权限</span><span class="sxs-lookup"><span data-stu-id="984f2-124">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="984f2-125">[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="984f2-125">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="984f2-126">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="984f2-126">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="984f2-127">有关语法和参数的详细信息，请参阅 [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="984f2-127">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="984f2-128">如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="984f2-128">How do you know this worked?</span></span>

<span data-ttu-id="984f2-129">若要验证是否成功授予了对安全与合规&访问权，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="984f2-129">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="984f2-130">在安全&中心，转到" **权限** "并选择角色组。</span><span class="sxs-lookup"><span data-stu-id="984f2-130">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="984f2-131">在打开的详细信息飞出中，验证角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="984f2-131">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="984f2-132">在安全&合规中心 PowerShell 中，将 替换为角色组 \<RoleGroupName\> 的名称，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="984f2-132">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="984f2-133">有关语法和参数的详细信息，请参阅 [Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="984f2-133">For detailed syntax and parameter information, see [Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember).</span></span>