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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: 独立 Exchange Online Protection (EOP) 中的管理员可了解如何在 Exchange 管理中心 (EAC 中以及独立 Exchange Online Protection (EOP) PowerShell 中创建) 、修改和删除通讯组和已启用邮件的安全组。
ms.openlocfilehash: e7b93b9d05fda7e4f5f8abea02fbe3f1c70a6c74
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826549"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="44580-103">在 EOP 中管理组</span><span class="sxs-lookup"><span data-stu-id="44580-103">Manage groups in EOP</span></span>

<span data-ttu-id="44580-104">在没有 Exchange Online 邮箱的 (EOP) 独立 Exchange Online Protection 组织中，可以创建、修改和删除以下类型的组：</span><span class="sxs-lookup"><span data-stu-id="44580-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="44580-105">**通讯组**：邮件用户或其他通讯组的集合。</span><span class="sxs-lookup"><span data-stu-id="44580-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="44580-106">例如，在常见的兴趣区域，需要接收或发送电子邮件的团队或其他临时组。</span><span class="sxs-lookup"><span data-stu-id="44580-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="44580-107">通讯组专用于分发电子邮件，也不适用于安全主体 (他们无法为其分配) 。</span><span class="sxs-lookup"><span data-stu-id="44580-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="44580-108">**启用邮件的安全组**：邮件用户以及需要具有管理员角色访问权限的其他安全组的集合。</span><span class="sxs-lookup"><span data-stu-id="44580-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="44580-109">例如，您可能想向特定组的用户授予管理员权限，使他们能够配置反垃圾邮件和反恶意软件设置。</span><span class="sxs-lookup"><span data-stu-id="44580-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="44580-110">默认情况下，启用邮件的安全组拒绝来自未通过 (外部)  (的邮件。</span><span class="sxs-lookup"><span data-stu-id="44580-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="44580-111">不要将通讯组添加到已启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="44580-111">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="44580-112">可以在 EAC 管理中心和独立 EOP PowerShell)  (Exchange 管理中心中的组。</span><span class="sxs-lookup"><span data-stu-id="44580-112">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="44580-113">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="44580-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="44580-114">要打开 Exchange 管理中心，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="44580-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="44580-115">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="44580-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="44580-116">当您在独立 EOP PowerShell 中管理组时，您可能会遇到限制。</span><span class="sxs-lookup"><span data-stu-id="44580-116">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="44580-117">本主题中的 PowerShell 过程使用批处理方法，在显示命令结果之前，有几分钟的传播延迟。</span><span class="sxs-lookup"><span data-stu-id="44580-117">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="44580-118">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="44580-118">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="44580-119">具体而说，需要有"通讯组"角色，默认情况下，该角色 (分配给 全局) 管理员角色和 RecipientManagement 角色组。</span><span class="sxs-lookup"><span data-stu-id="44580-119">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="44580-120">有关详细信息，请参阅独立[EOP 中的"权限](feature-permissions-in-eop.md)["和"使用 EAC 修改角色组中的成员列表"。](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="44580-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="44580-121">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 [Exchange Online 中 Exchange 管理中心的键盘快捷键](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="44580-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="44580-122">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="44580-122">Having problems?</span></span> <span data-ttu-id="44580-123">请在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="44580-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="44580-124">使用 Exchange 管理中心管理通讯组</span><span class="sxs-lookup"><span data-stu-id="44580-124">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="44580-125">使用 EAC 创建组</span><span class="sxs-lookup"><span data-stu-id="44580-125">Use the EAC to create groups</span></span>

1. <span data-ttu-id="44580-126">在 EAC 中，转到"**收件人组** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="44580-126">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="44580-127">单击 **"新建** ![ " ](../../media/ITPro-EAC-AddIcon.png) 图标，然后选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="44580-127">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="44580-128">**通讯组**</span><span class="sxs-lookup"><span data-stu-id="44580-128">**Distribution group**</span></span>

   - <span data-ttu-id="44580-129">**启用邮件的安全组**</span><span class="sxs-lookup"><span data-stu-id="44580-129">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="44580-130">在打开的新的组页中，配置以下设置。</span><span class="sxs-lookup"><span data-stu-id="44580-130">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="44580-131">标记有需要的 <sup>\*</sup> 设置。</span><span class="sxs-lookup"><span data-stu-id="44580-131">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="44580-132"><sup>\*</sup>**显示名称**：此名称将会出现在组织的通讯簿中、电子邮件中的"收件人："行中（电子邮件发送到该组时），以及 EAC **的"组** "列表中。</span><span class="sxs-lookup"><span data-stu-id="44580-132"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="44580-133">必须显示名称是唯一的，并且应当是用户友好的，以便用户可以识别其内容。</span><span class="sxs-lookup"><span data-stu-id="44580-133">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="44580-134"><sup>\*</sup>**别名**：使用此框键入组的别名。</span><span class="sxs-lookup"><span data-stu-id="44580-134"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="44580-135">别名不能超过 64 个字符，并且必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="44580-135">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="44580-136">当用户在电子邮件的"收件人"行中键入别名时，它将解析为该组的显示名称。</span><span class="sxs-lookup"><span data-stu-id="44580-136">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="44580-137"><sup>\*</sup>**电子邮件地址**：电子邮件地址由位于 (@) 符号左侧的别名和右侧的域。</span><span class="sxs-lookup"><span data-stu-id="44580-137"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="44580-138">默认情况下， **别名值将** 用于别名值，但您可以更改它。</span><span class="sxs-lookup"><span data-stu-id="44580-138">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="44580-139">对于域值，单击下拉列表，然后选择并接受组织中接受的域。</span><span class="sxs-lookup"><span data-stu-id="44580-139">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="44580-140">**Description：** 该描述出现在通讯簿和 EAC 的"详细信息"窗格中。</span><span class="sxs-lookup"><span data-stu-id="44580-140">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="44580-141"><sup>\*</sup>**所有者：** 组所有者可以管理组成员身份。</span><span class="sxs-lookup"><span data-stu-id="44580-141"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="44580-142">默认情况下，组创建者即为组所有者。</span><span class="sxs-lookup"><span data-stu-id="44580-142">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="44580-143">所有组都必须至少有一个所有者。</span><span class="sxs-lookup"><span data-stu-id="44580-143">All groups must have at least one owner.</span></span>

     <span data-ttu-id="44580-144">若要添加所有者，请单击"**Add**添加 ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) "。</span><span class="sxs-lookup"><span data-stu-id="44580-144">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="44580-145">在出现的对话框中，找到并选择一个收件人或组，然后单击 **"添加 ->**。</span><span class="sxs-lookup"><span data-stu-id="44580-145">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="44580-146">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="44580-146">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="44580-147">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="44580-147">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="44580-148">若要删除所有者，请选择该所有者，然后单击"删除 **"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="44580-148">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="44580-149">**成员**：添加和删除组成员。</span><span class="sxs-lookup"><span data-stu-id="44580-149">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="44580-150">若要添加成员，请单击**Add**" ![ 添加"图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="44580-150">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="44580-151">在出现的对话框中，找到并选择一个收件人或组，然后单击 **"添加 ->**。</span><span class="sxs-lookup"><span data-stu-id="44580-151">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="44580-152">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="44580-152">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="44580-153">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="44580-153">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="44580-154">若要删除成员，请选择该成员，然后单击"删除 **"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="44580-154">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="44580-155">完成后，请单击 **"保存** "创建通讯组。</span><span class="sxs-lookup"><span data-stu-id="44580-155">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="44580-156">使用 EAC 修改通讯组</span><span class="sxs-lookup"><span data-stu-id="44580-156">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="44580-157">在 EAC 中，转到"**收件人组** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="44580-157">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="44580-158">在组列表中，选择要修改的通讯组或已启用邮件的安全组，然后单击"编辑 **"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="44580-158">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="44580-159">在打开的通讯组属性页面上，单击下列选项卡之一查看或更改属性。</span><span class="sxs-lookup"><span data-stu-id="44580-159">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="44580-160">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44580-160">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="44580-161">常规</span><span class="sxs-lookup"><span data-stu-id="44580-161">General</span></span>

<span data-ttu-id="44580-162">使用此选项卡可以查看或更改有关组的基本信息。</span><span class="sxs-lookup"><span data-stu-id="44580-162">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="44580-163">**显示名称**：此名称将会出现在通讯簿中、电子邮件中的"收件人"行中（电子邮件发送到该组时）以及" **组"列表中**。</span><span class="sxs-lookup"><span data-stu-id="44580-163">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="44580-164">显示名称是必需的，并且应当是用户友好的，以便用户可以识别它。</span><span class="sxs-lookup"><span data-stu-id="44580-164">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="44580-165">显示名称在域中还必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="44580-165">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="44580-166">如果您已实现了一个组命名策略，则显示名称必须符合此策略定义的命名格式。</span><span class="sxs-lookup"><span data-stu-id="44580-166">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="44580-167">**别名**：这是电子邮件地址中 (@) 符号的部分。</span><span class="sxs-lookup"><span data-stu-id="44580-167">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="44580-168">如果更改别名，组的主 SMTP 地址也会更改，并包含新的别名。</span><span class="sxs-lookup"><span data-stu-id="44580-168">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="44580-169">同时，带有之前别名的电子邮件地址将作为该组的代理地址保留。</span><span class="sxs-lookup"><span data-stu-id="44580-169">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="44580-170">**电子邮件地址**：电子邮件地址由位于 (@) 符号左侧的别名和右侧的域。</span><span class="sxs-lookup"><span data-stu-id="44580-170">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="44580-171">默认情况下， **别名值将** 用于别名值，但您可以更改它。</span><span class="sxs-lookup"><span data-stu-id="44580-171">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="44580-172">对于域值，单击下拉列表，然后选择并接受组织中接受的域。</span><span class="sxs-lookup"><span data-stu-id="44580-172">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="44580-173">**Description：** 该描述出现在通讯簿和 EAC 的"详细信息"窗格中。</span><span class="sxs-lookup"><span data-stu-id="44580-173">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="44580-174">Ownership</span><span class="sxs-lookup"><span data-stu-id="44580-174">Ownership</span></span>

<span data-ttu-id="44580-175">使用此选项卡分配组所有者。</span><span class="sxs-lookup"><span data-stu-id="44580-175">Use this tab to assign group owners.</span></span> <span data-ttu-id="44580-176">组所有者可以管理组成员身份。</span><span class="sxs-lookup"><span data-stu-id="44580-176">A group owner can manage group membership.</span></span> <span data-ttu-id="44580-177">默认情况下，组创建者即为组所有者。</span><span class="sxs-lookup"><span data-stu-id="44580-177">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="44580-178">所有组都必须至少有一个所有者。</span><span class="sxs-lookup"><span data-stu-id="44580-178">All groups must have at least one owner.</span></span>

<span data-ttu-id="44580-179">若要添加所有者，请单击"**Add**添加 ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) "。</span><span class="sxs-lookup"><span data-stu-id="44580-179">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="44580-180">在出现的对话框中，找到并选择收件人，然后单击"添加 - **显示>**。</span><span class="sxs-lookup"><span data-stu-id="44580-180">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="44580-181">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="44580-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="44580-182">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="44580-182">When you're finished, click **OK**.</span></span>

<span data-ttu-id="44580-183">若要删除所有者，请选择该所有者，然后单击"删除 **"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="44580-183">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="44580-184">成员身份</span><span class="sxs-lookup"><span data-stu-id="44580-184">Membership</span></span>

<span data-ttu-id="44580-185">使用此选项卡可以添加或删除组成员。</span><span class="sxs-lookup"><span data-stu-id="44580-185">Use this tab to add or remove group members.</span></span> <span data-ttu-id="44580-186">组所有者无需是组的成员。</span><span class="sxs-lookup"><span data-stu-id="44580-186">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="44580-187">若要添加成员，请单击**Add**" ![ 添加"图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="44580-187">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="44580-188">在出现的对话框中，找到并选择一个收件人或组，然后单击 **"添加 ->**。</span><span class="sxs-lookup"><span data-stu-id="44580-188">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="44580-189">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="44580-189">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="44580-190">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="44580-190">When you're finished, click **OK**.</span></span>

<span data-ttu-id="44580-191">若要删除成员，请选择该成员，然后单击"删除 **"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="44580-191">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="44580-192">使用 EAC 删除组</span><span class="sxs-lookup"><span data-stu-id="44580-192">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="44580-193">在 EAC 中，转到"**收件人组** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="44580-193">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="44580-194">在组列表中，选择要删除的通讯组，然后单击 **"删除** ![ "图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="44580-194">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="44580-195">使用 PowerShell 管理组</span><span class="sxs-lookup"><span data-stu-id="44580-195">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="44580-196">使用独立 EOP PowerShell 查看组</span><span class="sxs-lookup"><span data-stu-id="44580-196">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="44580-197">若要返回独立 EOP PowerShell 中所有通讯组和已启用邮件的安全组的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="44580-197">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="44580-198">若要返回组成员的列表，请 \<GroupIdentity\> 替换为组的名称、别名或电子邮件地址，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="44580-198">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="44580-199">有关语法和参数的详细信息，请参阅 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) 和 [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="44580-199">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="44580-200">使用独立 EOP PowerShell 创建组</span><span class="sxs-lookup"><span data-stu-id="44580-200">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="44580-201">若要在独立 EOP PowerShell 中创建通讯组或已启用邮件的安全组，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="44580-201">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="44580-202">**注意**：</span><span class="sxs-lookup"><span data-stu-id="44580-202">**Notes**:</span></span>

- <span data-ttu-id="44580-203">_Name 参数_必需，最大长度为 64 个字符，并且必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="44580-203">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="44580-204">如果您不使用 _DisplayName_ 参数，_Name_ 参数的值可用于显示名称。</span><span class="sxs-lookup"><span data-stu-id="44580-204">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="44580-205">如果不使用 _Alias_ 参数， _则 Name_ 参数将用于别名值。</span><span class="sxs-lookup"><span data-stu-id="44580-205">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="44580-206">删除空格，并且不受支持的字符会被转换为问号 (？) 。</span><span class="sxs-lookup"><span data-stu-id="44580-206">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="44580-207">如果不使用 _PrimarySmtpAddress 参数_ ，则在 _PrimarySmtpAddress_ 参数中使用别名值。</span><span class="sxs-lookup"><span data-stu-id="44580-207">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="44580-208">如果不使用 _Type 参数_ ，则默认值为 Distribution。</span><span class="sxs-lookup"><span data-stu-id="44580-208">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="44580-209">本示例将创建具有指定属性的名为"IT Administrators"的通讯组。</span><span class="sxs-lookup"><span data-stu-id="44580-209">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="44580-210">有关语法和参数的详细信息，请参阅[New-EOPDistributionGroup。](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)</span><span class="sxs-lookup"><span data-stu-id="44580-210">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="44580-211">使用独立 EOP PowerShell 修改组</span><span class="sxs-lookup"><span data-stu-id="44580-211">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="44580-212">若要修改独立 EOP PowerShell 中的组，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="44580-212">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="44580-213">此示例使用将主 SMTP 地址类型 ("Seattle Employees"组) 也称为"答复地址"sea.employees@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="44580-213">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="44580-214">此示例将"安全团队"组中当前成员替换为 Kitty Petersen 和 Tyson Fawcett。</span><span class="sxs-lookup"><span data-stu-id="44580-214">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="44580-215">本示例将名为"安全团队"的新用户（"Tyson Fawcettt"）添加到名为"安全团队"的组中，同时保留该组的当前成员。</span><span class="sxs-lookup"><span data-stu-id="44580-215">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="44580-216">有关语法和参数的详细信息，请参阅[Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup)和[Update-EOPDistributionGroupMember。](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="44580-216">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="44580-217">使用远程用户删除Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44580-217">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="44580-218">本示例使用了删除名为"IT 管理员"的通讯组。</span><span class="sxs-lookup"><span data-stu-id="44580-218">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="44580-219">有关语法和参数的详细信息，请参阅[Remove-EOPDistributionGroup。](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)</span><span class="sxs-lookup"><span data-stu-id="44580-219">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="44580-220">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="44580-220">How do you know these procedures worked?</span></span>

<span data-ttu-id="44580-221">若要验证是否已成功创建、修改或删除通讯组或已启用邮件的安全组，请执行以下任意步骤：</span><span class="sxs-lookup"><span data-stu-id="44580-221">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="44580-222">在 EAC 中，转到"**收件人组** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="44580-222">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="44580-223">请验证组是否已 (列出或未列出) ，并验证组 **类型值** 。</span><span class="sxs-lookup"><span data-stu-id="44580-223">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="44580-224">选择该组并在"详细信息"窗格中查看信息，或单击"编辑 **"** ![ ](../../media/ITPro-EAC-AddIcon.png) 图标查看设置。</span><span class="sxs-lookup"><span data-stu-id="44580-224">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="44580-225">在独立 EOP PowerShell 中，运行以下命令来验证该组是否已 (或未列出) ：</span><span class="sxs-lookup"><span data-stu-id="44580-225">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="44580-226">将 \<GroupIdentity\> 组的名称、别名或电子邮件地址替换，并运行以下命令来验证设置：</span><span class="sxs-lookup"><span data-stu-id="44580-226">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="44580-227">若要查看组成员， \<GroupIdentity\> 请替换为该组的名称、别名或电子邮件地址，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="44580-227">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
