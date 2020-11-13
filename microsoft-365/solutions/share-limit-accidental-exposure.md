---
title: 限制意外公开
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
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
description: 了解如何在与组织外人员共享文件时限制意外公开信息。
ms.openlocfilehash: 430c00d46fa3801d0869b05a651fadd3bf5dea28
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49029965"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a><span data-ttu-id="11f98-103">在与组织外人员共享文件时限制意外公开信息</span><span class="sxs-lookup"><span data-stu-id="11f98-103">Limit accidental exposure to files when sharing with people outside your organization</span></span>

<span data-ttu-id="11f98-104">与组织外人员共享文件和文件夹时，可通过多种方法来降低意外共享敏感信息的机率。</span><span class="sxs-lookup"><span data-stu-id="11f98-104">When sharing files and folders with people outside your organization, there are a variety of options to reduce the chances of accidentally sharing sensitive information.</span></span> <span data-ttu-id="11f98-105">可从本文中的选项中进行选择，以最好地满足贵组织的需求。</span><span class="sxs-lookup"><span data-stu-id="11f98-105">You can choose from the options in this article to best meet the needs of your organization.</span></span>

## <a name="use-best-practices-for-anyone-links"></a><span data-ttu-id="11f98-106">对“任何人”链接使用最佳做法</span><span class="sxs-lookup"><span data-stu-id="11f98-106">Use best practices for Anyone links</span></span>

<span data-ttu-id="11f98-107">如果贵组织中的人员需要进行未经身份验证共享，但你担心未经身份验证的人员修改内容，请阅读[未经身份验证共享的最佳做法](best-practices-anonymous-sharing.md)，获取有关如何处理贵组织中的未经身份验证共享的指南。</span><span class="sxs-lookup"><span data-stu-id="11f98-107">If people in your organization need to do unauthenticated sharing, but you're concerned about unauthenticated people modifying content, read [Best practices for unauthenticated sharing](best-practices-anonymous-sharing.md) for guidance on how to work with unauthenticated sharing in your organization.</span></span>

## <a name="turn-off-anyone-links"></a><span data-ttu-id="11f98-108">关闭“任何人”链接</span><span class="sxs-lookup"><span data-stu-id="11f98-108">Turn off Anyone links</span></span>

<span data-ttu-id="11f98-109">建议对相应内容保持启用 *“任何人”* 链接，因为它是最简单的共享方法，可帮助降低用户查找超出 IT 部门控制范围的其他解决方案的风险。</span><span class="sxs-lookup"><span data-stu-id="11f98-109">We recommend leaving *Anyone* links enabled for appropriate content because it's the easiest way to share and can help reduce the risk of users seeking other solutions that are outside the control of your IT department.</span></span> <span data-ttu-id="11f98-110">可以将“ *任何人* ”链接转发给其他人，但是文件访问权只可用于拥有该链接的人。</span><span class="sxs-lookup"><span data-stu-id="11f98-110">*Anyone* links can be forwarded to others, but file access is only available to those who have the link.</span></span>

<span data-ttu-id="11f98-111">如果始终希望组织外人员在访问 SharePoint、组或团队中的内容时进行身份验证，则可关闭“ *任何人* ”共享。</span><span class="sxs-lookup"><span data-stu-id="11f98-111">If you always want people outside your organization to authenticate when accessing content in SharePoint, Groups, or Teams, you can turn off *Anyone* sharing.</span></span> <span data-ttu-id="11f98-112">这将能够防止用户未经验证身份而共享内容。</span><span class="sxs-lookup"><span data-stu-id="11f98-112">This will prevent users from unauthenticated sharing of content.</span></span>

<span data-ttu-id="11f98-113">如果禁用“ *任何人* ”链接，用户仍然可以使用“ *特定人员* ”链接与来宾轻松共享。</span><span class="sxs-lookup"><span data-stu-id="11f98-113">If you disable *Anyone* links, users can still easily share with guests using *Specific people* links.</span></span> <span data-ttu-id="11f98-114">在这种情况下，需要对所有组织外人员进行身份验证，然后才能访问共享内容。</span><span class="sxs-lookup"><span data-stu-id="11f98-114">In this case, all people outside your organization will be required to authenticate before they can access the shared content.</span></span>

