---
title: Microsoft 365 组过期策略
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
description: 了解 Microsoft 365 组过期策略。
ms.openlocfilehash: 4b283bcc9f4e54462a71b9aee70d6312b9f127d6
ms.sourcegitcommit: 5480982967a90ca3060a59676a6b29155f2de861
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49350708"
---
# <a name="microsoft-365-group-expiration-policy"></a><span data-ttu-id="970bd-103">Microsoft 365 组过期策略</span><span class="sxs-lookup"><span data-stu-id="970bd-103">Microsoft 365 group expiration policy</span></span>

<span data-ttu-id="970bd-104">随着 Microsoft 365 组和 Microsoft 团队的使用提高，管理员和用户需要一种方法来清除未使用的组和团队。</span><span class="sxs-lookup"><span data-stu-id="970bd-104">With the increase in usage of Microsoft 365 groups and Microsoft Teams, administrators and users need a way to clean up unused groups and teams.</span></span> <span data-ttu-id="970bd-105">Microsoft 365 组过期策略可帮助从系统中删除非活动组并使其更整洁。</span><span class="sxs-lookup"><span data-stu-id="970bd-105">A Microsoft 365 groups expiration policy can help remove inactive groups from the system and make things cleaner.</span></span>

<span data-ttu-id="970bd-106">当某个组过期时，其关联的所有服务 (邮箱、Planner、SharePoint 网站、团队等 ) 也将被删除。</span><span class="sxs-lookup"><span data-stu-id="970bd-106">When a group expires, all of its associated services (the mailbox, Planner, SharePoint site, team, etc.) are also deleted.</span></span>

<span data-ttu-id="970bd-107">当组过期时，它会被 "软删除"，这意味着它仍可恢复最长30天。</span><span class="sxs-lookup"><span data-stu-id="970bd-107">When a group expires it is "soft-deleted" which means it can still be recovered for up to 30 days.</span></span>

<span data-ttu-id="970bd-108">管理员可以指定过期时间和任何非活动组，达到该时间段结束时间后，不会被更新。</span><span class="sxs-lookup"><span data-stu-id="970bd-108">Administrators can specify an expiration period and any inactive group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="970bd-109"> (这包括存档的团队。 ) 过期期在创建组时或在上次续订日期时开始。</span><span class="sxs-lookup"><span data-stu-id="970bd-109">(This includes archived teams.) The expiration period begins when the group is created, or on the date it was last renewed.</span></span> <span data-ttu-id="970bd-110">在过期之前，将自动向组所有者发送一封电子邮件，以允许他们为其他过期间隔续订组。</span><span class="sxs-lookup"><span data-stu-id="970bd-110">Group owners will automatically be sent an email before the expiration that allows them to renew the group for another expiration interval.</span></span> <span data-ttu-id="970bd-111">团队用户将在团队中看到永久通知。</span><span class="sxs-lookup"><span data-stu-id="970bd-111">Teams users will see persistent notifications in Teams.</span></span>

<span data-ttu-id="970bd-112">正在使用的组将自动续订。</span><span class="sxs-lookup"><span data-stu-id="970bd-112">Groups that are actively in use are renewed automatically.</span></span> <span data-ttu-id="970bd-113">以下任一操作将自动续订组：</span><span class="sxs-lookup"><span data-stu-id="970bd-113">Any of the following actions will auto-renew a group:</span></span>
- <span data-ttu-id="970bd-114">SharePoint-查看、编辑、下载、移动、共享或上传文件。</span><span class="sxs-lookup"><span data-stu-id="970bd-114">SharePoint - view, edit, download, move, share, or upload files.</span></span> <span data-ttu-id="970bd-115"> (查看 SharePoint 页面不计为自动续订的操作。 ) </span><span class="sxs-lookup"><span data-stu-id="970bd-115">(Viewing a SharePoint page does not count as an action for automatic renewal.)</span></span>
- <span data-ttu-id="970bd-116">Outlook-加入组，从组中读取或写入组邮件，与 (Outlook 网页) 上的邮件类似。</span><span class="sxs-lookup"><span data-stu-id="970bd-116">Outlook - join group, read or write group message from the group, and like a message (Outlook on the web).</span></span>
- <span data-ttu-id="970bd-117">团队-访问团队频道。</span><span class="sxs-lookup"><span data-stu-id="970bd-117">Teams - visiting a teams channel.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="970bd-118">当您更改过期策略时，服务将重新计算每个组的到期日期。</span><span class="sxs-lookup"><span data-stu-id="970bd-118">When you change the expiration policy, the service recalculates the expiration date for each group.</span></span> <span data-ttu-id="970bd-119">它始终从创建组的日期开始计数，然后应用新的过期策略。</span><span class="sxs-lookup"><span data-stu-id="970bd-119">It always starts counting from the date when the group was created, and then applies the new expiration policy.</span></span>

