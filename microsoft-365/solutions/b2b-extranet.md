---
title: 创建托管有来宾的 B2B 外联网
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
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: 了解如何使用合作伙伴组织的托管来宾创建 B2B Extranet 站点或团队。
ms.openlocfilehash: d76951da5d8affa1dac08cbdc68a91329ca069ed
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538239"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="800bc-103">创建托管有来宾的 B2B 外联网</span><span class="sxs-lookup"><span data-stu-id="800bc-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="800bc-104">可以使用["Azure Active Directory](/azure/active-directory/governance/entitlement-management-overview)管理"创建 B2B Extranet，以与使用"授权管理"Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="800bc-104">You can use [Azure Active Directory Entitlement Management](/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="800bc-105">这允许用户在 Extranet 网站或团队中自行注册，并可以通过审批工作流接收访问权限。</span><span class="sxs-lookup"><span data-stu-id="800bc-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="800bc-106">通过这种共享协作资源的方法，合作伙伴组织可以帮助维护和批准来宾，从而减少 IT 部门的负担，并允许最熟悉协作协议的人管理用户访问。</span><span class="sxs-lookup"><span data-stu-id="800bc-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="800bc-107">本文逐步介绍了创建资源包的步骤 (在这种情况下，创建一个站点或工作组) 可通过自助服务访问注册模型与合作伙伴组织共享。</span><span class="sxs-lookup"><span data-stu-id="800bc-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="800bc-108">在开始之前，创建要与合作伙伴组织共享的站点或团队，并启用它进行来宾共享。</span><span class="sxs-lookup"><span data-stu-id="800bc-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="800bc-109">有关详细信息 [，请参阅在网站](collaborate-in-site.md) 中与来宾协作或与 [团队中的](collaborate-as-team.md) 来宾协作。</span><span class="sxs-lookup"><span data-stu-id="800bc-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="800bc-110">我们还建议您 [查看创建安全的](create-secure-guest-sharing-environment.md) 来宾共享环境，了解可用于在与来宾协作时维护治理策略的安全与合规性功能。</span><span class="sxs-lookup"><span data-stu-id="800bc-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="800bc-111">许可要求</span><span class="sxs-lookup"><span data-stu-id="800bc-111">License requirements</span></span>

<span data-ttu-id="800bc-112">使用此功能需要 Azure AD 高级版 P2 许可证。</span><span class="sxs-lookup"><span data-stu-id="800bc-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="800bc-113">专用云（如 Azure Germany 和 Azure China 21Vianet）目前不可用。</span><span class="sxs-lookup"><span data-stu-id="800bc-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="800bc-114">视频演示</span><span class="sxs-lookup"><span data-stu-id="800bc-114">Video demonstration</span></span>

<span data-ttu-id="800bc-115">此视频演示了本文中介绍的过程。</span><span class="sxs-lookup"><span data-stu-id="800bc-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="800bc-116">连接合作伙伴组织</span><span class="sxs-lookup"><span data-stu-id="800bc-116">Connect the partner organization</span></span>

<span data-ttu-id="800bc-117">为了邀请来自合作伙伴组织的来宾，你需要将合作伙伴的域添加为 Azure Active Directory 中的连接组织。</span><span class="sxs-lookup"><span data-stu-id="800bc-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="800bc-118">添加已连接的组织</span><span class="sxs-lookup"><span data-stu-id="800bc-118">To add a connected organization</span></span>
1. <span data-ttu-id="800bc-119">在 ["Azure Active Directory"](https://aad.portal.azure.com)中，单击 **"标识治理"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="800bc-120">单击"**连接的组织"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="800bc-121">单击 **"添加已连接的组织"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="800bc-122">键入组织的名称和说明，然后单击"下一步：**目录 + 域"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="800bc-123">单击 **"添加目录 + 域"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="800bc-124">键入要连接的组织的域，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="800bc-125">单击 **连接"，** 然后单击"下一 **步： 发起人"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="800bc-126">添加来自组织或要连接到要批准来宾访问的组织的人员。</span><span class="sxs-lookup"><span data-stu-id="800bc-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="800bc-127">单击“**下一步: 评审+创建**”。</span><span class="sxs-lookup"><span data-stu-id="800bc-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="800bc-128">查看已选择的设置，然后单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![已连接组织页面的屏幕截图Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="800bc-130">选择要共享的资源</span><span class="sxs-lookup"><span data-stu-id="800bc-130">Choose the resources to share</span></span>

<span data-ttu-id="800bc-131">选择要与合作伙伴组织共享的资源的第一步是创建包含这些资源的目录。</span><span class="sxs-lookup"><span data-stu-id="800bc-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="800bc-132">创建目录</span><span class="sxs-lookup"><span data-stu-id="800bc-132">To create a catalog</span></span>
1. <span data-ttu-id="800bc-133">在 ["Azure Active Directory"](https://aad.portal.azure.com)中，单击 **"标识治理"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="800bc-134">单击 **"目录"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="800bc-135">单击 **"新建目录"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="800bc-136">键入目录的名称和说明，并确保为外部用户启用和启用 **两者** 都设置为 **是**。</span><span class="sxs-lookup"><span data-stu-id="800bc-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="800bc-137">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="800bc-137">Click **Create**.</span></span>

   ![Identity Governance 中的目录页面Azure Active Directory屏幕截图](../media/identity-governance-catalogs.png)

<span data-ttu-id="800bc-139">创建目录后，添加SharePoint要与合作伙伴组织共享的网站或团队。</span><span class="sxs-lookup"><span data-stu-id="800bc-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="800bc-140">向目录添加资源</span><span class="sxs-lookup"><span data-stu-id="800bc-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="800bc-141">在 Azure AD Identity Governance 中，单击 **"目录"，** 然后单击要添加资源的目录。</span><span class="sxs-lookup"><span data-stu-id="800bc-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="800bc-142">单击 **"资源**"，然后单击"**添加资源"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="800bc-143">选择要包括在 extranet SharePoint团队或网站，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Identity Governance 中的目录资源Azure Active Directory屏幕截图](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="800bc-145">定义要共享的资源后，下一步是创建访问包，该包定义授予合作伙伴用户的访问权限类型以及请求访问的新合作伙伴用户的审批过程。</span><span class="sxs-lookup"><span data-stu-id="800bc-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="800bc-146">创建访问包</span><span class="sxs-lookup"><span data-stu-id="800bc-146">To create an access package</span></span>
1. <span data-ttu-id="800bc-147">在 Azure AD Identity Governance 中，单击 **"目录"，** 然后单击要创建访问包的目录。</span><span class="sxs-lookup"><span data-stu-id="800bc-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="800bc-148">单击 **"访问程序包**"，然后单击"**新建访问包"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="800bc-149">键入访问包的名称和说明，然后单击下一步： **资源角色**。</span><span class="sxs-lookup"><span data-stu-id="800bc-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="800bc-150">从目录中选择要用于 Extranet 的资源。</span><span class="sxs-lookup"><span data-stu-id="800bc-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="800bc-151">对于每个资源，在" **角色** "列中，选择要授予使用 Extranet 的来宾的用户角色。</span><span class="sxs-lookup"><span data-stu-id="800bc-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="800bc-152">单击 **"下一步：请求"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="800bc-153">在 **"可以请求访问的用户"下**，**选择"对于不在目录中的用户"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="800bc-154">确保选中"**特定连接的组织**"选项，然后单击"添加 **目录"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="800bc-155">选择之前添加的已连接组织，然后单击"选择 **"**</span><span class="sxs-lookup"><span data-stu-id="800bc-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="800bc-156">在 **"审批"** 下，**为"需要\*\*\*\*审批"选择"是"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="800bc-157">在 **"第一个审批者**"下，选择之前添加的发起人之一或选择特定用户。</span><span class="sxs-lookup"><span data-stu-id="800bc-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="800bc-158">单击 **"添加回退** "并选择回退审批者。</span><span class="sxs-lookup"><span data-stu-id="800bc-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="800bc-159">在 **"启用"** 下，选择"**是"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="800bc-160">单击 **下一步： 生命周期**。</span><span class="sxs-lookup"><span data-stu-id="800bc-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="800bc-161">Choose the expiration and access review settings that you want to use， and then click **Next： Review + Create**.</span><span class="sxs-lookup"><span data-stu-id="800bc-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="800bc-162">查看设置，然后单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-162">Review your settings, and then click **Create**.</span></span>

    ![用户标识管理中的访问包屏幕Azure Active Directory屏幕截图](../media/identity-governance-access-packages.png)

<span data-ttu-id="800bc-164">如果你正在与大型组织合作，你可能想要隐藏访问包。</span><span class="sxs-lookup"><span data-stu-id="800bc-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="800bc-165">如果包处于隐藏状态，则合作伙伴组织的用户将不会在"我的访问"门户 *上看到该* 包。</span><span class="sxs-lookup"><span data-stu-id="800bc-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="800bc-166">相反，必须发送直接链接以注册程序包。</span><span class="sxs-lookup"><span data-stu-id="800bc-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="800bc-167">隐藏访问包可以减少不恰当的访问请求数，还有助于保留在合作伙伴组织的门户中组织的可用访问包。</span><span class="sxs-lookup"><span data-stu-id="800bc-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="800bc-168">将访问包设置为隐藏</span><span class="sxs-lookup"><span data-stu-id="800bc-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="800bc-169">在 Azure AD Identity Governance 中，单击 **"访问程序包"，** 然后单击访问包。</span><span class="sxs-lookup"><span data-stu-id="800bc-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="800bc-170">在"**概述"页上**，单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="800bc-171">在 **"属性"** 下，**为"隐藏**"**选择**"是"，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="800bc-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![编辑访问包属性屏幕的屏幕截图](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="800bc-173">邀请合作伙伴用户</span><span class="sxs-lookup"><span data-stu-id="800bc-173">Invite partner users</span></span>

<span data-ttu-id="800bc-174">如果将访问包设置为隐藏，则需要向合作伙伴组织发送直接链接，以便他们可以请求访问你的站点或团队。</span><span class="sxs-lookup"><span data-stu-id="800bc-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="800bc-175">查找访问门户链接</span><span class="sxs-lookup"><span data-stu-id="800bc-175">To find the access portal link</span></span>
1. <span data-ttu-id="800bc-176">在 Azure AD Identity Governance 中，单击 **"访问程序包"，** 然后单击访问包。</span><span class="sxs-lookup"><span data-stu-id="800bc-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="800bc-177">在" **概述"** 页上，单击"我的访问门户"链接 **的** "复制到 **剪贴板"链接**。</span><span class="sxs-lookup"><span data-stu-id="800bc-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![包含访问门户链接的访问包属性的屏幕截图](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="800bc-179">复制链接后，你可以将其与合作伙伴组织的联系人共享，他们可以将其发送给协作团队中的用户。</span><span class="sxs-lookup"><span data-stu-id="800bc-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="800bc-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="800bc-180">See Also</span></span>

[<span data-ttu-id="800bc-181">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="800bc-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)