<span data-ttu-id="11f98-115">根据你的需要，可以针对特定网站或整个组织禁用“ *任何人* ”链接。</span><span class="sxs-lookup"><span data-stu-id="11f98-115">Depending on your needs, you can disable *Anyone* links for specific sites, or for your whole organization.</span></span>

<span data-ttu-id="11f98-116">关闭组织的 *“任何人”* 链接</span><span class="sxs-lookup"><span data-stu-id="11f98-116">To turn off *Anyone* links for your organization</span></span>
1. <span data-ttu-id="11f98-117">在 SharePoint 管理中心的左侧导航栏中，单击 **“共享”** 。</span><span class="sxs-lookup"><span data-stu-id="11f98-117">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="11f98-118">将 SharePoint 外部共享设置设为 **“新来宾和现有来宾”** 。</span><span class="sxs-lookup"><span data-stu-id="11f98-118">Set the SharePoint external sharing settings to **New and existing guests**.</span></span>

   ![组织级 SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-organization-external-sharing-controls-new-users.png)

3. <span data-ttu-id="11f98-120">单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="11f98-120">Click **Save**.</span></span>

<span data-ttu-id="11f98-121">关闭站点的 *“任何人”* 链接</span><span class="sxs-lookup"><span data-stu-id="11f98-121">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="11f98-122">在 SharePoint 管理中心的左侧导航栏中，展开 **“站点”** ，然后单击 **“活动站点”** 。</span><span class="sxs-lookup"><span data-stu-id="11f98-122">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="11f98-123">选择要配置的网站。</span><span class="sxs-lookup"><span data-stu-id="11f98-123">Select the site that you want to configure.</span></span>
3. <span data-ttu-id="11f98-124">在功能区中，单击 **“共享”** 。</span><span class="sxs-lookup"><span data-stu-id="11f98-124">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="11f98-125">确保将共享设置为 **“新来宾和现有来宾”** 。</span><span class="sxs-lookup"><span data-stu-id="11f98-125">Ensure that sharing is set to **New and existing guests**.</span></span>

   ![网站级 SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-site-external-sharing-settings.png)

5. <span data-ttu-id="11f98-127">如果进行了任何更改，请单击 **“保存”** 。</span><span class="sxs-lookup"><span data-stu-id="11f98-127">If you made changes, click **Save**.</span></span>

## <a name="domain-filtering"></a><span data-ttu-id="11f98-128">域筛选</span><span class="sxs-lookup"><span data-stu-id="11f98-128">Domain filtering</span></span>

<span data-ttu-id="11f98-129">可以使用域允许或拒绝列表来指定用户与组织外部人员共享时可以使用的域。</span><span class="sxs-lookup"><span data-stu-id="11f98-129">You can use domain allow or deny lists to specify which domains your users can use when sharing with people outside your organization.</span></span>

<span data-ttu-id="11f98-130">使用允许列表，可以指定贵组织中用户可与组织外人员共享的域名列表。</span><span class="sxs-lookup"><span data-stu-id="11f98-130">With an allow list, you can specify a list of domains where users in your organization can share with people outside your organization.</span></span> <span data-ttu-id="11f98-131">禁止与他人共享域名。</span><span class="sxs-lookup"><span data-stu-id="11f98-131">Sharing with to other domains is blocked.</span></span> <span data-ttu-id="11f98-132">如果贵组织仅从特定域的列表中与人员进行协作，则可以使用此功能阻止与其他域共享。</span><span class="sxs-lookup"><span data-stu-id="11f98-132">If your organization only collaborates with people from a list of specific domains, you can use this feature to prevent sharing with other domains.</span></span>

