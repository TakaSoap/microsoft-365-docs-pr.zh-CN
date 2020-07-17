---
title: 组过期策略
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
description: 了解 Microsoft 365 组过期策略。
ms.openlocfilehash: 8def757241dec28f5a54c76dc81614fd52fe85e5
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780417"
---
# <a name="microsoft-365-group-expiration-policy"></a><span data-ttu-id="85b65-103">Microsoft 365 组过期策略</span><span class="sxs-lookup"><span data-stu-id="85b65-103">Microsoft 365 group expiration policy</span></span>

<span data-ttu-id="85b65-104">随着 Microsoft 365 组的使用提高，管理员和用户需要一种方法来清除未使用的组。</span><span class="sxs-lookup"><span data-stu-id="85b65-104">With the increase in usage of Microsoft 365 groups, administrators and users need a way to clean up unused groups.</span></span> <span data-ttu-id="85b65-105">过期策略可帮助从系统中删除非活动组并使其更整洁。</span><span class="sxs-lookup"><span data-stu-id="85b65-105">Expiration policies can help remove inactive groups from the system and make things cleaner.</span></span>

<span data-ttu-id="85b65-106">当组过期时，也将删除其所有关联的服务（邮箱、Planner、SharePoint 网站、团队等）。</span><span class="sxs-lookup"><span data-stu-id="85b65-106">When a group expires, all of its associated services (the mailbox, Planner, SharePoint site, team, etc.) are also deleted.</span></span>

<span data-ttu-id="85b65-107">当组过期时，它会被 "软删除"，这意味着它仍可恢复最长30天。</span><span class="sxs-lookup"><span data-stu-id="85b65-107">When a group expires it is "soft-deleted" which means it can still be recovered for up to 30 days.</span></span>

<span data-ttu-id="85b65-108">管理员可以指定过期时间和任何非活动组，达到该时间段结束时间后，不会被更新。</span><span class="sxs-lookup"><span data-stu-id="85b65-108">Administrators can specify an expiration period and any inactive group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="85b65-109">过期时间是在创建组时开始，或在上次续订日期时开始。</span><span class="sxs-lookup"><span data-stu-id="85b65-109">The expiration period begins when the group is created, or on the date it was last renewed.</span></span> <span data-ttu-id="85b65-110">在过期之前，将自动向组所有者发送一封电子邮件，以允许他们为其他过期间隔续订组。</span><span class="sxs-lookup"><span data-stu-id="85b65-110">Group owners will automatically be sent an email before the expiration that allows them to renew the group for another expiration interval.</span></span> <span data-ttu-id="85b65-111">团队用户将在团队中看到永久通知。</span><span class="sxs-lookup"><span data-stu-id="85b65-111">Teams users will see persistent notifications in Teams.</span></span>

<span data-ttu-id="85b65-112">正在使用的组将自动续订。</span><span class="sxs-lookup"><span data-stu-id="85b65-112">Groups that are actively in use are renewed automatically.</span></span> <span data-ttu-id="85b65-113">以下任一操作将自动续订组：</span><span class="sxs-lookup"><span data-stu-id="85b65-113">Any of the following actions will auto-renew a group:</span></span>
- <span data-ttu-id="85b65-114">SharePoint-查看、编辑、下载、移动、共享或上传文件。</span><span class="sxs-lookup"><span data-stu-id="85b65-114">SharePoint - view, edit, download, move, share, or upload files.</span></span>
- <span data-ttu-id="85b65-115">Outlook-加入组、读取或写入组中的组邮件，以及类似于邮件（Outlook 网页网站）。</span><span class="sxs-lookup"><span data-stu-id="85b65-115">Outlook - join group, read or write group message from the group, and like a message (Outlook on the web).</span></span>
- <span data-ttu-id="85b65-116">团队-访问团队频道。</span><span class="sxs-lookup"><span data-stu-id="85b65-116">Teams - visiting a teams channel.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85b65-117">当您更改过期策略时，服务将重新计算每个组的到期日期。</span><span class="sxs-lookup"><span data-stu-id="85b65-117">When you change the expiration policy, the service recalculates the expiration date for each group.</span></span> <span data-ttu-id="85b65-118">它始终从创建组的日期开始计数，然后应用新的过期策略。</span><span class="sxs-lookup"><span data-stu-id="85b65-118">It always starts counting from the date when the group was created, and then applies the new expiration policy.</span></span>

<span data-ttu-id="85b65-119">请务必了解默认情况下禁用过期功能。</span><span class="sxs-lookup"><span data-stu-id="85b65-119">It's important to know that expiration is turned off by default.</span></span> <span data-ttu-id="85b65-120">如果管理员想要使用它，则必须为其组织启用它。</span><span class="sxs-lookup"><span data-stu-id="85b65-120">Administrators will have to enable it for their organization if they want to use it.</span></span>

