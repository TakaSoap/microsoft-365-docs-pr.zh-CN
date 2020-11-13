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
description: 了解设置 SharePoint 网站以与来宾进行协作所需的 Microsoft 365 配置步骤。
ms.openlocfilehash: df9068ef4b4eb35f946b78d8f7fefa01c254c79c
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49029989"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="a9f77-103">在网站中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="a9f77-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="a9f77-104">如果需要在文档、数据和列表之间与来宾进行协作，则可以使用 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="a9f77-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="a9f77-105">新式 SharePoint 网站连接到 Microsoft 365 组，并且可以管理网站成员身份并提供其他协作工具（如共享邮箱和日历）。</span><span class="sxs-lookup"><span data-stu-id="a9f77-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="a9f77-106">在本文中，我们将逐步完成为与来宾协作设置 SharePoint 网站所必需的 Microsoft 365 配置步骤。</span><span class="sxs-lookup"><span data-stu-id="a9f77-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="a9f77-107">视频演示</span><span class="sxs-lookup"><span data-stu-id="a9f77-107">Video demonstration</span></span>

<span data-ttu-id="a9f77-108">该视频显示了本文档中描述的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="a9f77-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="a9f77-109">Azure 外部协作设置</span><span class="sxs-lookup"><span data-stu-id="a9f77-109">Azure external collaboration settings</span></span>

