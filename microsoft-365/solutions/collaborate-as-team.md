---
title: 在团队中与来宾协作
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
localization_priority: Normal
f1.keywords: NOCSH
description: 了解与团队中的来宾设置任务、对话和文档协作的团队所需的 Microsoft 365 配置步骤。
ms.openlocfilehash: 7f00acb7b7b58169d6a66bfa4cabdc5a3035f67f
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030025"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="7e58a-103">在团队中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="7e58a-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="7e58a-104">如果需要在文档、任务和对话中与来宾进行协作，我们建议使用 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="7e58a-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="7e58a-105">团队提供了 Office 和 SharePoint 中提供的所有协作功能，并在统一的用户体验中提供了持续聊天和可自定义且可扩展的协作工具集。</span><span class="sxs-lookup"><span data-stu-id="7e58a-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="7e58a-106">在本文中，我们将完成必要的 Microsoft 365 配置步骤，以设置一个团队以与来宾协作。</span><span class="sxs-lookup"><span data-stu-id="7e58a-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="7e58a-107">视频演示</span><span class="sxs-lookup"><span data-stu-id="7e58a-107">Video demonstration</span></span>

<span data-ttu-id="7e58a-108">该视频显示了本文档中描述的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="7e58a-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="7e58a-109">Azure 组织关系设置</span><span class="sxs-lookup"><span data-stu-id="7e58a-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="7e58a-110">Microsoft 365 中的共享受 [Azure Active Directory 中的组织关系设置](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)的最高级别的管辖。</span><span class="sxs-lookup"><span data-stu-id="7e58a-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="7e58a-111">如果在 Azure AD 中禁用或限制来宾共享，此设置将覆盖您在 Microsoft 365 中配置的任何共享设置。</span><span class="sxs-lookup"><span data-stu-id="7e58a-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="7e58a-112">检查组织关系设置以确保不会阻止与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="7e58a-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 组织关系设置页面的屏幕截图](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="7e58a-114">设置组织关系设置</span><span class="sxs-lookup"><span data-stu-id="7e58a-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="7e58a-115">在上登录到 Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="7e58a-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="7e58a-116">在左侧导航窗格中，单击 " **Azure Active Directory** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="7e58a-117">单击 " **外部标识** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-117">Click **External identities**.</span></span>
4. <span data-ttu-id="7e58a-118">在 " **开始** " 屏幕的左侧导航窗格中，单击 " **外部协作设置** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="7e58a-119">确保 **来宾邀请者角色中的管理员和用户可以邀请** 和 **成员** 都可以邀请都设置为 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="7e58a-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="7e58a-120">如果进行了任何更改，请单击 **“保存”** 。</span><span class="sxs-lookup"><span data-stu-id="7e58a-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="7e58a-121">请注意 " **协作限制** " 部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="7e58a-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="7e58a-122">确保不会阻止您要与之进行协作的来宾域。</span><span class="sxs-lookup"><span data-stu-id="7e58a-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="7e58a-123">如果您使用多个组织的来宾，您可能希望限制其访问目录数据的能力。</span><span class="sxs-lookup"><span data-stu-id="7e58a-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="7e58a-124">这将阻止他们看到目录中的其他人是来宾。</span><span class="sxs-lookup"><span data-stu-id="7e58a-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="7e58a-125">若要执行此操作，请在 " **来宾用户访问限制** " 下，选择 " **来宾用户对属性和目录对象的成员身份的访问权限受到限制** "，并且 **来宾用户访问仅限于其自己的目录对象的属性和成员身份** 。</span><span class="sxs-lookup"><span data-stu-id="7e58a-125">To do this, under **Guest user access restrictions** , select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="7e58a-126">团队来宾访问设置</span><span class="sxs-lookup"><span data-stu-id="7e58a-126">Teams guest access settings</span></span>

<span data-ttu-id="7e58a-127">团队具有用于来宾访问的主开/关开关，以及可用于控制来宾在团队中可执行的操作的各种设置。</span><span class="sxs-lookup"><span data-stu-id="7e58a-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="7e58a-128">主开关， **允许在团队中\*\*\*\*进行来宾** 访问，以便来宾访问能够在团队中工作。</span><span class="sxs-lookup"><span data-stu-id="7e58a-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="7e58a-129">检查以确保在团队中启用了来宾访问，并根据你的业务需求对来宾设置进行任何调整。</span><span class="sxs-lookup"><span data-stu-id="7e58a-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="7e58a-130">请记住，这些设置会影响所有团队。</span><span class="sxs-lookup"><span data-stu-id="7e58a-130">Keep in mind that these settings affect all teams.</span></span>

