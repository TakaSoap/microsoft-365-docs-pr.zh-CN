---
title: 为组织中的邮箱设置存档和删除策略
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
ms.custom: seo-marvel-apr2020
description: 了解如何在 Microsoft 365 中创建存档和删除策略，以将项目自动移动到用户的存档邮箱。
ms.openlocfilehash: 5e8675c1cc6e1df4c22e55648e1655798bae5e5b
ms.sourcegitcommit: 21b0ea5715e20b4ab13719eb18c97fadb49b563d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49624774"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-organization"></a><span data-ttu-id="bb16f-103">为组织中的邮箱设置存档和删除策略</span><span class="sxs-lookup"><span data-stu-id="bb16f-103">Set up an archive and deletion policy for mailboxes in your organization</span></span>

<span data-ttu-id="bb16f-104">在 Microsoft 365 中，管理员可以创建存档和删除策略，该策略会自动将项目移动到用户的存档邮箱，并自动从邮箱中删除项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-104">In Microsoft 365, admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span> <span data-ttu-id="bb16f-105">管理员通过创建分配给邮箱的保留策略来达到此目标，并在特定时间段后将项目移动到用户的存档邮箱，并且还会在项目达到特定期限后从邮箱中删除项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-105">The admin does this by creating a retention policy that's assigned to mailboxes, and moves items to a user's archive mailbox after a certain period of time and that also deletes items from the mailbox after they reach a certain age limit.</span></span> <span data-ttu-id="bb16f-106">确定移动或删除哪些项目以及何时发生的实际规则称为保留标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-106">The actual rules that determine what items are moved or deleted and when that happens are called retention tags.</span></span> <span data-ttu-id="bb16f-107">保留标记链接到保留策略，而保留策略又分配给用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-107">Retention tags are linked to a retention policy, that in turn is assigned to a user's mailbox.</span></span> <span data-ttu-id="bb16f-108">保留标记将保留设置应用于用户邮箱中的单个邮件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="bb16f-108">A retention tag applies retention settings to individual messages and folders in a user's mailbox.</span></span> <span data-ttu-id="bb16f-109">它定义邮件在邮箱中的保留时间，以及当邮件达到指定的保留时间时将采取的操作。</span><span class="sxs-lookup"><span data-stu-id="bb16f-109">It defines how long a message remains in the mailbox and what action is taken when the message reaches the specified retention age.</span></span> <span data-ttu-id="bb16f-110">当邮件达到其保留时间时，该邮件将移动到用户的存档邮箱或被删除。</span><span class="sxs-lookup"><span data-stu-id="bb16f-110">When a message reaches its retention age, it's either moved to the user's archive mailbox or it's deleted.</span></span>
  
<span data-ttu-id="bb16f-111">本文中的步骤将为名为"Alpine House"的虚构组织设置存档和保留策略。</span><span class="sxs-lookup"><span data-stu-id="bb16f-111">The steps in this article will set up an archiving and retention policy for a fictitious organization named Alpine House.</span></span> <span data-ttu-id="bb16f-112">设置此策略包括以下任务：</span><span class="sxs-lookup"><span data-stu-id="bb16f-112">Setting up this policy includes the following tasks:</span></span>
  
- <span data-ttu-id="bb16f-113">为组织每个用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-113">Enabling an archive mailbox for every user in the organization.</span></span> <span data-ttu-id="bb16f-114">这将为用户提供添加邮箱存储，并且此存储是必需的，以便保留策略可以将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-114">This gives users addition mailbox storage, and is required so that a retention policy can move items to the archive mailbox.</span></span> <span data-ttu-id="bb16f-115">它还允许用户将项目移动到存档邮箱来存储存档信息。</span><span class="sxs-lookup"><span data-stu-id="bb16f-115">It also lets a user store archival information by moving items to their archive mailbox.</span></span>

- <span data-ttu-id="bb16f-116">创建三个执行以下操作的自定义保留标记：</span><span class="sxs-lookup"><span data-stu-id="bb16f-116">Creating three custom retention tags that do the following:</span></span>

  - <span data-ttu-id="bb16f-117">自动将 3 年的项目移动到用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-117">Automatically moves items that are 3 years old to the user's archive mailbox.</span></span> <span data-ttu-id="bb16f-118">将项目移动到存档邮箱可释放用户主邮箱中的空间。</span><span class="sxs-lookup"><span data-stu-id="bb16f-118">Moving items to the archive mailbox frees up space in a user's primary mailbox.</span></span>

  - <span data-ttu-id="bb16f-119">自动从"已删除邮件"文件夹中删除 5 年的项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-119">Automatically deletes items that are 5 years old from the Deleted Items folder.</span></span> <span data-ttu-id="bb16f-120">这还会释放用户的主邮箱中的空间。</span><span class="sxs-lookup"><span data-stu-id="bb16f-120">This also frees up space in the user's primary mailbox.</span></span> <span data-ttu-id="bb16f-121">用户将有机会在必要时恢复这些项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-121">User's will have the opportunity to recover these items if necessary.</span></span> <span data-ttu-id="bb16f-122">有关详细信息，请参阅 ["详细信息"](#more-information) 部分中的脚注。</span><span class="sxs-lookup"><span data-stu-id="bb16f-122">See the footnote in the [More information](#more-information) section for more details.</span></span> 

  - <span data-ttu-id="bb16f-123">自动 (并永久) 从主邮箱和存档邮箱中删除 7 年的项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-123">Automatically (and permanently) deletes items that are 7 years old from both the primary and archive mailbox.</span></span> <span data-ttu-id="bb16f-124">由于遵从性法规，某些组织需要将电子邮件保留一段时间。</span><span class="sxs-lookup"><span data-stu-id="bb16f-124">Because of compliance regulations, some organization's are required to retain email for a certain period of time.</span></span> <span data-ttu-id="bb16f-125">在此时间段过期后，组织可能希望永久删除这些项目用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-125">After this time period expires, an organization might want to permanently remove these items user mailboxes.</span></span>

- <span data-ttu-id="bb16f-126">创建新的保留策略，并添加新的自定义保留标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-126">Creating a new retention policy and adding the new custom retention tags to it.</span></span> <span data-ttu-id="bb16f-127">此外，你还将内置保留标记添加到新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="bb16f-127">Additionally, you'll also add built-in retention tags to the new retention policy.</span></span> <span data-ttu-id="bb16f-128">这包括用户可为其邮箱中的项目分配的个人标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-128">This includes personal tags that users can assign to items in their mailbox.</span></span> <span data-ttu-id="bb16f-129">您还将添加一个保留标记，用于将用户主邮箱中的"可恢复的项目"文件夹中的项目移动到存档邮箱中的"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="bb16f-129">You'll also add a retention tag that moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="bb16f-130">这有助于在用户的邮箱处于保留状态时释放用户的"可恢复的项目"文件夹中的空间。</span><span class="sxs-lookup"><span data-stu-id="bb16f-130">This helps free up space in a user's Recoverable Items folder when their mailbox is placed on hold.</span></span>

