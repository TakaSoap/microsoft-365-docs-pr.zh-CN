---
title: 在 EOP 中管理组
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: 独立 Exchange Online Protection （EOP）组织中的管理员可以了解如何在 Exchange 管理中心（EAC）和独立 Exchange Online Protection （EOP） PowerShell 中创建、修改和删除通讯组和启用邮件的安全组。
ms.openlocfilehash: 4f1dbdb503f8baf02b7dd763dbf7fc6acdf5771a
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352187"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="66308-103">在 EOP 中管理组</span><span class="sxs-lookup"><span data-stu-id="66308-103">Manage groups in EOP</span></span>

<span data-ttu-id="66308-104">在独立的 Exchange Online Protection （EOP）组织中，如果没有 Exchange Online 邮箱，您可以创建、修改和删除以下类型的组：</span><span class="sxs-lookup"><span data-stu-id="66308-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="66308-105">**通讯组**：邮件用户或其他通讯组的集合。</span><span class="sxs-lookup"><span data-stu-id="66308-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="66308-106">例如，需要在感兴趣的公共领域接收或发送电子邮件的团队或其他临时组。</span><span class="sxs-lookup"><span data-stu-id="66308-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="66308-107">通讯组专门用于分发电子邮件，而不是安全主体（他们不能向其分配权限）。</span><span class="sxs-lookup"><span data-stu-id="66308-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="66308-108">**启用邮件的安全组**：邮件用户和其他需要管理员角色访问权限的安全组的集合。</span><span class="sxs-lookup"><span data-stu-id="66308-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="66308-109">例如，您可能希望向特定用户组授予管理员权限，以便他们可以配置反垃圾邮件和反恶意软件设置。</span><span class="sxs-lookup"><span data-stu-id="66308-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <ul><li><span data-ttu-id="66308-110">默认情况下，启用邮件的新安全组拒绝来自外部（未经身份验证的）发件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="66308-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span></li><li><span data-ttu-id="66308-111">不向启用邮件的安全组添加通讯组。</span><span class="sxs-lookup"><span data-stu-id="66308-111">Don't add distribution groups to mail-enabled security groups.</span></span></li></ul><span data-ttu-id="66308-112">.</span><span class="sxs-lookup"><span data-stu-id="66308-112">.</span></span>

