---
title: 创建托管有来宾的 B2B 外联网
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
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: 了解如何使用合作伙伴组织中的受管理的来宾用户创建 B2B extranet 网站或团队。
ms.openlocfilehash: b052598f86072776f69e538c70a6bd56d79c3f81
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030049"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="eabe0-103">创建托管有来宾的 B2B 外联网</span><span class="sxs-lookup"><span data-stu-id="eabe0-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="eabe0-104">您可以使用 [Azure Active Directory 权限管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) 创建 B2B extranet，以与使用 Azure Active Directory 的合作伙伴组织进行协作。</span><span class="sxs-lookup"><span data-stu-id="eabe0-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="eabe0-105">这样，用户可以在 extranet 网站或团队中自行注册，并通过审批工作流接收访问权限。</span><span class="sxs-lookup"><span data-stu-id="eabe0-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="eabe0-106">通过这种共享资源进行协作的方法，合作伙伴组织可以帮助他们在他们的终端上维护和批准来宾用户，减少 IT 部门的负担，并允许最熟悉协作协议的人管理用户访问。</span><span class="sxs-lookup"><span data-stu-id="eabe0-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guest users on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="eabe0-107">本文逐步介绍了在此示例中创建资源包的步骤 (在此示例中，可以通过自助服务访问注册模型与合作伙伴组织共享的网站或团队) 。</span><span class="sxs-lookup"><span data-stu-id="eabe0-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="eabe0-108">在开始之前，请创建要与合作伙伴组织共享的网站或团队，并为其启用来宾共享。</span><span class="sxs-lookup"><span data-stu-id="eabe0-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="eabe0-109">有关详细信息，请参阅 [在网站中与来宾进行协作](collaborate-in-site.md) 或 [与团队中的来宾协作](collaborate-as-team.md) 。</span><span class="sxs-lookup"><span data-stu-id="eabe0-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="eabe0-110">我们还建议您查看 " [创建安全来宾共享环境](create-secure-guest-sharing-environment.md) "，以获取有关安全和合规性功能的信息，您可以使用这些功能来帮助维护与来宾协作时的管理策略。</span><span class="sxs-lookup"><span data-stu-id="eabe0-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="eabe0-111">许可要求</span><span class="sxs-lookup"><span data-stu-id="eabe0-111">License requirements</span></span>

<span data-ttu-id="eabe0-112">若要使用此功能，需要使用 Azure AD 高级 P2 许可证。</span><span class="sxs-lookup"><span data-stu-id="eabe0-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="eabe0-113">专用云（如 Azure 德国和 Azure 中国世纪）目前不可使用。</span><span class="sxs-lookup"><span data-stu-id="eabe0-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="eabe0-114">视频演示</span><span class="sxs-lookup"><span data-stu-id="eabe0-114">Video demonstration</span></span>

<span data-ttu-id="eabe0-115">该视频演示了本文中介绍的过程。</span><span class="sxs-lookup"><span data-stu-id="eabe0-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="eabe0-116">连接合作伙伴组织</span><span class="sxs-lookup"><span data-stu-id="eabe0-116">Connect the partner organization</span></span>

