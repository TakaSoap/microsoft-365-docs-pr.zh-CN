---
title: 在文档中与来宾协作
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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: 在本文中，您将了解如何与来宾在 SharePoint 和 OneDrive 中的文档中进行协作。
ms.openlocfilehash: 022811be642a79c07c632cefcc67a27f19e3af4f
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422601"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="49f64-103">在文档中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="49f64-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="49f64-104">如果需要与组织外部的人员协作处理 SharePoint 或 OneDrive 中的文档，则可以向其发送指向文档的共享链接。</span><span class="sxs-lookup"><span data-stu-id="49f64-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="49f64-105">在本文中，我们将演练必要的 Microsoft 365 配置步骤，以设置 SharePoint 和 OneDrive 的共享链接，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="49f64-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="49f64-106">视频演示</span><span class="sxs-lookup"><span data-stu-id="49f64-106">Video demonstration</span></span>

<span data-ttu-id="49f64-107">该视频显示了本文档中描述的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="49f64-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="49f64-108">Azure 组织关系设置</span><span class="sxs-lookup"><span data-stu-id="49f64-108">Azure organizational relationships settings</span></span>

<span data-ttu-id="49f64-109">Microsoft 365 中的共享受 [Azure Active Directory 中的组织关系设置](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)的最高级别的管辖。</span><span class="sxs-lookup"><span data-stu-id="49f64-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="49f64-110">如果在 Azure AD 中禁用或限制来宾共享，此设置将覆盖您在 Microsoft 365 中配置的任何共享设置。</span><span class="sxs-lookup"><span data-stu-id="49f64-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="49f64-111">检查组织关系设置以确保不会阻止与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="49f64-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 组织关系设置页面的屏幕截图](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="49f64-113">设置组织关系设置</span><span class="sxs-lookup"><span data-stu-id="49f64-113">To set organizational relationship settings</span></span>

