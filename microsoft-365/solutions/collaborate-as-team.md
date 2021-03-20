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
localization_priority: Priority
f1.keywords: NOCSH
description: 了解在 Teams 中设置团队与来宾进行任务、对话及文档协作所必需的 Microsoft 365 配置步骤。
ms.openlocfilehash: 4e734af198563d0bc4599b4476b3823384989212
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904656"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="357cd-103">在团队中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="357cd-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="357cd-104">如果需要在文档、任务和对话中与来宾进行协作，我们建议使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="357cd-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="357cd-105">Teams 在统一的用户体验中提供了 Office 和 SharePoint 中的所有协作功能，包括持续聊天和一套可定制和可扩展的协作工具。</span><span class="sxs-lookup"><span data-stu-id="357cd-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="357cd-106">在本文中，我们将介绍建立一个团队与客人协作所需的 Microsoft 365 配置步骤。</span><span class="sxs-lookup"><span data-stu-id="357cd-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="357cd-107">一旦配置客人的访问权限，就可以按照 [Teams 中的“添加来宾到团队”](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f) 中的步骤邀请来宾到团队。</span><span class="sxs-lookup"><span data-stu-id="357cd-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="357cd-108">视频演示</span><span class="sxs-lookup"><span data-stu-id="357cd-108">Video demonstration</span></span>

<span data-ttu-id="357cd-109">该视频展示了本文档中介绍的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="357cd-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="357cd-110">Azure 外部协作设置</span><span class="sxs-lookup"><span data-stu-id="357cd-110">Azure External collaboration settings</span></span>