<span data-ttu-id="eabe0-117">为了从合作伙伴组织中邀请来宾，您需要在 Azure Active Directory 中将合作伙伴的域添加为连接的组织。</span><span class="sxs-lookup"><span data-stu-id="eabe0-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="eabe0-118">添加已连接的组织</span><span class="sxs-lookup"><span data-stu-id="eabe0-118">To add a connected organization</span></span>
1. <span data-ttu-id="eabe0-119">在 " [Azure Active Directory](https://aad.portal.azure.com)" 中，单击 " **身份治理** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="eabe0-120">单击 " **连接的组织** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="eabe0-121">单击 " **添加已连接的组织** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="eabe0-122">键入组织的名称和说明，然后单击 " **下一步： Directory + 域** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="eabe0-123">单击 " **添加目录 + 域** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="eabe0-124">键入要连接的组织的域，然后单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="eabe0-125">单击 " **连接** "，然后单击 " **下一步：主办方** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-125">Click **Connect** , and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="eabe0-126">添加你的组织或你要连接到的组织中的人员，以批准来宾用户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="eabe0-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guest users.</span></span>
10. <span data-ttu-id="eabe0-127">单击 " **下一步：审阅 + 创建** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="eabe0-128">查看您选择的设置，然后单击 " **创建** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Azure Active Directory 中的 "连接的组织" 页面的屏幕截图](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="eabe0-130">选择要共享的资源</span><span class="sxs-lookup"><span data-stu-id="eabe0-130">Choose the resources to share</span></span>

<span data-ttu-id="eabe0-131">选择要与合作伙伴组织共享的资源的第一步是创建要包含它们的目录。</span><span class="sxs-lookup"><span data-stu-id="eabe0-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="eabe0-132">创建目录</span><span class="sxs-lookup"><span data-stu-id="eabe0-132">To create a catalog</span></span>
1. <span data-ttu-id="eabe0-133">在 " [Azure Active Directory](https://aad.portal.azure.com)" 中，单击 " **身份治理** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="eabe0-134">单击 " **目录** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="eabe0-135">单击 " **新建目录** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="eabe0-136">键入目录的名称和说明，并确保 **为外部用户\*\*\*\*启用** 和启用两者都设置为 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="eabe0-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="eabe0-137">单击“ **创建** ”。</span><span class="sxs-lookup"><span data-stu-id="eabe0-137">Click **Create**.</span></span>

   ![Azure Active Directory 标识管理中的目录页面的屏幕截图](../media/identity-governance-catalogs.png)

<span data-ttu-id="eabe0-139">创建目录后，添加要与合作伙伴组织共享的 SharePoint 网站或团队。</span><span class="sxs-lookup"><span data-stu-id="eabe0-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="eabe0-140">将资源添加到目录</span><span class="sxs-lookup"><span data-stu-id="eabe0-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="eabe0-141">在 Azure AD 标识管理中，单击 " **目录** "，然后单击要在其中添加资源的目录。</span><span class="sxs-lookup"><span data-stu-id="eabe0-141">In Azure AD Identity Governance, click **Catalogs** , and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="eabe0-142">单击 " **资源** "，然后单击 " **添加资源** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="eabe0-143">选择要包含在 extranet 中的团队或 SharePoint 网站，然后单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Azure Active Directory 标识管理中的 "目录资源" 页面的屏幕截图](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="eabe0-145">在定义了要共享的资源后，下一步是创建访问包，该程序包将定义合作伙伴用户授予的访问类型和请求访问的新合作伙伴用户的审批流程。</span><span class="sxs-lookup"><span data-stu-id="eabe0-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="eabe0-146">创建访问包</span><span class="sxs-lookup"><span data-stu-id="eabe0-146">To create an access package</span></span>
1. <span data-ttu-id="eabe0-147">在 Azure AD 标识管理中，单击 " **目录** "，然后单击要在其中创建访问包的目录。</span><span class="sxs-lookup"><span data-stu-id="eabe0-147">In Azure AD Identity Governance, click **Catalogs** , and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="eabe0-148">单击 " **访问包** "，然后单击 " **新建 Access 程序包** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-148">Click **Access packages** , and then click **New access package**.</span></span>
3. <span data-ttu-id="eabe0-149">键入访问包的名称和说明，然后单击 " **下一步：资源角色** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="eabe0-150">从目录中选择要用于 extranet 的资源。</span><span class="sxs-lookup"><span data-stu-id="eabe0-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="eabe0-151">对于每个资源，在 " **角色** " 列中，选择要为使用 extranet 的来宾用户授予的用户角色。</span><span class="sxs-lookup"><span data-stu-id="eabe0-151">For each resource, in the **Role** column, choose the user role you want to grant to the guest users who use the extranet.</span></span>
6. <span data-ttu-id="eabe0-152">单击 " **下一步：请求** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="eabe0-153">在 " **可请求访问权限的用户** " 下，选择 " **不在你的目录中的用户** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-153">Under **Users who can request access** , choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="eabe0-154">确保选择了 " **连接的特定组织** " 选项，然后单击 " **添加目录** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="eabe0-155">选择您之前添加的已连接的组织，然后单击 " **选择** "</span><span class="sxs-lookup"><span data-stu-id="eabe0-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="eabe0-156">在 " **审批** " 下，选择 **"是" 以 "** **需要审批** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-156">Under **Approval** , choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="eabe0-157">在 " **首次审批者** " 下，选择您之前添加的某个发起人或选择特定用户。</span><span class="sxs-lookup"><span data-stu-id="eabe0-157">Under **First approver** , choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="eabe0-158">单击 " **添加回退** " 并选择一个回退审批者。</span><span class="sxs-lookup"><span data-stu-id="eabe0-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="eabe0-159">在 " **启用** " 下，选择 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="eabe0-159">Under **Enable** , choose **Yes**.</span></span>
14. <span data-ttu-id="eabe0-160">单击 " **下一步：生命周期** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="eabe0-161">选择要使用的过期和访问检查设置，然后单击 " **下一步：审阅 + 创建** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="eabe0-162">查看您的设置，然后单击 " **创建** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-162">Review your settings, and then click **Create**.</span></span>

    ![Azure Active Directory 标识管理中的 access 程序包屏幕的屏幕截图](../media/identity-governance-access-packages.png)

<span data-ttu-id="eabe0-164">如果要与大型组织合作，您可能希望隐藏该访问包。</span><span class="sxs-lookup"><span data-stu-id="eabe0-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="eabe0-165">如果包处于隐藏状态，则合作伙伴组织中的用户将不会在其 *"我的 Access* " 门户上看到该程序包。</span><span class="sxs-lookup"><span data-stu-id="eabe0-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="eabe0-166">相反，必须向其发送直接链接以注册该包。</span><span class="sxs-lookup"><span data-stu-id="eabe0-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="eabe0-167">隐藏访问包可以减少不适当的访问请求数，还可以帮助保留组织在合作伙伴组织门户中的可用访问包。</span><span class="sxs-lookup"><span data-stu-id="eabe0-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="eabe0-168">将访问包设置为隐藏</span><span class="sxs-lookup"><span data-stu-id="eabe0-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="eabe0-169">在 Azure AD 标识管理中，单击 " **访问包** "，然后单击您的访问包。</span><span class="sxs-lookup"><span data-stu-id="eabe0-169">In Azure AD Identity Governance, click **Access packages** , and then click your access package.</span></span>
2. <span data-ttu-id="eabe0-170">在 " **概述** " 页上，单击 " **编辑** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="eabe0-171">在 " **属性** " 下，为 " **隐藏** **" 选择 "是"** ，然后单击 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="eabe0-171">Under **Properties** , choose **Yes** for **Hidden** , and then click **Save**.</span></span>

   ![编辑访问包属性屏幕的屏幕截图](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="eabe0-173">邀请合作伙伴用户</span><span class="sxs-lookup"><span data-stu-id="eabe0-173">Invite partner users</span></span>

<span data-ttu-id="eabe0-174">如果将访问包设置为 "隐藏"，则需要向合作伙伴组织发送直接链接，以便他们可以请求访问您的网站或团队。</span><span class="sxs-lookup"><span data-stu-id="eabe0-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="eabe0-175">查找访问门户链接</span><span class="sxs-lookup"><span data-stu-id="eabe0-175">To find the access portal link</span></span>
1. <span data-ttu-id="eabe0-176">在 Azure AD 标识管理中，单击 " **访问包** "，然后单击您的访问包。</span><span class="sxs-lookup"><span data-stu-id="eabe0-176">In Azure AD Identity Governance, click **Access packages** , and then click your access package.</span></span>
2. <span data-ttu-id="eabe0-177">在 " **概述** " 页上，单击 " **我的访问门户" 链接** 的 " **复制到剪贴板** " 链接。</span><span class="sxs-lookup"><span data-stu-id="eabe0-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![具有访问门户链接的 access 程序包属性的屏幕截图](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="eabe0-179">复制链接后，可以将其与合作伙伴组织的联系人共享，并可将其发送给协作团队中的用户。</span><span class="sxs-lookup"><span data-stu-id="eabe0-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="eabe0-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eabe0-180">See Also</span></span>

[<span data-ttu-id="eabe0-181">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="eabe0-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