<span data-ttu-id="66308-113">您可以在 Exchange 管理中心（EAC）和独立 EOP PowerShell 中管理组。</span><span class="sxs-lookup"><span data-stu-id="66308-113">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="66308-114">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="66308-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="66308-115">若要打开 Exchange 管理中心，请参阅[独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="66308-115">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="66308-116">若要连接到独立的 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="66308-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="66308-117">当您在独立 EOP PowerShell 中管理组时，您可能会遇到限制。</span><span class="sxs-lookup"><span data-stu-id="66308-117">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="66308-118">本主题中的 PowerShell 过程使用一种批处理方法，该方法会导致在几分钟内发生传播延迟，然后才能看到命令的结果。</span><span class="sxs-lookup"><span data-stu-id="66308-118">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="66308-119">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="66308-119">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="66308-120">具体来说，您需要 "通讯组" 角色，默认情况下该角色分配给 OrganizationManagement （全局管理员）和 RecipientManagement 角色组。</span><span class="sxs-lookup"><span data-stu-id="66308-120">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="66308-121">有关详细信息，请参阅[独立 EOP 中的权限](feature-permissions-in-eop.md)和[使用 EAC 修改角色组中的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="66308-121">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="66308-122">有关可能适用于本主题中的过程的键盘快捷方式的信息，请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="66308-122">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="66308-123">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="66308-123">Having problems?</span></span> <span data-ttu-id="66308-124">在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="66308-124">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="66308-125">使用 Exchange 管理中心管理通讯组</span><span class="sxs-lookup"><span data-stu-id="66308-125">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="66308-126">使用 EAC 创建组</span><span class="sxs-lookup"><span data-stu-id="66308-126">Use the EAC to create groups</span></span>

1. <span data-ttu-id="66308-127">在 EAC 中，转到 "**收件人** \> **组**"。</span><span class="sxs-lookup"><span data-stu-id="66308-127">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="66308-128">单击 "**新建** ![ 新图标 ](../../media/ITPro-EAC-AddIcon.png) "，然后选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="66308-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="66308-129">**通讯组**</span><span class="sxs-lookup"><span data-stu-id="66308-129">**Distribution group**</span></span>

   - <span data-ttu-id="66308-130">**启用邮件的安全组**</span><span class="sxs-lookup"><span data-stu-id="66308-130">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="66308-131">在打开的 "新建组" 页中，配置以下设置。</span><span class="sxs-lookup"><span data-stu-id="66308-131">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="66308-132">使用标记为的设置 <sup>\*</sup> 是必需的。</span><span class="sxs-lookup"><span data-stu-id="66308-132">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="66308-133"><sup>\*</sup>**显示名称**：此名称显示在组织的通讯簿中，在 "收件人：" 行中，电子邮件发送到此组，以及 EAC 的 "**组**" 列表中。</span><span class="sxs-lookup"><span data-stu-id="66308-133"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="66308-134">显示名称是必需的，必须是唯一的，并且应该是用户友好的，以便用户可以识别它。</span><span class="sxs-lookup"><span data-stu-id="66308-134">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="66308-135"><sup>\*</sup>**别名**：使用此框可以键入组的别名的名称。</span><span class="sxs-lookup"><span data-stu-id="66308-135"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="66308-136">别名不能超过64个字符，并且必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="66308-136">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="66308-137">当用户在电子邮件的 "To" 行中键入别名时，它将解析为组的显示名称。</span><span class="sxs-lookup"><span data-stu-id="66308-137">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="66308-138"><sup>\*</sup>**电子邮件地址**：电子邮件地址由 at （@）符号左侧的别名和右侧的域组成。</span><span class="sxs-lookup"><span data-stu-id="66308-138"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="66308-139">默认情况下，**别名**的值用于别名值，但您可以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="66308-139">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="66308-140">对于 "域" 值，请单击下拉，并在组织中选择并接受域。</span><span class="sxs-lookup"><span data-stu-id="66308-140">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="66308-141">**说明**：此说明出现在通讯簿和 EAC 的详细信息窗格中。</span><span class="sxs-lookup"><span data-stu-id="66308-141">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="66308-142"><sup>\*</sup>**所有者**：组所有者可以管理组成员身份。</span><span class="sxs-lookup"><span data-stu-id="66308-142"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="66308-143">默认情况下，组创建者即为组所有者。</span><span class="sxs-lookup"><span data-stu-id="66308-143">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="66308-144">所有组都必须至少有一个所有者。</span><span class="sxs-lookup"><span data-stu-id="66308-144">All groups must have at least one owner.</span></span>

     <span data-ttu-id="66308-145">若要添加所有者，请单击 "**添加** ![ 添加图标" ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="66308-145">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="66308-146">在出现的对话框中，查找并选择收件人或组，然后单击 "**加载项 >**"。</span><span class="sxs-lookup"><span data-stu-id="66308-146">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="66308-147">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="66308-147">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="66308-148">完成后，请单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="66308-148">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="66308-149">若要删除所有者，请选择所有者，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="66308-149">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="66308-150">**Members**：添加和删除组成员。</span><span class="sxs-lookup"><span data-stu-id="66308-150">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="66308-151">若要添加成员，请单击 "**添加** ![ 添加图标" ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="66308-151">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="66308-152">在出现的对话框中，查找并选择收件人或组，然后单击 "**加载项 >**"。</span><span class="sxs-lookup"><span data-stu-id="66308-152">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="66308-153">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="66308-153">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="66308-154">完成后，请单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="66308-154">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="66308-155">若要删除某个成员，请选择该成员，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="66308-155">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="66308-156">完成后，请单击 "**保存**" 以创建通讯组。</span><span class="sxs-lookup"><span data-stu-id="66308-156">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="66308-157">使用 EAC 修改通讯组</span><span class="sxs-lookup"><span data-stu-id="66308-157">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="66308-158">在 EAC 中，转到 "**收件人** \> **组**"。</span><span class="sxs-lookup"><span data-stu-id="66308-158">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="66308-159">在组列表中，选择要修改的通讯组或已启用邮件的安全组，然后单击 "**编辑** ![ 编辑图标" ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="66308-159">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="66308-160">在打开的 "通讯组属性" 页上，单击下列选项卡之一以查看或更改属性。</span><span class="sxs-lookup"><span data-stu-id="66308-160">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="66308-161">完成后，单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="66308-161">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="66308-162">常规</span><span class="sxs-lookup"><span data-stu-id="66308-162">General</span></span>

<span data-ttu-id="66308-163">使用此选项卡可以查看或更改有关组的基本信息。</span><span class="sxs-lookup"><span data-stu-id="66308-163">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="66308-164">**显示名称**：此名称显示在通讯簿中、电子邮件发送到此组的 "收件人" 行和 "组"**列表**中。</span><span class="sxs-lookup"><span data-stu-id="66308-164">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="66308-165">显示名称是必需的，并且应当是用户友好的，以便用户可以识别它。</span><span class="sxs-lookup"><span data-stu-id="66308-165">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="66308-166">显示名称在域中还必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="66308-166">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="66308-167">如果您已实现了一个组命名策略，则显示名称必须符合此策略定义的命名格式。</span><span class="sxs-lookup"><span data-stu-id="66308-167">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="66308-168">**别名**：这是电子邮件地址中出现在（@）符号左侧的部分。</span><span class="sxs-lookup"><span data-stu-id="66308-168">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="66308-169">如果更改别名，组的主 SMTP 地址也会更改，并包含新的别名。</span><span class="sxs-lookup"><span data-stu-id="66308-169">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="66308-170">同时，带有之前别名的电子邮件地址将作为该组的代理地址保留。</span><span class="sxs-lookup"><span data-stu-id="66308-170">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="66308-171">**电子邮件地址**：电子邮件地址由 at （@）符号左侧的别名和右侧的域组成。</span><span class="sxs-lookup"><span data-stu-id="66308-171">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="66308-172">默认情况下，**别名**的值用于别名值，但您可以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="66308-172">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="66308-173">对于 "域" 值，请单击下拉，并在组织中选择并接受域。</span><span class="sxs-lookup"><span data-stu-id="66308-173">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="66308-174">**说明**：此说明出现在通讯簿和 EAC 的详细信息窗格中。</span><span class="sxs-lookup"><span data-stu-id="66308-174">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="66308-175">Ownership</span><span class="sxs-lookup"><span data-stu-id="66308-175">Ownership</span></span>

<span data-ttu-id="66308-176">使用此选项卡可分配组所有者。</span><span class="sxs-lookup"><span data-stu-id="66308-176">Use this tab to assign group owners.</span></span> <span data-ttu-id="66308-177">组所有者可以管理组成员身份。</span><span class="sxs-lookup"><span data-stu-id="66308-177">A group owner can manage group membership.</span></span> <span data-ttu-id="66308-178">默认情况下，组创建者即为组所有者。</span><span class="sxs-lookup"><span data-stu-id="66308-178">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="66308-179">所有组都必须至少有一个所有者。</span><span class="sxs-lookup"><span data-stu-id="66308-179">All groups must have at least one owner.</span></span>

<span data-ttu-id="66308-180">若要添加所有者，请单击 "**添加** ![ 添加图标" ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="66308-180">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="66308-181">在出现的对话框中，查找并选择收件人，然后单击 "**加载项 >**"。</span><span class="sxs-lookup"><span data-stu-id="66308-181">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="66308-182">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="66308-182">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="66308-183">完成后，请单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="66308-183">When you're finished, click **OK**.</span></span>

<span data-ttu-id="66308-184">若要删除所有者，请选择所有者，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="66308-184">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="66308-185">成员身份</span><span class="sxs-lookup"><span data-stu-id="66308-185">Membership</span></span>

<span data-ttu-id="66308-186">使用此选项卡可以添加或删除组成员。</span><span class="sxs-lookup"><span data-stu-id="66308-186">Use this tab to add or remove group members.</span></span> <span data-ttu-id="66308-187">组所有者不需要是组的成员。</span><span class="sxs-lookup"><span data-stu-id="66308-187">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="66308-188">若要添加成员，请单击 "**添加** ![ 添加图标" ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="66308-188">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="66308-189">在出现的对话框中，查找并选择收件人或组，然后单击 "**加载项 >**"。</span><span class="sxs-lookup"><span data-stu-id="66308-189">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="66308-190">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="66308-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="66308-191">完成后，请单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="66308-191">When you're finished, click **OK**.</span></span>

<span data-ttu-id="66308-192">若要删除某个成员，请选择该成员，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="66308-192">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="66308-193">使用 EAC 删除组</span><span class="sxs-lookup"><span data-stu-id="66308-193">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="66308-194">在 EAC 中，转到 "**收件人** \> **组**"。</span><span class="sxs-lookup"><span data-stu-id="66308-194">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="66308-195">在组列表中，选择要删除的通讯组，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="66308-195">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="66308-196">使用 PowerShell 管理组</span><span class="sxs-lookup"><span data-stu-id="66308-196">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="66308-197">使用独立的 EOP PowerShell 查看组</span><span class="sxs-lookup"><span data-stu-id="66308-197">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="66308-198">若要在独立 EOP PowerShell 中返回所有通讯组和已启用邮件的安全组的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="66308-198">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="66308-199">若要返回组成员的列表，请将 \< GroupIdentity 替换 \> 为组的名称、别名或电子邮件地址，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="66308-199">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="66308-200">有关语法和参数的详细信息，请参阅 "[获取-收件人](https://docs.microsoft.com/powershell/module/exchange/get-recipient)" 和 " [get-distributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)"。</span><span class="sxs-lookup"><span data-stu-id="66308-200">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="66308-201">使用独立的 EOP PowerShell 创建组</span><span class="sxs-lookup"><span data-stu-id="66308-201">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="66308-202">若要在独立 EOP PowerShell 中创建通讯组或启用邮件的安全组，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="66308-202">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="66308-203">**注意**：</span><span class="sxs-lookup"><span data-stu-id="66308-203">**Notes**:</span></span>

- <span data-ttu-id="66308-204">_Name_参数是必需的，最大长度为64个字符，并且必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="66308-204">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="66308-205">如果您不使用 _DisplayName_ 参数，_Name_ 参数的值可用于显示名称。</span><span class="sxs-lookup"><span data-stu-id="66308-205">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="66308-206">如果不使用_alias_参数，则_Name_参数将用于别名值。</span><span class="sxs-lookup"><span data-stu-id="66308-206">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="66308-207">删除空格并将不受支持的字符转换为问号（？）。</span><span class="sxs-lookup"><span data-stu-id="66308-207">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="66308-208">如果不使用_PrimarySmtpAddress_参数，则在_PrimarySmtpAddress_参数中使用别名值。</span><span class="sxs-lookup"><span data-stu-id="66308-208">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="66308-209">如果不使用_Type_参数，则默认值为分布。</span><span class="sxs-lookup"><span data-stu-id="66308-209">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="66308-210">本示例将创建一个名为 "IT 管理员" 的通讯组，其中包含指定的属性。</span><span class="sxs-lookup"><span data-stu-id="66308-210">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="66308-211">有关语法和参数的详细信息，请参阅[set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)。</span><span class="sxs-lookup"><span data-stu-id="66308-211">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="66308-212">使用独立的 EOP PowerShell 修改组</span><span class="sxs-lookup"><span data-stu-id="66308-212">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="66308-213">若要修改独立 EOP PowerShell 中的组，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="66308-213">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="66308-214">本示例使用将 "西雅图员工" 组的主 SMTP 地址（也称为 "回复地址"）更改为 sea.employees@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="66308-214">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="66308-215">此示例将安全团队组的当前成员替换为 Kitty Petersen 和 Tyson Fawcett。</span><span class="sxs-lookup"><span data-stu-id="66308-215">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="66308-216">本示例将名为 Tyson Fawcett 的新用户添加到名为安全团队的组，同时保留该组的当前成员。</span><span class="sxs-lookup"><span data-stu-id="66308-216">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="66308-217">有关语法和参数的详细信息，请参阅[set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup)和[EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="66308-217">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="66308-218">使用远程 Windows PowerShell 删除组</span><span class="sxs-lookup"><span data-stu-id="66308-218">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="66308-219">本示例使用删除名为 "IT 管理员" 的通讯组。</span><span class="sxs-lookup"><span data-stu-id="66308-219">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="66308-220">有关语法和参数的详细信息，请参阅[set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)。</span><span class="sxs-lookup"><span data-stu-id="66308-220">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="66308-221">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="66308-221">How do you know these procedures worked?</span></span>

<span data-ttu-id="66308-222">若要验证您是否已成功创建、修改或删除了通讯组或已启用邮件的安全组，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="66308-222">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="66308-223">在 EAC 中，转到 "**收件人** \> **组**"。</span><span class="sxs-lookup"><span data-stu-id="66308-223">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="66308-224">验证组是否已列出（或未列出），并验证 "**组类型**" 值。</span><span class="sxs-lookup"><span data-stu-id="66308-224">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="66308-225">选择该组并查看详细信息窗格中的信息，或单击 "**编辑** ![ 编辑图标 ](../../media/ITPro-EAC-AddIcon.png) " 以查看设置。</span><span class="sxs-lookup"><span data-stu-id="66308-225">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="66308-226">在独立 EOP PowerShell 中，运行以下命令来验证组是否已列出（或未列出）：</span><span class="sxs-lookup"><span data-stu-id="66308-226">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="66308-227">\<将 GroupIdentity 替换 \> 为组的名称、别名或电子邮件地址，并运行以下命令来验证设置：</span><span class="sxs-lookup"><span data-stu-id="66308-227">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="66308-228">若要查看组成员，请将 \< GroupIdentity 替换 \> 为组的名称、别名或电子邮件地址，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="66308-228">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