<span data-ttu-id="bb16f-131">可以按照本文中的部分或所有步骤为自己组织的邮箱设置存档和删除策略。</span><span class="sxs-lookup"><span data-stu-id="bb16f-131">You can follow some or all of the steps in this article to set up an archive and deletion policy for mailboxes in your own organization.</span></span> <span data-ttu-id="bb16f-132">建议您先在几个邮箱上测试此过程，然后再在组织的所有邮箱上实现此过程。</span><span class="sxs-lookup"><span data-stu-id="bb16f-132">We recommend that you test this process on a few mailboxes before implementing it on all mailboxes in your organization.</span></span>
  
## <a name="before-you-set-up-an-archive-and-deletion-policy"></a><span data-ttu-id="bb16f-133">设置存档和删除策略之前</span><span class="sxs-lookup"><span data-stu-id="bb16f-133">Before you set up an archive and deletion policy</span></span>

- <span data-ttu-id="bb16f-134">您必须是组织的全局管理员才能执行本主题中的步骤。</span><span class="sxs-lookup"><span data-stu-id="bb16f-134">You have to be a global administrator in your organization to perform the steps in this topic.</span></span> 

- <span data-ttu-id="bb16f-135">创建新用户帐户并为其分配 Exchange Online 许可证时，将自动为该用户创建一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-135">When you create a new user account and assign the user an Exchange Online license, a mailbox is automatically created for the user.</span></span> <span data-ttu-id="bb16f-136">创建邮箱时，系统会自动为其分配默认保留策略，名为"默认 MRM 策略"。</span><span class="sxs-lookup"><span data-stu-id="bb16f-136">When the mailbox is created, it's automatically assigned a default retention policy, named Default MRM Policy.</span></span> <span data-ttu-id="bb16f-137">本文将创建新的保留策略，然后将它分配给用户邮箱，以替换默认 MRM 策略。</span><span class="sxs-lookup"><span data-stu-id="bb16f-137">In this article, you will create a new retention policy and then assign it to user mailboxes, replacing the Default MRM policy.</span></span> <span data-ttu-id="bb16f-138">邮箱一次只能分配一个保留策略。</span><span class="sxs-lookup"><span data-stu-id="bb16f-138">A mailbox can have only one retention policy assigned to it at any one time.</span></span>

