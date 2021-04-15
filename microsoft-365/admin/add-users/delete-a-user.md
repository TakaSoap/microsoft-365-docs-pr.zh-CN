---
title: 从组织删除用户
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
- SPO_Content
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: 了解如何删除用户帐户。 决定使用用户电子邮件和 OneDrive 内容应执行哪些操作。 并决定是保留产品许可证还是停止付费。
ms.openlocfilehash: 0069577b83c318fa57eaceddccc93b5832e634e0
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755548"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="04389-105">从组织删除用户</span><span class="sxs-lookup"><span data-stu-id="04389-105">Delete a user from your organization</span></span>
  
<span data-ttu-id="04389-106">**正在查找 *如何删除你在* 工作或学校使用自己的 Microsoft 365 用户帐户？请与工作或大学中的技术支持人员联系，以执行这些步骤。**</span><span class="sxs-lookup"><span data-stu-id="04389-106">**Looking for how to delete your *own* Microsoft 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>

## <a name="what-you-need-to-know-about-deleting-users"></a><span data-ttu-id="04389-107">删除用户需知事项</span><span class="sxs-lookup"><span data-stu-id="04389-107">What you need to know about deleting users</span></span>

- <span data-ttu-id="04389-108">只有具有 [Microsoft 365 全局管理员](about-admin-roles.md) 或企业或学校的用户管理权限的用户才能删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="04389-108">Only people who have [Microsoft 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span>
- <span data-ttu-id="04389-109">永久删除用户数据前 30 天内可[还原](restore-user.md)帐户。</span><span class="sxs-lookup"><span data-stu-id="04389-109">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span>
- <span data-ttu-id="04389-110">若要保留用户的 OneDrive 数据，请将其移动到其他位置。</span><span class="sxs-lookup"><span data-stu-id="04389-110">If you want to keep the user's OneDrive data, move it to a different location.</span></span> <span data-ttu-id="04389-111">您甚至可以在删除帐户后最多 30 天移动数据。</span><span class="sxs-lookup"><span data-stu-id="04389-111">You can even move the data up to 30 days after deleting the account.</span></span> <span data-ttu-id="04389-112">请参阅[访问并备份以往用户的数据](get-access-to-and-back-up-a-former-user-s-data.md)。</span><span class="sxs-lookup"><span data-stu-id="04389-112">See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span> <span data-ttu-id="04389-113">无需移动其 SharePoint 文件；仍将有权访问它们。</span><span class="sxs-lookup"><span data-stu-id="04389-113">You don't need to move their SharePoint files; you'll still have access to them.</span></span>
- <span data-ttu-id="04389-p103">若要保留用户的电子邮件，请在删除帐户 **之前** ，将电子邮件移动到其他位置。如果已删除该帐户：如果删除时间未超过 30 天，可恢复该帐户，然后移动电子邮件数据，最后删除该帐户。请参阅 [访问并备份以往用户的数据](get-access-to-and-back-up-a-former-user-s-data.md)。</span><span class="sxs-lookup"><span data-stu-id="04389-p103">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
- <span data-ttu-id="04389-117">如果你有 Office 365 企业版 E3 等企业版订阅，则可以通过将已删除用户帐户的邮箱数据转换为非活动邮箱来 *保留该帐户的邮箱数据*。</span><span class="sxs-lookup"><span data-stu-id="04389-117">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="04389-118">若要了解详细信息，请参阅 [管理 Exchange Online 中的非活动邮箱](../../compliance/inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="04389-118">To learn more, see [Manage inactive mailboxes in Exchange Online](../../compliance/inactive-mailboxes-in-office-365.md).</span></span>

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="04389-119">全局管理员：删除用户、停止支付其许可证费用，然后选择使用电子邮件和 OneDrive 内容执行哪些操作</span><span class="sxs-lookup"><span data-stu-id="04389-119">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="04389-120">如果你是全局管理员，在删除用户时，还可以向其他用户授予访问其电子邮件的访问权限，并选择使用 OneDrive 内容执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="04389-120">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span>

### <a name="things-to-consider"></a><span data-ttu-id="04389-121">要考虑的事项...</span><span class="sxs-lookup"><span data-stu-id="04389-121">Things to consider...</span></span>

<span data-ttu-id="04389-122">开始之前，考虑想要使用用户的电子邮件和 OneDrive 内容，以及是想要保留许可证还是停止支付许可证费用。</span><span class="sxs-lookup"><span data-stu-id="04389-122">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|<span data-ttu-id="04389-123">项目</span><span class="sxs-lookup"><span data-stu-id="04389-123">Item</span></span> | <span data-ttu-id="04389-124">说明</span><span class="sxs-lookup"><span data-stu-id="04389-124">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="04389-125">产品许可证</span><span class="sxs-lookup"><span data-stu-id="04389-125">Product licenses</span></span>  <br/> |<span data-ttu-id="04389-126">你可以从用户中删除许可证，并从订阅中删除该许可证，以停止支付该许可证费用。</span><span class="sxs-lookup"><span data-stu-id="04389-126">You can remove the license from the user and remove it from your subscriptions to stop paying for that license.</span></span> <span data-ttu-id="04389-127">如果选择此选项，许可证将自动从订阅中删除。</span><span class="sxs-lookup"><span data-stu-id="04389-127">If you select this option, the license will be removed automatically from your subscriptions.</span></span>  <br/><br/> <span data-ttu-id="04389-128">**如果通过合作伙伴或** 批量许可购买了许可证，则不能删除该许可证。</span><span class="sxs-lookup"><span data-stu-id="04389-128">**You can't remove the license** if you bought it through a Partner or volume licensing.</span></span> <span data-ttu-id="04389-129">如果你为年度计划付费，或正在计费周期中，那么在承诺完成之前，你将无法从订阅中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="04389-129">If you're paying for an annual plan or if you're in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.</span></span>  <br/> |
|<span data-ttu-id="04389-130">OneDrive 内容</span><span class="sxs-lookup"><span data-stu-id="04389-130">OneDrive content</span></span>  <br/> |<span data-ttu-id="04389-131">如果用户将文件保存到 OneDrive，你可以向其他用户授予对这些文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="04389-131">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="04389-132">你需要在为 OneDrive 文件设置的保留期内移动想要保留的文件。</span><span class="sxs-lookup"><span data-stu-id="04389-132">You'll need to move the files you want to keep within the retention period that is set for OneDrive files.</span></span> <span data-ttu-id="04389-133">**默认情况下，保留期为 30 天。**</span><span class="sxs-lookup"><span data-stu-id="04389-133">**By default, the retention period is 30 days.**</span></span> <span data-ttu-id="04389-134">如果在删除用户后没有在保留期内移动文件，OneDrive 内容将永久删除。</span><span class="sxs-lookup"><span data-stu-id="04389-134">If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted.</span></span> <span data-ttu-id="04389-135">若要增加保留已删除帐户的 OneDrive 文件的天数，请参阅为已删除的用户设置 [OneDrive 保留期](/onedrive/set-retention)。</span><span class="sxs-lookup"><span data-stu-id="04389-135">To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span>  <br/><br/> <span data-ttu-id="04389-136">**重要说明！**</span><span class="sxs-lookup"><span data-stu-id="04389-136">**Important!**</span></span> <span data-ttu-id="04389-137">如果已删除的用户使用个人计算机从 SharePoint 和 OneDrive 下载文件，则你无法擦除存储在其计算机中的文件。</span><span class="sxs-lookup"><span data-stu-id="04389-137">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="04389-138">他们将继续有权访问从 OneDrive 同步的任何文件。</span><span class="sxs-lookup"><span data-stu-id="04389-138">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="04389-139">电子邮件</span><span class="sxs-lookup"><span data-stu-id="04389-139">Email</span></span>  <br/> | <span data-ttu-id="04389-140">向其他用户提供对已删除用户的电子邮件的访问权限会将已删除用户的邮箱转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="04389-140">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="04389-141">然后，新邮箱所有者可以访问邮箱并监视新电子邮件。</span><span class="sxs-lookup"><span data-stu-id="04389-141">The new mailbox owner can then access the mailbox and monitor for new email.</span></span> <span data-ttu-id="04389-142">还可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="04389-142">You'll also have the following options:</span></span>  <br/>  <br/><span data-ttu-id="04389-143">更改显示名称 - 建议更改显示名称，以便轻松识别"活动用户"列表中的 **共享** 邮箱。</span><span class="sxs-lookup"><span data-stu-id="04389-143">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the **Active users** list.</span></span>  <br/>  <span data-ttu-id="04389-144">启用自动答复 - 我们已经为用户撰写了一份很乐于回复的自动答复。</span><span class="sxs-lookup"><span data-stu-id="04389-144">Turn on automatic replies - We've already written a polite automatic reply for you.</span></span> <span data-ttu-id="04389-145">您可以向组织内部人员以及组织外部人员发送不同的自动答复。</span><span class="sxs-lookup"><span data-stu-id="04389-145">You can send different automatic replies to people within your organization and people from outside your organization.</span></span>  <br/> <br/> <span data-ttu-id="04389-146">清理别名 - 别名是用户的其他电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="04389-146">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="04389-147">某些组织不使用它们，因此，如果没有，则无需在这里执行任何其他工作。</span><span class="sxs-lookup"><span data-stu-id="04389-147">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="04389-148">如果用户具有别名，我们建议删除这些别名，以便可以重复使用这些电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="04389-148">If the user does have aliases, we recommend removing them so that you can reuse those email addresses.</span></span> <span data-ttu-id="04389-149">否则，在已删除邮箱的保留期过去之前，无法重复使用这些电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="04389-149">Otherwise, you can't reuse those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="04389-150">默认情况下，已删除的邮箱可恢复 30 天。</span><span class="sxs-lookup"><span data-stu-id="04389-150">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="04389-151">有关详细信息，请参阅删除  [或还原 Exchange Online 中的用户邮箱](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="04389-151">For more information, see  [Delete or restore user mailboxes in Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="04389-152">Active Directory</span><span class="sxs-lookup"><span data-stu-id="04389-152">Active Directory</span></span>  <br/> |<span data-ttu-id="04389-153">如果你的公司使用与 Azure AD 同步的 **Active Directory** ，则需要从 Active Directory 中删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="04389-153">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="04389-154">无法通过 Office 365 删除帐户。</span><span class="sxs-lookup"><span data-stu-id="04389-154">You can't do it through Office 365.</span></span> <span data-ttu-id="04389-155">有关说明，请参阅 [删除用户帐户](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="04389-155">For instructions, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>  <br/> |

### <a name="get-started"></a><span data-ttu-id="04389-156">入门</span><span class="sxs-lookup"><span data-stu-id="04389-156">Get started</span></span>

<span data-ttu-id="04389-157">由于指导体验将完成删除用户的步骤，下面介绍如何开始操作。</span><span class="sxs-lookup"><span data-stu-id="04389-157">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="04389-158">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="04389-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="04389-159">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="04389-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="04389-160">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="04389-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="04389-161">选择要删除的用户，然后选择"删除 **用户"。**</span><span class="sxs-lookup"><span data-stu-id="04389-161">Select the user that you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="04389-162">用户管理管理员：从 Office 365 中删除一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="04389-162">User management admin: Delete one or more users from Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04389-163">如果已将其转换为共享邮箱，或已设置该帐户的电子邮件转发[](../email/convert-user-mailbox-to-shared-mailbox.md)，请不要删除该用户帐户。</span><span class="sxs-lookup"><span data-stu-id="04389-163">Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account.</span></span> <span data-ttu-id="04389-164">这些函数仍然需要帐户。</span><span class="sxs-lookup"><span data-stu-id="04389-164">Those functions still need the account.</span></span> <span data-ttu-id="04389-165">共享邮箱不需要许可证。</span><span class="sxs-lookup"><span data-stu-id="04389-165">A shared mailbox doesn't require a license.</span></span> <span data-ttu-id="04389-166">如果已将帐户转换为共享邮箱，可以 [停止支付许可证费用](#stop-paying-for-the-license)。</span><span class="sxs-lookup"><span data-stu-id="04389-166">If you've converted the account to a shared mailbox you can [Stop paying for the license](#stop-paying-for-the-license).</span></span> <span data-ttu-id="04389-167">如果已设置帐户的电子邮件转发，则不能删除许可证。</span><span class="sxs-lookup"><span data-stu-id="04389-167">If you've set up email forwarding on the account, you can't remove the license.</span></span> <span data-ttu-id="04389-168">这样做将停止电子邮件转发并停用邮箱。</span><span class="sxs-lookup"><span data-stu-id="04389-168">Doing so will stop email forwarding and deactivate the mailbox.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="04389-169">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="04389-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="04389-170">选择要删除的用户的名称，选择"其他选项"" (...) "，然后选择"删除 **用户"。** </span><span class="sxs-lookup"><span data-stu-id="04389-170">Select the names of the users that you want to delete, select **More options** (**...**), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="04389-171">虽然删除了用户帐户， **但仍需要支付许可证费用**。</span><span class="sxs-lookup"><span data-stu-id="04389-171">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="04389-172">请参阅下一过程以停止支付许可证费用。</span><span class="sxs-lookup"><span data-stu-id="04389-172">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="04389-173">或者，你可以将许可证分配给其他用户。</span><span class="sxs-lookup"><span data-stu-id="04389-173">Or, you can assign the license to another user.</span></span> <span data-ttu-id="04389-174">它不会自动分配给某人。</span><span class="sxs-lookup"><span data-stu-id="04389-174">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="04389-175">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="04389-175">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="04389-176">选择要删除的用户的名称，在"批量操作"窗格中，选择"**删除用户"。** </span><span class="sxs-lookup"><span data-stu-id="04389-176">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="04389-177">虽然删除了用户帐户， **但仍需要支付许可证费用**。</span><span class="sxs-lookup"><span data-stu-id="04389-177">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="04389-178">请参阅下一过程以停止支付许可证费用。</span><span class="sxs-lookup"><span data-stu-id="04389-178">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="04389-179">或者，你可以将许可证分配给其他用户。</span><span class="sxs-lookup"><span data-stu-id="04389-179">Or, you can assign the license to another user.</span></span> <span data-ttu-id="04389-180">它不会自动分配给某人。</span><span class="sxs-lookup"><span data-stu-id="04389-180">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="04389-181">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="04389-181">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="04389-182">选择要删除的用户的名称，在"批量操作"窗格中，选择"**删除用户"。** </span><span class="sxs-lookup"><span data-stu-id="04389-182">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="04389-183">虽然删除了用户帐户， **但仍需要支付许可证费用**。</span><span class="sxs-lookup"><span data-stu-id="04389-183">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="04389-184">请参阅下一过程以停止支付许可证费用。</span><span class="sxs-lookup"><span data-stu-id="04389-184">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="04389-185">或者，你可以将许可证分配给其他用户。</span><span class="sxs-lookup"><span data-stu-id="04389-185">Or, you can assign the license to another user.</span></span> <span data-ttu-id="04389-186">它不会自动分配给某人。</span><span class="sxs-lookup"><span data-stu-id="04389-186">It won't be assigned to someone automatically.</span></span>

::: moniker-end

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="04389-187">停止支付许可证费用</span><span class="sxs-lookup"><span data-stu-id="04389-187">Stop paying for the license</span></span>

<span data-ttu-id="04389-188">减少许可证数量是一个单独的步骤，只有全局管理员或帐单管理员才能执行。</span><span class="sxs-lookup"><span data-stu-id="04389-188">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="04389-189">在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="04389-189">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span> <span data-ttu-id="04389-190">如果未看到此选项，则不是全局管理员或帐单管理员，无法执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="04389-190">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="04389-191">在 **"产品** "选项卡上，选择要删除其许可证的订阅。</span><span class="sxs-lookup"><span data-stu-id="04389-191">On the **Products** tab, select the subscription that you want to remove licenses for.</span></span>

3. <span data-ttu-id="04389-192">在订阅详细信息页面上，选择”**删除许可证**”。</span><span class="sxs-lookup"><span data-stu-id="04389-192">On the subscription details page, select **Remove licenses**.</span></span>

4. <span data-ttu-id="04389-193">在"**删除许可证"** 窗格中的"新数量"**下的**"许可证总数"框中，输入要用于此订阅的许可证总数。 </span><span class="sxs-lookup"><span data-stu-id="04389-193">In the **Remove licenses** pane, under **New quantity**, in the **Total licenses** box, enter the total number of licenses that you want for this subscription.</span></span> <span data-ttu-id="04389-194">例如，如果你有 100 个许可证，并且想要删除其中五个许可证，请输入 95。</span><span class="sxs-lookup"><span data-stu-id="04389-194">For example, if you have 100 licenses and you want to remove five of them, enter 95.</span></span>

5. <span data-ttu-id="04389-195">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="04389-195">Select **Save**.</span></span>

<span data-ttu-id="04389-196">稍后，当你完成将其他人添加到你的企业的步骤时，系统将提示你同时购买许可证，只需一个步骤！</span><span class="sxs-lookup"><span data-stu-id="04389-196">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="04389-197">在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">订阅</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="04389-197">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="04389-198">如果未看到此选项，则不是全局管理员或帐单管理员，无法执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="04389-198">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="04389-199">如果你有多个 (，请选择订阅选项) 然后选择添加 **/** 删除许可证以删除许可证，这样你才会支付许可证费用，直到聘用其他人。</span><span class="sxs-lookup"><span data-stu-id="04389-199">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="04389-200">稍后，当你完成将其他人添加到你的企业的步骤时，系统将提示你同时购买许可证，只需一个步骤！</span><span class="sxs-lookup"><span data-stu-id="04389-200">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="04389-201">在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">订阅</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="04389-201">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="04389-202">如果未看到此选项，则不是全局管理员或帐单管理员，无法执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="04389-202">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="04389-203">如果你有多个 (，请选择订阅选项) 然后选择添加 **/** 删除许可证以删除许可证，这样你才会支付许可证费用，直到聘用其他人。</span><span class="sxs-lookup"><span data-stu-id="04389-203">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="04389-204">稍后，当你完成将其他人添加到你的企业的步骤时，系统将提示你同时购买许可证，只需一个步骤！</span><span class="sxs-lookup"><span data-stu-id="04389-204">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="04389-205">同时删除多个用户</span><span class="sxs-lookup"><span data-stu-id="04389-205">Delete many users at the same time</span></span>

<span data-ttu-id="04389-206">请参阅 [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="04389-206">See the [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="04389-207">解决删除用户时遇到的问题</span><span class="sxs-lookup"><span data-stu-id="04389-207">Fix issues with deleting a user</span></span>

<span data-ttu-id="04389-208">以下是用户在删除用户时遇到的最常见问题：</span><span class="sxs-lookup"><span data-stu-id="04389-208">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="04389-209">**You get an error message along the lines of "User cannot be deleted.请稍后重试。"**</span><span class="sxs-lookup"><span data-stu-id="04389-209">**You get an error message along the lines of "User cannot be deleted. Please try again later."**</span></span> <span data-ttu-id="04389-210">仔细检查帐户是否设置了电子邮件转发，或者是否将其转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="04389-210">Double-check whether the account has email forwarding set up on it, or it's been converted to a shared mailbox.</span></span> <span data-ttu-id="04389-211">这两者都将导致该错误。</span><span class="sxs-lookup"><span data-stu-id="04389-211">Both of these will cause that error.</span></span> <span data-ttu-id="04389-212">如果帐户具有电子邮件转发或已转换为共享邮箱，请不要删除该帐户。</span><span class="sxs-lookup"><span data-stu-id="04389-212">Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="04389-213">**你没有删除用户的相应权限** 。</span><span class="sxs-lookup"><span data-stu-id="04389-213">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="04389-214">只有 Microsoft [365 全局管理员或用户管理管理员才能](about-admin-roles.md) 删除用户。</span><span class="sxs-lookup"><span data-stu-id="04389-214">Only people who are [Microsoft 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="04389-215">该管理员通常是学校或企业中的技术支持人员。</span><span class="sxs-lookup"><span data-stu-id="04389-215">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="04389-216">**删除用户后，用户姓名继续显示在全局通讯录中** 。</span><span class="sxs-lookup"><span data-stu-id="04389-216">**You delete the user but their name continues appear in your global address book**.</span></span> <span data-ttu-id="04389-217">企业使用 Active Directory 时会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="04389-217">This happens when a business is using Active Directory.</span></span> <span data-ttu-id="04389-218">您必须从 Active Directory 中删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="04389-218">You must delete the users account from Active Directory.</span></span> <span data-ttu-id="04389-219">有关说明，请参阅 [删除用户帐户。](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="04389-219">For instructions, see [Delete a User Account.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span></span>

<span data-ttu-id="04389-220">**是否要从计算机中删除 Microsoft 365？转到 [取消订阅](../../commerce/subscriptions/cancel-your-subscription.md)。**</span><span class="sxs-lookup"><span data-stu-id="04389-220">**Do you want to delete Microsoft 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>

## <a name="related-articles"></a><span data-ttu-id="04389-221">相关文章</span><span class="sxs-lookup"><span data-stu-id="04389-221">Related articles</span></span>

[<span data-ttu-id="04389-222">还原用户</span><span class="sxs-lookup"><span data-stu-id="04389-222">Restore a user</span></span>](restore-user.md)
  
[<span data-ttu-id="04389-223">永久删除邮箱</span><span class="sxs-lookup"><span data-stu-id="04389-223">Permanently delete a mailbox</span></span>](/exchange/permanently-delete-a-mailbox-exchange-2013-help)

[<span data-ttu-id="04389-224">从 Office 365 中删除以前的员工</span><span class="sxs-lookup"><span data-stu-id="04389-224">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="04389-225">向 Office 365 添加新员工</span><span class="sxs-lookup"><span data-stu-id="04389-225">Add a new employee to Office 365</span></span>](add-new-employee.md)

<span data-ttu-id="04389-226">[删除用户帐户](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))：如果你的企业使用与 Azure AD 同步的 **Active Directory，** 请使用以下说明。</span><span class="sxs-lookup"><span data-stu-id="04389-226">[Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="04389-227">无法通过 Office 365 删除帐户。</span><span class="sxs-lookup"><span data-stu-id="04389-227">You can't do it through Office 365.</span></span>