> [!NOTE]
> <span data-ttu-id="85b65-121">配置和使用适用于 Microsoft 365 组的过期策略要求您拥有（但不一定）为应用过期策略的所有组的成员分配 Azure AD Premium 许可证。</span><span class="sxs-lookup"><span data-stu-id="85b65-121">Configuring and using the expiration policy for Microsoft 365 groups requires you to possess but not necessarily assign Azure AD Premium licenses for the members of all groups to which the expiration policy is applied.</span></span> <span data-ttu-id="85b65-122">有关详细信息，请参阅[Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)入门。</span><span class="sxs-lookup"><span data-stu-id="85b65-122">For more information see [Getting started with Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).</span></span>

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a><span data-ttu-id="85b65-123">哪些用户可以配置和使用 Microsoft 365 组过期策略？</span><span class="sxs-lookup"><span data-stu-id="85b65-123">Who can configure and use the Microsoft 365 groups expiration policy?</span></span>

|<span data-ttu-id="85b65-124">Role</span><span class="sxs-lookup"><span data-stu-id="85b65-124">Role</span></span>|<span data-ttu-id="85b65-125">可以执行的操作</span><span class="sxs-lookup"><span data-stu-id="85b65-125">What they can do</span></span>|
|---------|---------|
|<span data-ttu-id="85b65-126">全局管理员（在 Azure 中，公司管理员）、用户管理员</span><span class="sxs-lookup"><span data-stu-id="85b65-126">Global admin (in Azure, the Company administrator), User administrator</span></span>|<span data-ttu-id="85b65-127">创建、读取、更新或删除 Microsoft 365 组过期策略设置。</span><span class="sxs-lookup"><span data-stu-id="85b65-127">Create, read, update, or delete the Microsoft 365 groups expiration policy settings.</span></span>|
|<span data-ttu-id="85b65-128">User</span><span class="sxs-lookup"><span data-stu-id="85b65-128">User</span></span>|<span data-ttu-id="85b65-129">续订或[还原](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)自己拥有的 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="85b65-129">Renew or [restore](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) a Microsoft 365 group that they own</span></span>|

## <a name="how-to-set-the-expiration-policy"></a><span data-ttu-id="85b65-130">如何设置过期策略</span><span class="sxs-lookup"><span data-stu-id="85b65-130">How to set the expiration policy</span></span>

<span data-ttu-id="85b65-131">如上所述，默认情况下过期功能处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="85b65-131">As noted above, expiry is turned off by default.</span></span> <span data-ttu-id="85b65-132">管理员必须启用过期策略并将其属性设置为生效。</span><span class="sxs-lookup"><span data-stu-id="85b65-132">An administrator will have to enable the expiration policy and set the properties for it to take effect.</span></span> <span data-ttu-id="85b65-133">若要启用它，请转到**Azure Active Directory （AAD）**  >  **组**  >  **过期**。</span><span class="sxs-lookup"><span data-stu-id="85b65-133">To enable it go to **Azure Active Directory (AAD)** > **Groups** > **Expiration**.</span></span> <span data-ttu-id="85b65-134">你可以在此处设置默认组生存期，并指定你希望第一个和第二个过期通知转到组所有者的提前程度。</span><span class="sxs-lookup"><span data-stu-id="85b65-134">Here you can set the default group lifetime and specify how far in advance you want the first and second expiration notifications to go to the group owner.</span></span>

<span data-ttu-id="85b65-135">组生存期以天为单位指定，可设置为180、365或指定的自定义值。</span><span class="sxs-lookup"><span data-stu-id="85b65-135">The group lifetime is specified in days and can be set to 180, 365 or to a custom value that you specify.</span></span> <span data-ttu-id="85b65-136">自定义值必须至少为30天。</span><span class="sxs-lookup"><span data-stu-id="85b65-136">The custom value has to be at least 30 days.</span></span>

<span data-ttu-id="85b65-137">如果组没有所有者，到期电子邮件将转到指定的管理员。</span><span class="sxs-lookup"><span data-stu-id="85b65-137">If the group does not have an owner, the expiration emails will go to a specified administrator.</span></span>

<span data-ttu-id="85b65-138">您可以设置所有组的策略、仅选定的组或通过选择 "**无**" 将其完全关闭。</span><span class="sxs-lookup"><span data-stu-id="85b65-138">You can set the policy for all of your groups, only selected groups, or turn it off completely by selecting **None**.</span></span> <span data-ttu-id="85b65-139">请注意，对于不同的组，当前不能有不同的策略。</span><span class="sxs-lookup"><span data-stu-id="85b65-139">Note that currently you can't have different policies for different groups.</span></span>

