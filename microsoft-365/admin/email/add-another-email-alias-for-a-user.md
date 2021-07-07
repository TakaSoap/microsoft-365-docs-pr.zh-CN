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
description: '了解如何将多个电子邮件地址（称为电子邮件别名）与企业Microsoft 365相关联。 '
ms.openlocfilehash: e6eac45c3ade3fd737f93c88c29b56ccd497212e
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314352"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="6072a-103">为用户添加另一个电子邮件别名</span><span class="sxs-lookup"><span data-stu-id="6072a-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="6072a-104">本文适用于Microsoft 365订阅的管理员。</span><span class="sxs-lookup"><span data-stu-id="6072a-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="6072a-105">不适用于家庭用户。</span><span class="sxs-lookup"><span data-stu-id="6072a-105">It's not for home users.</span></span>
  
<span data-ttu-id="6072a-106">用户邮箱中Microsoft 365电子邮件地址通常是用户创建帐户时分配的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6072a-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="6072a-107">当用户向其他人发送电子邮件时，其主要电子邮件地址通常在电子邮件应用的" *发件人*  "字段中显示。</span><span class="sxs-lookup"><span data-stu-id="6072a-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="6072a-108">他们还可以将多个电子邮件地址与其企业帐户Microsoft 365关联。</span><span class="sxs-lookup"><span data-stu-id="6072a-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="6072a-109">其他地址称为别名。</span><span class="sxs-lookup"><span data-stu-id="6072a-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="6072a-110">例如，假设 Jenna 的电子邮件地址是 jenna@contosoco.com，但是她还想在 jen@contosoco.com 接收电子邮件，因为有人通过该姓名引用她。</span><span class="sxs-lookup"><span data-stu-id="6072a-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="6072a-111">你可以为她创建别名，以便两个电子邮件地址都转到 Jenna 的收件箱。</span><span class="sxs-lookup"><span data-stu-id="6072a-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
  
<span data-ttu-id="6072a-p104">最多可为一个用户创建 400 个别名。无需其他费用或许可证。</span><span class="sxs-lookup"><span data-stu-id="6072a-p104">You can create up to 400 aliases for a user. No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="6072a-114">如果希望多个用户管理发送到单个电子邮件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的电子邮件，请创建共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="6072a-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="6072a-115">若要了解更多信息，请参阅 [创建共享邮箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="6072a-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="6072a-116">向用户添加电子邮件别名</span><span class="sxs-lookup"><span data-stu-id="6072a-116">Add email aliases to a user</span></span>

<span data-ttu-id="6072a-117">为此， [你必须具有](../add-users/about-admin-roles.md) 管理员权限。</span><span class="sxs-lookup"><span data-stu-id="6072a-117">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

