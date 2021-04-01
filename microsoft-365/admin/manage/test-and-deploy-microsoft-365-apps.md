---
title: 由合作伙伴在集成应用门户中测试和部署 Microsoft 365 应用版
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
description: 从 Microsoft 365 管理中心中的集成应用门户查找、测试和部署组织中用户和组的 Microsoft 和 Microsoft 合作伙伴应用。
ms.openlocfilehash: f806d48e0ed582b1b5c1ee262058ce987125bd99
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488285"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a><span data-ttu-id="cff6d-103">由合作伙伴在集成应用门户中测试和部署 Microsoft 365 应用版</span><span class="sxs-lookup"><span data-stu-id="cff6d-103">Test and deploy Microsoft 365 Apps by partners in the Integrated apps portal</span></span>

<span data-ttu-id="cff6d-104">Microsoft 365 管理中心让你能够灵活地从单个位置部署单个应用商店应用、自定义业务线应用和 Microsoft 365 合作伙伴应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-104">The Microsoft 365 admin center gives you the flexibility to deploy single store apps, custom business line of apps and  Microsoft 365 partner apps from a single location.</span></span> <span data-ttu-id="cff6d-105">可以在 Microsoft 管理中心访问该位置，>集成>设置"。</span><span class="sxs-lookup"><span data-stu-id="cff6d-105">The location can be accessed at Microsoft Admin center > Settings > Integrated apps.</span></span> <span data-ttu-id="cff6d-106">通过集成应用门户查找、测试并完全部署由 Microsoft 合作伙伴购买和许可的应用，可为组织保持业务服务的定期更新和高效运行带来便利和好处。</span><span class="sxs-lookup"><span data-stu-id="cff6d-106">The ability to find, test, and fully deploy purchased and licensed apps by Microsoft partners from the Integrated apps portal provides the convenience and benefits your organization requires to keep business services updated regularly and running efficiently.</span></span>

<span data-ttu-id="cff6d-107">有关从组织的合作伙伴购买和许可 Microsoft 365 应用的其他信息，请参阅从 [Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)管理中心管理和部署 Microsoft 365 应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-107">For additional information about purchasing and licensing Microsoft 365 apps from partners for your organization, see [Manage and deploy Microsoft 365 Apps from the Microsoft 365 admin center](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).</span></span>

