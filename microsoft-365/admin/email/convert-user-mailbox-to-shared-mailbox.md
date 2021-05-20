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
description: '了解如何将专用邮箱转换为多个人员（而不是一个人）可以访问的共享邮箱。 '
ms.openlocfilehash: 73e2bad40037e1343f4e08c07ca6b26df16b1a30
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537615"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="15576-103">将用户邮箱转换为共享邮箱</span><span class="sxs-lookup"><span data-stu-id="15576-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="15576-104">将用户的邮箱转换为共享邮箱时，将保留所有现有电子邮件和日历。</span><span class="sxs-lookup"><span data-stu-id="15576-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="15576-105">现在，它才在一个共享邮箱中，多个人员将能够访问它，而不是一个人。</span><span class="sxs-lookup"><span data-stu-id="15576-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="15576-106">稍后，可以将共享邮箱转换回专用 (用户) 邮箱。</span><span class="sxs-lookup"><span data-stu-id="15576-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="15576-107">**以下是您需要了解的一些非常重要的事情：**</span><span class="sxs-lookup"><span data-stu-id="15576-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="15576-108">要转换的用户邮箱需要分配有许可证，然后才能将其转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="15576-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="15576-109">否则，将看不到用于转换邮箱的选项。</span><span class="sxs-lookup"><span data-stu-id="15576-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="15576-110">如果已删除许可证，请重新添加它，以便转换邮箱。</span><span class="sxs-lookup"><span data-stu-id="15576-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="15576-111">将邮箱转换为共享邮箱后，可以从用户帐户中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="15576-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="15576-112">共享邮箱可具有多达 50 GB 的数据，无需为其分配许可证。</span><span class="sxs-lookup"><span data-stu-id="15576-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="15576-113">要保留的数据超过此限制，需要为其分配许可证。</span><span class="sxs-lookup"><span data-stu-id="15576-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="15576-114">你可能需要从共享邮箱中删除一 (大电子邮件，例如) 附件的电子邮件，以便你可以删除许可证。</span><span class="sxs-lookup"><span data-stu-id="15576-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="15576-115">不要删除旧用户帐户。</span><span class="sxs-lookup"><span data-stu-id="15576-115">Don't delete the old user's account.</span></span> <span data-ttu-id="15576-116">这是定位共享邮箱所需的。</span><span class="sxs-lookup"><span data-stu-id="15576-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="15576-117">如果已删除用户帐户，请参阅转换已删除 [用户的邮箱](#convert-the-mailbox-of-a-deleted-user)。</span><span class="sxs-lookup"><span data-stu-id="15576-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="15576-118">将邮箱转换为共享邮箱后，这些规则将保持不变。</span><span class="sxs-lookup"><span data-stu-id="15576-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="15576-119">使用 Exchange 管理中心转换邮箱</span><span class="sxs-lookup"><span data-stu-id="15576-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="15576-120">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="15576-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="15576-121">选择 **"收件人** \> **""邮箱"。**</span><span class="sxs-lookup"><span data-stu-id="15576-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="15576-122">选择用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="15576-122">Select the user mailbox.</span></span> <span data-ttu-id="15576-123">在 **"转换为共享邮箱"下，** 选择"**转换"。**</span><span class="sxs-lookup"><span data-stu-id="15576-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="15576-124">如果邮箱小于 50 GB，可以从用户中删除许可证，[](../manage/remove-licenses-from-users.md)并停止付费。</span><span class="sxs-lookup"><span data-stu-id="15576-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="15576-125">不要删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="15576-125">Don't delete the user's account.</span></span> <span data-ttu-id="15576-126">共享邮箱需要它作为定位标记。</span><span class="sxs-lookup"><span data-stu-id="15576-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="15576-127">如果要转换离开组织的员工的邮箱，应执行其他步骤以确保他们不再登录。</span><span class="sxs-lookup"><span data-stu-id="15576-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="15576-128">请参阅从[公司中删除以前的Microsoft 365。](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="15576-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="15576-129">无需在邮箱转换期间重置用户密码。</span><span class="sxs-lookup"><span data-stu-id="15576-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="15576-130">但是，如果未重置密码，则 **完成** 邮箱转换后，原始用户名和密码将继续工作。</span><span class="sxs-lookup"><span data-stu-id="15576-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="15576-131">有关有关共享邮箱的一切其他信息，请参阅关于 [共享](about-shared-mailboxes.md) 邮箱和 [创建共享邮箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="15576-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="15576-132">共享邮箱不需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="15576-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="15576-133">但是，如果你想要启用就地存档或将就地保留或诉讼保留置于共享邮箱，则必须向邮箱分配带有 Exchange Online Archiving 的 Exchange Online 计划 1 或 Exchange Online 计划 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="15576-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="15576-134">转换已删除用户的邮箱</span><span class="sxs-lookup"><span data-stu-id="15576-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="15576-135">假设你已删除用户帐户，现在想要将其旧邮箱转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="15576-135">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="15576-136">下面是你需要执行哪些工作：</span><span class="sxs-lookup"><span data-stu-id="15576-136">Here's what you need to do:</span></span>

1. <span data-ttu-id="15576-137">[还原用户帐户](../add-users/restore-user.md)。</span><span class="sxs-lookup"><span data-stu-id="15576-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="15576-138">请确保分配Microsoft 365许可证。</span><span class="sxs-lookup"><span data-stu-id="15576-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="15576-139">重置用户密码。</span><span class="sxs-lookup"><span data-stu-id="15576-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="15576-140">等待 20-30 分钟，以重新创建其邮箱。</span><span class="sxs-lookup"><span data-stu-id="15576-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="15576-141">现在按照此页面上的说明将其邮箱转换为共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="15576-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="15576-142">完成后，可以从用户邮箱中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="15576-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="15576-143">不要删除用户的旧邮箱。</span><span class="sxs-lookup"><span data-stu-id="15576-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="15576-144">共享邮箱需要它作为定位标记。</span><span class="sxs-lookup"><span data-stu-id="15576-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="15576-145">将成员添加到共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="15576-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="15576-146">将共享邮箱转换回用户的专用 () 邮箱</span><span class="sxs-lookup"><span data-stu-id="15576-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="15576-147">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="15576-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="15576-148">选择 **"收件人** \> **""共享"。**</span><span class="sxs-lookup"><span data-stu-id="15576-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="15576-149">选择共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="15576-149">Select the shared mailbox.</span></span> <span data-ttu-id="15576-150">在 **"转换为常规邮箱"下，** 选择"**转换"。**</span><span class="sxs-lookup"><span data-stu-id="15576-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="15576-151">返回到管理中心。</span><span class="sxs-lookup"><span data-stu-id="15576-151">Go back to the admin center.</span></span> <span data-ttu-id="15576-152">在 **"用户**"下，选择与旧共享邮箱关联的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="15576-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="15576-153">向帐户分配许可证，然后重置密码。</span><span class="sxs-lookup"><span data-stu-id="15576-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="15576-154">设置邮箱需要几分钟时间，但之后，打算使用该帐户的人就可以了。</span><span class="sxs-lookup"><span data-stu-id="15576-154">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="15576-155">登录后，他们会看到共享邮箱中过去的电子邮件和日历项目。</span><span class="sxs-lookup"><span data-stu-id="15576-155">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="15576-156">在混合环境中转换用户邮箱</span><span class="sxs-lookup"><span data-stu-id="15576-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="15576-157">有关将用户邮箱转换为混合环境中共享邮箱Exchange，请参阅：</span><span class="sxs-lookup"><span data-stu-id="15576-157">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="15576-158">在内部部署部署环境中创建或修改远程共享邮箱Exchange Cmdlet</span><span class="sxs-lookup"><span data-stu-id="15576-158">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="15576-159">在混合部署中运行目录同步后，共享邮箱Exchange转换为用户邮箱</span><span class="sxs-lookup"><span data-stu-id="15576-159">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="15576-160">如果您是组织管理或收件人管理角色组的成员，可以使用 Exchange 命令行管理程序将用户邮箱更改为本地共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="15576-160">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="15576-161">例如，`Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`。</span><span class="sxs-lookup"><span data-stu-id="15576-161">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-content"></a><span data-ttu-id="15576-162">相关内容</span><span class="sxs-lookup"><span data-stu-id="15576-162">Related content</span></span>

<span data-ttu-id="15576-163">[关于共享邮箱 (](about-shared-mailboxes.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="15576-163">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>

<span data-ttu-id="15576-164">[创建共享邮箱 (](create-a-shared-mailbox.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="15576-164">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="15576-165">[配置共享邮箱 (](configure-a-shared-mailbox.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="15576-165">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="15576-166">[从共享邮箱中删除许可证 (](remove-license-from-shared-mailbox.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="15576-166">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="15576-167">[解决共享邮箱问题 (](resolve-issues-with-shared-mailboxes.md) 本文) </span><span class="sxs-lookup"><span data-stu-id="15576-167">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>