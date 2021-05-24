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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: 电子邮件转发允许您将发送到用户邮箱Microsoft 365电子邮件转发到组织内部或外部的另一个邮箱。
ms.openlocfilehash: eb72204211a8eff929c024fbcede66dfe1f4b879
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635482"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="b5393-103">配置电子邮件转发Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b5393-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="b5393-104">作为组织的管理员，您可能有公司要求为用户邮箱设置电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="b5393-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="b5393-105">通过电子邮件转发，你可以将发送到用户邮箱的电子邮件转发到组织内部或外部的其他用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="b5393-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5393-106">您可以使用出站垃圾邮件筛选器策略来控制自动转发给外部收件人。</span><span class="sxs-lookup"><span data-stu-id="b5393-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="b5393-107">有关详细信息，请参阅在邮件中[控制自动外部电子邮件Microsoft 365。](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)</span><span class="sxs-lookup"><span data-stu-id="b5393-107">For more information, see [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="b5393-108">配置电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="b5393-108">Configure email forwarding</span></span>

<span data-ttu-id="b5393-109">在设置电子邮件转发之前，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="b5393-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="b5393-110">设置电子邮件转发后，只会转发发送到从邮箱发送的新电子邮件。 </span><span class="sxs-lookup"><span data-stu-id="b5393-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="b5393-111">电子邮件转发要求 from  *帐户*  具有许可证。</span><span class="sxs-lookup"><span data-stu-id="b5393-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="b5393-112">如果由于用户已离开组织而设置电子邮件转发，另一个选项是将其邮箱 [转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="b5393-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="b5393-113">这样一来，多个人员就可以访问它。</span><span class="sxs-lookup"><span data-stu-id="b5393-113">This way several people can access it.</span></span> <span data-ttu-id="b5393-114">但是，共享邮箱不能超过 50GB。</span><span class="sxs-lookup"><span data-stu-id="b5393-114">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="b5393-115">您必须是管理员Exchange全局管理员Microsoft 365才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="b5393-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="b5393-116">有关详细信息，请参阅关于 [管理员角色的主题](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="b5393-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="b5393-117">在管理中心，转到"用户 \> **[""活动用户"](https://go.microsoft.com/fwlink/p/?linkid=834822)** 页面。</span><span class="sxs-lookup"><span data-stu-id="b5393-117">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="b5393-118">选择要转发其电子邮件的用户的名称，然后打开属性页。</span><span class="sxs-lookup"><span data-stu-id="b5393-118">Select the name of the user whose email you want to forward, then open the properties page.</span></span>

3. <span data-ttu-id="b5393-119">在"**邮件"** 选项卡上，选择 **"管理电子邮件转发"。**</span><span class="sxs-lookup"><span data-stu-id="b5393-119">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="b5393-120">在"电子邮件转发"页面上，选择"转发发送到此邮箱的所有电子邮件"，输入转发地址，然后选择是否要保留转发电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="b5393-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="b5393-121">如果看不到此选项，请确保将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b5393-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="b5393-122">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="b5393-122">Select **Save changes**.</span></span>

    <span data-ttu-id="b5393-123">**若要转发到多个电子邮件地址**，可以要求用户在邮箱中设置Outlook转发到地址。</span><span class="sxs-lookup"><span data-stu-id="b5393-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="b5393-124">若要了解更多信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="b5393-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="b5393-125">或者，在管理中心创建通讯[](../setup/create-distribution-lists.md)组，将地址添加到[](add-user-or-contact-to-distribution-list.md)该组，然后按照本文中的说明将转发设置为指向 DL。</span><span class="sxs-lookup"><span data-stu-id="b5393-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="b5393-126">请勿删除要转发的电子邮件用户的帐户，或删除其许可证！</span><span class="sxs-lookup"><span data-stu-id="b5393-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="b5393-127">如果这样做，电子邮件转发将停止。</span><span class="sxs-lookup"><span data-stu-id="b5393-127">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b5393-128">在管理中心，转到"用户 \> **[""活动用户"](https://go.microsoft.com/fwlink/p/?linkid=847686)** 页面。</span><span class="sxs-lookup"><span data-stu-id="b5393-128">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="b5393-129">选择要转发其电子邮件的用户的名称，以打开属性页。</span><span class="sxs-lookup"><span data-stu-id="b5393-129">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="b5393-130">展开 **"邮件设置**"，然后在"电子邮件 **转发"部分**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="b5393-130">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="b5393-131">在电子邮件转发页面上，将切换设置为 **"** 打开"，输入转发地址，然后选择是否要保留转发电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="b5393-131">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="b5393-132">如果看不到此选项，请确保将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b5393-132">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="b5393-133">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b5393-133">Select **Save**.</span></span>

   <span data-ttu-id="b5393-134">**若要转发到多个电子邮件地址**，可以要求用户在邮箱中设置Outlook转发到地址。</span><span class="sxs-lookup"><span data-stu-id="b5393-134">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="b5393-135">若要了解更多信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="b5393-135">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="b5393-136">或者，在管理中心创建通讯[](../setup/create-distribution-lists.md)组，将地址添加到[](add-user-or-contact-to-distribution-list.md)该组，然后按照本文中的说明将转发设置为指向 DL。</span><span class="sxs-lookup"><span data-stu-id="b5393-136">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="b5393-137">请勿删除要转发的电子邮件用户的帐户，或删除其许可证！</span><span class="sxs-lookup"><span data-stu-id="b5393-137">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="b5393-138">如果这样做，电子邮件转发将停止。</span><span class="sxs-lookup"><span data-stu-id="b5393-138">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b5393-139">在管理中心，转到"用户 \> **[""活动用户"](https://go.microsoft.com/fwlink/p/?linkid=850628)** 页面。</span><span class="sxs-lookup"><span data-stu-id="b5393-139">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="b5393-140">选择要转发其电子邮件的用户的名称，以打开属性页。</span><span class="sxs-lookup"><span data-stu-id="b5393-140">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="b5393-141">展开 **"邮件设置**"，然后在"电子邮件 **转发"部分**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="b5393-141">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="b5393-142">在电子邮件转发页面上，将切换设置为 **"** 打开"，输入转发地址，然后选择是否要保留转发电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="b5393-142">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="b5393-143">如果看不到此选项，请确保将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b5393-143">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="b5393-144">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b5393-144">Select **Save**.</span></span>

   <span data-ttu-id="b5393-145">**若要转发到多个电子邮件地址**，可以要求用户在邮箱中设置Outlook转发到地址。</span><span class="sxs-lookup"><span data-stu-id="b5393-145">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="b5393-146">若要了解更多信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="b5393-146">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="b5393-147">或者，在管理中心创建通讯[](../setup/create-distribution-lists.md)组，将地址添加到[](add-user-or-contact-to-distribution-list.md)该组，然后按照本文中的说明将转发设置为指向 DL。</span><span class="sxs-lookup"><span data-stu-id="b5393-147">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="b5393-148">请勿删除要转发的电子邮件用户的帐户，或删除其许可证！</span><span class="sxs-lookup"><span data-stu-id="b5393-148">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span> <span data-ttu-id="b5393-149">如果这样做，电子邮件转发将停止。</span><span class="sxs-lookup"><span data-stu-id="b5393-149">If you do, email forwarding will stop.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="b5393-150">相关内容</span><span class="sxs-lookup"><span data-stu-id="b5393-150">Related content</span></span> 

<span data-ttu-id="b5393-151">[Create a shared mailbox (](../email/create-a-shared-mailbox.md) article) </span><span class="sxs-lookup"><span data-stu-id="b5393-151">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="b5393-152">[从不同地址发送电子邮件， (](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) 文章) </span><span class="sxs-lookup"><span data-stu-id="b5393-152">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>\
<span data-ttu-id="b5393-153">[更改用户名称和电子邮件地址 (](../add-users/change-a-user-name-and-email-address.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="b5393-153">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>

