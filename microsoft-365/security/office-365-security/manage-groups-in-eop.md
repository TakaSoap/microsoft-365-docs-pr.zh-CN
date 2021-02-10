---
title: 在 EOP 中管理组
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: 独立 Exchange Online Protection (EOP) 组织的管理员可以了解如何在 Exchange 管理中心 (EAC) 和独立 Exchange Online Protection (EOP) PowerShell 中创建、修改和删除通讯组和启用邮件的安全组。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01fe5c6ab1555749d38f9c092b05aca9befb67fe
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166959"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="b2cb4-103">在 EOP 中管理组</span><span class="sxs-lookup"><span data-stu-id="b2cb4-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b2cb4-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-104">**Applies to**</span></span>
-  [<span data-ttu-id="b2cb4-105">独立 Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b2cb4-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="b2cb4-106">在独立 Exchange Online Protection (EOP) 没有 Exchange Online 邮箱的组织，您可以创建、修改和删除以下类型的组：</span><span class="sxs-lookup"><span data-stu-id="b2cb4-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="b2cb4-107">**通讯组**：邮件用户或其他通讯组的集合。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="b2cb4-108">例如，需要在共同关注领域接收或发送电子邮件的团队或其他临时组。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="b2cb4-109">通讯组专用于分发电子邮件，并且不是安全主体 (他们无法为其分配权限) 。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="b2cb4-110">**启用邮件的安全组**：需要管理员角色访问权限的邮件用户和其他安全组的集合。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="b2cb4-111">例如，您可能希望授予特定组用户管理员权限，以便他们可以配置反垃圾邮件和反恶意软件设置。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="b2cb4-112">默认情况下，新的启用邮件的安全组拒绝来自外部 (未经身份验证) 的邮件。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="b2cb4-113">不要向启用邮件的安全组添加通讯组。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="b2cb4-114">您可以在 Exchange 管理中心和 EAC (和) EOP PowerShell 中管理组。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b2cb4-115">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="b2cb4-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b2cb4-116">若要打开 Exchange 管理中心，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="b2cb4-117">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b2cb4-118">在独立 EOP PowerShell 中管理组时，可能会遇到限制。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="b2cb4-119">本文中的 PowerShell 过程使用批处理方法，该方法在命令结果可见之前导致传播延迟几分钟。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="b2cb4-120">您需在 Exchange Online Protection 中获得权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="b2cb4-121">具体来说，您需要"**通讯组"** 角色，该角色默认分配给"组织管理"和"**收件人管理**"角色组。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="b2cb4-122">有关详细信息，请参阅独立 [EOP 中的权限](feature-permissions-in-eop.md) 和使用 [EAC 修改角色组的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="b2cb4-123">有关可能适用于本文中的过程的键盘快捷方式的信息，请参阅 Exchange Online 中 [Exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="b2cb4-124">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="b2cb4-124">Having problems?</span></span> <span data-ttu-id="b2cb4-125">请在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-125">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="b2cb4-126">使用 Exchange 管理中心管理通讯组</span><span class="sxs-lookup"><span data-stu-id="b2cb4-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="b2cb4-127">使用 EAC 创建组</span><span class="sxs-lookup"><span data-stu-id="b2cb4-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="b2cb4-128">在 EAC 中，转到 **"收件人** \> **组"。**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="b2cb4-129">单击 **"** ![ 新建" ](../../media/ITPro-EAC-AddIcon.png) 图标，然后选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b2cb4-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="b2cb4-130">**通讯组**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-130">**Distribution group**</span></span>

   - <span data-ttu-id="b2cb4-131">**启用邮件的安全组**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="b2cb4-132">在打开的新组页中，配置以下设置。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="b2cb4-133">标有 an <sup>\*</sup> 的设置是必需的。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="b2cb4-134"><sup>\*</sup>**显示名称**：此名称将出现在组织的通讯簿中、电子邮件发送到该组时位于"To："行上以及 EAC 中的"组"列表中。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="b2cb4-135">此显示名称是必需的，必须是唯一的，并且应该用户友好，以便用户能够识别它。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="b2cb4-136"><sup>\*</sup>**别名**：使用此框键入组的别名。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="b2cb4-137">别名不能超过 64 个字符，并且必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="b2cb4-138">当用户在电子邮件的"收件人"行中输入别名时，它将解析为组的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="b2cb4-139"><sup>\*</sup>**电子邮件地址：** 电子邮件地址由 @ (@) 符号左侧的别名和右侧域组成。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="b2cb4-140">默认情况下， **别名** 的值用于别名值，但您可以更改它。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="b2cb4-141">对于域值，单击下拉列表并选择和接受您组织的域。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="b2cb4-142">**说明**：此说明出现在通讯簿和 EAC 的"详细信息"窗格中。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="b2cb4-143"><sup>\*</sup>**所有者**：组所有者可以管理组成员身份。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="b2cb4-144">默认情况下，组创建者即为组所有者。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="b2cb4-145">所有组都必须至少有一个所有者。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="b2cb4-146">若要添加所有者，请单击 **"添加"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="b2cb4-147">在出现的对话框中，查找并选择收件人或组，然后单击 **"添加>。**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="b2cb4-148">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="b2cb4-149">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="b2cb4-150">若要删除所有者，请选择所有者，然后单击"删除 **"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="b2cb4-151">**Members**： Add and remove group members.</span><span class="sxs-lookup"><span data-stu-id="b2cb4-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="b2cb4-152">若要添加成员，请单击 **"添加"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="b2cb4-153">在出现的对话框中，查找并选择收件人或组，然后单击 **"添加>。**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="b2cb4-154">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="b2cb4-155">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="b2cb4-156">若要删除成员，请选择该成员，然后单击" **删除"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="b2cb4-157">完成后，单击"保存"创建通讯组。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="b2cb4-158">使用 EAC 修改通讯组</span><span class="sxs-lookup"><span data-stu-id="b2cb4-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="b2cb4-159">在 EAC 中，转到 **"收件人** \> **组"。**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="b2cb4-160">在组列表中，选择要修改的通讯组或启用邮件的安全组，然后单击"编辑 ![ 编辑"图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="b2cb4-161">在打开的通讯组属性页上，单击以下选项卡之一以查看或更改属性。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="b2cb4-162">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="b2cb4-163">常规</span><span class="sxs-lookup"><span data-stu-id="b2cb4-163">General</span></span>

