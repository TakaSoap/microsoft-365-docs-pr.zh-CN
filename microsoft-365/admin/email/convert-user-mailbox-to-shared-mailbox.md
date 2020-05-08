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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '了解如何将专用邮箱转换为可由多个用户访问的共享邮箱。 '
ms.openlocfilehash: 51817001b02c1dd5dd0e82f5795ef1a3f66bf7c7
ms.sourcegitcommit: 9ffa2fd25776726475e10148940987fa076bbd91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44162694"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="7438d-103">将用户邮箱转换为共享邮箱</span><span class="sxs-lookup"><span data-stu-id="7438d-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="7438d-104">将用户的邮箱转换为共享邮箱时，所有现有的电子邮件和日历都将保留。</span><span class="sxs-lookup"><span data-stu-id="7438d-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="7438d-105">只有在共享邮箱中，多个用户才能访问它，而不是一个人。</span><span class="sxs-lookup"><span data-stu-id="7438d-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="7438d-106">稍后，您可以将共享邮箱转换回用户（专用）邮箱。</span><span class="sxs-lookup"><span data-stu-id="7438d-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="7438d-107">**下面是您需要了解的一些真正重要的事项：**</span><span class="sxs-lookup"><span data-stu-id="7438d-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="7438d-108">在转换为共享邮箱之前，要转换的用户邮箱需要分配有许可证。</span><span class="sxs-lookup"><span data-stu-id="7438d-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="7438d-109">否则，将看不到用于转换邮箱的选项。</span><span class="sxs-lookup"><span data-stu-id="7438d-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="7438d-110">如果已删除许可证，请将其添加回来，以便可以转换邮箱。</span><span class="sxs-lookup"><span data-stu-id="7438d-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="7438d-111">将邮箱转换为共享邮箱后，可以从用户帐户中删除该许可证。</span><span class="sxs-lookup"><span data-stu-id="7438d-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="7438d-112">共享邮箱最高可包含50GB 的数据，而无需向其分配许可证。</span><span class="sxs-lookup"><span data-stu-id="7438d-112">Shared mailboxes can have up to 50GB of data without a license assigned to them.</span></span> <span data-ttu-id="7438d-113">若要保留的数据多于该数据，你需要分配给它的许可证。</span><span class="sxs-lookup"><span data-stu-id="7438d-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="7438d-114">您可能需要删除共享邮箱中的一组大型电子邮件（称为附件），以便将其缩小，以便您可以删除该许可证。</span><span class="sxs-lookup"><span data-stu-id="7438d-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="7438d-115">请勿删除旧用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="7438d-115">Don't delete the old user's account.</span></span> <span data-ttu-id="7438d-116">这是锁定共享邮箱所必需的。</span><span class="sxs-lookup"><span data-stu-id="7438d-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="7438d-117">如果已删除用户帐户，请参阅[转换已删除用户的邮箱](#convert-the-mailbox-of-a-deleted-user)。</span><span class="sxs-lookup"><span data-stu-id="7438d-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="7438d-118">将邮箱转换为共享邮箱后，规则将保持不变。</span><span class="sxs-lookup"><span data-stu-id="7438d-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="7438d-119">使用 Exchange 管理中心转换邮箱</span><span class="sxs-lookup"><span data-stu-id="7438d-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="7438d-120">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="7438d-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="7438d-121">选择 "**收件人** \> " "**邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="7438d-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="7438d-122">选择用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="7438d-122">Select the user mailbox.</span></span> <span data-ttu-id="7438d-123">在 "**转换为共享邮箱**" 下，选择 "**转换**"。</span><span class="sxs-lookup"><span data-stu-id="7438d-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="7438d-124">如果邮箱小于50GB，则可以[从用户处删除许可证](../manage/remove-licenses-from-users.md)，然后停止付款。</span><span class="sxs-lookup"><span data-stu-id="7438d-124">If the mailbox is smaller than 50GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="7438d-125">请勿删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7438d-125">Don't delete the user's account.</span></span> <span data-ttu-id="7438d-126">共享邮箱需要将其作为定位点。</span><span class="sxs-lookup"><span data-stu-id="7438d-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="7438d-127">如果要转换离开组织的员工的邮箱，则应执行其他步骤以确保他们无法再登录。</span><span class="sxs-lookup"><span data-stu-id="7438d-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="7438d-128">请参阅[从 Microsoft 365 删除以前的员工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="7438d-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="7438d-129">有关共享邮箱需要了解的其他信息，请参阅[关于共享](about-shared-mailboxes.md)邮箱和[创建共享邮箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="7438d-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="7438d-130">使用 Microsoft 365 管理中心转换邮箱</span><span class="sxs-lookup"><span data-stu-id="7438d-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7438d-131">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="7438d-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="7438d-132">选择要转换其邮箱的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="7438d-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="7438d-133">重置用户的密码。</span><span class="sxs-lookup"><span data-stu-id="7438d-133">Reset the user's password.</span></span>

> [!NOTE]
> <span data-ttu-id="7438d-134">在邮箱转换过程中，不需要重置用户的密码。</span><span class="sxs-lookup"><span data-stu-id="7438d-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="7438d-135">但是，如果未重置密码，则在邮箱转换完成后，**原始用户名和密码将继续正常工作**。</span><span class="sxs-lookup"><span data-stu-id="7438d-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="7438d-136">在 "**邮件**" 选项卡上的 "**其他操作**" 下，选择 "**转换为共享邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="7438d-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7438d-137">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="7438d-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="7438d-138">选择要转换其邮箱的用户。</span><span class="sxs-lookup"><span data-stu-id="7438d-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="7438d-139">在右窗格中，展开 "**邮件设置**"。</span><span class="sxs-lookup"><span data-stu-id="7438d-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="7438d-140">在 "**更多设置**" 旁边，选择 "**转换为共享邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="7438d-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7438d-141">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="7438d-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="7438d-142">选择要转换其邮箱的用户。</span><span class="sxs-lookup"><span data-stu-id="7438d-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="7438d-143">在右窗格中，展开 "**邮件设置**"。</span><span class="sxs-lookup"><span data-stu-id="7438d-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="7438d-144">在 "**更多设置**" 旁边，选择 "**转换为共享邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="7438d-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="7438d-145">如果邮箱小于50GB，则可以[从用户处删除许可证](../manage/remove-licenses-from-users.md)，然后停止付款。</span><span class="sxs-lookup"><span data-stu-id="7438d-145">If the mailbox is smaller than 50GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="7438d-146">请勿删除用户的旧邮箱。</span><span class="sxs-lookup"><span data-stu-id="7438d-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="7438d-147">共享邮箱需要将其作为定位点。</span><span class="sxs-lookup"><span data-stu-id="7438d-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="7438d-148">如果要转换离开组织的员工的邮箱，则应执行其他步骤以确保他们无法再登录。</span><span class="sxs-lookup"><span data-stu-id="7438d-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="7438d-149">请参阅[从 Microsoft 365 删除以前的员工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="7438d-149">See [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="7438d-150">有关共享邮箱需要了解的其他信息，请参阅[关于共享](about-shared-mailboxes.md)邮箱和[创建共享邮箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="7438d-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="7438d-151">转换已删除用户的邮箱</span><span class="sxs-lookup"><span data-stu-id="7438d-151">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="7438d-152">假设您已删除用户帐户，现在想要将其旧邮箱转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="7438d-152">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="7438d-153">您需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7438d-153">Here's what you need to do:</span></span>

1. <span data-ttu-id="7438d-154">[还原用户的帐户](../add-users/restore-user.md)。</span><span class="sxs-lookup"><span data-stu-id="7438d-154">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="7438d-155">请确保向其分配了 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="7438d-155">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="7438d-156">重置用户的密码。</span><span class="sxs-lookup"><span data-stu-id="7438d-156">Reset the user's password.</span></span>
    
4. <span data-ttu-id="7438d-157">等待20-30 分钟，以便重新创建其邮箱。</span><span class="sxs-lookup"><span data-stu-id="7438d-157">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="7438d-158">现在，按照此页面上的说明将其邮箱转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="7438d-158">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="7438d-159">完成此操作后，您可以从用户的邮箱中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="7438d-159">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="7438d-160">请勿删除用户的旧邮箱。</span><span class="sxs-lookup"><span data-stu-id="7438d-160">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="7438d-161">共享邮箱需要将其作为定位点。</span><span class="sxs-lookup"><span data-stu-id="7438d-161">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="7438d-162">将成员添加到共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="7438d-162">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="7438d-163">将共享邮箱转换回用户的（专用）邮箱</span><span class="sxs-lookup"><span data-stu-id="7438d-163">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="7438d-164">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="7438d-164">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="7438d-165">选择 "**共享\*\*\*\*收件人** \> "。</span><span class="sxs-lookup"><span data-stu-id="7438d-165">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="7438d-166">选择共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="7438d-166">Select the shared mailbox.</span></span> <span data-ttu-id="7438d-167">在 "**转换为常规邮箱**" 下，选择 "**转换**"。</span><span class="sxs-lookup"><span data-stu-id="7438d-167">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="7438d-168">返回到管理中心。</span><span class="sxs-lookup"><span data-stu-id="7438d-168">Go back to the admin center.</span></span> <span data-ttu-id="7438d-169">在 "**用户**" 下，选择与旧共享邮箱相关联的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7438d-169">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="7438d-170">将许可证分配给帐户，然后重置密码。</span><span class="sxs-lookup"><span data-stu-id="7438d-170">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="7438d-171">设置邮箱需要几分钟时间，但在此之后，将使用该帐户的人员可以转到。</span><span class="sxs-lookup"><span data-stu-id="7438d-171">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="7438d-172">登录时，他们将看到已在共享邮箱中使用的电子邮件和日历项目。</span><span class="sxs-lookup"><span data-stu-id="7438d-172">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="7438d-173">在混合环境中转换用户的邮箱</span><span class="sxs-lookup"><span data-stu-id="7438d-173">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="7438d-174">如果此共享邮箱位于混合环境中，**强烈建议**（几乎需要！）将用户邮箱移回本地，将用户邮箱转换为共享邮箱，然后将共享邮箱移回云。</span><span class="sxs-lookup"><span data-stu-id="7438d-174">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span>

<span data-ttu-id="7438d-175">原因如下：如果您在云中转换邮箱，可以对其进行转换，但本地仍认为邮箱是用户邮箱，因为新的现实不会同步回本地。</span><span class="sxs-lookup"><span data-stu-id="7438d-175">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="7438d-176">通常情况下，这并不是问题，但在某些情况下，本地属性（可能会认为邮箱是用户邮箱）可能会覆盖这些属性的新云版本，因此邮箱可能会转换回来。</span><span class="sxs-lookup"><span data-stu-id="7438d-176">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="7438d-177">这是一个问题，因为用户邮箱需要许可证**或在30天后软删除**！</span><span class="sxs-lookup"><span data-stu-id="7438d-177">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="7438d-178">我们解决了这种情况的大部分原因，但仍可能会发生，尽管不常这样做。</span><span class="sxs-lookup"><span data-stu-id="7438d-178">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="7438d-179">最好是安全的，并将邮箱移回本地。</span><span class="sxs-lookup"><span data-stu-id="7438d-179">It's best to be safe and move the mailbox back to on-premises.</span></span>

> [!NOTE]
> <span data-ttu-id="7438d-180">如果您是组织管理或收件人管理的一部分，则可以使用 Exchange 命令行管理程序将用户邮箱更改为本地共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="7438d-180">If you are a part of Organization Management or Recipient Management, you can use the  Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="7438d-181">例如，`Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`。</span><span class="sxs-lookup"><span data-stu-id="7438d-181">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="7438d-182">如果[共享邮箱意外转换为用户邮箱](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)，请参阅此支持解决方案中针对实例的解决方法</span><span class="sxs-lookup"><span data-stu-id="7438d-182">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="7438d-183">相关文章</span><span class="sxs-lookup"><span data-stu-id="7438d-183">Related articles</span></span>

[<span data-ttu-id="7438d-184">关于共享邮箱</span><span class="sxs-lookup"><span data-stu-id="7438d-184">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="7438d-185">创建共享邮箱</span><span class="sxs-lookup"><span data-stu-id="7438d-185">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="7438d-186">配置共享邮箱</span><span class="sxs-lookup"><span data-stu-id="7438d-186">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="7438d-187">从共享邮箱删除许可证</span><span class="sxs-lookup"><span data-stu-id="7438d-187">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="7438d-188">解决共享邮箱问题</span><span class="sxs-lookup"><span data-stu-id="7438d-188">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