<span data-ttu-id="357cd-111">Microsoft 365 中的共享在最高级别由 [Azure Active Directory 中的 B2B 外部协作设置](/azure/active-directory/external-identities/delegate-invitations) 管理。</span><span class="sxs-lookup"><span data-stu-id="357cd-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="357cd-112">如果在 Azure AD 中禁用或限制来宾共享，此设置将覆盖你在 Microsoft 365 中配置的任何共享设置。</span><span class="sxs-lookup"><span data-stu-id="357cd-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="357cd-113">检查 B2B 外部协作设置设置以确保不会阻止与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="357cd-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 组织关系设置页面的屏幕截图](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="357cd-115">设置外部协作设置</span><span class="sxs-lookup"><span data-stu-id="357cd-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="357cd-116">在 [https://aad.portal.azure.com](https://aad.portal.azure.com) 上登录到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="357cd-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="357cd-117">在左侧导航窗格中，单击 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="357cd-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="357cd-118">单击 **“外部标识”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-118">Click **External identities**.</span></span>
4. <span data-ttu-id="357cd-119">在 **“入门”** 屏幕的左侧导航窗格中，单击 **“外部协作设置”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="357cd-120">确保 **“管理员和来宾邀请者角色中的用户可以邀请”**，且 **“成员可以邀请”** 同时设置为 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="357cd-121">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="357cd-122">请注意 **“协作限制"** 部分的设置。</span><span class="sxs-lookup"><span data-stu-id="357cd-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="357cd-123">确保不会阻止要协作来宾的域。</span><span class="sxs-lookup"><span data-stu-id="357cd-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="357cd-124">如果与多个组织的来宾合作，可能需要限制其访问目录数据的能力。 </span><span class="sxs-lookup"><span data-stu-id="357cd-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="357cd-125">这将阻止他们查看目录中的来宾。</span><span class="sxs-lookup"><span data-stu-id="357cd-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="357cd-126">为此，在 **“来宾用户访问限制”** 下，选择 **“来宾用户具有对目录对象设置的属性和成员身份的有限访问权限”** 或 **“来宾用户访问仅限于其自己的目录对象的属性和成员身份”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="357cd-127">Teams 来宾访问设置</span><span class="sxs-lookup"><span data-stu-id="357cd-127">Teams guest access settings</span></span>

<span data-ttu-id="357cd-128">Teams 具有用于来宾访问的主 “开/关” 开关，以及可用于控制来宾在团队中所能执行操作的各种设置。</span><span class="sxs-lookup"><span data-stu-id="357cd-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="357cd-129">主开关 **“允许来宾在 Teams 中访问”** 必须 **“打开”**，来宾才可以在 Teams 中工作。</span><span class="sxs-lookup"><span data-stu-id="357cd-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="357cd-130">检查以确保 Teams 中已启用“来宾访问”，并根据你的业务需求对来宾设置作出调整。</span><span class="sxs-lookup"><span data-stu-id="357cd-130">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="357cd-131">请记住，这些设置会影响所有团队。</span><span class="sxs-lookup"><span data-stu-id="357cd-131">Keep in mind that these settings affect all teams.</span></span>

![Teams 来宾访问切换的屏幕截图](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="357cd-133">设定 Teams 来宾访问设置</span><span class="sxs-lookup"><span data-stu-id="357cd-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="357cd-134">访问 [https://admin.microsoft.com](https://admin.microsoft.com) 登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="357cd-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="357cd-135">在左侧导航窗格中，单击 **“显示所有”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="357cd-136">在 **“管理中心”** 下，单击 **“Teams”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="357cd-137">在 Teams 管理中心左侧导航窗格中，展开 **“组织范围设置”**，然后单击 **“来宾访问”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="357cd-138">确保 **在 Teams 中允许来宾访问** 设置为“**开**”。</span><span class="sxs-lookup"><span data-stu-id="357cd-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="357cd-139">对其他来宾设置进行任何所需的更改，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="357cd-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="357cd-140">启用 Teams 来宾访问后，可以选择使用敏感度标签控制对各个团队及其关联 SharePoint 网站的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="357cd-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="357cd-141">有关详细信息，请参阅 [使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="357cd-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!NOTE]
> <span data-ttu-id="357cd-142">Teams 来宾设置将在启用后 24 小时内生效。</span><span class="sxs-lookup"><span data-stu-id="357cd-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="357cd-143">Microsoft 365 组来宾设置</span><span class="sxs-lookup"><span data-stu-id="357cd-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="357cd-144">Teams 使用 Microsoft 365 组作为团队成员身份。</span><span class="sxs-lookup"><span data-stu-id="357cd-144">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="357cd-145">必须打开 Microsoft 365 组来宾设置，Teams 中的来宾访问才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="357cd-145">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Microsoft 365 管理中心中的 Microsoft 365 组来宾设置的屏幕截图](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="357cd-147">设置 Microsoft 365 组来宾设置</span><span class="sxs-lookup"><span data-stu-id="357cd-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="357cd-148">在 Microsoft 365 管理中心左侧导航窗格中，展开 **“设置”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="357cd-149">单击 **“组织设置”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="357cd-150">在列表中，单击 **“Microsoft 365 组”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="357cd-151">确保复选框 **允许组所有者将组织外部人员作为来宾添加到 Microsoft 365 组** 和 **允许来宾组成员访问组内容** 都已选中。</span><span class="sxs-lookup"><span data-stu-id="357cd-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="357cd-152">如果进行了更改，请单击 **“保存更改”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="357cd-153">SharePoint 组织级别共享设置</span><span class="sxs-lookup"><span data-stu-id="357cd-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="357cd-154">Teams 内容（如文件、文件夹和列表）均存储在 SharePoint 中。</span><span class="sxs-lookup"><span data-stu-id="357cd-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="357cd-155">为了使来宾能够访问 Teams 中的这些项目，SharePoint 组织级别的共享设置必须允许与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="357cd-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="357cd-156">组织级别设置确定各个网站（包括与团队关联的网站）可用的设置。</span><span class="sxs-lookup"><span data-stu-id="357cd-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="357cd-157">网站设置不能比组织级别设置更宽松。</span><span class="sxs-lookup"><span data-stu-id="357cd-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="357cd-158">如果要允许与未经身份验证的人共享文件和文件夹，请选择 **“任何人”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="357cd-159">如果要确保所有来宾都进行身份验证，请选择 **“新来宾和现有来宾”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="357cd-160">选择组织中任何网站所需的最宽松设置。</span><span class="sxs-lookup"><span data-stu-id="357cd-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 组织级别共享设置的屏幕截图](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="357cd-162">设置 SharePoint 组织级共享设置</span><span class="sxs-lookup"><span data-stu-id="357cd-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="357cd-163">在 Microsoft 365 管理中心左侧导航窗格中的 **“管理中心”** 下，单击 **“SharePoint”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="357cd-164">在 SharePoint 管理中心的左侧导航窗格中，展开 **"策略"**，然后单击 **“共享”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="357cd-165">确保 SharePoint 的外部共享设置为 **“任何人”** 或 **“新来宾和现有来宾”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="357cd-166">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="357cd-167">SharePoint 组织级别的默认链接设置</span><span class="sxs-lookup"><span data-stu-id="357cd-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="357cd-168">默认文件和文件夹链接设置确定在用户共享文件或文件夹时默认向用户显示的链接选项。</span><span class="sxs-lookup"><span data-stu-id="357cd-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="357cd-169">如果需要，用户可以在共享之前将链接类型更改为其他选项之一。</span><span class="sxs-lookup"><span data-stu-id="357cd-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="357cd-170">请记住，此设置会影响组织的所有团队和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="357cd-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="357cd-171">选择以下任一链接类型，当用户共享文件和文件夹时将默认选择这些链接类型：</span><span class="sxs-lookup"><span data-stu-id="357cd-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="357cd-172">**拥有链接的任何人** - 如果希望对文件和文件夹执行大量未经身份验证的共享，请选择此选项。 </span><span class="sxs-lookup"><span data-stu-id="357cd-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="357cd-173">如果希望允许 *“任何人”* 链接，但担心意外的未经身份验证的共享，请考虑使用其他选项之一作为默认选项。</span><span class="sxs-lookup"><span data-stu-id="357cd-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="357cd-174">此链接类型仅在启用 **”任何人“** 共享时可用。</span><span class="sxs-lookup"><span data-stu-id="357cd-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="357cd-175">**仅组织内部人员** - 如果希望大多数文件和文件夹共享是与组织内部人员共享，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="357cd-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="357cd-176">**特定人员** - 如果希望与来宾进行大量文件和文件夹共享，请考虑此选项。</span><span class="sxs-lookup"><span data-stu-id="357cd-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="357cd-177">此类链接适用于来宾，且要求他们进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="357cd-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 组织级别文件和文件夹共享设置的屏幕截图](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="357cd-179">设置 SharePoint 组织级别的默认链接设置</span><span class="sxs-lookup"><span data-stu-id="357cd-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="357cd-180">导航到 SharePoint 管理中心的"共享"页面。</span><span class="sxs-lookup"><span data-stu-id="357cd-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="357cd-181">在 **“文件夹链接”** 下，选择要使用的默认共享链接。</span><span class="sxs-lookup"><span data-stu-id="357cd-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="357cd-182">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="357cd-183">创建团队</span><span class="sxs-lookup"><span data-stu-id="357cd-183">Create a team</span></span>

<span data-ttu-id="357cd-184">下一步是创建计划用于与来宾协作的团队。</span><span class="sxs-lookup"><span data-stu-id="357cd-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="357cd-185">创建团队</span><span class="sxs-lookup"><span data-stu-id="357cd-185">To create a team</span></span>
1. <span data-ttu-id="357cd-186">在 Teams 中的 **“Teams”** 选项卡上，单击左侧窗格底部的 **“加入”或“创建团队”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="357cd-187">单击 **“创建团队”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="357cd-188">单击 **“从头开始建立团队”**.</span><span class="sxs-lookup"><span data-stu-id="357cd-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="357cd-189">选择 **“专用”** 或 **“公共”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="357cd-190">键入团队名称和说明，然后单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="357cd-191">单击 **“跳过”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-191">Click **Skip**.</span></span>

<span data-ttu-id="357cd-192">我们稍后将邀请用户。</span><span class="sxs-lookup"><span data-stu-id="357cd-192">We'll invite users later.</span></span> <span data-ttu-id="357cd-193">接下来，检查与团队关联的 SharePoint 网站的网站级别共享设置非常重要。</span><span class="sxs-lookup"><span data-stu-id="357cd-193">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="357cd-194">SharePoint 网站级别共享设置</span><span class="sxs-lookup"><span data-stu-id="357cd-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="357cd-195">检查网站级别共享设置，确保它们允许此团队所需的访问类型。</span><span class="sxs-lookup"><span data-stu-id="357cd-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="357cd-196">例如，如果将组织级别设置设置为 **“任何人”**，但想让所有来宾都为此团队进行身份验证，则请确保网站级别共享设置设置为 **“新来宾和现有来宾”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="357cd-198">设置网站级别共享设置</span><span class="sxs-lookup"><span data-stu-id="357cd-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="357cd-199">在 SharePoint 管理中心的左侧导航栏中，展开 **“网站”**，然后单击 **“活动网站”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="357cd-200">选择刚才创建的团队站点。</span><span class="sxs-lookup"><span data-stu-id="357cd-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="357cd-201">单击 ... 然后选择 **“共享”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="357cd-202">确保将共享设置为 **“任何人”** 或 **“新来宾和现有来宾”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="357cd-203">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="357cd-204">邀请用户</span><span class="sxs-lookup"><span data-stu-id="357cd-204">Invite users</span></span>

<span data-ttu-id="357cd-205">现在配置了来宾共享设置，以便你可以开始向团队添加内部用户和来宾。</span><span class="sxs-lookup"><span data-stu-id="357cd-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="357cd-206">邀请内部用户加入团队</span><span class="sxs-lookup"><span data-stu-id="357cd-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="357cd-207">在团队中，单击 **“更多选项”** (**\*\*\***)，然后单击 **“添加成员”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="357cd-208">键入要邀请人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="357cd-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="357cd-209">单击 **“添加”**，然后单击 **“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="357cd-210">邀请来宾加入团队</span><span class="sxs-lookup"><span data-stu-id="357cd-210">To invite guests to a team</span></span>
1. <span data-ttu-id="357cd-211">在团队中，单击 **“更多选项”** (**\*\*\***)，然后单击 **“添加成员”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="357cd-212">键入要邀请来宾的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="357cd-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="357cd-213">单击 **“编辑来宾信息”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="357cd-214">键入来宾全名，然后单击选中标记。</span><span class="sxs-lookup"><span data-stu-id="357cd-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="357cd-215">单击 **“添加”**，然后单击 **“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="357cd-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="357cd-216">另请参阅</span><span class="sxs-lookup"><span data-stu-id="357cd-216">See also</span></span>

[<span data-ttu-id="357cd-217">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="357cd-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="357cd-218">与来宾共享时限制文件意外曝光</span><span class="sxs-lookup"><span data-stu-id="357cd-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

<span data-ttu-id="357cd-219">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md)（创建安全的来宾共享环境）</span><span class="sxs-lookup"><span data-stu-id="357cd-219">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md)</span></span>

[<span data-ttu-id="357cd-220">创建有托管来宾的 B2B 外网</span><span class="sxs-lookup"><span data-stu-id="357cd-220">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="357cd-221">SharePoint 和 OneDrive 与 Azure AD B2B 的集成</span><span class="sxs-lookup"><span data-stu-id="357cd-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="357cd-222">从 SharePoint 或 OneDrive 共享时，共享选项呈灰色</span><span class="sxs-lookup"><span data-stu-id="357cd-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)