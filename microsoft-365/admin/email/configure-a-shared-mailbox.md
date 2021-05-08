---
title: 配置共享邮箱设置
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 创建共享邮箱后，您需要为用户配置一些设置，例如电子邮件转发和自动答复。 稍后，您可能需要更改其他设置，如邮箱名称或成员。
ms.openlocfilehash: 01d5aaa686e1d64c9ea7d89913d8208f779dcfd1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52243968"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="22712-104">配置共享邮箱设置</span><span class="sxs-lookup"><span data-stu-id="22712-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="22712-105">创建共享 [邮箱后](create-a-shared-mailbox.md)，您需要为邮箱用户配置一些设置，例如电子邮件转发和自动答复。</span><span class="sxs-lookup"><span data-stu-id="22712-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="22712-106">稍后，您可能需要更改其他设置，如邮箱名称、成员或成员权限。</span><span class="sxs-lookup"><span data-stu-id="22712-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="22712-107">更改共享邮箱的名称或电子邮件别名，或更改主电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="22712-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="22712-108">在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="22712-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="22712-109">选择要编辑的共享邮箱，然后选择"名称、电子邮件、电子邮件别名"旁边的"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="22712-109">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="22712-110">输入新名称，或添加其他别名。</span><span class="sxs-lookup"><span data-stu-id="22712-110">Enter a new name, or add another alias.</span></span> <span data-ttu-id="22712-111">如果要更改主电子邮件地址，邮箱必须拥有多个电子邮件别名。</span><span class="sxs-lookup"><span data-stu-id="22712-111">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="22712-112">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="22712-112">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="22712-113">转发共享邮箱收到的电子邮件</span><span class="sxs-lookup"><span data-stu-id="22712-113">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="22712-114">无需为共享邮箱分配许可证，就不必转发发送给它的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="22712-114">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="22712-115">可以将邮件转发到任何有效的电子邮件地址或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="22712-115">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="22712-116">在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="22712-116">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="22712-117">选择要编辑的共享邮箱，然后选择"**电子邮件转发编辑** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="22712-117">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="22712-118">将开关设置为 **"打开"，** 然后输入一个电子邮件地址以将邮件转发到 。</span><span class="sxs-lookup"><span data-stu-id="22712-118">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="22712-119">它可以是任何有效的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="22712-119">It can be any valid email address.</span></span> <span data-ttu-id="22712-120">若要转发到多个地址，需要为这些地址[](/office365/admin/setup/create-distribution-lists)创建通讯组，然后在此框中输入该组的名称。</span><span class="sxs-lookup"><span data-stu-id="22712-120">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="22712-121">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="22712-121">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="22712-122">从共享邮箱发送自动答复</span><span class="sxs-lookup"><span data-stu-id="22712-122">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="22712-123">在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="22712-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="22712-124">选择要编辑的共享邮箱，然后选择"**自动答复""** \> **编辑"。**</span><span class="sxs-lookup"><span data-stu-id="22712-124">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="22712-125">将开关切换到" **开**"，选择将答复发送给组织内部还是外部的人员。</span><span class="sxs-lookup"><span data-stu-id="22712-125">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="22712-p106">输入要向组织内部的人员发送的答复。不能添加图像，只能输入文本。</span><span class="sxs-lookup"><span data-stu-id="22712-p106">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="22712-128">如果还要 *向* 组织外部人员发送答复，请选中要获取答复的复选框，然后键入文本。</span><span class="sxs-lookup"><span data-stu-id="22712-128">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="22712-129">不能只发送给组织外部的人员而不发送给组织内部的人员。</span><span class="sxs-lookup"><span data-stu-id="22712-129">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="22712-130">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="22712-130">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="22712-131">使所有人都能看到已发送的电子邮件（答复邮件）</span><span class="sxs-lookup"><span data-stu-id="22712-131">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="22712-p108">默认情况下，发送自共享邮箱的邮件不会保存到共享邮箱的"已发送邮件"文件夹中。相反，它们会保存到发件人的"已发送邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="22712-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="22712-134">如果要允许所有人查看"已发送电子邮件"，请在管理中心编辑共享邮箱设置，然后选择"已发送邮件""**编辑** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="22712-134">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="22712-135">选择共享邮箱可用于访问 Microsoft 电子邮件的应用</span><span class="sxs-lookup"><span data-stu-id="22712-135">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="22712-136">在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="22712-136">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="22712-137">选择要编辑的共享邮箱，然后选择"**电子邮件应用** 编辑 \> **"。**</span><span class="sxs-lookup"><span data-stu-id="22712-137">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="22712-138">对于您希望成员能够用于访问共享邮箱的所有应用，将开关设置为"打开"。</span><span class="sxs-lookup"><span data-stu-id="22712-138">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="22712-139">对于你 **不希望他们** 使用的任何应用，将开关设置为"关闭"。</span><span class="sxs-lookup"><span data-stu-id="22712-139">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="22712-140">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="22712-140">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="22712-141">将共享邮箱置于诉讼保留状态</span><span class="sxs-lookup"><span data-stu-id="22712-141">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="22712-142">若要了解有关诉讼保留的更多信息，请参阅 [创建诉讼保留](../../compliance/create-a-litigation-hold.md)。</span><span class="sxs-lookup"><span data-stu-id="22712-142">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="22712-143">在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="22712-143">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="22712-144">选择要编辑的共享邮箱，然后选择"**诉讼保留""** \> **编辑"。**</span><span class="sxs-lookup"><span data-stu-id="22712-144">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="22712-145">将开关设置为 **"打开"。**</span><span class="sxs-lookup"><span data-stu-id="22712-145">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="22712-146">（可选）输入持续时间、保留说明和包含详细信息的 URL。</span><span class="sxs-lookup"><span data-stu-id="22712-146">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="22712-147">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="22712-147">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="22712-148">添加或删除成员</span><span class="sxs-lookup"><span data-stu-id="22712-148">Add or remove members</span></span>

