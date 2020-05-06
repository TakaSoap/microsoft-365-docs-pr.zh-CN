---
title: 添加用户的其他电子邮件别名
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '了解如何将多个电子邮件地址（称为 "电子邮件别名"）与 Microsoft 365 商业版帐户相关联。 '
ms.openlocfilehash: efd0dbf5ae072c803b52d94dd41f16db9bb0413a
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048803"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="dc67d-103">添加用户的其他电子邮件别名</span><span class="sxs-lookup"><span data-stu-id="dc67d-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="dc67d-104">本文适用于具有业务订阅的 Microsoft 365 管理员。</span><span class="sxs-lookup"><span data-stu-id="dc67d-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="dc67d-105">不适用于家庭用户。</span><span class="sxs-lookup"><span data-stu-id="dc67d-105">It's not for home users.</span></span>
  
<span data-ttu-id="dc67d-106">Microsoft 365 中的主电子邮件地址通常是创建帐户时分配给用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="dc67d-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="dc67d-107">当用户向其他人发送电子邮件时，其主要电子邮件地址通常在电子邮件应用的" *发件人*  "字段中显示。</span><span class="sxs-lookup"><span data-stu-id="dc67d-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="dc67d-108">他们还可以有多个电子邮件地址与他们的 Microsoft 365 商业版帐户关联。</span><span class="sxs-lookup"><span data-stu-id="dc67d-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="dc67d-109">其他地址称为别名。</span><span class="sxs-lookup"><span data-stu-id="dc67d-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="dc67d-110">例如，假设 Jenna 具有电子邮件地址 jenna@contosoco.com，但她还希望在 jen@contosoco.com 中接收电子邮件，因为某些人会按该名称引用她。</span><span class="sxs-lookup"><span data-stu-id="dc67d-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="dc67d-111">您可以为她创建别名，以便这两个电子邮件地址都转到 Jenna 的收件箱。</span><span class="sxs-lookup"><span data-stu-id="dc67d-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="dc67d-112">最多可为一个用户创建 400 个别名。</span><span class="sxs-lookup"><span data-stu-id="dc67d-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="dc67d-113">无需其他费用或许可证。</span><span class="sxs-lookup"><span data-stu-id="dc67d-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="dc67d-114">如果您希望多个用户管理发送到单个电子邮件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的电子邮件，请创建一个共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="dc67d-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="dc67d-115">若要了解详细信息，请参阅[创建共享邮箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="dc67d-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="dc67d-116">向用户添加电子邮件别名</span><span class="sxs-lookup"><span data-stu-id="dc67d-116">Add email aliases to a user</span></span>
<span data-ttu-id="dc67d-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="dc67d-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="dc67d-118">您必须具有[管理员权限](../add-users/about-admin-roles.md)才能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="dc67d-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="dc67d-119">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="dc67d-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="dc67d-120">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="dc67d-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="dc67d-121">在 "**活动用户**" 页上，选择 "用户 >**管理电子邮件别名**。</span><span class="sxs-lookup"><span data-stu-id="dc67d-121">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="dc67d-122">如果没有为用户分配许可证，则不会看到此选项。</span><span class="sxs-lookup"><span data-stu-id="dc67d-122">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="dc67d-123">选择 " **+ 添加别名**"，然后输入用户的新别名。</span><span class="sxs-lookup"><span data-stu-id="dc67d-123">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="dc67d-124">如果您收到错误消息 "**找不到与参数名匹配的参数" EmailAddresses**"，这意味着完成对租户的设置或自定义域（如果您最近添加了一个）会花一些时间。</span><span class="sxs-lookup"><span data-stu-id="dc67d-124">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="dc67d-125">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="dc67d-125">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="dc67d-126">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="dc67d-126">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="dc67d-127">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="dc67d-127">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="dc67d-128">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="dc67d-128">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="dc67d-129">电子邮件别名必须以下拉列表中的域结尾。</span><span class="sxs-lookup"><span data-stu-id="dc67d-129">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="dc67d-130">若要向列表中添加其他域名，请参阅[add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。</span><span class="sxs-lookup"><span data-stu-id="dc67d-130">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="dc67d-131">完成后，请选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="dc67d-131">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="dc67d-132">等待 24 小时，让新的别名跨整个 Office 365 进行填充。</span><span class="sxs-lookup"><span data-stu-id="dc67d-132">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="dc67d-133">用户现在将拥有一个主地址和一个别名。</span><span class="sxs-lookup"><span data-stu-id="dc67d-133">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="dc67d-134">例如，发送到陶湘 Hoffman 的主要地址、Eliza@NodPublishers.com 和她的别名 Sales@NodPublishers.com 的所有邮件都将转到陶湘的 "收件箱"。</span><span class="sxs-lookup"><span data-stu-id="dc67d-134">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="dc67d-135">**当用户回复时，"*发件*人" 地址将成为她的主要电子邮件别名。**</span><span class="sxs-lookup"><span data-stu-id="dc67d-135">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="dc67d-136">例如，假设向 Sales@NodPublishers.com 发送了一封邮件，并且该邮件到达陶湘的收件箱中。</span><span class="sxs-lookup"><span data-stu-id="dc67d-136">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="dc67d-137">陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="dc67d-137">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="dc67d-138">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="dc67d-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="dc67d-139">在" **活动用户**"页面上，选择要编辑的用户名。</span><span class="sxs-lookup"><span data-stu-id="dc67d-139">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="dc67d-140">在 "**用户名/电子邮件别名**" 旁边，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="dc67d-140">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="dc67d-141">如果您收到错误消息 "**找不到与参数名匹配的参数" EmailAddresses**"，这意味着完成对租户的设置或自定义域（如果您最近添加了一个）会花一些时间。</span><span class="sxs-lookup"><span data-stu-id="dc67d-141">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="dc67d-142">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="dc67d-142">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="dc67d-143">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="dc67d-143">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="dc67d-144">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="dc67d-144">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="dc67d-145">在 "**别名**" 下的文本框中，键入新电子邮件别名的第一部分。</span><span class="sxs-lookup"><span data-stu-id="dc67d-145">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="dc67d-146">如果已将自己的域添加到 Office 365，可以使用下拉列表，选择新电子邮件别名的域。</span><span class="sxs-lookup"><span data-stu-id="dc67d-146">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="dc67d-147">然后，选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="dc67d-147">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="dc67d-148">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="dc67d-148">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="dc67d-149">电子邮件别名必须以下拉列表中的域结尾。</span><span class="sxs-lookup"><span data-stu-id="dc67d-149">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="dc67d-150">若要向列表中添加其他域名，请参阅[add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。</span><span class="sxs-lookup"><span data-stu-id="dc67d-150">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="dc67d-151">完成后，请选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="dc67d-151">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="dc67d-152">等待 24 小时，让新的别名跨整个 Office 365 进行填充。</span><span class="sxs-lookup"><span data-stu-id="dc67d-152">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="dc67d-153">用户现在将拥有一个主地址和一个别名。</span><span class="sxs-lookup"><span data-stu-id="dc67d-153">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="dc67d-154">例如，发送到陶湘 Hoffman 的主要地址、Eliza@NodPublishers.com 和她的别名 Sales@NodPublishers.com 的所有邮件都将转到陶湘的 "收件箱"。</span><span class="sxs-lookup"><span data-stu-id="dc67d-154">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="dc67d-155">**当用户回复时，"*发件*人" 地址将成为她的主要电子邮件别名。**</span><span class="sxs-lookup"><span data-stu-id="dc67d-155">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="dc67d-156">例如，假设向 Sales@NodPublishers.com 发送了一封邮件，并且该邮件到达陶湘的收件箱中。</span><span class="sxs-lookup"><span data-stu-id="dc67d-156">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="dc67d-157">陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="dc67d-157">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="dc67d-158">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="dc67d-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="dc67d-159">在" **活动用户**"页面上，选择要编辑的用户名。</span><span class="sxs-lookup"><span data-stu-id="dc67d-159">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="dc67d-160">在 "**用户名/电子邮件别名**" 旁边，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="dc67d-160">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="dc67d-161">如果您收到错误消息 "**找不到与参数名匹配的参数" EmailAddresses**"，这意味着完成对租户的设置或自定义域（如果您最近添加了一个）会花一些时间。</span><span class="sxs-lookup"><span data-stu-id="dc67d-161">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="dc67d-162">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="dc67d-162">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="dc67d-163">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="dc67d-163">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="dc67d-164">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="dc67d-164">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="dc67d-165">在 "**别名**" 下的文本框中，键入新电子邮件别名的第一部分。</span><span class="sxs-lookup"><span data-stu-id="dc67d-165">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="dc67d-166">如果已将自己的域添加到 Office 365，可以使用下拉列表，选择新电子邮件别名的域。</span><span class="sxs-lookup"><span data-stu-id="dc67d-166">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="dc67d-167">然后，选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="dc67d-167">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="dc67d-168">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="dc67d-168">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="dc67d-169">电子邮件别名必须以下拉列表中的域结尾。</span><span class="sxs-lookup"><span data-stu-id="dc67d-169">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="dc67d-170">若要向列表中添加其他域名，请参阅[add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。</span><span class="sxs-lookup"><span data-stu-id="dc67d-170">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="dc67d-171">完成后，请选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="dc67d-171">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="dc67d-172">等待 24 小时，让新的别名跨整个 Office 365 进行填充。</span><span class="sxs-lookup"><span data-stu-id="dc67d-172">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="dc67d-173">用户现在将拥有一个主地址和一个别名。</span><span class="sxs-lookup"><span data-stu-id="dc67d-173">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="dc67d-174">例如，发送到陶湘 Hoffman 的主要地址、Eliza@NodPublishers.com 和她的别名 Sales@NodPublishers.com 的所有邮件都将转到陶湘的 "收件箱"。</span><span class="sxs-lookup"><span data-stu-id="dc67d-174">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="dc67d-175">**当用户回复时，"*发件*人" 地址将成为她的主要电子邮件别名。**</span><span class="sxs-lookup"><span data-stu-id="dc67d-175">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="dc67d-176">例如，假设向 Sales@NodPublishers.com 发送了一封邮件，并且该邮件到达陶湘的收件箱中。</span><span class="sxs-lookup"><span data-stu-id="dc67d-176">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="dc67d-177">陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="dc67d-177">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="dc67d-178">您是否收到 "找不到与参数名称 EmailAddresses 匹配的参数？"</span><span class="sxs-lookup"><span data-stu-id="dc67d-178">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="dc67d-179">如果您收到错误消息 "**找不到与参数名称 EmailAddresses 匹配的参数**"，这意味着完成设置租户或自定义域（如果最近添加了一个）会花一些时间。</span><span class="sxs-lookup"><span data-stu-id="dc67d-179">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="dc67d-180">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="dc67d-180">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="dc67d-181">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="dc67d-181">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="dc67d-182">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="dc67d-182">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="dc67d-183">是否从 GoDaddy 或另一合作伙伴处购买订阅？</span><span class="sxs-lookup"><span data-stu-id="dc67d-183">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="dc67d-184">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="dc67d-184">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="dc67d-185">相关文章</span><span class="sxs-lookup"><span data-stu-id="dc67d-185">Related articles</span></span>

[<span data-ttu-id="dc67d-186">从不同的地址发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="dc67d-186">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="dc67d-187">更改用户名和电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="dc67d-187">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

