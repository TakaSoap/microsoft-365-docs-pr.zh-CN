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
description: 了解设置团队与 Teams 中的来宾进行任务、对话以及文档协作所需的 Microsoft 365 配置步骤。
ms.openlocfilehash: cc962e22bde70220e07f805b0a7a83c111886369
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659602"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="70bcf-103">在团队中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="70bcf-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="70bcf-104">如果你需要跨文档、任务和对话与来宾协作，我们建议使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="70bcf-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="70bcf-105">Teams 提供 Office 和 SharePoint 中提供的所有协作功能，在统一的用户体验中提供持久聊天和一组可自定义和可扩展的协作工具。</span><span class="sxs-lookup"><span data-stu-id="70bcf-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="70bcf-106">本文将介绍设置团队以与来宾协作所需的 Microsoft 365 配置步骤。</span><span class="sxs-lookup"><span data-stu-id="70bcf-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="70bcf-107">视频演示</span><span class="sxs-lookup"><span data-stu-id="70bcf-107">Video demonstration</span></span>

<span data-ttu-id="70bcf-108">此视频演示本文档中所述的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="70bcf-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="70bcf-109">Azure 外部协作设置</span><span class="sxs-lookup"><span data-stu-id="70bcf-109">Azure External collaboration settings</span></span>

