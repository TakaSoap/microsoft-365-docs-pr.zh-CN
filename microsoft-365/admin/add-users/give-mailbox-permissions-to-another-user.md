---
title: 向其他用户授予邮箱权限 - 管理员帮助
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 授予用户访问其他用户邮箱的权限，此操作允许用户从其他用户的邮箱读取和发送电子邮件。
ms.openlocfilehash: 1c1b591ff9053e20e8754df5b7c69288d198cc98
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394335"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="89b2d-103">向其他用户授予邮箱权限 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="89b2d-103">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="89b2d-p101">作为管理员，你可能需要按照公司要求允许某些用户访问其他用户的邮箱。例如，你可能希望使助理可以从其经理的邮箱发送或阅读电子邮件，或者希望其中某一位用户可以代表另一用户发送电子邮件。本主题介绍如何实现这一目的。</span><span class="sxs-lookup"><span data-stu-id="89b2d-p101">As the admin, you may have company requirements to allow some users access to another user's mailbox. For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user. This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="89b2d-107">如果需要查找有关创建和管理共享邮箱的信息，请查看[创建共享邮箱](../email/create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="89b2d-107">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="89b2d-108">需要设置邮箱权限？</span><span class="sxs-lookup"><span data-stu-id="89b2d-108">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="89b2d-p102">通过邮箱权限，你可以向其他用户授予邮箱读取/写入访问权限。以下文章可提供设置和使用此功能所需的帮助：</span><span class="sxs-lookup"><span data-stu-id="89b2d-p102">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="89b2d-111">**设置权限：**</span><span class="sxs-lookup"><span data-stu-id="89b2d-111">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="89b2d-p103">设置权限的第一步是确定你希望允许其他用户在特定邮箱中可以执行哪些操作。你可以允许用户阅读邮箱中的电子邮件、代表其他用户发送电子邮件和以如同邮件从该邮箱发送的形式发送电子邮件。请参阅以下文章，了解如何设置每类权限：</span><span class="sxs-lookup"><span data-stu-id="89b2d-p103">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="89b2d-115">从其他用户的邮箱读取电子邮件</span><span class="sxs-lookup"><span data-stu-id="89b2d-115">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="89b2d-116">从其他用户的邮箱发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="89b2d-116">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="89b2d-117">代表其他用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="89b2d-117">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="89b2d-118">**更改传播：**</span><span class="sxs-lookup"><span data-stu-id="89b2d-118">**Changing propagation:**</span></span>
  
<span data-ttu-id="89b2d-119">设置权限后，更改项在系统传播和生效可能需要长达 60 分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="89b2d-119">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="89b2d-120">**权限设置后如何使用：**</span><span class="sxs-lookup"><span data-stu-id="89b2d-120">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="89b2d-p104">获得访问权限后，你可通过几种不同的方式访问邮箱。相关帮助请参阅[访问他人的邮箱](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)一文。</span><span class="sxs-lookup"><span data-stu-id="89b2d-p104">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="89b2d-123">只能在当前组织租户中设置权限。</span><span class="sxs-lookup"><span data-stu-id="89b2d-123">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="89b2d-124">无法在没有租户用户的情况下设置邮箱权限。</span><span class="sxs-lookup"><span data-stu-id="89b2d-124">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="89b2d-125">从其他用户的邮箱发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="89b2d-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="89b2d-126">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="89b2d-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="89b2d-127">选择用户的名称（你打算向其授予发送权限），打开其 "属性" 窗格。</span><span class="sxs-lookup"><span data-stu-id="89b2d-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="89b2d-128">在 **邮件** 选项卡上，选择 **管理邮箱权限**。</span><span class="sxs-lookup"><span data-stu-id="89b2d-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="89b2d-129">在"**发送方式**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="89b2d-130">选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="89b2d-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="89b2d-131">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="89b2d-132">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="89b2d-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="89b2d-133">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**”旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="89b2d-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="89b2d-134">在"**发送方式**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="89b2d-135">选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="89b2d-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="89b2d-136">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="89b2d-137">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="89b2d-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="89b2d-138">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**”旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="89b2d-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="89b2d-139">在"**发送方式**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="89b2d-140">选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="89b2d-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="89b2d-141">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="89b2d-142">读取其他用户邮箱中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="89b2d-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="89b2d-143">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="89b2d-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="89b2d-144">选择用户名（你想要允许阅读的邮箱）以打开其 "属性" 窗格。</span><span class="sxs-lookup"><span data-stu-id="89b2d-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="89b2d-145">在 **邮件** 选项卡上，选择 **管理邮箱权限**。</span><span class="sxs-lookup"><span data-stu-id="89b2d-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="89b2d-146">在 "**读取和管理**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="89b2d-147">选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="89b2d-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="89b2d-148">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-148">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="89b2d-149">“**读取**”和“**管理**”权限在 Exchange 管理中心中授予时称为“**完全访问**”权限。</span><span class="sxs-lookup"><span data-stu-id="89b2d-149">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="89b2d-150">完全访问权限不授予“**发送方式**”或“**代表发送**”权限。</span><span class="sxs-lookup"><span data-stu-id="89b2d-150">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="89b2d-151">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="89b2d-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="89b2d-152">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="89b2d-152">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="89b2d-153">在 "**读取和管理**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-153">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="89b2d-154">选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="89b2d-154">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="89b2d-155">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-155">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="89b2d-156">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="89b2d-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="89b2d-157">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="89b2d-157">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="89b2d-158">在 "**读取和管理**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-158">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="89b2d-159">选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="89b2d-159">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="89b2d-160">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-160">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="89b2d-161">代表其他用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="89b2d-161">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="89b2d-162">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="89b2d-162">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="89b2d-163">选择用户的名称（你打算向其授予 **代表发送** 权限），打开其 "属性" 窗格。</span><span class="sxs-lookup"><span data-stu-id="89b2d-163">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="89b2d-164">在 **邮件** 选项卡上，选择 **管理邮箱权限**。</span><span class="sxs-lookup"><span data-stu-id="89b2d-164">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="89b2d-165">在"**代表发送**”旁边，选择“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="89b2d-165">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="89b2d-166">选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="89b2d-166">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="89b2d-167">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-167">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="89b2d-168">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="89b2d-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="89b2d-169">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="89b2d-169">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="89b2d-170">在"**代表发送**”旁边，选择“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="89b2d-170">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="89b2d-171">选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="89b2d-171">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="89b2d-172">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-172">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="89b2d-173">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="89b2d-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="89b2d-174">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="89b2d-174">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="89b2d-175">在"**代表发送**”旁边，选择“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="89b2d-175">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="89b2d-176">选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="89b2d-176">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="89b2d-177">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89b2d-177">Select **Save**.</span></span>

::: moniker-end


## <a name="related-content"></a><span data-ttu-id="89b2d-178">相关内容</span><span class="sxs-lookup"><span data-stu-id="89b2d-178">Related content</span></span>
  
<span data-ttu-id="89b2d-179">[管理他人的邮件和日历项目](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)（文章）</span><span class="sxs-lookup"><span data-stu-id="89b2d-179">[Manage another person's mail and calendar items](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (article)</span></span>\   
<span data-ttu-id="89b2d-180">[代表他人或组发送电子邮件](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)（文章）</span><span class="sxs-lookup"><span data-stu-id="89b2d-180">[Send email from another person or group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (article)</span></span>\
<span data-ttu-id="89b2d-181">[更改用户名和电子邮件地址](../add-users/change-a-user-name-and-email-address.md)（视频）</span><span class="sxs-lookup"><span data-stu-id="89b2d-181">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (video)</span></span>

