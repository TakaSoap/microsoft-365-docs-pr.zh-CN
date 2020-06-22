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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: '了解如何授予用户访问其他用户的邮箱的权限。 这将使用户拥有从其他用户的邮箱读取邮件和发送邮件的权限。 '
ms.openlocfilehash: dafe0f8c8f7d65b2721b70f6c132d179c461a89b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780597"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="a7cb3-104">向其他用户授予邮箱权限 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="a7cb3-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="a7cb3-105">作为管理员，你可能需要按照公司要求允许某些用户访问其他用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="a7cb3-106">例如，你可能希望使助理可以从其经理的邮箱发送或阅读电子邮件，或者希望其中某一位用户可以代表另一用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="a7cb3-107">本主题介绍如何实现这一目的。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="a7cb3-108">如果需要查找有关创建和管理共享邮箱的信息，请查看[创建共享邮箱](../email/create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="a7cb3-109">需要设置邮箱权限？</span><span class="sxs-lookup"><span data-stu-id="a7cb3-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="a7cb3-110">Mailbox permissions allow you to give read/write access to a mailbox to another user.</span><span class="sxs-lookup"><span data-stu-id="a7cb3-110">Mailbox permissions allow you to give read/write access to a mailbox to another user.</span></span> <span data-ttu-id="a7cb3-111">The articles below might give you the help you need to set up and use this feature:</span><span class="sxs-lookup"><span data-stu-id="a7cb3-111">The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="a7cb3-112">**设置权限：**</span><span class="sxs-lookup"><span data-stu-id="a7cb3-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="a7cb3-113">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox.</span><span class="sxs-lookup"><span data-stu-id="a7cb3-113">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox.</span></span> <span data-ttu-id="a7cb3-114">You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox.</span><span class="sxs-lookup"><span data-stu-id="a7cb3-114">You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox.</span></span> <span data-ttu-id="a7cb3-115">Refer to the following articles on how to set up each type of permissions:</span><span class="sxs-lookup"><span data-stu-id="a7cb3-115">Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="a7cb3-116">从其他用户的邮箱读取电子邮件</span><span class="sxs-lookup"><span data-stu-id="a7cb3-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="a7cb3-117">从其他用户的邮箱发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a7cb3-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="a7cb3-118">代表其他用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a7cb3-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="a7cb3-119">**更改传播：**</span><span class="sxs-lookup"><span data-stu-id="a7cb3-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="a7cb3-120">设置权限后，更改项在系统传播和生效可能需要长达 60 分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="a7cb3-121">**权限设置后如何使用：**</span><span class="sxs-lookup"><span data-stu-id="a7cb3-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="a7cb3-122">There are a few different ways you can access a mailbox once you've been given access.</span><span class="sxs-lookup"><span data-stu-id="a7cb3-122">There are a few different ways you can access a mailbox once you've been given access.</span></span> <span data-ttu-id="a7cb3-123">For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span><span class="sxs-lookup"><span data-stu-id="a7cb3-123">For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="a7cb3-124">从其他用户的邮箱发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a7cb3-124">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a7cb3-125">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-125">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="a7cb3-126">选择用户的名称（你打算向其授予发送权限），打开其 "属性" 窗格。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-126">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="a7cb3-127">在 **邮件** 选项卡上，选择 **管理邮箱权限**。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-127">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="a7cb3-128">在"**发送方式**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-128">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="a7cb3-129">选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-129">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="a7cb3-130">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-130">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a7cb3-131">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="a7cb3-132">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**”旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-132">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="a7cb3-133">在"**发送方式**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-133">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="a7cb3-134">选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-134">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="a7cb3-135">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-135">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a7cb3-136">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="a7cb3-137">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**”旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-137">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="a7cb3-138">在"**发送方式**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-138">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="a7cb3-139">选择“**添加权限**”，然后选择你希望该用户可以使用其身份发送的人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-139">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="a7cb3-140">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-140">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="a7cb3-141">读取其他用户邮箱中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="a7cb3-141">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a7cb3-142">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="a7cb3-143">选择用户名（你想要允许阅读的邮箱）以打开其 "属性" 窗格。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-143">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="a7cb3-144">在 **邮件** 选项卡上，选择 **管理邮箱权限**。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-144">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="a7cb3-145">在 "**读取和管理**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-145">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="a7cb3-146">选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-146">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="a7cb3-147">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-147">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a7cb3-148">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-148">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="a7cb3-149">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-149">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="a7cb3-150">在 "**读取和管理**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-150">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="a7cb3-151">选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-151">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="a7cb3-152">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-152">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a7cb3-153">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-153">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="a7cb3-154">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-154">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="a7cb3-155">在 "**读取和管理**" 旁，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-155">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="a7cb3-156">选择“**添加权限**”，然后选择允许其从该邮箱读取电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-156">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="a7cb3-157">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-157">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="a7cb3-158">代表其他用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a7cb3-158">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a7cb3-159">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="a7cb3-160">选择用户的名称（你打算向其授予**代表发送**权限），打开其 "属性" 窗格。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-160">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="a7cb3-161">在 **邮件** 选项卡上，选择 **管理邮箱权限**。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-161">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="a7cb3-162">在"**代表发送**”旁边，选择“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-162">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="a7cb3-163">选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-163">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="a7cb3-164">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-164">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a7cb3-165">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="a7cb3-166">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-166">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="a7cb3-167">在"**代表发送**”旁边，选择“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-167">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="a7cb3-168">选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-168">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="a7cb3-169">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-169">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a7cb3-170">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-170">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="a7cb3-171">选择所需用户，展开“**邮件设置**”，然后选择 "**邮箱权限**"旁边的“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-171">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="a7cb3-172">在"**代表发送**”旁边，选择“**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-172">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="a7cb3-173">选择“**添加权限**”，然后选择允许其代表该邮箱发送电子邮件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-173">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="a7cb3-174">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7cb3-174">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="a7cb3-175">从 Outlook 和适用于企业的 Outlook 网页版发送和阅读电子邮件</span><span class="sxs-lookup"><span data-stu-id="a7cb3-175">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="a7cb3-176">Want to know how to send email from another user's mailbox?</span><span class="sxs-lookup"><span data-stu-id="a7cb3-176">Want to know how to send email from another user's mailbox?</span></span> <span data-ttu-id="a7cb3-177">Check out the following topics:</span><span class="sxs-lookup"><span data-stu-id="a7cb3-177">Check out the following topics:</span></span>
  
- [<span data-ttu-id="a7cb3-178">管理他人的邮件和日历项目</span><span class="sxs-lookup"><span data-stu-id="a7cb3-178">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="a7cb3-179">代表他人或组发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a7cb3-179">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
