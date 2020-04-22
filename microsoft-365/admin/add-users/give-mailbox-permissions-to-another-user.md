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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: '了解如何授予用户访问其他用户的邮箱的权限。 这将使用户拥有从其他用户的邮箱读取邮件和发送邮件的权限。 '
ms.openlocfilehash: 5a0677844e8503253561c57f926c9c4fadadd76d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43617166"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="327a5-104">向其他用户授予邮箱权限 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="327a5-104">Give mailbox permissions to another user - Admin Help</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="327a5-105">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="327a5-105">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="327a5-106">作为管理员，你可能需要按照公司要求允许某些用户访问其他用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="327a5-106">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="327a5-107">例如，你可能希望使助理可以从其经理的邮箱发送或阅读电子邮件，或者希望其中某一位用户可以代表另一用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="327a5-107">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="327a5-108">本主题介绍如何实现这一目的。</span><span class="sxs-lookup"><span data-stu-id="327a5-108">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="327a5-109">如果需要查找有关创建和管理共享邮箱的信息，请查看[创建共享邮箱](../email/create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="327a5-109">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="327a5-110">需要设置邮箱权限？</span><span class="sxs-lookup"><span data-stu-id="327a5-110">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="327a5-p103">通过邮箱权限，你可以向其他用户授予邮箱读取/写入访问权限。以下文章可提供设置和使用此功能所需的帮助：</span><span class="sxs-lookup"><span data-stu-id="327a5-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="327a5-113">**设置权限：**</span><span class="sxs-lookup"><span data-stu-id="327a5-113">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="327a5-p104">设置权限的第一步是确定你希望允许其他用户在特定邮箱中可以执行哪些操作。你可以允许用户阅读邮箱中的电子邮件、代表其他用户发送电子邮件和以如同邮件从该邮箱发送的形式发送电子邮件。请参阅以下文章，了解如何设置每类权限：</span><span class="sxs-lookup"><span data-stu-id="327a5-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="327a5-117">从其他用户的邮箱读取电子邮件</span><span class="sxs-lookup"><span data-stu-id="327a5-117">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="327a5-118">从其他用户的邮箱发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="327a5-118">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="327a5-119">代表其他用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="327a5-119">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="327a5-120">**更改传播：**</span><span class="sxs-lookup"><span data-stu-id="327a5-120">**Changing propagation:**</span></span>
  
<span data-ttu-id="327a5-121">设置权限后，更改项在系统传播和生效可能需要长达 60 分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="327a5-121">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="327a5-122">**权限设置后如何使用：**</span><span class="sxs-lookup"><span data-stu-id="327a5-122">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="327a5-p105">授予访问权限后，你可以通过几种不同的方式访问邮箱。相关帮助请参阅以下文章：[访问他人的邮箱](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span><span class="sxs-lookup"><span data-stu-id="327a5-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="327a5-125">从其他用户的邮箱发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="327a5-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="327a5-126">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="327a5-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="327a5-127">选择用户的名称（你打算向其授予发送权限），打开其 "属性" 窗格。</span><span class="sxs-lookup"><span data-stu-id="327a5-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="327a5-128">在 **邮件** 选项卡上，选择 **管理邮箱权限**。</span><span class="sxs-lookup"><span data-stu-id="327a5-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="327a5-129">在"**发送方式**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="327a5-130">选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="327a5-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="327a5-131">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="327a5-132">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="327a5-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="327a5-133">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**”旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="327a5-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="327a5-134">在"**发送方式**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="327a5-135">选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="327a5-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="327a5-136">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="327a5-137">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="327a5-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="327a5-138">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**”旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="327a5-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="327a5-139">在"**发送方式**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="327a5-140">选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="327a5-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="327a5-141">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="327a5-142">读取其他用户邮箱中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="327a5-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="327a5-143">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="327a5-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="327a5-144">选择用户名（你想要允许阅读的邮箱）以打开其 "属性" 窗格。</span><span class="sxs-lookup"><span data-stu-id="327a5-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="327a5-145">在 **邮件** 选项卡上，选择 **管理邮箱权限**。</span><span class="sxs-lookup"><span data-stu-id="327a5-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="327a5-146">在 "**读取和管理**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="327a5-147">选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="327a5-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="327a5-148">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-148">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="327a5-149">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="327a5-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="327a5-150">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="327a5-150">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="327a5-151">在 "**读取和管理**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-151">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="327a5-152">选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="327a5-152">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="327a5-153">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-153">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="327a5-154">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="327a5-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="327a5-155">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="327a5-155">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="327a5-156">在 "**读取和管理**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-156">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="327a5-157">选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="327a5-157">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="327a5-158">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-158">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="327a5-159">代表其他用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="327a5-159">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="327a5-160">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="327a5-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="327a5-161">选择用户的名称（你打算向其授予**代表发送**权限），打开其 "属性" 窗格。</span><span class="sxs-lookup"><span data-stu-id="327a5-161">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="327a5-162">在 **邮件** 选项卡上，选择 **管理邮箱权限**。</span><span class="sxs-lookup"><span data-stu-id="327a5-162">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="327a5-163">在"**代表发送**”旁边，选择“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="327a5-163">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="327a5-164">选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="327a5-164">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="327a5-165">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-165">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="327a5-166">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="327a5-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="327a5-167">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="327a5-167">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="327a5-168">在"**代表发送**”旁边，选择“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="327a5-168">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="327a5-169">选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="327a5-169">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="327a5-170">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-170">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="327a5-171">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="327a5-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="327a5-172">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="327a5-172">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="327a5-173">在"**代表发送**”旁边，选择“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="327a5-173">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="327a5-174">选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="327a5-174">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="327a5-175">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="327a5-175">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="327a5-176">从 Outlook 和适用于企业的 Outlook 网页版发送和阅读电子邮件</span><span class="sxs-lookup"><span data-stu-id="327a5-176">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="327a5-p106">希望了解如何从其他用户的邮箱发送电子邮件？请查看以下主题：</span><span class="sxs-lookup"><span data-stu-id="327a5-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="327a5-179">管理他人的邮件和日历项目</span><span class="sxs-lookup"><span data-stu-id="327a5-179">Manage another person's mail and calendar items</span></span>](https://support.office.com/article/afb79d6b-2967-43b9-a944-a6b953190af5.aspx)
    
- [<span data-ttu-id="327a5-180">代表他人或组发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="327a5-180">Send email from another person or group</span></span>](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)