<span data-ttu-id="a9f77-110">Microsoft 365 中的共享受 [Azure Active Directory 中的组织关系设置](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)的最高级别的管辖。</span><span class="sxs-lookup"><span data-stu-id="a9f77-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="a9f77-111">如果在 Azure AD 中禁用或限制来宾共享，此设置将覆盖您在 Microsoft 365 中配置的任何共享设置。</span><span class="sxs-lookup"><span data-stu-id="a9f77-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="a9f77-112">检查外部协作设置以确保不会阻止与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="a9f77-112">Check the external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 外部协作设置页面的屏幕截图](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="a9f77-114">设置外部协作设置</span><span class="sxs-lookup"><span data-stu-id="a9f77-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="a9f77-115">在上登录到 Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="a9f77-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="a9f77-116">在左侧导航窗格中，单击 " **Azure Active Directory** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="a9f77-117">单击 " **外部标识** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-117">Click **External identities**.</span></span>
4. <span data-ttu-id="a9f77-118">在 " **开始** " 屏幕的左侧导航窗格中，单击 " **外部协作设置** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="a9f77-119">确保 **来宾邀请者角色中的管理员和用户可以邀请** 和 **成员** 都可以邀请都设置为 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="a9f77-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="a9f77-120">如果进行了任何更改，请单击 **“保存”** 。</span><span class="sxs-lookup"><span data-stu-id="a9f77-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="a9f77-121">请注意 " **协作限制** " 部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="a9f77-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="a9f77-122">确保不会阻止您要与之进行协作的来宾域。</span><span class="sxs-lookup"><span data-stu-id="a9f77-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="a9f77-123">如果您使用多个组织的来宾，您可能希望限制其访问目录数据的能力。</span><span class="sxs-lookup"><span data-stu-id="a9f77-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="a9f77-124">这将阻止他们看到目录中的其他人是来宾。</span><span class="sxs-lookup"><span data-stu-id="a9f77-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="a9f77-125">若要执行此操作，请在 " **来宾用户访问限制** " 下，选择 " **来宾用户对属性和目录对象的成员身份的访问权限受到限制** "，并且 **来宾用户访问仅限于其自己的目录对象的属性和成员身份** 。</span><span class="sxs-lookup"><span data-stu-id="a9f77-125">To do this, under **Guest user access restrictions** , select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="a9f77-126">Microsoft 365 组来宾设置</span><span class="sxs-lookup"><span data-stu-id="a9f77-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="a9f77-127">新式 SharePoint 网站使用 Microsoft 365 组来控制网站访问。</span><span class="sxs-lookup"><span data-stu-id="a9f77-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="a9f77-128">必须打开 Microsoft 365 组来宾设置，才能使 SharePoint 网站中的来宾访问能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="a9f77-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Microsoft 365 管理中心中的 Microsoft 365 组来宾设置的屏幕截图](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="a9f77-130">设置 Microsoft 365 组来宾设置</span><span class="sxs-lookup"><span data-stu-id="a9f77-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="a9f77-131">在 Microsoft 365 管理中心的左侧导航窗格中，展开 " **设置** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="a9f77-132">单击 " **组织设置** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="a9f77-133">在列表中，单击 " **Microsoft 365 组** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="a9f77-134">确保选中 " **允许组所有者将组织外部的人员添加为 Microsoft 365 组** " 和 " **允许来宾组成员访问组内容** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="a9f77-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="a9f77-135">如果进行了更改，请单击 " **保存更改** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="a9f77-136">SharePoint 组织级别的共享设置</span><span class="sxs-lookup"><span data-stu-id="a9f77-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="a9f77-137">为使来宾能够访问 SharePoint 网站，SharePoint 组织级别的共享设置必须允许与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="a9f77-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="a9f77-138">组织级别设置确定将对单个网站可用的设置。</span><span class="sxs-lookup"><span data-stu-id="a9f77-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="a9f77-139">网站设置不能比组织级别设置更具有更好的许可。</span><span class="sxs-lookup"><span data-stu-id="a9f77-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="a9f77-140">如果要允许未经身份验证的文件和文件夹共享，请选择 " **任何人** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="a9f77-141">如果要确保组织外部的所有人员都必须进行身份验证，请选择 " **新建" 和 "现有来宾** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="a9f77-142">选择组织中的任何网站将需要的 "最高" 设置。</span><span class="sxs-lookup"><span data-stu-id="a9f77-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 组织级别共享设置的屏幕截图](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="a9f77-144">设置 SharePoint 组织级别的共享设置</span><span class="sxs-lookup"><span data-stu-id="a9f77-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="a9f77-145">在 Microsoft 365 管理中心的左侧导航窗格中，单击 " **管理中心** " 下的 " **SharePoint** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers** , click **SharePoint**.</span></span>
2. <span data-ttu-id="a9f77-146">在 SharePoint 管理中心中，在左侧导航窗格中的 " **策略** " 下，单击 " **共享** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-146">In the SharePoint admin center, in the left navigation pane, under **Policies** , click **Sharing**.</span></span>
3. <span data-ttu-id="a9f77-147">确保将 SharePoint 的 "外部共享" 设置为 " **任何人** " 或 " **新的和现有的来宾** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="a9f77-148">如果进行了任何更改，请单击 **“保存”** 。</span><span class="sxs-lookup"><span data-stu-id="a9f77-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="a9f77-149">创建网站</span><span class="sxs-lookup"><span data-stu-id="a9f77-149">Create a site</span></span>

<span data-ttu-id="a9f77-150">下一步是创建您计划用于与来宾协作的网站。</span><span class="sxs-lookup"><span data-stu-id="a9f77-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="a9f77-151">创建网站</span><span class="sxs-lookup"><span data-stu-id="a9f77-151">To create a site</span></span>
1. <span data-ttu-id="a9f77-152">在 SharePoint 管理中心中的“ **网站** ”下，单击“ **活动站点** ”。</span><span class="sxs-lookup"><span data-stu-id="a9f77-152">In the SharePoint admin center, under **Sites** , click **Active sites**.</span></span>
2. <span data-ttu-id="a9f77-153">单击“ **创建** ”。</span><span class="sxs-lookup"><span data-stu-id="a9f77-153">Click **Create**.</span></span>
3. <span data-ttu-id="a9f77-154">单击 " **团队网站** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-154">Click **Team site**.</span></span>
4. <span data-ttu-id="a9f77-155">键入网站名称，并为组所有者 (网站所有者) 输入名称。</span><span class="sxs-lookup"><span data-stu-id="a9f77-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="a9f77-156">在 " **高级设置** " 下，选择要将此网站设为公共网站还是专用网站。</span><span class="sxs-lookup"><span data-stu-id="a9f77-156">Under **Advanced settings** , choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="a9f77-157">单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="a9f77-157">Click **Next**.</span></span>
7. <span data-ttu-id="a9f77-158">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="a9f77-158">Click **Finish**.</span></span>

<span data-ttu-id="a9f77-159">我们将稍后邀请用户。</span><span class="sxs-lookup"><span data-stu-id="a9f77-159">We'll invite users later.</span></span> <span data-ttu-id="a9f77-160">接下来，请务必检查此网站的网站级共享设置。</span><span class="sxs-lookup"><span data-stu-id="a9f77-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="a9f77-161">SharePoint 网站级别的共享设置</span><span class="sxs-lookup"><span data-stu-id="a9f77-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="a9f77-162">检查网站级别的共享设置以确保它们允许您对此网站所需的访问类型。</span><span class="sxs-lookup"><span data-stu-id="a9f77-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="a9f77-163">例如，如果将组织级别设置设置为 " **任何人** "，但希望所有来宾都对此网站进行身份验证，请确保将网站级别的共享设置设置为 " **新建" 和 "现有来宾** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-163">For example, if you set the organization-level settings to **Anyone** , but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="a9f77-164">请注意，不能将网站与未经身份验证的人员共享 ( **任何人** 设置) ，但可以使用各个文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="a9f77-164">Note that the site cannot be shared with unauthenticated people ( **Anyone** setting), but individual files and folders can.</span></span>

![SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="a9f77-166">设置网站级共享设置</span><span class="sxs-lookup"><span data-stu-id="a9f77-166">To set site-level sharing settings</span></span>
1. <span data-ttu-id="a9f77-167">在 SharePoint 管理中心的左侧导航栏中，展开 **“站点”** ，然后单击 **“活动站点”** 。</span><span class="sxs-lookup"><span data-stu-id="a9f77-167">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="a9f77-168">选择要共享的网站。</span><span class="sxs-lookup"><span data-stu-id="a9f77-168">Select the site that you want to share.</span></span>
3. <span data-ttu-id="a9f77-169">单击 "..."，然后单击 " **共享** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-169">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="a9f77-170">确保将 "共享" 设置为 " **任何人** " 或 " **新的和现有的来宾** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-170">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="a9f77-171">如果进行了任何更改，请单击 **“保存”** 。</span><span class="sxs-lookup"><span data-stu-id="a9f77-171">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="a9f77-172">邀请用户</span><span class="sxs-lookup"><span data-stu-id="a9f77-172">Invite users</span></span>

<span data-ttu-id="a9f77-173">现在已配置来宾共享设置，因此您可以开始向网站添加内部用户和来宾。</span><span class="sxs-lookup"><span data-stu-id="a9f77-173">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="a9f77-174">网站访问通过关联的 Microsoft 365 组进行控制，因此我们将在此处添加用户。</span><span class="sxs-lookup"><span data-stu-id="a9f77-174">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="a9f77-175">向组邀请内部用户</span><span class="sxs-lookup"><span data-stu-id="a9f77-175">To invite internal users to a group</span></span>
1. <span data-ttu-id="a9f77-176">导航到要在其中添加用户的网站。</span><span class="sxs-lookup"><span data-stu-id="a9f77-176">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="a9f77-177">单击右上角表示成员计数的 " **成员** " 链接。</span><span class="sxs-lookup"><span data-stu-id="a9f77-177">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="a9f77-178">单击“ **添加成员** ”。</span><span class="sxs-lookup"><span data-stu-id="a9f77-178">Click **Add members**.</span></span>
4. <span data-ttu-id="a9f77-179">键入要邀请到网站的用户的名称或电子邮件地址，然后单击 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-179">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="a9f77-180">无法从网站添加来宾用户。</span><span class="sxs-lookup"><span data-stu-id="a9f77-180">Guest users can't be added from the site.</span></span> <span data-ttu-id="a9f77-181">您需要在 web 上使用 Outlook 添加它们。</span><span class="sxs-lookup"><span data-stu-id="a9f77-181">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="a9f77-182">因此，作为向组添加和邀请来宾的先决条件，可在 " **URL**  " 列中单击网站的 url 以导航到特定于站点的页面。</span><span class="sxs-lookup"><span data-stu-id="a9f77-182">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="a9f77-183">在此页面中，单击 **应用启动器** 图标，然后选择 " **Outlook** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-183">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="a9f77-184">在此屏幕中，可以将来宾邀请到组中，具体步骤如下所述。</span><span class="sxs-lookup"><span data-stu-id="a9f77-184">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="a9f77-185">将来宾邀请到组</span><span class="sxs-lookup"><span data-stu-id="a9f77-185">To invite guests to a group</span></span>
1. <span data-ttu-id="a9f77-186">在 " **组** " 下，单击要邀请其来宾的组。</span><span class="sxs-lookup"><span data-stu-id="a9f77-186">Under **Groups** , click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="a9f77-187">打开 "组联系人卡片"，单击右上方的 " **成员** " 链接 (表示成员计数) 的链接。</span><span class="sxs-lookup"><span data-stu-id="a9f77-187">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="a9f77-188">单击 " **添加成员** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-188">click **Add members**.</span></span>
4. <span data-ttu-id="a9f77-189">键入要邀请的来宾的电子邮件地址，然后单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="a9f77-189">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="a9f77-190">单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="a9f77-190">Click **Close**.</span></span>
<span data-ttu-id="a9f77-191">请注意，仅当您不是组的所有者时，才需要单击 " **关闭** "，因此，不允许将来宾添加到组中。</span><span class="sxs-lookup"><span data-stu-id="a9f77-191">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="a9f77-192">在这种情况下，将来宾添加到组中的请求将转移到组所有者以供审批。</span><span class="sxs-lookup"><span data-stu-id="a9f77-192">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9f77-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9f77-193">See also</span></span>

[<span data-ttu-id="a9f77-194">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="a9f77-194">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="a9f77-195">与来宾共享时限制文件意外曝光</span><span class="sxs-lookup"><span data-stu-id="a9f77-195">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

<span data-ttu-id="a9f77-196">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md)（创建安全的来宾共享环境）</span><span class="sxs-lookup"><span data-stu-id="a9f77-196">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md)</span></span>

[<span data-ttu-id="a9f77-197">创建托管有来宾的 B2B 外联网</span><span class="sxs-lookup"><span data-stu-id="a9f77-197">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="a9f77-198">与 Azure AD B2B 的 SharePoint 和 OneDrive 集成</span><span class="sxs-lookup"><span data-stu-id="a9f77-198">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
