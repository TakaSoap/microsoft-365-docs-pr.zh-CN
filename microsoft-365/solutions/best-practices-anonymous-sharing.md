---
title: 未经身份验证共享的最佳做法
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
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: 在本文中，你将了解与身份未经验证的用户共享文件和文件夹的最佳做法。
ms.openlocfilehash: 2c89ca319ba79d6f0463cc6d244c8d91928d6e42
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327019"
---
# <a name="best-practices-for-sharing-files-and-folders-with-unauthenticated-users"></a><span data-ttu-id="9c477-103">有关与身份未经验证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="9c477-103">Best practices for sharing files and folders with unauthenticated users</span></span>

<span data-ttu-id="9c477-104">未经身份验证共享（*任何人* 链接）非常方便，在各种情景中都很有用。</span><span class="sxs-lookup"><span data-stu-id="9c477-104">Unauthenticated sharing (*Anyone* links) can be convenient and is useful in various scenarios.</span></span> <span data-ttu-id="9c477-105">*任何人* 链接是最简单的共享方式：用户无需身份验证即可打开链接，并可将其自由传递给其他人。</span><span class="sxs-lookup"><span data-stu-id="9c477-105">*Anyone* links are the easiest way to share: people can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="9c477-p102">通常，并非组织内容所有内容都适用于未经身份验证的共享。本文介绍了可用来帮助创建一个环境的选项，在这个环境中，用户可以使用未经身份验证的文件和文件夹共享，但同时也有安全措施帮助保护组织的内容。</span><span class="sxs-lookup"><span data-stu-id="9c477-p102">Usually, not all content in an organization is appropriate for unauthenticated sharing. This article covers the options available to help you create an environment where your users can use unauthenticated sharing of files and folders, but where there are safeguards in place to help protect your organization's content.</span></span>

> [!NOTE]
> <span data-ttu-id="9c477-108">若要正常使用未经身份验证共享功能，必须为你的组织以及要使用的各个网站或团队启用该功能。</span><span class="sxs-lookup"><span data-stu-id="9c477-108">For unauthenticated sharing to work, you must enable it for your organization and for the individual site or team that you'll be using.</span></span> <span data-ttu-id="9c477-109">对于你希望启用该功能的情景，请参阅[与组织外部人员协作](collaborate-with-people-outside-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="9c477-109">See [Collaborating with people outside your organization](collaborate-with-people-outside-your-organization.md) for the scenario that you want to enable.</span></span>

## <a name="set-an-expiration-date-for-anyone-links"></a><span data-ttu-id="9c477-110">设置“任何人”链接的到期日期</span><span class="sxs-lookup"><span data-stu-id="9c477-110">Set an expiration date for Anyone links</span></span>

<span data-ttu-id="9c477-111">文件通常在网站、组和团队中存储很长一段时间。</span><span class="sxs-lookup"><span data-stu-id="9c477-111">Files are often stored in sites, groups, and teams for long periods of time.</span></span> <span data-ttu-id="9c477-112">偶尔有些数据保留策略会要求将文件保留几年时间。</span><span class="sxs-lookup"><span data-stu-id="9c477-112">Occasionally there are data retention policies that require files to be retained for years.</span></span> <span data-ttu-id="9c477-113">如果与未经身份验证人员共享此类文件，可能会导致将来在意想不到的情况下访问和更改文件。</span><span class="sxs-lookup"><span data-stu-id="9c477-113">If such files are shared with unauthenticated people, this could lead to unexpected access and changes to files in the future.</span></span> <span data-ttu-id="9c477-114">为了降低这种可能性，可为 *任何人* 链接配置到期时间。</span><span class="sxs-lookup"><span data-stu-id="9c477-114">To mitigate this possibility, you can configure an expiration time for *Anyone* links.</span></span>

<span data-ttu-id="9c477-115">*任何人* 链接到期后，不能再将其用于访问内容。</span><span class="sxs-lookup"><span data-stu-id="9c477-115">Once an *Anyone* link expires, it can no longer be used to access content.</span></span>

<span data-ttu-id="9c477-116">设置组织中“任何人”链接到期日期</span><span class="sxs-lookup"><span data-stu-id="9c477-116">To set an expiration date for Anyone links across the organization</span></span>

