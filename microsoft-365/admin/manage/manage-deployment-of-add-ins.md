---
title: 在管理中心部署加载项
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 了解如何通过在管理中心中使用集中部署将外接程序部署到组织中的用户和组。
ms.openlocfilehash: 20ebdfd2072c49fabadcbaf66dead54e75f9becd
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304788"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="8f40a-103">在管理中心部署加载项</span><span class="sxs-lookup"><span data-stu-id="8f40a-103">Deploy add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8f40a-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="8f40a-104">The admin center is changing.</span></span> <span data-ttu-id="8f40a-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="8f40a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="8f40a-106">Office 加载项可帮助用户个性化设置文档并加速访问 Web 上的信息（请参阅[开始使用 Office 加载项](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)）。</span><span class="sxs-lookup"><span data-stu-id="8f40a-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="8f40a-107">作为管理员，你可以使用 Microsoft 365 管理中心中的集中部署功能为组织中的用户部署 Office 外接程序。</span><span class="sxs-lookup"><span data-stu-id="8f40a-107">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8f40a-108">集中部署是大多数管理员为将外接程序部署到组织内的用户和组的建议功能和功能最丰富的方式。</span><span class="sxs-lookup"><span data-stu-id="8f40a-108">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> 

<span data-ttu-id="8f40a-109">若要详细了解如何确定组织是否可以支持集中部署，请参阅 [确定加载项的集中部署是否适用于你的组织](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="8f40a-109">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="8f40a-110">若要详细了解如何在部署后管理外接程序，请参阅 [在管理中心管理外接程序](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="8f40a-110">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="8f40a-111">对于 Word，Excel 和 PowerPoint 使用 [Sharepoint 应用程序目录](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) 将外接程序部署到本地环境中的用户，而无需连接到 Microsoft 365 和/或支持 SharePoint 外接程序。</span><span class="sxs-lookup"><span data-stu-id="8f40a-111">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="8f40a-112">对于 Outlook，在不连接到 Microsoft 365 的情况下，使用 Exchange 控制面板在本地环境中部署。</span><span class="sxs-lookup"><span data-stu-id="8f40a-112">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="8f40a-113">部署 Office 外接程序的推荐方法</span><span class="sxs-lookup"><span data-stu-id="8f40a-113">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="8f40a-114">若要使用分阶段方式推出外接程序，我们建议您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8f40a-114">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="8f40a-115">将加载项推出给一小部分业务利益干系人和 IT 部门的成员。</span><span class="sxs-lookup"><span data-stu-id="8f40a-115">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="8f40a-116">如果部署成功，请转到步骤2。</span><span class="sxs-lookup"><span data-stu-id="8f40a-116">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="8f40a-117">将加载项部署到企业内的更多个人。</span><span class="sxs-lookup"><span data-stu-id="8f40a-117">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="8f40a-118">再次评估结果，如果成功，则继续完全部署。</span><span class="sxs-lookup"><span data-stu-id="8f40a-118">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="8f40a-119">对所有用户执行完整的部署。</span><span class="sxs-lookup"><span data-stu-id="8f40a-119">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="8f40a-120">根据目标访问群体的大小，可以添加或删除向外外接步骤。</span><span class="sxs-lookup"><span data-stu-id="8f40a-120">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="8f40a-121">使用管理中心部署 Office 外接程序</span><span class="sxs-lookup"><span data-stu-id="8f40a-121">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="8f40a-122">在开始之前，请参阅 [确定加载项的集中部署是否适用于你的组织](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="8f40a-122">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="8f40a-123">在管理中心中，转到 " **设置** \> **外接程序** " 页。</span><span class="sxs-lookup"><span data-stu-id="8f40a-123">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span> <span data-ttu-id="8f40a-124">如果看不到 **外** 接程序页，请转到 " **设置** \> **集成应用** \> **外** 接程序" 页。</span><span class="sxs-lookup"><span data-stu-id="8f40a-124">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** page.</span></span>
    
2. <span data-ttu-id="8f40a-125">在页面顶部选择 " **部署加载项** "，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8f40a-125">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="8f40a-126">使用集成的应用程序对管理中心进行了更新以获得部署体验。</span><span class="sxs-lookup"><span data-stu-id="8f40a-126">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="8f40a-127">如果看不到上述步骤，请转到 "**设置**" "  >  **集成应用**"，转到 "集中部署" 部分。</span><span class="sxs-lookup"><span data-stu-id="8f40a-127">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="8f40a-128">在 " **集成应用** " 页面顶部，选择 " **外接程序**"。</span><span class="sxs-lookup"><span data-stu-id="8f40a-128">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="8f40a-129">选择一个选项，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="8f40a-129">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="8f40a-130">如果选择了从 Office 应用商店添加外接程序的选项，请将您的外接程序选择。</span><span class="sxs-lookup"><span data-stu-id="8f40a-130">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="8f40a-131">您可以按类别查看可用的加载项： **建议为你**、 **评级**或 **名称**。</span><span class="sxs-lookup"><span data-stu-id="8f40a-131">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="8f40a-132">Office 应用商店仅提供免费的外接程序。</span><span class="sxs-lookup"><span data-stu-id="8f40a-132">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="8f40a-133">目前尚不支持付费加载项。</span><span class="sxs-lookup"><span data-stu-id="8f40a-133">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="8f40a-134">选择加载项后，请接受条款和条件以继续。</span><span class="sxs-lookup"><span data-stu-id="8f40a-134">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="8f40a-135">使用 Office 应用商店选项，更新和增强功能将自动应用于用户。</span><span class="sxs-lookup"><span data-stu-id="8f40a-135">With the Office Store option, updates and enhancements are automatically to users.</span></span>

5. <span data-ttu-id="8f40a-136">在下一页上，选择 " **所有人**"、" **特定用户/组**" 或 " **仅我** " 以指定要向其部署加载项的用户。</span><span class="sxs-lookup"><span data-stu-id="8f40a-136">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="8f40a-137">使用搜索框查找特定用户或组。</span><span class="sxs-lookup"><span data-stu-id="8f40a-137">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE] 
    > <span data-ttu-id="8f40a-138">若要了解适用于外接程序的其他状态，请参阅 [外接程序状态](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8f40a-138">To learn about other states that apply to an add-in, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="8f40a-139">选择“部署”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8f40a-139">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="8f40a-140">部署加载项时，将显示绿色计时周期。</span><span class="sxs-lookup"><span data-stu-id="8f40a-140">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="8f40a-141">按照页面上的说明测试加载项。</span><span class="sxs-lookup"><span data-stu-id="8f40a-141">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8f40a-142">用户可能需要重新启动 Office 以查看应用程序功能区上的外接程序图标。</span><span class="sxs-lookup"><span data-stu-id="8f40a-142">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="8f40a-143">Outlook 加载项最长可能需要24小时才能显示在应用程序功能区上。</span><span class="sxs-lookup"><span data-stu-id="8f40a-143">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>
    
8. <span data-ttu-id="8f40a-144">完成后，选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8f40a-144">When finished, select **Next**.</span></span> <span data-ttu-id="8f40a-145">如果只部署到自己的，则可以选择 " **更改谁有权访问外接程序** 以将其部署到更多用户"。</span><span class="sxs-lookup"><span data-stu-id="8f40a-145">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="8f40a-146">如果已将外接程序部署到组织中的其他成员，请按照说明宣布外接程序的部署。</span><span class="sxs-lookup"><span data-stu-id="8f40a-146">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="8f40a-147">最好通知用户和组已部署的外接程序可用。</span><span class="sxs-lookup"><span data-stu-id="8f40a-147">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="8f40a-148">请考虑发送描述何时以及如何使用外接程序的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8f40a-148">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="8f40a-149">包含或链接，以帮助用户在加载项中遇到问题时可能会帮助用户。</span><span class="sxs-lookup"><span data-stu-id="8f40a-149">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="8f40a-150">为用户和组分配加载项时的注意事项</span><span class="sxs-lookup"><span data-stu-id="8f40a-150">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="8f40a-151">管理员可以为每个人或特定用户和组分配加载项。</span><span class="sxs-lookup"><span data-stu-id="8f40a-151">Admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="8f40a-152">每个选项都有含义：</span><span class="sxs-lookup"><span data-stu-id="8f40a-152">Each option has implications:</span></span>
  
- <span data-ttu-id="8f40a-153">**所有人** 此选项将加载项分配给组织中的每个用户。</span><span class="sxs-lookup"><span data-stu-id="8f40a-153">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="8f40a-154">请谨慎使用此选项，且仅应用于真正在组织中通用的加载项。</span><span class="sxs-lookup"><span data-stu-id="8f40a-154">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="8f40a-155">**用户** 如果向单个用户分配外接程序，然后将该外接程序部署到新用户，则必须先添加新用户。</span><span class="sxs-lookup"><span data-stu-id="8f40a-155">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>
    
- <span data-ttu-id="8f40a-156">**组** 如果将加载项分配给某个组，则会自动为添加到该组的用户分配该外接程序。</span><span class="sxs-lookup"><span data-stu-id="8f40a-156">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="8f40a-157">从组中删除用户时，用户将无法访问加载项。</span><span class="sxs-lookup"><span data-stu-id="8f40a-157">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="8f40a-158">在这两种情况下，管理员无需执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="8f40a-158">In either case, no additional action is required from the admin.</span></span> 

- <span data-ttu-id="8f40a-159">**仅我** 如果只向自己分配加载项，则会将外接程序分配给您的帐户，这是测试外接程序的理想选择。</span><span class="sxs-lookup"><span data-stu-id="8f40a-159">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>
    
<span data-ttu-id="8f40a-160">您的组织的正确选项取决于您的配置。</span><span class="sxs-lookup"><span data-stu-id="8f40a-160">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="8f40a-161">但是，建议使用组进行分配。</span><span class="sxs-lookup"><span data-stu-id="8f40a-161">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="8f40a-162">作为管理员，您可能会发现使用组管理外接程序并控制这些组的成员身份，而不是每次分配单个用户，这会更加轻松。</span><span class="sxs-lookup"><span data-stu-id="8f40a-162">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="8f40a-163">在某些情况下，您可能希望通过手动分配用户来限制对一小部分用户进行的访问。</span><span class="sxs-lookup"><span data-stu-id="8f40a-163">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="8f40a-164">有关 Office 外接程序安全性的详细信息</span><span class="sxs-lookup"><span data-stu-id="8f40a-164">More about Office add-ins security</span></span>

<span data-ttu-id="8f40a-p118">Office 加载项结合了一个包含加载项相关元数据的 XML 清单文件，但最重要的是它指向包含所有代码和逻辑的 Web 应用程序。加载项的功能范围很广。例如，加载项可以：</span><span class="sxs-lookup"><span data-stu-id="8f40a-p118">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="8f40a-168">显示数据。</span><span class="sxs-lookup"><span data-stu-id="8f40a-168">Display data.</span></span>
    
- <span data-ttu-id="8f40a-169">读取用户文档以提供上下文服务。</span><span class="sxs-lookup"><span data-stu-id="8f40a-169">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="8f40a-170">从用户文档读取数据并向用户文档写入数据，以便向该用户提供价值。</span><span class="sxs-lookup"><span data-stu-id="8f40a-170">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="8f40a-171">若要详细了解 Office 加载项的类型和功能，请参阅 [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)（Office 加载项平台概述），尤其是"Anatomy of an Office Add-in"（Office 加载项分析）一节。</span><span class="sxs-lookup"><span data-stu-id="8f40a-171">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="8f40a-p119">若要与用户文档进行交互，加载项需要在清单中声明需要哪些权限。五级 JavaScript API 访问权限模型为任务窗格加载项的用户提供隐私和安全性的基础。Office 应用商店 中的大多数加载项是 ReadWriteDocument 级别，几乎所有加载项均至少支持 ReadDocument 级别。有关权限级别的详细信息，请参阅 [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)（请求在内容和任务窗格加载项中使用 API 的权限）。</span><span class="sxs-lookup"><span data-stu-id="8f40a-p119">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="8f40a-p120">更新清单时，通常更改加载项的图标和文本。有时会更改加载项命令。但是，不会更改加载项的权限。Web 应用程序（加载项的所有代码和逻辑在其中运行）可以随时更改，这是 Web 应用程序的特性。</span><span class="sxs-lookup"><span data-stu-id="8f40a-p120">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="8f40a-179">加载项更新的情况如下：</span><span class="sxs-lookup"><span data-stu-id="8f40a-179">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="8f40a-p121">**业务线加载项：** 在这种情况下，管理员显式上传清单，加载项需要管理员上传新的清单文件以支持元数据的更改。相关 Office 应用程序下次启动时，该加载项会更新。Web 应用程序可以随时更改。</span><span class="sxs-lookup"><span data-stu-id="8f40a-p121">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="8f40a-183">管理员无需删除 LOB 加载项即可进行更新。</span><span class="sxs-lookup"><span data-stu-id="8f40a-183">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="8f40a-184">在 "外接程序" 部分中，管理员只需单击 LOB 外接程序，然后选择右下角的 " **更新" 按钮** 即可。</span><span class="sxs-lookup"><span data-stu-id="8f40a-184">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="8f40a-185">仅当新外接程序的版本大于现有加载项的版本时，更新才有效。</span><span class="sxs-lookup"><span data-stu-id="8f40a-185">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="8f40a-p123">**Office 应用商店加载项：** 管理员从 Office 应用商店 中选择加载项后，如果 Office 应用商店 中更新了加载项，则该加载项会稍后以集中式部署方式更新。相关 Office 应用程序下次启动时，该加载项会更新。Web 应用程序可以随时更改。</span><span class="sxs-lookup"><span data-stu-id="8f40a-p123">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 
  
## <a name="learn-more"></a><span data-ttu-id="8f40a-189">了解更多</span><span class="sxs-lookup"><span data-stu-id="8f40a-189">Learn more</span></span>

[<span data-ttu-id="8f40a-190">在管理中心管理加载项</span><span class="sxs-lookup"><span data-stu-id="8f40a-190">Manage add-ins in the admin center</span></span>](manage-addins-in-the-admin-center.md)

<span data-ttu-id="8f40a-191">[生成 Office 外接程序](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals)。</span><span class="sxs-lookup"><span data-stu-id="8f40a-191">[Building Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals).</span></span>

[<span data-ttu-id="8f40a-192">向应用商店中的未成年人和收购外接程序</span><span class="sxs-lookup"><span data-stu-id="8f40a-192">Minors and acquiring add-ins from the store</span></span>](minors-and-acquiring-addins-from-the-store.md)
  
[<span data-ttu-id="8f40a-193">使用集中部署 PowerShell cmdlet 管理外接程序</span><span class="sxs-lookup"><span data-stu-id="8f40a-193">Use Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[<span data-ttu-id="8f40a-194">疑难解答：用户看不到外接程序</span><span class="sxs-lookup"><span data-stu-id="8f40a-194">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
