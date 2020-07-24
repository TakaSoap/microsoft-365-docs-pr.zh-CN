---
title: 将用户邮箱转换为共享邮箱
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '了解如何将专用邮箱转换为可由多个用户访问的共享邮箱。 '
ms.openlocfilehash: 7ae00c1d9c901378798f063554a44a3e5b741442
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391526"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="f754c-103">将用户邮箱转换为共享邮箱</span><span class="sxs-lookup"><span data-stu-id="f754c-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="f754c-104">将用户的邮箱转换为共享邮箱时，所有现有的电子邮件和日历都将保留。</span><span class="sxs-lookup"><span data-stu-id="f754c-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="f754c-105">只有在共享邮箱中，多个用户才能访问它，而不是一个人。</span><span class="sxs-lookup"><span data-stu-id="f754c-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="f754c-106">稍后，您可以将共享邮箱转换回用户（专用）邮箱。</span><span class="sxs-lookup"><span data-stu-id="f754c-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="f754c-107">**下面是您需要了解的一些真正重要的事项：**</span><span class="sxs-lookup"><span data-stu-id="f754c-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="f754c-108">在转换为共享邮箱之前，要转换的用户邮箱需要分配有许可证。</span><span class="sxs-lookup"><span data-stu-id="f754c-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="f754c-109">否则，将看不到用于转换邮箱的选项。</span><span class="sxs-lookup"><span data-stu-id="f754c-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="f754c-110">如果已删除许可证，请将其添加回来，以便可以转换邮箱。</span><span class="sxs-lookup"><span data-stu-id="f754c-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="f754c-111">将邮箱转换为共享邮箱后，可以从用户帐户中删除该许可证。</span><span class="sxs-lookup"><span data-stu-id="f754c-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="f754c-112">共享邮箱最高可包含50GB 的数据，而无需向其分配许可证。</span><span class="sxs-lookup"><span data-stu-id="f754c-112">Shared mailboxes can have up to 50GB of data without a license assigned to them.</span></span> <span data-ttu-id="f754c-113">若要保留的数据多于该数据，你需要分配给它的许可证。</span><span class="sxs-lookup"><span data-stu-id="f754c-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="f754c-114">您可能需要删除共享邮箱中的一组大型电子邮件（称为附件），以便将其缩小，以便您可以删除该许可证。</span><span class="sxs-lookup"><span data-stu-id="f754c-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="f754c-115">请勿删除旧用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="f754c-115">Don't delete the old user's account.</span></span> <span data-ttu-id="f754c-116">这是锁定共享邮箱所必需的。</span><span class="sxs-lookup"><span data-stu-id="f754c-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="f754c-117">如果已删除用户帐户，请参阅[转换已删除用户的邮箱](#convert-the-mailbox-of-a-deleted-user)。</span><span class="sxs-lookup"><span data-stu-id="f754c-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="f754c-118">将邮箱转换为共享邮箱后，规则将保持不变。</span><span class="sxs-lookup"><span data-stu-id="f754c-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="f754c-119">使用 Exchange 管理中心转换邮箱</span><span class="sxs-lookup"><span data-stu-id="f754c-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="f754c-120">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="f754c-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="f754c-121">选择 "**收件人**" " \> **邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="f754c-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="f754c-122">选择用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="f754c-122">Select the user mailbox.</span></span> <span data-ttu-id="f754c-123">在 "**转换为共享邮箱**" 下，选择 "**转换**"。</span><span class="sxs-lookup"><span data-stu-id="f754c-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="f754c-124">如果邮箱小于50GB，则可以[从用户处删除许可证](../manage/remove-licenses-from-users.md)，然后停止付款。</span><span class="sxs-lookup"><span data-stu-id="f754c-124">If the mailbox is smaller than 50GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="f754c-125">请勿删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f754c-125">Don't delete the user's account.</span></span> <span data-ttu-id="f754c-126">共享邮箱需要将其作为定位点。</span><span class="sxs-lookup"><span data-stu-id="f754c-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="f754c-127">如果要转换离开组织的员工的邮箱，则应执行其他步骤以确保他们无法再登录。</span><span class="sxs-lookup"><span data-stu-id="f754c-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="f754c-128">请参阅[从 Microsoft 365 删除以前的员工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="f754c-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="f754c-129">有关共享邮箱需要了解的其他信息，请参阅[关于共享](about-shared-mailboxes.md)邮箱和[创建共享邮箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="f754c-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="f754c-130">使用 Microsoft 365 管理中心转换邮箱</span><span class="sxs-lookup"><span data-stu-id="f754c-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f754c-131">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f754c-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="f754c-132">选择要转换其邮箱的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="f754c-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="f754c-133">重置用户的密码。</span><span class="sxs-lookup"><span data-stu-id="f754c-133">Reset the user's password.</span></span>

> [!NOTE]
> <span data-ttu-id="f754c-134">在邮箱转换过程中，不需要重置用户的密码。</span><span class="sxs-lookup"><span data-stu-id="f754c-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="f754c-135">但是，如果未重置密码，则在邮箱转换完成后，**原始用户名和密码将继续正常工作**。</span><span class="sxs-lookup"><span data-stu-id="f754c-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="f754c-136">在 "**邮件**" 选项卡上的 "**其他操作**" 下，选择 "**转换为共享邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="f754c-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="f754c-137">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f754c-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="f754c-138">选择要转换其邮箱的用户。</span><span class="sxs-lookup"><span data-stu-id="f754c-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="f754c-139">在右窗格中，展开 "**邮件设置**"。</span><span class="sxs-lookup"><span data-stu-id="f754c-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="f754c-140">在 "**更多设置**" 旁边，选择 "**转换为共享邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="f754c-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f754c-141">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f754c-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="f754c-142">选择要转换其邮箱的用户。</span><span class="sxs-lookup"><span data-stu-id="f754c-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="f754c-143">在右窗格中，展开 "**邮件设置**"。</span><span class="sxs-lookup"><span data-stu-id="f754c-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="f754c-144">在 "**更多设置**" 旁边，选择 "**转换为共享邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="f754c-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="f754c-145">如果邮箱小于50GB，则可以[从用户处删除许可证](../manage/remove-licenses-from-users.md)，然后停止付款。</span><span class="sxs-lookup"><span data-stu-id="f754c-145">If the mailbox is smaller than 50GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="f754c-146">请勿删除用户的旧邮箱。</span><span class="sxs-lookup"><span data-stu-id="f754c-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="f754c-147">共享邮箱需要将其作为定位点。</span><span class="sxs-lookup"><span data-stu-id="f754c-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="f754c-148">如果要转换离开组织的员工的邮箱，则应执行其他步骤以确保他们无法再登录。</span><span class="sxs-lookup"><span data-stu-id="f754c-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="f754c-149">请参阅[从 Microsoft 365 删除以前的员工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="f754c-149">See [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="f754c-150">有关共享邮箱需要了解的其他信息，请参阅[关于共享](about-shared-mailboxes.md)邮箱和[创建共享邮箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="f754c-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f754c-151">共享邮箱不需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="f754c-151">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="f754c-152">但是，如果你想要启用就地存档或将就地保留或诉讼保留置于共享邮箱，则必须向邮箱分配带有 Exchange Online Archiving 的 Exchange Online 计划 1 或 Exchange Online 计划 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="f754c-152">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="f754c-153">转换已删除用户的邮箱</span><span class="sxs-lookup"><span data-stu-id="f754c-153">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="f754c-154">假设您已删除用户帐户，现在想要将其旧邮箱转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="f754c-154">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="f754c-155">您需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f754c-155">Here's what you need to do:</span></span>

1. <span data-ttu-id="f754c-156">[还原用户的帐户](../add-users/restore-user.md)。</span><span class="sxs-lookup"><span data-stu-id="f754c-156">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="f754c-157">请确保向其分配了 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="f754c-157">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="f754c-158">重置用户的密码。</span><span class="sxs-lookup"><span data-stu-id="f754c-158">Reset the user's password.</span></span>
    
4. <span data-ttu-id="f754c-159">等待20-30 分钟，以便重新创建其邮箱。</span><span class="sxs-lookup"><span data-stu-id="f754c-159">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="f754c-160">现在，按照此页面上的说明将其邮箱转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="f754c-160">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="f754c-161">完成此操作后，您可以从用户的邮箱中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="f754c-161">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="f754c-162">请勿删除用户的旧邮箱。</span><span class="sxs-lookup"><span data-stu-id="f754c-162">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="f754c-163">共享邮箱需要将其作为定位点。</span><span class="sxs-lookup"><span data-stu-id="f754c-163">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="f754c-164">将成员添加到共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="f754c-164">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="f754c-165">将共享邮箱转换回用户的（专用）邮箱</span><span class="sxs-lookup"><span data-stu-id="f754c-165">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="f754c-166">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="f754c-166">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="f754c-167">选择**Recipients** " \> **共享**收件人"。</span><span class="sxs-lookup"><span data-stu-id="f754c-167">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="f754c-168">选择共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="f754c-168">Select the shared mailbox.</span></span> <span data-ttu-id="f754c-169">在 "**转换为常规邮箱**" 下，选择 "**转换**"。</span><span class="sxs-lookup"><span data-stu-id="f754c-169">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="f754c-170">返回到管理中心。</span><span class="sxs-lookup"><span data-stu-id="f754c-170">Go back to the admin center.</span></span> <span data-ttu-id="f754c-171">在 "**用户**" 下，选择与旧共享邮箱相关联的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f754c-171">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="f754c-172">将许可证分配给帐户，然后重置密码。</span><span class="sxs-lookup"><span data-stu-id="f754c-172">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="f754c-173">设置邮箱需要几分钟时间，但在此之后，将使用该帐户的人员可以转到。</span><span class="sxs-lookup"><span data-stu-id="f754c-173">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="f754c-174">登录时，他们将看到已在共享邮箱中使用的电子邮件和日历项目。</span><span class="sxs-lookup"><span data-stu-id="f754c-174">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="f754c-175">在混合环境中转换用户的邮箱</span><span class="sxs-lookup"><span data-stu-id="f754c-175">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="f754c-176">如果此共享邮箱位于混合环境中，**强烈建议**（几乎需要！）将用户邮箱移回本地，将用户邮箱转换为共享邮箱，然后将共享邮箱移回云。</span><span class="sxs-lookup"><span data-stu-id="f754c-176">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span>

<span data-ttu-id="f754c-177">原因如下：如果您在云中转换邮箱，可以对其进行转换，但本地仍认为邮箱是用户邮箱，因为新的现实不会同步回本地。</span><span class="sxs-lookup"><span data-stu-id="f754c-177">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="f754c-178">通常情况下，这并不是问题，但在某些情况下，本地属性（可能会认为邮箱是用户邮箱）可能会覆盖这些属性的新云版本，因此邮箱可能会转换回来。</span><span class="sxs-lookup"><span data-stu-id="f754c-178">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="f754c-179">这是一个问题，因为用户邮箱需要许可证**或在30天后软删除**！</span><span class="sxs-lookup"><span data-stu-id="f754c-179">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="f754c-180">我们解决了这种情况的大部分原因，但仍可能会发生，尽管不常这样做。</span><span class="sxs-lookup"><span data-stu-id="f754c-180">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="f754c-181">最好是安全的，并将邮箱移回本地。</span><span class="sxs-lookup"><span data-stu-id="f754c-181">It's best to be safe and move the mailbox back to on-premises.</span></span>

> [!NOTE]
> <span data-ttu-id="f754c-182">如果您是组织管理或收件人管理的一部分，则可以使用 Exchange 命令行管理程序将用户邮箱更改为本地共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="f754c-182">If you are a part of Organization Management or Recipient Management, you can use the  Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="f754c-183">例如，`Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`。</span><span class="sxs-lookup"><span data-stu-id="f754c-183">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="f754c-184">如果[共享邮箱意外转换为用户邮箱](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)，请参阅此支持解决方案中针对实例的解决方法</span><span class="sxs-lookup"><span data-stu-id="f754c-184">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="f754c-185">相关文章</span><span class="sxs-lookup"><span data-stu-id="f754c-185">Related articles</span></span>

[<span data-ttu-id="f754c-186">关于共享邮箱</span><span class="sxs-lookup"><span data-stu-id="f754c-186">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="f754c-187">创建共享邮箱</span><span class="sxs-lookup"><span data-stu-id="f754c-187">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="f754c-188">配置共享邮箱</span><span class="sxs-lookup"><span data-stu-id="f754c-188">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="f754c-189">从共享邮箱删除许可证</span><span class="sxs-lookup"><span data-stu-id="f754c-189">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="f754c-190">解决共享邮箱问题</span><span class="sxs-lookup"><span data-stu-id="f754c-190">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