1. <span data-ttu-id="9c477-117">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="9c477-117">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="9c477-118">在左侧导航中，展开“**策略**”，然后单击“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-118">In the left navigation, expand **Policies**, and then click **Sharing**.</span></span>
3. <span data-ttu-id="9c477-119">在 **“任何人链接的选择到期和权限”** 下，选中 **“这些链接必须在这些天数内过期”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="9c477-119">Under **Choose expiration and permissions options for Anyone links**, select the **These links must expire within this many days** check box.</span></span></br>
   <span data-ttu-id="9c477-120">![SharePoint 组织级别的“任何人”链接到期设置的屏幕截图](../media/sharepoint-organization-anyone-link-expiration.png)</span><span class="sxs-lookup"><span data-stu-id="9c477-120">![Screenshot of SharePoint organization-level Anyone link expiration settings](../media/sharepoint-organization-anyone-link-expiration.png)</span></span>
4. <span data-ttu-id="9c477-121">在输入框中键入天数，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-121">Type a number of days in the box, and then click **Save**.</span></span>

<span data-ttu-id="9c477-122">设置特定站点“任何人”链接的到期日期</span><span class="sxs-lookup"><span data-stu-id="9c477-122">To set an expiration date for Anyone links on a specific site</span></span>

1. <span data-ttu-id="9c477-123">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="9c477-123">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="9c477-124">在左侧导航中，展开“**站点**”，然后单击“**活动站点**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-124">In the left navigation, expand **Sites**, and then click **Active sites**.</span></span>
3. <span data-ttu-id="9c477-125">选择要更改的站点，然后单击“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-125">Select the site you want to change, and then click **Sharing**.</span></span>
4. <span data-ttu-id="9c477-126">在“**“任何人”链接的高级设置**” 的“**”任何人“链接到期**”下，取消选中“**与组织级设置相同**”复选框。</span><span class="sxs-lookup"><span data-stu-id="9c477-126">Under **Advanced settings for Anyone links**, under **Expiration of Anyone links**, clear the **Same as organization-level setting** check box.</span></span></br>
   <span data-ttu-id="9c477-127">![SharePoint 网站级别的“任何人”链接到期设置的屏幕截图](../media/sharepoint-organization-anyone-link-expiration-site.png)</span><span class="sxs-lookup"><span data-stu-id="9c477-127">![Screenshot of SharePoint site-level Anyone link expiration settings](../media/sharepoint-organization-anyone-link-expiration-site.png)</span></span>
5. <span data-ttu-id="9c477-128">选择“**这些链接必须在该天数内过期**”选项，然后再框中输入天数。</span><span class="sxs-lookup"><span data-stu-id="9c477-128">Select the **These links must expire within this many days** option, and type a number of days in the box.</span></span>
6. <span data-ttu-id="9c477-129">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-129">Click **Save**.</span></span>

<span data-ttu-id="9c477-130">请注意，*任何人* 链接到期后，可以使用新的“*任何人*”链接重新共享该文件或文件夹。</span><span class="sxs-lookup"><span data-stu-id="9c477-130">Note that once an *Anyone* link expires, the file or folder can be re-shared with a new *Anyone* link.</span></span>

<span data-ttu-id="9c477-131">可使用 [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) 设置特定 OneDrive 的“*任何人*”链接的到期时间。</span><span class="sxs-lookup"><span data-stu-id="9c477-131">You can set *Anyone* link expiration for a specific OneDrive by using [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite).</span></span>

## <a name="set-link-permissions"></a><span data-ttu-id="9c477-132">设置链接权限</span><span class="sxs-lookup"><span data-stu-id="9c477-132">Set link permissions</span></span>

<span data-ttu-id="9c477-133">默认情况下，文件的 *任何人* 链接允许用户编辑文件，而文件夹的 *任何人* 链接允许用户编辑和查看其中的文件以及向文件夹上传新文件。</span><span class="sxs-lookup"><span data-stu-id="9c477-133">By default, *Anyone* links for a file allow people to edit the file, and *Anyone* links for a folder allow people to edit and view files, and upload new files to the folder.</span></span> <span data-ttu-id="9c477-134">可单独将这些文件和文件夹的权限更改为“仅查看”。</span><span class="sxs-lookup"><span data-stu-id="9c477-134">You can change these permissions for files and for folders independently to view-only.</span></span>