<span data-ttu-id="b2cb4-164">使用此选项卡可以查看或更改有关组的基本信息。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="b2cb4-165">**显示名称**：此名称显示在通讯簿中、电子邮件发送到该组时，在"接收"行上以及"组 **"列表中**。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="b2cb4-166">显示名称是必需的，并且应当是用户友好的，以便用户可以识别它。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="b2cb4-167">显示名称在域中还必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="b2cb4-168">如果您已实现了一个组命名策略，则显示名称必须符合此策略定义的命名格式。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="b2cb4-169">**别名**：这是电子邮件地址的一部分，显示在 (@) 符号的左侧。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="b2cb4-170">如果更改别名，组的主 SMTP 地址也会更改，并包含新的别名。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="b2cb4-171">同时，带有之前别名的电子邮件地址将作为该组的代理地址保留。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="b2cb4-172">**电子邮件地址：** 电子邮件地址由 @ (@) 符号左侧的别名和右侧域组成。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="b2cb4-173">默认情况下， **别名** 的值用于别名值，但您可以更改它。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="b2cb4-174">对于域值，单击下拉列表并选择和接受您组织的域。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="b2cb4-175">**说明**：此说明出现在通讯簿和 EAC 的"详细信息"窗格中。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="b2cb4-176">Ownership</span><span class="sxs-lookup"><span data-stu-id="b2cb4-176">Ownership</span></span>

<span data-ttu-id="b2cb4-177">使用此选项卡可分配组所有者。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="b2cb4-178">组所有者可以管理组成员身份。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-178">A group owner can manage group membership.</span></span> <span data-ttu-id="b2cb4-179">默认情况下，组创建者即为组所有者。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="b2cb4-180">所有组都必须至少有一个所有者。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="b2cb4-181">若要添加所有者，请单击 **"添加"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="b2cb4-182">在出现的对话框中，查找并选择收件人，然后单击 **"添加->"。**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="b2cb4-183">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="b2cb4-184">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="b2cb4-185">若要删除所有者，请选择所有者，然后单击"删除 **"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="b2cb4-186">成员身份</span><span class="sxs-lookup"><span data-stu-id="b2cb4-186">Membership</span></span>