<span data-ttu-id="11f98-133">使用拒绝列表，可以指定贵组织用户无法与组织外人员共享的域名列表。</span><span class="sxs-lookup"><span data-stu-id="11f98-133">With a deny list, you can specify a list of domains from which users in your organization cannot share with people outside your organization.</span></span> <span data-ttu-id="11f98-134">禁止共享列出的域名。</span><span class="sxs-lookup"><span data-stu-id="11f98-134">Sharing with the listed domains is blocked.</span></span> <span data-ttu-id="11f98-135">如果有竞争对手（例如想要阻止其访问组织中的内容的人员），此功能可能非常有用。</span><span class="sxs-lookup"><span data-stu-id="11f98-135">This can be useful if you have competitors, for example, who you want to prevent from accessing content in your organization.</span></span>

<span data-ttu-id="11f98-136">允许列表和拒绝列表仅影响与来宾的共享。</span><span class="sxs-lookup"><span data-stu-id="11f98-136">The allow and deny lists only affect sharing with guests.</span></span> <span data-ttu-id="11f98-137">如果尚未禁用用户，用户仍可使用“ *任何人* ”链接与被禁止域中的人员共享。</span><span class="sxs-lookup"><span data-stu-id="11f98-137">Users can still share with people from prohibited domains by using *Anyone* links if you haven't disabled them.</span></span> <span data-ttu-id="11f98-138">若要使用域允许和拒绝列表获得最佳结果，请考虑按上面所述禁用“ *任何人* ”链接。</span><span class="sxs-lookup"><span data-stu-id="11f98-138">For best results with domain allow and deny lists, consider disabling *Anyone* links as described above.</span></span>

<span data-ttu-id="11f98-139">设置域允许或拒绝列表</span><span class="sxs-lookup"><span data-stu-id="11f98-139">To set up a domain allow or deny list</span></span>
1. <span data-ttu-id="11f98-140">在 SharePoint 管理中心的左侧导航栏中，单击“ **共享** ”。</span><span class="sxs-lookup"><span data-stu-id="11f98-140">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="11f98-141">在 **“用于外部共享的高级设置”** 下，选中 **“限制外部共享(按域)”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="11f98-141">Under **Advanced settings for external sharing** , select the **Limit external sharing by domain** check box.</span></span>
3. <span data-ttu-id="11f98-142">单击 **“添加域”** 。</span><span class="sxs-lookup"><span data-stu-id="11f98-142">Click **Add domains**.</span></span>
4. <span data-ttu-id="11f98-143">选择是否要阻止域，键入域，然后单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="11f98-143">Select whether you want to block domains, type the domains, and click **OK**.</span></span>

   ![SharePoint 按域限制外部共享设置的屏幕截图](../media/sharepoint-sharing-block-domain.png)

5. <span data-ttu-id="11f98-145">单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="11f98-145">Click **Save**.</span></span>

