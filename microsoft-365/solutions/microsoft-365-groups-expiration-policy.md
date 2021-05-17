---
title: Microsoft 365组过期策略
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
description: 了解Microsoft 365组过期策略。
ms.openlocfilehash: fdef06918ec2c35547c084e5f431aa7bef8d6a8c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587619"
---
# <a name="microsoft-365-group-expiration-policy"></a><span data-ttu-id="1bf14-103">Microsoft 365组过期策略</span><span class="sxs-lookup"><span data-stu-id="1bf14-103">Microsoft 365 group expiration policy</span></span>

<span data-ttu-id="1bf14-104">随着组和Microsoft 365的使用Microsoft Teams，管理员和用户需要一种方法来清理未使用的组和团队。</span><span class="sxs-lookup"><span data-stu-id="1bf14-104">With the increase in usage of Microsoft 365 groups and Microsoft Teams, administrators and users need a way to clean up unused groups and teams.</span></span> <span data-ttu-id="1bf14-105">一Microsoft 365组过期策略可帮助从系统中删除非活动组，使情况更简洁。</span><span class="sxs-lookup"><span data-stu-id="1bf14-105">A Microsoft 365 groups expiration policy can help remove inactive groups from the system and make things cleaner.</span></span>

<span data-ttu-id="1bf14-106">当组过期时，还将删除 (、Planner、SharePoint网站、团队等) 服务。</span><span class="sxs-lookup"><span data-stu-id="1bf14-106">When a group expires, all of its associated services (the mailbox, Planner, SharePoint site, team, etc.) are also deleted.</span></span>

<span data-ttu-id="1bf14-107">当组过期时，它将"软删除"，这意味着它仍然可以恢复最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="1bf14-107">When a group expires it is "soft-deleted" which means it can still be recovered for up to 30 days.</span></span>

<span data-ttu-id="1bf14-108">管理员可以指定过期期限，达到该期限末尾且未续订的任何非活动组都将被删除。</span><span class="sxs-lookup"><span data-stu-id="1bf14-108">Administrators can specify an expiration period and any inactive group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="1bf14-109"> (包括存档的 teams.) 到期日期从组创建时开始，或自上次续订日期开始。</span><span class="sxs-lookup"><span data-stu-id="1bf14-109">(This includes archived teams.) The expiration period begins when the group is created, or on the date it was last renewed.</span></span> <span data-ttu-id="1bf14-110">组所有者将在过期前自动收到一封电子邮件，允许他们续订组的另一个过期间隔。</span><span class="sxs-lookup"><span data-stu-id="1bf14-110">Group owners will automatically be sent an email before the expiration that allows them to renew the group for another expiration interval.</span></span> <span data-ttu-id="1bf14-111">Teams用户将在网站中看到永久性Teams。</span><span class="sxs-lookup"><span data-stu-id="1bf14-111">Teams users will see persistent notifications in Teams.</span></span>

<span data-ttu-id="1bf14-112">主动使用的组将自动续订。</span><span class="sxs-lookup"><span data-stu-id="1bf14-112">Groups that are actively in use are renewed automatically.</span></span> <span data-ttu-id="1bf14-113">以下任一操作将自动续订组：</span><span class="sxs-lookup"><span data-stu-id="1bf14-113">Any of the following actions will auto-renew a group:</span></span>
- <span data-ttu-id="1bf14-114">SharePoint - 查看、编辑、下载、移动、共享或上载文件。</span><span class="sxs-lookup"><span data-stu-id="1bf14-114">SharePoint - view, edit, download, move, share, or upload files.</span></span> <span data-ttu-id="1bf14-115"> (查看SharePoint页面不作为自动续订的操作。) </span><span class="sxs-lookup"><span data-stu-id="1bf14-115">(Viewing a SharePoint page does not count as an action for automatic renewal.)</span></span>
- <span data-ttu-id="1bf14-116">Outlook - 加入组、从组读取或写入组消息， (Outlook Web 上的) 。</span><span class="sxs-lookup"><span data-stu-id="1bf14-116">Outlook - join group, read or write group message from the group, and like a message (Outlook on the web).</span></span>
- <span data-ttu-id="1bf14-117">Teams - 访问团队频道。</span><span class="sxs-lookup"><span data-stu-id="1bf14-117">Teams - visiting a teams channel.</span></span>