1. <span data-ttu-id="6072a-118">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="6072a-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6072a-119">在" **活动用户"** 页上，选择"管理> **和电子邮件"的用户**。</span><span class="sxs-lookup"><span data-stu-id="6072a-119">On the **Active Users** page, select the user > **Manage username and email**.</span></span> <span data-ttu-id="6072a-120">如果用户未分配许可证，则看不到此选项。</span><span class="sxs-lookup"><span data-stu-id="6072a-120">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="6072a-121">选择 **+ 添加别名** ，然后输入用户的新别名。</span><span class="sxs-lookup"><span data-stu-id="6072a-121">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="6072a-122">如果收到错误消息"找不到与参数名称 **"EmailAddresses"** 匹配的参数，则意味着完成租户或自定义域设置（如果最近添加了一个）需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="6072a-122">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6072a-123">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="6072a-123">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6072a-124">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="6072a-124">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6072a-125">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="6072a-125">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="6072a-126">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="6072a-126">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="6072a-127">电子邮件别名必须以下拉列表中的域结尾。</span><span class="sxs-lookup"><span data-stu-id="6072a-127">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="6072a-128">若要向列表中添加其他域名，请参阅将[域添加到Microsoft 365。](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="6072a-128">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="6072a-129">完成后，选择"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="6072a-129">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="6072a-130">请等待 24 小时，以在整个过程中填充Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6072a-130">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="6072a-131">用户现在将具有主地址和别名。</span><span class="sxs-lookup"><span data-stu-id="6072a-131">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="6072a-132">例如，发送到 Eliza Hoffman 的主地址、Eliza@NodPublishers.com 和别名 Sales@NodPublishers.com 的所有邮件都将发送到 Eliza 的收件箱。</span><span class="sxs-lookup"><span data-stu-id="6072a-132">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="6072a-133">**当用户回复时，"*发送\* 者"地址将取决于她Outlook客户端。Outlook 网页版会使用收到电子邮件的别名 (我们将此称为 ping- 一) 。Outlook桌面将使用她的主要电子邮件别名。*\*</span><span class="sxs-lookup"><span data-stu-id="6072a-133">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="6072a-134">例如，假设有一封邮件发送到 Sales@NodPublishers.com，并到达吉萨的收件箱。</span><span class="sxs-lookup"><span data-stu-id="6072a-134">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="6072a-135">当 Eliza 使用桌面Outlook邮件时，她的主要电子邮件地址将显示为 Eliza@NodPublishers.com，而不是 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="6072a-135">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="6072a-136">您是否收到"找不到与参数名称 EmailAddresses 匹配的参数"？</span><span class="sxs-lookup"><span data-stu-id="6072a-136">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>

<span data-ttu-id="6072a-137">如果收到错误消息" 找不到与参数名称 **EmailAddresses**" 匹配的参数，则意味着完成租户或自定义域设置（如果最近添加了一个）需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="6072a-137">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6072a-138">设置过程最多需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="6072a-138">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6072a-139">稍等片刻，待设置过程完成后重试。</span><span class="sxs-lookup"><span data-stu-id="6072a-139">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6072a-140">如果问题仍然存在，请致电支持人员，他们会为你执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="6072a-140">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="6072a-141">是否从 GoDaddy 或另一合作伙伴处购买订阅？</span><span class="sxs-lookup"><span data-stu-id="6072a-141">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="6072a-142">如果从 GoDaddy 或另一合作伙伴购买订阅，则必须转到 GoDaddy/合作伙伴管理控制台，才能将新别名设置为主要。</span><span class="sxs-lookup"><span data-stu-id="6072a-142">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>

## <a name="sending-email-from-the-proxy-address-easily"></a><span data-ttu-id="6072a-143">轻松地从代理地址发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="6072a-143">Sending email from the proxy address easily</span></span>

<span data-ttu-id="6072a-144">2021 年 7 月推出一项新功能，允许用户在使用别名时轻松Outlook 网页版。</span><span class="sxs-lookup"><span data-stu-id="6072a-144">A new feature is rolling out in July 2021 that allows users to send from their aliases easily when using Outlook on the web.</span></span> <span data-ttu-id="6072a-145">当功能推出到租户管理员使用 cmdlet 的租赁时，租户内的用户将有权访问复选框列表，其中每个条目对应其 Outlook 设置中的别名。 `Set-OrganizationConfig -SendFromAliasEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="6072a-145">When the feature rolls out to a tenancy where the tenant admin uses the `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, users within the tenancy will get access to a list of checkboxes where each entry corresponds to an alias in their Outlook settings.</span></span> <span data-ttu-id="6072a-146">选择别名将使其出现在"撰写"窗体的"自"下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="6072a-146">Selecting an alias will make it appear in the From dropdown in the Compose form.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="6072a-147">相关内容</span><span class="sxs-lookup"><span data-stu-id="6072a-147">Related content</span></span>

<span data-ttu-id="6072a-148">[本文介绍的不同地址 (](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) 发送电子邮件) </span><span class="sxs-lookup"><span data-stu-id="6072a-148">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>

<span data-ttu-id="6072a-149">[更改用户名称和电子邮件地址 (](../add-users/change-a-user-name-and-email-address.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="6072a-149">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>

<span data-ttu-id="6072a-150">[在 Microsoft 365 中配置电子邮件转发](configure-email-forwarding.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="6072a-150">[Configure email forwarding in Microsoft 365](configure-email-forwarding.md) (article)</span></span>
