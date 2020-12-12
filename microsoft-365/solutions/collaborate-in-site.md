---
title: 在网站中与来宾协作
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
localization_priority: Normal
f1.keywords: NOCSH
description: 了解设置 SharePoint 网站以与来宾协作所需的 Microsoft 365 配置步骤。
ms.openlocfilehash: 6862fe715fe2f19b968b773bc6df6c70c207a44f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663520"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="11ada-103">在网站中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="11ada-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="11ada-104">如果需要跨文档、数据和列表与来宾进行协作，可以使用 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="11ada-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="11ada-105">新式 SharePoint 网站连接到 Microsoft 365 组，可以管理网站成员身份并提供其他协作工具，如共享邮箱和日历。</span><span class="sxs-lookup"><span data-stu-id="11ada-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="11ada-106">本文将介绍设置 SharePoint 网站以与来宾协作所需的 Microsoft 365 配置步骤。</span><span class="sxs-lookup"><span data-stu-id="11ada-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="11ada-107">视频演示</span><span class="sxs-lookup"><span data-stu-id="11ada-107">Video demonstration</span></span>

<span data-ttu-id="11ada-108">此视频演示本文档中所述的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="11ada-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="11ada-109">Azure 外部协作设置</span><span class="sxs-lookup"><span data-stu-id="11ada-109">Azure external collaboration settings</span></span>