<span data-ttu-id="9c477-135">如果希望允许未经身份验证共享，但担心未经身份验证的人员修改组织的内容，可考虑将文件和文件夹权限设置为“**查看**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-135">If you want to allow unauthenticated sharing, but are concerned about unauthenticated people modifying your organization's content, consider setting the file and folder permissions to **View**.</span></span>

<span data-ttu-id="9c477-136">设置组织中“任何人”链接权限</span><span class="sxs-lookup"><span data-stu-id="9c477-136">To set permissions for Anyone links across the organization</span></span>

1. <span data-ttu-id="9c477-137">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="9c477-137">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="9c477-138">在左侧导航中，单击“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-138">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="9c477-139">在“**‘任何人’链接的高级设置**”下，选择要使用的文件和文件夹权限。</span><span class="sxs-lookup"><span data-stu-id="9c477-139">Under **Advanced settings for "Anyone" links**, select the file and folder permissions that you want to use.</span></span></br>
   <span data-ttu-id="9c477-140">![SharePoint 组织级别的“任何人”链接权限设置的屏幕截图](../media/sharepoint-organization-anyone-link-permissions.png)</span><span class="sxs-lookup"><span data-stu-id="9c477-140">![Screenshot of SharePoint organization-level Anyone link permissions settings](../media/sharepoint-organization-anyone-link-permissions.png)</span></span>

<span data-ttu-id="9c477-141">“*任何人*”链接设置为“**查看**”后，用户仍可与来宾共享文件和文件夹，并可使用 *特定人员* 链接为其提供编辑权限。</span><span class="sxs-lookup"><span data-stu-id="9c477-141">With *Anyone* links set to **View**, users can still share files and folders with guests and give them edit permissions by using *Specific people* links.</span></span> <span data-ttu-id="9c477-142">这些链接要求组织外人员作为来宾进行身份验证，并且你可以跟踪和审核使用这些链接共享的文件和文件夹上的来宾活动。</span><span class="sxs-lookup"><span data-stu-id="9c477-142">These links require people outside your organization to authenticate as guests, and you can track and audit guest activity on files and folders shared with these links.</span></span>

## <a name="set-default-link-type-to-only-work-for-people-in-your-organization"></a><span data-ttu-id="9c477-143">将默认链接类型设置为仅适用于组织内部人员</span><span class="sxs-lookup"><span data-stu-id="9c477-143">Set default link type to only work for people in your organization</span></span>

<span data-ttu-id="9c477-144">为组织启用 *任何人* 共享后，通常将默认共享链接设置为“**任何人**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-144">When *Anyone* sharing is enabled for your organization, the default sharing link is normally set to **Anyone**.</span></span> <span data-ttu-id="9c477-145">虽然这对用户来说非常方便，但是会增加意外的未经身份验证的共享风险。</span><span class="sxs-lookup"><span data-stu-id="9c477-145">While this can be convenient for users, it can increase the risk of unintentional unauthenticated sharing.</span></span> <span data-ttu-id="9c477-146">如果用户忘记在共享敏感文档时更改链接类型，可能会意外地创建不需要身份验证的共享链接。</span><span class="sxs-lookup"><span data-stu-id="9c477-146">If a user forgets to change the link type while sharing a sensitive document, they might accidentally create a sharing link that doesn't require authentication.</span></span>

<span data-ttu-id="9c477-147">你可以通过将默认链接设置更改为仅适用于组织内部人员的链接来降低此风险。</span><span class="sxs-lookup"><span data-stu-id="9c477-147">You can mitigate this risk by changing the default link setting to a link that only works for people inside your organization.</span></span> <span data-ttu-id="9c477-148">确实需要未经身份验证共享的用户，则必须明确选择该选项。</span><span class="sxs-lookup"><span data-stu-id="9c477-148">Users who want to share with unauthenticated people would then have to specifically select that option.</span></span>