<span data-ttu-id="1bf14-118">请注意，唯一Yammer触发自动组续订的活动是将文档上载到SharePoint社区内。</span><span class="sxs-lookup"><span data-stu-id="1bf14-118">Note that the only Yammer activity which will trigger an automatic group renewal is the upload of a document to SharePoint within the community.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bf14-119">更改过期策略时，该服务将重新计算每个组的到期日期。</span><span class="sxs-lookup"><span data-stu-id="1bf14-119">When you change the expiration policy, the service recalculates the expiration date for each group.</span></span> <span data-ttu-id="1bf14-120">它始终从组创建日期开始计数，然后应用新的过期策略。</span><span class="sxs-lookup"><span data-stu-id="1bf14-120">It always starts counting from the date when the group was created, and then applies the new expiration policy.</span></span>

<span data-ttu-id="1bf14-121">了解默认情况下关闭过期很重要。</span><span class="sxs-lookup"><span data-stu-id="1bf14-121">It's important to know that expiration is turned off by default.</span></span> <span data-ttu-id="1bf14-122">如果想使用，管理员必须针对其组织启用它。</span><span class="sxs-lookup"><span data-stu-id="1bf14-122">Administrators have to enable it for their organization if they want to use it.</span></span>

> [!NOTE]
> <span data-ttu-id="1bf14-123">配置和使用 Microsoft 365 组的过期策略需要你拥有（但不一定）为应用过期策略的所有组的成员分配 Azure AD 高级版 许可证。</span><span class="sxs-lookup"><span data-stu-id="1bf14-123">Configuring and using the expiration policy for Microsoft 365 groups requires you to possess but not necessarily assign Azure AD Premium licenses for the members of all groups to which the expiration policy is applied.</span></span> <span data-ttu-id="1bf14-124">有关详细信息，请参阅[入门Azure Active Directory 高级版。](/azure/active-directory/active-directory-get-started-premium)</span><span class="sxs-lookup"><span data-stu-id="1bf14-124">For more information see [Getting started with Azure Active Directory Premium](/azure/active-directory/active-directory-get-started-premium).</span></span>

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a><span data-ttu-id="1bf14-125">Who配置和使用组Microsoft 365策略？</span><span class="sxs-lookup"><span data-stu-id="1bf14-125">Who can configure and use the Microsoft 365 groups expiration policy?</span></span>

|<span data-ttu-id="1bf14-126">角色</span><span class="sxs-lookup"><span data-stu-id="1bf14-126">Role</span></span>|<span data-ttu-id="1bf14-127">他们可以执行哪些功能</span><span class="sxs-lookup"><span data-stu-id="1bf14-127">What they can do</span></span>|
|---------|---------|
|<span data-ttu-id="1bf14-128">Office 365 Azure (全局管理员，公司管理员) 用户管理员</span><span class="sxs-lookup"><span data-stu-id="1bf14-128">Office 365 global admin (in Azure, the Company administrator), User administrator</span></span>|<span data-ttu-id="1bf14-129">创建、读取、更新或删除Microsoft 365组过期策略设置。</span><span class="sxs-lookup"><span data-stu-id="1bf14-129">Create, read, update, or delete the Microsoft 365 groups expiration policy settings.</span></span>|
|<span data-ttu-id="1bf14-130">用户</span><span class="sxs-lookup"><span data-stu-id="1bf14-130">User</span></span>|<span data-ttu-id="1bf14-131">续订[或还原](/azure/active-directory/users-groups-roles/groups-restore-deleted)Microsoft 365他们拥有的任何组</span><span class="sxs-lookup"><span data-stu-id="1bf14-131">Renew or [restore](/azure/active-directory/users-groups-roles/groups-restore-deleted) a Microsoft 365 group that they own</span></span>|