<span data-ttu-id="70bcf-110">Microsoft 365 中的共享由 Azure Active Directory 中的 [B2B](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)外部协作设置在最高级别管理。</span><span class="sxs-lookup"><span data-stu-id="70bcf-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="70bcf-111">如果在 Azure AD 中禁用或限制来宾共享，此设置将覆盖你在 Microsoft 365 中配置的任何共享设置。</span><span class="sxs-lookup"><span data-stu-id="70bcf-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="70bcf-112">检查 B2B 外部协作设置设置以确保不会阻止与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="70bcf-112">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 组织关系设置页面的屏幕截图](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="70bcf-114">设置外部协作设置</span><span class="sxs-lookup"><span data-stu-id="70bcf-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="70bcf-115">登录 Azure Active [https://aad.portal.azure.com](https://aad.portal.azure.com) Directory。</span><span class="sxs-lookup"><span data-stu-id="70bcf-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="70bcf-116">在左侧导航窗格中，单击 **Azure Active Directory。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="70bcf-117">单击 **"外部标识"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-117">Click **External identities**.</span></span>
4. <span data-ttu-id="70bcf-118">在 **"入门"** 屏幕的左侧导航窗格中，单击 **"外部协作设置"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="70bcf-119">确保 **管理员和来宾邀请** 者角色中的用户可以邀请，**并且成员可以邀请** 都设置为 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="70bcf-120">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="70bcf-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="70bcf-121">记下"协作限制 **"部分** 中的设置。</span><span class="sxs-lookup"><span data-stu-id="70bcf-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="70bcf-122">确保未阻止要协作的来宾的域。</span><span class="sxs-lookup"><span data-stu-id="70bcf-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="70bcf-123">如果与多个组织的来宾合作，可能需要限制其访问目录数据的能力。</span><span class="sxs-lookup"><span data-stu-id="70bcf-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="70bcf-124">这将阻止他们查看目录中的来宾。</span><span class="sxs-lookup"><span data-stu-id="70bcf-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="70bcf-125">为此，在"来宾用户访问限制"下，选择"来宾用户对目录对象设置的属性和成员身份具有有限访问权限"或"来宾"用户访问仅限于其自己的目录对象的属性和 **成员身份**。</span><span class="sxs-lookup"><span data-stu-id="70bcf-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="70bcf-126">Teams 来宾访问设置</span><span class="sxs-lookup"><span data-stu-id="70bcf-126">Teams guest access settings</span></span>

<span data-ttu-id="70bcf-127">Teams 具有用于来宾访问的主开/关开关，以及可用于控制来宾可在团队中执行哪些操作的各种设置。</span><span class="sxs-lookup"><span data-stu-id="70bcf-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="70bcf-128">主开关 **"在 Teams 中允许来宾访问** "必须 **打开，来宾** 访问在 Teams 中工作。</span><span class="sxs-lookup"><span data-stu-id="70bcf-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="70bcf-129">检查以确保 Teams 中已启用来宾访问，并根据您的业务需求对来宾设置进行任何调整。</span><span class="sxs-lookup"><span data-stu-id="70bcf-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="70bcf-130">请记住，这些设置会影响所有团队。</span><span class="sxs-lookup"><span data-stu-id="70bcf-130">Keep in mind that these settings affect all teams.</span></span>

![Teams 来宾访问切换的屏幕截图](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="70bcf-132">设定 Teams 来宾访问设置</span><span class="sxs-lookup"><span data-stu-id="70bcf-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="70bcf-133">访问 [https://admin.microsoft.com](https://admin.microsoft.com) 登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="70bcf-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="70bcf-134">在左侧导航窗格中，单击"**全部显示"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="70bcf-135">在“**管理中心**”下，单击“**团队**”。</span><span class="sxs-lookup"><span data-stu-id="70bcf-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="70bcf-136">在 Teams 管理中心的左侧导航窗格中，展开 **组织范围的设置**，然后单击"**来宾访问"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="70bcf-137">确保 **在 Teams 中允许来宾访问** 设置为“**开**”。</span><span class="sxs-lookup"><span data-stu-id="70bcf-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="70bcf-138">对其他来宾设置进行任何所需的更改，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="70bcf-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="70bcf-139">启用 Teams 来宾访问后，可以选择使用敏感度标签控制对各个团队及其关联 SharePoint 网站的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="70bcf-139">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="70bcf-140">有关详细信息，请参阅使用 [敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="70bcf-140">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="70bcf-141">Teams 来宾设置可能需要 24 小时才能在打开后变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="70bcf-141">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="70bcf-142">Microsoft 365 组来宾设置</span><span class="sxs-lookup"><span data-stu-id="70bcf-142">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="70bcf-143">Teams 使用 Microsoft 365 组作为团队成员身份。</span><span class="sxs-lookup"><span data-stu-id="70bcf-143">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="70bcf-144">必须打开 Microsoft 365 组来宾设置，Teams 中的来宾访问才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="70bcf-144">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Microsoft 365 管理中心中的 Microsoft 365 组来宾设置的屏幕截图](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="70bcf-146">设置 Microsoft 365 组来宾设置</span><span class="sxs-lookup"><span data-stu-id="70bcf-146">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="70bcf-147">在 Microsoft 365 管理中心的左侧导航窗格中，展开"**设置"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-147">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="70bcf-148">单击 **"组织设置"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-148">Click **Org settings**.</span></span>
3. <span data-ttu-id="70bcf-149">在列表中，单击 **"Microsoft 365 组"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-149">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="70bcf-150">确保允许组所有者将组织外部人员作为来宾添加到 **Microsoft 365** 组，同时选中"允许 **来宾** 组成员访问组内容"复选框。</span><span class="sxs-lookup"><span data-stu-id="70bcf-150">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="70bcf-151">如果进行了更改，请单击"**保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-151">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="70bcf-152">SharePoint 组织级别共享设置</span><span class="sxs-lookup"><span data-stu-id="70bcf-152">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="70bcf-153">Teams 内容（如文件、文件夹和列表）均存储在 SharePoint 中。</span><span class="sxs-lookup"><span data-stu-id="70bcf-153">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="70bcf-154">为了让来宾能够访问 Teams 中的这些项目，SharePoint 组织级共享设置必须允许与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="70bcf-154">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="70bcf-155">组织级别的设置确定各个网站（包括与团队关联的网站）可用的设置。</span><span class="sxs-lookup"><span data-stu-id="70bcf-155">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="70bcf-156">网站设置不能比组织级别的设置更宽松。</span><span class="sxs-lookup"><span data-stu-id="70bcf-156">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="70bcf-157">如果要允许与未经身份验证的人共享文件和文件夹，请选择"任何人 **"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-157">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="70bcf-158">如果要确保所有来宾均必须进行身份验证，请选择 **"新建来宾"和"现有来宾"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-158">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="70bcf-159">选择组织中任何网站所需的最宽松设置。</span><span class="sxs-lookup"><span data-stu-id="70bcf-159">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 组织级别共享设置的屏幕截图](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="70bcf-161">设置 SharePoint 组织级共享设置</span><span class="sxs-lookup"><span data-stu-id="70bcf-161">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="70bcf-162">在 Microsoft 365 管理中心左侧导航窗格中的"管理中心"下，单击 **"SharePoint"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-162">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="70bcf-163">在 SharePoint 管理中心的左侧导航窗格中，展开"策略 **"，然后单击**"**共享"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-163">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="70bcf-164">确保 SharePoint 的外部共享设置为"任何人 **"** 或"**新来宾"和"现有来宾"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-164">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="70bcf-165">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="70bcf-165">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="70bcf-166">SharePoint 组织级别的默认链接设置</span><span class="sxs-lookup"><span data-stu-id="70bcf-166">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="70bcf-167">默认文件和文件夹链接设置确定在用户共享文件或文件夹时默认向用户显示的链接选项。</span><span class="sxs-lookup"><span data-stu-id="70bcf-167">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="70bcf-168">如果需要，用户可以在共享之前将链接类型更改为其他选项之一。</span><span class="sxs-lookup"><span data-stu-id="70bcf-168">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="70bcf-169">请记住，此设置会影响组织的所有团队和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="70bcf-169">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="70bcf-170">选择以下任一链接类型，当用户共享文件和文件夹时，将默认选择这些链接类型：</span><span class="sxs-lookup"><span data-stu-id="70bcf-170">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="70bcf-171">**具有链接的** 任何人 - 如果希望对文件和文件夹执行大量未经身份验证的共享，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="70bcf-171">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="70bcf-172">如果要允许"任何人 *"* 链接，但担心意外的未经身份验证的共享，请考虑使用其他选项之一作为默认选项。</span><span class="sxs-lookup"><span data-stu-id="70bcf-172">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="70bcf-173">此链接类型仅在启用了"任何人共享 **"时** 可用。</span><span class="sxs-lookup"><span data-stu-id="70bcf-173">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="70bcf-174">**仅组织内部人员** - 如果希望大多数文件和文件夹共享与组织内部人员共享，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="70bcf-174">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="70bcf-175">**特定人员** - 如果你希望与来宾共享大量文件和文件夹，请考虑使用此选项。</span><span class="sxs-lookup"><span data-stu-id="70bcf-175">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="70bcf-176">此类链接适用于来宾，要求他们进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="70bcf-176">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 组织级别文件和文件夹共享设置的屏幕截图](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="70bcf-178">设置 SharePoint 组织级别默认链接设置</span><span class="sxs-lookup"><span data-stu-id="70bcf-178">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="70bcf-179">导航到 SharePoint 管理中心中的"共享"页面。</span><span class="sxs-lookup"><span data-stu-id="70bcf-179">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="70bcf-180">在 **"文件和文件夹链接**"下，选择要使用的默认共享链接。</span><span class="sxs-lookup"><span data-stu-id="70bcf-180">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="70bcf-181">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="70bcf-181">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="70bcf-182">创建团队</span><span class="sxs-lookup"><span data-stu-id="70bcf-182">Create a team</span></span>

<span data-ttu-id="70bcf-183">下一步是创建计划用于与来宾协作的团队。</span><span class="sxs-lookup"><span data-stu-id="70bcf-183">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="70bcf-184">创建团队</span><span class="sxs-lookup"><span data-stu-id="70bcf-184">To create a team</span></span>
1. <span data-ttu-id="70bcf-185">在 Teams 中的 **"Teams"** 选项卡上，单击"加入"或在左窗格底部创建团队。</span><span class="sxs-lookup"><span data-stu-id="70bcf-185">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="70bcf-186">单击 **"创建团队"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-186">Click **Create a team**.</span></span>
3. <span data-ttu-id="70bcf-187">单击 **"从头开始建立团队"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-187">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="70bcf-188">选择 **"专用"** 或 **"公共"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-188">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="70bcf-189">键入团队的名称和说明，然后单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-189">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="70bcf-190">单击 **"跳过"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-190">Click **Skip**.</span></span>

<span data-ttu-id="70bcf-191">我们稍后将邀请用户。</span><span class="sxs-lookup"><span data-stu-id="70bcf-191">We'll invite users later.</span></span> <span data-ttu-id="70bcf-192">接下来，检查与团队关联的 SharePoint 网站的网站级共享设置非常重要。</span><span class="sxs-lookup"><span data-stu-id="70bcf-192">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="70bcf-193">SharePoint 网站级共享设置</span><span class="sxs-lookup"><span data-stu-id="70bcf-193">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="70bcf-194">检查网站级别的共享设置，以确保这些设置允许此团队访问的类型。</span><span class="sxs-lookup"><span data-stu-id="70bcf-194">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="70bcf-195">例如，如果将组织级别设置设置为"任何人"，但希望所有来宾对此团队进行身份验证，请确保网站级别共享设置设置为"新来宾"和"现有来宾 **"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-195">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="70bcf-197">设置网站级共享设置</span><span class="sxs-lookup"><span data-stu-id="70bcf-197">To set site-level sharing settings</span></span>
1. <span data-ttu-id="70bcf-198">在 SharePoint 管理中心的左侧导航窗格中，展开 **"** 网站"，然后单击 **"活动网站"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-198">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="70bcf-199">选择刚才创建的团队站点。</span><span class="sxs-lookup"><span data-stu-id="70bcf-199">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="70bcf-200">单击...然后选择"**共享"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-200">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="70bcf-201">确保共享设置为"任何人 **"或\*\*\*\*"新来宾"和"现有来宾"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-201">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="70bcf-202">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="70bcf-202">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="70bcf-203">邀请用户</span><span class="sxs-lookup"><span data-stu-id="70bcf-203">Invite users</span></span>

<span data-ttu-id="70bcf-204">现在配置了来宾共享设置，因此你可以开始向团队添加内部用户和来宾。</span><span class="sxs-lookup"><span data-stu-id="70bcf-204">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="70bcf-205">邀请内部用户加入团队</span><span class="sxs-lookup"><span data-stu-id="70bcf-205">To invite internal users to a team</span></span>
1. <span data-ttu-id="70bcf-206">在团队中，单击 **" ()** **\*\*\*** 选项，然后单击"添加 **成员"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-206">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="70bcf-207">键入要邀请的人的姓名。</span><span class="sxs-lookup"><span data-stu-id="70bcf-207">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="70bcf-208">单击“**添加**”，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="70bcf-208">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="70bcf-209">邀请来宾加入团队</span><span class="sxs-lookup"><span data-stu-id="70bcf-209">To invite guests to a team</span></span>
1. <span data-ttu-id="70bcf-210">在团队中，单击 **" ()** **\*\*\*** 选项，然后单击"添加 **成员"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-210">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="70bcf-211">键入要邀请的来宾的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="70bcf-211">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="70bcf-212">单击 **"编辑来宾信息"。**</span><span class="sxs-lookup"><span data-stu-id="70bcf-212">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="70bcf-213">键入来宾的全名，然后单击选中标记。</span><span class="sxs-lookup"><span data-stu-id="70bcf-213">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="70bcf-214">单击“**添加**”，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="70bcf-214">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="70bcf-215">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70bcf-215">See also</span></span>

[<span data-ttu-id="70bcf-216">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="70bcf-216">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="70bcf-217">与来宾共享时限制文件意外曝光</span><span class="sxs-lookup"><span data-stu-id="70bcf-217">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="70bcf-218">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="70bcf-218">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="70bcf-219">创建托管有来宾的 B2B 外联网</span><span class="sxs-lookup"><span data-stu-id="70bcf-219">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="70bcf-220">SharePoint 和 OneDrive 与 Azure AD B2B 集成</span><span class="sxs-lookup"><span data-stu-id="70bcf-220">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
