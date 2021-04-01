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
ms.openlocfilehash: a44271cdbf52136e61702697a960cc3cbcd8119d
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470997"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="f3099-103">为用户添加另一个电子邮件别名</span><span class="sxs-lookup"><span data-stu-id="f3099-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="f3099-104">本文适用于具有商业版订阅的 Microsoft 365 管理员。</span><span class="sxs-lookup"><span data-stu-id="f3099-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="f3099-105">不适用于家庭用户。</span><span class="sxs-lookup"><span data-stu-id="f3099-105">It's not for home users.</span></span>
  
<span data-ttu-id="f3099-106">Microsoft 365 中的主要电子邮件地址通常是用户创建帐户时分配的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f3099-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="f3099-107">当用户向其他人发送电子邮件时，其主要电子邮件地址通常在电子邮件应用的" *发件人*  "字段中显示。</span><span class="sxs-lookup"><span data-stu-id="f3099-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="f3099-108">他们还可以将多个电子邮件地址与其 Microsoft 365 商业版帐户关联。</span><span class="sxs-lookup"><span data-stu-id="f3099-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="f3099-109">其他地址称为别名。</span><span class="sxs-lookup"><span data-stu-id="f3099-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="f3099-110">例如，假设 Jenna 的电子邮件地址是 jenna@contosoco.com，但是她还想在 jen@contosoco.com 接收电子邮件，因为有人通过该姓名引用她。</span><span class="sxs-lookup"><span data-stu-id="f3099-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="f3099-111">你可以为她创建别名，以便两个电子邮件地址都转到 Jenna 的收件箱。</span><span class="sxs-lookup"><span data-stu-id="f3099-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="f3099-112">最多可为一个用户创建 400 个别名。</span><span class="sxs-lookup"><span data-stu-id="f3099-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="f3099-113">无需其他费用或许可证。</span><span class="sxs-lookup"><span data-stu-id="f3099-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="f3099-114">如果希望多个用户管理发送到单个电子邮件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的电子邮件，请创建共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="f3099-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="f3099-115">若要了解更多信息，请参阅 [创建共享邮箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="f3099-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="f3099-116">向用户添加电子邮件别名</span><span class="sxs-lookup"><span data-stu-id="f3099-116">Add email aliases to a user</span></span>
<span data-ttu-id="f3099-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="f3099-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="f3099-118">为此， [你必须具有](../add-users/about-admin-roles.md) 管理员权限。</span><span class="sxs-lookup"><span data-stu-id="f3099-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="f3099-119">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f3099-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="f3099-120">在" **活动用户"** 页上，选择"管理> **别名"的用户**。</span><span class="sxs-lookup"><span data-stu-id="f3099-120">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="f3099-121">如果用户未分配许可证，则看不到此选项。</span><span class="sxs-lookup"><span data-stu-id="f3099-121">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="f3099-122">选择 **+ 添加别名** ，然后输入用户的新别名。</span><span class="sxs-lookup"><span data-stu-id="f3099-122">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="f3099-123">如果收到错误消息"找不到与参数名称 **"EmailAddresses"** 匹配的参数，则意味着完成租户或自定义域设置（如果最近添加了一个）需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="f3099-123">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="f3099-124">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="f3099-124">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="f3099-125">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="f3099-125">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="f3099-126">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="f3099-126">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="f3099-127">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="f3099-127">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="f3099-128">电子邮件别名必须以下拉列表中的域结尾。</span><span class="sxs-lookup"><span data-stu-id="f3099-128">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="f3099-129">若要向列表中添加其他域名，请参阅将域[添加到 Microsoft 365。](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="f3099-129">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="f3099-130">完成后，选择"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="f3099-130">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="f3099-131">等待 24 小时，以在整个 Microsoft 365 中填充新的别名。</span><span class="sxs-lookup"><span data-stu-id="f3099-131">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="f3099-132">用户现在将具有主地址和别名。</span><span class="sxs-lookup"><span data-stu-id="f3099-132">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="f3099-133">例如，发送到 Eliza Hoffman 的主地址、Eliza@NodPublishers.com 和别名 Sales@NodPublishers.com 的所有邮件都将发送到 Eliza 的收件箱。</span><span class="sxs-lookup"><span data-stu-id="f3099-133">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="f3099-134">**当用户回复时，" *发送地址*  "将成为她的主要电子邮件别名。**</span><span class="sxs-lookup"><span data-stu-id="f3099-134">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="f3099-135">例如，假设有一封邮件发送到 Sales@NodPublishers.com，并到达吉萨的收件箱。</span><span class="sxs-lookup"><span data-stu-id="f3099-135">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="f3099-136">陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="f3099-136">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="f3099-137">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f3099-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="f3099-138">在" **活动用户**"页面上，选择要编辑的用户名。</span><span class="sxs-lookup"><span data-stu-id="f3099-138">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="f3099-139">在"**用户名/电子邮件别名"旁边**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="f3099-139">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="f3099-140">如果收到错误消息"找不到与参数名称 **"EmailAddresses"** 匹配的参数，则意味着完成租户或自定义域设置（如果最近添加了一个）需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="f3099-140">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="f3099-141">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="f3099-141">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="f3099-142">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="f3099-142">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="f3099-143">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="f3099-143">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="f3099-144">在"别名 **"下的文本框** 中，键入新电子邮件别名的第一部分。</span><span class="sxs-lookup"><span data-stu-id="f3099-144">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="f3099-145">如果已将自己的域添加到 Microsoft 365，则可使用下拉列表为新电子邮件别名选择域。</span><span class="sxs-lookup"><span data-stu-id="f3099-145">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="f3099-146">然后，选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="f3099-146">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f3099-147">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="f3099-147">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="f3099-148">电子邮件别名必须以下拉列表中的域结尾。</span><span class="sxs-lookup"><span data-stu-id="f3099-148">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="f3099-149">若要向列表中添加其他域名，请参阅将域[添加到 Microsoft 365。](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="f3099-149">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="f3099-150">完成后，选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f3099-150">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="f3099-151">等待 24 小时，以在整个 Microsoft 365 中填充新的别名。</span><span class="sxs-lookup"><span data-stu-id="f3099-151">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="f3099-152">用户现在将具有主地址和别名。</span><span class="sxs-lookup"><span data-stu-id="f3099-152">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="f3099-153">例如，发送到 Eliza Hoffman 的主地址、Eliza@NodPublishers.com 和别名 Sales@NodPublishers.com 的所有邮件都将发送到 Eliza 的收件箱。</span><span class="sxs-lookup"><span data-stu-id="f3099-153">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="f3099-154">**当用户回复时，" *发送地址*  "将成为她的主要电子邮件别名。**</span><span class="sxs-lookup"><span data-stu-id="f3099-154">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="f3099-155">例如，假设有一封邮件发送到 Sales@NodPublishers.com，并到达吉萨的收件箱。</span><span class="sxs-lookup"><span data-stu-id="f3099-155">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="f3099-156">陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="f3099-156">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f3099-157">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f3099-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="f3099-158">在" **活动用户**"页面上，选择要编辑的用户名。</span><span class="sxs-lookup"><span data-stu-id="f3099-158">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="f3099-159">在"**用户名/电子邮件别名"旁边**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="f3099-159">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="f3099-160">如果收到错误消息"找不到与参数名称 **"EmailAddresses"** 匹配的参数，则意味着完成租户或自定义域设置（如果最近添加了一个）需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="f3099-160">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="f3099-161">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="f3099-161">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="f3099-162">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="f3099-162">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="f3099-163">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="f3099-163">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="f3099-164">在"别名 **"下的文本框** 中，键入新电子邮件别名的第一部分。</span><span class="sxs-lookup"><span data-stu-id="f3099-164">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="f3099-165">如果已将自己的域添加到 Microsoft 365，则可使用下拉列表为新电子邮件别名选择域。</span><span class="sxs-lookup"><span data-stu-id="f3099-165">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="f3099-166">然后，选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="f3099-166">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f3099-167">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="f3099-167">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="f3099-168">电子邮件别名必须以下拉列表中的域结尾。</span><span class="sxs-lookup"><span data-stu-id="f3099-168">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="f3099-169">若要向列表中添加其他域名，请参阅将域[添加到 Microsoft 365。](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="f3099-169">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="f3099-170">完成后，选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f3099-170">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="f3099-171">等待 24 小时，以在整个 Microsoft 365 中填充新的别名。</span><span class="sxs-lookup"><span data-stu-id="f3099-171">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="f3099-172">用户现在将具有主地址和别名。</span><span class="sxs-lookup"><span data-stu-id="f3099-172">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="f3099-173">例如，发送到 Eliza Hoffman 的主地址、Eliza@NodPublishers.com 和别名 Sales@NodPublishers.com 的所有邮件都将发送到 Eliza 的收件箱。</span><span class="sxs-lookup"><span data-stu-id="f3099-173">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="f3099-174">**当用户回复时，" *发送地址*  "将成为她的主要电子邮件别名。**</span><span class="sxs-lookup"><span data-stu-id="f3099-174">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="f3099-175">例如，假设有一封邮件发送到 Sales@NodPublishers.com，并到达吉萨的收件箱。</span><span class="sxs-lookup"><span data-stu-id="f3099-175">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="f3099-176">陶湘回复邮件时，其主电子邮件地址将显示为发件人，而不是 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="f3099-176">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="f3099-177">您是否收到"找不到与参数名称 EmailAddresses 匹配的参数"？</span><span class="sxs-lookup"><span data-stu-id="f3099-177">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="f3099-178">如果收到错误消息" 找不到与参数名称 **EmailAddresses**" 匹配的参数，则意味着完成租户或自定义域设置（如果最近添加了一个）需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="f3099-178">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="f3099-179">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="f3099-179">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="f3099-180">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="f3099-180">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="f3099-181">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="f3099-181">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="f3099-182">是否从 GoDaddy 或另一合作伙伴处购买订阅？</span><span class="sxs-lookup"><span data-stu-id="f3099-182">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="f3099-183">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="f3099-183">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="f3099-184">相关文章</span><span class="sxs-lookup"><span data-stu-id="f3099-184">Related articles</span></span>

[<span data-ttu-id="f3099-185">从不同的地址发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="f3099-185">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="f3099-186">更改用户名和电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="f3099-186">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
