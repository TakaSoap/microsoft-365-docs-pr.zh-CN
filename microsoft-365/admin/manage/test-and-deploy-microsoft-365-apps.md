---
title: 在集成Microsoft 365 应用版门户中测试并部署合作伙伴部署的应用
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 从组织中集成应用门户中查找、测试和部署组织中用户和组的 Microsoft 和 Microsoft 合作伙伴Microsoft 365 管理中心。
ms.openlocfilehash: dcd4a91d9e43c0a740094615cd3dca0b0e8bc0f6
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007053"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a><span data-ttu-id="6b860-103">在集成Microsoft 365 应用版门户中测试并部署合作伙伴部署的应用</span><span class="sxs-lookup"><span data-stu-id="6b860-103">Test and deploy Microsoft 365 Apps by partners in the Integrated apps portal</span></span>

<span data-ttu-id="6b860-104">利用Microsoft 365 管理中心，你可以灵活地从单个位置部署单个应用商店应用、自定义业务线应用Microsoft 365合作伙伴应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-104">The Microsoft 365 admin center gives you the flexibility to deploy single store apps, custom business line of apps and  Microsoft 365 partner apps from a single location.</span></span> <span data-ttu-id="6b860-105">可以在 Microsoft 管理中心设置中，在集成应用中访问该位置。</span><span class="sxs-lookup"><span data-stu-id="6b860-105">The location can be accessed in the Microsoft Admin center settings, in Integrated apps.</span></span> <span data-ttu-id="6b860-106">通过集成应用门户查找、测试并完全部署由 Microsoft 合作伙伴购买和许可的应用，可为组织保持业务服务的定期更新和高效运行带来便利和好处。</span><span class="sxs-lookup"><span data-stu-id="6b860-106">The ability to find, test, and fully deploy purchased and licensed apps by Microsoft partners from the Integrated apps portal provides the convenience and benefits your organization requires to keep business services updated regularly and running efficiently.</span></span>

<span data-ttu-id="6b860-107">有关从组织的合作伙伴购买和Microsoft 365应用的其他信息，请参阅从 Microsoft 365 管理中心 管理和部署[Microsoft 365 应用版应用程序](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)。</span><span class="sxs-lookup"><span data-stu-id="6b860-107">For additional information about purchasing and licensing Microsoft 365 apps from partners for your organization, see [Manage and deploy Microsoft 365 Apps from the Microsoft 365 admin center](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).</span></span>

