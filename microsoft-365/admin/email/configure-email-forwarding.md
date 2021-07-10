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
ms.openlocfilehash: 9d645c2b36bdac2ab53dcb8af4ff6ebdbd0ee601
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363787"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="9600c-103">配置电子邮件转发Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9600c-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="9600c-104">作为组织的管理员，您可能有公司要求为用户邮箱设置电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="9600c-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="9600c-105">通过电子邮件转发，你可以将发送到用户邮箱的电子邮件转发到组织内部或外部的其他用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="9600c-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9600c-106">您可以使用出站垃圾邮件筛选器策略来控制自动转发给外部收件人。</span><span class="sxs-lookup"><span data-stu-id="9600c-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="9600c-107">有关详细信息，请参阅在邮件中[控制自动外部电子邮件Microsoft 365。](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)</span><span class="sxs-lookup"><span data-stu-id="9600c-107">For more information, see [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="9600c-108">配置电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="9600c-108">Configure email forwarding</span></span>

<span data-ttu-id="9600c-109">在设置电子邮件转发之前，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="9600c-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="9600c-110">允许向远程域用户自动转发邮件。</span><span class="sxs-lookup"><span data-stu-id="9600c-110">Allow automatically forwarded messages to be sent to people on the remote domain.</span></span> <span data-ttu-id="9600c-111">有关详细信息 [，请参阅管理](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) 远程域。</span><span class="sxs-lookup"><span data-stu-id="9600c-111">See [Manage remote domains](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) for details.</span></span>