<span data-ttu-id="970bd-120">请务必了解默认情况下禁用过期功能。</span><span class="sxs-lookup"><span data-stu-id="970bd-120">It's important to know that expiration is turned off by default.</span></span> <span data-ttu-id="970bd-121">管理员必须为其组织启用此策略，如果他们想要使用它。</span><span class="sxs-lookup"><span data-stu-id="970bd-121">Administrators have to enable it for their organization if they want to use it.</span></span>

> [!NOTE]
> <span data-ttu-id="970bd-122">配置和使用适用于 Microsoft 365 组的过期策略要求您拥有（但不一定）为应用过期策略的所有组的成员分配 Azure AD Premium 许可证。</span><span class="sxs-lookup"><span data-stu-id="970bd-122">Configuring and using the expiration policy for Microsoft 365 groups requires you to possess but not necessarily assign Azure AD Premium licenses for the members of all groups to which the expiration policy is applied.</span></span> <span data-ttu-id="970bd-123">有关详细信息，请参阅 [Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)入门。</span><span class="sxs-lookup"><span data-stu-id="970bd-123">For more information see [Getting started with Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).</span></span>

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a><span data-ttu-id="970bd-124">哪些用户可以配置和使用 Microsoft 365 组过期策略？</span><span class="sxs-lookup"><span data-stu-id="970bd-124">Who can configure and use the Microsoft 365 groups expiration policy?</span></span>

|<span data-ttu-id="970bd-125">Role</span><span class="sxs-lookup"><span data-stu-id="970bd-125">Role</span></span>|<span data-ttu-id="970bd-126">可以执行的操作</span><span class="sxs-lookup"><span data-stu-id="970bd-126">What they can do</span></span>|
|---------|---------|
|<span data-ttu-id="970bd-127">Office 365 全局管理员 (在 Azure 中，公司管理员) ，用户管理员</span><span class="sxs-lookup"><span data-stu-id="970bd-127">Office 365 global admin (in Azure, the Company administrator), User administrator</span></span>|<span data-ttu-id="970bd-128">创建、读取、更新或删除 Microsoft 365 组过期策略设置。</span><span class="sxs-lookup"><span data-stu-id="970bd-128">Create, read, update, or delete the Microsoft 365 groups expiration policy settings.</span></span>|
|<span data-ttu-id="970bd-129">User</span><span class="sxs-lookup"><span data-stu-id="970bd-129">User</span></span>|<span data-ttu-id="970bd-130">续订或 [还原](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) 自己拥有的 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="970bd-130">Renew or [restore](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) a Microsoft 365 group that they own</span></span>|

## <a name="how-to-set-the-expiration-policy"></a><span data-ttu-id="970bd-131">如何设置过期策略</span><span class="sxs-lookup"><span data-stu-id="970bd-131">How to set the expiration policy</span></span>

<span data-ttu-id="970bd-132">如上所述，默认情况下过期功能处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="970bd-132">As noted above, expiry is turned off by default.</span></span> <span data-ttu-id="970bd-133">管理员必须启用过期策略并将其属性设置为生效。</span><span class="sxs-lookup"><span data-stu-id="970bd-133">An administrator will have to enable the expiration policy and set the properties for it to take effect.</span></span> <span data-ttu-id="970bd-134">若要启用它，请转到 **Azure Active Directory**  >  **组**  >  **过期**。</span><span class="sxs-lookup"><span data-stu-id="970bd-134">To enable it, go to **Azure Active Directory** > **Groups** > **Expiration**.</span></span> <span data-ttu-id="970bd-135">你可以在此处设置默认组生存期，并指定你希望第一个和第二个过期通知转到组所有者的提前程度。</span><span class="sxs-lookup"><span data-stu-id="970bd-135">Here you can set the default group lifetime and specify how far in advance you want the first and second expiration notifications to go to the group owner.</span></span>

<span data-ttu-id="970bd-136">组生存期以天为单位指定，可设置为180、365或指定的自定义值。</span><span class="sxs-lookup"><span data-stu-id="970bd-136">The group lifetime is specified in days and can be set to 180, 365 or to a custom value that you specify.</span></span> <span data-ttu-id="970bd-137">自定义值必须至少为30天。</span><span class="sxs-lookup"><span data-stu-id="970bd-137">The custom value has to be at least 30 days.</span></span>

<span data-ttu-id="970bd-138">如果组没有所有者，到期电子邮件将转到指定的管理员。</span><span class="sxs-lookup"><span data-stu-id="970bd-138">If the group does not have an owner, the expiration emails will go to the specified administrator.</span></span>

<span data-ttu-id="970bd-139">您可以设置所有组的策略、仅选定的组或通过选择 " **无**" 将其完全关闭。</span><span class="sxs-lookup"><span data-stu-id="970bd-139">You can set the policy for all of your groups, only selected groups, or turn it off completely by selecting **None**.</span></span> <span data-ttu-id="970bd-140">请注意，对于不同的组，当前不能有不同的策略。</span><span class="sxs-lookup"><span data-stu-id="970bd-140">Note that currently you can't have different policies for different groups.</span></span>