<span data-ttu-id="6b860-108">若要详细了解合作伙伴如何创建这些应用，请参阅如何为商业市场规划 [SaaS 产品](https://go.microsoft.com/fwlink/?linkid=2158277)</span><span class="sxs-lookup"><span data-stu-id="6b860-108">For more info on how partners create these apps, see [How to plan a SaaS offer for the commercial marketplace](https://go.microsoft.com/fwlink/?linkid=2158277)</span></span>

<span data-ttu-id="6b860-109">集成应用门户仅可供全局管理员访问，并且仅适用于全球客户。</span><span class="sxs-lookup"><span data-stu-id="6b860-109">The Integrated apps portal is only accessible to global admins and available to world-wide customers only.</span></span> <span data-ttu-id="6b860-110">此功能在自主云和政府云中不可用。</span><span class="sxs-lookup"><span data-stu-id="6b860-110">This feature is not available in sovereign and government clouds.</span></span>

<span data-ttu-id="6b860-111">集成应用门户显示应用列表，其中包括单个应用Microsoft 365部署你的组织的合作伙伴提供的应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-111">The Integrated apps portal displays a list of apps, which includes single apps and Microsoft 365 apps from partners which are deployed your organization.</span></span> <span data-ttu-id="6b860-112">仅列出了 web SPFx、Office、Teams应用程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-112">Only web apps, SPFx apps, Office add-ins and Teams apps are listed.</span></span> <span data-ttu-id="6b860-113">对于 Web 应用，你可以看到两种类型的应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-113">For web apps, you can see two kinds of apps.</span></span>

- <span data-ttu-id="6b860-114">SaaS 应用在 appsource.microsoft.com 中提供，并且由管理员代表组织进行部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-114">SaaS apps that are available in appsource.microsoft.com, and can be deployed by admins giving consent on behalf of the organization.</span></span>
- <span data-ttu-id="6b860-115">与 Office 加载项链接的 SAML 库应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-115">SAML gallery apps that are linked with office add-ins.</span></span>

## <a name="manage-apps-in-the-integrated-apps-portal"></a><span data-ttu-id="6b860-116">在集成应用门户中管理应用</span><span class="sxs-lookup"><span data-stu-id="6b860-116">Manage apps in the Integrated apps portal</span></span>

<span data-ttu-id="6b860-117">你可以管理从合作伙伴处购买和Microsoft 365 应用版部署的测试和部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-117">You can manage testing and deployment of purchased and licensed Microsoft 365 Apps from partners.</span></span>

1. <span data-ttu-id="6b860-118">在管理中心中，选择 **"设置"，** 然后选择"集成 **应用"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-118">In the admin center, select **Settings**, and then select **Integrated apps**.</span></span>

2. <span data-ttu-id="6b860-119">选择"状态 **"** 为 **"更多应用"的应用，** 以打开 **"管理"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="6b860-119">Choose an app with **Status** of **More apps available** to open the **Manage** pane.</span></span> <span data-ttu-id="6b860-120">通过 **更多可用应用** 的状态，你可以知道来自 ISV 的更多集成尚未部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-120">The status of **more apps available** lets you know that there are more integrations from the ISVs that aren't yet deployed.</span></span>

3. <span data-ttu-id="6b860-121">在"**概述"选项卡** 上，选择"部署 **"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-121">On the **Overview** tab, select **Deploy**.</span></span> <span data-ttu-id="6b860-122">某些应用要求你先添加用户，然后才能选择部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-122">Some apps require you to add users before you can select Deploy.</span></span>

4. <span data-ttu-id="6b860-123">选择 **"用户**"，选择 **"这是测试部署**"，然后选择 **"整个** 组织 **"、"特定用户/组**"或"**只有我"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-123">Select  **Users**, choose **Is this a test deployment**, and then choose **Entire organization**, **Specific users/groups** or **Just me**.</span></span> <span data-ttu-id="6b860-124">如果你想要等待将 **应用部署到** 整个组织，还可以选择测试部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-124">You can also choose **Test deployment** if you prefer to wait to deploy the app to the entire organization.</span></span> <span data-ttu-id="6b860-125">特定用户或组可以是Microsoft 365组、安全组或通讯组。</span><span class="sxs-lookup"><span data-stu-id="6b860-125">Specific users or groups can be a Microsoft 365 group, a security group, or a distribution group.</span></span>

5. <span data-ttu-id="6b860-126">选择 **"更新**"，然后选择"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-126">Select **Update** and then **Done**.</span></span> <span data-ttu-id="6b860-127">现在，可以在"概述"选项卡上选择"部署"。</span><span class="sxs-lookup"><span data-stu-id="6b860-127">You can now select Deploy on the Overview tab.</span></span>

6. <span data-ttu-id="6b860-128">查看应用信息，然后选择部署 **。**</span><span class="sxs-lookup"><span data-stu-id="6b860-128">Review the app information, and then select **Deploy**.</span></span>

7. <span data-ttu-id="6b860-129">在 **"** 部署已完成"页上选择"完成"，并查看"概述"选项卡上的测试或完整 **部署** 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6b860-129">Select **Done** on the Deployment completed page and review the details of the test or full deployment on the **Overview** tab.</span></span>

8. <span data-ttu-id="6b860-130">如果应用程序的状态为"更新挂起 **"，** 你可以单击该应用程序以打开"管理"窗格并更新应用程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-130">If the app has a status of **Update pending**, you can click on the app to open the Manage pane and update the app.</span></span>

## <a name="find-published-apps-for-testing-and-full-deployment"></a><span data-ttu-id="6b860-131">查找已发布的应用以进行测试和完整部署</span><span class="sxs-lookup"><span data-stu-id="6b860-131">Find published apps for testing and full deployment</span></span>

<span data-ttu-id="6b860-132">你可以查找、测试和完全部署未显示在"集成应用"页上的列表中的已发布应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-132">You can find, test, and fully deploy published apps that don't already appear in the list on the Integrated apps page.</span></span> <span data-ttu-id="6b860-133">通过从管理中心购买和许可应用，可以从单个位置将 Microsoft 和 Microsoft 合作伙伴应用添加到你的列表中。</span><span class="sxs-lookup"><span data-stu-id="6b860-133">By purchasing and licensing the apps from the admin center, you can add Microsoft and Microsoft partner apps to your list from a single location.</span></span>

1. <span data-ttu-id="6b860-134">在管理中心的左侧导航中，选择 **"设置"，** 然后选择"集成 **应用"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-134">In the admin center, in the left nav, choose **Settings**, and then choose **Integrated apps**.</span></span>

2. <span data-ttu-id="6b860-135">选择 **"获取** 应用"，获取应用的视图。</span><span class="sxs-lookup"><span data-stu-id="6b860-135">Select **Get apps** to get a view of the apps.</span></span>

3. <span data-ttu-id="6b860-136">On the **Microsoft 365 应用版** published apps page， select the app you want to deploy by choosing **Get it now**.</span><span class="sxs-lookup"><span data-stu-id="6b860-136">On the **Microsoft 365 Apps** published apps page, select the app you want to deploy by choosing **Get it now**.</span></span> <span data-ttu-id="6b860-137">显示的应用主要是 Word、PowerPoint、Excel、Outlook 加载项、Teams 应用和 SharePoint 应用 (基于 SharePoint 框架 技术) 。</span><span class="sxs-lookup"><span data-stu-id="6b860-137">The apps displayed primarily are Word, PowerPoint, Excel, Outlook add-ins, Teams app and SharePoint apps (built on SharePoint Framework technology).</span></span> <span data-ttu-id="6b860-138">接受权限，然后选择"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-138">Accept the permissions and select **Continue**.</span></span>

5. <span data-ttu-id="6b860-139">选择 **页面** 顶部引用等待部署的消息旁边的"部署"。</span><span class="sxs-lookup"><span data-stu-id="6b860-139">Select **Deploy** at the top of the page next to the message that refers to waiting to be deployed.</span></span>

    <span data-ttu-id="6b860-140">如果所选应用由 ISV 链接到 SaaS 产品/服务，则属于此链接优惠的所有其他应用将显示在"配置"页面上。</span><span class="sxs-lookup"><span data-stu-id="6b860-140">If the app selected is linked to a SaaS offer by an ISV, all the other apps that are part of this linked offer will appear on the Configuration page.</span></span> <span data-ttu-id="6b860-141">如果选择部署所有应用，请选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-141">If you choose to deploy of all of the apps, select **Next**.</span></span> <span data-ttu-id="6b860-142">否则， **请选择"编辑**"，然后选择要部署的应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-142">Otherwise, select **Edit**, and choose which apps you want deployed.</span></span> <span data-ttu-id="6b860-143">某些应用要求你先添加用户， **然后才能选择部署**。</span><span class="sxs-lookup"><span data-stu-id="6b860-143">Some apps require you to add users before you can select **Deploy**.</span></span>

6. <span data-ttu-id="6b860-144">选择 **"添加用户"，** 选择 **"这是测试部署**"，然后选择 **"整个** 组织"或"**特定用户/组**"或"**只有我"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-144">Select **Add users**, choose **Is this a test deployment**, and then choose **Entire organization** or **Specific users/groups** or **Just me**.</span></span>

    <span data-ttu-id="6b860-145">特定用户/组可以是Microsoft 365组、安全组或分布式组。</span><span class="sxs-lookup"><span data-stu-id="6b860-145">Specific users/groups can be a Microsoft 365 group, a security group, or a distributed group.</span></span> <span data-ttu-id="6b860-146">如果你想要等待将 **应用部署到** 整个组织，还可以选择测试部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-146">You can also choose **Test deployment** if you prefer to wait to deploy the app to the entire organization.</span></span>

7. <span data-ttu-id="6b860-147">选择 **"下** 一步"以进入 **"接受权限请求"** 页。</span><span class="sxs-lookup"><span data-stu-id="6b860-147">Select **Next** to get to the **Accept permission request** page.</span></span> <span data-ttu-id="6b860-148">列出了每个应用的应用功能和权限。</span><span class="sxs-lookup"><span data-stu-id="6b860-148">The app capabilities and permissions of each of the apps are listed.</span></span> <span data-ttu-id="6b860-149">如果应用需要同意，请选择 **"接受权限"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-149">If the app needs consent, select **Accept permissions**.</span></span> <span data-ttu-id="6b860-150">只有全局管理员可以同意。</span><span class="sxs-lookup"><span data-stu-id="6b860-150">Only a global administrator can give consent.</span></span>

8. <span data-ttu-id="6b860-151">选择 **"下** 一步"查看部署，然后选择"**完成部署"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-151">Select **Next** to review the deployment and choose **Finish deployment**.</span></span> <span data-ttu-id="6b860-152">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span><span class="sxs-lookup"><span data-stu-id="6b860-152">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span></span> <span data-ttu-id="6b860-153">在Microsoft 365 管理中心中，你可以看到每个已部署应用的状态和部署应用的日期。</span><span class="sxs-lookup"><span data-stu-id="6b860-153">In the Microsoft 365 admin center, you can see the status of each deployed app and the date you deployed the app.</span></span>

> [!NOTE]
> <span data-ttu-id="6b860-154">如果应用以前从集成应用门户外的其他位置部署，则 **部署类型为\*\*\*\*自定义。**</span><span class="sxs-lookup"><span data-stu-id="6b860-154">If an app was previously deployed from somewhere other than the Integrated Apps portal, the **Deployment Type** is **Custom.**</span></span>

## <a name="unsupported-scenarios"></a><span data-ttu-id="6b860-155">不支持的方案</span><span class="sxs-lookup"><span data-stu-id="6b860-155">Unsupported scenarios</span></span>

<span data-ttu-id="6b860-156">对于以下方案，你无法从集成应用门户Microsoft 365 应用版合作伙伴部署单个应用商店应用或应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-156">You won't be able to deploy a single store app or Microsoft 365 Apps by partner from Integrated apps portal for the following scenarios.</span></span>

- <span data-ttu-id="6b860-157">同一外接程序链接到多个 SaaS 产品。</span><span class="sxs-lookup"><span data-stu-id="6b860-157">The same add-in is linked to more than one SaaS offer.</span></span>
- <span data-ttu-id="6b860-158">SaaS 产品链接到加载项，但它不与 Microsoft Graph，也不提供 AAD 应用 ID。</span><span class="sxs-lookup"><span data-stu-id="6b860-158">The SaaS offer is linked to add-ins, but it does not integrate with Microsoft Graph and no AAD App ID is provided.</span></span>
- <span data-ttu-id="6b860-159">SaaS 产品链接到外接程序，但为 Microsoft Graph提供的 AAD 应用 ID 在多个 SaaS 产品/服务之间共享。</span><span class="sxs-lookup"><span data-stu-id="6b860-159">The SaaS offer is linked to add-ins, but AAD App ID provided for Microsoft Graph integration is shared across multiple SaaS offers.</span></span>

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a><span data-ttu-id="6b860-160">Upload自定义业务线应用进行测试和完整部署</span><span class="sxs-lookup"><span data-stu-id="6b860-160">Upload custom line-of-business apps for testing and full deployment</span></span>

1. <span data-ttu-id="6b860-161">在管理中心的左侧导航中，选择"设置集成 **应用"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-161">In the admin center, in the left nav, choose **Settings** and then **Integrated apps**.</span></span>

2. <span data-ttu-id="6b860-162">选择 **Upload应用"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-162">Select **Upload custom apps**.</span></span> <span data-ttu-id="6b860-163">仅支持 Word、PowerPoint、Excel 和 Outlook 应用的自定义行。</span><span class="sxs-lookup"><span data-stu-id="6b860-163">Only a custom line of apps for Word, PowerPoint, Excel and Outlook  is supported.</span></span>

3. <span data-ttu-id="6b860-164">Upload显示清单文件或添加 URL 链接。</span><span class="sxs-lookup"><span data-stu-id="6b860-164">Upload the manifest file from your device or add a URL link.</span></span> <span data-ttu-id="6b860-165">某些应用要求你先添加用户，然后才能选择部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-165">Some apps require you to add users before you can select Deploy.</span></span>

4. <span data-ttu-id="6b860-166">选择 **"添加用户"，** 选择 **"这是测试部署**"，**然后选择"整个** 组织"或"**特定用户/组**"或"**只有我"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-166">Select **Add users**, choose **Is this a test Deployment**, and choose **Entire organization** or **Specific users/groups** or **Just me**.</span></span>

    <span data-ttu-id="6b860-167">特定用户/组可以是Microsoft 365组、安全组或分布式组。</span><span class="sxs-lookup"><span data-stu-id="6b860-167">Specific users/groups can be a Microsoft 365 group, a security group, or a distributed group.</span></span> <span data-ttu-id="6b860-168">如果你想要等待将 **应用** 部署到整个组织，还可以选择测试部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-168">You can also choose **Test deployment** if you want to wait to deploy the app to the entire organization.</span></span>

5. <span data-ttu-id="6b860-169">选择 **"下** 一步"以进入 **"接受权限请求"** 页。</span><span class="sxs-lookup"><span data-stu-id="6b860-169">Select **Next** to get to the **Accept permission request** page.</span></span> <span data-ttu-id="6b860-170">列出了应用的功能和权限。</span><span class="sxs-lookup"><span data-stu-id="6b860-170">The app capabilities and permissions of the apps are listed.</span></span> <span data-ttu-id="6b860-171">如果应用需要同意，请选择 **"接受权限"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-171">If the app needs consent, select **Accept permissions**.</span></span> <span data-ttu-id="6b860-172">只有全局管理员可以同意。</span><span class="sxs-lookup"><span data-stu-id="6b860-172">Only a global administrator can give consent.</span></span>

6. <span data-ttu-id="6b860-173">选择 **"下** 一步"查看部署，然后选择"**完成部署"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-173">Select **Next** to review the deployment and choose **Finish deployment**.</span></span> <span data-ttu-id="6b860-174">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span><span class="sxs-lookup"><span data-stu-id="6b860-174">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span></span>

## <a name="prepare-to-deploy-add-ins-in-integrated-apps"></a><span data-ttu-id="6b860-175">准备在集成应用中部署外接程序</span><span class="sxs-lookup"><span data-stu-id="6b860-175">Prepare to deploy add-ins in Integrated apps</span></span>

<span data-ttu-id="6b860-176">Office加载项有助于个性化设置文档并简化访问 Web 上信息 (请参阅开始使用 Office 加载项) 。</span><span class="sxs-lookup"><span data-stu-id="6b860-176">Office add-ins help you personalize your documents and streamline the way you access information on the web (see Start using your Office Add-in).</span></span> 

<span data-ttu-id="6b860-177">外接程序具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="6b860-177">Add-ins provides the following benefits:</span></span> 

- <span data-ttu-id="6b860-178">当相关Office应用程序启动时，外接程序将自动下载。</span><span class="sxs-lookup"><span data-stu-id="6b860-178">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="6b860-179">如果外接程序支持外接程序命令，则外接程序会自动显示在应用程序内的功能Office中。</span><span class="sxs-lookup"><span data-stu-id="6b860-179">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span> 

- <span data-ttu-id="6b860-180">如果管理员关闭或删除外接程序，或者如果用户从 Azure Active Directory 或外接程序分配到的组中删除，则用户将不再显示外接程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-180">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span> 

<span data-ttu-id="6b860-181">外接程序在三个桌面平台中受支持，Windows、Mac 和 Online Office应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-181">Add-ins are supported in three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="6b860-182">它还在 iOS 和 Android (Outlook仅移动外接程序中) 。</span><span class="sxs-lookup"><span data-stu-id="6b860-182">It is also supported in iOS and Android (Outlook Mobile Add-ins Only).</span></span> 

<span data-ttu-id="6b860-183">外接程序最多可能需要 24 小时才能显示给所有用户的客户端。</span><span class="sxs-lookup"><span data-stu-id="6b860-183">It can take up to 24 hours for an add-in to show up for client for all users.</span></span> 

<span data-ttu-id="6b860-184">现在，Exchange管理员和全局管理员都可以从集成应用部署外接程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-184">Today both Exchange Admins and Global Admins can deploy add-ins from Integrated apps.</span></span>   

### <a name="before-you-begin"></a><span data-ttu-id="6b860-185">准备工作</span><span class="sxs-lookup"><span data-stu-id="6b860-185">Before you begin</span></span>

<span data-ttu-id="6b860-186">部署外接程序要求用户使用 Microsoft 365 企业版 许可证 (E3/E5/F3) 或 Microsoft 365 Business (Business Basic、Business Standard、Business 高级版) 。</span><span class="sxs-lookup"><span data-stu-id="6b860-186">Deployment of add-ins requires that the users are using Microsoft 365 Enterprise licenses (E3/E5/F3) or Microsoft 365 Business licenses (Business Basic, Business Standard, Business Premium).</span></span> <span data-ttu-id="6b860-187">用户还需要使用其组织 ID Office登录到) ，Exchange Online活动Exchange Online邮箱。</span><span class="sxs-lookup"><span data-stu-id="6b860-187">The users also need to be signed into Office using their organizational ID) and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="6b860-188">订阅目录必须位于 中，或已联合Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="6b860-188">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span> 