<span data-ttu-id="cff6d-108">若要详细了解合作伙伴如何创建这些应用，请参阅如何为商业市场规划 [SaaS 产品](https://go.microsoft.com/fwlink/?linkid=2158277)</span><span class="sxs-lookup"><span data-stu-id="cff6d-108">For more info on how partners create these apps, see [How to plan a SaaS offer for the commercial marketplace](https://go.microsoft.com/fwlink/?linkid=2158277)</span></span>

<span data-ttu-id="cff6d-109">集成应用门户仅可供全局管理员访问，并且仅对 WorldWide 客户可用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-109">The Integrated apps portal is only accessible to global admins and available to WorldWide customers only.</span></span> <span data-ttu-id="cff6d-110">此功能在自主云和政府云中不可用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-110">This feature is not available in sovereign and government clouds.</span></span>

<span data-ttu-id="cff6d-111">集成应用门户显示应用列表，其中包括单个应用和部署你的组织的合作伙伴的 Microsoft 365 应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-111">The Integrated apps portal displays a list of apps, which includes single apps and Microsoft 365 apps from partners which are deployed your organization.</span></span> <span data-ttu-id="cff6d-112">仅列出了 Web 应用、SPFx 应用、Office 加载项和 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-112">Only web apps, SPFx apps, Office add-ins and Teams apps are listed.</span></span> <span data-ttu-id="cff6d-113">对于 Web 应用，你可以看到 2 种类型的应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-113">For web apps, we you can see 2 kinds of apps.</span></span>

- <span data-ttu-id="cff6d-114">SaaS 应用可在 appsource.microsoft.com 中提供，并且由管理员代表组织进行部署。</span><span class="sxs-lookup"><span data-stu-id="cff6d-114">SaaS apps that are available in appsource.microsoft.com, and can be deployed by admins giving consent on behalf of organization.</span></span>
- <span data-ttu-id="cff6d-115">与 Office 加载项链接的 SAML 库应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-115">SAML gallery apps that are linked with office add-ins.</span></span>

## <a name="manage-apps-in-the-integrated-apps-portal"></a><span data-ttu-id="cff6d-116">在集成应用门户中管理应用</span><span class="sxs-lookup"><span data-stu-id="cff6d-116">Manage apps in the Integrated apps portal</span></span>

<span data-ttu-id="cff6d-117">你可以管理从合作伙伴处购买和许可的 Microsoft 365 应用的测试和部署。</span><span class="sxs-lookup"><span data-stu-id="cff6d-117">You can manage testing and deployment of purchased and licensed Microsoft 365 Apps from partners.</span></span>

1. <span data-ttu-id="cff6d-118">在管理中心的左侧导航中，选择 **"设置**"，然后选择"集成 **应用"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-118">In the admin center, in the left nav, choose **Settings**, and then choose **Integrated apps**.</span></span>

2. <span data-ttu-id="cff6d-119">选择"状态 **"** 为 **"更多应用"的应用，** 以打开 **"管理"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="cff6d-119">Choose an app with **Status** of **More apps available** to open the **Manage** pane.</span></span> <span data-ttu-id="cff6d-120">通过 **更多可用应用** 的状态，你可以知道来自 ISV 的更多集成尚未部署。</span><span class="sxs-lookup"><span data-stu-id="cff6d-120">The status of **more apps available** lets you know that there are more integrations from the ISVs that aren't yet deployed.</span></span>

3. <span data-ttu-id="cff6d-121">在"概述 **"选项卡上**，选择"部署 **"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-121">On the **Overview** tab select **Deploy**.</span></span> <span data-ttu-id="cff6d-122">某些应用要求你先添加用户，然后才能选择部署。</span><span class="sxs-lookup"><span data-stu-id="cff6d-122">Some apps require you to add users before you can select Deploy.</span></span>

4. <span data-ttu-id="cff6d-123">选择 **"用户**"，选择 **"这是测试部署**"，然后选择 **"整个** 组织 **"、"特定用户/组**"或"**只有我"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-123">Select  **Users**, choose **Is this a test deployment**, and then choose **Entire organization**, **Specific users/groups** or **Just me**.</span></span> <span data-ttu-id="cff6d-124">如果你想要等待将 **应用部署到** 整个组织，还可以选择测试部署。</span><span class="sxs-lookup"><span data-stu-id="cff6d-124">You can also choose **Test deployment** if you prefer to wait to deploy the app to the entire organization.</span></span> <span data-ttu-id="cff6d-125">特定用户或组可以是 Microsoft 365 组、安全组或通讯组。</span><span class="sxs-lookup"><span data-stu-id="cff6d-125">Specific users or groups can be a Microsoft 365 group, a security group, or a distribution group.</span></span>

5. <span data-ttu-id="cff6d-126">选择 **"更新**"，然后选择"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-126">Select **Update** and then **Done**.</span></span> <span data-ttu-id="cff6d-127">现在，可以在"概述"选项卡上选择"部署"。</span><span class="sxs-lookup"><span data-stu-id="cff6d-127">You can now select Deploy on the Overview tab.</span></span>

6. <span data-ttu-id="cff6d-128">查看应用信息，然后选择部署 **。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-128">Review the app information, and then select **Deploy**.</span></span>

7. <span data-ttu-id="cff6d-129">在 **"** 部署已完成"页上选择"完成"，并查看"概述"选项卡上的测试或完整 **部署** 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cff6d-129">Select **Done** on the Deployment completed page and review the details of the test or full deployment on the **Overview** tab.</span></span>

8. <span data-ttu-id="cff6d-130">如果应用程序的状态为"更新挂起 **"，** 你可以单击该应用程序以打开"管理"窗格并更新应用程序。</span><span class="sxs-lookup"><span data-stu-id="cff6d-130">If the app has a status of **Update pending**, you can click on the app to open the Manage pane and update the app.</span></span>

## <a name="find-published-apps-for-testing-and-full-deployment"></a><span data-ttu-id="cff6d-131">查找已发布的应用以进行测试和完整部署</span><span class="sxs-lookup"><span data-stu-id="cff6d-131">Find published apps for testing and full deployment</span></span>

<span data-ttu-id="cff6d-132">你可以查找、测试和完全部署未显示在"集成应用"页上的列表中的已发布应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-132">You can find, test, and fully deploy published apps that don't already appear in the list on the Integrated apps page.</span></span> <span data-ttu-id="cff6d-133">通过从管理中心购买和许可应用，可以从单个位置将 Microsoft 和 Microsoft 合作伙伴应用添加到你的列表中。</span><span class="sxs-lookup"><span data-stu-id="cff6d-133">By purchasing and licensing the apps from the admin center, you can add Microsoft and Microsoft partner apps to your list from a single location.</span></span>

1. <span data-ttu-id="cff6d-134">在管理中心的左侧导航中，选择 **"设置**"，然后选择"集成 **应用"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-134">In the admin center, in the left nav, choose **Settings**, and then choose **Integrated apps**.</span></span>

2. <span data-ttu-id="cff6d-135">选择 **"获取** 应用"，获取应用的视图。</span><span class="sxs-lookup"><span data-stu-id="cff6d-135">Select **Get apps** to get a view of the apps.</span></span>

3. <span data-ttu-id="cff6d-136">在 **"Microsoft 365** 应用发布应用"页面上，通过选择"立即获取"选择要 **部署的应用**。</span><span class="sxs-lookup"><span data-stu-id="cff6d-136">On the **Microsoft 365 Apps** published apps page, select the app you want to deploy by choosing **Get it now**.</span></span> <span data-ttu-id="cff6d-137">显示的应用程序主要是 Word、PowerPoint、Excel、Outlook 外接程序、Teams 应用和 SharePoint (SharePoint 框架技术) 。</span><span class="sxs-lookup"><span data-stu-id="cff6d-137">The apps displayed primarily are Word, PowerPoint, Excel, Outlook add-ins, Teams app and SharePoint apps (built on SharePoint Framework technology).</span></span> <span data-ttu-id="cff6d-138">接受权限，然后选择"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-138">Accept the permissions and select **Continue**.</span></span>

5. <span data-ttu-id="cff6d-139">选择 **页面** 顶部引用等待部署的消息旁边的"部署"。</span><span class="sxs-lookup"><span data-stu-id="cff6d-139">Select **Deploy** at the top of the page next to the message that refers to waiting to be deployed.</span></span>

    <span data-ttu-id="cff6d-140">如果所选应用由 ISV 链接到 SaaS 产品/服务，则属于此链接优惠的所有其他应用将显示在"配置"页面上。</span><span class="sxs-lookup"><span data-stu-id="cff6d-140">If the app selected is linked to a SaaS offer by an ISV, all the other apps that are part of this linked offer will appear on the Configuration page.</span></span> <span data-ttu-id="cff6d-141">如果选择部署所有应用，请选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-141">If you choose to deploy of all of the apps, select **Next**.</span></span> <span data-ttu-id="cff6d-142">否则， **请选择"编辑**"，然后选择要部署的应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-142">Otherwise, select **Edit**, and choose which apps you want deployed.</span></span> <span data-ttu-id="cff6d-143">某些应用要求你先添加用户， **然后才能选择部署**。</span><span class="sxs-lookup"><span data-stu-id="cff6d-143">Some apps require you to add users before you can select **Deploy**.</span></span>

6. <span data-ttu-id="cff6d-144">选择 **"添加用户"，** 选择 **"这是测试部署**"，然后选择 **"整个** 组织"或"**特定用户/组**"或"**只有我"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-144">Select **Add users**, choose **Is this a test deployment**, and then choose **Entire organization** or **Specific users/groups** or **Just me**.</span></span>

    <span data-ttu-id="cff6d-145">特定用户/组可以是 Microsoft 365 组、安全组或分布式组。</span><span class="sxs-lookup"><span data-stu-id="cff6d-145">Specific users/groups can be a Microsoft 365 group, a security group, or a distributed group.</span></span> <span data-ttu-id="cff6d-146">如果你想要等待将 **应用部署到** 整个组织，还可以选择测试部署。</span><span class="sxs-lookup"><span data-stu-id="cff6d-146">You can also choose **Test deployment** if you prefer to wait to deploy the app to the entire organization.</span></span>

7. <span data-ttu-id="cff6d-147">选择 **"下** 一步"以进入 **"接受权限请求"** 页。</span><span class="sxs-lookup"><span data-stu-id="cff6d-147">Select **Next** to get to the **Accept permission request** page.</span></span> <span data-ttu-id="cff6d-148">列出了每个应用的应用功能和权限。</span><span class="sxs-lookup"><span data-stu-id="cff6d-148">The app capabilities and permissions of each of the apps are listed.</span></span> <span data-ttu-id="cff6d-149">如果应用需要同意，请选择 **"接受权限"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-149">If the app needs consent, select **Accept permissions**.</span></span> <span data-ttu-id="cff6d-150">只有全局管理员可以同意。</span><span class="sxs-lookup"><span data-stu-id="cff6d-150">Only a global administrator can give consent.</span></span>

8. <span data-ttu-id="cff6d-151">选择 **"下** 一步"查看部署，然后选择"**完成部署"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-151">Select **Next** to review the deployment and choose **Finish deployment**.</span></span> <span data-ttu-id="cff6d-152">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span><span class="sxs-lookup"><span data-stu-id="cff6d-152">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span></span> <span data-ttu-id="cff6d-153">在 Microsoft 365 管理中心中，你可以看到每个已部署应用的状态和部署应用的日期。</span><span class="sxs-lookup"><span data-stu-id="cff6d-153">In the Microsoft 365 admin center, you can see the status of each deployed app and the date you deployed the app.</span></span>

> [!NOTE]
> <span data-ttu-id="cff6d-154">如果应用以前从集成应用门户外的其他位置部署，则 **部署类型为\*\*\*\*自定义。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-154">If an app was previously deployed from somewhere other than the Integrated Apps portal, the **Deployment Type** is **Custom.**</span></span>

## <a name="unsupported-scenarios"></a><span data-ttu-id="cff6d-155">不受支持的方案</span><span class="sxs-lookup"><span data-stu-id="cff6d-155">Unsupported scenarios</span></span>

<span data-ttu-id="cff6d-156">对于以下方案，无法由合作伙伴从集成应用门户部署单个应用商店应用或 Microsoft 365 应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-156">You won't be able to deploy a single store app or Microsoft 365 Apps by partner from Integrated apps portal for the following scenarios.</span></span>

- <span data-ttu-id="cff6d-157">同一外接程序链接到多个 SaaS 产品。</span><span class="sxs-lookup"><span data-stu-id="cff6d-157">The same add-in is linked to more than one SaaS offer.</span></span>
- <span data-ttu-id="cff6d-158">SaaS 产品链接到加载项，但它不与 Microsoft Graph 集成，也不提供 AAD 应用 ID。</span><span class="sxs-lookup"><span data-stu-id="cff6d-158">The SaaS offer is linked to add-ins, but it does not integrate with Microsoft Graph and no AAD App ID is provided.</span></span>
- <span data-ttu-id="cff6d-159">SaaS 产品链接到外接程序，但为 Microsoft Graph 集成提供的 AAD 应用 ID 在多个 SaaS 产品/服务之间共享。</span><span class="sxs-lookup"><span data-stu-id="cff6d-159">The SaaS offer is linked to add-ins, but AAD App ID provided for Microsoft Graph integration is shared across multiple SaaS offers.</span></span>

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a><span data-ttu-id="cff6d-160">上载自定义业务线应用以进行测试和完整部署</span><span class="sxs-lookup"><span data-stu-id="cff6d-160">Upload custom line of business apps for testing and full deployment</span></span>

1. <span data-ttu-id="cff6d-161">在管理中心的左侧导航中，选择 **"设置**"，然后选择"**集成应用"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-161">In the admin center, in the left nav, choose **Settings** and then **Integrated apps**.</span></span>

2. <span data-ttu-id="cff6d-162">选择 **上传自定义应用**。</span><span class="sxs-lookup"><span data-stu-id="cff6d-162">Select **Upload custom apps**.</span></span> <span data-ttu-id="cff6d-163">仅支持 Word、PowerPoint、Excel 和 Outlook 的自定义应用程序行。</span><span class="sxs-lookup"><span data-stu-id="cff6d-163">Only a custom line of apps for Word, PowerPoint, Excel and Outlook  is supported.</span></span>

3. <span data-ttu-id="cff6d-164">从设备上载清单文件或添加 URL 链接。</span><span class="sxs-lookup"><span data-stu-id="cff6d-164">Upload the manifest file from your device or add a URL link.</span></span> <span data-ttu-id="cff6d-165">某些应用要求你先添加用户，然后才能选择部署。</span><span class="sxs-lookup"><span data-stu-id="cff6d-165">Some apps require you to add users before you can select Deploy.</span></span>

4. <span data-ttu-id="cff6d-166">选择 **"添加用户"，** 选择 **"这是测试部署**"，**然后选择"整个** 组织"或"**特定用户/组**"或"**只有我"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-166">Select **Add users**, choose **Is this a test Deployment**, and choose **Entire organization** or **Specific users/groups** or **Just me**.</span></span>

    <span data-ttu-id="cff6d-167">特定用户/组可以是 Microsoft 365 组、安全组或分布式组。</span><span class="sxs-lookup"><span data-stu-id="cff6d-167">Specific users/groups can be a Microsoft 365 group, a security group, or a distributed group.</span></span> <span data-ttu-id="cff6d-168">如果你想要等待将 **应用** 部署到整个组织，还可以选择测试部署。</span><span class="sxs-lookup"><span data-stu-id="cff6d-168">You can also choose **Test deployment** if you want to wait to deploy the app to the entire organization.</span></span>

5. <span data-ttu-id="cff6d-169">选择 **"下** 一步"以进入 **"接受权限请求"** 页。</span><span class="sxs-lookup"><span data-stu-id="cff6d-169">Select **Next** to get to the **Accept permission request** page.</span></span> <span data-ttu-id="cff6d-170">列出了应用的功能和权限。</span><span class="sxs-lookup"><span data-stu-id="cff6d-170">The app capabilities and permissions of the apps are listed.</span></span> <span data-ttu-id="cff6d-171">如果应用需要同意，请选择 **"接受权限"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-171">If the app needs consent, select **Accept permissions**.</span></span> <span data-ttu-id="cff6d-172">只有全局管理员可以同意。</span><span class="sxs-lookup"><span data-stu-id="cff6d-172">Only a global administrator can give consent.</span></span>

6. <span data-ttu-id="cff6d-173">选择 **"下** 一步"查看部署，然后选择"**完成部署"。**</span><span class="sxs-lookup"><span data-stu-id="cff6d-173">Select **Next** to review the deployment and choose **Finish deployment**.</span></span> <span data-ttu-id="cff6d-174">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span><span class="sxs-lookup"><span data-stu-id="cff6d-174">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="cff6d-175">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="cff6d-175">Frequently asked questions</span></span>

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a><span data-ttu-id="cff6d-176">我需要哪个管理员角色才能访问集成应用？</span><span class="sxs-lookup"><span data-stu-id="cff6d-176">Which administrator role do I need to access Integrated apps?</span></span>

<span data-ttu-id="cff6d-177">只有全局管理员可以访问集成应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-177">Only global administrators can access Integrated Apps.</span></span> <span data-ttu-id="cff6d-178">集成应用不会在其他管理员的左侧导航中显示。</span><span class="sxs-lookup"><span data-stu-id="cff6d-178">Integrated apps won't show up in the left nav for other administrators.</span></span>

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a><span data-ttu-id="cff6d-179">为什么在"设置"而非"集成应用"下的左侧导航中会看到外接程序？</span><span class="sxs-lookup"><span data-stu-id="cff6d-179">Why do I see Add-in in the left nav under Setting but not Integrated apps?</span></span>

<span data-ttu-id="cff6d-180">可能有几个原因：</span><span class="sxs-lookup"><span data-stu-id="cff6d-180">There could be a few reasons:</span></span>

- <span data-ttu-id="cff6d-181">登录的管理员是 Exchange 管理员。</span><span class="sxs-lookup"><span data-stu-id="cff6d-181">The logged in administrator is an Exchange admininstrator.</span></span>
- <span data-ttu-id="cff6d-182">客户位于独立云中，集成应用体验还可供独立云客户使用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-182">The customer is in sovereign cloud and Integrated apps experience is available to sovereign cloud customers yet.</span></span>

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a><span data-ttu-id="cff6d-183">可以从集成应用部署哪些应用？</span><span class="sxs-lookup"><span data-stu-id="cff6d-183">What apps can I deploy from Integrated apps?</span></span>

<span data-ttu-id="cff6d-184">集成应用允许部署 Web 应用、Teams 应用、Excel、PowerPoint、Word、Outlook 加载项和 SPFx 应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-184">Integrated apps allows deployment of Web Apps, Teams app, Excel, PowerPoint, Word, Outlook add-ins, and SPFx apps.</span></span> <span data-ttu-id="cff6d-185">对于外接程序，集成应用支持部署到 Exchange Online 邮箱，而不是本地 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="cff6d-185">For add-ins, Integrated apps supports deployment to Exchange online mailboxes and not on-premises Exchange mailboxes.</span></span>

### <a name="can-administrators-delete-or-remove-apps"></a><span data-ttu-id="cff6d-186">管理员能否删除或删除应用？</span><span class="sxs-lookup"><span data-stu-id="cff6d-186">Can administrators delete or remove apps?</span></span>

<span data-ttu-id="cff6d-187">是。</span><span class="sxs-lookup"><span data-stu-id="cff6d-187">Yes.</span></span> <span data-ttu-id="cff6d-188">全局管理员可以删除或删除应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-188">Global administrators can delete or remove apps.</span></span>

- <span data-ttu-id="cff6d-189">从列表视图中选择应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-189">Select an app from the list view.</span></span> <span data-ttu-id="cff6d-190">在" **配置"** 选项卡上，选择要删除的应用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-190">On the **Configuration** tab, select which apps to remove.</span></span>  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a><span data-ttu-id="cff6d-191">集成应用在自主云中是否可用？</span><span class="sxs-lookup"><span data-stu-id="cff6d-191">Is Integrated apps available in sovereign cloud?</span></span>

<span data-ttu-id="cff6d-192">不正确。</span><span class="sxs-lookup"><span data-stu-id="cff6d-192">No.</span></span> <span data-ttu-id="cff6d-193">集成应用对独立云客户不可用。</span><span class="sxs-lookup"><span data-stu-id="cff6d-193">Integrated apps aren't available to sovereign cloud customers.</span></span>

### <a name="is-integrated-apps-available-in-government-clouds"></a><span data-ttu-id="cff6d-194">集成应用在政府云中是否可用？</span><span class="sxs-lookup"><span data-stu-id="cff6d-194">Is Integrated apps available in government clouds?</span></span>

<span data-ttu-id="cff6d-195">不正确。</span><span class="sxs-lookup"><span data-stu-id="cff6d-195">No.</span></span> <span data-ttu-id="cff6d-196">集成应用不适用于政府云客户。</span><span class="sxs-lookup"><span data-stu-id="cff6d-196">Integrated apps aren't available to government cloud customers.</span></span>