<span data-ttu-id="11f98-146">如果想要在高于 SharePoint 和 OneDrive 的级别限制按域共享，则可以在 Azure Active Directory 中[允许或阻止来自特定组织的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="11f98-146">If you want to limit sharing by domain at a higher level than SharePoint and OneDrive, you can [allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) in Azure Active Directory.</span></span> <span data-ttu-id="11f98-147">（必须配置 [SharePoint 和 OneDrive 与 Azure AD B2B Preview 的集成](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)，这些设置才会影响 SharePoint 和 OneDrive。）</span><span class="sxs-lookup"><span data-stu-id="11f98-147">(You must configure the [SharePoint and OneDrive integration with Azure AD B2B Preview](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) for these settings to affect SharePoint and OneDrive.)</span></span>

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a><span data-ttu-id="11f98-148">限制与外部组织人员共享的文件、文件夹和站点至指定安全组。</span><span class="sxs-lookup"><span data-stu-id="11f98-148">Limit sharing of files, folders, and sites with people outside your organization to specified security groups</span></span>

<span data-ttu-id="11f98-149">可以将于组织外人员共享的文件、文件见和站点限定至指定安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="11f98-149">You can restrict sharing of files, folders, and sites with people outside your organization to members of a specific security group.</span></span> <span data-ttu-id="11f98-150">如果希望启用外部共享，但有批准工作流或请求流程，则此功能非常有用。</span><span class="sxs-lookup"><span data-stu-id="11f98-150">This is useful if you want to enable external sharing, but with an approval workflow or request process.</span></span> <span data-ttu-id="11f98-151">或者，可能需要用户先完成培训课程，然后再将其添加到安全组，并允许外部共享。</span><span class="sxs-lookup"><span data-stu-id="11f98-151">Alternatively, you might require your users to complete a training course before they're added to the security group and are allowed to share externally.</span></span>

<span data-ttu-id="11f98-152">限制与安全组成员进行外部共享</span><span class="sxs-lookup"><span data-stu-id="11f98-152">To limit external sharing to members of a security group</span></span>
1. <span data-ttu-id="11f98-153">在 “ [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)”左侧导航栏的“ **策略** ”下，单击 “ **共享** ”。</span><span class="sxs-lookup"><span data-stu-id="11f98-153">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), in the left navigation, under **Policies** , click **Sharing**.</span></span>
2. <span data-ttu-id="11f98-154">在“ **外部共享** ”下，展开“ **更多外部共享设置** ”。</span><span class="sxs-lookup"><span data-stu-id="11f98-154">Under **External sharing** , expand **More external sharing settings**.</span></span>

3. <span data-ttu-id="11f98-155">选择“ **仅允许特定安全组中的用户外部共享** ”，然后选择“ **管理安全组** ”。</span><span class="sxs-lookup"><span data-stu-id="11f98-155">Select **Allow only users in specific security groups to share externally** , and then select **Manage security groups**.</span></span>

    ![“管理安全组”窗格屏幕截图](https://docs.microsoft.com/sharepoint/sharepointonline/media/manage-security-groups.png)

4. <span data-ttu-id="11f98-157">在“ **添加安全组** ”框中，输入安全组的名称。</span><span class="sxs-lookup"><span data-stu-id="11f98-157">In the **Add a security group** box, enter a name for a security group.</span></span> <span data-ttu-id="11f98-158">安全组框出现。</span><span class="sxs-lookup"><span data-stu-id="11f98-158">The security group box appears.</span></span>

5. <span data-ttu-id="11f98-159">在安全组名称旁边的“ **共享对象** ”下拉菜单中，选择以下任一选项：</span><span class="sxs-lookup"><span data-stu-id="11f98-159">Next to the security group name, from the **Can share with** dropdown, select either:</span></span>

    - <span data-ttu-id="11f98-160">**仅限经过身份验证的访客** （默认）</span><span class="sxs-lookup"><span data-stu-id="11f98-160">**Authenticated guests only** (default)</span></span>
    - <span data-ttu-id="11f98-161">**任何人**</span><span class="sxs-lookup"><span data-stu-id="11f98-161">**Anyone**</span></span>

6. <span data-ttu-id="11f98-162">选择“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="11f98-162">Select **Save**.</span></span>

<span data-ttu-id="11f98-163">请注意，这会影响文件、文件夹和网站，但不会影响 Microsoft 365 组或 Teams。</span><span class="sxs-lookup"><span data-stu-id="11f98-163">Note that this affects files, folders, and sites, but not Microsoft 365 groups or Teams.</span></span> <span data-ttu-id="11f98-164">如果成员邀请来宾加入 Microsoft 365 专用组或 Microsoft Teams 专用团队，邀请会发送给组或团队所有者以供审批。</span><span class="sxs-lookup"><span data-stu-id="11f98-164">When members invite guests to a private Microsoft 365 group or a private team in Microsoft Teams, the invitation is sent to the group or team owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="11f98-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11f98-165">See Also</span></span>

[<span data-ttu-id="11f98-166">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="11f98-166">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="11f98-167">有关与匿名用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="11f98-167">Best practices for sharing files and folders with anonymous users</span></span>](best-practices-anonymous-sharing.md)