<span data-ttu-id="6b860-189">部署不支持以下内容：</span><span class="sxs-lookup"><span data-stu-id="6b860-189">Deployment doesn't support the following:</span></span> 

- <span data-ttu-id="6b860-190">针对 Office 2013 中 Word、Excel 或 PowerPoint 的加载项</span><span class="sxs-lookup"><span data-stu-id="6b860-190">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="6b860-191">本地目录服务</span><span class="sxs-lookup"><span data-stu-id="6b860-191">An on-premises directory service</span></span> 
- <span data-ttu-id="6b860-192">部署到内部部署Exchange的外接程序部署</span><span class="sxs-lookup"><span data-stu-id="6b860-192">Add-in Deployment to an Exchange On-prem Mailbox</span></span> 
- <span data-ttu-id="6b860-193">部署组件对象模型 (COM) 或Visual Studio Tools for Office (VSTO) 加载项。</span><span class="sxs-lookup"><span data-stu-id="6b860-193">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span> 
- <span data-ttu-id="6b860-194">不包含Microsoft 365（如 Exchange Online for Business 和 Microsoft 365 应用版 for Microsoft 365 应用版 for Enterprise）的部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-194">Deployments of Microsoft 365 that do not include Exchange Online such as Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>  

### <a name="office-requirements"></a><span data-ttu-id="6b860-195">Office要求</span><span class="sxs-lookup"><span data-stu-id="6b860-195">Office Requirements</span></span> 

