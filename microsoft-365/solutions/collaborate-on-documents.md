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
description: 本文将了解如何与来宾协作处理 SharePoint 和 OneDrive 中的文档。
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663507"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="47b03-103">在文档中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="47b03-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="47b03-104">如果需要与组织外部人员协作处理 SharePoint 或 OneDrive 中的文档，可以发送指向文档的共享链接。</span><span class="sxs-lookup"><span data-stu-id="47b03-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="47b03-105">本文将介绍为 SharePoint 和 OneDrive 设置共享链接以满足组织需求所需的 Microsoft 365 配置步骤。</span><span class="sxs-lookup"><span data-stu-id="47b03-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="47b03-106">视频演示</span><span class="sxs-lookup"><span data-stu-id="47b03-106">Video demonstration</span></span>

<span data-ttu-id="47b03-107">此视频演示本文档中所述的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="47b03-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="47b03-108">Azure 外部协作设置</span><span class="sxs-lookup"><span data-stu-id="47b03-108">Azure external collaboration settings</span></span>

<span data-ttu-id="47b03-109">Microsoft 365 中的共享由 Azure Active Directory 中的 [B2B](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)外部协作设置在最高级别管理。</span><span class="sxs-lookup"><span data-stu-id="47b03-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="47b03-110">如果在 Azure AD 中禁用或限制来宾共享，此设置将覆盖在 Microsoft 365 中配置的任何共享设置。</span><span class="sxs-lookup"><span data-stu-id="47b03-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="47b03-111">检查 B2B 外部协作设置以确保不会阻止与来宾共享。</span><span class="sxs-lookup"><span data-stu-id="47b03-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 组织关系设置页面的屏幕截图](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="47b03-113">设置外部协作设置</span><span class="sxs-lookup"><span data-stu-id="47b03-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="47b03-114">登录 Azure Active [https://aad.portal.azure.com](https://aad.portal.azure.com) Directory。</span><span class="sxs-lookup"><span data-stu-id="47b03-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="47b03-115">在左侧导航窗格中，单击 **Azure Active Directory。**</span><span class="sxs-lookup"><span data-stu-id="47b03-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="47b03-116">单击 **"外部标识"。**</span><span class="sxs-lookup"><span data-stu-id="47b03-116">Click **External identities**.</span></span>
4. <span data-ttu-id="47b03-117">在 **"入门"** 屏幕的左侧导航窗格中，单击 **"外部协作设置"。**</span><span class="sxs-lookup"><span data-stu-id="47b03-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="47b03-118">确保 **管理员和来宾邀请** 者角色中的用户可以邀请，**并且成员可以邀请** 都设置为 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="47b03-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="47b03-119">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="47b03-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="47b03-120">记下"协作限制 **"部分** 中的设置。</span><span class="sxs-lookup"><span data-stu-id="47b03-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="47b03-121">确保未阻止要协作的来宾的域。</span><span class="sxs-lookup"><span data-stu-id="47b03-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="47b03-122">如果与多个组织的来宾合作，可能需要限制其访问目录数据的能力。</span><span class="sxs-lookup"><span data-stu-id="47b03-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="47b03-123">这将阻止他们查看目录中的来宾。</span><span class="sxs-lookup"><span data-stu-id="47b03-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="47b03-124">为此，在"来宾用户访问限制"下，选择"来宾用户对目录对象设置的属性和成员身份具有有限访问权限"或"来宾"用户访问仅限于其自己的目录对象的属性和 **成员身份**。</span><span class="sxs-lookup"><span data-stu-id="47b03-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="47b03-125">SharePoint 组织级共享设置</span><span class="sxs-lookup"><span data-stu-id="47b03-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="47b03-126">为了让组织外部人员能够访问 SharePoint 或 OneDrive 中的文档，SharePoint 和 OneDrive 组织级共享设置必须允许与组织外部人员共享。</span><span class="sxs-lookup"><span data-stu-id="47b03-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="47b03-127">SharePoint 的组织级别设置决定了各个 SharePoint 网站可用的设置。</span><span class="sxs-lookup"><span data-stu-id="47b03-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="47b03-128">网站设置不能比组织级别的设置更宽松。</span><span class="sxs-lookup"><span data-stu-id="47b03-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="47b03-129">OneDrive 的组织级别设置确定将在用户的 OneDrive 库中可用的共享级别。</span><span class="sxs-lookup"><span data-stu-id="47b03-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="47b03-130">对于 SharePoint 和 OneDrive，如果要允许未经身份验证的文件和文件夹共享，请选择"任何人 **"。**</span><span class="sxs-lookup"><span data-stu-id="47b03-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="47b03-131">如果要确保组织外部人员必须进行身份验证，请选择 **"新来宾"和"现有来宾"。**</span><span class="sxs-lookup"><span data-stu-id="47b03-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="47b03-132">*任何人* 链接都是最简单的共享方式：组织外部人员无需身份验证即可打开链接，并可以免费将链接传递给其他人。</span><span class="sxs-lookup"><span data-stu-id="47b03-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="47b03-133">对于 SharePoint，选择组织中任何网站所需的最宽松设置。</span><span class="sxs-lookup"><span data-stu-id="47b03-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 组织级别共享设置的屏幕截图](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="47b03-135">设置 SharePoint 组织级共享设置</span><span class="sxs-lookup"><span data-stu-id="47b03-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="47b03-136">在 Microsoft 365 管理中心左侧导航窗格中的"管理中心"下，单击 **"SharePoint"。**</span><span class="sxs-lookup"><span data-stu-id="47b03-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="47b03-137">在 SharePoint 管理中心的左侧导航窗格中，**在"策略**"下，单击"**共享"。**</span><span class="sxs-lookup"><span data-stu-id="47b03-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="47b03-138">确保 SharePoint 或 OneDrive 的外部共享设置为"任何人"**或"\*\*\*\*新来宾"和"现有来宾"。**</span><span class="sxs-lookup"><span data-stu-id="47b03-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="47b03-139"> (请注意，OneDrive 设置不能比 SharePoint 设置更宽松。) </span><span class="sxs-lookup"><span data-stu-id="47b03-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="47b03-140">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="47b03-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="47b03-141">SharePoint 组织级别的默认链接设置</span><span class="sxs-lookup"><span data-stu-id="47b03-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="47b03-142">默认文件和文件夹链接设置确定在用户共享文件或文件夹时默认向用户显示的链接选项。</span><span class="sxs-lookup"><span data-stu-id="47b03-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="47b03-143">如果需要，用户可以在共享之前将链接类型更改为其他选项之一。</span><span class="sxs-lookup"><span data-stu-id="47b03-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="47b03-144">请记住，此设置会影响您组织的 SharePoint 网站以及 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="47b03-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="47b03-145">从以下任一类型中选择一个链接，然后在用户共享文件和文件夹时默认选择该链接：</span><span class="sxs-lookup"><span data-stu-id="47b03-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="47b03-146">**具有链接的任何人** - 如果希望执行大量未经身份验证的文件和文件夹共享，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="47b03-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="47b03-147">如果要允许"任何人 *"* 链接，但担心意外的未经身份验证的共享，请考虑使用其他选项之一作为默认选项。</span><span class="sxs-lookup"><span data-stu-id="47b03-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="47b03-148">此链接类型仅在启用了"任何人共享 **"时** 可用。</span><span class="sxs-lookup"><span data-stu-id="47b03-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="47b03-149">**仅组织内部人员** - 如果希望大多数文件和文件夹共享与组织内部人员共享，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="47b03-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="47b03-150">**特定人员** - 如果你希望与来宾共享大量文件和文件夹，请考虑使用此选项。</span><span class="sxs-lookup"><span data-stu-id="47b03-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="47b03-151">此类链接适用于来宾，要求他们进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="47b03-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 组织级别文件和文件夹共享设置的屏幕截图](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="47b03-153">设置 SharePoint 和 OneDrive 组织级别的默认链接设置</span><span class="sxs-lookup"><span data-stu-id="47b03-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="47b03-154">导航到 SharePoint 管理中心中的"共享"页面。</span><span class="sxs-lookup"><span data-stu-id="47b03-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="47b03-155">在 **"文件和文件夹链接**"下，选择要使用的默认共享链接。</span><span class="sxs-lookup"><span data-stu-id="47b03-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="47b03-156">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="47b03-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="47b03-157">若要设置共享链接的权限，在"选择默认为共享链接 **选择的权限"下。**</span><span class="sxs-lookup"><span data-stu-id="47b03-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="47b03-158">如果您 **不希望** 未经身份验证的用户对文件和文件夹进行更改，请选择"查看"。</span><span class="sxs-lookup"><span data-stu-id="47b03-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="47b03-159">如果要 **允许** 未经身份验证的用户对文件和文件夹进行更改，请选择"编辑"。</span><span class="sxs-lookup"><span data-stu-id="47b03-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="47b03-160">请注意，上述两个预提交选项不仅适用于来宾/外部用户，还可以应用于内部用户。</span><span class="sxs-lookup"><span data-stu-id="47b03-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="47b03-161">您选择的权限选项由自行决定。</span><span class="sxs-lookup"><span data-stu-id="47b03-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="47b03-162">设置允许与任何人共享的链接的权限</span><span class="sxs-lookup"><span data-stu-id="47b03-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="47b03-163">在 **"这些链接"下，可以授予** 以下权限：子窗格、</span><span class="sxs-lookup"><span data-stu-id="47b03-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="47b03-164">从 **"文件** "下拉列表中，</span><span class="sxs-lookup"><span data-stu-id="47b03-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="47b03-165">如果要 **允许** 未经身份验证的用户对文件进行更改，请选择"查看和编辑"。</span><span class="sxs-lookup"><span data-stu-id="47b03-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="47b03-166">如果您 **不希望** 未经身份验证的用户对文件进行更改，请选择"查看"。</span><span class="sxs-lookup"><span data-stu-id="47b03-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="47b03-167">从 **"文件夹** "下拉列表中，</span><span class="sxs-lookup"><span data-stu-id="47b03-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="47b03-168">如果要 **允许** 未经身份验证的用户对文件夹进行更改，请选择"查看、编辑和上载"。</span><span class="sxs-lookup"><span data-stu-id="47b03-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="47b03-169">如果您 **不希望** 未经身份验证的用户对文件夹进行更改，请选择"查看"。</span><span class="sxs-lookup"><span data-stu-id="47b03-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="47b03-170">SharePoint 网站级共享设置</span><span class="sxs-lookup"><span data-stu-id="47b03-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="47b03-171">如果要共享 SharePoint 网站中的文件和文件夹，还需要检查该网站的网站级共享设置。</span><span class="sxs-lookup"><span data-stu-id="47b03-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="47b03-173">设置网站级共享设置</span><span class="sxs-lookup"><span data-stu-id="47b03-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="47b03-174">在 SharePoint 管理中心的左侧导航窗格中，展开 **"** 网站"，然后单击 **"活动网站"。**</span><span class="sxs-lookup"><span data-stu-id="47b03-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="47b03-175">选择要与来宾共享文件和文件夹的网站。</span><span class="sxs-lookup"><span data-stu-id="47b03-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="47b03-176">在选定网站 (的行中向右滚动，) 单击"外部共享"列中 **的** 任意位置。</span><span class="sxs-lookup"><span data-stu-id="47b03-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="47b03-177">在弹出的页面中，单击"策略 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="47b03-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="47b03-178">在"**外部共享"** 窗格下，单击"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="47b03-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="47b03-179">确保共享设置为"任何人 **"或\*\*\*\*"新来宾"和"现有来宾"。**</span><span class="sxs-lookup"><span data-stu-id="47b03-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="47b03-180">如果进行了任何更改，请单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="47b03-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="47b03-181">邀请用户</span><span class="sxs-lookup"><span data-stu-id="47b03-181">Invite users</span></span>

<span data-ttu-id="47b03-182">来宾共享设置现已配置;以便用户现在可以与组织外部人员共享文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="47b03-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="47b03-183">有关详细信息[，请参阅"共享 OneDrive 文件和文件夹](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07)["和"共享 SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)文件或文件夹"。</span><span class="sxs-lookup"><span data-stu-id="47b03-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="47b03-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47b03-184">See also</span></span>

[<span data-ttu-id="47b03-185">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="47b03-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="47b03-186">与来宾共享时限制文件意外曝光</span><span class="sxs-lookup"><span data-stu-id="47b03-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="47b03-187">SharePoint 和 OneDrive 与 Azure AD B2B 集成</span><span class="sxs-lookup"><span data-stu-id="47b03-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
