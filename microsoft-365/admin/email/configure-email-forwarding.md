---
title: 配置电子邮件转发
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
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: 使用 Office365 设置向一个或多个电子邮件帐户转发电子邮件。
ms.openlocfilehash: c821d4363a053b432c4376d7b4fec4926df7b568
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560788"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="8f9de-103">配置电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="8f9de-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8f9de-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="8f9de-104">The admin center is changing.</span></span> <span data-ttu-id="8f9de-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="8f9de-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="8f9de-106">作为组织的管理员，您可能需要为用户的邮箱设置电子邮件转发功能的公司要求。</span><span class="sxs-lookup"><span data-stu-id="8f9de-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="8f9de-107">通过电子邮件转发，可以将发送到用户邮箱的电子邮件转发到组织内部或外部的其他用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="8f9de-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f9de-108">您可以使用出站垃圾邮件筛选器策略来控制自动转发到外部收件人。</span><span class="sxs-lookup"><span data-stu-id="8f9de-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="8f9de-109">有关详细信息，请参阅 [在 Microsoft 365 中控制自动外部电子邮件转发](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)。</span><span class="sxs-lookup"><span data-stu-id="8f9de-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="8f9de-110">配置电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="8f9de-110">Configure email forwarding</span></span>

 <span data-ttu-id="8f9de-111">在设置电子邮件转发之前，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="8f9de-111">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="8f9de-112">一旦设置了电子邮件转发，则只会转发发送到 "*发件人*" 邮箱的 **新** 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8f9de-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span> 
    
- <span data-ttu-id="8f9de-113">电子邮件转发要求 "  *发件人*  " 帐户具有许可证。</span><span class="sxs-lookup"><span data-stu-id="8f9de-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="8f9de-114">如果你正在设置电子邮件转发，因为用户已离开你的组织，另一种方法是 [将其邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="8f9de-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="8f9de-115">通过这种方式，多个人可以对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="8f9de-115">This way several people can access it.</span></span> <span data-ttu-id="8f9de-116">但是，共享邮箱不能超过50GB。</span><span class="sxs-lookup"><span data-stu-id="8f9de-116">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="8f9de-117">您必须是 Microsoft 365 中的 Exchange 管理员或全局管理员才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="8f9de-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="8f9de-118">有关详细信息，请参阅 [有关管理员角色](../add-users/about-admin-roles.md)的主题。</span><span class="sxs-lookup"><span data-stu-id="8f9de-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8f9de-119">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="8f9de-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="8f9de-120">选择要将其电子邮件转发到的用户的名称，以打开 "属性" 页。</span><span class="sxs-lookup"><span data-stu-id="8f9de-120">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="8f9de-121">在 " **邮件** " 选项卡上，选择 " **管理电子邮件转发**"。</span><span class="sxs-lookup"><span data-stu-id="8f9de-121">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="8f9de-122">在 "电子邮件转发" 页面上，选择 " **转发所有发送到此邮箱的电子邮件**"，输入转发地址，然后选择是否要保留转发的电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="8f9de-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="8f9de-123">如果看不到此选项，请确保将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8f9de-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="8f9de-124">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="8f9de-124">Select **Save changes**.</span></span>
    
    <span data-ttu-id="8f9de-125">**若要转发到多个电子邮件地址**，您可以要求用户在 Outlook 中设置一条规则，以转发到地址。</span><span class="sxs-lookup"><span data-stu-id="8f9de-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="8f9de-126">若要了解详细信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="8f9de-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="8f9de-127">或者，在 "管理中心" 中， [创建一个通讯组](../setup/create-distribution-lists.md)， [向其添加地址](add-user-or-contact-to-distribution-list.md)，然后使用本文中的说明将 "转发" 设置为指向 DL。</span><span class="sxs-lookup"><span data-stu-id="8f9de-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="8f9de-128">请勿删除要转发的电子邮件的用户帐户或删除其许可证！</span><span class="sxs-lookup"><span data-stu-id="8f9de-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="8f9de-129">如果这样做，电子邮件转发将停止。</span><span class="sxs-lookup"><span data-stu-id="8f9de-129">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="8f9de-130">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="8f9de-130">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="8f9de-131">选择要将其电子邮件转发到的用户的名称，以打开 "属性" 页。</span><span class="sxs-lookup"><span data-stu-id="8f9de-131">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="8f9de-132">展开 " **邮件设置**"，然后在 " **电子邮件转发** " 部分，选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="8f9de-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="8f9de-133">在 "电子邮件转发" 页面上，将 "切换到" 设置为 **"开**"，输入转发地址，然后选择是否要保留转发的电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="8f9de-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="8f9de-134">如果看不到此选项，请确保将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8f9de-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="8f9de-135">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8f9de-135">Select **Save**.</span></span>
    
    <span data-ttu-id="8f9de-136">**若要转发到多个电子邮件地址**，您可以要求用户在 Outlook 中设置一条规则，以转发到地址。</span><span class="sxs-lookup"><span data-stu-id="8f9de-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="8f9de-137">若要了解详细信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="8f9de-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="8f9de-138">或者，在 "管理中心" 中， [创建一个通讯组](../setup/create-distribution-lists.md)， [向其添加地址](add-user-or-contact-to-distribution-list.md)，然后使用本文中的说明将 "转发" 设置为指向 DL。</span><span class="sxs-lookup"><span data-stu-id="8f9de-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="8f9de-139">请勿删除要转发的电子邮件的用户帐户或删除其许可证！</span><span class="sxs-lookup"><span data-stu-id="8f9de-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="8f9de-140">如果这样做，电子邮件转发将停止。</span><span class="sxs-lookup"><span data-stu-id="8f9de-140">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="8f9de-141">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="8f9de-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="8f9de-142">选择要将其电子邮件转发到的用户的名称，以打开 "属性" 页。</span><span class="sxs-lookup"><span data-stu-id="8f9de-142">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="8f9de-143">展开 " **邮件设置**"，然后在 " **电子邮件转发** " 部分，选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="8f9de-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="8f9de-144">在 "电子邮件转发" 页面上，将 "切换到" 设置为 **"开**"，输入转发地址，然后选择是否要保留转发的电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="8f9de-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="8f9de-145">如果看不到此选项，请确保将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8f9de-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="8f9de-146">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8f9de-146">Select **Save**.</span></span>
    
    <span data-ttu-id="8f9de-147">**若要转发到多个电子邮件地址**，您可以要求用户在 Outlook 中设置一条规则，以转发到地址。</span><span class="sxs-lookup"><span data-stu-id="8f9de-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="8f9de-148">若要了解详细信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="8f9de-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="8f9de-149">或者，在 "管理中心" 中， [创建一个通讯组](../setup/create-distribution-lists.md)， [向其添加地址](add-user-or-contact-to-distribution-list.md)，然后使用本文中的说明将 "转发" 设置为指向 DL。</span><span class="sxs-lookup"><span data-stu-id="8f9de-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="8f9de-150">请勿删除要转发的电子邮件的用户帐户或删除其许可证！</span><span class="sxs-lookup"><span data-stu-id="8f9de-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="8f9de-151">如果这样做，电子邮件转发将停止。</span><span class="sxs-lookup"><span data-stu-id="8f9de-151">If you do, email forwarding will stop.</span></span> 


::: moniker-end 
