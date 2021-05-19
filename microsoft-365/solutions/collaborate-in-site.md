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
recommendations: false
description: 了解设置Microsoft 365来宾协作的 SharePoint 网站所需的配置步骤。
ms.openlocfilehash: f91b9c64dbdca8ed7e3ada3315cb57f1c728f838
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539247"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="0d109-103">在网站中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="0d109-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="0d109-104">如果需要跨文档、数据和列表与来宾进行协作，可以使用SharePoint网站。</span><span class="sxs-lookup"><span data-stu-id="0d109-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="0d109-105">新式SharePoint网站连接到Microsoft 365组，可以管理网站成员身份并提供其他协作工具，如共享邮箱和日历。</span><span class="sxs-lookup"><span data-stu-id="0d109-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="0d109-106">本文将介绍设置与来宾Microsoft 365网站所需的SharePoint配置步骤。</span><span class="sxs-lookup"><span data-stu-id="0d109-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="0d109-107">视频演示</span><span class="sxs-lookup"><span data-stu-id="0d109-107">Video demonstration</span></span>

<span data-ttu-id="0d109-108">该视频展示了本文档中介绍的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="0d109-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="0d109-109">Azure 外部协作设置</span><span class="sxs-lookup"><span data-stu-id="0d109-109">Azure external collaboration settings</span></span>

<span data-ttu-id="0d109-110">Microsoft 365 中的共享在最高级别由 [Azure Active Directory 中的 B2B 外部协作设置](/azure/active-directory/external-identities/delegate-invitations) 管理。</span><span class="sxs-lookup"><span data-stu-id="0d109-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="0d109-111">如果在 Azure AD 中禁用或限制来宾共享，此设置将覆盖你在 Microsoft 365 中配置的任何共享设置。</span><span class="sxs-lookup"><span data-stu-id="0d109-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="0d109-112">检查 B2B 外部协作设置，确保不会阻止与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="0d109-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