![Teams 来宾访问切换的屏幕截图](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="7e58a-132">设定 Teams 来宾访问设置</span><span class="sxs-lookup"><span data-stu-id="7e58a-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="7e58a-133">访问 [https://admin.microsoft.com](https://admin.microsoft.com) 登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="7e58a-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="7e58a-134">在左侧导航窗格中，单击 " **全部显示** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="7e58a-135">在“ **管理中心** ”下，单击“ **团队** ”。</span><span class="sxs-lookup"><span data-stu-id="7e58a-135">Under **Admin centers** , click **Teams**.</span></span>
4. <span data-ttu-id="7e58a-136">在团队管理中心的左侧导航窗格中，展开 " **组织范围的设置** "，然后单击 " **来宾访问** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="7e58a-137">确保 **在 Teams 中允许来宾访问** 设置为“ **开** ”。</span><span class="sxs-lookup"><span data-stu-id="7e58a-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="7e58a-138">对其他来宾设置进行任何所需的更改，然后单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="7e58a-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="7e58a-139">在将团队来宾设置启用后，可能需要长达24小时才能使其变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="7e58a-139">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="7e58a-140">Microsoft 365 组来宾设置</span><span class="sxs-lookup"><span data-stu-id="7e58a-140">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="7e58a-141">团队使用适用于团队成员身份的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="7e58a-141">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="7e58a-142">必须打开 Microsoft 365 组来宾设置，才能使团队中的来宾访问能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="7e58a-142">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Microsoft 365 管理中心中的 Microsoft 365 组来宾设置的屏幕截图](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="7e58a-144">设置 Microsoft 365 组来宾设置</span><span class="sxs-lookup"><span data-stu-id="7e58a-144">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="7e58a-145">在 Microsoft 365 管理中心的左侧导航窗格中，展开 " **设置** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-145">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="7e58a-146">单击 " **组织设置** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-146">Click **Org settings**.</span></span>
3. <span data-ttu-id="7e58a-147">在列表中，单击 " **Microsoft 365 组** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-147">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="7e58a-148">确保选中 " **允许组所有者将组织外部的人员添加为 Microsoft 365 组** " 和 " **允许来宾组成员访问组内容** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="7e58a-148">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="7e58a-149">如果进行了更改，请单击 " **保存更改** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-149">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="7e58a-150">SharePoint 组织级别的共享设置</span><span class="sxs-lookup"><span data-stu-id="7e58a-150">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="7e58a-151">工作组内容（如文件、文件夹和列表）都存储在 SharePoint 中。</span><span class="sxs-lookup"><span data-stu-id="7e58a-151">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="7e58a-152">为使来宾能够访问团队中的这些项目，SharePoint 组织级别的共享设置必须允许与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="7e58a-152">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="7e58a-153">组织级别设置决定了可用于单个网站的设置，包括与团队相关的网站。</span><span class="sxs-lookup"><span data-stu-id="7e58a-153">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="7e58a-154">网站设置不能比组织级别设置更具有更好的许可。</span><span class="sxs-lookup"><span data-stu-id="7e58a-154">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="7e58a-155">如果要允许与未经身份验证的用户共享文件和文件夹，请选择 " **任何人** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-155">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="7e58a-156">如果要确保所有来宾都必须进行身份验证，请选择 " **新建" 和 "现有来宾** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-156">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="7e58a-157">选择组织中的任何网站将需要的 "最高" 设置。</span><span class="sxs-lookup"><span data-stu-id="7e58a-157">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 组织级别共享设置的屏幕截图](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="7e58a-159">设置 SharePoint 组织级别的共享设置</span><span class="sxs-lookup"><span data-stu-id="7e58a-159">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="7e58a-160">在 Microsoft 365 管理中心的左侧导航窗格中，单击 " **管理中心** " 下的 " **SharePoint** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-160">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers** , click **SharePoint**.</span></span>
2. <span data-ttu-id="7e58a-161">在 SharePoint 管理中心中，在左侧导航窗格中，展开 " **策略** "，然后单击 " **共享** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-161">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="7e58a-162">确保将 SharePoint 的 "外部共享" 设置为 " **任何人** " 或 " **新的和现有的来宾** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-162">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="7e58a-163">如果进行了任何更改，请单击 **“保存”** 。</span><span class="sxs-lookup"><span data-stu-id="7e58a-163">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="7e58a-164">SharePoint 组织级别的默认链接设置</span><span class="sxs-lookup"><span data-stu-id="7e58a-164">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="7e58a-165">默认的文件和文件夹链接设置确定在用户共享文件或文件夹时，默认情况下将向用户显示的链接选项。</span><span class="sxs-lookup"><span data-stu-id="7e58a-165">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="7e58a-166">如果需要，用户可以在共享之前将链接类型更改为其他选项之一。</span><span class="sxs-lookup"><span data-stu-id="7e58a-166">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="7e58a-167">请注意，此设置会影响组织中的所有团队和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="7e58a-167">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="7e58a-168">选择以下任一链接类型，当用户共享文件和文件夹时，默认情况下将选择这些类型之一：</span><span class="sxs-lookup"><span data-stu-id="7e58a-168">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="7e58a-169">**任何具有链接的人** -如果您希望执行大量未经身份验证的文件和文件夹共享，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="7e58a-169">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="7e58a-170">如果要允许 *任何人* 链接，但担心意外的共享，请考虑其他选项之一作为默认选项。</span><span class="sxs-lookup"><span data-stu-id="7e58a-170">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="7e58a-171">仅当您已启用 **任何** 共享时，此链接类型才可用。</span><span class="sxs-lookup"><span data-stu-id="7e58a-171">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="7e58a-172">**仅限组织中的人员** -如果您希望大多数文件和文件夹共享与组织内部的人员共享，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="7e58a-172">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="7e58a-173">**特定人员** -如果您希望对来宾执行大量文件和文件夹共享，请考虑此选项。</span><span class="sxs-lookup"><span data-stu-id="7e58a-173">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="7e58a-174">此类型的链接可与来宾配合使用，并要求用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="7e58a-174">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 组织级别文件和文件夹共享设置的屏幕截图](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="7e58a-176">设置 SharePoint 组织级别的默认链接设置</span><span class="sxs-lookup"><span data-stu-id="7e58a-176">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="7e58a-177">导航到 SharePoint 管理中心中的 "共享" 页面。</span><span class="sxs-lookup"><span data-stu-id="7e58a-177">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="7e58a-178">在 " **文件和文件夹链接** " 下，选择要使用的默认共享链接。</span><span class="sxs-lookup"><span data-stu-id="7e58a-178">Under **File and folder links** , select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="7e58a-179">如果进行了任何更改，请单击 **“保存”** 。</span><span class="sxs-lookup"><span data-stu-id="7e58a-179">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="7e58a-180">创建团队</span><span class="sxs-lookup"><span data-stu-id="7e58a-180">Create a team</span></span>

<span data-ttu-id="7e58a-181">下一步是创建计划用于与来宾协作的团队。</span><span class="sxs-lookup"><span data-stu-id="7e58a-181">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="7e58a-182">创建团队</span><span class="sxs-lookup"><span data-stu-id="7e58a-182">To create a team</span></span>
1. <span data-ttu-id="7e58a-183">在团队中的 " **团队** " 选项卡上，单击 "加入" 或 "在左窗格底部 **创建团队** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-183">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="7e58a-184">单击 " **创建团队** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-184">Click **Create a team**.</span></span>
3. <span data-ttu-id="7e58a-185">单击 " **从头开始构建团队** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-185">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="7e58a-186">选择 " **专用** " 或 " **公共** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-186">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="7e58a-187">键入团队的名称和说明，然后单击 " **创建** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-187">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="7e58a-188">单击 " **跳过** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-188">Click **Skip**.</span></span>

<span data-ttu-id="7e58a-189">我们将稍后邀请用户。</span><span class="sxs-lookup"><span data-stu-id="7e58a-189">We'll invite users later.</span></span> <span data-ttu-id="7e58a-190">接下来，请务必检查与团队关联的 SharePoint 网站的网站级别共享设置。</span><span class="sxs-lookup"><span data-stu-id="7e58a-190">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="7e58a-191">SharePoint 网站级别的共享设置</span><span class="sxs-lookup"><span data-stu-id="7e58a-191">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="7e58a-192">检查网站级别的共享设置以确保它们允许此团队的访问类型。</span><span class="sxs-lookup"><span data-stu-id="7e58a-192">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="7e58a-193">例如，如果将组织级别设置设置为 " **任何人** "，但希望所有来宾都对此团队进行身份验证，请确保将网站级别的共享设置设置为 " **新建" 和 "现有来宾** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-193">For example, if you set the organization-level settings to **Anyone** , but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="7e58a-195">设置网站级共享设置</span><span class="sxs-lookup"><span data-stu-id="7e58a-195">To set site-level sharing settings</span></span>
1. <span data-ttu-id="7e58a-196">在 SharePoint 管理中心中，在左侧导航窗格中，展开 " **网站** "，然后单击 " **活动网站** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-196">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="7e58a-197">选择刚才创建的团队站点。</span><span class="sxs-lookup"><span data-stu-id="7e58a-197">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="7e58a-198">单击 .。。并选择 " **共享** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-198">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="7e58a-199">确保将 "共享" 设置为 " **任何人** " 或 " **新的和现有的来宾** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-199">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="7e58a-200">如果进行了任何更改，请单击 **“保存”** 。</span><span class="sxs-lookup"><span data-stu-id="7e58a-200">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="7e58a-201">邀请用户</span><span class="sxs-lookup"><span data-stu-id="7e58a-201">Invite users</span></span>

<span data-ttu-id="7e58a-202">现在已配置来宾共享设置，因此您可以开始向团队添加内部用户和来宾。</span><span class="sxs-lookup"><span data-stu-id="7e58a-202">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="7e58a-203">向团队邀请内部用户</span><span class="sxs-lookup"><span data-stu-id="7e58a-203">To invite internal users to a team</span></span>
1. <span data-ttu-id="7e58a-204">在团队中，单击 " **更多选项** " ( **\*\*\*** ) "，然后单击" **添加成员** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-204">In the team, click **More options** ( **\*\*\*** ), and then click **Add member**.</span></span>
2. <span data-ttu-id="7e58a-205">键入要邀请的人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="7e58a-205">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="7e58a-206">单击“ **添加** ”，然后单击“ **关闭** ”。</span><span class="sxs-lookup"><span data-stu-id="7e58a-206">Click **Add** , and then click **Close**.</span></span>

<span data-ttu-id="7e58a-207">向团队邀请来宾</span><span class="sxs-lookup"><span data-stu-id="7e58a-207">To invite guests to a team</span></span>
1. <span data-ttu-id="7e58a-208">在团队中，单击 " **更多选项** " ( **\*\*\*** ) "，然后单击" **添加成员** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-208">In the team, click **More options** ( **\*\*\*** ), and then click **Add member**.</span></span>
2. <span data-ttu-id="7e58a-209">键入要邀请的来宾的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7e58a-209">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="7e58a-210">单击 " **编辑来宾信息** "。</span><span class="sxs-lookup"><span data-stu-id="7e58a-210">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="7e58a-211">键入来宾的全名并单击复选标记。</span><span class="sxs-lookup"><span data-stu-id="7e58a-211">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="7e58a-212">单击“ **添加** ”，然后单击“ **关闭** ”。</span><span class="sxs-lookup"><span data-stu-id="7e58a-212">Click **Add** , and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e58a-213">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e58a-213">See also</span></span>

[<span data-ttu-id="7e58a-214">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="7e58a-214">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="7e58a-215">与来宾共享时限制文件意外曝光</span><span class="sxs-lookup"><span data-stu-id="7e58a-215">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

<span data-ttu-id="7e58a-216">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md)（创建安全的来宾共享环境）</span><span class="sxs-lookup"><span data-stu-id="7e58a-216">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md)</span></span>

[<span data-ttu-id="7e58a-217">创建托管有来宾的 B2B 外联网</span><span class="sxs-lookup"><span data-stu-id="7e58a-217">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="7e58a-218">与 Azure AD B2B 的 SharePoint 和 OneDrive 集成</span><span class="sxs-lookup"><span data-stu-id="7e58a-218">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