![Azure Active Directory 中的组过期设置的屏幕截图](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a><span data-ttu-id="970bd-142">到期日期如何与保留策略一起使用</span><span class="sxs-lookup"><span data-stu-id="970bd-142">How expiry works with the retention policy</span></span>

<span data-ttu-id="970bd-143">如果已为安全与合规中心中的组设置保留策略，则过期策略将与保留策略无缝运行。</span><span class="sxs-lookup"><span data-stu-id="970bd-143">If you have set up a retention policy for groups in the Security and Compliance center, the expiration policy works seamlessly with retention policy.</span></span> <span data-ttu-id="970bd-144">当组过期时，组中的邮箱对话和组网站中的文件将保留在保留策略中定义的特定天数的保留容器中。</span><span class="sxs-lookup"><span data-stu-id="970bd-144">When a group expires, the group's mailbox conversations and files in the group site are retained in the retention container for the specific number of days defined in the retention policy.</span></span> <span data-ttu-id="970bd-145">但是，用户在过期后将看不到该组或其内容。</span><span class="sxs-lookup"><span data-stu-id="970bd-145">Users will not see the group, or its content, after expiration however.</span></span>

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a><span data-ttu-id="970bd-146">组所有者在其组过期时的学习方式和时间</span><span class="sxs-lookup"><span data-stu-id="970bd-146">How and when a group owner learns if their groups are going to expire</span></span>

<span data-ttu-id="970bd-147">组所有者将仅通过电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="970bd-147">Group owners will only be notified via email.</span></span> <span data-ttu-id="970bd-148">如果组是通过计划者、SharePoint 或任何其他应用程序创建的，则到期通知将始终通过电子邮件发送。</span><span class="sxs-lookup"><span data-stu-id="970bd-148">If the group was created via Planner, SharePoint, or any other app, the expiration notifications will always come via email.</span></span> <span data-ttu-id="970bd-149">如果组是通过团队创建的，则组所有者将通过 "活动" 部分收到要续订的通知。</span><span class="sxs-lookup"><span data-stu-id="970bd-149">If the group was created via Teams, the group owner will receive a notification to renew through the activity section.</span></span> <span data-ttu-id="970bd-150">如果您的组所有者没有有效的电子邮件地址，则建议您在组中启用过期。</span><span class="sxs-lookup"><span data-stu-id="970bd-150">It's not recommended that you enable expiration on a group if your group owner doesn't have a valid email address.</span></span>

<span data-ttu-id="970bd-151">组过期前三十天，组所有者 (或为没有所有者) 的组指定的电子邮件地址将会收到一封电子邮件，使用户可以轻松地续订该组。</span><span class="sxs-lookup"><span data-stu-id="970bd-151">Thirty days before the group expires, the group owners (or the email addresses that you specified for groups that don't have an owner) will receive an email allowing them to easily renew the group.</span></span> <span data-ttu-id="970bd-152">如果不续订，他们将在到期前15天收到另一封续订电子邮件。</span><span class="sxs-lookup"><span data-stu-id="970bd-152">If they don't renew it, they'll receive another renewal email 15 days before expiration.</span></span> <span data-ttu-id="970bd-153">如果他们仍未续订，则会在过期前一天收到一封电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="970bd-153">If they still haven't renewed it, they will receive one more email notification the day before expiration.</span></span>

<span data-ttu-id="970bd-154">如果由于某种原因，所有者或管理员在过期之前没有对组进行续订，则管理员仍可以在到期后的30天内还原组。</span><span class="sxs-lookup"><span data-stu-id="970bd-154">If for some reason none of the owners or admins renew the group before it expires, the admin can still restore the group for up to 30 days after expiration.</span></span> <span data-ttu-id="970bd-155">有关详细信息，请参阅： [还原已删除的 Microsoft 365 组](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)。</span><span class="sxs-lookup"><span data-stu-id="970bd-155">For details see: [Restore a deleted Microsoft 365 group](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).</span></span>

## <a name="archiving-group-contents"></a><span data-ttu-id="970bd-156">存档组内容</span><span class="sxs-lookup"><span data-stu-id="970bd-156">Archiving group contents</span></span>

<span data-ttu-id="970bd-157">如果您有一个您不再打算使用的组，但您希望保留其内容，请参阅 [存档组、团队和 Yammer](end-life-cycle-groups-teams-sites-yammer.md) ，了解有关如何从不同的组服务中导出信息的信息。</span><span class="sxs-lookup"><span data-stu-id="970bd-157">If you have a group that you no longer plan to use, but you want to retain its content, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information about how to export information from the different groups services.</span></span>

## <a name="related-articles"></a><span data-ttu-id="970bd-158">相关文章</span><span class="sxs-lookup"><span data-stu-id="970bd-158">Related articles</span></span>

[<span data-ttu-id="970bd-159">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="970bd-159">Overview of retention policies</span></span>](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[<span data-ttu-id="970bd-160">向孤立组分配新的所有者</span><span class="sxs-lookup"><span data-stu-id="970bd-160">Assign a new owner to an orphaned group</span></span>](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[<span data-ttu-id="970bd-161">配置 Microsoft 365 组过期</span><span class="sxs-lookup"><span data-stu-id="970bd-161">Configure Microsoft 365 groups expiration</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