- <span data-ttu-id="bb16f-139">若要详细了解 Exchange Online 中的保留标记和保留策略，请参阅 [保留标记和保留策略](https://go.microsoft.com/fwlink/p/?LinkId=404424)。</span><span class="sxs-lookup"><span data-stu-id="bb16f-139">To learn more about retention tags and retention policies in Exchange Online, see [Retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkId=404424).</span></span>

## <a name="step-1-enable-archive-mailboxes-for-users"></a><span data-ttu-id="bb16f-140">步骤 1：为用户启用存档邮箱</span><span class="sxs-lookup"><span data-stu-id="bb16f-140">Step 1: Enable archive mailboxes for users</span></span>

<span data-ttu-id="bb16f-141">第一步是为组织中每个用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-141">The first step is to enable the archive mailbox for each user in your organization.</span></span> <span data-ttu-id="bb16f-142">必须启用用户的存档邮箱，以便具有"移动到存档"保留操作保留的保留标记可以在保留时间到期后移动项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-142">A user's archive mailbox has to be enabled so that a retention tag with a "Move to Archive" retention action can move the item after the retention age expires.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb16f-143">您可以在此过程期间随时启用存档邮箱，只要在此过程完成之前在某些时候启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-143">You can enable archive mailboxes any time during this process, just as long as they're enabled at some point before you complete the process.</span></span> <span data-ttu-id="bb16f-144">如果未启用存档邮箱，则不会对已为其分配存档或删除策略的任何项目执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="bb16f-144">If an archive mailbox isn't enabled, no action is taken on any items that have an archive or deletion policy assigned to it.</span></span>
  
1. <span data-ttu-id="bb16f-145">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="bb16f-145">Go to [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="bb16f-146">使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="bb16f-146">Sign in using your global administrator account.</span></span>
    
3. <span data-ttu-id="bb16f-147">在安全&中心，转到 **"信息治理** \> **存档"。**</span><span class="sxs-lookup"><span data-stu-id="bb16f-147">In the Security & Compliance Center, go to **Information governance** \> **Archive**.</span></span>

    <span data-ttu-id="bb16f-148">将显示组织中邮箱的列表，以及启用还是禁用相应的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-148">A list of the mailboxes in your organization is displayed and whether the corresponding archive mailbox is enabled or disabled.</span></span>

4. <span data-ttu-id="bb16f-149">单击列表中的第一个邮箱，按住 **Shift** 键，然后单击列表中的最后一个邮箱，选择所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-149">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span>

    > [!TIP]
    > <span data-ttu-id="bb16f-150">此步骤假定未启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-150">This step assumes that no archive mailboxes are enabled.</span></span> <span data-ttu-id="bb16f-151">如果有任何已启用存档的邮箱，请按住 **Ctrl** 键，然后单击每个已禁用存档邮箱的邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-151">If you have any mailboxes with the archive enabled, hold down the **Ctrl** key and click each mailbox that has a disabled archive mailbox.</span></span> <span data-ttu-id="bb16f-152">或者，您可以单击"存档 **邮箱** "列标题，根据存档邮箱是启用还是禁用来对行进行排序，以便更轻松地选择邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-152">Or you can click the **Archive mailbox** column header to sort the rows based on whether the archive mailbox is enabled or disabled to make it easier to select mailboxes.</span></span>
  
5. <span data-ttu-id="bb16f-153">在详细信息窗格中的"**批量编辑"下**，单击"**启用"。**</span><span class="sxs-lookup"><span data-stu-id="bb16f-153">In the details pane, under **Bulk Edit**, click **Enable**.</span></span>

    <span data-ttu-id="bb16f-154">将显示一条警告，指出超过两年的项目将移动到新的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-154">A warning is displayed saying that items that are older than two years will be moved to the new archive mailbox.</span></span> <span data-ttu-id="bb16f-155">这是因为创建新用户邮箱时为其分配的默认保留策略具有保留期限为 2 年的存档默认策略标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-155">This is because the default retention policy that's assigned a new user mailbox when it's created has an archive default policy tag that has a retention age of 2 years.</span></span> <span data-ttu-id="bb16f-156">您将在步骤 2 创建的自定义存档默认策略标记的保留期限为 3 年。</span><span class="sxs-lookup"><span data-stu-id="bb16f-156">The custom archive default policy tag that you'll create in Step 2 has a retention age of 3 years.</span></span> <span data-ttu-id="bb16f-157">这意味着 3 年或更旧的项目将移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-157">That means items that are 3 years or older will be moved to the archive mailbox.</span></span>

6. <span data-ttu-id="bb16f-158">单击 **"** 是"关闭警告消息并启动进程以启用每个选定邮箱的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-158">Click **Yes** to close the warning message and start the process to enable the archive mailbox for each selected mailbox.</span></span>

7. <span data-ttu-id="bb16f-159">此过程完成后，单击 **"刷新** ![ 刷新" ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) 以更新"存档"页上的列表。</span><span class="sxs-lookup"><span data-stu-id="bb16f-159">When the process is complete, click **Refresh** ![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the list on the **Archive** page.</span></span>

    <span data-ttu-id="bb16f-160">为组织中每个用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-160">The archive mailbox is enabled for all user's in your organization.</span></span>

    ![已启用存档邮箱的邮箱列表](../media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)

## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a><span data-ttu-id="bb16f-162">步骤 2：为存档和删除策略创建新的保留标记</span><span class="sxs-lookup"><span data-stu-id="bb16f-162">Step 2: Create new retention tags for the archive and deletion policies</span></span>

<span data-ttu-id="bb16f-163">在此步骤中，将创建前面介绍的三个自定义保留标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-163">In this step, you'll create the three custom retention tags that were previously described.</span></span>
  
- <span data-ttu-id="bb16f-164">House 3 年移动到存档 (自定义存档策略) </span><span class="sxs-lookup"><span data-stu-id="bb16f-164">Alpine House 3 Year Move to Archive (custom archive policy)</span></span>

- <span data-ttu-id="bb16f-165">一年 7 年，将 (自定义删除策略) </span><span class="sxs-lookup"><span data-stu-id="bb16f-165">Alpine House 7 Year Permanently Delete (custom deletion policy)</span></span>

- <span data-ttu-id="bb16f-166">一年一次，"一座大楼删除项目 5 年"， ("已删除邮件"文件夹文件夹的自定义标记) </span><span class="sxs-lookup"><span data-stu-id="bb16f-166">Alpine House Deleted Items 5 Years Delete and Allow Recovery (custom tag for the Deleted Items folder)</span></span>

<span data-ttu-id="bb16f-167">若要创建新的保留标记，将使用 Exchange Online (EAC) Exchange 管理中心。</span><span class="sxs-lookup"><span data-stu-id="bb16f-167">To create new retention tags, you'll use the Exchange admin center (EAC) in your Exchange Online organization.</span></span> <span data-ttu-id="bb16f-168">请务必使用经典版本的 EAC。</span><span class="sxs-lookup"><span data-stu-id="bb16f-168">Be sure to use the classic version of the EAC.</span></span>
  
1. <span data-ttu-id="bb16f-169">转到 [https://admin.protection.outlook.com/ecp/](https://admin.protection.outlook.com/ecp/) 你的凭据并登录。</span><span class="sxs-lookup"><span data-stu-id="bb16f-169">Go to [https://admin.protection.outlook.com/ecp/](https://admin.protection.outlook.com/ecp/) and sign in using your credentials.</span></span>
  
2. <span data-ttu-id="bb16f-170">在 EAC 中，转到 **"合规性管理**  >  **保留标记"**</span><span class="sxs-lookup"><span data-stu-id="bb16f-170">In the EAC, go to **Compliance management** > **Retention tags**</span></span>

    <span data-ttu-id="bb16f-171">将显示组织的保留标记列表。</span><span class="sxs-lookup"><span data-stu-id="bb16f-171">A list of the retention tags for your organization is displayed.</span></span>

### <a name="create-a-custom-archive-default-policy-tag"></a><span data-ttu-id="bb16f-172">创建自定义存档默认策略标记</span><span class="sxs-lookup"><span data-stu-id="bb16f-172">Create a custom archive default policy tag</span></span>
  
<span data-ttu-id="bb16f-173">首先，你将使用 DPT (创建一个自定义) 策略标记，该标记将在 3 年后将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-173">First, you'll create a custom archive default policy tag (DPT) that will move items to the archive mailbox after 3 years.</span></span>
  
1. <span data-ttu-id="bb16f-174">在"**保留标记"** 页上，**单击"** 新建标记新建"图标，然后选择"自动应用于整个邮箱" (![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **默认) 。**</span><span class="sxs-lookup"><span data-stu-id="bb16f-174">On the **Retention tags** page, click **New tag**![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span>

2. <span data-ttu-id="bb16f-175">在自动 **应用于整个邮箱的新 (默认**) ，填写以下字段：</span><span class="sxs-lookup"><span data-stu-id="bb16f-175">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 

    ![用于创建新的存档默认策略标记的设置](../media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
   1. <span data-ttu-id="bb16f-177">**名称** 键入新保留标记的名称。</span><span class="sxs-lookup"><span data-stu-id="bb16f-177">**Name** Type a name for the new retention tag.</span></span> 

   2. <span data-ttu-id="bb16f-178">**保留操作** 选择 **"移动到存档** "，在保留期到期时将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-178">**Retention action** Select **Move to Archive** to move items to the archive mailbox when the retention period expires.</span></span>

   3. <span data-ttu-id="bb16f-179">**保留期** Select **When the item reaches the following age (in days) ，** and then enter the duration of the retention period.</span><span class="sxs-lookup"><span data-stu-id="bb16f-179">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="bb16f-180">对于此方案，项目将在 1095 天后移动到存档邮箱， (3 年) 。</span><span class="sxs-lookup"><span data-stu-id="bb16f-180">For this scenario, items will be moved to the archive mailbox after 1095 days (3 years).</span></span>

   4. <span data-ttu-id="bb16f-181">**注释** (可选) 键入说明自定义保留标记用途的注释。</span><span class="sxs-lookup"><span data-stu-id="bb16f-181">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span>

3. <span data-ttu-id="bb16f-182">单击 **"** 保存"创建自定义存档 DPT。</span><span class="sxs-lookup"><span data-stu-id="bb16f-182">Click **Save** to create the custom archive DPT.</span></span>

    <span data-ttu-id="bb16f-183">新的存档 DPT 显示在保留标记列表中。</span><span class="sxs-lookup"><span data-stu-id="bb16f-183">The new archive DPT is displayed in the list of retention tags.</span></span>

### <a name="create-a-custom-deletion-default-policy-tag"></a><span data-ttu-id="bb16f-184">创建自定义删除默认策略标记</span><span class="sxs-lookup"><span data-stu-id="bb16f-184">Create a custom deletion default policy tag</span></span>
  
<span data-ttu-id="bb16f-185">接下来，您将创建另一个自定义 DPT，但此 DPT 将是一个在 7 年后永久删除项目的删除策略。</span><span class="sxs-lookup"><span data-stu-id="bb16f-185">Next, you'll create another custom DPT but this one will be a deletion policy that permanently deletes items after 7 years.</span></span>
  
1. <span data-ttu-id="bb16f-186">在"**保留标记"** 页上，**单击"** 新建标记新建"图标，然后选择"自动应用于整个邮箱" (![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **默认) 。**</span><span class="sxs-lookup"><span data-stu-id="bb16f-186">On the **Retention tags** page, click **New tag**![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span>

2. <span data-ttu-id="bb16f-187">在自动 **应用于整个邮箱的新 (默认**) ，填写以下字段：</span><span class="sxs-lookup"><span data-stu-id="bb16f-187">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 

    ![用于创建新的删除默认策略标记的设置](../media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
   1. <span data-ttu-id="bb16f-189">**名称** 键入新保留标记的名称。</span><span class="sxs-lookup"><span data-stu-id="bb16f-189">**Name** Type a name for the new retention tag.</span></span> 

   2. <span data-ttu-id="bb16f-190">**保留操作** 选择 **"永久删除** "以在保留期到期时清除邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-190">**Retention action** Select **Permanently Delete** to purge items from the mailbox when the retention period expires.</span></span>

   3. <span data-ttu-id="bb16f-191">**保留期** Select **When the item reaches the following age (in days) ，** and then enter the duration of the retention period.</span><span class="sxs-lookup"><span data-stu-id="bb16f-191">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="bb16f-192">对于此方案，项目将在 2555 天后清除， (7 年后清除) 。</span><span class="sxs-lookup"><span data-stu-id="bb16f-192">For this scenario, items will be purged after 2555 days (7 years).</span></span>

   4. <span data-ttu-id="bb16f-193">**注释** (可选) 键入说明自定义保留标记用途的注释。</span><span class="sxs-lookup"><span data-stu-id="bb16f-193">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 

3. <span data-ttu-id="bb16f-194">单击 **"** 保存"创建自定义删除 DPT。</span><span class="sxs-lookup"><span data-stu-id="bb16f-194">Click **Save** to create the custom deletion DPT.</span></span> 

    <span data-ttu-id="bb16f-195">新的删除 DPT 显示在保留标记列表中。</span><span class="sxs-lookup"><span data-stu-id="bb16f-195">The new deletion DPT is displayed in the list of retention tags.</span></span>

### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a><span data-ttu-id="bb16f-196">为"已删除邮件"文件夹创建自定义保留策略标记</span><span class="sxs-lookup"><span data-stu-id="bb16f-196">Create a custom retention policy tag for the Deleted Items folder</span></span>
  
<span data-ttu-id="bb16f-197">最后一个创建的保留标记是"已删除邮件" (RPT) 的自定义保留策略标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-197">The last retention tag that you'll create is a custom retention policy tag (RPT) for the Deleted Items folder.</span></span> <span data-ttu-id="bb16f-198">此标记将在 5 年后删除"已删除邮件"文件夹中的项目，并提供用户可以使用"恢复已删除邮件"工具恢复项目的恢复期。</span><span class="sxs-lookup"><span data-stu-id="bb16f-198">This tag will delete items in the Deleted Items folder after 5 years, and provides a recovery period when users can use the Recover Deleted Items tool to recover an item.</span></span>
  
1. <span data-ttu-id="bb16f-199">在" **保留标记"** 页上，单击 **"新建标记**" ![ 图标， ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) 然后选择 **自动应用于默认文件夹**。</span><span class="sxs-lookup"><span data-stu-id="bb16f-199">On the **Retention tags** page, click **New tag** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to a default folder**.</span></span>

2. <span data-ttu-id="bb16f-200">在 **自动应用于默认文件夹页** 的新标记上，填写以下字段：</span><span class="sxs-lookup"><span data-stu-id="bb16f-200">On the **New tag applied automatically to a default folder** page, complete the following fields:</span></span>

    ![为"已删除邮件"文件夹创建新的保留策略标记的设置](../media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
   1. <span data-ttu-id="bb16f-202">**名称** 键入新保留标记的名称。</span><span class="sxs-lookup"><span data-stu-id="bb16f-202">**Name** Type a name for the new retention tag.</span></span> 

   2. <span data-ttu-id="bb16f-203">**将此标记应用于以下默认文件夹** 在下拉列表中，选择 **"已删除邮件"。**</span><span class="sxs-lookup"><span data-stu-id="bb16f-203">**Apply this tag to the following default folder** In the drop-down list, select **Deleted Items**.</span></span>

   3. <span data-ttu-id="bb16f-204">**保留操作** 选择"删除并允许恢复"以在保留期过期时删除项目，但允许用户在已删除项目保留期（默认为 14 天）内恢复已删除) 。 (</span><span class="sxs-lookup"><span data-stu-id="bb16f-204">**Retention action** Select **Delete and Allow Recovery** to delete items when the retention period expires, but allow users to recover a deleted item within the deleted item retention period (which by default is 14 days).</span></span>

   4. <span data-ttu-id="bb16f-205">**保留期** Select **When the item reaches the following age (in days) ，** and then enter the duration of the retention period.</span><span class="sxs-lookup"><span data-stu-id="bb16f-205">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="bb16f-206">对于此方案，将在 1825 天后删除项目， (5 年后删除) 。</span><span class="sxs-lookup"><span data-stu-id="bb16f-206">For this scenario, items will be deleted after 1825 days (5 years).</span></span>

   5. <span data-ttu-id="bb16f-207">**注释** (可选) 键入说明自定义保留标记用途的注释。</span><span class="sxs-lookup"><span data-stu-id="bb16f-207">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 

3. <span data-ttu-id="bb16f-208">单击 **"** 保存"为"已删除邮件"文件夹创建自定义 RPT。</span><span class="sxs-lookup"><span data-stu-id="bb16f-208">Click **Save** to create the custom RPT for the Deleted Items folder.</span></span>

    <span data-ttu-id="bb16f-209">新的 RPT 显示在保留标记列表中。</span><span class="sxs-lookup"><span data-stu-id="bb16f-209">The new RPT is displayed in the list of retention tags.</span></span>

## <a name="step-3-create-a-new-retention-policy"></a><span data-ttu-id="bb16f-210">步骤 3：创建新的保留策略</span><span class="sxs-lookup"><span data-stu-id="bb16f-210">Step 3: Create a new retention policy</span></span>

<span data-ttu-id="bb16f-211">创建自定义保留标记后，下一步是创建新的保留策略并添加保留标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-211">After you create the custom retention tags, the next step is to create a new retention policy and add the retention tags.</span></span> <span data-ttu-id="bb16f-212">您将添加在步骤 2 中创建的三个自定义保留标记，以及第一部分中提及的内置标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-212">You'll add the three custom retention tags that you created in Step 2, and the built-in tags that were mentioned in the first section.</span></span> <span data-ttu-id="bb16f-213">在步骤 4 中，将这个新保留策略分配给用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-213">In Step 4, you'll assign this new retention policy to user mailboxes.</span></span>
  
1. <span data-ttu-id="bb16f-214">在 EAC 中，转到 **"合规性管理**  >  **保留策略"。**</span><span class="sxs-lookup"><span data-stu-id="bb16f-214">In the EAC, go to **Compliance management** > **Retention policies**.</span></span>

2. <span data-ttu-id="bb16f-215">在" **保留策略"** 页上，单击 **"新建** ![ "图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) 。</span><span class="sxs-lookup"><span data-stu-id="bb16f-215">On the **Retention policies** page, click **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>

3. <span data-ttu-id="bb16f-216">在 **"名称** "框中，键入新保留策略的名称;例如 **，House House 存档和删除策略**。</span><span class="sxs-lookup"><span data-stu-id="bb16f-216">In the **Name** box, type a name for the new retention policy; for example, **Alpine House Archive and Deletion Policy**.</span></span>

4. <span data-ttu-id="bb16f-217">在 **"保留标记"** 下，单击 **"** ![ 添加新"图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) 。</span><span class="sxs-lookup"><span data-stu-id="bb16f-217">Under **Retention tags**, click **Add** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>

    <span data-ttu-id="bb16f-218">将显示组织中保留标记的列表。</span><span class="sxs-lookup"><span data-stu-id="bb16f-218">A list of the retention tags in your organization is displayed.</span></span> <span data-ttu-id="bb16f-219">请注意，将显示在步骤 2 中创建的自定义标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-219">Note the custom tags that you created in Step 2 are displayed.</span></span>

5. <span data-ttu-id="bb16f-220">添加以下屏幕截图中突出显示的 9 个保留标记 ("详细信息"部分将详细介绍这些标记) 。 [](#more-information)</span><span class="sxs-lookup"><span data-stu-id="bb16f-220">Add the 9 retention tags that are highlighted in the following screenshot (these tags are described in more detail in the [More information](#more-information) section).</span></span> <span data-ttu-id="bb16f-221">若要添加保留标记，请选择它，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="bb16f-221">To add a retention tag, select it and then click **Add**.</span></span>

    ![将保留标记添加到新的保留策略](../media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > <span data-ttu-id="bb16f-223">按住 **Ctrl** 键，然后单击每个标记，可以选择多个保留标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-223">You can select multiple retention tags by holding down the **Ctrl** key and then clicking each tag.</span></span> 
  
6. <span data-ttu-id="bb16f-224">添加保留标记后，单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="bb16f-224">After you've added the retention tags, click **OK**.</span></span>

7. <span data-ttu-id="bb16f-225">在 **"新建保留策略"** 页上，单击 **"保存** "创建新策略。</span><span class="sxs-lookup"><span data-stu-id="bb16f-225">On the **New retention policy** page, click **Save** to create the new policy.</span></span>

    <span data-ttu-id="bb16f-226">新的保留策略将显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="bb16f-226">The new retention policy is displayed in the list.</span></span> <span data-ttu-id="bb16f-227">选择它以显示详细信息窗格中链接到它的保留标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-227">Select it to display the retention tags linked to it in the details pane.</span></span>

    ![新的保留策略和链接的保留标记列表](../media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a><span data-ttu-id="bb16f-229">步骤 4：将新的保留策略分配给用户邮箱</span><span class="sxs-lookup"><span data-stu-id="bb16f-229">Step 4: Assign the new retention policy to user mailboxes</span></span>

<span data-ttu-id="bb16f-230">新建邮箱后，默认情况下会为其分配名为"默认 MRM 策略"的保留策略。</span><span class="sxs-lookup"><span data-stu-id="bb16f-230">When a new mailbox is created, a retention policy named Default MRM policy is assigned to it by default.</span></span> <span data-ttu-id="bb16f-231">在此步骤中，您将替换此保留策略 (因为邮箱只能分配有一个保留策略) 只需将步骤 3 中创建的新保留策略分配给组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-231">In this step, you'll replace this retention policy (because a mailbox can have only one retention policy assigned to it) by assigning the new retention policy that you created in Step 3 to the user mailboxes in your organization.</span></span> <span data-ttu-id="bb16f-232">此步骤假定您将新策略分配给组织的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-232">This step assumes that you'll assign the new policy to all mailboxes in your organization.</span></span>
  
1. <span data-ttu-id="bb16f-233">在 EAC 中，转到 **"收件人**  >  **邮箱"。**</span><span class="sxs-lookup"><span data-stu-id="bb16f-233">In the EAC, go to **Recipients** > **Mailboxes**.</span></span>

    <span data-ttu-id="bb16f-234">将显示组织中所有用户邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="bb16f-234">A list of all user mailboxes in your organization is displayed.</span></span>

2. <span data-ttu-id="bb16f-235">单击列表中的第一个邮箱，按住 **Shift** 键，然后单击列表中的最后一个邮箱，选择所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-235">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 

3. <span data-ttu-id="bb16f-236">在 EAC 右侧的详细信息窗格中，在"批量编辑"下，单击 **"更多选项"。**</span><span class="sxs-lookup"><span data-stu-id="bb16f-236">In the details pane on the right side of the EAC, under **Bulk Edit**, click **More options**.</span></span>

4. <span data-ttu-id="bb16f-237">在“保留策略”下，单击“更新”。</span><span class="sxs-lookup"><span data-stu-id="bb16f-237">Under **Retention Policy**, click **Update**.</span></span>

5. <span data-ttu-id="bb16f-238">在 **"批量分配保留策略**"页上的"选择保留策略"下拉列表中，选择在步骤 3 中创建的保留策略;例如 **，House House 存档和保留策略**。</span><span class="sxs-lookup"><span data-stu-id="bb16f-238">On the **Bulk assign retention policy** page, in the **Select the retention policy** drop-down list, select the retention policy that you created in Step 3; for example, **Alpine House Archive and Retention Policy**.</span></span>

6. <span data-ttu-id="bb16f-239">单击 **"** 保存"保存新的保留策略分配。</span><span class="sxs-lookup"><span data-stu-id="bb16f-239">Click **Save** to save the new retention policy assignment.</span></span>

7. <span data-ttu-id="bb16f-240">若要验证新保留策略是否分配给邮箱，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bb16f-240">To verify that the new retention policy was assigned to mailboxes, you can do the following:</span></span>

   1. <span data-ttu-id="bb16f-241">在"邮箱"页上 **选择一个邮箱**，然后单击"编辑 ![ ](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png) "。</span><span class="sxs-lookup"><span data-stu-id="bb16f-241">Select a mailbox on the **Mailboxes** page, and then click **Edit** ![Edit](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png).</span></span>

   2. <span data-ttu-id="bb16f-242">在所选用户的邮箱属性页上，单击"**邮箱功能"。**</span><span class="sxs-lookup"><span data-stu-id="bb16f-242">On the mailbox properties page for the selected user, click **Mailbox features**.</span></span>

   <span data-ttu-id="bb16f-243">分配给邮箱的新策略的名称显示在"保留策略"下拉列表中。 </span><span class="sxs-lookup"><span data-stu-id="bb16f-243">The name of the new policy assigned to the mailbox is displayed in the **Retention policy** drop-down list.</span></span>

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a><span data-ttu-id="bb16f-244"> (可选) 步骤 5：运行托管文件夹助理以应用新设置</span><span class="sxs-lookup"><span data-stu-id="bb16f-244">(Optional) Step 5: Run the Managed Folder Assistant to apply the new settings</span></span>

<span data-ttu-id="bb16f-245">在步骤 4 中将新的保留策略应用于邮箱后，Exchange Online 中可能需要 7 天才能将新的保留设置应用于邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-245">After you apply the new retention policy to mailboxes in Step 4, it can take up to 7 days in Exchange Online for the new retention settings to be applied to the mailboxes.</span></span> <span data-ttu-id="bb16f-246">这是因为名为托管文件夹助理 *的进程每* 7 天至少处理一次邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-246">This is because a process called the *Managed Folder Assistant* processes mailboxes at least once every 7 days.</span></span> <span data-ttu-id="bb16f-247">无需等待托管文件夹助理运行，您可以通过在 Exchange Online PowerShell 中运行 **Start-ManagedFolderAssistant** cmdlet 来强制实现此操作。</span><span class="sxs-lookup"><span data-stu-id="bb16f-247">Instead of waiting for the Managed Folder Assistant to run, you can force this to happen by running the **Start-ManagedFolderAssistant** cmdlet in Exchange Online PowerShell.</span></span>

 <span data-ttu-id="bb16f-248">**运行托管文件夹助理时会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="bb16f-248">**What happens when you run the Managed Folder Assistant?**</span></span> <span data-ttu-id="bb16f-249">它通过检查邮箱中的项目并确定它们是否受保留限制来应用保留策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="bb16f-249">It applies the settings in the retention policy by inspecting items in the mailbox and determining whether they're subject to retention.</span></span> <span data-ttu-id="bb16f-250">然后，它会使用相应的保留标记标记需要保留的项目，然后对已过保留期限的项目执行指定的保留操作。</span><span class="sxs-lookup"><span data-stu-id="bb16f-250">It then stamps items subject to retention with the appropriate retention tag, and then takes the specified retention action on items past their retention age.</span></span>
  
<span data-ttu-id="bb16f-251">下面是连接到 Exchange Online PowerShell 的步骤，然后在组织每个邮箱上运行托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="bb16f-251">Here are the steps to connect to Exchange Online PowerShell, and then run the Managed Folder Assistant on every mailbox in your organization.</span></span>

1. <span data-ttu-id="bb16f-252">[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)。</span><span class="sxs-lookup"><span data-stu-id="bb16f-252">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span>
  
2. <span data-ttu-id="bb16f-253">运行以下两个命令，为组织中所有的用户邮箱启动托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="bb16f-253">Run the following two commands to start the Managed Folder Assistant for all user mailboxes in your organization.</span></span>

    ```powershell
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```powershell
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

<span data-ttu-id="bb16f-254">就是这么简单。</span><span class="sxs-lookup"><span data-stu-id="bb16f-254">That's it!</span></span> <span data-ttu-id="bb16f-255">你已设置一个 Archive and deletion policy for the Alpine House 组织。</span><span class="sxs-lookup"><span data-stu-id="bb16f-255">You've set up an archive and deletion policy for the Alpine House organization.</span></span>

> [!NOTE]
> <span data-ttu-id="bb16f-256">如前所述，托管文件夹助理每 7 天至少处理一次邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-256">As previously stated, the Managed Folder Assistant processes mailboxes at least once every 7 days.</span></span> <span data-ttu-id="bb16f-257">因此，托管文件夹助理可以更频繁地处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-257">So it's possible that a mailbox can be processed by the Managed Folder Assistant more frequently.</span></span> <span data-ttu-id="bb16f-258">此外，管理员无法预测托管文件夹助理下次处理邮箱的时间，这也是您可能需要手动运行邮箱的一个原因。</span><span class="sxs-lookup"><span data-stu-id="bb16f-258">Also, admins can't predict the next time a mailbox is processed by the Managed Folder Assistant, which is one reason why you may want to run it manually.</span></span> <span data-ttu-id="bb16f-259">但是，如果要暂时阻止托管文件夹助理将新的保留设置应用于邮箱，可以运行该命令来临时禁用托管文件夹助理处理 `Set-Mailbox -ElcProcessingDisabled $true` 邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-259">However, if you want to temporarily prevent the Managed Folder Assistant from applying the new retention settings to a mailbox, you can run the `Set-Mailbox -ElcProcessingDisabled $true` command to temporarily disable the the Managed Folder Assistant from processing a mailbox.</span></span> <span data-ttu-id="bb16f-260">若要重新启用邮箱的托管文件夹助理，请运行 `Set-Mailbox -ElcProcessingDisabled $false` 该命令。</span><span class="sxs-lookup"><span data-stu-id="bb16f-260">To re-enable the Managed Folder Assistant for a mailbox, run the `Set-Mailbox -ElcProcessingDisabled $false` command.</span></span> <span data-ttu-id="bb16f-261">最后，如果邮箱用户具有禁用的帐户，我们不会处理移动项目以存档该邮箱的操作。</span><span class="sxs-lookup"><span data-stu-id="bb16f-261">Finally, if a mailbox user has a disabled account, we will not process the move items to archive action for that mailbox.</span></span>
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a><span data-ttu-id="bb16f-262"> (可选) 步骤 6：将新的保留策略设置为组织的默认策略</span><span class="sxs-lookup"><span data-stu-id="bb16f-262">(Optional) Step 6: Make the new retention policy the default for your organization</span></span>

<span data-ttu-id="bb16f-263">在步骤 4 中，您必须将新的保留策略分配给现有邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-263">In Step 4, you have to assign the new retention policy to existing mailboxes.</span></span> <span data-ttu-id="bb16f-264">但是，您可以配置 Exchange Online，以便新保留策略分配给将来创建的新邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-264">But you can configure Exchange Online so that the new retention policy is assigned to new mailboxes that are created in the future.</span></span> <span data-ttu-id="bb16f-265">为此，可以使用 Exchange Online PowerShell 更新组织的默认邮箱计划。</span><span class="sxs-lookup"><span data-stu-id="bb16f-265">You do this by using Exchange Online PowerShell to update your organization's default mailbox plan.</span></span> <span data-ttu-id="bb16f-266">邮箱 *计划* 是一个模板，可自动配置新邮箱的属性。</span><span class="sxs-lookup"><span data-stu-id="bb16f-266">A *mailbox plan* is a template that automatically configures properties on new mailboxes.</span></span>  <span data-ttu-id="bb16f-267">在此可选步骤中，可以将分配给邮箱计划 (的当前保留策略（默认 MRM 策略) 替换为在步骤 3 中创建的保留策略）。</span><span class="sxs-lookup"><span data-stu-id="bb16f-267">In this optional step, you can replace the current retention policy that's assigned to the mailbox plan (by default, the Default MRM Policy) with the retention policy that you created in Step 3.</span></span> <span data-ttu-id="bb16f-268">更新邮箱计划后，新的保留策略将分配给新邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-268">After you update the mailbox plan, the new retention policy will be assigned to new mailboxes.</span></span>

1. <span data-ttu-id="bb16f-269">[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)。</span><span class="sxs-lookup"><span data-stu-id="bb16f-269">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span>

2. <span data-ttu-id="bb16f-270">运行以下命令以显示有关组织中邮箱计划的信息。</span><span class="sxs-lookup"><span data-stu-id="bb16f-270">Run the following command to display information about the mailbox plans in your organization.</span></span>

    ```powershell
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```

    <span data-ttu-id="bb16f-271">请注意设置为默认值的邮箱计划。</span><span class="sxs-lookup"><span data-stu-id="bb16f-271">Note the mailbox plan that's set as the default.</span></span>

3. <span data-ttu-id="bb16f-272">运行以下命令，将步骤 3 中创建的新保留策略 (例如，为默认邮箱计划分配 **) 和** 保留策略。</span><span class="sxs-lookup"><span data-stu-id="bb16f-272">Run the following command to assign the new retention policy that you created in Step 3 (for example, **Alpine House Archive and Retention Policy**) to the default mailbox plan.</span></span> <span data-ttu-id="bb16f-273">本示例假定默认邮箱计划的名称为 **ExchangeOnlineEnterprise。**</span><span class="sxs-lookup"><span data-stu-id="bb16f-273">This example assumes the name of the default mailbox plan is **ExchangeOnlineEnterprise**.</span></span>

    ```powershell
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```

4. <span data-ttu-id="bb16f-274">可以重新运行步骤 2 中的命令，以验证分配给默认邮箱计划的保留策略已更改。</span><span class="sxs-lookup"><span data-stu-id="bb16f-274">You can rerun the command in step 2 to verify that the retention policy assigned to the default mailbox plan was changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="bb16f-275">更多信息</span><span class="sxs-lookup"><span data-stu-id="bb16f-275">More information</span></span>

- <span data-ttu-id="bb16f-276">如何计算保留时间？</span><span class="sxs-lookup"><span data-stu-id="bb16f-276">How is retention age calculated?</span></span> <span data-ttu-id="bb16f-277">邮箱项目的保留时间从传递日期或项目创建日期开始计算，例如未发送但由用户创建的草稿邮件。</span><span class="sxs-lookup"><span data-stu-id="bb16f-277">The retention age of mailbox items is calculated from the date of delivery or the date of creation for items such as draft messages that aren't sent but are created by the user.</span></span> <span data-ttu-id="bb16f-278">When the Managed Folder Assistant processes items in a mailbox, it stamps a start date and an expiration date for all items that have retention tags with the Delete and Allow Recovery or Permanently Delete retention action.</span><span class="sxs-lookup"><span data-stu-id="bb16f-278">When the Managed Folder Assistant processes items in a mailbox, it stamps a start date and an expiration date for all items that have retention tags with the Delete and Allow Recovery or Permanently Delete retention action.</span></span> <span data-ttu-id="bb16f-279">具有存档标记的项目使用移动日期进行标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-279">Items that have an archive tag are stamped with a move date.</span></span> 

- <span data-ttu-id="bb16f-280">下表提供了有关添加到按照本主题中的步骤创建的自定义保留策略的每个保留标记的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bb16f-280">The following table provides more information about each retention tag that is added to the custom retention policy that was created by following the steps in this topic.</span></span>

    | <span data-ttu-id="bb16f-281">保留标记</span><span class="sxs-lookup"><span data-stu-id="bb16f-281">Retention tag</span></span> | <span data-ttu-id="bb16f-282">此标记有什么功能</span><span class="sxs-lookup"><span data-stu-id="bb16f-282">What this tag does</span></span> | <span data-ttu-id="bb16f-283">内置还是自定义？</span><span class="sxs-lookup"><span data-stu-id="bb16f-283">Built-in or custom?</span></span> | <span data-ttu-id="bb16f-284">类型</span><span class="sxs-lookup"><span data-stu-id="bb16f-284">Type</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bb16f-285">大本市 3 年移动到存档</span><span class="sxs-lookup"><span data-stu-id="bb16f-285">Alpine House 3 Year Move to Archive</span></span>  <br/> |<span data-ttu-id="bb16f-286">将 1095 天 (3 年的项目) 存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-286">Moves items that are 1095 days (3 years) old to the archive mailbox.</span></span>  <br/> |<span data-ttu-id="bb16f-287">自定义 (步骤 [2：为](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies) 存档和删除策略创建新的保留标记) </span><span class="sxs-lookup"><span data-stu-id="bb16f-287">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="bb16f-288">默认策略标记 (存档) ;此标记将自动应用于整个邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-288">Default Policy Tag (archive); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="bb16f-289">大人 7 年永久删除</span><span class="sxs-lookup"><span data-stu-id="bb16f-289">Alpine House 7 Year Permanently Delete</span></span>  <br/> |<span data-ttu-id="bb16f-290">7 年后永久删除主邮箱或存档邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-290">Permanently deletes items in the primary mailbox or the archive mailbox when they are 7 years old.</span></span>  <br/> |<span data-ttu-id="bb16f-291">自定义 (步骤 [2：为](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies) 存档和删除策略创建新的保留标记) </span><span class="sxs-lookup"><span data-stu-id="bb16f-291">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="bb16f-292">默认策略标记 (删除) ;此标记将自动应用于整个邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-292">Default Policy Tag (deletion); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="bb16f-293">大人删除项目 5 年删除并允许恢复</span><span class="sxs-lookup"><span data-stu-id="bb16f-293">Alpine House Deleted Items 5 Years Delete and Allow Recovery</span></span>  <br/> |<span data-ttu-id="bb16f-294">从"已删除邮件"文件夹中删除 5 年的项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-294">Deletes items from the Deleted Items folder that are 5 years old.</span></span> <span data-ttu-id="bb16f-295">用户可以在删除后最多 14 天内恢复这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb16f-295">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="bb16f-296">自定义 (步骤 [2：为](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies) 存档和删除策略创建新的保留标记) </span><span class="sxs-lookup"><span data-stu-id="bb16f-296">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="bb16f-297">保留策略标记 (已删除邮件) ;此标记将自动应用于"已删除邮件"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-297">Retention Policy Tag (Deleted Items); this tag is automatically applied to items in the Deleted items folder.</span></span>  <br/> |
    |<span data-ttu-id="bb16f-298">可恢复项目 14 天移动到存档</span><span class="sxs-lookup"><span data-stu-id="bb16f-298">Recoverable Items 14 days Move to Archive</span></span>  <br/> |<span data-ttu-id="bb16f-299">将"可恢复的项目"文件夹中 14 天的项目移动到存档邮箱中的"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="bb16f-299">Moves items that have been in the Recoverable Items folder for 14 days to the Recoverable Items folder in the archive mailbox.</span></span>  <br/> |<span data-ttu-id="bb16f-300">内置</span><span class="sxs-lookup"><span data-stu-id="bb16f-300">Built-in</span></span>  <br/> |<span data-ttu-id="bb16f-301">保留策略标记 (可恢复项目) ;此标记将自动应用于"可恢复的项目"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-301">Retention Policy Tag (Recoverable Items); this tag is automatically applied to items in the Recoverable Items folder.</span></span>  <br/> |
    |<span data-ttu-id="bb16f-302">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="bb16f-302">Junk Email</span></span>  <br/> |<span data-ttu-id="bb16f-303">永久删除"垃圾邮件"文件夹中已保留 30 天的项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-303">Permanently deletes items that have been in the Junk Email folder for 30 days.</span></span> <span data-ttu-id="bb16f-304">用户可以在删除后最多 14 天内恢复这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb16f-304">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="bb16f-305">内置</span><span class="sxs-lookup"><span data-stu-id="bb16f-305">Built-in</span></span>  <br/> |<span data-ttu-id="bb16f-306">保留策略标记 (垃圾邮件) ;此标记将自动应用于"垃圾邮件"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-306">Retention Policy Tag (Junk Email); this tag is automatically applied to items in Junk Email folder.</span></span>  <br/> |
    |<span data-ttu-id="bb16f-307">1 个月后删除</span><span class="sxs-lookup"><span data-stu-id="bb16f-307">1 Month Delete</span></span>  <br/> |<span data-ttu-id="bb16f-308">永久删除 30 天的项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-308">Permanently deletes items that are 30 days old.</span></span> <span data-ttu-id="bb16f-309">用户可以在删除后最多 14 天内恢复这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb16f-309">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="bb16f-310">内置</span><span class="sxs-lookup"><span data-stu-id="bb16f-310">Built-in</span></span>  <br/> |<span data-ttu-id="bb16f-311">个人;用户可以应用此标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-311">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="bb16f-312">1 年后删除</span><span class="sxs-lookup"><span data-stu-id="bb16f-312">1 Year Delete</span></span>  <br/> |<span data-ttu-id="bb16f-313">永久删除 365 天的项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-313">Permanently deletes items that are 365 days old.</span></span> <span data-ttu-id="bb16f-314">用户可以在删除后最多 14 天内恢复这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb16f-314">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="bb16f-315">内置</span><span class="sxs-lookup"><span data-stu-id="bb16f-315">Built-in</span></span>  <br/> |<span data-ttu-id="bb16f-316">个人;用户可以应用此标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-316">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="bb16f-317">从不删除</span><span class="sxs-lookup"><span data-stu-id="bb16f-317">Never Delete</span></span>  <br/> |<span data-ttu-id="bb16f-318">此标记可防止保留策略删除项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-318">This tag prevents items from being deleted by a retention policy.</span></span>  <br/> |<span data-ttu-id="bb16f-319">内置</span><span class="sxs-lookup"><span data-stu-id="bb16f-319">Built-in</span></span>  <br/> |<span data-ttu-id="bb16f-320">个人;用户可以应用此标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-320">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="bb16f-321">个人 1 年后移动到存档</span><span class="sxs-lookup"><span data-stu-id="bb16f-321">Personal 1 year move to archive</span></span>  <br/> |<span data-ttu-id="bb16f-322">在 1 年后将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-322">Moves items to the archive mailbox after 1 year.</span></span>  <br/> |<span data-ttu-id="bb16f-323">内置</span><span class="sxs-lookup"><span data-stu-id="bb16f-323">Built-in</span></span>  <br/> |<span data-ttu-id="bb16f-324">个人;用户可以应用此标记。</span><span class="sxs-lookup"><span data-stu-id="bb16f-324">Personal; this tag can be applied by users.</span></span>  <br/> |

    > <span data-ttu-id="bb16f-325"><sup>\*</sup> 用户可以使用 Outlook 和 Web 上的 Outlook 中的"恢复已删除邮件"工具 (以前称为 Outlook Web App) 在已删除项目的保留期（默认情况下为 Exchange Online 中的 14 天）中恢复已删除项目。</span><span class="sxs-lookup"><span data-stu-id="bb16f-325"><sup>\*</sup> Users can use the Recover Deleted Items tool in Outlook and Outlook on the web (formerly known as Outlook Web App) to recover a deleted item within the deleted item retention period, which by default is 14 days in Exchange Online.</span></span> <span data-ttu-id="bb16f-326">管理员可以使用Windows PowerShell将已删除项目的保留期增加至最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="bb16f-326">An administrator can use Windows PowerShell to increase the deleted item retention period to a maximum of 30 days.</span></span> <span data-ttu-id="bb16f-327">有关详细信息，请参阅：恢复 [Outlook for Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) 中的已删除项目，并更改 Exchange Online 中邮箱的已删除邮件 [保留期](https://www.microsoft.com/?ref=go)</span><span class="sxs-lookup"><span data-stu-id="bb16f-327">For more information, see: [Recover deleted items in Outlook for Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) and [Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go)</span></span>
  
- <span data-ttu-id="bb16f-328">使用 **"可恢复的项目 14 天** 移动到存档"保留标记有助于释放用户主邮箱中"可恢复的项目"文件夹中的存储空间。</span><span class="sxs-lookup"><span data-stu-id="bb16f-328">Using the **Recoverable Items 14 days Move to Archive** retention tag helps free up storage space in the Recoverable Items folder in the user's primary mailbox.</span></span> <span data-ttu-id="bb16f-329">当用户的邮箱处于保留状态时，这非常有用，这意味着不会永久删除用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="bb16f-329">This is useful when a user's mailbox is placed on hold, which means nothing is ever permanently deleted the user's mailbox.</span></span> <span data-ttu-id="bb16f-330">如果不将项目移动到存档邮箱，则可能会达到主邮箱中"可恢复的项目"文件夹的存储配额。</span><span class="sxs-lookup"><span data-stu-id="bb16f-330">Without moving items to the archive mailbox, it's possible the storage quota for the Recoverable Items folder in the primary mailbox will be reached.</span></span> <span data-ttu-id="bb16f-331">有关此情况以及如何避免它，请参阅增加保留邮箱的"可恢复的项目" [配额](https://go.microsoft.com/fwlink/p/?LinkId=786479)。</span><span class="sxs-lookup"><span data-stu-id="bb16f-331">For more information about this and how to avoid it, see [Increase the Recoverable Items quota for mailboxes on hold](https://go.microsoft.com/fwlink/p/?LinkId=786479).</span></span>