<span data-ttu-id="b2cb4-187">使用此选项卡可以添加或删除组的成员。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="b2cb4-188">组所有者不需要是组的成员。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="b2cb4-189">若要添加成员，请单击 **"添加"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="b2cb4-190">在出现的对话框中，查找并选择收件人或组，然后单击 **"添加>。**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="b2cb4-191">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="b2cb4-192">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="b2cb4-193">若要删除成员，请选择该成员，然后单击" **删除"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="b2cb4-194">使用 EAC 删除组</span><span class="sxs-lookup"><span data-stu-id="b2cb4-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="b2cb4-195">在 EAC 中，转到 **"收件人** \> **组"。**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="b2cb4-196">在组列表中，选择要删除的通讯组，然后单击"删除 **删除"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="b2cb4-197">使用 PowerShell 管理组</span><span class="sxs-lookup"><span data-stu-id="b2cb4-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="b2cb4-198">使用独立 EOP PowerShell 查看组</span><span class="sxs-lookup"><span data-stu-id="b2cb4-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="b2cb4-199">若要返回独立 EOP PowerShell 中所有通讯组和启用邮件的安全组的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b2cb4-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="b2cb4-200">若要返回组的成员列表，请替换为组的名称、别名或电子邮件地址，然后 \<GroupIdentity\> 运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b2cb4-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="b2cb4-201">有关语法和参数的详细信息，请参阅[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient)和[Get-DistributionGroupMember。](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="b2cb4-201">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="b2cb4-202">使用独立 EOP PowerShell 创建组</span><span class="sxs-lookup"><span data-stu-id="b2cb4-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="b2cb4-203">若要在独立 EOP PowerShell 中创建通讯组或启用邮件的安全组，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="b2cb4-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="b2cb4-204">**注意**：</span><span class="sxs-lookup"><span data-stu-id="b2cb4-204">**Notes**:</span></span>

- <span data-ttu-id="b2cb4-205">_Name_ 参数是必需的，最大长度为 64 个字符，并且必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="b2cb4-206">如果您不使用 _DisplayName_ 参数，_Name_ 参数的值可用于显示名称。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="b2cb4-207">如果不使用 Alias 参数， _则_ _Name_ 参数用于别名值。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="b2cb4-208">空格将被删除，不受支持的字符将转换为问号 (？) 。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="b2cb4-209">如果不使用 _PrimarySmtpAddress_ 参数，则别名值在 _PrimarySmtpAddress_ 参数中使用。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="b2cb4-210">如果不使用 _Type_ 参数，则默认值为 Distribution。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="b2cb4-211">此示例创建一个名为 IT Administrators 的通讯组，该组具有指定的属性。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="b2cb4-212">有关语法和参数的详细信息，请参阅[New-EOPDistributionGroup。](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)</span><span class="sxs-lookup"><span data-stu-id="b2cb4-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="b2cb4-213">使用独立 EOP PowerShell 修改组</span><span class="sxs-lookup"><span data-stu-id="b2cb4-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="b2cb4-214">若要在独立 EOP PowerShell 中修改组，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="b2cb4-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="b2cb4-215">此示例使用更改主 SMTP 地址 (也称为答复地址) Seattle Employees 组更改sea.employees@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="b2cb4-216">本示例将安全团队组的当前成员替换为 Kitty Petersen 和 Tyson Fawcett。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="b2cb4-217">本示例将名为 Tyson Fawcett 的新用户添加到名为"安全团队"的组中，同时保留该组的当前成员。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="b2cb4-218">有关语法和参数的详细信息，请参阅[Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup)和[Update-EOPDistributionGroupMember。](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="b2cb4-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b2cb4-219">使用远程客户端删除Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2cb4-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b2cb4-220">此示例使用删除名为"IT 管理员"的通讯组。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="b2cb4-221">有关语法和参数的详细信息，请参阅[Remove-EOPDistributionGroup。](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)</span><span class="sxs-lookup"><span data-stu-id="b2cb4-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b2cb4-222">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="b2cb4-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="b2cb4-223">若要验证您是否已成功创建、修改或删除通讯组或启用邮件的安全组，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="b2cb4-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="b2cb4-224">在 EAC 中，转到 **"收件人** \> **组"。**</span><span class="sxs-lookup"><span data-stu-id="b2cb4-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="b2cb4-225">验证组是否 (列出) ，并验证组 **类型** 值。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="b2cb4-226">选择组并查看详细信息窗格中的信息，或单击"编辑编辑" ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 查看设置。</span><span class="sxs-lookup"><span data-stu-id="b2cb4-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="b2cb4-227">在独立 EOP PowerShell 中，运行以下命令，验证组是否 (列出) ：</span><span class="sxs-lookup"><span data-stu-id="b2cb4-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="b2cb4-228">替换为组的名称、别名或电子邮件地址，并 \<GroupIdentity\> 运行以下命令来验证设置：</span><span class="sxs-lookup"><span data-stu-id="b2cb4-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="b2cb4-229">若要查看这些组的成员，请替换为组的名称、别名或电子邮件地址， \<GroupIdentity\> 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b2cb4-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