<span data-ttu-id="6b860-196">对于 Word、Excel 和 PowerPoint 加载项，用户必须使用下列加载项之一：</span><span class="sxs-lookup"><span data-stu-id="6b860-196">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span> 
- <span data-ttu-id="6b860-197">在 Windows 设备上，Microsoft 365 企业版 版本 1704 或更高版本的 Microsoft 365 企业版 许可证 (E3/E5/F3) 或 Microsoft 365 商业版许可证 (Business Basic、Business Standard、Business 高级版) 。</span><span class="sxs-lookup"><span data-stu-id="6b860-197">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise licenses (E3/E5/F3) or Microsoft 365 Business licenses (Business Basic, Business Standard, Business Premium).</span></span> 
- <span data-ttu-id="6b860-198">在 Mac 版本 15.34 或更高版本上。</span><span class="sxs-lookup"><span data-stu-id="6b860-198">On a Mac, Version 15.34 or later.</span></span> 

<span data-ttu-id="6b860-199">对于Outlook，用户必须使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="6b860-199">For Outlook, your users must be using one of the following:</span></span> 
- <span data-ttu-id="6b860-200">版本 1701 或更高版本的 Microsoft 365 企业版 许可证 (E3/E5/F3) 或 Microsoft 365 Business (Business Basic、Business Standard、Business 高级版) 。</span><span class="sxs-lookup"><span data-stu-id="6b860-200">Version 1701 or later of Microsoft 365 Enterprise licenses (E3/E5/F3) or Microsoft 365 Business licenses (Business Basic, Business Standard, Business Premium).</span></span> 
- <span data-ttu-id="6b860-201">Office Professional Plus 2019 或 Office Standard 2019 的版本 1808 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="6b860-201">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span> 
- <span data-ttu-id="6b860-202">MS) I 2016 (或 Office Standard 2016 Office Professional Plus 2016 版本 16.0.4494.1000 (MSI) 。</span><span class="sxs-lookup"><span data-stu-id="6b860-202">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI).</span></span>
    > [!NOTE]
    > <span data-ttu-id="6b860-203">MSI 版本的 Outlook 在相应的 Outlook 功能区中显示管理员安装的外接程序，而不是"我的外接程序"部分。</span><span class="sxs-lookup"><span data-stu-id="6b860-203">MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>  
- <span data-ttu-id="6b860-204">Office Professional Plus MSI 2013 版本 15.0.4937.1000 或更高版本 (MSI) 或 Office Standard 2013 (MSI) 。</span><span class="sxs-lookup"><span data-stu-id="6b860-204">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI).</span></span>
- <span data-ttu-id="6b860-205">Office 2016 for Mac 的版本 16.0.9318.1000 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="6b860-205">Version 16.0.9318.1000 or later of Office 2016 for Mac.</span></span> 
- <span data-ttu-id="6b860-206">适用于 iOS 的 Outlook Mobile 版本 2.75.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="6b860-206">Version 2.75.0 or later of Outlook mobile for iOS.</span></span> 
- <span data-ttu-id="6b860-207">适用于 Android 的 Outlook Mobile 版本 2.2.145 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="6b860-207">Version 2.2.145 or later of Outlook mobile for Android.</span></span> 



### <a name="exchange-online-requirements"></a><span data-ttu-id="6b860-208">Exchange Online 要求</span><span class="sxs-lookup"><span data-stu-id="6b860-208">Exchange Online requirements</span></span> 
<span data-ttu-id="6b860-209">Microsoft Exchange 存储组织的租户中的加载项清单。</span><span class="sxs-lookup"><span data-stu-id="6b860-209">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="6b860-210">部署外接程序的管理员和接收这些外接程序的用户必须位于支持 OAuth 身份验证的 Exchange Online 版本上。</span><span class="sxs-lookup"><span data-stu-id="6b860-210">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span> 

<span data-ttu-id="6b860-211">请与组织的 Exchange 管理员联系，了解正在使用哪个配置。</span><span class="sxs-lookup"><span data-stu-id="6b860-211">Check with your organization's Exchange admin to find out which configuration is in use.</span></span> <span data-ttu-id="6b860-212">可以使用 [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity)   PowerShell cmdlet 验证每个用户的 OAuth 连接。</span><span class="sxs-lookup"><span data-stu-id="6b860-212">OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet.</span></span> 

### <a name="user-and-group-assignments"></a><span data-ttu-id="6b860-213">用户和组分配</span><span class="sxs-lookup"><span data-stu-id="6b860-213">User and group assignments</span></span>
<span data-ttu-id="6b860-214">Azure Active Directory 支持的大多数组（包括 Microsoft 365 组、通讯组列表和安全组）当前都支持部署外接程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-214">The deployment of add-in is currently supported to the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span> <span data-ttu-id="6b860-215">部署支持顶级组或没有父组的组的用户，但支持嵌套组或具有父组的组的用户。</span><span class="sxs-lookup"><span data-stu-id="6b860-215">Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="6b860-216">当前不支持未启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="6b860-216">Non-mail enabled security groups are not currently supported.</span></span> 

<span data-ttu-id="6b860-217">在下面的示例中，将 Sandra、Sheila 和 Sales Department 组分配给外接程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-217">In the following example, Sandra, Sheila, and the Sales Department group are assigned to an add-in.</span></span> <span data-ttu-id="6b860-218">由于西海岸销售部门是嵌套组，赵强和熊飞未被分配加载项。</span><span class="sxs-lookup"><span data-stu-id="6b860-218">Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span> 

