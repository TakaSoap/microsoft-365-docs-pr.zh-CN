---
title: 设计独立的 SharePoint Online 团队网站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 设计独立的 SharePoint Online 团队网站，包括确定权限级别、向具有访问组的用户分配权限以及嵌套的 Azure AD 组。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d53f3b45e3f406dfb0b38bcc910bd34876acb08
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288331"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="d818b-103">设计独立的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="d818b-103">Design an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d818b-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="d818b-104">**Applies to**</span></span>
- [<span data-ttu-id="d818b-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="d818b-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d818b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d818b-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


 <span data-ttu-id="d818b-107">**摘要：** 逐步完成独立 SharePoint Online 团队网站的设计过程。</span><span class="sxs-lookup"><span data-stu-id="d818b-107">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="d818b-108">本文将介绍创建独立 SharePoint Online 团队网站之前必须做出的关键设计决策。</span><span class="sxs-lookup"><span data-stu-id="d818b-108">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="d818b-109">第 1 阶段：确定 SharePoint 组和权限级别</span><span class="sxs-lookup"><span data-stu-id="d818b-109">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="d818b-110">默认情况下，每个 SharePoint Online 团队网站都是通过以下 SharePoint 组创建的：</span><span class="sxs-lookup"><span data-stu-id="d818b-110">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>

- <span data-ttu-id="d818b-111">\<site name> 成员</span><span class="sxs-lookup"><span data-stu-id="d818b-111">\<site name> Members</span></span>

- <span data-ttu-id="d818b-112">\<site name> 访问者</span><span class="sxs-lookup"><span data-stu-id="d818b-112">\<site name> Visitors</span></span>

- <span data-ttu-id="d818b-113">\<site name> 所有者</span><span class="sxs-lookup"><span data-stu-id="d818b-113">\<site name> Owners</span></span>

<span data-ttu-id="d818b-114">这些组独立于 Microsoft 365 和 Azure Active Directory (AD) 组，是分配网站资源权限的基础。</span><span class="sxs-lookup"><span data-stu-id="d818b-114">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>

<span data-ttu-id="d818b-115">确定 SharePoint 组的成员可在网站中执行哪些操作的特定权限集是权限级别。</span><span class="sxs-lookup"><span data-stu-id="d818b-115">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="d818b-116">默认情况下，SharePoint Online 团队网站有三个权限级别：编辑、读取和完全控制。</span><span class="sxs-lookup"><span data-stu-id="d818b-116">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="d818b-117">下表显示了 SharePoint 组和分配的权限级别的默认关联：</span><span class="sxs-lookup"><span data-stu-id="d818b-117">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>

****

|<span data-ttu-id="d818b-118">SharePoint 组</span><span class="sxs-lookup"><span data-stu-id="d818b-118">SharePoint group</span></span>|<span data-ttu-id="d818b-119">权限级别</span><span class="sxs-lookup"><span data-stu-id="d818b-119">Permission level</span></span>|
|---|---|
|<span data-ttu-id="d818b-120">\<site name> 成员</span><span class="sxs-lookup"><span data-stu-id="d818b-120">\<site name> Members</span></span>|<span data-ttu-id="d818b-121">编辑</span><span class="sxs-lookup"><span data-stu-id="d818b-121">Edit</span></span>|
|<span data-ttu-id="d818b-122">\<site name> 访问者</span><span class="sxs-lookup"><span data-stu-id="d818b-122">\<site name> Visitors</span></span>|<span data-ttu-id="d818b-123">读取</span><span class="sxs-lookup"><span data-stu-id="d818b-123">Read</span></span>|
|<span data-ttu-id="d818b-124">\<site name> 所有者</span><span class="sxs-lookup"><span data-stu-id="d818b-124">\<site name> Owners</span></span>|<span data-ttu-id="d818b-125">完全控制</span><span class="sxs-lookup"><span data-stu-id="d818b-125">Full control</span></span>|
|

 <span data-ttu-id="d818b-126">**最佳做法：** 您可以创建其他 SharePoint 组和权限级别。</span><span class="sxs-lookup"><span data-stu-id="d818b-126">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="d818b-127">但是，我们建议对独立 SharePoint Online 网站使用默认 SharePoint 组和权限级别。</span><span class="sxs-lookup"><span data-stu-id="d818b-127">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>

<span data-ttu-id="d818b-128">以下是默认的 SharePoint 组和权限级别。</span><span class="sxs-lookup"><span data-stu-id="d818b-128">Here are the default SharePoint groups and permission levels.</span></span>

![SharePoint Online 网站的默认 SharePoint 组和权限级别。](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="d818b-130">第 2 阶段：向具有访问组的用户分配权限</span><span class="sxs-lookup"><span data-stu-id="d818b-130">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="d818b-131">可以通过向 SharePoint 组添加用户帐户或用户帐户为一个成员的 Microsoft 365 或 Azure AD 组来向用户分配权限。</span><span class="sxs-lookup"><span data-stu-id="d818b-131">You can assign permissions to users by adding their user account, or a Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="d818b-132">添加后，将直接或间接通过 Microsoft 365 或 Azure AD 组的成员身份为用户帐户分配与 SharePoint 组关联的权限级别。</span><span class="sxs-lookup"><span data-stu-id="d818b-132">Once added, the user accounts, either directly or indirectly via membership in a Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>

<span data-ttu-id="d818b-133">使用默认 SharePoint 组作为示例：</span><span class="sxs-lookup"><span data-stu-id="d818b-133">Using the default SharePoint groups as an example:</span></span>

- <span data-ttu-id="d818b-134">成员 **\<site name> SharePoint** 组的成员（可同时包括用户帐户和组）分配有"编辑 **"** 权限级别</span><span class="sxs-lookup"><span data-stu-id="d818b-134">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>

- <span data-ttu-id="d818b-135">为 **\<site name> Visitors** SharePoint 组的成员分配了读取权限级别（可同时包括用户帐户和组）</span><span class="sxs-lookup"><span data-stu-id="d818b-135">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>

- <span data-ttu-id="d818b-136">SharePoint **\<site name> 组的所有者**（可同时包括用户帐户和组）的成员分配有完全 **控制** 权限级别</span><span class="sxs-lookup"><span data-stu-id="d818b-136">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>

 <span data-ttu-id="d818b-137">**最佳做法：** 尽管可以通过单个用户帐户管理权限，但我们建议改为使用单个 Azure AD 组（称为访问组）。</span><span class="sxs-lookup"><span data-stu-id="d818b-137">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="d818b-138">这简化了通过访问组成员身份管理权限，而不是管理每个 SharePoint 组的用户帐户列表。</span><span class="sxs-lookup"><span data-stu-id="d818b-138">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>

<span data-ttu-id="d818b-139">Microsoft 365 的 Azure AD 组不同于 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="d818b-139">Azure AD groups for Microsoft 365 are different tha Microsoft 365 groups.</span></span> <span data-ttu-id="d818b-140">Azure AD 组显示在 Microsoft 365 管理中心，其 **类型** 设置为 **"** 安全"，并且没有电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d818b-140">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="d818b-141">可以在：</span><span class="sxs-lookup"><span data-stu-id="d818b-141">Azure AD groups can be managed within:</span></span>

- <span data-ttu-id="d818b-142">Active Directory 域服务 (AD DS)</span><span class="sxs-lookup"><span data-stu-id="d818b-142">Active Directory Domain Services (AD DS)</span></span>

    <span data-ttu-id="d818b-143">这些组是在内部部署 AD DS 基础结构中创建并同步到 Microsoft 365 订阅的组。</span><span class="sxs-lookup"><span data-stu-id="d818b-143">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="d818b-144">在 Microsoft 365 管理中心中，这些组的状态为"已 **与 active directory 同步"。**</span><span class="sxs-lookup"><span data-stu-id="d818b-144">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>

- <span data-ttu-id="d818b-145">Office 365</span><span class="sxs-lookup"><span data-stu-id="d818b-145">Office 365</span></span>

    <span data-ttu-id="d818b-146">这些是已使用 Microsoft 365 管理中心、Azure 门户或 Microsoft PowerShell 创建的组。</span><span class="sxs-lookup"><span data-stu-id="d818b-146">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="d818b-147">在 Microsoft 365 管理中心中，这些组具有 **云\*\*\*\*状态**。</span><span class="sxs-lookup"><span data-stu-id="d818b-147">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>

 <span data-ttu-id="d818b-148">**最佳做法：** 如果使用的是本地 AD DS，并且与 Microsoft 365 订阅同步，则使用 AD DS 执行用户和组管理。</span><span class="sxs-lookup"><span data-stu-id="d818b-148">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>

<span data-ttu-id="d818b-149">对于独立的 SharePoint Online 团队网站，建议的组结构如下所示：</span><span class="sxs-lookup"><span data-stu-id="d818b-149">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>

****

|<span data-ttu-id="d818b-150">SharePoint 组</span><span class="sxs-lookup"><span data-stu-id="d818b-150">SharePoint group</span></span>|<span data-ttu-id="d818b-151">基于 Azure AD 的访问组</span><span class="sxs-lookup"><span data-stu-id="d818b-151">Azure AD-based access group</span></span>|<span data-ttu-id="d818b-152">权限级别</span><span class="sxs-lookup"><span data-stu-id="d818b-152">Permission level</span></span>|
|---|---|---|
|<span data-ttu-id="d818b-153">\<site name> 成员</span><span class="sxs-lookup"><span data-stu-id="d818b-153">\<site name> Members</span></span>|<span data-ttu-id="d818b-154">\<site name> 成员</span><span class="sxs-lookup"><span data-stu-id="d818b-154">\<site name> Members</span></span>|<span data-ttu-id="d818b-155">编辑</span><span class="sxs-lookup"><span data-stu-id="d818b-155">Edit</span></span>|
|<span data-ttu-id="d818b-156">\<site name> 访问者</span><span class="sxs-lookup"><span data-stu-id="d818b-156">\<site name> Visitors</span></span>|<span data-ttu-id="d818b-157">\<site name> 查看者</span><span class="sxs-lookup"><span data-stu-id="d818b-157">\<site name> Viewers</span></span>|<span data-ttu-id="d818b-158">读取</span><span class="sxs-lookup"><span data-stu-id="d818b-158">Read</span></span>|
|<span data-ttu-id="d818b-159">\<site name> 所有者</span><span class="sxs-lookup"><span data-stu-id="d818b-159">\<site name> Owners</span></span>|<span data-ttu-id="d818b-160">\<site name> 管理员</span><span class="sxs-lookup"><span data-stu-id="d818b-160">\<site name> Admins</span></span>|<span data-ttu-id="d818b-161">完全控制</span><span class="sxs-lookup"><span data-stu-id="d818b-161">Full control</span></span>|
|

 <span data-ttu-id="d818b-162">**最佳做法：** 虽然可以使用 Microsoft 365 或 Azure AD 组作为 SharePoint 组的成员，但我们建议你使用 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="d818b-162">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="d818b-163">Azure AD 组通过 AD DS 或 Microsoft 365 进行管理，可让你更灵活地使用嵌套组分配权限。</span><span class="sxs-lookup"><span data-stu-id="d818b-163">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>

<span data-ttu-id="d818b-164">下面是配置为使用基于 Azure AD 的访问组的默认 SharePoint 组。</span><span class="sxs-lookup"><span data-stu-id="d818b-164">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>

![将访问组用作默认 SharePoint Online 网站组的成员。](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

<span data-ttu-id="d818b-166">设计三个访问组时，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="d818b-166">When designing the three access groups, keep the following in mind:</span></span>

- <span data-ttu-id="d818b-167">管理员访问组中应该只有几个成员，与 **\<site name>** 管理团队网站的少量 SharePoint Online 管理员相对应。</span><span class="sxs-lookup"><span data-stu-id="d818b-167">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>

- <span data-ttu-id="d818b-168">大多数网站成员均在 **\<site name> "** 成员"或"**\<site name> 查看者"** 访问组中。</span><span class="sxs-lookup"><span data-stu-id="d818b-168">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="d818b-169">由于 Members 访问 **\<site name> 组的网站** 成员能够删除或修改网站中的资源，因此请仔细考虑其成员身份。</span><span class="sxs-lookup"><span data-stu-id="d818b-169">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="d818b-170">如果有疑问，将网站成员添加到 **\<site name> 查看者** 访问组。</span><span class="sxs-lookup"><span data-stu-id="d818b-170">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>

<span data-ttu-id="d818b-171">下面是名为 ProjectX 的隔离网站的 SharePoint 组和访问组的示例。</span><span class="sxs-lookup"><span data-stu-id="d818b-171">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>

![对名为 ProjectX 的 SharePoint Online 网站使用访问组的示例。](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="d818b-173">阶段 3：使用嵌套的 Azure AD 组</span><span class="sxs-lookup"><span data-stu-id="d818b-173">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="d818b-174">对于仅限于少数人员的项目，添加到网站的 SharePoint 组的基于 Azure AD 的单个级别访问组适合大多数方案。</span><span class="sxs-lookup"><span data-stu-id="d818b-174">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="d818b-175">但是，如果你拥有大量人员，并且这些人员已经是已建立 Azure AD 组的成员，则通过使用嵌套组或包含其他组作为成员的组，可以更轻松地分配 SharePoint 权限。</span><span class="sxs-lookup"><span data-stu-id="d818b-175">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>

<span data-ttu-id="d818b-176">例如，您希望创建独立的 SharePoint Online 团队网站，以在销售、市场营销、工程、法律和支持部门的主管人员以及那些已具有执行用户帐户成员身份的部门之间协作。</span><span class="sxs-lookup"><span data-stu-id="d818b-176">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="d818b-177">不要为新网站成员创建新组，并放入所有单独的行政用户帐户，而是将每个部门的现有执行组放在新组中。</span><span class="sxs-lookup"><span data-stu-id="d818b-177">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>

 <span data-ttu-id="d818b-178">如果在多个组织之间共享 Microsoft 365 订阅，则组织独立网站的单个级别的组成员身份可能由于用户帐户数量而变得难以管理。</span><span class="sxs-lookup"><span data-stu-id="d818b-178">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="d818b-179">在这种情况下，你可以为包含其组织中组的每个组织使用嵌套的 Azure AD 组来管理权限。</span><span class="sxs-lookup"><span data-stu-id="d818b-179">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>

<span data-ttu-id="d818b-180">若要使用嵌套的 Azure AD 组，</span><span class="sxs-lookup"><span data-stu-id="d818b-180">To use nested Azure AD groups:</span></span>

1. <span data-ttu-id="d818b-181">标识或创建将包含用户帐户的 Azure AD 组，并添加相应的用户帐户作为成员。</span><span class="sxs-lookup"><span data-stu-id="d818b-181">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>

2. <span data-ttu-id="d818b-182">创建将包含其他 Azure AD 组的基于 Azure AD 的访问组容器，并添加这些组作为成员。</span><span class="sxs-lookup"><span data-stu-id="d818b-182">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>

3. <span data-ttu-id="d818b-183">对于容器访问组的相应访问级别，请标识 SharePoint 组和相应的权限级别。</span><span class="sxs-lookup"><span data-stu-id="d818b-183">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>

> [!NOTE]
> <span data-ttu-id="d818b-184">不能使用嵌套的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="d818b-184">You cannot use nested Microsoft 365 groups.</span></span>

<span data-ttu-id="d818b-185">下面是 ProjectX 成员访问组的嵌套 Azure AD 组的示例。</span><span class="sxs-lookup"><span data-stu-id="d818b-185">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>

![对 ProjectX 网站的成员访问组使用嵌套访问组的示例。](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

<span data-ttu-id="d818b-187">由于研究、工程和项目领导团队中所有的用户帐户都是网站成员，因此将其 Azure AD 组添加到 ProjectX 成员访问组会更容易。</span><span class="sxs-lookup"><span data-stu-id="d818b-187">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>

## <a name="next-step"></a><span data-ttu-id="d818b-188">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d818b-188">Next step</span></span>

<span data-ttu-id="d818b-189">准备好在生产中创建和配置独立网站时，请参阅["部署独立的 SharePoint Online 团队网站"。](deploy-an-isolated-sharepoint-online-team-site.md)</span><span class="sxs-lookup"><span data-stu-id="d818b-189">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d818b-190">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d818b-190">See Also</span></span>

[<span data-ttu-id="d818b-191">独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="d818b-191">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="d818b-192">管理独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="d818b-192">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="d818b-193">部署独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="d818b-193">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