!["外部Azure Active Directory协作设置屏幕截图](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="0d109-114">设置外部协作设置</span><span class="sxs-lookup"><span data-stu-id="0d109-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="0d109-115">在 [https://aad.portal.azure.com](https://aad.portal.azure.com) 上登录到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="0d109-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="0d109-116">在左侧导航窗格中，单击 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="0d109-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="0d109-117">单击 **“外部标识”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-117">Click **External identities**.</span></span>
4. <span data-ttu-id="0d109-118">在 **“入门”** 屏幕的左侧导航窗格中，单击 **“外部协作设置”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="0d109-119">确保 **“管理员和来宾邀请者角色中的用户可以邀请”**，且 **“成员可以邀请”** 同时设置为 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="0d109-120">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="0d109-121">请注意 **“协作限制"** 部分的设置。</span><span class="sxs-lookup"><span data-stu-id="0d109-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="0d109-122">确保不会阻止要协作来宾的域。</span><span class="sxs-lookup"><span data-stu-id="0d109-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="0d109-123">如果与多个组织的来宾合作，可能需要限制其访问目录数据的能力。 </span><span class="sxs-lookup"><span data-stu-id="0d109-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="0d109-124">这将阻止他们查看目录中的来宾。</span><span class="sxs-lookup"><span data-stu-id="0d109-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="0d109-125">为此，在 **“来宾用户访问限制”** 下，选择 **“来宾用户具有对目录对象设置的属性和成员身份的有限访问权限”** 或 **“来宾用户访问仅限于其自己的目录对象的属性和成员身份”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="0d109-126">Microsoft 365 组来宾设置</span><span class="sxs-lookup"><span data-stu-id="0d109-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="0d109-127">新式SharePoint网站使用Microsoft 365组来控制网站访问。</span><span class="sxs-lookup"><span data-stu-id="0d109-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="0d109-128">必须Microsoft 365组来宾设置，才能在网站中访问SharePoint来宾访问。</span><span class="sxs-lookup"><span data-stu-id="0d109-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Microsoft 365 管理中心中的 Microsoft 365 组来宾设置的屏幕截图](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="0d109-130">设置 Microsoft 365 组来宾设置</span><span class="sxs-lookup"><span data-stu-id="0d109-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="0d109-131">在 Microsoft 365 管理中心左侧导航窗格中，展开 **“设置”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="0d109-132">单击 **“组织设置”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="0d109-133">在列表中，单击 **“Microsoft 365 组”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="0d109-134">确保复选框 **允许组所有者将组织外部人员作为来宾添加到 Microsoft 365 组** 和 **允许来宾组成员访问组内容** 都已选中。</span><span class="sxs-lookup"><span data-stu-id="0d109-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="0d109-135">如果进行了更改，请单击 **“保存更改”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="0d109-136">SharePoint组织级别的共享设置</span><span class="sxs-lookup"><span data-stu-id="0d109-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="0d109-137">若要使来宾能够访问SharePoint网站，SharePoint级别共享设置必须允许与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="0d109-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="0d109-138">组织级别设置确定将可用于各个网站的设置。</span><span class="sxs-lookup"><span data-stu-id="0d109-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="0d109-139">网站设置不能比组织级别设置更宽松。</span><span class="sxs-lookup"><span data-stu-id="0d109-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="0d109-140">如果要允许未经身份验证的文件和文件夹共享，请选择"任何人 **"。**</span><span class="sxs-lookup"><span data-stu-id="0d109-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="0d109-141">如果希望确保组织外部的所有人员均必须进行身份验证，请选择"**新来宾和现有来宾"。**</span><span class="sxs-lookup"><span data-stu-id="0d109-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="0d109-142">选择组织中任何网站所需的最宽松设置。</span><span class="sxs-lookup"><span data-stu-id="0d109-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 组织级别共享设置的屏幕截图](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="0d109-144">设置 SharePoint 组织级共享设置</span><span class="sxs-lookup"><span data-stu-id="0d109-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="0d109-145">在 Microsoft 365 管理中心左侧导航窗格中的 **“管理中心”** 下，单击 **“SharePoint”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="0d109-146">In the SharePoint admin center， in the left navigation pane， under **Policies**， click **Sharing**.</span><span class="sxs-lookup"><span data-stu-id="0d109-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="0d109-147">确保 SharePoint 的外部共享设置为 **“任何人”** 或 **“新来宾和现有来宾”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="0d109-148">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="0d109-149">创建网站</span><span class="sxs-lookup"><span data-stu-id="0d109-149">Create a site</span></span>

<span data-ttu-id="0d109-150">下一步是创建计划用于与来宾协作的网站。</span><span class="sxs-lookup"><span data-stu-id="0d109-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="0d109-151">创建网站</span><span class="sxs-lookup"><span data-stu-id="0d109-151">To create a site</span></span>
1. <span data-ttu-id="0d109-152">在 SharePoint 管理中心中的“**网站**”下，单击“**活动站点**”。</span><span class="sxs-lookup"><span data-stu-id="0d109-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="0d109-153">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="0d109-153">Click **Create**.</span></span>
3. <span data-ttu-id="0d109-154">单击 **"团队网站"。**</span><span class="sxs-lookup"><span data-stu-id="0d109-154">Click **Team site**.</span></span>
4. <span data-ttu-id="0d109-155">键入网站名称，然后输入组所有者名称 (网站所有者) 。</span><span class="sxs-lookup"><span data-stu-id="0d109-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="0d109-156">在 **"高级设置**"下，选择是希望此网站是公共网站还是专用网站。</span><span class="sxs-lookup"><span data-stu-id="0d109-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="0d109-157">单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="0d109-157">Click **Next**.</span></span>
7. <span data-ttu-id="0d109-158">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="0d109-158">Click **Finish**.</span></span>

<span data-ttu-id="0d109-159">我们稍后将邀请用户。</span><span class="sxs-lookup"><span data-stu-id="0d109-159">We'll invite users later.</span></span> <span data-ttu-id="0d109-160">接下来，检查此网站的网站级别共享设置非常重要。</span><span class="sxs-lookup"><span data-stu-id="0d109-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="0d109-161">SharePoint 网站级别共享设置</span><span class="sxs-lookup"><span data-stu-id="0d109-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="0d109-162">检查网站级别的共享设置，以确保这些设置允许您希望用于此网站的访问类型。</span><span class="sxs-lookup"><span data-stu-id="0d109-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="0d109-163">例如，如果将组织级别设置设置为"任何人"，但希望所有来宾对此网站进行身份验证，请确保网站级别共享设置设置为"新来宾和现有来宾 **"。**</span><span class="sxs-lookup"><span data-stu-id="0d109-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="0d109-164">请注意，该网站无法与"任何人"设置 (未经身份验证) ，但单个文件和文件夹可以共享。</span><span class="sxs-lookup"><span data-stu-id="0d109-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="0d109-165">您还可以使用[敏感度标签来控制网站的外部SharePoint设置](../compliance/sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="0d109-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

![SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="0d109-167">设置网站级别共享设置</span><span class="sxs-lookup"><span data-stu-id="0d109-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="0d109-168">在 SharePoint 管理中心的左侧导航栏中，展开 **“站点”**，然后单击 **“活动站点”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="0d109-169">选择要共享的网站。</span><span class="sxs-lookup"><span data-stu-id="0d109-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="0d109-170">单击"..."，然后单击"**共享"。**</span><span class="sxs-lookup"><span data-stu-id="0d109-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="0d109-171">确保将共享设置为 **“任何人”** 或 **“新来宾和现有来宾”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="0d109-172">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="0d109-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="0d109-173">邀请用户</span><span class="sxs-lookup"><span data-stu-id="0d109-173">Invite users</span></span>

<span data-ttu-id="0d109-174">来宾共享设置现已配置，因此你可以开始向网站添加内部用户和来宾。</span><span class="sxs-lookup"><span data-stu-id="0d109-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="0d109-175">网站访问通过关联的组Microsoft 365，因此我们将在那里添加用户。</span><span class="sxs-lookup"><span data-stu-id="0d109-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="0d109-176">邀请内部用户加入组</span><span class="sxs-lookup"><span data-stu-id="0d109-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="0d109-177">导航到要添加用户的网站。</span><span class="sxs-lookup"><span data-stu-id="0d109-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="0d109-178">单击 **右上角** 的"成员"链接，该链接表示成员计数。</span><span class="sxs-lookup"><span data-stu-id="0d109-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="0d109-179">单击“**添加成员**”。</span><span class="sxs-lookup"><span data-stu-id="0d109-179">Click **Add members**.</span></span>
4. <span data-ttu-id="0d109-180">键入要邀请到网站的用户的姓名或电子邮件地址，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="0d109-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="0d109-181">无法从网站添加来宾。</span><span class="sxs-lookup"><span data-stu-id="0d109-181">Guests can't be added from the site.</span></span> <span data-ttu-id="0d109-182">你需要使用 Web 上的Outlook添加它们。</span><span class="sxs-lookup"><span data-stu-id="0d109-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="0d109-183">因此，作为添加来宾并邀请来宾加入组的先决条件，请单击"URL"列中网站的 **URL**  以导航到特定于网站的页面。</span><span class="sxs-lookup"><span data-stu-id="0d109-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="0d109-184">从此页中，单击 **应用启动器** 图标并选择"Outlook"。 </span><span class="sxs-lookup"><span data-stu-id="0d109-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="0d109-185">这是你可以从其中邀请来宾加入组的屏幕，此过程如下所述。</span><span class="sxs-lookup"><span data-stu-id="0d109-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="0d109-186">邀请来宾加入组</span><span class="sxs-lookup"><span data-stu-id="0d109-186">To invite guests to a group</span></span>
1. <span data-ttu-id="0d109-187">在 **"** 组"下，单击要邀请来宾的组。</span><span class="sxs-lookup"><span data-stu-id="0d109-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="0d109-188">打开组联系人卡片，单击右上角的"成员"链接 (表示成员计数) 。</span><span class="sxs-lookup"><span data-stu-id="0d109-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="0d109-189">单击 **"添加成员"。**</span><span class="sxs-lookup"><span data-stu-id="0d109-189">click **Add members**.</span></span>
4. <span data-ttu-id="0d109-190">键入要邀请的来宾的电子邮件地址，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="0d109-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="0d109-191">单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="0d109-191">Click **Close**.</span></span>
<span data-ttu-id="0d109-192">请注意，只有不是 **组所有者时** ，才需要单击"关闭"，因此，不允许将来宾添加到组中。</span><span class="sxs-lookup"><span data-stu-id="0d109-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="0d109-193">在这种情况下，将来宾添加到组的请求将传输给组所有者进行审批。</span><span class="sxs-lookup"><span data-stu-id="0d109-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d109-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d109-194">See also</span></span>

[<span data-ttu-id="0d109-195">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="0d109-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="0d109-196">与来宾共享时限制文件意外曝光</span><span class="sxs-lookup"><span data-stu-id="0d109-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

<span data-ttu-id="0d109-197">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md)（创建安全的来宾共享环境）</span><span class="sxs-lookup"><span data-stu-id="0d109-197">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md)</span></span>

[<span data-ttu-id="0d109-198">创建有托管来宾的 B2B 外网</span><span class="sxs-lookup"><span data-stu-id="0d109-198">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="0d109-199">SharePoint 和 OneDrive 与 Azure AD B2B 的集成</span><span class="sxs-lookup"><span data-stu-id="0d109-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)