<span data-ttu-id="9c477-149">为组织设置默认文件和文件夹共享链接</span><span class="sxs-lookup"><span data-stu-id="9c477-149">To set the default file and folder sharing link for the organization</span></span>
1. <span data-ttu-id="9c477-150">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="9c477-150">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="9c477-151">在左侧导航中，单击“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-151">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="9c477-152">在“**文件和文件夹链接**”下，选中“**仅限组织中的人员**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-152">Under **File and folder links**, select **Only people in your organization**.</span></span>

   ![SharePoint 默认链接类型设置的屏幕截图](../media/sharepoint-default-sharing-link-company-link.png)

4. <span data-ttu-id="9c477-154">单击“**保存**”</span><span class="sxs-lookup"><span data-stu-id="9c477-154">Click **Save**</span></span>

<span data-ttu-id="9c477-155">为特定站点设置默认文件和文件夹共享链接</span><span class="sxs-lookup"><span data-stu-id="9c477-155">To set the default file and folder sharing link for a specific site</span></span>
1. <span data-ttu-id="9c477-156">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="9c477-156">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="9c477-157">在左侧导航中，展开“**站点**”，然后单击“**活动站点**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-157">In the left navigation, expand **Sites**, and then click **Active sites**.</span></span>
3. <span data-ttu-id="9c477-158">选择要更改的站点，然后单击“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-158">Select the site you want to change, and then click **Sharing**.</span></span>
4. <span data-ttu-id="9c477-159">在“**默认共享链接类型**”下，清除“**与组织级别设置相同**”复选框。</span><span class="sxs-lookup"><span data-stu-id="9c477-159">Under **Default sharing link type**,  clear the **Same as organization-level setting** check box.</span></span>

   ![SharePoint 网站级默认链接类型设置的屏幕快照](../media/sharepoint-organization-anyone-link-permissions-site.png)

5. <span data-ttu-id="9c477-161">选择“**仅限组织中的人员**”选项，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-161">Select the **Only people in your organization** option and click **Save**.</span></span>

## <a name="prevent-unauthenticated-sharing-of-sensitive-content"></a><span data-ttu-id="9c477-162">阻止未经身份验证共享敏感内容</span><span class="sxs-lookup"><span data-stu-id="9c477-162">Prevent unauthenticated sharing of sensitive content</span></span>

<span data-ttu-id="9c477-163">可使用 [数据丢失防护（DLP）](../compliance/dlp-learn-about-dlp.md) 阻止未经身份验证共享敏感内容。</span><span class="sxs-lookup"><span data-stu-id="9c477-163">You can use [data loss prevention (DLP)](../compliance/dlp-learn-about-dlp.md) to prevent unauthenticated sharing of sensitive content.</span></span> <span data-ttu-id="9c477-164">数据丢失防护可以根据文件的敏感度标签、保留标签或文件本身中的敏感信息采取措施。</span><span class="sxs-lookup"><span data-stu-id="9c477-164">Data loss prevention can take action based on a file's sensitivity label, retention label, or sensitive information in the file itself.</span></span>