## <a name="how-to-set-the-expiration-policy"></a><span data-ttu-id="1bf14-132">如何设置过期策略</span><span class="sxs-lookup"><span data-stu-id="1bf14-132">How to set the expiration policy</span></span>

<span data-ttu-id="1bf14-133">如上所述，过期默认为关闭状态。</span><span class="sxs-lookup"><span data-stu-id="1bf14-133">As noted above, expiry is turned off by default.</span></span> <span data-ttu-id="1bf14-134">管理员必须启用过期策略并设置其属性才能生效。</span><span class="sxs-lookup"><span data-stu-id="1bf14-134">An administrator will have to enable the expiration policy and set the properties for it to take effect.</span></span> <span data-ttu-id="1bf14-135">若要启用它，**请转到"Azure Active Directory**  >  **组**  >  **过期"。**</span><span class="sxs-lookup"><span data-stu-id="1bf14-135">To enable it, go to **Azure Active Directory** > **Groups** > **Expiration**.</span></span> <span data-ttu-id="1bf14-136">你可以在此处设置默认组生存期，并指定希望第一个和第二个过期通知提前多远转到组所有者。</span><span class="sxs-lookup"><span data-stu-id="1bf14-136">Here you can set the default group lifetime and specify how far in advance you want the first and second expiration notifications to go to the group owner.</span></span>

<span data-ttu-id="1bf14-137">组生存期以天指定，可以设置为 180，365 或您指定的自定义值。</span><span class="sxs-lookup"><span data-stu-id="1bf14-137">The group lifetime is specified in days and can be set to 180, 365 or to a custom value that you specify.</span></span> <span data-ttu-id="1bf14-138">自定义值必须至少为 30 天。</span><span class="sxs-lookup"><span data-stu-id="1bf14-138">The custom value has to be at least 30 days.</span></span>

<span data-ttu-id="1bf14-139">如果组没有所有者，过期电子邮件将转到指定的管理员。</span><span class="sxs-lookup"><span data-stu-id="1bf14-139">If the group does not have an owner, the expiration emails will go to the specified administrator.</span></span>

<span data-ttu-id="1bf14-140">你可以为所有组设置策略，仅选定组 (最多 500) ，或者选择"无"将其完全 **关闭**。</span><span class="sxs-lookup"><span data-stu-id="1bf14-140">You can set the policy for all of your groups, only selected groups (up to 500), or turn it off completely by selecting **None**.</span></span> <span data-ttu-id="1bf14-141">请注意，目前不能为不同的组设置不同的策略。</span><span class="sxs-lookup"><span data-stu-id="1bf14-141">Note that currently you can't have different policies for different groups.</span></span>