<span data-ttu-id="49f64-114">设置外部协作设置</span><span class="sxs-lookup"><span data-stu-id="49f64-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="49f64-115">在上登录到 Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="49f64-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="49f64-116">在左侧导航窗格中，单击 " **Azure Active Directory**"。</span><span class="sxs-lookup"><span data-stu-id="49f64-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="49f64-117">单击 " **外部标识**"。</span><span class="sxs-lookup"><span data-stu-id="49f64-117">Click **External identities**.</span></span>
4. <span data-ttu-id="49f64-118">在 " **开始** " 屏幕的左侧导航窗格中，单击 " **外部协作设置**"。</span><span class="sxs-lookup"><span data-stu-id="49f64-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="49f64-119">确保 **来宾邀请者角色中的管理员和用户可以邀请** 和 **成员** 都可以邀请都设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="49f64-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="49f64-120">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="49f64-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="49f64-121">请注意 " **协作限制** " 部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="49f64-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="49f64-122">确保不会阻止您要与之进行协作的来宾域。</span><span class="sxs-lookup"><span data-stu-id="49f64-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="49f64-123">如果您使用多个组织的来宾，您可能希望限制其访问目录数据的能力。</span><span class="sxs-lookup"><span data-stu-id="49f64-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="49f64-124">这将阻止他们看到目录中的其他人是来宾。</span><span class="sxs-lookup"><span data-stu-id="49f64-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="49f64-125">若要执行此操作，请在 " **来宾用户访问限制**" 下，选择 " **来宾用户对属性和目录对象的成员身份的访问权限受到限制** "，并且 **来宾用户访问仅限于其自己的目录对象的属性和成员身份**。</span><span class="sxs-lookup"><span data-stu-id="49f64-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="49f64-126">SharePoint 组织级别的共享设置</span><span class="sxs-lookup"><span data-stu-id="49f64-126">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="49f64-127">为使组织外部的人员能够访问 SharePoint 或 OneDrive 中的文档，SharePoint 和 OneDrive 组织级共享设置必须允许与组织外部的人员共享。</span><span class="sxs-lookup"><span data-stu-id="49f64-127">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="49f64-128">SharePoint 的组织级别设置确定将对单个 SharePoint 网站可用的设置。</span><span class="sxs-lookup"><span data-stu-id="49f64-128">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="49f64-129">网站设置不能比组织级别设置更具有更好的许可。</span><span class="sxs-lookup"><span data-stu-id="49f64-129">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="49f64-130">OneDrive 的组织级别设置决定了将在用户的 OneDrive 库中可用的共享级别。</span><span class="sxs-lookup"><span data-stu-id="49f64-130">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="49f64-131">对于 SharePoint 和 OneDrive，如果要允许未经身份验证的文件和文件夹共享，请选择 " **任何人**"。</span><span class="sxs-lookup"><span data-stu-id="49f64-131">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="49f64-132">如果您想要确保组织外部的人员必须进行身份验证，请选择 " **新建" 和 "现有来宾**"。</span><span class="sxs-lookup"><span data-stu-id="49f64-132">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="49f64-133">*任何* 链接都是最简单的共享方式：组织外部的人员可以在不进行身份验证的情况下打开链接，并且可以自由地将其传递给其他人。</span><span class="sxs-lookup"><span data-stu-id="49f64-133">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="49f64-134">对于 SharePoint，选择组织中的任何网站将需要的 "最高" 设置。</span><span class="sxs-lookup"><span data-stu-id="49f64-134">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 组织级别共享设置的屏幕截图](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="49f64-136">设置 SharePoint 组织级别的共享设置</span><span class="sxs-lookup"><span data-stu-id="49f64-136">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="49f64-137">在 Microsoft 365 管理中心的左侧导航窗格中，单击 " **管理中心**" 下的 " **SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="49f64-137">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="49f64-138">在 SharePoint 管理中心中，在左侧导航窗格中的 " **策略**" 下，单击 " **共享**"。</span><span class="sxs-lookup"><span data-stu-id="49f64-138">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="49f64-139">确保将 SharePoint 或 OneDrive 的外部共享设置为 " **任何人** " 或 **新的和现有的来宾**。</span><span class="sxs-lookup"><span data-stu-id="49f64-139">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="49f64-140"> (请注意，OneDrive 设置不能比 SharePoint 设置更许可。 ) </span><span class="sxs-lookup"><span data-stu-id="49f64-140">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="49f64-141">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="49f64-141">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="49f64-142">SharePoint 组织级别的默认链接设置</span><span class="sxs-lookup"><span data-stu-id="49f64-142">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="49f64-143">默认的文件和文件夹链接设置确定在用户共享文件或文件夹时，默认情况下将向用户显示的链接选项。</span><span class="sxs-lookup"><span data-stu-id="49f64-143">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="49f64-144">如果需要，用户可以在共享之前将链接类型更改为其他选项之一。</span><span class="sxs-lookup"><span data-stu-id="49f64-144">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="49f64-145">请注意，此设置会影响组织中的 SharePoint 网站以及 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="49f64-145">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="49f64-146">从以下任何类型中选择一个链接，当用户共享文件和文件夹时，默认情况下会选择该链接：</span><span class="sxs-lookup"><span data-stu-id="49f64-146">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="49f64-147">**任何具有链接的人** -如果您想要执行大量未经身份验证的文件和文件夹共享，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="49f64-147">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="49f64-148">如果要允许 *任何人* 链接，但担心意外的共享，请考虑其他选项之一作为默认选项。</span><span class="sxs-lookup"><span data-stu-id="49f64-148">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="49f64-149">仅当您已启用 **任何** 共享时，此链接类型才可用。</span><span class="sxs-lookup"><span data-stu-id="49f64-149">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="49f64-150">**仅限组织中的人员** -如果您希望大多数文件和文件夹共享与组织内部的人员共享，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="49f64-150">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="49f64-151">**特定人员** -如果您希望对来宾执行大量文件和文件夹共享，请考虑此选项。</span><span class="sxs-lookup"><span data-stu-id="49f64-151">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="49f64-152">此类型的链接可与来宾配合使用，并要求用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="49f64-152">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 组织级别文件和文件夹共享设置的屏幕截图](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="49f64-154">设置 SharePoint 和 OneDrive 组织级默认链接设置</span><span class="sxs-lookup"><span data-stu-id="49f64-154">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="49f64-155">导航到 SharePoint 管理中心中的 "共享" 页面。</span><span class="sxs-lookup"><span data-stu-id="49f64-155">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="49f64-156">在 " **文件和文件夹链接**" 下，选择要使用的默认共享链接。</span><span class="sxs-lookup"><span data-stu-id="49f64-156">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="49f64-157">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="49f64-157">If you made changes, click **Save**.</span></span>

<span data-ttu-id="49f64-158">若要设置共享链接的权限，请在 " **选择默认情况下为共享链接选择的权限" 下。**</span><span class="sxs-lookup"><span data-stu-id="49f64-158">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="49f64-159">如果不希望未经身份验证的用户对文件和文件夹进行更改，请选择 " **查看** "。</span><span class="sxs-lookup"><span data-stu-id="49f64-159">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="49f64-160">如果要允许未经身份验证的用户对文件和文件夹进行更改，请选择 " **编辑** "。</span><span class="sxs-lookup"><span data-stu-id="49f64-160">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="49f64-161">请注意，以上两个 premission 选项不仅可用于来宾/外部用户，而且适用于内部用户。</span><span class="sxs-lookup"><span data-stu-id="49f64-161">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="49f64-162">您选择的权限选项由自行决定决定。</span><span class="sxs-lookup"><span data-stu-id="49f64-162">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="49f64-163">设置允许与任何人共享的链接的权限</span><span class="sxs-lookup"><span data-stu-id="49f64-163">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="49f64-164">在 " **以下链接可以提供这些权限：** " 子窗格中，</span><span class="sxs-lookup"><span data-stu-id="49f64-164">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="49f64-165">从 " **文件** " 下拉列表中，</span><span class="sxs-lookup"><span data-stu-id="49f64-165">From the **Files** drop-down list,</span></span> 
        1. <span data-ttu-id="49f64-166">如果要允许未经身份验证的用户对文件进行更改，请选择 " **查看和编辑** "。</span><span class="sxs-lookup"><span data-stu-id="49f64-166">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        2. <span data-ttu-id="49f64-167">如果不希望未经身份验证的用户对文件进行更改，请选择 " **查看** "。</span><span class="sxs-lookup"><span data-stu-id="49f64-167">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="49f64-168">从 " **文件夹** " 下拉列表中，</span><span class="sxs-lookup"><span data-stu-id="49f64-168">From the **Folders** drop-down list,</span></span>
        1. <span data-ttu-id="49f64-169">如果您希望允许未经身份验证的用户对文件夹进行更改，请选择 **"查看、编辑和上传** "。</span><span class="sxs-lookup"><span data-stu-id="49f64-169">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        2. <span data-ttu-id="49f64-170">如果不希望未经身份验证的用户对文件夹进行更改，请选择 " **查看** "。</span><span class="sxs-lookup"><span data-stu-id="49f64-170">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="49f64-171">SharePoint 网站级别的共享设置</span><span class="sxs-lookup"><span data-stu-id="49f64-171">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="49f64-172">如果要共享 SharePoint 网站中的文件和文件夹，则还需要检查该网站的网站级共享设置。</span><span class="sxs-lookup"><span data-stu-id="49f64-172">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="49f64-174">设置网站级共享设置</span><span class="sxs-lookup"><span data-stu-id="49f64-174">To set site-level sharing settings</span></span>

1. <span data-ttu-id="49f64-175">在 SharePoint 管理中心中，在左侧导航窗格中，展开 " **网站** "，然后单击 " **活动网站**"。</span><span class="sxs-lookup"><span data-stu-id="49f64-175">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="49f64-176">选择要在其上与来宾共享文件和文件夹的网站。</span><span class="sxs-lookup"><span data-stu-id="49f64-176">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="49f64-177">在所选网站所在行 (中向右滚动) 并单击 " **外部共享** " 列中的任意位置。</span><span class="sxs-lookup"><span data-stu-id="49f64-177">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="49f64-178">从弹出的页面中，单击 " **策略** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="49f64-178">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="49f64-179">在 " **外部共享** " 窗格中，单击 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="49f64-179">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="49f64-180">确保将 "共享" 设置为 " **任何人** " 或 " **新的和现有的来宾**"。</span><span class="sxs-lookup"><span data-stu-id="49f64-180">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="49f64-181">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="49f64-181">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="49f64-182">邀请用户</span><span class="sxs-lookup"><span data-stu-id="49f64-182">Invite users</span></span>

<span data-ttu-id="49f64-183">现在已配置来宾共享设置;因此，用户现在可以与组织外部的人员共享文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="49f64-183">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="49f64-184">有关详细信息，请参阅 [共享 OneDrive 文件和文件夹](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) 以及 [共享 SharePoint 文件或文件夹](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) 。</span><span class="sxs-lookup"><span data-stu-id="49f64-184">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="49f64-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49f64-185">See also</span></span>

[<span data-ttu-id="49f64-186">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="49f64-186">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="49f64-187">与来宾共享时限制文件意外曝光</span><span class="sxs-lookup"><span data-stu-id="49f64-187">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="49f64-188">与 Azure AD B2B 的 SharePoint 和 OneDrive 集成</span><span class="sxs-lookup"><span data-stu-id="49f64-188">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