![销售部门的关系图](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="6b860-220">找出一个组是否包含嵌套组</span><span class="sxs-lookup"><span data-stu-id="6b860-220">Find out if a group contains nested groups</span></span>

<span data-ttu-id="6b860-221">若要找出一个组是否包含嵌套组，最简单的方法是查看 Outlook 内的组联系人卡片。</span><span class="sxs-lookup"><span data-stu-id="6b860-221">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="6b860-222">如果在电子邮件的"到"字段中输入 \*\*\*\* 组名称，然后在解析时选择组名称，它将显示该组是否包含用户或   嵌套组。</span><span class="sxs-lookup"><span data-stu-id="6b860-222">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="6b860-223">在下面的示例中，测试组的 \*\*\*\* Outlook 联系人卡片的"成员"   选项卡显示没有用户，只有两个子组。</span><span class="sxs-lookup"><span data-stu-id="6b860-223">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 

![Outlook 联系人卡片的"成员"选项卡](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

<span data-ttu-id="6b860-225">可以解析某个组，查看该组是否是任何组的成员，从而进行反向查询。</span><span class="sxs-lookup"><span data-stu-id="6b860-225">You can do the opposite query by resolving the group to see if it's a member of any group.</span></span> <span data-ttu-id="6b860-226">在下面的示例中，可以在 Outlook 联系人卡片 <b></b>的"成员身份"选项卡下看到"子组   1"是测试组的成员。</span><span class="sxs-lookup"><span data-stu-id="6b860-226">In the example below, you can see under the <b>Membership</b> tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 

![Outlook 联系人卡片的"成员身份"选项卡](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

<span data-ttu-id="6b860-228">请注意，可以使用 Azure Active Directory 图形 API 运行查询，以查找组内的组列表。</span><span class="sxs-lookup"><span data-stu-id="6b860-228">Note that you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group.</span></span> <span data-ttu-id="6b860-229">有关详细信息，请参阅对组 [和组|图形 API 参考](/previous-versions/azure/ad/graph/api/groups-operations)。</span><span class="sxs-lookup"><span data-stu-id="6b860-229">For more information, see [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations).</span></span> 

## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="6b860-230">部署 Office 加载项的推荐方法</span><span class="sxs-lookup"><span data-stu-id="6b860-230">Recommended approach for deploying Office add-ins</span></span> 
<span data-ttu-id="6b860-231">若要使用分阶段方法推出加载项，建议采用以下方法：</span><span class="sxs-lookup"><span data-stu-id="6b860-231">To roll out add-ins by using a phased approach, we recommend the following:</span></span> 
1. <span data-ttu-id="6b860-232">向小部分业务利益干系人和 IT 部门成员推出加载项。</span><span class="sxs-lookup"><span data-stu-id="6b860-232">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="6b860-233">你可以打开标志 **"这是否一个测试部署"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-233">You can turn on the flag **Is this a test deployment**.</span></span> <span data-ttu-id="6b860-234">如果部署成功，请移至步骤 2。</span><span class="sxs-lookup"><span data-stu-id="6b860-234">If the deployment is successful, move to step 2.</span></span> 

2. <span data-ttu-id="6b860-235">向更多企业内部人员推出外接程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-235">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="6b860-236">同样，评估结果，如果成功，则继续完整部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-236">Again, evaluate the results and, if successful, continue with full deployment.</span></span> 

3. <span data-ttu-id="6b860-237">向所有用户执行全面推出。</span><span class="sxs-lookup"><span data-stu-id="6b860-237">Perform a full rollout to all users.</span></span> <span data-ttu-id="6b860-238">关闭"这是否测试 **部署"中的标记**。</span><span class="sxs-lookup"><span data-stu-id="6b860-238">Turn off the flag from **Is this a Test deployment**.</span></span> 

<span data-ttu-id="6b860-239">根据目标访问群体的规模，可以添加或删除推出步骤。</span><span class="sxs-lookup"><span data-stu-id="6b860-239">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>  

## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="6b860-240">使用管理中心部署 Office 加载项</span><span class="sxs-lookup"><span data-stu-id="6b860-240">Deploy an Office add-in using the admin center</span></span> 

1. <span data-ttu-id="6b860-241">在管理中心中，选择"**设置"，** 然后选择"**集成应用"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-241">In the admin center, select **Settings**, then select **Integrated apps**.</span></span> 

2. <span data-ttu-id="6b860-242">选择 **页面顶部的** "获取应用"。</span><span class="sxs-lookup"><span data-stu-id="6b860-242">Select **Get apps** at the top of the page.</span></span> <span data-ttu-id="6b860-243">AppSource 将采用嵌入格式加载。</span><span class="sxs-lookup"><span data-stu-id="6b860-243">AppSource will load in an embedded format.</span></span> <span data-ttu-id="6b860-244">搜索外接程序，或者通过单击左侧导航导航上的"产品"找到它。</span><span class="sxs-lookup"><span data-stu-id="6b860-244">Either search for an add-in or find it through clicking on Product on the left nav.</span></span>  <span data-ttu-id="6b860-245">如果外接程序已被 ISV 链接到 SaaS 应用或其他应用和外接程序，并且 SaaS 应用是付费应用，则将显示一个对话框，用于购买许可证或部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-245">If the add-in has been linked by the ISV to a SaaS app or other apps and add-ins and if the SaaS app is a paid app then you will be shown a dialog box to either buy the license or Deploy.</span></span> <span data-ttu-id="6b860-246">无论你是否已购买许可证，都可以继续部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-246">Irrespective of whether you have bought the license or not you can go ahead with the deployment.</span></span> <span data-ttu-id="6b860-247">选择“**部署**”。</span><span class="sxs-lookup"><span data-stu-id="6b860-247">Select **Deploy**.</span></span>  

3. <span data-ttu-id="6b860-248">你将看到" **配置"** 页，其中列出了所有应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-248">You will see the **Configuration** page where all the apps are listed.</span></span> <span data-ttu-id="6b860-249">如果你没有部署应用的权限或权限，将突出显示相应的信息。</span><span class="sxs-lookup"><span data-stu-id="6b860-249">If you don’t have permissions or the right access to deploy the app, the respective information will be highlighted.</span></span> <span data-ttu-id="6b860-250">可以选择要部署的应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-250">You can select the apps you want to deploy.</span></span> <span data-ttu-id="6b860-251">通过选择 **"下** 一步"，你将查看 **"用户"** 页。</span><span class="sxs-lookup"><span data-stu-id="6b860-251">By selecting **Next**, you will view the **Users** page.</span></span> <span data-ttu-id="6b860-252">如果外接程序尚未由 ISV 链接，您将被路由到"用户"页面。</span><span class="sxs-lookup"><span data-stu-id="6b860-252">If the add-in hasn’t been linked by the ISV, you will be routed to the Users page.</span></span> 

4. <span data-ttu-id="6b860-253">选择 **"每个人** **"、"** 特定用户/ \*\*\*\* 组"或"只有我"以指定外接程序   将部署到的用户。</span><span class="sxs-lookup"><span data-stu-id="6b860-253">Select **Everyone**, **Specific users/groups**, or **Just me** to specify whom the add-in is deployed to.</span></span> <span data-ttu-id="6b860-254">使用"搜索"框查找特定用户或组。</span><span class="sxs-lookup"><span data-stu-id="6b860-254">Use the Search box to find specific users or groups.</span></span> <span data-ttu-id="6b860-255">如果要测试外接程序，请选择"**这是否测试部署"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-255">If you are testing the add-in, select **Is this a test deployment**.</span></span> 

5. <span data-ttu-id="6b860-256">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="6b860-256">Select **Next**.</span></span> <span data-ttu-id="6b860-257">如果应用具有 Microsoft 365 认证，则所有应用功能和权限都随认证信息一起显示在单个窗格中。</span><span class="sxs-lookup"><span data-stu-id="6b860-257">All the app capabilities and permissions are displayed in a single pane along with certification info if the app has Microsoft 365 certification.</span></span> <span data-ttu-id="6b860-258">选择认证徽标可使用户查看有关认证的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="6b860-258">Selecting the certification logo lets the user see more details about the certification.</span></span>  

6. <span data-ttu-id="6b860-259">查看，然后选择"完成 **部署"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-259">Review, and then select **Finish deployment**.</span></span>  

7. <span data-ttu-id="6b860-260">部署外接程序时，将显示一个绿色"刻度线"图标。</span><span class="sxs-lookup"><span data-stu-id="6b860-260">A green "tick" icon appears when the add-in is deployed.</span></span> <span data-ttu-id="6b860-261">按照页面上的说明测试外接程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-261">Follow the on-page instructions to test the add-in.</span></span> 

> [!NOTE]
> <span data-ttu-id="6b860-262">用户可能需要重新启动 Office，以查看应用程序功能区上的外接程序图标。</span><span class="sxs-lookup"><span data-stu-id="6b860-262">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="6b860-263">Outlook 外接程序最多可能需要 24 小时才能显示在应用程序功能区上。</span><span class="sxs-lookup"><span data-stu-id="6b860-263">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span> 

<span data-ttu-id="6b860-264">最佳做法是通知用户和组已部署的外接程序可用。</span><span class="sxs-lookup"><span data-stu-id="6b860-264">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="6b860-265">请考虑发送描述何时以及如何使用外接程序的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6b860-265">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="6b860-266">包含或链接以帮助用户在加载项出现问题时可能帮助的内容或常见问题解答。</span><span class="sxs-lookup"><span data-stu-id="6b860-266">Include or link to help content or FAQs that might help users if they have problems with the add-in.</span></span> 

## <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="6b860-267">为用户和组分配加载项时的注意事项</span><span class="sxs-lookup"><span data-stu-id="6b860-267">Considerations when assigning an add-in to users and groups</span></span> 

<span data-ttu-id="6b860-268">全局管理员和 Exchange 管理员可以将外接程序分配给每个人或特定用户和组。</span><span class="sxs-lookup"><span data-stu-id="6b860-268">Global admins and Exchange admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="6b860-269">每个选项都有含义：</span><span class="sxs-lookup"><span data-stu-id="6b860-269">Each option has implications:</span></span> 

- <span data-ttu-id="6b860-270">**所有人**  此选项将外接程序分配给组织的每个用户。</span><span class="sxs-lookup"><span data-stu-id="6b860-270">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="6b860-271">请谨慎使用此选项，且仅应用于真正在组织中通用的加载项。</span><span class="sxs-lookup"><span data-stu-id="6b860-271">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 

- <span data-ttu-id="6b860-272">**用户**  如果将加载项分配给单个用户，然后将加载项部署到新用户，则必须先添加新用户。</span><span class="sxs-lookup"><span data-stu-id="6b860-272">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span> 

- <span data-ttu-id="6b860-273">**组**  如果将外接程序分配给组，则会自动为添加到该组的用户分配外接程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-273">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="6b860-274">从组中删除用户时，用户将失去对外接程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6b860-274">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="6b860-275">在任一情况下，管理员无需执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="6b860-275">In either case, no additional action is required from the admin.</span></span> 

- <span data-ttu-id="6b860-276">**只有我**  如果您仅将外接程序分配给自己，则仅将外接程序分配给您的帐户，这是测试外接程序的理想帐户。</span><span class="sxs-lookup"><span data-stu-id="6b860-276">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span> 

<span data-ttu-id="6b860-277">适合贵组织的选项取决于您的配置。</span><span class="sxs-lookup"><span data-stu-id="6b860-277">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="6b860-278">但是，我们建议使用组进行分配。</span><span class="sxs-lookup"><span data-stu-id="6b860-278">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="6b860-279">作为管理员，您可能会发现使用组并控制这些组的成员身份（而不是每次分配单个用户）可以更轻松地管理外接程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-279">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="6b860-280">在某些情况下，您可能希望通过手动分配用户来向特定用户分配分配，从而限制对一小组用户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6b860-280">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span> 

### <a name="more-about-office-add-ins-security"></a><span data-ttu-id="6b860-281">有关 Office 加载项安全性的更多内容</span><span class="sxs-lookup"><span data-stu-id="6b860-281">More about Office add-ins security</span></span> 
<span data-ttu-id="6b860-p143">Office 加载项结合了一个包含加载项相关元数据的 XML 清单文件，但最重要的是它指向包含所有代码和逻辑的 Web 应用程序。加载项的功能范围很广。例如，加载项可以：</span><span class="sxs-lookup"><span data-stu-id="6b860-p143">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
- <span data-ttu-id="6b860-285">显示数据。</span><span class="sxs-lookup"><span data-stu-id="6b860-285">Display data.</span></span> 
- <span data-ttu-id="6b860-286">读取用户文档以提供上下文服务。</span><span class="sxs-lookup"><span data-stu-id="6b860-286">Read a user's document to provide contextual services.</span></span> 
- <span data-ttu-id="6b860-287">从用户文档读取数据并向用户文档写入数据，以便向该用户提供价值。</span><span class="sxs-lookup"><span data-stu-id="6b860-287">Read and write data to and from a user's document to provide value to that user.</span></span>  

<span data-ttu-id="6b860-288">有关 Office 外接程序的类型和功能详细信息，请参阅 [Office 外接程序](/office/dev/add-ins/overview/office-add-ins)平台概述，尤其是"Office 外接程序剖析"一节。</span><span class="sxs-lookup"><span data-stu-id="6b860-288">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span> 

<span data-ttu-id="6b860-289">若要与用户文档交互，外接程序需要在清单中声明所需的权限。</span><span class="sxs-lookup"><span data-stu-id="6b860-289">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest.</span></span> <span data-ttu-id="6b860-290">五级 JavaScript API 访问权限模型为任务窗格加载项用户的隐私和安全性提供了基础。Office 应用商店中的大多数外接程序都是 ReadWriteDocument 级别，几乎所有外接程序都至少支持 ReadDocument 级别。</span><span class="sxs-lookup"><span data-stu-id="6b860-290">A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level.</span></span> <span data-ttu-id="6b860-291">有关权限级别的详细信息，请参阅S [requesting permissions for API use in content and task pane add-ins。](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)</span><span class="sxs-lookup"><span data-stu-id="6b860-291">For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span> 

<span data-ttu-id="6b860-p145">更新清单时，通常更改加载项的图标和文本。有时会更改加载项命令。但是，不会更改加载项的权限。Web 应用程序（加载项的所有代码和逻辑在其中运行）可以随时更改，这是 Web 应用程序的特性。</span><span class="sxs-lookup"><span data-stu-id="6b860-p145">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span> 

<span data-ttu-id="6b860-296">加载项更新的情况如下：</span><span class="sxs-lookup"><span data-stu-id="6b860-296">Updates for add-ins happen as follows:</span></span> 
- <span data-ttu-id="6b860-297">**业务线** 外接程序：在这种情况下，如果管理员显式上载了清单，则外接程序要求管理员上载新的清单文件以支持元数据更改。</span><span class="sxs-lookup"><span data-stu-id="6b860-297">**Line-of-business add-in**: In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes.</span></span> <span data-ttu-id="6b860-298">相关 Office 应用程序下次启动时，该加载项会更新。</span><span class="sxs-lookup"><span data-stu-id="6b860-298">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="6b860-299">Web 应用程序可以随时更改。</span><span class="sxs-lookup"><span data-stu-id="6b860-299">The web application can change at any time.</span></span> 

- <span data-ttu-id="6b860-300">**Office 应用商店** 外接程序：当管理员从 Office 应用商店选择外接程序时，如果 Office 商店中的外接程序更新，则下次相关 Office 应用程序启动时，外接程序将更新。</span><span class="sxs-lookup"><span data-stu-id="6b860-300">**Office Store add-in**: When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="6b860-301">Web 应用程序可以随时更改。</span><span class="sxs-lookup"><span data-stu-id="6b860-301">The web application can change at any time.</span></span> 

> [!NOTE]
> <span data-ttu-id="6b860-302">对于 Word，Excel 和 PowerPoint 使用 [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)应用程序目录向本地环境中的用户部署外接程序，无需连接到   Microsoft 365 和/或需要支持 SharePoint 外接程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-302">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="6b860-303">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6b860-303">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>  

## <a name="add-in-states"></a><span data-ttu-id="6b860-304">加载项状态</span><span class="sxs-lookup"><span data-stu-id="6b860-304">Add-in states</span></span>
<span data-ttu-id="6b860-305">加载项可以"开"或"关 \*\*\*\*    **"**   状态。</span><span class="sxs-lookup"><span data-stu-id="6b860-305">An add-in can be in either the **On** or **Off** state.</span></span> 

| <span data-ttu-id="6b860-306">状态</span><span class="sxs-lookup"><span data-stu-id="6b860-306">State</span></span> | <span data-ttu-id="6b860-307">此状态如何出现</span><span class="sxs-lookup"><span data-stu-id="6b860-307">How the state occurs</span></span> | <span data-ttu-id="6b860-308">影响</span><span class="sxs-lookup"><span data-stu-id="6b860-308">Impact</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="6b860-309">**活动**</span><span class="sxs-lookup"><span data-stu-id="6b860-309">**Active**</span></span>  <br/> |<span data-ttu-id="6b860-310">管理员已上载外接程序并将其分配给用户或组。</span><span class="sxs-lookup"><span data-stu-id="6b860-310">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="6b860-311">分配了加载项的用户和组可在相关客户端中看到它。</span><span class="sxs-lookup"><span data-stu-id="6b860-311">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="6b860-312">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="6b860-312">**Turned off**</span></span>  <br/> |<span data-ttu-id="6b860-313">管理员已禁用加载项。</span><span class="sxs-lookup"><span data-stu-id="6b860-313">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="6b860-314">分配了外接程序的用户和组无法再访问它。</span><span class="sxs-lookup"><span data-stu-id="6b860-314">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="6b860-315">如果外接程序的状态更改为"可用"，则用户和组将再次有权访问它。</span><span class="sxs-lookup"><span data-stu-id="6b860-315">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="6b860-316">**已删除**</span><span class="sxs-lookup"><span data-stu-id="6b860-316">**Deleted**</span></span>  <br/> |<span data-ttu-id="6b860-317">管理员已删除加载项。</span><span class="sxs-lookup"><span data-stu-id="6b860-317">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="6b860-318">分配了加载项的用户和组无法再访问它。</span><span class="sxs-lookup"><span data-stu-id="6b860-318">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
 
<span data-ttu-id="6b860-319">如果没有人再使用加载项，请考虑将其删除。</span><span class="sxs-lookup"><span data-stu-id="6b860-319">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="6b860-320">例如，如果仅在一年的特定时间使用外接程序，则关闭外接程序可能有意义。</span><span class="sxs-lookup"><span data-stu-id="6b860-320">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span> 

## <a name="manage-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="6b860-321">使用Office管理中心管理加载项</span><span class="sxs-lookup"><span data-stu-id="6b860-321">Manage an Office add-in using the admin center</span></span>

<span data-ttu-id="6b860-322">部署后，管理员还可以管理用户对外接程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6b860-322">Post deployment, admins can also manage user access to add-ins.</span></span> 

1. <span data-ttu-id="6b860-323">在管理中心中，选择 **"设置"，** 然后选择"**集成应用"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-323">In the admin center, select **Settings**, then select **Integrated apps**.</span></span> 
2. <span data-ttu-id="6b860-324">在"集成应用"页面上，它将显示应用列表，这些应用可能是单个加载项，或者是已与其他应用链接的加载项。</span><span class="sxs-lookup"><span data-stu-id="6b860-324">On the Integrated apps page, it will display a list of apps will be either single add-ins or add-ins that have been linked with other apps.</span></span> 
3. <span data-ttu-id="6b860-325">选择"状态 **"**   为 **"更多可用应用"的应用**   以打开 **"管理"**   窗格。</span><span class="sxs-lookup"><span data-stu-id="6b860-325">Select an app with **Status** of **More apps available** to open the **Manage** pane.</span></span> <span data-ttu-id="6b860-326">通过 **更多可用应用** 的状态，你可以知道来自 ISV 的更多集成   尚未部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-326">The status of **more apps available** lets you know that there are more integrations from the ISVs that aren't yet deployed.</span></span> 
4. <span data-ttu-id="6b860-327">在" **概述"选项卡**   上，选择"部署 **"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-327">On the **Overview** tab, select **Deploy**.</span></span> <span data-ttu-id="6b860-328">某些应用要求你先添加用户，然后才能选择部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-328">Some apps require you to add users before you can select Deploy.</span></span> 
5. <span data-ttu-id="6b860-329">选择 **"用户**"，选择 **"这是测试部署**"， **然后选择"整个** 组织"、" **特定用户/组**"   或" **只有我"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-329">Select **Users**, select **Is this a test deployment**, and then select either **Entire organization**, **Specific users/groups** or **Just me**.</span></span> <span data-ttu-id="6b860-330">如果你想要 **等待将应用** 部署到整个组织，也可以选择测试   部署。</span><span class="sxs-lookup"><span data-stu-id="6b860-330">You can also select **Test deployment** if you prefer to wait to deploy the app to the entire organization.</span></span> <span data-ttu-id="6b860-331">特定用户或组可以是Microsoft 365组、安全组或通讯组。</span><span class="sxs-lookup"><span data-stu-id="6b860-331">Specific users or groups can be a Microsoft 365 group, a security group, or a distribution group.</span></span> 
6. <span data-ttu-id="6b860-332">选择  **"更新**   "，然后选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-332">Select  **Update** and then select **Done**.</span></span> <span data-ttu-id="6b860-333">现在，可以在"概述 **"选项卡** 上选择" **部署** "。</span><span class="sxs-lookup"><span data-stu-id="6b860-333">You can now select **Deploy** on the **Overview** tab.</span></span> 
7. <span data-ttu-id="6b860-334">查看应用信息，然后选择部署 **。**</span><span class="sxs-lookup"><span data-stu-id="6b860-334">Review the app information, and then select **Deploy**.</span></span>
8. <span data-ttu-id="6b860-335">选择 **"** 部署已完成"页上的"完成"，然后查看"概述"选项卡上的测试或   完整 **部署**   的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6b860-335">Select  **Done** on the **Deployment completed** page, and review the details of the test or full deployment on the **Overview** tab.</span></span> 
9. <span data-ttu-id="6b860-336">如果应用程序的状态为"更新挂起 **"，** 你可以单击该应用程序以打开"管理"窗格并更新应用程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-336">If the app has a status of  **Update pending**, you can click on the app to open the **Manage** pane and update the app.</span></span> 
10. <span data-ttu-id="6b860-337">若要仅更新用户，请选择" **用户"** 选项卡，然后进行相应的更改。</span><span class="sxs-lookup"><span data-stu-id="6b860-337">To just update users, select the **Users** tab and make the appropriate change.</span></span> <span data-ttu-id="6b860-338">进行更改 **后** ，选择"更新"。</span><span class="sxs-lookup"><span data-stu-id="6b860-338">Select **Update** after making your changes.</span></span>  

## <a name="delete-an-add-in"></a><span data-ttu-id="6b860-339">删除加载项</span><span class="sxs-lookup"><span data-stu-id="6b860-339">Delete an add-in</span></span>

<span data-ttu-id="6b860-340">您还可以删除已部署的外接程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-340">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="6b860-341">在管理中心中，选择 **"设置"，** 然后选择"**集成应用"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-341">In the admin center, select **Settings**, then select **Integrated apps** .</span></span>
2. <span data-ttu-id="6b860-342">选择任意行以显示管理窗格。</span><span class="sxs-lookup"><span data-stu-id="6b860-342">Select any row to display the management pane.</span></span> 
3. <span data-ttu-id="6b860-343">选择" **配置"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6b860-343">Select the **Configuration** tab.</span></span> 
4. <span data-ttu-id="6b860-344">选择要删除的外接程序，然后选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="6b860-344">Select the add-in that you want to delete and then select **Remove**.</span></span>  

> [!NOTE]
>  <span data-ttu-id="6b860-345">如果加载项已由另一个管理员部署，则"删除"按钮将被禁用。</span><span class="sxs-lookup"><span data-stu-id="6b860-345">If the add-in has been deployed by another admin, then the Remove button will be disabled.</span></span> <span data-ttu-id="6b860-346">只有已部署应用的管理员或全局管理员才能删除加载项。</span><span class="sxs-lookup"><span data-stu-id="6b860-346">Only the admin who has deployed the app or a global admin can delete the add-in.</span></span>

## <a name="scenarios-where-exchange-admin-cannot-deploy-an-add-in"></a><span data-ttu-id="6b860-347">管理员Exchange加载项的方案</span><span class="sxs-lookup"><span data-stu-id="6b860-347">Scenarios where Exchange admin cannot deploy an add-in</span></span> 

<span data-ttu-id="6b860-348">有两种情况Exchange管理员无法部署外接程序：</span><span class="sxs-lookup"><span data-stu-id="6b860-348">There are two cases in which an Exchange Admin won't be able to deploy an add-in:</span></span>
- <span data-ttu-id="6b860-349">如果加载项需要 MS 权限Graph API，并且需要获得全局管理员同意。</span><span class="sxs-lookup"><span data-stu-id="6b860-349">If an add-in needs permission to MS Graph APIs and needs consent from a global admin.</span></span>
- <span data-ttu-id="6b860-350">如果外接程序链接到两个或多个外接程序和 webapp，并且至少其中一个外接程序由另一个管理员 (exchange/global) 且用户分配不统一。</span><span class="sxs-lookup"><span data-stu-id="6b860-350">If an add-in is linked to two or more add-ins and webapps, and at least one of these add-ins is deployed by another admin (exchange/global) and the user assignment is not uniform.</span></span> <span data-ttu-id="6b860-351">只有当所有已部署的应用的用户分配相同时，我们才允许部署外接程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-351">We only allow deployment of add-ins when the user assignment is the same for all the already deployed apps.</span></span>  


## <a name="frequently-asked-questions"></a><span data-ttu-id="6b860-352">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="6b860-352">Frequently asked questions</span></span>

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a><span data-ttu-id="6b860-353">我需要哪个管理员角色才能访问集成应用？</span><span class="sxs-lookup"><span data-stu-id="6b860-353">Which administrator role do I need to access Integrated apps?</span></span>

<span data-ttu-id="6b860-354">只有全局管理员可以访问集成应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-354">Only global administrators can access Integrated Apps.</span></span> <span data-ttu-id="6b860-355">集成应用不会在其他管理员的左侧导航中显示。</span><span class="sxs-lookup"><span data-stu-id="6b860-355">Integrated apps won't show up in the left nav for other administrators.</span></span>

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a><span data-ttu-id="6b860-356">为什么在"设置"而非"集成应用"下的左侧导航中会看到外接程序？</span><span class="sxs-lookup"><span data-stu-id="6b860-356">Why do I see Add-in in the left nav under Setting but not Integrated apps?</span></span>

<span data-ttu-id="6b860-357">可能有几个原因：</span><span class="sxs-lookup"><span data-stu-id="6b860-357">There could be a few reasons:</span></span>

- <span data-ttu-id="6b860-358">登录的管理员是Exchange管理员。</span><span class="sxs-lookup"><span data-stu-id="6b860-358">The logged in administrator is an Exchange administrator.</span></span>
- <span data-ttu-id="6b860-359">客户位于独立云中，集成应用体验还可供独立云客户使用。</span><span class="sxs-lookup"><span data-stu-id="6b860-359">The customer is in sovereign cloud and Integrated apps experience is available to sovereign cloud customers yet.</span></span>

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a><span data-ttu-id="6b860-360">可以从集成应用部署哪些应用？</span><span class="sxs-lookup"><span data-stu-id="6b860-360">What apps can I deploy from Integrated apps?</span></span>

<span data-ttu-id="6b860-361">集成应用允许部署 Web 应用、Teams 应用、Excel、PowerPoint、Word、Outlook 加载项SPFx应用程序。</span><span class="sxs-lookup"><span data-stu-id="6b860-361">Integrated apps allow deployment of Web Apps, Teams app, Excel, PowerPoint, Word, Outlook add-ins, and SPFx apps.</span></span> <span data-ttu-id="6b860-362">对于外接程序，集成应用支持部署到Exchange邮箱，而不是本地Exchange邮箱。</span><span class="sxs-lookup"><span data-stu-id="6b860-362">For add-ins, Integrated apps support deployment to Exchange online mailboxes and not on-premises Exchange mailboxes.</span></span>

### <a name="can-administrators-delete-or-remove-apps"></a><span data-ttu-id="6b860-363">管理员能否删除或删除应用？</span><span class="sxs-lookup"><span data-stu-id="6b860-363">Can administrators delete or remove apps?</span></span>

<span data-ttu-id="6b860-364">是。</span><span class="sxs-lookup"><span data-stu-id="6b860-364">Yes.</span></span> <span data-ttu-id="6b860-365">全局管理员可以删除或删除应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-365">Global administrators can delete or remove apps.</span></span>

- <span data-ttu-id="6b860-366">从列表视图中选择应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-366">Select an app from the list view.</span></span> <span data-ttu-id="6b860-367">在" **配置"** 选项卡上，选择要删除的应用。</span><span class="sxs-lookup"><span data-stu-id="6b860-367">On the **Configuration** tab, select which apps to remove.</span></span>  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a><span data-ttu-id="6b860-368">集成应用在自主云中是否可用？</span><span class="sxs-lookup"><span data-stu-id="6b860-368">Is Integrated apps available in sovereign cloud?</span></span>

<span data-ttu-id="6b860-369">不正确。</span><span class="sxs-lookup"><span data-stu-id="6b860-369">No.</span></span> <span data-ttu-id="6b860-370">集成应用对独立云客户不可用。</span><span class="sxs-lookup"><span data-stu-id="6b860-370">Integrated apps aren't available to sovereign cloud customers.</span></span>

### <a name="is-integrated-apps-available-in-government-clouds"></a><span data-ttu-id="6b860-371">集成应用在政府云中是否可用？</span><span class="sxs-lookup"><span data-stu-id="6b860-371">Is Integrated apps available in government clouds?</span></span>

<span data-ttu-id="6b860-372">不正确。</span><span class="sxs-lookup"><span data-stu-id="6b860-372">No.</span></span> <span data-ttu-id="6b860-373">集成应用不适用于政府云客户。</span><span class="sxs-lookup"><span data-stu-id="6b860-373">Integrated apps aren't available to government cloud customers.</span></span>
