---
title: 将用户邮箱转换为共享邮箱
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
ms.openlocfilehash: bc867c9b43656e40149eb7cd7a7e5ce186c10798
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445683"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="1be9f-103">将用户邮箱转换为共享邮箱</span><span class="sxs-lookup"><span data-stu-id="1be9f-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="1be9f-104">将用户的邮箱转换为共享邮箱时，所有现有的电子邮件和日历都将保留。</span><span class="sxs-lookup"><span data-stu-id="1be9f-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="1be9f-105">只有在共享邮箱中，多个用户才能访问它，而不是一个人。</span><span class="sxs-lookup"><span data-stu-id="1be9f-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="1be9f-106">稍后，您可以将共享邮箱转换回用户 (专用) 邮箱。</span><span class="sxs-lookup"><span data-stu-id="1be9f-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="1be9f-107">**下面是您需要了解的一些真正重要的事项：**</span><span class="sxs-lookup"><span data-stu-id="1be9f-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="1be9f-108">在转换为共享邮箱之前，要转换的用户邮箱需要分配有许可证。</span><span class="sxs-lookup"><span data-stu-id="1be9f-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="1be9f-109">否则，将看不到用于转换邮箱的选项。</span><span class="sxs-lookup"><span data-stu-id="1be9f-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="1be9f-110">如果已删除许可证，请将其添加回来，以便可以转换邮箱。</span><span class="sxs-lookup"><span data-stu-id="1be9f-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="1be9f-111">将邮箱转换为共享邮箱后，可以从用户帐户中删除该许可证。</span><span class="sxs-lookup"><span data-stu-id="1be9f-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="1be9f-112">共享邮箱最高可包含 50 GB 的数据，而无需向其分配许可证。</span><span class="sxs-lookup"><span data-stu-id="1be9f-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="1be9f-113">若要保留的数据多于该数据，你需要分配给它的许可证。</span><span class="sxs-lookup"><span data-stu-id="1be9f-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="1be9f-114">您可能需要删除一组大型电子邮件 (说，其中包含来自共享邮箱的附件) 的电子邮件将其缩小，以便您可以删除该许可证。</span><span class="sxs-lookup"><span data-stu-id="1be9f-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="1be9f-115">请勿删除旧用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="1be9f-115">Don't delete the old user's account.</span></span> <span data-ttu-id="1be9f-116">这是锁定共享邮箱所必需的。</span><span class="sxs-lookup"><span data-stu-id="1be9f-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="1be9f-117">如果已删除用户帐户，请参阅 [转换已删除用户的邮箱](#convert-the-mailbox-of-a-deleted-user)。</span><span class="sxs-lookup"><span data-stu-id="1be9f-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="1be9f-118">将邮箱转换为共享邮箱后，规则将保持不变。</span><span class="sxs-lookup"><span data-stu-id="1be9f-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="1be9f-119">使用 Exchange 管理中心转换邮箱</span><span class="sxs-lookup"><span data-stu-id="1be9f-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="1be9f-120">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="1be9f-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="1be9f-121">选择 " **收件人**" " \> **邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="1be9f-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="1be9f-122">选择用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="1be9f-122">Select the user mailbox.</span></span> <span data-ttu-id="1be9f-123">在 " **转换为共享邮箱**" 下，选择 " **转换**"。</span><span class="sxs-lookup"><span data-stu-id="1be9f-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="1be9f-124">如果邮箱小于 50 GB，则可以 [从用户处删除许可证](../manage/remove-licenses-from-users.md)并停止付款。</span><span class="sxs-lookup"><span data-stu-id="1be9f-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="1be9f-125">请勿删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1be9f-125">Don't delete the user's account.</span></span> <span data-ttu-id="1be9f-126">共享邮箱需要将其作为定位点。</span><span class="sxs-lookup"><span data-stu-id="1be9f-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="1be9f-127">如果要转换离开组织的员工的邮箱，则应执行其他步骤以确保他们无法再登录。</span><span class="sxs-lookup"><span data-stu-id="1be9f-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="1be9f-128">请参阅 [从 Microsoft 365 删除以前的员工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="1be9f-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="1be9f-129">在邮箱转换过程中，不需要重置用户的密码。</span><span class="sxs-lookup"><span data-stu-id="1be9f-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="1be9f-130">但是，如果未重置密码，则在邮箱转换完成后， **原始用户名和密码将继续正常工作** 。</span><span class="sxs-lookup"><span data-stu-id="1be9f-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="1be9f-131">有关共享邮箱需要了解的其他信息，请参阅 [关于共享](about-shared-mailboxes.md) 邮箱和 [创建共享邮箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="1be9f-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1be9f-132">共享邮箱不需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="1be9f-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="1be9f-133">但是，如果你想要启用就地存档或将就地保留或诉讼保留置于共享邮箱，则必须向邮箱分配带有 Exchange Online Archiving 的 Exchange Online 计划 1 或 Exchange Online 计划 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="1be9f-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="1be9f-134">转换已删除用户的邮箱</span><span class="sxs-lookup"><span data-stu-id="1be9f-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="1be9f-135">假设您已删除用户帐户，现在想要将其旧邮箱转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="1be9f-135">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="1be9f-136">您需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1be9f-136">Here's what you need to do:</span></span>

1. <span data-ttu-id="1be9f-137">[还原用户的帐户](../add-users/restore-user.md)。</span><span class="sxs-lookup"><span data-stu-id="1be9f-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="1be9f-138">请确保向其分配了 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="1be9f-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="1be9f-139">重置用户的密码。</span><span class="sxs-lookup"><span data-stu-id="1be9f-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="1be9f-140">等待20-30 分钟，以便重新创建其邮箱。</span><span class="sxs-lookup"><span data-stu-id="1be9f-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="1be9f-141">现在，按照此页面上的说明将其邮箱转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="1be9f-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="1be9f-142">完成此操作后，您可以从用户的邮箱中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="1be9f-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="1be9f-143">请勿删除用户的旧邮箱。</span><span class="sxs-lookup"><span data-stu-id="1be9f-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="1be9f-144">共享邮箱需要将其作为定位点。</span><span class="sxs-lookup"><span data-stu-id="1be9f-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="1be9f-145">将成员添加到共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="1be9f-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="1be9f-146">将共享邮箱转换回用户的 (专用) 邮箱</span><span class="sxs-lookup"><span data-stu-id="1be9f-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="1be9f-147">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="1be9f-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="1be9f-148">选择**Recipients** " \> **共享**收件人"。</span><span class="sxs-lookup"><span data-stu-id="1be9f-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="1be9f-149">选择共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="1be9f-149">Select the shared mailbox.</span></span> <span data-ttu-id="1be9f-150">在 " **转换为常规邮箱**" 下，选择 " **转换**"。</span><span class="sxs-lookup"><span data-stu-id="1be9f-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="1be9f-151">返回到管理中心。</span><span class="sxs-lookup"><span data-stu-id="1be9f-151">Go back to the admin center.</span></span> <span data-ttu-id="1be9f-152">在 " **用户**" 下，选择与旧共享邮箱相关联的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1be9f-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="1be9f-153">将许可证分配给帐户，然后重置密码。</span><span class="sxs-lookup"><span data-stu-id="1be9f-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="1be9f-154">设置邮箱需要几分钟时间，但在此之后，将使用该帐户的人员可以转到。</span><span class="sxs-lookup"><span data-stu-id="1be9f-154">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="1be9f-155">登录时，他们将看到已在共享邮箱中使用的电子邮件和日历项目。</span><span class="sxs-lookup"><span data-stu-id="1be9f-155">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="1be9f-156">在混合环境中转换用户的邮箱</span><span class="sxs-lookup"><span data-stu-id="1be9f-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="1be9f-157">如果此共享邮箱在混合环境中， **强烈建议** (几乎需要！ ) 将用户邮箱移回本地，请将用户邮箱转换为共享邮箱，然后将共享邮箱移回云。</span><span class="sxs-lookup"><span data-stu-id="1be9f-157">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="1be9f-158">原因如下：如果您在云中转换邮箱，可以对其进行转换，但本地仍认为邮箱是用户邮箱，因为新的现实不会同步回本地。</span><span class="sxs-lookup"><span data-stu-id="1be9f-158">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="1be9f-159">通常情况下，这并不是问题，但在某些情况下 (会认为邮箱是用户邮箱) 可以覆盖这些属性的新云版本，因此邮箱可能会转换回来。</span><span class="sxs-lookup"><span data-stu-id="1be9f-159">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="1be9f-160">这是一个问题，因为用户邮箱需要许可证 **或在30天后软删除**！</span><span class="sxs-lookup"><span data-stu-id="1be9f-160">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="1be9f-161">我们解决了这种情况的大部分原因，但仍可能会发生，尽管不常这样做。</span><span class="sxs-lookup"><span data-stu-id="1be9f-161">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="1be9f-162">最好是安全的，并将邮箱移回本地，再进行转换，然后将共享邮箱移回云。</span><span class="sxs-lookup"><span data-stu-id="1be9f-162">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="1be9f-163">此建议的解决方案不违反混合环境的许可协议，因为本地用户邮箱的存在仅是临时性的。</span><span class="sxs-lookup"><span data-stu-id="1be9f-163">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="1be9f-164">如果您在内部部署组织中维护了用户邮箱或共享邮箱，并且未将其移回云，则会违反许可证。</span><span class="sxs-lookup"><span data-stu-id="1be9f-164">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="1be9f-165">如果您是组织管理或收件人管理角色组的成员，则可以使用 Exchange 命令行管理程序将用户邮箱更改为本地共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="1be9f-165">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="1be9f-166">例如，`Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`。</span><span class="sxs-lookup"><span data-stu-id="1be9f-166">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="1be9f-167">如果 [共享邮箱意外转换为用户邮箱](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)，请参阅此支持解决方案中有关实例的解决方法。</span><span class="sxs-lookup"><span data-stu-id="1be9f-167">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="1be9f-168">相关文章</span><span class="sxs-lookup"><span data-stu-id="1be9f-168">Related articles</span></span>

[<span data-ttu-id="1be9f-169">关于共享邮箱</span><span class="sxs-lookup"><span data-stu-id="1be9f-169">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="1be9f-170">创建共享邮箱</span><span class="sxs-lookup"><span data-stu-id="1be9f-170">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="1be9f-171">配置共享邮箱</span><span class="sxs-lookup"><span data-stu-id="1be9f-171">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="1be9f-172">从共享邮箱删除许可证</span><span class="sxs-lookup"><span data-stu-id="1be9f-172">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="1be9f-173">解决共享邮箱问题</span><span class="sxs-lookup"><span data-stu-id="1be9f-173">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