<span data-ttu-id="9c477-165">创建 DLP 规则</span><span class="sxs-lookup"><span data-stu-id="9c477-165">To create a DLP rule</span></span>
1. <span data-ttu-id="9c477-166">在 Microsoft 365 合规性管理中心中，转到“[数据丢失防护页面](https://compliance.microsoft.com/datalossprevention)”。</span><span class="sxs-lookup"><span data-stu-id="9c477-166">In the Microsoft 365 compliance admin center, go to the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention).</span></span>
2. <span data-ttu-id="9c477-167">单击“**创建策略**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-167">Click **Create policy**.</span></span>
3. <span data-ttu-id="9c477-168">选择“**自定义**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-168">Choose **Custom** and click **Next**.</span></span>
4. <span data-ttu-id="9c477-169">键入策略名称，并单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-169">Type a name for the policy and click **Next**.</span></span>
5. <span data-ttu-id="9c477-170">在“**要应用该策略的位置**”页面上，关闭除 “**SharePoint 网站**”和 “**OneDrive 帐户**”之外的所有设置，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-170">On the **Locations to apply the policy** page turn off all settings except **SharePoint sites** and **OneDrive accounts**, and then click **Next**.</span></span>
6. <span data-ttu-id="9c477-171">在“**定义策略设置**”页面上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-171">On the **Define policy settings** page, click **Next**.</span></span>
7. <span data-ttu-id="9c477-172">在“**自定义高级 DLP 规则**”页面上，单击“**创建规则**”并输入规则名称。</span><span class="sxs-lookup"><span data-stu-id="9c477-172">On the **Customize advanced DLP rules** page, click **Create rule** and type a name for the rule.</span></span>
8. <span data-ttu-id="9c477-173">在“**条件**”下，单击“**添加条件**”，然后选择“**内容包含**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-173">Under **Conditions**, click **Add condition**, and choose **Content contains**.</span></span>
9. <span data-ttu-id="9c477-174">单击“**添加**”，然后选择要阻止未经身份验证共享的信息类型。</span><span class="sxs-lookup"><span data-stu-id="9c477-174">Click **Add** and choose the type of information for which you want to prevent unauthenticated sharing.</span></span>

   ![条件选项、敏感信息类型、敏感度标签和保留标签的屏幕截图。](../media/limit-accidental-exposure-dlp-conditions.png)

10. <span data-ttu-id="9c477-176">在“**操作**”下，单击“**添加操作**”，然后选择“**限制访问或对 Microsoft 365 位置中的内容进行加密**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-176">Under **Actions** click **Add an action** and choose **Restrict access or encrypt the content in Microsoft 365 locations**.</span></span>
11. <span data-ttu-id="9c477-177">选中“**限制访问或对 Microsoft 365 位置中的内容进行加密**”复选框，然后选择“**仅限通过“使用此链接的任何人”选项提供内容访问权限的人员**”选项。</span><span class="sxs-lookup"><span data-stu-id="9c477-177">Select the **Restrict access or encrypt the content in Microsoft 365 locations** check box and then choose the **Only people who were given access to the content through the "Anyone withe the link" options** option.</span></span>

      ![DLP 规则操作选项屏幕截图](../media/limit-accidental-exposure-dlp-anyone-links.png)

12. <span data-ttu-id="9c477-179">单击“**保存**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-179">Click **Save** and then click **Next**.</span></span>
13. <span data-ttu-id="9c477-180">选择测试选项，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-180">Choose your test options and click **Next**.</span></span>
14. <span data-ttu-id="9c477-181">单击“**提交**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-181">Click **Submit**, and then click **Done**.</span></span>

## <a name="protect-against-malicious-files"></a><span data-ttu-id="9c477-182">防范恶意文件</span><span class="sxs-lookup"><span data-stu-id="9c477-182">Protect against malicious files</span></span>

<span data-ttu-id="9c477-183">如果允许匿名用户上传文件，可能会增加他人上载恶意文件的风险。</span><span class="sxs-lookup"><span data-stu-id="9c477-183">When you allow anonymous users to upload files, you're at an increased risk of someone uploading a malicious file.</span></span> <span data-ttu-id="9c477-184">在 Microsoft 365 中，可使用 Defender for Office 365 中的 *安全附件* 功能自动扫描上传的文件并隔离发现的不安全文件。</span><span class="sxs-lookup"><span data-stu-id="9c477-184">In Microsoft 365, you can use the *Safe Attachments* feature in Defender for Office 365 to automatically scan uploaded files and quarantine files that are found to be unsafe.</span></span>

<span data-ttu-id="9c477-185">启用安全附件</span><span class="sxs-lookup"><span data-stu-id="9c477-185">To turn on safe attachments</span></span>
1. <span data-ttu-id="9c477-186">在安全性和合规性管理中心中打开 “[ATP 安全附件页面](https://protection.office.com/safeattachmentv2)”。</span><span class="sxs-lookup"><span data-stu-id="9c477-186">Open the [ATP Safe Attachments page](https://protection.office.com/safeattachmentv2) in the Security and Compliance admin center.</span></span>
2. <span data-ttu-id="9c477-187">单击“**全局设置**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-187">Click **Global settings**.</span></span>
3. <span data-ttu-id="9c477-188">启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP。</span><span class="sxs-lookup"><span data-stu-id="9c477-188">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   ![安全与合规中心的安全附件设置的屏幕截图](../media/safe-attachments-setting.png)

4. <span data-ttu-id="9c477-190">也可以选择打开安全文档，然后单击“**保存**”</span><span class="sxs-lookup"><span data-stu-id="9c477-190">Optionally turn on Safe Documents as well, and then click **Save**</span></span>

<span data-ttu-id="9c477-191">请参阅[适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](../security/office-365-security/mdo-for-spo-odb-and-teams.md) 和[启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](../security/office-365-security/turn-on-mdo-for-spo-odb-and-teams.md) 以获取其他指导。</span><span class="sxs-lookup"><span data-stu-id="9c477-191">See [ATP for SharePoint, OneDrive, and Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](../security/office-365-security/turn-on-mdo-for-spo-odb-and-teams.md) for additional guidance.</span></span>

## <a name="add-copyright-information-to-your-files"></a><span data-ttu-id="9c477-192">将版权信息添加到文件</span><span class="sxs-lookup"><span data-stu-id="9c477-192">Add copyright information to your files</span></span>

<span data-ttu-id="9c477-193">如果在 Microsoft 365 合规管理中心使用灵敏度标签，则可以配置标签，以便自动向组织的 Office 文档添加水印或页眉/页脚。</span><span class="sxs-lookup"><span data-stu-id="9c477-193">If you use sensitivity labels in the Microsoft 365 Compliance admin center, you can configure your labels to add a watermark or a header or footer automatically to your organization's Office documents.</span></span> <span data-ttu-id="9c477-194">通过这种方法，可确保共享文件包含版权或其他所有权信息。</span><span class="sxs-lookup"><span data-stu-id="9c477-194">In this way, you can make sure that shared files contain copyright or other ownership information.</span></span>

<span data-ttu-id="9c477-195">向带标签的文件添加页脚</span><span class="sxs-lookup"><span data-stu-id="9c477-195">To add a footer to a labeled file</span></span>

1. <span data-ttu-id="9c477-196">打开 [Microsoft 365 合规管理中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="9c477-196">Open the [Microsoft 365 compliance admin center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="9c477-197">在左侧导航栏中的“**解决方案**”下，单击“**信息保护**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-197">In the left navigation, under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="9c477-198">单击要添加页脚的标签，然后单击“**编辑标签**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-198">Click the label that you want to have add a footer, and then click **Edit label**.</span></span>
4. <span data-ttu-id="9c477-199">单击“**下一步**”以进入“**内容标记**”选项卡，然后“**启用**”内容标记。</span><span class="sxs-lookup"><span data-stu-id="9c477-199">Click **Next** to reach the **Content marking** tab, and then turn **On** content marking.</span></span>
5. <span data-ttu-id="9c477-200">选中要添加的文本类型的复选框，然后单击“**自定义文本**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-200">Select the check box for the type of text you want to add, and then click **Customize text**.</span></span>
6. <span data-ttu-id="9c477-201">键入要添加到文档中的文本，选择所需的文本选项，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-201">Type the text that you want added to your documents, select the text options that you want, and then click **Save**.</span></span></br>
   <span data-ttu-id="9c477-202">![灵敏度标签的内容标记设置的屏幕截图](../media/content-marking-for-anonymous-sharing.png)</span><span class="sxs-lookup"><span data-stu-id="9c477-202">![Screenshot of the content marking settings for a sensitivity label](../media/content-marking-for-anonymous-sharing.png)</span></span>
7. <span data-ttu-id="9c477-203">单击“**下一步**”以到达向导的结尾，然后单击“**保存标签**”。</span><span class="sxs-lookup"><span data-stu-id="9c477-203">Click **Next** to reach the end of the wizard, and then click **Save label**.</span></span>

<span data-ttu-id="9c477-204">为标签启用内容标记后，用户应用该标签时，你指定的文本将添加到 Office 文档。</span><span class="sxs-lookup"><span data-stu-id="9c477-204">With content marking enabled for the label, the text you specified will be added to Office documents when a user applies that label.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c477-205">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c477-205">See Also</span></span>

[<span data-ttu-id="9c477-206">敏感度标签概述</span><span class="sxs-lookup"><span data-stu-id="9c477-206">Overview of sensitivity labels</span></span>](/Office365/SecurityCompliance/sensitivity-labels)

[<span data-ttu-id="9c477-207">与来宾共享时限制文件意外曝光</span><span class="sxs-lookup"><span data-stu-id="9c477-207">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="9c477-208">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="9c477-208">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
