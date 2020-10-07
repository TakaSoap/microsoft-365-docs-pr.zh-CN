---
title: 限制 Microsoft 365 中的共享
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
search.appverid:
- SPO160
- MET150
f1.keywords: NOCSH
ms.custom: ''
localization_priority: Priority
description: 了解在 Microsoft 365 中用于限制或禁用共享的选项。
ms.openlocfilehash: 7397078b6f347858e4ca91a0deeb9a1cf2fb6911
ms.sourcegitcommit: d648356b27842e779921859480b1b405a1804c7c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361901"
---
# <a name="limit-sharing-in-microsoft-365"></a><span data-ttu-id="31789-103">限制 Microsoft 365 中的共享</span><span class="sxs-lookup"><span data-stu-id="31789-103">Limit sharing in Microsoft 365</span></span>

<span data-ttu-id="31789-104">虽然无法完全禁用内部共享，也无法删除网站中的“共享”按钮，但可通过多种方式来限制 Microsoft 365 中的共享，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="31789-104">While you can't disable internal sharing entirely or remove the Share button from sites, there are a variety of ways that you can limit sharing in Microsoft 365 to meet the needs of your organization.</span></span>

<span data-ttu-id="31789-105">下表列出了共享文件的方法。</span><span class="sxs-lookup"><span data-stu-id="31789-105">The methods of sharing files are listed in the table below.</span></span> <span data-ttu-id="31789-106">有关详细信息，请单击“**共享方法**”列中的链接。</span><span class="sxs-lookup"><span data-stu-id="31789-106">Click the link in the **Sharing method** column for detailed information.</span></span>