![Azure Active Directory 中的组过期设置的屏幕截图](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a><span data-ttu-id="85b65-141">到期日期如何与保留策略一起使用</span><span class="sxs-lookup"><span data-stu-id="85b65-141">How expiry works with the retention policy</span></span>

<span data-ttu-id="85b65-142">如果您在组的安全性和合规性中心中设置了保留策略，则过期策略将与保留策略无缝运行。</span><span class="sxs-lookup"><span data-stu-id="85b65-142">If you have setup retention policy in Security and Compliance center for groups, expiration policy works seamlessly with retention policy.</span></span> <span data-ttu-id="85b65-143">当组过期时，组中的 "在邮箱中的对话" 框和组网站中的文件将保留在保留策略中定义的特定天数的保留容器中。</span><span class="sxs-lookup"><span data-stu-id="85b65-143">When a group expires, the group's conversations in mail box and files in the group site are retained in the retention container for the specific number of days defined in the retention policy.</span></span> <span data-ttu-id="85b65-144">但是，用户在过期后将看不到该组或其内容。</span><span class="sxs-lookup"><span data-stu-id="85b65-144">Users will not see the group, or its content, after expiration however.</span></span>

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a><span data-ttu-id="85b65-145">组所有者在其组过期时的学习方式和时间</span><span class="sxs-lookup"><span data-stu-id="85b65-145">How and when a group owner learns if their groups are going to expire</span></span>

<span data-ttu-id="85b65-146">组所有者将仅通过电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="85b65-146">Group owners will only be notified via email.</span></span> <span data-ttu-id="85b65-147">如果组是通过计划者、SharePoint 或任何其他应用程序创建的，则到期通知将始终通过电子邮件发送。</span><span class="sxs-lookup"><span data-stu-id="85b65-147">If the group was created via Planner, SharePoint, or any other app, the expiration notifications will always come via email.</span></span> <span data-ttu-id="85b65-148">如果组是通过团队创建的，则组所有者将通过 "活动" 部分收到要续订的通知。</span><span class="sxs-lookup"><span data-stu-id="85b65-148">If the group was created via Teams, the group owner will receive a notification to renew through the activity section.</span></span> <span data-ttu-id="85b65-149">如果您的组所有者没有有效的电子邮件地址，则建议您在组中启用过期。</span><span class="sxs-lookup"><span data-stu-id="85b65-149">It's not recommended that you enable expiration on a group if your group owner doesn't have a valid email address.</span></span>

<span data-ttu-id="85b65-150">在组过期之前的30天内，组所有者（或为没有所有者的组指定的电子邮件地址）将会收到一封电子邮件，允许他们轻松地续订组。</span><span class="sxs-lookup"><span data-stu-id="85b65-150">30 days before the group expires, the group owners (or the email addresses that you specified for groups that don't have an owner) will receive an email allowing them to easily renew the group.</span></span> <span data-ttu-id="85b65-151">如果不续订，他们将在到期前15天收到另一封续订电子邮件。</span><span class="sxs-lookup"><span data-stu-id="85b65-151">If they don't renew it, they'll receive another renewal email 15 days before expiration.</span></span> <span data-ttu-id="85b65-152">如果他们仍未续订，则会在过期前一天收到一封电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="85b65-152">If they still haven't renewed it, they will receive one more email notification the day before expiration.</span></span>

<span data-ttu-id="85b65-153">如果由于某种原因，所有者或管理员在过期之前没有对组进行续订，则管理员仍可以在到期后的30天内还原组。</span><span class="sxs-lookup"><span data-stu-id="85b65-153">If for some reason none of the owners or admins renew the group before it expires, the admin can still restore the group for up to 30 days after expiration.</span></span> <span data-ttu-id="85b65-154">有关详细信息，请参阅：[还原已删除的 Microsoft 365 组](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)。</span><span class="sxs-lookup"><span data-stu-id="85b65-154">For details see: [Restore a deleted Microsoft 365 group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

## <a name="related-articles"></a><span data-ttu-id="85b65-155">相关文章</span><span class="sxs-lookup"><span data-stu-id="85b65-155">Related articles</span></span>

[<span data-ttu-id="85b65-156">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="85b65-156">Overview of retention policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

[<span data-ttu-id="85b65-157">向孤立组分配新的所有者</span><span class="sxs-lookup"><span data-stu-id="85b65-157">Assign a new owner to an orphaned group</span></span>](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

<span data-ttu-id="85b65-158">[配置 Microsoft 365 组过期](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)'</span><span class="sxs-lookup"><span data-stu-id="85b65-158">[Configure Microsoft 365 groups expiration](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal) '</span></span>