- <span data-ttu-id="9600c-112">设置电子邮件转发后，只会转发发送到从邮箱发送的新电子邮件。 </span><span class="sxs-lookup"><span data-stu-id="9600c-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="9600c-113">电子邮件转发要求 from  *帐户*  具有许可证。</span><span class="sxs-lookup"><span data-stu-id="9600c-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="9600c-114">如果由于用户已离开组织而设置电子邮件转发，另一个选项是将其邮箱 [转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="9600c-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="9600c-115">这样一来，多个人员就可以访问它。</span><span class="sxs-lookup"><span data-stu-id="9600c-115">This way several people can access it.</span></span> <span data-ttu-id="9600c-116">但是，共享邮箱不能超过 50GB。</span><span class="sxs-lookup"><span data-stu-id="9600c-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="9600c-117">您必须是管理员Exchange全局管理员Microsoft 365才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="9600c-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="9600c-118">有关详细信息，请参阅关于 [管理员角色的主题](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="9600c-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9600c-119">在管理中心，转到"用户 \> **[""活动用户"](https://go.microsoft.com/fwlink/p/?linkid=834822)** 页面。</span><span class="sxs-lookup"><span data-stu-id="9600c-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="9600c-120">选择要转发其电子邮件的用户的名称，然后打开属性页。</span><span class="sxs-lookup"><span data-stu-id="9600c-120">Select the name of the user whose email you want to forward, then open the properties page.</span></span>

3. <span data-ttu-id="9600c-121">在"**邮件"** 选项卡上，选择 **"管理电子邮件转发"。**</span><span class="sxs-lookup"><span data-stu-id="9600c-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="9600c-122">在"电子邮件转发"页面上，选择"转发发送到此邮箱的所有电子邮件"，输入转发地址，然后选择是否要保留转发电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="9600c-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="9600c-123">如果看不到此选项，请确保将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9600c-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="9600c-124">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="9600c-124">Select **Save changes**.</span></span>

    <span data-ttu-id="9600c-125">**若要转发到多个电子邮件地址**，可以要求用户在邮箱中设置Outlook转发到地址。</span><span class="sxs-lookup"><span data-stu-id="9600c-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> 
    
    1.  <span data-ttu-id="9600c-126">打开 **Outlook** > **主页** > **规则**>选择"管理&**通知"**  </span><span class="sxs-lookup"><span data-stu-id="9600c-126">Open **outlook** > **Home** >  **Rules** > Select **Manage Rules & Alerts**</span></span>
    1. <span data-ttu-id="9600c-127">选择 **"新建** > **规则" 选择"** 在列表底部附近收到的邮件上应用规则"，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="9600c-127">Select **New Rule** > **Select Apply rule on message I receive** located near bottom of list, then click **Next**.</span></span>
    1. <span data-ttu-id="9600c-128">当 **系统** 询问"是"时，单击"是"：此规则将应用于你收到的每封邮件。</span><span class="sxs-lookup"><span data-stu-id="9600c-128">Click **Yes** when asked This rule will be applied to every message you receive.</span></span> 
    1. <span data-ttu-id="9600c-129">On the next list select the actions **redirect it to people or public group** and stop processing more **rules**</span><span class="sxs-lookup"><span data-stu-id="9600c-129">On the next list select the actions **redirect it to people or public group** and **stop processing more rules**</span></span>
    1. <span data-ttu-id="9600c-130">单击窗口 **底部带下划线** 的短语"人员"或"公共组"。</span><span class="sxs-lookup"><span data-stu-id="9600c-130">Click the underlined phrase **people or public group** in the bottom part of window.</span></span>
    1. <span data-ttu-id="9600c-131">在 **"收件人"** 字段中键入要转发邮件的电子邮件地址，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="9600c-131">Type the **email address** to forward mail to in the To field, then click **OK**.</span></span>
    1. <span data-ttu-id="9600c-132">选择 **"完成"**</span><span class="sxs-lookup"><span data-stu-id="9600c-132">Select **Finish**</span></span>
    

     <span data-ttu-id="9600c-133">或者，在管理中心创建通讯[](../setup/create-distribution-lists.md)组，将地址添加到[](add-user-or-contact-to-distribution-list.md)该组，然后按照本文中的说明将转发设置为指向 DL。</span><span class="sxs-lookup"><span data-stu-id="9600c-133">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="9600c-134">请勿删除要转发的电子邮件用户的帐户，或删除其许可证！</span><span class="sxs-lookup"><span data-stu-id="9600c-134">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="9600c-135">如果这样做，电子邮件转发将停止。</span><span class="sxs-lookup"><span data-stu-id="9600c-135">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9600c-136">在管理中心，转到"用户 \> **[""活动用户"](https://go.microsoft.com/fwlink/p/?linkid=847686)** 页面。</span><span class="sxs-lookup"><span data-stu-id="9600c-136">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="9600c-137">选择要转发其电子邮件的用户的名称，以打开属性页。</span><span class="sxs-lookup"><span data-stu-id="9600c-137">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="9600c-138">展开 **"邮件设置**"，然后在"电子邮件 **转发"部分**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="9600c-138">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="9600c-139">在电子邮件转发页面上，将切换设置为 **"** 打开"，输入转发地址，然后选择是否要保留转发电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="9600c-139">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="9600c-140">如果看不到此选项，请确保将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9600c-140">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="9600c-141">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="9600c-141">Select **Save**.</span></span>

   <span data-ttu-id="9600c-142">**若要转发到多个电子邮件地址**，可以要求用户在邮箱中设置Outlook转发到地址。</span><span class="sxs-lookup"><span data-stu-id="9600c-142">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="9600c-143">若要了解更多信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="9600c-143">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="9600c-144">或者，在管理中心创建通讯[](../setup/create-distribution-lists.md)组，将地址添加到[](add-user-or-contact-to-distribution-list.md)该组，然后按照本文中的说明将转发设置为指向 DL。</span><span class="sxs-lookup"><span data-stu-id="9600c-144">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="9600c-145">请勿删除要转发的电子邮件用户的帐户，或删除其许可证！</span><span class="sxs-lookup"><span data-stu-id="9600c-145">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="9600c-146">如果这样做，电子邮件转发将停止。</span><span class="sxs-lookup"><span data-stu-id="9600c-146">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9600c-147">在管理中心，转到"用户 \> **[""活动用户"](https://go.microsoft.com/fwlink/p/?linkid=850628)** 页面。</span><span class="sxs-lookup"><span data-stu-id="9600c-147">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="9600c-148">选择要转发其电子邮件的用户的名称，以打开属性页。</span><span class="sxs-lookup"><span data-stu-id="9600c-148">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="9600c-149">展开 **"邮件设置**"，然后在"电子邮件 **转发"部分**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="9600c-149">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="9600c-150">在电子邮件转发页面上，将切换设置为 **"** 打开"，输入转发地址，然后选择是否要保留转发电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="9600c-150">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="9600c-151">如果看不到此选项，请确保将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9600c-151">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="9600c-152">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="9600c-152">Select **Save**.</span></span>

   <span data-ttu-id="9600c-153">**若要转发到多个电子邮件地址**，可以要求用户在邮箱中设置Outlook转发到地址。</span><span class="sxs-lookup"><span data-stu-id="9600c-153">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="9600c-154">若要了解更多信息，请参阅 [使用规则自动转发邮件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="9600c-154">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="9600c-155">或者，在管理中心创建通讯[](../setup/create-distribution-lists.md)组，将地址添加到[](add-user-or-contact-to-distribution-list.md)该组，然后按照本文中的说明将转发设置为指向 DL。</span><span class="sxs-lookup"><span data-stu-id="9600c-155">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="9600c-156">请勿删除要转发的电子邮件用户的帐户，或删除其许可证！</span><span class="sxs-lookup"><span data-stu-id="9600c-156">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span> <span data-ttu-id="9600c-157">如果这样做，电子邮件转发将停止。</span><span class="sxs-lookup"><span data-stu-id="9600c-157">If you do, email forwarding will stop.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="9600c-158">相关内容</span><span class="sxs-lookup"><span data-stu-id="9600c-158">Related content</span></span> 

<span data-ttu-id="9600c-159">[Create a shared mailbox (](../email/create-a-shared-mailbox.md) article) </span><span class="sxs-lookup"><span data-stu-id="9600c-159">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="9600c-160">[从不同地址发送电子邮件， (](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) 文章) </span><span class="sxs-lookup"><span data-stu-id="9600c-160">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>\
<span data-ttu-id="9600c-161">[更改用户名称和电子邮件地址 (](../add-users/change-a-user-name-and-email-address.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="9600c-161">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>
