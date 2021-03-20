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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '了解如何将多个电子邮件地址（称为电子邮件别名）与 Microsoft 365 商业版帐户关联。 '
ms.openlocfilehash: 590782f7b22b1d26abef83f884d45da567f0425c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915946"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="82d25-103">为用户添加另一个电子邮件别名</span><span class="sxs-lookup"><span data-stu-id="82d25-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="82d25-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="82d25-104">The admin center is changing.</span></span> <span data-ttu-id="82d25-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="82d25-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="82d25-106">本文适用于具有商业版订阅的 Microsoft 365 管理员。</span><span class="sxs-lookup"><span data-stu-id="82d25-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="82d25-107">不适用于家庭用户。</span><span class="sxs-lookup"><span data-stu-id="82d25-107">It's not for home users.</span></span>
  
<span data-ttu-id="82d25-108">Microsoft 365 中的主要电子邮件地址通常是用户创建帐户时分配的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="82d25-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="82d25-109">当用户向其他人发送电子邮件时，其主要电子邮件地址通常在电子邮件应用的" *发件人*  "字段中显示。</span><span class="sxs-lookup"><span data-stu-id="82d25-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="82d25-110">他们还可以将多个电子邮件地址与其 Microsoft 365 商业版帐户关联。</span><span class="sxs-lookup"><span data-stu-id="82d25-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="82d25-111">其他地址称为别名。</span><span class="sxs-lookup"><span data-stu-id="82d25-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="82d25-112">例如，假设 Jenna 的电子邮件地址是 jenna@contosoco.com，但是她还想在 jen@contosoco.com 接收电子邮件，因为有人通过该姓名引用她。</span><span class="sxs-lookup"><span data-stu-id="82d25-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="82d25-113">你可以为她创建别名，以便两个电子邮件地址都转到 Jenna 的收件箱。</span><span class="sxs-lookup"><span data-stu-id="82d25-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="82d25-114">最多可为一个用户创建 400 个别名。</span><span class="sxs-lookup"><span data-stu-id="82d25-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="82d25-115">无需其他费用或许可证。</span><span class="sxs-lookup"><span data-stu-id="82d25-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="82d25-116">如果希望多个用户管理发送到单个电子邮件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的电子邮件，请创建共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="82d25-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="82d25-117">若要了解更多信息，请参阅 [创建共享邮箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="82d25-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="82d25-118">向用户添加电子邮件别名</span><span class="sxs-lookup"><span data-stu-id="82d25-118">Add email aliases to a user</span></span>
<span data-ttu-id="82d25-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="82d25-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="82d25-120">为此， [你必须具有](../add-users/about-admin-roles.md) 管理员权限。</span><span class="sxs-lookup"><span data-stu-id="82d25-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="82d25-121">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="82d25-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="82d25-122">在" **活动用户"** 页上，选择"管理> **别名"的用户**。</span><span class="sxs-lookup"><span data-stu-id="82d25-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="82d25-123">如果用户未分配许可证，则看不到此选项。</span><span class="sxs-lookup"><span data-stu-id="82d25-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="82d25-124">选择 **+ 添加别名** ，然后输入用户的新别名。</span><span class="sxs-lookup"><span data-stu-id="82d25-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="82d25-125">如果收到错误消息"找不到与参数名称 **"EmailAddresses"** 匹配的参数，则意味着完成租户或自定义域设置（如果最近添加了一个）需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="82d25-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="82d25-126">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="82d25-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="82d25-127">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="82d25-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="82d25-128">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="82d25-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="82d25-129">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="82d25-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="82d25-130">电子邮件别名必须以下拉列表中的域结尾。</span><span class="sxs-lookup"><span data-stu-id="82d25-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="82d25-131">若要向列表中添加其他域名，请参阅将域[添加到 Microsoft 365。](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="82d25-131">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="82d25-132">完成后，选择"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="82d25-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="82d25-133">等待 24 小时，以在整个 Microsoft 365 中填充新的别名。</span><span class="sxs-lookup"><span data-stu-id="82d25-133">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="82d25-134">用户现在将具有主地址和别名。</span><span class="sxs-lookup"><span data-stu-id="82d25-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="82d25-135">例如，发送到 Eliza Hoffman 的主地址、Eliza@NodPublishers.com 和别名 Sales@NodPublishers.com 的所有邮件都将发送到 Eliza 的收件箱。</span><span class="sxs-lookup"><span data-stu-id="82d25-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="82d25-136">**当用户回复时，" *发送地址*  "将成为她的主要电子邮件别名。**</span><span class="sxs-lookup"><span data-stu-id="82d25-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="82d25-137">例如，假设有一封邮件发送到 Sales@NodPublishers.com，并到达吉萨的收件箱。</span><span class="sxs-lookup"><span data-stu-id="82d25-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="82d25-138">陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="82d25-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="82d25-139">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="82d25-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="82d25-140">在" **活动用户**"页面上，选择要编辑的用户名。</span><span class="sxs-lookup"><span data-stu-id="82d25-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="82d25-141">在"**用户名/电子邮件别名"旁边**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="82d25-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="82d25-142">如果收到错误消息"找不到与参数名称 **"EmailAddresses"** 匹配的参数，则意味着完成租户或自定义域设置（如果最近添加了一个）需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="82d25-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="82d25-143">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="82d25-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="82d25-144">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="82d25-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="82d25-145">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="82d25-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="82d25-146">在"别名 **"下的文本框** 中，键入新电子邮件别名的第一部分。</span><span class="sxs-lookup"><span data-stu-id="82d25-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="82d25-147">如果已将自己的域添加到 Microsoft 365，则可使用下拉列表为新电子邮件别名选择域。</span><span class="sxs-lookup"><span data-stu-id="82d25-147">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="82d25-148">然后，选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="82d25-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="82d25-149">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="82d25-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="82d25-150">电子邮件别名必须以下拉列表中的域结尾。</span><span class="sxs-lookup"><span data-stu-id="82d25-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="82d25-151">若要向列表中添加其他域名，请参阅将域[添加到 Microsoft 365。](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="82d25-151">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="82d25-152">完成后，选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="82d25-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="82d25-153">等待 24 小时，以在整个 Microsoft 365 中填充新的别名。</span><span class="sxs-lookup"><span data-stu-id="82d25-153">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="82d25-154">用户现在将具有主地址和别名。</span><span class="sxs-lookup"><span data-stu-id="82d25-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="82d25-155">例如，发送到 Eliza Hoffman 的主地址、Eliza@NodPublishers.com 和别名 Sales@NodPublishers.com 的所有邮件都将发送到 Eliza 的收件箱。</span><span class="sxs-lookup"><span data-stu-id="82d25-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="82d25-156">**当用户回复时，" *发送地址*  "将成为她的主要电子邮件别名。**</span><span class="sxs-lookup"><span data-stu-id="82d25-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="82d25-157">例如，假设有一封邮件发送到 Sales@NodPublishers.com，并到达吉萨的收件箱。</span><span class="sxs-lookup"><span data-stu-id="82d25-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="82d25-158">陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="82d25-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="82d25-159">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="82d25-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="82d25-160">在" **活动用户**"页面上，选择要编辑的用户名。</span><span class="sxs-lookup"><span data-stu-id="82d25-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="82d25-161">在"**用户名/电子邮件别名"旁边**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="82d25-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="82d25-162">如果收到错误消息"找不到与参数名称 **"EmailAddresses"** 匹配的参数，则意味着完成租户或自定义域设置（如果最近添加了一个）需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="82d25-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="82d25-163">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="82d25-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="82d25-164">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="82d25-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="82d25-165">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="82d25-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="82d25-166">在"别名 **"下的文本框** 中，键入新电子邮件别名的第一部分。</span><span class="sxs-lookup"><span data-stu-id="82d25-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="82d25-167">如果已将自己的域添加到 Microsoft 365，则可使用下拉列表为新电子邮件别名选择域。</span><span class="sxs-lookup"><span data-stu-id="82d25-167">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="82d25-168">然后，选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="82d25-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="82d25-169">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="82d25-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="82d25-170">电子邮件别名必须以下拉列表中的域结尾。</span><span class="sxs-lookup"><span data-stu-id="82d25-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="82d25-171">若要向列表中添加其他域名，请参阅将域[添加到 Microsoft 365。](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="82d25-171">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="82d25-172">完成后，选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="82d25-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="82d25-173">等待 24 小时，以在整个 Microsoft 365 中填充新的别名。</span><span class="sxs-lookup"><span data-stu-id="82d25-173">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="82d25-174">用户现在将具有主地址和别名。</span><span class="sxs-lookup"><span data-stu-id="82d25-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="82d25-175">例如，发送到 Eliza Hoffman 的主地址、Eliza@NodPublishers.com 和别名 Sales@NodPublishers.com 的所有邮件都将发送到 Eliza 的收件箱。</span><span class="sxs-lookup"><span data-stu-id="82d25-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="82d25-176">**当用户回复时，" *发送地址*  "将成为她的主要电子邮件别名。**</span><span class="sxs-lookup"><span data-stu-id="82d25-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="82d25-177">例如，假设有一封邮件发送到 Sales@NodPublishers.com，并到达吉萨的收件箱。</span><span class="sxs-lookup"><span data-stu-id="82d25-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="82d25-178">陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="82d25-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="82d25-179">您是否收到"找不到与参数名称 EmailAddresses 匹配的参数"？</span><span class="sxs-lookup"><span data-stu-id="82d25-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="82d25-180">如果收到错误消息" 找不到与参数名称 **EmailAddresses**" 匹配的参数，则意味着完成租户或自定义域设置（如果最近添加了一个）需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="82d25-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="82d25-181">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="82d25-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="82d25-182">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="82d25-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="82d25-183">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="82d25-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="82d25-184">是否从 GoDaddy 或另一合作伙伴处购买订阅？</span><span class="sxs-lookup"><span data-stu-id="82d25-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="82d25-185">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="82d25-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="82d25-186">相关文章</span><span class="sxs-lookup"><span data-stu-id="82d25-186">Related articles</span></span>

[<span data-ttu-id="82d25-187">从不同的地址发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="82d25-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="82d25-188">更改用户名和电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="82d25-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