<span data-ttu-id="11ada-110">Microsoft 365 中的共享由 Azure Active Directory 中的 [B2B](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)外部协作设置在最高级别管理。</span><span class="sxs-lookup"><span data-stu-id="11ada-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="11ada-111">如果在 Azure AD 中禁用或限制来宾共享，此设置将覆盖你在 Microsoft 365 中配置的任何共享设置。</span><span class="sxs-lookup"><span data-stu-id="11ada-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="11ada-112">检查 B2B 外部协作设置以确保不会阻止与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="11ada-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 外部协作设置页的屏幕截图](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="11ada-114">设置外部协作设置</span><span class="sxs-lookup"><span data-stu-id="11ada-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="11ada-115">登录 Azure Active [https://aad.portal.azure.com](https://aad.portal.azure.com) Directory。</span><span class="sxs-lookup"><span data-stu-id="11ada-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="11ada-116">在左侧导航窗格中，单击 **Azure Active Directory。**</span><span class="sxs-lookup"><span data-stu-id="11ada-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="11ada-117">单击 **"外部标识"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-117">Click **External identities**.</span></span>
4. <span data-ttu-id="11ada-118">在 **"入门"** 屏幕的左侧导航窗格中，单击 **"外部协作设置"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="11ada-119">确保 **管理员和来宾邀请** 者角色中的用户可以邀请，**并且成员可以邀请** 都设置为 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="11ada-120">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="11ada-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="11ada-121">记下"协作限制 **"部分** 中的设置。</span><span class="sxs-lookup"><span data-stu-id="11ada-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="11ada-122">确保未阻止要协作的来宾的域。</span><span class="sxs-lookup"><span data-stu-id="11ada-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="11ada-123">如果与多个组织的来宾合作，可能需要限制其访问目录数据的能力。</span><span class="sxs-lookup"><span data-stu-id="11ada-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="11ada-124">这将阻止他们查看目录中的来宾。</span><span class="sxs-lookup"><span data-stu-id="11ada-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="11ada-125">为此，在"来宾用户访问限制"下，选择"来宾用户对目录对象设置的属性和成员身份具有有限访问权限"或"来宾"用户访问仅限于其自己的目录对象的属性和 **成员身份**。</span><span class="sxs-lookup"><span data-stu-id="11ada-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="11ada-126">Microsoft 365 组来宾设置</span><span class="sxs-lookup"><span data-stu-id="11ada-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="11ada-127">新式 SharePoint 网站使用 Microsoft 365 组来控制网站访问。</span><span class="sxs-lookup"><span data-stu-id="11ada-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="11ada-128">必须打开 Microsoft 365 组来宾设置，SharePoint 网站中的来宾访问才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="11ada-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Microsoft 365 管理中心中的 Microsoft 365 组来宾设置的屏幕截图](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="11ada-130">设置 Microsoft 365 组来宾设置</span><span class="sxs-lookup"><span data-stu-id="11ada-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="11ada-131">在 Microsoft 365 管理中心的左侧导航窗格中，展开"**设置"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="11ada-132">单击 **"组织设置"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="11ada-133">在列表中，单击 **"Microsoft 365 组"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="11ada-134">确保允许组所有者将组织外部人员作为来宾添加到 **Microsoft 365** 组，同时选中"允许 **来宾** 组成员访问组内容"复选框。</span><span class="sxs-lookup"><span data-stu-id="11ada-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="11ada-135">如果进行了更改，请单击"**保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="11ada-136">SharePoint 组织级共享设置</span><span class="sxs-lookup"><span data-stu-id="11ada-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="11ada-137">若要使来宾能够访问 SharePoint 网站，SharePoint 组织级共享设置必须允许与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="11ada-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="11ada-138">组织级别的设置确定将可用于各个网站的设置。</span><span class="sxs-lookup"><span data-stu-id="11ada-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="11ada-139">网站设置不能比组织级别的设置更宽松。</span><span class="sxs-lookup"><span data-stu-id="11ada-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="11ada-140">如果要允许未经身份验证的文件和文件夹共享，请选择"任何人 **"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="11ada-141">如果要确保组织外部的所有人员均必须进行身份验证，请选择 **"新来宾"和"现有来宾"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="11ada-142">选择组织中任何网站所需的最宽松设置。</span><span class="sxs-lookup"><span data-stu-id="11ada-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 组织级别共享设置的屏幕截图](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="11ada-144">设置 SharePoint 组织级共享设置</span><span class="sxs-lookup"><span data-stu-id="11ada-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="11ada-145">在 Microsoft 365 管理中心左侧导航窗格中的"管理中心"下，单击 **"SharePoint"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="11ada-146">在 SharePoint 管理中心的左侧导航窗格中，**在"策略**"下，单击"**共享"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="11ada-147">确保 SharePoint 的外部共享设置为"任何人 **"** 或"**新来宾"和"现有来宾"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="11ada-148">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="11ada-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="11ada-149">创建网站</span><span class="sxs-lookup"><span data-stu-id="11ada-149">Create a site</span></span>

<span data-ttu-id="11ada-150">下一步是创建计划用于与来宾协作的网站。</span><span class="sxs-lookup"><span data-stu-id="11ada-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="11ada-151">创建网站</span><span class="sxs-lookup"><span data-stu-id="11ada-151">To create a site</span></span>
1. <span data-ttu-id="11ada-152">在 SharePoint 管理中心中的“**网站**”下，单击“**活动站点**”。</span><span class="sxs-lookup"><span data-stu-id="11ada-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="11ada-153">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="11ada-153">Click **Create**.</span></span>
3. <span data-ttu-id="11ada-154">单击 **"团队网站"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-154">Click **Team site**.</span></span>
4. <span data-ttu-id="11ada-155">键入网站名称，然后输入组所有者的名称 (网站所有者) 。</span><span class="sxs-lookup"><span data-stu-id="11ada-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="11ada-156">在 **"高级** 设置"下，选择是希望此网站是公共网站还是专用网站。</span><span class="sxs-lookup"><span data-stu-id="11ada-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="11ada-157">单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="11ada-157">Click **Next**.</span></span>
7. <span data-ttu-id="11ada-158">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="11ada-158">Click **Finish**.</span></span>

<span data-ttu-id="11ada-159">我们稍后将邀请用户。</span><span class="sxs-lookup"><span data-stu-id="11ada-159">We'll invite users later.</span></span> <span data-ttu-id="11ada-160">接下来，检查此网站的网站级别共享设置非常重要。</span><span class="sxs-lookup"><span data-stu-id="11ada-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="11ada-161">SharePoint 网站级共享设置</span><span class="sxs-lookup"><span data-stu-id="11ada-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="11ada-162">检查网站级别的共享设置，以确保这些设置允许此网站访问的类型。</span><span class="sxs-lookup"><span data-stu-id="11ada-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="11ada-163">例如，如果将组织级别设置设置为"任何人"，但希望所有来宾对此网站进行身份验证，请确保网站级别共享设置设置为"新建"和"现有来宾 **"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="11ada-164">请注意，网站无法与未通过身份验证 (**任何人** 进行) ，但单个文件和文件夹可以。</span><span class="sxs-lookup"><span data-stu-id="11ada-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="11ada-165">您还可以使用敏感度标签 [来控制 SharePoint 网站的外部共享设置](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="11ada-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

![SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="11ada-167">设置网站级共享设置</span><span class="sxs-lookup"><span data-stu-id="11ada-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="11ada-168">在 SharePoint 管理中心的左侧导航栏中，展开 **“站点”**，然后单击 **“活动站点”**。</span><span class="sxs-lookup"><span data-stu-id="11ada-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="11ada-169">选择要共享的网站。</span><span class="sxs-lookup"><span data-stu-id="11ada-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="11ada-170">单击...，然后单击"**共享"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="11ada-171">确保共享设置为"任何人 **"或\*\*\*\*"新来宾"和"现有来宾"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="11ada-172">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="11ada-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="11ada-173">邀请用户</span><span class="sxs-lookup"><span data-stu-id="11ada-173">Invite users</span></span>

<span data-ttu-id="11ada-174">现在配置了来宾共享设置，因此您可以开始向网站添加内部用户和来宾。</span><span class="sxs-lookup"><span data-stu-id="11ada-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="11ada-175">网站访问通过关联的 Microsoft 365 组进行控制，因此我们将在那里添加用户。</span><span class="sxs-lookup"><span data-stu-id="11ada-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="11ada-176">邀请内部用户加入组</span><span class="sxs-lookup"><span data-stu-id="11ada-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="11ada-177">导航到要添加用户的网站。</span><span class="sxs-lookup"><span data-stu-id="11ada-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="11ada-178">单击 **表示** 成员计数的右上角的"成员"链接。</span><span class="sxs-lookup"><span data-stu-id="11ada-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="11ada-179">单击“**添加成员**”。</span><span class="sxs-lookup"><span data-stu-id="11ada-179">Click **Add members**.</span></span>
4. <span data-ttu-id="11ada-180">键入要邀请到网站的用户的名称或电子邮件地址，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="11ada-181">无法从网站添加来宾。</span><span class="sxs-lookup"><span data-stu-id="11ada-181">Guests can't be added from the site.</span></span> <span data-ttu-id="11ada-182">你需要使用 Web 上的 Outlook 添加它们。</span><span class="sxs-lookup"><span data-stu-id="11ada-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="11ada-183">因此，作为添加来宾并邀请来宾加入组的先决条件，请单击 URL 列中网站的 **URL**  以导航到特定于网站的页面。</span><span class="sxs-lookup"><span data-stu-id="11ada-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="11ada-184">在此页中，单击 **应用启动器** 图标并选择 **Outlook。**</span><span class="sxs-lookup"><span data-stu-id="11ada-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="11ada-185">这是你可以从其中邀请来宾加入组的屏幕，此过程如下所述。</span><span class="sxs-lookup"><span data-stu-id="11ada-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="11ada-186">邀请来宾加入组</span><span class="sxs-lookup"><span data-stu-id="11ada-186">To invite guests to a group</span></span>
1. <span data-ttu-id="11ada-187">在 **"** 组"下，单击要邀请来宾的组。</span><span class="sxs-lookup"><span data-stu-id="11ada-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="11ada-188">打开组联系人卡片，单击右上角的"成员"链接 (表示成员计数) 。</span><span class="sxs-lookup"><span data-stu-id="11ada-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="11ada-189">单击 **"添加成员"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-189">click **Add members**.</span></span>
4. <span data-ttu-id="11ada-190">键入要邀请的来宾的电子邮件地址，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="11ada-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="11ada-191">单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="11ada-191">Click **Close**.</span></span>
<span data-ttu-id="11ada-192">请注意，仅当您不是组 **的所有者时** ，才需要单击"关闭"，因此，不允许将来宾添加到组中。</span><span class="sxs-lookup"><span data-stu-id="11ada-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="11ada-193">在这种情况下，将来宾添加到组的请求将转移给组所有者进行审批。</span><span class="sxs-lookup"><span data-stu-id="11ada-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="11ada-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11ada-194">See also</span></span>

[<span data-ttu-id="11ada-195">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="11ada-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="11ada-196">与来宾共享时限制文件意外曝光</span><span class="sxs-lookup"><span data-stu-id="11ada-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="11ada-197">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="11ada-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="11ada-198">创建托管有来宾的 B2B 外联网</span><span class="sxs-lookup"><span data-stu-id="11ada-198">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="11ada-199">SharePoint 和 OneDrive 与 Azure AD B2B 集成</span><span class="sxs-lookup"><span data-stu-id="11ada-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