1. <span data-ttu-id="22712-149">在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="22712-149">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="22712-150">选择要编辑的共享邮箱，然后选择"成员 **编辑** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="22712-150">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="22712-151">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="22712-151">Do one of the following:</span></span>
   - <span data-ttu-id="22712-152">若要添加成员，请选择"**添加成员"，** 搜索或选择要添加的成员，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="22712-152">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="22712-153">若要删除成员，请使用"搜索"框在必要时搜索成员，选择成员名称旁边的 **"X"，** 然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="22712-153">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="22712-154">再次 **选择"保存** "。</span><span class="sxs-lookup"><span data-stu-id="22712-154">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="22712-155">添加或删除成员的权限</span><span class="sxs-lookup"><span data-stu-id="22712-155">Add or remove permissions of members</span></span>

1. <span data-ttu-id="22712-156">在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="22712-156">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="22712-157">选择要编辑的共享邮箱，然后选择"**成员** \> **自定义权限"。**</span><span class="sxs-lookup"><span data-stu-id="22712-157">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="22712-158">选择要 **为** 成员更改的权限旁边的"编辑"。</span><span class="sxs-lookup"><span data-stu-id="22712-158">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="22712-159">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="22712-159">Do one of the following:</span></span>
   - <span data-ttu-id="22712-160">若要向其他会员授予该权限，请选择"添加权限"，搜索或选择要添加的成员，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="22712-160">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="22712-161">若要从成员中删除权限，请使用"搜索"框搜索该成员（如有必要，请选择成员名称旁边的 **"X"，** 然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="22712-161">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="22712-162">再次 **选择"保存** "。</span><span class="sxs-lookup"><span data-stu-id="22712-162">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="22712-163">在全局地址列表中显示或隐藏共享邮箱</span><span class="sxs-lookup"><span data-stu-id="22712-163">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="22712-164">如果选择不在全局地址列表中显示共享邮箱，则邮箱不会显示在组织的地址列表中，但仍会收到发送给它的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="22712-164">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="22712-165">在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="22712-165">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="22712-166">选择要编辑的共享邮箱，然后选择"**在全局地址列表中显示""编辑** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="22712-166">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="22712-167">将开关设置为 **开**  或 **关**。</span><span class="sxs-lookup"><span data-stu-id="22712-167">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="22712-168">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="22712-168">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="22712-169">隐藏地址列表中的共享邮箱会使新的共享邮箱成员无法将隐藏邮箱添加到其 Outlook 配置文件中，直到共享邮箱再次显示在地址列表中。</span><span class="sxs-lookup"><span data-stu-id="22712-169">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="22712-170">相关内容</span><span class="sxs-lookup"><span data-stu-id="22712-170">Related content</span></span>

<span data-ttu-id="22712-171">[关于共享邮箱 (](about-shared-mailboxes.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="22712-171">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>

<span data-ttu-id="22712-172">[创建共享邮箱 (](create-a-shared-mailbox.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="22712-172">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="22712-173">[将用户邮箱转换为共享邮箱 (](convert-user-mailbox-to-shared-mailbox.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="22712-173">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="22712-174">[从共享邮箱中删除许可证 (](remove-license-from-shared-mailbox.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="22712-174">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="22712-175">[解决共享邮箱问题 (](resolve-issues-with-shared-mailboxes.md) 本文) </span><span class="sxs-lookup"><span data-stu-id="22712-175">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>