![Screenshot of Groups expiration settings in Azure Active Directory](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a><span data-ttu-id="1bf14-143">到期日期如何与保留策略一起运行</span><span class="sxs-lookup"><span data-stu-id="1bf14-143">How expiry works with the retention policy</span></span>

<span data-ttu-id="1bf14-144">如果在安全与合规中心为组设置了保留策略，则过期策略可与保留策略无缝协作。</span><span class="sxs-lookup"><span data-stu-id="1bf14-144">If you have set up a retention policy for groups in the Security and Compliance center, the expiration policy works seamlessly with retention policy.</span></span> <span data-ttu-id="1bf14-145">当组过期时，该组的邮箱对话和组网站中的文件将在保留策略中定义的特定天数内保留在保留容器中。</span><span class="sxs-lookup"><span data-stu-id="1bf14-145">When a group expires, the group's mailbox conversations and files in the group site are retained in the retention container for the specific number of days defined in the retention policy.</span></span> <span data-ttu-id="1bf14-146">但是，在过期后，用户将不会看到组或其内容。</span><span class="sxs-lookup"><span data-stu-id="1bf14-146">Users will not see the group, or its content, after expiration however.</span></span>

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a><span data-ttu-id="1bf14-147">组所有者如何以及何时了解其组是否即将过期</span><span class="sxs-lookup"><span data-stu-id="1bf14-147">How and when a group owner learns if their groups are going to expire</span></span>

<span data-ttu-id="1bf14-148">组所有者将仅通过电子邮件收到通知。</span><span class="sxs-lookup"><span data-stu-id="1bf14-148">Group owners will only be notified via email.</span></span> <span data-ttu-id="1bf14-149">如果组是通过 Planner、SharePoint或任何其他应用创建的，过期通知将始终通过电子邮件发送。</span><span class="sxs-lookup"><span data-stu-id="1bf14-149">If the group was created via Planner, SharePoint, or any other app, the expiration notifications will always come via email.</span></span> <span data-ttu-id="1bf14-150">如果组是通过 Teams创建的，组所有者将收到通过活动部分续订的通知。</span><span class="sxs-lookup"><span data-stu-id="1bf14-150">If the group was created via Teams, the group owner will receive a notification to renew through the activity section.</span></span> <span data-ttu-id="1bf14-151">如果你的组所有者没有有效的电子邮件地址，建议不要对组启用过期。</span><span class="sxs-lookup"><span data-stu-id="1bf14-151">It's not recommended that you enable expiration on a group if your group owner doesn't have a valid email address.</span></span>

<span data-ttu-id="1bf14-152">在组过期前 30 天， (或你为没有所有者) 的组指定的电子邮件地址将收到一封电子邮件，允许他们轻松续订组。</span><span class="sxs-lookup"><span data-stu-id="1bf14-152">Thirty days before the group expires, the group owners (or the email addresses that you specified for groups that don't have an owner) will receive an email allowing them to easily renew the group.</span></span> <span data-ttu-id="1bf14-153">如果他们没有续订，将在过期前 15 天收到另一封续订电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf14-153">If they don't renew it, they'll receive another renewal email 15 days before expiration.</span></span> <span data-ttu-id="1bf14-154">如果他们仍未续订，将在过期前一天收到一封多封电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="1bf14-154">If they still haven't renewed it, they will receive one more email notification the day before expiration.</span></span>

<span data-ttu-id="1bf14-155">如果出于某种原因，没有任何所有者或管理员在组过期前续订组，则管理员仍然可以在过期后最多 30 天内还原组。</span><span class="sxs-lookup"><span data-stu-id="1bf14-155">If for some reason none of the owners or admins renew the group before it expires, the admin can still restore the group for up to 30 days after expiration.</span></span> <span data-ttu-id="1bf14-156">有关详细信息，请参阅[：Restore a deleted Microsoft 365 group](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).</span><span class="sxs-lookup"><span data-stu-id="1bf14-156">For details see: [Restore a deleted Microsoft 365 group](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).</span></span>

## <a name="archiving-group-contents"></a><span data-ttu-id="1bf14-157">存档组内容</span><span class="sxs-lookup"><span data-stu-id="1bf14-157">Archiving group contents</span></span>

<span data-ttu-id="1bf14-158">如果您有一个不再计划使用的组，但希望保留其内容，请参阅存档组、团队[和](end-life-cycle-groups-teams-sites-yammer.md)Yammer，了解如何从不同的组服务导出信息。</span><span class="sxs-lookup"><span data-stu-id="1bf14-158">If you have a group that you no longer plan to use, but you want to retain its content, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information about how to export information from the different groups services.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1bf14-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="1bf14-159">Related topics</span></span>

[<span data-ttu-id="1bf14-160">协作治理规划分步规划</span><span class="sxs-lookup"><span data-stu-id="1bf14-160">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="1bf14-161">创建协作管理计划</span><span class="sxs-lookup"><span data-stu-id="1bf14-161">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="1bf14-162">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="1bf14-162">Overview of retention policies</span></span>](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[<span data-ttu-id="1bf14-163">向孤立组分配新的所有者</span><span class="sxs-lookup"><span data-stu-id="1bf14-163">Assign a new owner to an orphaned group</span></span>](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[<span data-ttu-id="1bf14-164">配置Microsoft 365组过期</span><span class="sxs-lookup"><span data-stu-id="1bf14-164">Configure Microsoft 365 groups expiration</span></span>](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
