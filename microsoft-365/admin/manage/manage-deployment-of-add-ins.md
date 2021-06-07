---
title: 在管理中心部署加载项
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 了解如何使用管理中心中的集中部署将加载项部署到组织的用户和组。
ms.openlocfilehash: 796517ba13a4718c38d5200fcf9cbe38b5dc62d0
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779634"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="249e9-103">在管理中心部署加载项</span><span class="sxs-lookup"><span data-stu-id="249e9-103">Deploy add-ins in the admin center</span></span>

<span data-ttu-id="249e9-104">Office 加载项可帮助用户个性化设置文档并加速访问 Web 上的信息（请参阅[开始使用 Office 加载项](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)）。</span><span class="sxs-lookup"><span data-stu-id="249e9-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="249e9-105">作为管理员，Office管理中心中的集中部署功能为Microsoft 365部署外接程序。</span><span class="sxs-lookup"><span data-stu-id="249e9-105">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="249e9-106">对于大多数管理员来说，集中部署是推荐且功能最丰富的方法，用于将外接程序部署到组织内的用户和组。</span><span class="sxs-lookup"><span data-stu-id="249e9-106">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span>

<span data-ttu-id="249e9-107">若要详细了解如何确定组织能否支持集中部署，请参阅确定加载项集中部署是否 [适用于组织](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="249e9-107">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="249e9-108">若要了解有关在部署后管理加载项的更多信息，请参阅在[管理](manage-addins-in-the-admin-center.md)中心管理加载项</span><span class="sxs-lookup"><span data-stu-id="249e9-108">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="249e9-109">对于 Word、Excel 和 PowerPoint 使用[SharePoint](/office/dev/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)应用程序目录向本地环境中的用户部署外接程序，无需连接到 Microsoft 365 和/或支持所需的 SharePoint 外接程序。</span><span class="sxs-lookup"><span data-stu-id="249e9-109">For Word, Excel and PowerPoint use a [SharePoint App Catalog](/office/dev/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="249e9-110">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="249e9-110">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="249e9-111">部署 Office 加载项的推荐方法</span><span class="sxs-lookup"><span data-stu-id="249e9-111">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="249e9-112">若要使用分阶段方法推出加载项，建议采用以下方法：</span><span class="sxs-lookup"><span data-stu-id="249e9-112">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="249e9-113">向小部分业务利益干系人和 IT 部门成员推出加载项。</span><span class="sxs-lookup"><span data-stu-id="249e9-113">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="249e9-114">如果部署成功，请移至步骤 2。</span><span class="sxs-lookup"><span data-stu-id="249e9-114">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="249e9-115">向更多企业内部人员推出外接程序。</span><span class="sxs-lookup"><span data-stu-id="249e9-115">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="249e9-116">同样，评估结果，如果成功，则继续完整部署。</span><span class="sxs-lookup"><span data-stu-id="249e9-116">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="249e9-117">向所有用户执行全面推出。</span><span class="sxs-lookup"><span data-stu-id="249e9-117">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="249e9-118">根据目标访问群体的规模，可以添加或删除推出步骤。</span><span class="sxs-lookup"><span data-stu-id="249e9-118">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="249e9-119">使用管理中心部署 Office 加载项</span><span class="sxs-lookup"><span data-stu-id="249e9-119">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="249e9-120">在开始之前，请参阅确定外接程序的集中部署 [是否适用于你的组织](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="249e9-120">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="249e9-121">在管理中心，转到设置 \> **外接程序"** 页面。</span><span class="sxs-lookup"><span data-stu-id="249e9-121">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span> <span data-ttu-id="249e9-122">如果看不到"加载项 **"页面，** 请转到"设置 \>  \> **集成应用加载项"** 页面。</span><span class="sxs-lookup"><span data-stu-id="249e9-122">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** page.</span></span>

2. <span data-ttu-id="249e9-123">选择 **页面顶部的"** 部署外接程序"，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="249e9-123">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="249e9-124">管理中心将更新为集成应用的部署体验。</span><span class="sxs-lookup"><span data-stu-id="249e9-124">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="249e9-125">集成应用仅对全局管理员可见，而对于其他人，旧体验仍然存在。</span><span class="sxs-lookup"><span data-stu-id="249e9-125">Integrated Apps is only visible to Global administrators, while for others the old experience still exists.</span></span> <span data-ttu-id="249e9-126">如果你看不到上述步骤，请转到集中部署部分，设置  >  **集成应用。**</span><span class="sxs-lookup"><span data-stu-id="249e9-126">If you don't see the above steps, go to the Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="249e9-127">在"集成应用"**页面顶部**，选择"**加载项"。**</span><span class="sxs-lookup"><span data-stu-id="249e9-127">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

3. <span data-ttu-id="249e9-128">选择一个选项，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="249e9-128">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="249e9-129">如果选择了从应用商店添加加载项的选项，Office选择加载项。</span><span class="sxs-lookup"><span data-stu-id="249e9-129">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="249e9-130">可以按类别查看可用加载项：**建议**、评级或 **名称**。 </span><span class="sxs-lookup"><span data-stu-id="249e9-130">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="249e9-131">仅免费加载项可从应用商店Office应用商店。</span><span class="sxs-lookup"><span data-stu-id="249e9-131">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="249e9-132">目前尚不支持付费加载项。</span><span class="sxs-lookup"><span data-stu-id="249e9-132">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="249e9-133">选择外接程序后，接受条款和条件以继续。</span><span class="sxs-lookup"><span data-stu-id="249e9-133">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE]
    > <span data-ttu-id="249e9-134">使用 Office 应用商店选项，更新和增强功能将自动部署到用户。</span><span class="sxs-lookup"><span data-stu-id="249e9-134">With the Office Store option, updates and enhancements are automatically deployed to users.</span></span>

5. <span data-ttu-id="249e9-135">在下一页上，选择“**每个人**”、“**特定用户/组**”或“**只有我**”来指定要为其部署加载项的人。</span><span class="sxs-lookup"><span data-stu-id="249e9-135">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="249e9-136">使用"搜索"框查找特定用户或组。</span><span class="sxs-lookup"><span data-stu-id="249e9-136">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE]
    > <span data-ttu-id="249e9-137">若要了解适用于加载项的其他状态，请参阅 [加载项状态](./manage-addins-in-the-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="249e9-137">To learn about other states that apply to an add-in, see [Add-in states](./manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="249e9-138">选择“部署”。</span><span class="sxs-lookup"><span data-stu-id="249e9-138">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="249e9-139">部署加载项时，会出现绿色刻度线。</span><span class="sxs-lookup"><span data-stu-id="249e9-139">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="249e9-140">按照页面上的说明测试外接程序。</span><span class="sxs-lookup"><span data-stu-id="249e9-140">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="249e9-141">用户可能需要重新启动Office，以查看应用程序功能区上的外接程序图标。</span><span class="sxs-lookup"><span data-stu-id="249e9-141">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="249e9-142">Outlook外接程序最多可能需要 24 小时才能显示在应用程序功能区上。</span><span class="sxs-lookup"><span data-stu-id="249e9-142">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>

8. <span data-ttu-id="249e9-143">完成后，选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="249e9-143">When finished, select **Next**.</span></span> <span data-ttu-id="249e9-144">如果只向自己部署，可以选择"更改有权访问加载项的用户 **"，** 以部署到更多用户。</span><span class="sxs-lookup"><span data-stu-id="249e9-144">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="249e9-145">如果已经将加载项部署到组织的其他成员，请按照说明宣布部署加载项。</span><span class="sxs-lookup"><span data-stu-id="249e9-145">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="249e9-146">最佳做法是通知用户和组已部署的外接程序可用。</span><span class="sxs-lookup"><span data-stu-id="249e9-146">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="249e9-147">请考虑发送描述何时以及如何使用外接程序的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="249e9-147">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="249e9-148">包含或链接到帮助内容或常见问题解答，如果用户遇到加载项问题，这些内容或常见问题解答可能会帮助用户。</span><span class="sxs-lookup"><span data-stu-id="249e9-148">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="249e9-149">为用户和组分配加载项时的注意事项</span><span class="sxs-lookup"><span data-stu-id="249e9-149">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="249e9-150">全局管理员Exchange管理员可以将外接程序分配给所有人或特定用户和组。</span><span class="sxs-lookup"><span data-stu-id="249e9-150">Global admins and Exchange admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="249e9-151">每个选项都有含义：</span><span class="sxs-lookup"><span data-stu-id="249e9-151">Each option has implications:</span></span>
  
- <span data-ttu-id="249e9-152">**所有人** 此选项将外接程序分配给组织的每个用户。</span><span class="sxs-lookup"><span data-stu-id="249e9-152">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="249e9-153">请谨慎使用此选项，且仅应用于真正在组织中通用的加载项。</span><span class="sxs-lookup"><span data-stu-id="249e9-153">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span>

- <span data-ttu-id="249e9-154">**用户** 如果将加载项分配给单个用户，然后将加载项部署到新用户，则必须先添加新用户。</span><span class="sxs-lookup"><span data-stu-id="249e9-154">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>

- <span data-ttu-id="249e9-155">**组** 如果将外接程序分配给组，则会自动为添加到该组的用户分配外接程序。</span><span class="sxs-lookup"><span data-stu-id="249e9-155">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="249e9-156">从组中删除用户时，用户将失去对外接程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="249e9-156">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="249e9-157">在任一情况下，管理员无需执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="249e9-157">In either case, no additional action is required from the admin.</span></span>

- <span data-ttu-id="249e9-158">**只有我** 如果您仅将外接程序分配给自己，则仅将外接程序分配给您的帐户，这是测试外接程序的理想帐户。</span><span class="sxs-lookup"><span data-stu-id="249e9-158">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>

<span data-ttu-id="249e9-159">适合贵组织的选项取决于您的配置。</span><span class="sxs-lookup"><span data-stu-id="249e9-159">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="249e9-160">但是，我们建议使用组进行分配。</span><span class="sxs-lookup"><span data-stu-id="249e9-160">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="249e9-161">作为管理员，您可能会发现使用组并控制这些组的成员身份（而不是每次分配单个用户）可以更轻松地管理外接程序。</span><span class="sxs-lookup"><span data-stu-id="249e9-161">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="249e9-162">在某些情况下，您可能希望通过手动分配用户来向特定用户分配分配，从而限制对一小组用户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="249e9-162">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="249e9-163">有关Office加载项安全性</span><span class="sxs-lookup"><span data-stu-id="249e9-163">More about Office add-ins security</span></span>

<span data-ttu-id="249e9-p117">Office 加载项结合了一个包含加载项相关元数据的 XML 清单文件，但最重要的是它指向包含所有代码和逻辑的 Web 应用程序。加载项的功能范围很广。例如，加载项可以：</span><span class="sxs-lookup"><span data-stu-id="249e9-p117">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="249e9-167">显示数据。</span><span class="sxs-lookup"><span data-stu-id="249e9-167">Display data.</span></span>

- <span data-ttu-id="249e9-168">读取用户文档以提供上下文服务。</span><span class="sxs-lookup"><span data-stu-id="249e9-168">Read a user's document to provide contextual services.</span></span>

- <span data-ttu-id="249e9-169">从用户文档读取数据并向用户文档写入数据，以便向该用户提供价值。</span><span class="sxs-lookup"><span data-stu-id="249e9-169">Read and write data to and from a user's document to provide value to that user.</span></span>

<span data-ttu-id="249e9-170">若要详细了解 Office 加载项的类型和功能，请参阅 [Office Add-ins platform overview](/office/dev/add-ins/overview/office-add-ins)（Office 加载项平台概述），尤其是"Anatomy of an Office Add-in"（Office 加载项分析）一节。</span><span class="sxs-lookup"><span data-stu-id="249e9-170">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="249e9-p118">若要与用户文档进行交互，加载项需要在清单中声明需要哪些权限。五级 JavaScript API 访问权限模型为任务窗格加载项的用户提供隐私和安全性的基础。Office 应用商店 中的大多数加载项是 ReadWriteDocument 级别，几乎所有加载项均至少支持 ReadDocument 级别。有关权限级别的详细信息，请参阅 [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)（请求在内容和任务窗格加载项中使用 API 的权限）。</span><span class="sxs-lookup"><span data-stu-id="249e9-p118">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="249e9-p119">更新清单时，通常更改加载项的图标和文本。有时会更改加载项命令。但是，不会更改加载项的权限。Web 应用程序（加载项的所有代码和逻辑在其中运行）可以随时更改，这是 Web 应用程序的特性。</span><span class="sxs-lookup"><span data-stu-id="249e9-p119">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="249e9-178">加载项更新的情况如下：</span><span class="sxs-lookup"><span data-stu-id="249e9-178">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="249e9-p120">**业务线加载项：** 在这种情况下，管理员显式上传清单，加载项需要管理员上传新的清单文件以支持元数据的更改。相关 Office 应用程序下次启动时，该加载项会更新。Web 应用程序可以随时更改。</span><span class="sxs-lookup"><span data-stu-id="249e9-p120">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span>

    > [!NOTE]
    > <span data-ttu-id="249e9-182">管理员无需删除 LOB 加载项以执行更新。</span><span class="sxs-lookup"><span data-stu-id="249e9-182">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="249e9-183">在"外接程序"部分，管理员只需单击 LOB 外接程序并选择右下角的"更新按钮"。</span><span class="sxs-lookup"><span data-stu-id="249e9-183">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="249e9-184">只有在新加载项的版本大于现有加载项版本时，更新才能运行。</span><span class="sxs-lookup"><span data-stu-id="249e9-184">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>

- <span data-ttu-id="249e9-p122">**Office 应用商店加载项：** 管理员从 Office 应用商店 中选择加载项后，如果 Office 应用商店 中更新了加载项，则该加载项会稍后以集中式部署方式更新。相关 Office 应用程序下次启动时，该加载项会更新。Web 应用程序可以随时更改。</span><span class="sxs-lookup"><span data-stu-id="249e9-p122">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="249e9-188">相关内容</span><span class="sxs-lookup"><span data-stu-id="249e9-188">Related content</span></span>

<span data-ttu-id="249e9-189">[管理中心中的外接程序 (](manage-addins-in-the-admin-center.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="249e9-189">[Manage add-ins in the admin center](manage-addins-in-the-admin-center.md) (article)</span></span>\
<span data-ttu-id="249e9-190">[生成首个 Word 任务窗格加载项 (](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) 文章</span><span class="sxs-lookup"><span data-stu-id="249e9-190">[Build your first Word task pane add-in](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (article</span></span>\
<span data-ttu-id="249e9-191">[从应用商店](minors-and-acquiring-addins-from-the-store.md) 获取外接程序的次要 (文章) \ 使用集中部署 [PowerShell cmdlet](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) 管理外接程序 (文章) </span><span class="sxs-lookup"><span data-stu-id="249e9-191">[Minors and acquiring add-ins from the store](minors-and-acquiring-addins-from-the-store.md) (article)\ [Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)</span></span>\  
<span data-ttu-id="249e9-192">[疑难解答：用户看不到外接程序 (](/office365/troubleshoot/access-management/user-not-seeing-add-ins) 文章) </span><span class="sxs-lookup"><span data-stu-id="249e9-192">[Troubleshoot: User not seeing add-ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (article)</span></span>