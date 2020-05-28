---
title: 配置电子邮件转发
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
ms.openlocfilehash: 72eca099f0c7e60efe8f616dfe23201cd46975cf
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400120"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="c2c45-103">配置电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="c2c45-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c2c45-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="c2c45-104">The admin center is changing.</span></span> <span data-ttu-id="c2c45-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="c2c45-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="c2c45-106">作为组织的管理员，您可能需要为用户的邮箱设置电子邮件转发功能的公司要求。</span><span class="sxs-lookup"><span data-stu-id="c2c45-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="c2c45-107">通过电子邮件转发，可以将发送到用户邮箱的电子邮件转发到组织内部或外部的其他用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="c2c45-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="c2c45-108">配置电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="c2c45-108">Configure email forwarding</span></span>

 <span data-ttu-id="c2c45-109">在设置电子邮件转发之前，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="c2c45-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="c2c45-110">一旦设置了电子邮件转发，只有发送到*发件人*邮箱的**新**电子邮件才会 fowarded。</span><span class="sxs-lookup"><span data-stu-id="c2c45-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="c2c45-111">电子邮件转发要求 "*发件人*" 帐户具有许可证。</span><span class="sxs-lookup"><span data-stu-id="c2c45-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="c2c45-112">如果你正在设置电子邮件转发，因为用户已离开你的组织，另一种方法是[将其邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="c2c45-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="c2c45-113">通过这种方式，多个人可以对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="c2c45-113">This way several people can access it.</span></span> <span data-ttu-id="c2c45-114">但是，共享邮箱不能超过50GB。</span><span class="sxs-lookup"><span data-stu-id="c2c45-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="c2c45-115">您必须是 Microsoft 365 中的 Exchange 管理员或全局管理员才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c2c45-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="c2c45-116">有关详细信息，请参阅[有关管理员角色](../add-users/about-admin-roles.md)的主题。</span><span class="sxs-lookup"><span data-stu-id="c2c45-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="c2c45-117">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="c2c45-117">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="c2c45-118">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c2c45-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="c2c45-119">选择要将其电子邮件转发到的用户的名称，以打开 "属性" 页。</span><span class="sxs-lookup"><span data-stu-id="c2c45-119">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="c2c45-120">在 "**邮件**" 选项卡上，选择 "**管理电子邮件转发**"。</span><span class="sxs-lookup"><span data-stu-id="c2c45-120">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="c2c45-121">在 "电子邮件转发" 页面上，选择 "**转发所有发送到此邮箱的电子邮件**"，输入转发地址，然后选择是否要保留转发的电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="c2c45-121">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c2c45-122">如果看不到此选项，请确保将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c2c45-122">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c2c45-123">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="c2c45-123">Select **Save changes**.</span></span>
    
    <span data-ttu-id="c2c45-124">**若要转发到多个电子邮件地址**，您可以要求用户在 Outlook 中设置一条规则，以转发到地址。</span><span class="sxs-lookup"><span data-stu-id="c2c45-124">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c2c45-125">若要了解详细信息，请参阅[使用规则自动转发邮件](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="c2c45-125">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="c2c45-126">或者，在 "管理中心" 中，[创建一个通讯组](../setup/create-distribution-lists.md)，[向其添加地址](add-user-or-contact-to-distribution-list.md)，然后使用本文中的说明将 "转发" 设置为指向 DL。</span><span class="sxs-lookup"><span data-stu-id="c2c45-126">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="c2c45-127">请勿删除要转发的电子邮件的用户帐户或删除其许可证！</span><span class="sxs-lookup"><span data-stu-id="c2c45-127">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="c2c45-128">如果这样做，电子邮件转发将停止。</span><span class="sxs-lookup"><span data-stu-id="c2c45-128">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="c2c45-129">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c2c45-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="c2c45-130">选择要将其电子邮件转发到的用户的名称，以打开 "属性" 页。</span><span class="sxs-lookup"><span data-stu-id="c2c45-130">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="c2c45-131">展开 "**邮件设置**"，然后在 "**电子邮件转发**" 部分，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="c2c45-131">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="c2c45-132">在 "电子邮件转发" 页面上，将 "切换到" 设置为 **"开**"，输入转发地址，然后选择是否要保留转发的电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="c2c45-132">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c2c45-133">如果看不到此选项，请确保将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c2c45-133">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c2c45-134">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c2c45-134">Select **Save**.</span></span>
    
    <span data-ttu-id="c2c45-135">**若要转发到多个电子邮件地址**，您可以要求用户在 Outlook 中设置一条规则，以转发到地址。</span><span class="sxs-lookup"><span data-stu-id="c2c45-135">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c2c45-136">若要了解详细信息，请参阅[使用规则自动转发邮件](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="c2c45-136">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="c2c45-137">或者，在 "管理中心" 中，[创建一个通讯组](../setup/create-distribution-lists.md)，[向其添加地址](add-user-or-contact-to-distribution-list.md)，然后使用本文中的说明将 "转发" 设置为指向 DL。</span><span class="sxs-lookup"><span data-stu-id="c2c45-137">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="c2c45-138">请勿删除要转发的电子邮件的用户帐户或删除其许可证！</span><span class="sxs-lookup"><span data-stu-id="c2c45-138">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="c2c45-139">如果这样做，电子邮件转发将停止。</span><span class="sxs-lookup"><span data-stu-id="c2c45-139">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="c2c45-140">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c2c45-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="c2c45-141">选择要将其电子邮件转发到的用户的名称，以打开 "属性" 页。</span><span class="sxs-lookup"><span data-stu-id="c2c45-141">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="c2c45-142">展开 "**邮件设置**"，然后在 "**电子邮件转发**" 部分，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="c2c45-142">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="c2c45-143">在 "电子邮件转发" 页面上，将 "切换到" 设置为 **"开**"，输入转发地址，然后选择是否要保留转发的电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="c2c45-143">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c2c45-144">如果看不到此选项，请确保将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c2c45-144">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c2c45-145">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c2c45-145">Select **Save**.</span></span>
    
    <span data-ttu-id="c2c45-146">**若要转发到多个电子邮件地址**，您可以要求用户在 Outlook 中设置一条规则，以转发到地址。</span><span class="sxs-lookup"><span data-stu-id="c2c45-146">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c2c45-147">若要了解详细信息，请参阅[使用规则自动转发邮件](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="c2c45-147">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="c2c45-148">或者，在 "管理中心" 中，[创建一个通讯组](../setup/create-distribution-lists.md)，[向其添加地址](add-user-or-contact-to-distribution-list.md)，然后使用本文中的说明将 "转发" 设置为指向 DL。</span><span class="sxs-lookup"><span data-stu-id="c2c45-148">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="c2c45-149">请勿删除要转发的电子邮件的用户帐户或删除其许可证！</span><span class="sxs-lookup"><span data-stu-id="c2c45-149">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="c2c45-150">如果这样做，电子邮件转发将停止。</span><span class="sxs-lookup"><span data-stu-id="c2c45-150">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
