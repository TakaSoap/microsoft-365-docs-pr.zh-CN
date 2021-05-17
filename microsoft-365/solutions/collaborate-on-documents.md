---
title: 在文档中与来宾协作
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
description: 本文将了解如何与来宾协作处理 SharePoint OneDrive。
ms.openlocfilehash: 9158ec7692ef90eb2e270242472fceb10d0e60b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920224"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="3d697-103">在文档中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="3d697-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="3d697-104">如果需要与组织外部人员协作处理SharePoint或OneDrive文档，您可以向这些人员发送一个指向该文档的共享链接。</span><span class="sxs-lookup"><span data-stu-id="3d697-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="3d697-105">本文将介绍为 Microsoft 365 和 SharePoint 设置共享链接所需的 OneDrive 配置步骤，以满足组织的需要。</span><span class="sxs-lookup"><span data-stu-id="3d697-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="3d697-106">视频演示</span><span class="sxs-lookup"><span data-stu-id="3d697-106">Video demonstration</span></span>

<span data-ttu-id="3d697-107">该视频展示了本文档中介绍的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="3d697-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="3d697-108">Azure 外部协作设置</span><span class="sxs-lookup"><span data-stu-id="3d697-108">Azure external collaboration settings</span></span>

<span data-ttu-id="3d697-109">Microsoft 365 中的共享在最高级别由 [Azure Active Directory 中的 B2B 外部协作设置](/azure/active-directory/external-identities/delegate-invitations) 管理。</span><span class="sxs-lookup"><span data-stu-id="3d697-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="3d697-110">如果在 Azure AD 中禁用或限制来宾共享，则此设置将覆盖在 Azure AD 中配置的任何Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3d697-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="3d697-111">检查 B2B 外部协作设置，确保不会阻止与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="3d697-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 组织关系设置页面的屏幕截图](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="3d697-113">设置外部协作设置</span><span class="sxs-lookup"><span data-stu-id="3d697-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="3d697-114">在 [https://aad.portal.azure.com](https://aad.portal.azure.com) 上登录到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="3d697-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="3d697-115">在左侧导航窗格中，单击 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="3d697-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="3d697-116">单击 **“外部标识”**。</span><span class="sxs-lookup"><span data-stu-id="3d697-116">Click **External identities**.</span></span>
4. <span data-ttu-id="3d697-117">在 **“入门”** 屏幕的左侧导航窗格中，单击 **“外部协作设置”**。</span><span class="sxs-lookup"><span data-stu-id="3d697-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="3d697-118">确保 **“管理员和来宾邀请者角色中的用户可以邀请”**，且 **“成员可以邀请”** 同时设置为 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="3d697-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="3d697-119">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="3d697-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="3d697-120">请注意 **“协作限制"** 部分的设置。</span><span class="sxs-lookup"><span data-stu-id="3d697-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="3d697-121">确保不会阻止要协作来宾的域。</span><span class="sxs-lookup"><span data-stu-id="3d697-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="3d697-122">如果与多个组织的来宾合作，可能需要限制其访问目录数据的能力。 </span><span class="sxs-lookup"><span data-stu-id="3d697-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="3d697-123">这将阻止他们查看目录中的来宾。</span><span class="sxs-lookup"><span data-stu-id="3d697-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="3d697-124">为此，在 **“来宾用户访问限制”** 下，选择 **“来宾用户具有对目录对象设置的属性和成员身份的有限访问权限”** 或 **“来宾用户访问仅限于其自己的目录对象的属性和成员身份”**。</span><span class="sxs-lookup"><span data-stu-id="3d697-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="3d697-125">SharePoint组织级别的共享设置</span><span class="sxs-lookup"><span data-stu-id="3d697-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="3d697-126">为了使组织外部人员能够访问 SharePoint 或 OneDrive 中的文档，SharePoint 和 OneDrive 组织级别的共享设置必须允许与组织外部人员共享。</span><span class="sxs-lookup"><span data-stu-id="3d697-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="3d697-127">网站的组织级别SharePoint确定各个网站可用的SharePoint设置。</span><span class="sxs-lookup"><span data-stu-id="3d697-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="3d697-128">网站设置不能比组织级别设置更宽松。</span><span class="sxs-lookup"><span data-stu-id="3d697-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="3d697-129">用户的组织级别设置OneDrive确定将在用户的管理库中可用的OneDrive级别。</span><span class="sxs-lookup"><span data-stu-id="3d697-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="3d697-130">For SharePoint and OneDrive， if you want to allow unauthenticated file and folder sharing， choose **Anyone**.</span><span class="sxs-lookup"><span data-stu-id="3d697-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="3d697-131">如果希望确保组织外部人员必须进行身份验证，请选择"**新来宾和现有来宾"。**</span><span class="sxs-lookup"><span data-stu-id="3d697-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="3d697-132">*任何人* 链接是最简单的共享方式：组织外部人员无需身份验证即可打开链接，并可以自由将链接传递给其他人。</span><span class="sxs-lookup"><span data-stu-id="3d697-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="3d697-133">对于SharePoint，请选择组织中任何网站所需的最宽松设置。</span><span class="sxs-lookup"><span data-stu-id="3d697-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 组织级别共享设置的屏幕截图](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="3d697-135">设置 SharePoint 组织级共享设置</span><span class="sxs-lookup"><span data-stu-id="3d697-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="3d697-136">在 Microsoft 365 管理中心左侧导航窗格中的 **“管理中心”** 下，单击 **“SharePoint”**。</span><span class="sxs-lookup"><span data-stu-id="3d697-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="3d697-137">In the SharePoint admin center， in the left navigation pane， under **Policies**， click **Sharing**.</span><span class="sxs-lookup"><span data-stu-id="3d697-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="3d697-138">确保将用户或SharePoint的外部OneDrive设置为"任何人"或"**新来宾和现有来宾"。** </span><span class="sxs-lookup"><span data-stu-id="3d697-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="3d697-139"> (请注意，OneDrive设置不能比 SharePoint 设置更宽松。) </span><span class="sxs-lookup"><span data-stu-id="3d697-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="3d697-140">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="3d697-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="3d697-141">SharePoint 组织级别的默认链接设置</span><span class="sxs-lookup"><span data-stu-id="3d697-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="3d697-142">默认文件和文件夹链接设置确定在用户共享文件或文件夹时默认向用户显示的链接选项。</span><span class="sxs-lookup"><span data-stu-id="3d697-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="3d697-143">如果需要，用户可以在共享之前将链接类型更改为其他选项之一。</span><span class="sxs-lookup"><span data-stu-id="3d697-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="3d697-144">请记住，此设置会影响SharePoint网站和网站OneDrive。</span><span class="sxs-lookup"><span data-stu-id="3d697-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="3d697-145">从以下任一类型中选择一个链接，然后在用户共享文件和文件夹时默认选择该链接：</span><span class="sxs-lookup"><span data-stu-id="3d697-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="3d697-146">**具有链接的** 任何人 - 如果希望执行大量未经身份验证的文件和文件夹共享，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="3d697-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="3d697-147">如果希望允许 *“任何人”* 链接，但担心意外的未经身份验证的共享，请考虑使用其他选项之一作为默认选项。</span><span class="sxs-lookup"><span data-stu-id="3d697-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="3d697-148">此链接类型仅在启用 **”任何人“** 共享时可用。</span><span class="sxs-lookup"><span data-stu-id="3d697-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="3d697-149">**仅组织内部人员** - 如果希望大多数文件和文件夹共享是与组织内部人员共享，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="3d697-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="3d697-150">**特定人员** - 如果希望与来宾进行大量文件和文件夹共享，请考虑此选项。</span><span class="sxs-lookup"><span data-stu-id="3d697-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="3d697-151">此类链接适用于来宾，且要求他们进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="3d697-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 组织级别文件和文件夹共享设置的屏幕截图](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="3d697-153">设置网站SharePoint OneDrive组织级别的默认链接设置</span><span class="sxs-lookup"><span data-stu-id="3d697-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="3d697-154">导航到 SharePoint 管理中心的"共享"页面。</span><span class="sxs-lookup"><span data-stu-id="3d697-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="3d697-155">在 **“文件夹链接”** 下，选择要使用的默认共享链接。</span><span class="sxs-lookup"><span data-stu-id="3d697-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="3d697-156">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="3d697-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="3d697-157">若要设置共享链接的权限，在"选择默认为共享链接 **选择的权限"下。**</span><span class="sxs-lookup"><span data-stu-id="3d697-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="3d697-158">如果 **不希望** 未经身份验证的用户对文件和文件夹进行更改，请选择"查看"。</span><span class="sxs-lookup"><span data-stu-id="3d697-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="3d697-159">如果要 **允许** 未经身份验证的用户对文件和文件夹进行更改，请选择"编辑"。</span><span class="sxs-lookup"><span data-stu-id="3d697-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="3d697-160">请注意，上述两个预提交选项不仅适用于来宾/外部用户，还可以应用于内部用户。</span><span class="sxs-lookup"><span data-stu-id="3d697-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="3d697-161">您选择的权限选项由自行决定。</span><span class="sxs-lookup"><span data-stu-id="3d697-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="3d697-162">设置允许与任何人共享的链接的权限</span><span class="sxs-lookup"><span data-stu-id="3d697-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="3d697-163">在" **这些链接可以授予以下权限"下：** 子窗格</span><span class="sxs-lookup"><span data-stu-id="3d697-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="3d697-164">从 **"文件** "下拉列表中，</span><span class="sxs-lookup"><span data-stu-id="3d697-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="3d697-165">如果要 **允许未经** 身份验证的用户对文件进行更改，请选择"查看和编辑"。</span><span class="sxs-lookup"><span data-stu-id="3d697-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="3d697-166">如果您 **不希望** 未经身份验证的用户对文件进行更改，请选择"查看"。</span><span class="sxs-lookup"><span data-stu-id="3d697-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="3d697-167">从 **"文件夹** "下拉列表中，</span><span class="sxs-lookup"><span data-stu-id="3d697-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="3d697-168">如果要 **允许未经身份验证的用户** 对文件夹进行更改，请选择"查看、编辑和上载"。</span><span class="sxs-lookup"><span data-stu-id="3d697-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="3d697-169">如果 **不希望** 未经身份验证的用户对文件夹进行更改，请选择"查看"。</span><span class="sxs-lookup"><span data-stu-id="3d697-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="3d697-170">SharePoint 网站级别共享设置</span><span class="sxs-lookup"><span data-stu-id="3d697-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="3d697-171">如果要共享网站中的文件和文件夹SharePoint，还需要检查该网站的网站级别共享设置。</span><span class="sxs-lookup"><span data-stu-id="3d697-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="3d697-173">设置网站级别共享设置</span><span class="sxs-lookup"><span data-stu-id="3d697-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="3d697-174">在 SharePoint 管理中心的左侧导航栏中，展开 **“网站”**，然后单击 **“活动网站”**。</span><span class="sxs-lookup"><span data-stu-id="3d697-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="3d697-175">选择要与来宾共享文件和文件夹的网站。</span><span class="sxs-lookup"><span data-stu-id="3d697-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="3d697-176">在选定网站 (的行中向右滚动，) "外部共享"列中 **的任意位置** 单击。</span><span class="sxs-lookup"><span data-stu-id="3d697-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="3d697-177">在弹出的页面中，单击"策略 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3d697-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="3d697-178">在"外部 **共享"窗格下**，单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="3d697-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="3d697-179">确保将共享设置为 **“任何人”** 或 **“新来宾和现有来宾”**。</span><span class="sxs-lookup"><span data-stu-id="3d697-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="3d697-180">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="3d697-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="3d697-181">邀请用户</span><span class="sxs-lookup"><span data-stu-id="3d697-181">Invite users</span></span>

<span data-ttu-id="3d697-182">来宾共享设置现已配置;以便用户现在可以与组织外部人员共享文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="3d697-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="3d697-183">有关详细信息[，OneDrive共享文件和文件夹和](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07)[共享 SharePoint 文件或](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)文件夹。</span><span class="sxs-lookup"><span data-stu-id="3d697-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d697-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d697-184">See also</span></span>

[<span data-ttu-id="3d697-185">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="3d697-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="3d697-186">与来宾共享时限制文件意外曝光</span><span class="sxs-lookup"><span data-stu-id="3d697-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="3d697-187">SharePoint 和 OneDrive 与 Azure AD B2B 的集成</span><span class="sxs-lookup"><span data-stu-id="3d697-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)