|<span data-ttu-id="31789-107">共享方法</span><span class="sxs-lookup"><span data-stu-id="31789-107">Sharing method</span></span>|<span data-ttu-id="31789-108">说明</span><span class="sxs-lookup"><span data-stu-id="31789-108">Description</span></span>|<span data-ttu-id="31789-109">限制选项</span><span class="sxs-lookup"><span data-stu-id="31789-109">Limiting options</span></span>|
|:-------------|:----------|:-------------|
|[<span data-ttu-id="31789-110">Microsoft 365 组或团队</span><span class="sxs-lookup"><span data-stu-id="31789-110">Microsoft 365 group or team</span></span>](#microsoft-365-group-or-team)|<span data-ttu-id="31789-111">如果被授予对 Microsoft Teams 团队或 Microsoft 365 组的访问权限，可以有权编辑关联的 SharePoint 网站中的文件。</span><span class="sxs-lookup"><span data-stu-id="31789-111">People granted access to a Microsoft Teams team or Microsoft 365 group have edit access to files in the associated SharePoint site.</span></span>|<span data-ttu-id="31789-112">如果组或团队是专用的，则用于加入团队的共享邀请将会转到所有者那里以供其审批。</span><span class="sxs-lookup"><span data-stu-id="31789-112">If the group or team is private, sharing invitations to join the team go to the owner for approval.</span></span> <span data-ttu-id="31789-113">管理员可通过禁用来宾访问或使用敏感度标签来阻止组织外部人员的访问。</span><span class="sxs-lookup"><span data-stu-id="31789-113">Admins can disable guest access or use sensitivity labels to prevent access by people from outside the organization.</span></span>|
|[<span data-ttu-id="31789-114">SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="31789-114">SharePoint site</span></span>](#sharepoint-site)|<span data-ttu-id="31789-115">可向用户授予对 SharePoint 网站的“所有者”、“成员”或“访问者”访问权限，他们将拥有对网站中文件的相应访问权限级别。</span><span class="sxs-lookup"><span data-stu-id="31789-115">People can be granted Owner, Member, or Visitor access to a SharePoint site and will have that level of access to files in the site.</span></span>|<span data-ttu-id="31789-116">可限制网站权限，以便只有网站所有者可以共享网站。</span><span class="sxs-lookup"><span data-stu-id="31789-116">Site permissions can be restricted so that only site owners can share the site.</span></span> <span data-ttu-id="31789-117">管理员可以将网站设置为只读或完全阻止访问。</span><span class="sxs-lookup"><span data-stu-id="31789-117">Admins can set a site to read-only or block access entirely.</span></span>|
|[<span data-ttu-id="31789-118">与特定人员共享</span><span class="sxs-lookup"><span data-stu-id="31789-118">Sharing with specific people</span></span>](#sharing-with-specific-people)|<span data-ttu-id="31789-119">网站成员和拥有编辑权限的人员可以提供对文件和文件夹的直接权限，或通过使用*特定人员*链接进行共享。</span><span class="sxs-lookup"><span data-stu-id="31789-119">Site members and people with edit permissions can give direct permissions to files and folders or share them by using *Specific people* links.</span></span>|<span data-ttu-id="31789-120">可限制网站权限，以便只有网站所有者可以共享文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="31789-120">Site permissions can be restricted so that only site owners can share files and folders.</span></span> <span data-ttu-id="31789-121">在这种情况下，网站成员提供的直接访问和*特定人员*链接共享将会转到网站所有者那里以供其审批。</span><span class="sxs-lookup"><span data-stu-id="31789-121">In this case, direct access and *Specific people* link sharing by site members goes to site owner for approval.</span></span>|
|[<span data-ttu-id="31789-122">SharePoint 来宾共享</span><span class="sxs-lookup"><span data-stu-id="31789-122">SharePoint guest sharing</span></span>](#sharepoint-guest-sharing)|<span data-ttu-id="31789-123">SharePoint 网站所有者和成员可与组织外部的人员共享文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="31789-123">SharePoint site owners and members can share files and folders with people outside the organization.</span></span>|<span data-ttu-id="31789-124">可针对整个组织或单个网站禁用来宾共享。</span><span class="sxs-lookup"><span data-stu-id="31789-124">Guest sharing can be disabled for the entire organization or for individual sites.</span></span>|
|[<span data-ttu-id="31789-125">*你组织中的人员*共享链接</span><span class="sxs-lookup"><span data-stu-id="31789-125">*People in your organization* sharing links</span></span>](#people-in-your-organization-sharing-links)|<span data-ttu-id="31789-126">SharePoint 网站所有者和成员可以使用*你组织中的人员*链接（可用于组织内的所有人）来共享文件。</span><span class="sxs-lookup"><span data-stu-id="31789-126">SharePoint site owners and members can share files using *People in your organization* links, which will work for anyone inside the organization.</span></span>|<span data-ttu-id="31789-127">可在网站级别禁用*你组织中的人员*链接。</span><span class="sxs-lookup"><span data-stu-id="31789-127">*People in your organization* links can be disabled at the site level.</span></span>|
|[<span data-ttu-id="31789-128">创建网站、组和团队</span><span class="sxs-lookup"><span data-stu-id="31789-128">Create sites, groups, and teams</span></span>](#create-sites-groups-and-teams)|<span data-ttu-id="31789-129">默认情况下，用户可以创建他们可以共享内容的新网站、组和团队。</span><span class="sxs-lookup"><span data-stu-id="31789-129">By default, users can create new sites, groups, and teams from which they can share content.</span></span>|<span data-ttu-id="31789-130">管理员可限制可创建网站、组和团队的人员。</span><span class="sxs-lookup"><span data-stu-id="31789-130">Admins can restrict who can create sites, groups, and teams.</span></span>|
|[<span data-ttu-id="31789-131">电子邮件</span><span class="sxs-lookup"><span data-stu-id="31789-131">Email</span></span>](#email)|<span data-ttu-id="31789-132">有权访问文件的人员可通过电子邮件将其发送给其他人。</span><span class="sxs-lookup"><span data-stu-id="31789-132">People with access to a file can send it to others via email.</span></span>|<span data-ttu-id="31789-133">管理员可以使用敏感度标签对文件进行加密，以防止有人与未经授权的人员共享这些文件。</span><span class="sxs-lookup"><span data-stu-id="31789-133">Admins can encrypt files by using sensitivity labels to prevent them being shared with unauthorized people.</span></span>|
|[<span data-ttu-id="31789-134">下载或文件复制</span><span class="sxs-lookup"><span data-stu-id="31789-134">Download or file copy</span></span>](#download-or-file-copy)|<span data-ttu-id="31789-135">有权访问文件的人员可以下载或复制该文件，并与 Microsoft 365 范围之外的其他人共享。</span><span class="sxs-lookup"><span data-stu-id="31789-135">People with access to a file can download or copy it and share it with others outside the scope of Microsoft 365.</span></span>|<span data-ttu-id="31789-136">管理员可以使用敏感度标签对文件进行加密，以防止有人与未经授权的人员共享这些文件。</span><span class="sxs-lookup"><span data-stu-id="31789-136">Admins can encrypt files by using sensitivity labels to prevent them being shared with unauthorized people.</span></span>|

<span data-ttu-id="31789-137">你还可以限制人员访问共享内容的条件。</span><span class="sxs-lookup"><span data-stu-id="31789-137">You can also restrict the conditions under which people access shared content.</span></span> <span data-ttu-id="31789-138">有关详细信息，请参阅本文后面的[条件访问](#conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="31789-138">See [conditional access](#conditional-access) later in this article for more information.</span></span>

<span data-ttu-id="31789-139">虽然可使用本文中介绍的管理员控制措施来限制组织内的共享，但我们强烈建议考虑使用 Microsoft 365 中提供的安全和合规性功能，以创建安全的共享环境。</span><span class="sxs-lookup"><span data-stu-id="31789-139">While you can use the admin controls described in this article to limit sharing in your organization, we highly recommend that you consider using the security and compliance features available in Microsoft 365 to create a secure sharing environment.</span></span> <span data-ttu-id="31789-140">有关信息，请参阅[使用 Microsoft 365 在 SharePoint 中进行文件协作](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)和[使用安全隔离配置团队](secure-teams-security-isolation.md)。</span><span class="sxs-lookup"><span data-stu-id="31789-140">See [File collaboration in SharePoint with Microsoft 365](https://docs.microsoft.com/sharepoint/deploy-file-collaboration) and [Configure a team with security isolation](secure-teams-security-isolation.md) for information.</span></span>

<span data-ttu-id="31789-141">若要了解组织中如何使用共享，请[运行文件和文件夹共享报告](https://docs.microsoft.com/sharepoint/sharing-reports)。</span><span class="sxs-lookup"><span data-stu-id="31789-141">To understand how sharing is being used in your organization, [run a report on file and folder sharing](https://docs.microsoft.com/sharepoint/sharing-reports).</span></span>

## <a name="microsoft-365-group-or-team"></a><span data-ttu-id="31789-142">Microsoft 365 组或团队</span><span class="sxs-lookup"><span data-stu-id="31789-142">Microsoft 365 group or team</span></span>

<span data-ttu-id="31789-143">若要限制 Microsoft 365 组或 Microsoft Teams 团队中的共享，请务必将组或团队设为私人。</span><span class="sxs-lookup"><span data-stu-id="31789-143">If you want to limit sharing in a Microsoft 365 group or Microsoft Teams team, it's important to make the group or team private.</span></span> <span data-ttu-id="31789-144">组织内部人员可以随时加入公共组或团队。</span><span class="sxs-lookup"><span data-stu-id="31789-144">People inside your organization can join a public group or team anytime.</span></span> <span data-ttu-id="31789-145">除非组或团队是专用的，否则无法在组织内限制团队或其文件的共享。</span><span class="sxs-lookup"><span data-stu-id="31789-145">Unless the group or team is private, there's no way to limit sharing of the team or its files within the organization.</span></span>

### <a name="guest-sharing"></a><span data-ttu-id="31789-146">来宾共享</span><span class="sxs-lookup"><span data-stu-id="31789-146">Guest sharing</span></span>

<span data-ttu-id="31789-147">如果想要阻止 Teams 中的来宾访问，可在 Teams 管理中心内关闭来宾共享。</span><span class="sxs-lookup"><span data-stu-id="31789-147">If you want to prevent guest access in Teams, you can turn off guest sharing in the Teams admin center.</span></span>

<span data-ttu-id="31789-148">关闭 Teams 的来宾共享</span><span class="sxs-lookup"><span data-stu-id="31789-148">To turn off guest sharing for Teams</span></span>
1. <span data-ttu-id="31789-149">在 Teams 管理中心中，展开“**组织范围的设置**”，然后单击“**来宾访问**”。</span><span class="sxs-lookup"><span data-stu-id="31789-149">In the Teams admin center, expand **Org-wide settings**, and then click **Guest access**.</span></span>
2. <span data-ttu-id="31789-150">关闭“**在 Teams 中允许访客访问**”。</span><span class="sxs-lookup"><span data-stu-id="31789-150">Turn off **Allow guest access in Teams**.</span></span>
3. <span data-ttu-id="31789-151">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="31789-151">Click **Save**.</span></span>

<span data-ttu-id="31789-152">若要阻止 Microsoft 365 组中的来宾访问，可以在 Microsoft 365 管理中心内禁用组来宾访问设置。</span><span class="sxs-lookup"><span data-stu-id="31789-152">If you want to prevent guest access in Microsoft 365 Groups, you can turn off the groups guest access settings in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="31789-153">禁用 Microsoft 365 组中的来宾共享的具体步骤</span><span class="sxs-lookup"><span data-stu-id="31789-153">To turn off guest sharing in Microsoft 365 Groups</span></span>
1. <span data-ttu-id="31789-154">在 Microsoft 365 管理中心中，单击“**设置**”，然后单击“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="31789-154">In the Microsoft 365 admin center, click **Settings**, and then click **Settings**.</span></span>
2. <span data-ttu-id="31789-155">在“服务”\*\*\*\* 选项卡上，单击“Microsoft 365 组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="31789-155">On the **Services** tab, click **Microsoft 365 Groups**.</span></span>
3. <span data-ttu-id="31789-156">取消选中“**允许组织外部的组成员访问组内容**”和“**允许组所有者将组织外部的人员添加到组**”复选框。</span><span class="sxs-lookup"><span data-stu-id="31789-156">Clear the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes.</span></span>
4. <span data-ttu-id="31789-157">单击“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="31789-157">Click **Save changes**.</span></span>

    ![Microsoft 365 管理中心中内的 Microsoft 365 组共享设置的屏幕截图](../media/office-365-groups-guest-settings-off.png)

> [!NOTE]
> <span data-ttu-id="31789-159">如果想要阻止特定组或团队的来宾共享，可使用 [Microsoft PowerShell](per-group-guest-access.md) 或[敏感性标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="31789-159">If you want to prevent guest sharing for a particular group or team, you can do so by using [Microsoft PowerShell](per-group-guest-access.md) or [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

<span data-ttu-id="31789-160">可通过在 Azure Active Directory 中允许或阻止域，将来宾共享限制为指定域的用户。</span><span class="sxs-lookup"><span data-stu-id="31789-160">You can limit guest sharing to users from specific domains by allowing or blocking domains in Azure Active Directory.</span></span> <span data-ttu-id="31789-161">如果已启用 [Azure AD B2B 的 SharePoint 和 OneDrive 集成](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)，该操作还会影响 SharePoint 中的来宾共享。</span><span class="sxs-lookup"><span data-stu-id="31789-161">This will also affect guest sharing in SharePoint if you have enabled [SharePoint and OneDrive integration with Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

<span data-ttu-id="31789-162">仅允许向指定域发出共享邀请</span><span class="sxs-lookup"><span data-stu-id="31789-162">To allow sharing invitations only from specified domains</span></span>
1. <span data-ttu-id="31789-163">在 Azure Active Directory 中的“概述”页面上，单击“**组织关系**”。</span><span class="sxs-lookup"><span data-stu-id="31789-163">In Azure Active Directory, on the Overview page, click **Organizational relationships**.</span></span>
2. <span data-ttu-id="31789-164">单击“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="31789-164">Click **Settings**.</span></span>
3. <span data-ttu-id="31789-165">在“**协作限制**”下，选择“**拒绝向指定域发出邀请**”或“**仅允许向指定域发出邀请**”，然后键入要使用的域。</span><span class="sxs-lookup"><span data-stu-id="31789-165">Under **Collaboration restrictions**, select **Deny invitations to the specified domains** or **Allow invitations only to the specified domains**, and then type the domains that you want to use.</span></span>
4. <span data-ttu-id="31789-166">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="31789-166">Click **Save**.</span></span>

    ![Azure Active Directory 中的协作限制设置的屏幕截图](../media/azure-ad-allow-only-specified-domains.png)

## <a name="sharepoint-site"></a><span data-ttu-id="31789-168">SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="31789-168">SharePoint site</span></span>

<span data-ttu-id="31789-169">你可以将 SharePoint 网站共享的执行者限制为仅限网站所有者。</span><span class="sxs-lookup"><span data-stu-id="31789-169">You can limit SharePoint site sharing to site owners only.</span></span> <span data-ttu-id="31789-170">这将防止网站成员共享网站。</span><span class="sxs-lookup"><span data-stu-id="31789-170">This prevents site members from sharing the site.</span></span> <span data-ttu-id="31789-171">请注意，如果网站连接到了 Microsoft 365 组，组成员可以邀请其他人加入此组，这些用户将拥有网站访问权限。</span><span class="sxs-lookup"><span data-stu-id="31789-171">Keep in mind that if the site is connected to a Microsoft 365 group, group members can invite others to the group and those users will have site access.</span></span>

<span data-ttu-id="31789-172">将网站共享的执行者限制为所有者</span><span class="sxs-lookup"><span data-stu-id="31789-172">To limit site sharing to owners</span></span>
1. <span data-ttu-id="31789-173">在网站中，单击齿轮图标，然后单击“**网站权限**”。</span><span class="sxs-lookup"><span data-stu-id="31789-173">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="31789-174">在“**共享设置**”下，单击“**更改共享设置**”。</span><span class="sxs-lookup"><span data-stu-id="31789-174">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="31789-175">选择“**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**”。</span><span class="sxs-lookup"><span data-stu-id="31789-175">Select **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**.</span></span>
4. <span data-ttu-id="31789-176">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="31789-176">Click **Save**.</span></span>

    ![SharePoint 网站中共享权限设置的屏幕截图](../media/sharepoint-site-sharing-permissions-level-two.png)

<span data-ttu-id="31789-178">可通过关闭访问请求来阻止不是网站成员的用户请求访问。</span><span class="sxs-lookup"><span data-stu-id="31789-178">You can prevent users who are not members of the site from requesting access by turning off access requests.</span></span>

<span data-ttu-id="31789-179">关闭访问请求</span><span class="sxs-lookup"><span data-stu-id="31789-179">To turn off access requests</span></span>
1. <span data-ttu-id="31789-180">在网站中，单击齿轮图标，然后单击“**网站权限**”。</span><span class="sxs-lookup"><span data-stu-id="31789-180">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="31789-181">在“**共享设置**”下，单击“**更改共享设置**”。</span><span class="sxs-lookup"><span data-stu-id="31789-181">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="31789-182">关闭“**允许访问请求**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="31789-182">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="31789-183">可通过为相应网站允许或阻止域，将网站共享限制为指定域。</span><span class="sxs-lookup"><span data-stu-id="31789-183">You can limit site sharing to specific domains by allowing or blocking domains for the site.</span></span>

<span data-ttu-id="31789-184">按域限制网站共享</span><span class="sxs-lookup"><span data-stu-id="31789-184">To limit site sharing by domain</span></span>
1. <span data-ttu-id="31789-185">在 SharePoint 管理中心中的“**网站**”下，单击“**活动站点**”。</span><span class="sxs-lookup"><span data-stu-id="31789-185">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="31789-186">单击要配置的网站。</span><span class="sxs-lookup"><span data-stu-id="31789-186">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="31789-187">在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="31789-187">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="31789-188">在“**外部共享的高级设置**”下，选中“**按域限制共享**”。</span><span class="sxs-lookup"><span data-stu-id="31789-188">Under **Advanced settings for external sharing**, select the **Limit sharing by domain**.</span></span>
5. <span data-ttu-id="31789-189">添加你想要允许或阻止的域，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="31789-189">Add the domains that you want to allow or block, and then click **Save**.</span></span>
6. <span data-ttu-id="31789-190">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="31789-190">Click **Save**.</span></span>

    ![允许的域网站级别设置的屏幕截图](../media/limit-site-sharing-by-domain.png)

### <a name="block-access-to-a-site"></a><span data-ttu-id="31789-192">阻止访问网站</span><span class="sxs-lookup"><span data-stu-id="31789-192">Block access to a site</span></span>

<span data-ttu-id="31789-193">可通过更改网站的锁定状态，阻止访问网站或将网站设置为只读。</span><span class="sxs-lookup"><span data-stu-id="31789-193">You can block access to a site or make a site read-only by changing the lock state of the site.</span></span> <span data-ttu-id="31789-194">有关详细信息，请参阅[锁定和解除锁定网站](https://docs.microsoft.com/sharepoint/manage-lock-status)。</span><span class="sxs-lookup"><span data-stu-id="31789-194">For details, see [Lock and unlock sites](https://docs.microsoft.com/sharepoint/manage-lock-status).</span></span>

### <a name="permissions-inheritance"></a><span data-ttu-id="31789-195">权限继承</span><span class="sxs-lookup"><span data-stu-id="31789-195">Permissions inheritance</span></span>

<span data-ttu-id="31789-196">虽然不推荐，但你可以使用 [SharePoint 权限继承](https://docs.microsoft.com/sharepoint/what-is-permissions-inheritance)自定义网站和子网站的访问级别。</span><span class="sxs-lookup"><span data-stu-id="31789-196">While not recommended, you can use [SharePoint permissions inheritance](https://docs.microsoft.com/sharepoint/what-is-permissions-inheritance) to customize access levels to sites and subsites.</span></span>

## <a name="sharing-with-specific-people"></a><span data-ttu-id="31789-197">与特定人员共享</span><span class="sxs-lookup"><span data-stu-id="31789-197">Sharing with specific people</span></span>

<span data-ttu-id="31789-198">如果你想限制网站或其内容的共享，可以将网站配置为仅允许网站所有者共享文件、文件夹和该网站。</span><span class="sxs-lookup"><span data-stu-id="31789-198">if you want to limit the sharing of a site or its contents, you can configure the site to only allow site owners to share files, folders, and the site.</span></span> <span data-ttu-id="31789-199">进行此配置后，当网站成员尝试使用*特定人员*链接共享文件或文件夹时，该尝试将会转到网站所有者那里以供其审批。</span><span class="sxs-lookup"><span data-stu-id="31789-199">When this is configured, site members' attempts to share files or folders by using *Specific people* links will go to the site owner for approval.</span></span>

<span data-ttu-id="31789-200">将网站、文件和文件夹共享的执行者限制为所有者</span><span class="sxs-lookup"><span data-stu-id="31789-200">To limit site, file, and folder sharing to owners</span></span>
1. <span data-ttu-id="31789-201">在网站中，单击齿轮图标，然后单击“**网站权限**”。</span><span class="sxs-lookup"><span data-stu-id="31789-201">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="31789-202">在“**共享设置**”下，单击“**更改共享设置**”。</span><span class="sxs-lookup"><span data-stu-id="31789-202">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="31789-203">选择“**只有站点所有者可共享文件、文件夹和站点**”。</span><span class="sxs-lookup"><span data-stu-id="31789-203">Select **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="31789-204">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="31789-204">Click **Save**.</span></span>

    ![将 SharePoint 网站中共享权限设置设为仅限所有者的屏幕截图](../media/sharepoint-site-only-site-owners-can-share.png)

## <a name="sharepoint-guest-sharing"></a><span data-ttu-id="31789-206">SharePoint 来宾共享</span><span class="sxs-lookup"><span data-stu-id="31789-206">SharePoint guest sharing</span></span>

<span data-ttu-id="31789-207">如果想要阻止与组织外部的人员共享 SharePoint 或 OneDrive 文件和文件夹，可针对整个组织或单个网站关闭来宾共享。</span><span class="sxs-lookup"><span data-stu-id="31789-207">If you want to prevent sharing SharePoint or OneDrive files and folders with people outside your organization, you can turn off guest sharing for the entire organization or for an individual site.</span></span>

<span data-ttu-id="31789-208">针对组织关闭 SharePoint 来宾共享</span><span class="sxs-lookup"><span data-stu-id="31789-208">To turn off SharePoint guest sharing for your organization</span></span>
1. <span data-ttu-id="31789-209">在 SharePoint 管理中心中的“**策略**”下，单击“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="31789-209">In the SharePoint admin center, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="31789-210">在“**外部共享**”下，将 SharePoint 滑块向下拖动到“**仅限组织中的人员**”。</span><span class="sxs-lookup"><span data-stu-id="31789-210">Under **External sharing**, drag the SharePoint slider down to **Only people in your organization**.</span></span>
3. <span data-ttu-id="31789-211">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="31789-211">Click **Save**.</span></span>

    ![将 SharePoint 组织级别共享设置设为面向所有人的屏幕截图](../media/sharepoint-tenant-sharing-off.png)


<span data-ttu-id="31789-213">针对网站关闭来宾共享</span><span class="sxs-lookup"><span data-stu-id="31789-213">To turn off guest sharing for a site</span></span>
1. <span data-ttu-id="31789-214">在 SharePoint 管理中心中的“**网站**”下，单击“**活动站点**”。</span><span class="sxs-lookup"><span data-stu-id="31789-214">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="31789-215">单击要配置的网站。</span><span class="sxs-lookup"><span data-stu-id="31789-215">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="31789-216">在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="31789-216">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="31789-217">在“**外部共享**”下，选择“**仅限组织中的人员**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="31789-217">Under **External sharing**, choose **Only people in your organization**, and then click **Save**.</span></span>

    ![将 SharePoint 网站级别共享设置设为仅面向组织中的人员的屏幕截图](../media/sharepoint-site-external-sharing-settings-off.png)

<span data-ttu-id="31789-219">如果想要允许与组织外部的人员共享，但要确保每个人都进行身份验证，可以针对整个组织或单个网站禁用*任何人*（匿名共享）链接。</span><span class="sxs-lookup"><span data-stu-id="31789-219">If you would like to allow sharing with people outside your organization but you want to make sure that everyone authenticates, you can disable *Anyone* (anonymous sharing) links for the entire organization or for an individual site.</span></span>

<span data-ttu-id="31789-220">在组织级别关闭*任何人*链接</span><span class="sxs-lookup"><span data-stu-id="31789-220">To turn off *Anyone* links at the organization level</span></span>
1. <span data-ttu-id="31789-221">在 SharePoint 管理中心中的“**策略**”下，单击“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="31789-221">In the SharePoint admin center, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="31789-222">在“**外部共享**”下，将 SharePoint 滑块向下拖动到“**新来宾和现有来宾**”。</span><span class="sxs-lookup"><span data-stu-id="31789-222">Under **External sharing**, drag the SharePoint slider down to **New and existing guests**.</span></span>
3. <span data-ttu-id="31789-223">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="31789-223">Click **Save**.</span></span>

    ![将 SharePoint 组织级别共享设置设为面向新来宾和现有来宾的屏幕截图](../media/sharepoint-guest-sharing-new-existing-guests.png)

<span data-ttu-id="31789-225">关闭站点的 *“任何人”* 链接</span><span class="sxs-lookup"><span data-stu-id="31789-225">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="31789-226">在 SharePoint 管理中心中的“**网站**”下，单击“**活动站点**”。</span><span class="sxs-lookup"><span data-stu-id="31789-226">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="31789-227">单击要配置的网站。</span><span class="sxs-lookup"><span data-stu-id="31789-227">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="31789-228">在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="31789-228">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="31789-229">在“**外部共享**”下，选择“**新来宾和现有来宾**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="31789-229">Under **External sharing**, choose **New and existing guests**, and then click **Save**.</span></span>

    ![将 SharePoint 网站级别共享设置设为面向新设置和现有设置的屏幕截图](../media/sharepoint-site-external-sharing-settings-new-existing-guests.png)

## <a name="people-in-your-organization-sharing-links"></a><span data-ttu-id="31789-231">*你组织中的人员*共享链接</span><span class="sxs-lookup"><span data-stu-id="31789-231">*People in your organization* sharing links</span></span>

<span data-ttu-id="31789-232">默认情况下，网站的成员可以使用*你组织中的人员*链接来与组织中的其他人共享文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="31789-232">By default, members of a site can share files and folders with other people in your organization by using a *People in your organization* link.</span></span> <span data-ttu-id="31789-233">你可以使用 PowerShell 禁用*你组织中的人员*链接：</span><span class="sxs-lookup"><span data-stu-id="31789-233">You can disable *People in your organization* links by using PowerShell:</span></span>

`Set-SPOSite -Identity <site> -DisableCompanyWideSharingLinks`

<span data-ttu-id="31789-234">例如：</span><span class="sxs-lookup"><span data-stu-id="31789-234">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com -DisableCompanyWideSharingLinks`

## <a name="create-sites-groups-and-teams"></a><span data-ttu-id="31789-235">创建网站、组和团队</span><span class="sxs-lookup"><span data-stu-id="31789-235">Create sites, groups, and teams</span></span>

<span data-ttu-id="31789-236">默认情况下，用户可以创建他们可以共享内容的新网站、组和团队（具体取决于你的共享设置）。</span><span class="sxs-lookup"><span data-stu-id="31789-236">By default, users can create new sites, groups, and teams from which they may be able to share content (depending on your sharing settings).</span></span> <span data-ttu-id="31789-237">你可限制可创建网站、组和团队的人员。</span><span class="sxs-lookup"><span data-stu-id="31789-237">You can restrict who can create sites, groups, and teams.</span></span> <span data-ttu-id="31789-238">请参阅以下参考：</span><span class="sxs-lookup"><span data-stu-id="31789-238">See the following references:</span></span>

- [<span data-ttu-id="31789-239">管理 SharePoint 中的网站创建</span><span class="sxs-lookup"><span data-stu-id="31789-239">Manage site creation in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/manage-site-creation)
- [<span data-ttu-id="31789-240">管理可创建 Microsoft 365 组的人员</span><span class="sxs-lookup"><span data-stu-id="31789-240">Manage who can create Microsoft 365 Groups</span></span>](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups)

<span data-ttu-id="31789-241">请注意，限制组创建将限制团队创建。</span><span class="sxs-lookup"><span data-stu-id="31789-241">Note that restricting group creation restricts team creation.</span></span>

## <a name="email"></a><span data-ttu-id="31789-242">电子邮件</span><span class="sxs-lookup"><span data-stu-id="31789-242">Email</span></span>

<span data-ttu-id="31789-243">可通过加密防止不必要的电子邮件共享。</span><span class="sxs-lookup"><span data-stu-id="31789-243">You can prevent unwanted sharing of emails by using encryption.</span></span> <span data-ttu-id="31789-244">这将防止电子邮件被转发或与未经授权的用户共享。</span><span class="sxs-lookup"><span data-stu-id="31789-244">This prevents emails being forwarded or otherwise shared with unauthorized users.</span></span> <span data-ttu-id="31789-245">你可以使用敏感度标签来启用电子邮件加密。</span><span class="sxs-lookup"><span data-stu-id="31789-245">Email encryption can be enabled by using sensitivity labels.</span></span> <span data-ttu-id="31789-246">有关详细信息，请参阅[使用敏感度标签中的加密限制对内容的访问](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="31789-246">See [Restrict access to content by using encryption in sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) for details.</span></span>

## <a name="download-or-file-copy"></a><span data-ttu-id="31789-247">下载或文件复制</span><span class="sxs-lookup"><span data-stu-id="31789-247">Download or file copy</span></span>

<span data-ttu-id="31789-248">有权访问 Microsoft 365 中的文件和文件夹的用户可以下载文件并将其复制到外部媒体。</span><span class="sxs-lookup"><span data-stu-id="31789-248">Users who have access to files and folders in Microsoft 365 can download files and copy them to external media.</span></span> <span data-ttu-id="31789-249">若要减少不必要的文件共享的风险，可使用敏感度标签对内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="31789-249">To reduce the risk of unwanted file sharing, you can encrypt the content by using sensitivity labels.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="31789-250">条件访问</span><span class="sxs-lookup"><span data-stu-id="31789-250">Conditional access</span></span>

<span data-ttu-id="31789-251">Azure Active Directory 条件访问提供的选项可根据网络位置、设备运行状况、登录风险和其他因素限制或防止与人员共享。</span><span class="sxs-lookup"><span data-stu-id="31789-251">Azure Active Directory conditional access provides options to limit or prevent sharing with people based on network location, device health, sign-in risk, and other factors.</span></span> <span data-ttu-id="31789-252">查看[什么是条件访问？](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="31789-252">See [What is Conditional Access?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

<span data-ttu-id="31789-253">SharePoint 提供与 Azure AD 条件访问的直接集成，适用于未托管的设备和网络位置。</span><span class="sxs-lookup"><span data-stu-id="31789-253">SharePoint provides direct integration with Azure AD conditional access for both unmanaged devices and network location.</span></span> <span data-ttu-id="31789-254">有关详细信息，请参阅以下参考：</span><span class="sxs-lookup"><span data-stu-id="31789-254">See the following references for details:</span></span>

- [<span data-ttu-id="31789-255">控制来自非托管设备的访问</span><span class="sxs-lookup"><span data-stu-id="31789-255">Control access from unmanaged devices</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
- [<span data-ttu-id="31789-256">根据网络位置控制对 SharePoint 和 OneDrive 数据的访问</span><span class="sxs-lookup"><span data-stu-id="31789-256">Control access to SharePoint and OneDrive data based on network location</span></span>](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)

## <a name="see-also"></a><span data-ttu-id="31789-257">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31789-257">See also</span></span>

[<span data-ttu-id="31789-258">Microsoft 365 来宾共享设置参考</span><span class="sxs-lookup"><span data-stu-id="31789-258">Microsoft 365 guest sharing settings reference</span></span>](microsoft-365-guest-settings.md)
