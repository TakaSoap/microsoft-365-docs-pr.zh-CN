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
ms.openlocfilehash: 9e19825ce0f8224b2aee8e1419ef5d1ad425aadb
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165411"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="09bd8-103">向用户授予对安全与合规中心的访问权限</span><span class="sxs-lookup"><span data-stu-id="09bd8-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="09bd8-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="09bd8-104">**Applies to**</span></span>
- [<span data-ttu-id="09bd8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="09bd8-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="09bd8-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="09bd8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="09bd8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09bd8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="09bd8-108">用户需要在安全与合规中心&权限，然后才能管理其任何安全或合规性功能。</span><span class="sxs-lookup"><span data-stu-id="09bd8-108">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="09bd8-109">作为安全与合规中心内 OrganizationManagement 角色组&全局管理员或成员，你可以向用户授予这些权限。</span><span class="sxs-lookup"><span data-stu-id="09bd8-109">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="09bd8-110">用户将只能管理你授权他们访问的安全或合规性功能。</span><span class="sxs-lookup"><span data-stu-id="09bd8-110">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="09bd8-111">有关可以授予安全与合规中心用户的不同权限&，请查看安全与合规中心& [权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="09bd8-111">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="09bd8-112">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="09bd8-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="09bd8-113">你需要是全局管理员或安全与合规中心内 OrganizationManagement 角色组&才能完成本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="09bd8-113">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="09bd8-114">安全与合规中心&组的名称可能类似于 Exchange Online 中的角色组，但它们不同。</span><span class="sxs-lookup"><span data-stu-id="09bd8-114">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="09bd8-115">Exchange Online 与安全与合规中心之间不&成员身份。</span><span class="sxs-lookup"><span data-stu-id="09bd8-115">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="09bd8-116">委派访问权限 (DAP) 代表管理 (AOBO) 合作伙伴无法访问安全与合规&中心。</span><span class="sxs-lookup"><span data-stu-id="09bd8-116">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="09bd8-117">使用安全&合规中心向其他用户授予对安全与合规&的访问权限</span><span class="sxs-lookup"><span data-stu-id="09bd8-117">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="09bd8-118">打开安全& <https://protection.office.com> 合规中心，然后转到 **"权限"。**</span><span class="sxs-lookup"><span data-stu-id="09bd8-118">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="09bd8-119">若要直接转到" **权限"** 选项卡，请打开 <https://protection.office.com/permissions> 。</span><span class="sxs-lookup"><span data-stu-id="09bd8-119">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="09bd8-120">从角色组列表中，选择角色组，然后单击"编辑 **编辑"** ![ 图标 ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="09bd8-120">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="09bd8-121">在角色组的属性页的 **"** 成员"下，单击"添加图标"，然后选择要添加 (或) ![ ](../../media/ITPro-EAC-AddIcon.gif) 用户的名称。</span><span class="sxs-lookup"><span data-stu-id="09bd8-121">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="09bd8-122">选择要添加到角色 **\>** 组的所有用户后，单击"添加"，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="09bd8-122">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="09bd8-123">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="09bd8-123">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="09bd8-124">使用安全&合规中心 PowerShell 为其他用户授予对安全与合规&的访问权限</span><span class="sxs-lookup"><span data-stu-id="09bd8-124">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="09bd8-125">[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="09bd8-125">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="09bd8-126">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="09bd8-126">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="09bd8-127">有关语法和参数的详细信息，请参阅 [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="09bd8-127">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="09bd8-128">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="09bd8-128">How do you know this worked?</span></span>

<span data-ttu-id="09bd8-129">若要验证您是否已成功授予对安全与合规中心&访问权限，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="09bd8-129">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="09bd8-130">在安全&合规中心，转到 **"权限** "并选择角色组。</span><span class="sxs-lookup"><span data-stu-id="09bd8-130">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="09bd8-131">在打开的详细信息飞出中，验证角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="09bd8-131">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="09bd8-132">在安全&合规中心 PowerShell 中，替换为角色组 \<RoleGroupName\> 的名称，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="09bd8-132">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="09bd8-133">有关语法和参数的详细信息，请参阅[Get-RoleGroupMember。](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="09bd8-133">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
