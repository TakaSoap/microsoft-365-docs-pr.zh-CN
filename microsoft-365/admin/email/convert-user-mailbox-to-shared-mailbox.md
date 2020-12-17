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
description: '了解如何将专用邮箱转换为多个用户访问的共享邮箱。 '
ms.openlocfilehash: fa8e37b5e924f1b38755a953f40d8b70011213d0
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698275"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="9a7f3-103">将用户邮箱转换为共享邮箱</span><span class="sxs-lookup"><span data-stu-id="9a7f3-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="9a7f3-104">将用户的邮箱转换为共享邮箱时，将保留所有现有电子邮件和日历。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="9a7f3-105">现在，它才在一个共享邮箱中，多个用户将能够访问该邮箱，而不是一个人。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="9a7f3-106">稍后，可以将共享邮箱转换回专用 (用户) 邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="9a7f3-107">**以下是您需要了解的一些非常重要的事情：**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="9a7f3-108">要转换的用户邮箱需要分配有许可证，然后才能将其转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="9a7f3-109">否则，你将看不到转换邮箱的选项。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="9a7f3-110">如果已删除许可证，请重新添加它，以便转换邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="9a7f3-111">将邮箱转换为共享邮箱后，可以从用户帐户中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="9a7f3-112">共享邮箱可具有多达 50 GB 的数据，而无需分配许可证。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="9a7f3-113">要保留的数据超过此限制，需要为其分配许可证。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="9a7f3-114">你可能需要从共享邮箱中删除一 (电子邮件，例如) 附件的电子邮件，以便你可以删除许可证。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="9a7f3-115">不要删除旧用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-115">Don't delete the old user's account.</span></span> <span data-ttu-id="9a7f3-116">这是定位共享邮箱所需的。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="9a7f3-117">如果已删除用户帐户，请参阅"转换已删除[用户的邮箱"。](#convert-the-mailbox-of-a-deleted-user)</span><span class="sxs-lookup"><span data-stu-id="9a7f3-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="9a7f3-118">将邮箱转换为共享邮箱后，规则将保持不变。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="9a7f3-119">使用 Exchange 管理中心转换邮箱</span><span class="sxs-lookup"><span data-stu-id="9a7f3-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="9a7f3-120">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="9a7f3-121">选择 **"** \> **收件人邮箱"。**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="9a7f3-122">选择用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-122">Select the user mailbox.</span></span> <span data-ttu-id="9a7f3-123">在 **"转换为共享邮箱"下，** 选择"**转换"。**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="9a7f3-124">如果邮箱小于 50 GB，可以从用户中删除许可证，[](../manage/remove-licenses-from-users.md)并停止付费。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="9a7f3-125">不要删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-125">Don't delete the user's account.</span></span> <span data-ttu-id="9a7f3-126">共享邮箱需要它作为定位标记。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="9a7f3-127">如果要转换要离开组织的员工的邮箱，则应该采取其他步骤以确保他们不能再登录。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="9a7f3-128">请参阅 [从 Microsoft 365 中删除以前的员工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="9a7f3-129">无需在邮箱转换期间重置用户密码。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="9a7f3-130">但是，如果未重置密码，则完成邮箱转换后，原始用户名和密码将继续工作。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="9a7f3-131">有关共享邮箱需要了解的一切信息，请参阅"[关于共享](about-shared-mailboxes.md)邮箱和[创建共享邮箱"。](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="9a7f3-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9a7f3-132">共享邮箱不需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="9a7f3-133">但是，如果你想要启用就地存档或将就地保留或诉讼保留置于共享邮箱，则必须向邮箱分配带有 Exchange Online Archiving 的 Exchange Online 计划 1 或 Exchange Online 计划 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="9a7f3-134">转换已删除用户的邮箱</span><span class="sxs-lookup"><span data-stu-id="9a7f3-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="9a7f3-135">假设你已删除用户帐户，现在你想要将其旧邮箱转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-135">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="9a7f3-136">以下是你需要执行哪些工作：</span><span class="sxs-lookup"><span data-stu-id="9a7f3-136">Here's what you need to do:</span></span>

1. <span data-ttu-id="9a7f3-137">[还原用户帐户](../add-users/restore-user.md)。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="9a7f3-138">确保已为其分配 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="9a7f3-139">重置用户密码。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="9a7f3-140">等待 20-30 分钟，以重新创建其邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="9a7f3-141">现在按照此页面上的说明将其邮箱转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="9a7f3-142">完成后，可以从用户的邮箱中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="9a7f3-143">不要删除用户的旧邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="9a7f3-144">共享邮箱需要它作为定位标记。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="9a7f3-145">向共享邮箱添加成员。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="9a7f3-146">将共享邮箱转换回用户的专用 () 邮箱</span><span class="sxs-lookup"><span data-stu-id="9a7f3-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="9a7f3-147">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="9a7f3-148">选择 **"收件人** \> **共享"。**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="9a7f3-149">选择共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-149">Select the shared mailbox.</span></span> <span data-ttu-id="9a7f3-150">在 **"转换为常规邮箱"下**，选择"**转换"。**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="9a7f3-151">返回到管理中心。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-151">Go back to the admin center.</span></span> <span data-ttu-id="9a7f3-152">在 **"** 用户"下，选择与旧共享邮箱关联的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="9a7f3-153">向帐户分配许可证，并重置密码。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="9a7f3-154">设置邮箱需要几分钟时间，但之后，将使用该帐户的人就可以了。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-154">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="9a7f3-155">登录后，他们将看到共享邮箱中过去的电子邮件和日历项目。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-155">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="9a7f3-156">在混合环境中转换用户邮箱</span><span class="sxs-lookup"><span data-stu-id="9a7f3-156">Convert a user's mailbox in a hybrid environment</span></span>

> [!NOTE] 
> <span data-ttu-id="9a7f3-157">从 2018 年 10 月 11 日起，Exchange 混合部署支持在本地 Exchange Server 环境中从 Exchange Server 2013 累积更新 21 和 Exchange Server 2016 累积更新 10 开始创建远程共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-157">Starting October 11th, 2018, Exchange hybrid deployment supports the creation of remote shared mailboxes starting in Cumulative Update 21 for Exchange Server 2013 and Cumulative Update 10 for Exchange Server 2016 in an on-premises Exchange Server environment.</span></span> <span data-ttu-id="9a7f3-158">可以使用新的 _-shared_ 参数直接创建或修改远程共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-158">You can directly create or modify a remote shared mailbox by using the new _-shared_ parameter.</span></span> <span data-ttu-id="9a7f3-159">有关详细信息，请访问 [Cmdlet 创建或修改](https://support.microsoft.com/help/4133605/cmdlets-to-create-modify-remote-shared-mailbox-in-on-premises-exchange)本地 Exchange 环境中远程共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-159">For more information, visit [Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment](https://support.microsoft.com/help/4133605/cmdlets-to-create-modify-remote-shared-mailbox-in-on-premises-exchange).</span></span>

<span data-ttu-id="9a7f3-160">如果此共享邮箱位于混合环境中，并且未属于上述方案，我们强烈建议 **(** 几乎需要！) 将用户邮箱移回本地，将用户邮箱转换为共享邮箱，然后将共享邮箱移回云。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-160">If this shared mailbox is in a hybrid environment and not falling under the above scenario, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="9a7f3-161">原因包括：如果你在云中转换邮箱，它可以被转换，但本地仍认为邮箱是用户邮箱，因为新现实不会同步回本地。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-161">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="9a7f3-162">通常这不是问题，但在某些情况下，本地属性 (认为邮箱是用户邮箱) 可能会覆盖这些属性的新云版本，因此邮箱可能会转换回。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-162">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="9a7f3-163">这是一个问题，因为用户邮箱需要许可证或在 **30** 天后软删除！</span><span class="sxs-lookup"><span data-stu-id="9a7f3-163">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="9a7f3-164">我们已解决出现此情况的原因，但仍可能发生此情况，尽管这种情况很少发生。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-164">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="9a7f3-165">最好是安全的，并将邮箱移回本地，转换它，然后将共享邮箱移回云。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-165">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="9a7f3-166">此建议的解决方案不会违反混合环境的许可协议，因为本地用户邮箱的存在只是临时的。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-166">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="9a7f3-167">如果在内部部署组织中维护用户邮箱或共享邮箱，并且未将其移回云，则违反了许可证。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-167">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>


> [!NOTE]
> <span data-ttu-id="9a7f3-168">如果您是组织管理或收件人管理角色组的成员，可以使用 Exchange 命令行管理程序将用户邮箱更改为本地共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-168">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="9a7f3-169">例如，`Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-169">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="9a7f3-170">有关共享邮箱意外转换为用户邮箱的情况，请参阅此支持 [解决方案中的解决方法](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-170">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="9a7f3-171">相关文章</span><span class="sxs-lookup"><span data-stu-id="9a7f3-171">Related articles</span></span>

[<span data-ttu-id="9a7f3-172">关于共享邮箱</span><span class="sxs-lookup"><span data-stu-id="9a7f3-172">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="9a7f3-173">创建共享邮箱</span><span class="sxs-lookup"><span data-stu-id="9a7f3-173">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="9a7f3-174">配置共享邮箱</span><span class="sxs-lookup"><span data-stu-id="9a7f3-174">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="9a7f3-175">从共享邮箱删除许可证</span><span class="sxs-lookup"><span data-stu-id="9a7f3-175">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="9a7f3-176">解决共享邮箱问题</span><span class="sxs-lookup"><span data-stu-id="9a7f3-176">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
