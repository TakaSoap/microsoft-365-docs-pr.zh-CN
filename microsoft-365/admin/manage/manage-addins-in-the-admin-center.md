---
title: 在管理中心管理加载项
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
description: 了解如何使用集中式加载项将加载项部署到组织中用户和组。
ms.openlocfilehash: 836dfa7a0c1b6cf1550e5c139bc0ca36be8f5424
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470937"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="b8607-103">在管理中心管理加载项</span><span class="sxs-lookup"><span data-stu-id="b8607-103">Manage add-ins in the admin center</span></span>

<span data-ttu-id="b8607-104">Office 加载项有助于个性化设置文档，并简化访问 Web (方式，请参阅开始使用 [Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 加载项) 。</span><span class="sxs-lookup"><span data-stu-id="b8607-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="b8607-105">管理员为组织中用户部署外接程序后，管理员可以关闭或打开外接程序、编辑、删除和管理对外接程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b8607-105">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="b8607-106">若要详细了解如何从管理中心安装加载项，请参阅在管理中心部署 [加载项](./manage-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="b8607-106">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="b8607-107">加载项状态</span><span class="sxs-lookup"><span data-stu-id="b8607-107">Add-in states</span></span>

<span data-ttu-id="b8607-108">加载项可以"开"或"关 **"** 状态。 </span><span class="sxs-lookup"><span data-stu-id="b8607-108">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="b8607-109">**状态**</span><span class="sxs-lookup"><span data-stu-id="b8607-109">**State**</span></span>|<span data-ttu-id="b8607-110">**状态出现的原因**</span><span class="sxs-lookup"><span data-stu-id="b8607-110">**How the state occurs**</span></span>|<span data-ttu-id="b8607-111">**影响**</span><span class="sxs-lookup"><span data-stu-id="b8607-111">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b8607-112">**Active**</span><span class="sxs-lookup"><span data-stu-id="b8607-112">**Active**</span></span>  <br/> |<span data-ttu-id="b8607-113">管理员已上载外接程序并将其分配给用户或组。</span><span class="sxs-lookup"><span data-stu-id="b8607-113">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="b8607-114">分配了加载项的用户和组可在相关客户端中看到它。</span><span class="sxs-lookup"><span data-stu-id="b8607-114">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="b8607-115">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="b8607-115">**Turned off**</span></span>  <br/> |<span data-ttu-id="b8607-116">管理员已禁用加载项。</span><span class="sxs-lookup"><span data-stu-id="b8607-116">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="b8607-117">分配了外接程序的用户和组无法再访问它。</span><span class="sxs-lookup"><span data-stu-id="b8607-117">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="b8607-118">如果外接程序的状态更改为"可用"，则用户和组将再次有权访问它。</span><span class="sxs-lookup"><span data-stu-id="b8607-118">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="b8607-119">**已删除**</span><span class="sxs-lookup"><span data-stu-id="b8607-119">**Deleted**</span></span>  <br/> |<span data-ttu-id="b8607-120">管理员已删除加载项。</span><span class="sxs-lookup"><span data-stu-id="b8607-120">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="b8607-121">分配了加载项的用户和组无法再访问它。</span><span class="sxs-lookup"><span data-stu-id="b8607-121">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="b8607-122">如果没有人再使用加载项，请考虑将其删除。</span><span class="sxs-lookup"><span data-stu-id="b8607-122">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="b8607-123">例如，如果仅在一年的特定时间使用外接程序，则关闭外接程序可能有意义。</span><span class="sxs-lookup"><span data-stu-id="b8607-123">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="b8607-124">删除加载项</span><span class="sxs-lookup"><span data-stu-id="b8607-124">Delete an add-in</span></span>

<span data-ttu-id="b8607-125">您还可以删除已部署的外接程序。</span><span class="sxs-lookup"><span data-stu-id="b8607-125">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="b8607-126">In the admin center， go to the **Settings**  >  **Services & add-ins** page.</span><span class="sxs-lookup"><span data-stu-id="b8607-126">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="b8607-127">管理中心将更新为集成应用的部署体验。</span><span class="sxs-lookup"><span data-stu-id="b8607-127">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="b8607-128">如果看不到上述步骤，请转到"集中部署"部分，**具体方法为** 转到"设置""集成应用  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="b8607-128">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="b8607-129">在"集成应用"**页面顶部**，选择"**加载项"。**</span><span class="sxs-lookup"><span data-stu-id="b8607-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="b8607-130">选择已部署的外接程序。</span><span class="sxs-lookup"><span data-stu-id="b8607-130">Select the deployed add-in.</span></span>

3. <span data-ttu-id="b8607-131">单击"**删除外接程序"。**</span><span class="sxs-lookup"><span data-stu-id="b8607-131">Click on **Delete Add-In**.</span></span> <span data-ttu-id="b8607-132">删除右下角的"加载项"按钮。</span><span class="sxs-lookup"><span data-stu-id="b8607-132">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="b8607-133">验证您的选择，然后选择"**删除外接程序"。**</span><span class="sxs-lookup"><span data-stu-id="b8607-133">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="b8607-134">编辑外接程序访问</span><span class="sxs-lookup"><span data-stu-id="b8607-134">Edit add-in access</span></span>

<span data-ttu-id="b8607-135">部署后，管理员还可以管理用户对外接程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b8607-135">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="b8607-136">In the admin center， go to the **Settings**  >  **Services & add-ins** page.</span><span class="sxs-lookup"><span data-stu-id="b8607-136">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="b8607-137">管理中心将更新为集成应用的部署体验。</span><span class="sxs-lookup"><span data-stu-id="b8607-137">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="b8607-138">如果看不到上述步骤，请转到"集中部署"部分，**具体方法为** 转到"设置""集成应用  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="b8607-138">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="b8607-139">在"集成应用"**页面顶部**，选择"**加载项"。**</span><span class="sxs-lookup"><span data-stu-id="b8607-139">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="b8607-140">选择已部署的外接程序。</span><span class="sxs-lookup"><span data-stu-id="b8607-140">Select the deployed add-in.</span></span>

3. <span data-ttu-id="b8607-141">单击"**谁** 具有访问权限 **"下的"编辑"。**</span><span class="sxs-lookup"><span data-stu-id="b8607-141">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="b8607-142">保存更改。</span><span class="sxs-lookup"><span data-stu-id="b8607-142">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="b8607-143">通过在所有客户端上关闭 Office 应用商店来阻止外接程序下载 (Outlook) </span><span class="sxs-lookup"><span data-stu-id="b8607-143">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="b8607-144">Outlook 外接程序安装由不同的进程 [管理](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="b8607-144">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="b8607-145">作为组织，你可能希望阻止从 Office 应用商店下载新的 Office 外接程序。</span><span class="sxs-lookup"><span data-stu-id="b8607-145">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="b8607-146">这可与集中部署结合使用，以确保仅向组织内部的用户部署经组织核准的外接程序。</span><span class="sxs-lookup"><span data-stu-id="b8607-146">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="b8607-147">**关闭加载项购置**</span><span class="sxs-lookup"><span data-stu-id="b8607-147">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="b8607-148">在管理中心，转到“**设置**”\> [服务和加载项](https://go.microsoft.com/fwlink/p/?linkid=2053743)页面。</span><span class="sxs-lookup"><span data-stu-id="b8607-148">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="b8607-149">管理中心将更新为集成应用的部署体验。</span><span class="sxs-lookup"><span data-stu-id="b8607-149">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="b8607-150">如果看不到上述步骤，请转到"集中部署"部分，**具体方法为** 转到"设置""集成应用  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="b8607-150">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="b8607-151">在"集成应用"**页面顶部**，选择"**加载项"。**</span><span class="sxs-lookup"><span data-stu-id="b8607-151">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="b8607-152">选择 **"用户拥有的应用和服务"。**</span><span class="sxs-lookup"><span data-stu-id="b8607-152">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="b8607-153">清除允许用户访问 Office 商店的选项。</span><span class="sxs-lookup"><span data-stu-id="b8607-153">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="b8607-154">这将阻止所有用户从应用商店获取以下外接程序。</span><span class="sxs-lookup"><span data-stu-id="b8607-154">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="b8607-155">适用于 Word、Excel 和 PowerPoint 2016 的外接程序来自：</span><span class="sxs-lookup"><span data-stu-id="b8607-155">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="b8607-156">Windows</span><span class="sxs-lookup"><span data-stu-id="b8607-156">Windows</span></span>
    
  - <span data-ttu-id="b8607-157">Mac</span><span class="sxs-lookup"><span data-stu-id="b8607-157">Mac</span></span>
    
  - <span data-ttu-id="b8607-158">Office</span><span class="sxs-lookup"><span data-stu-id="b8607-158">Office</span></span>
    
    
- <span data-ttu-id="b8607-159">从 **AppSource 内开始购置**</span><span class="sxs-lookup"><span data-stu-id="b8607-159">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="b8607-160">Microsoft 365 中的外接程序</span><span class="sxs-lookup"><span data-stu-id="b8607-160">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="b8607-161">尝试访问应用商店的用户将看到以下消息：抱歉 **，Microsoft 365** 已配置为阻止单独获取 Office 应用商店外接程序。</span><span class="sxs-lookup"><span data-stu-id="b8607-161">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="b8607-162">以下版本支持关闭 Office 应用商店：</span><span class="sxs-lookup"><span data-stu-id="b8607-162">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="b8607-163">Windows：16.0.9001 - 当前可用。</span><span class="sxs-lookup"><span data-stu-id="b8607-163">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="b8607-164">Mac：16.10.18011401 - 当前可用。</span><span class="sxs-lookup"><span data-stu-id="b8607-164">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="b8607-165">iOS：2.9.18010804 - 当前可用。</span><span class="sxs-lookup"><span data-stu-id="b8607-165">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="b8607-166">Web - 当前可用。</span><span class="sxs-lookup"><span data-stu-id="b8607-166">The web - Currently available.</span></span>
    
<span data-ttu-id="b8607-167">这不会阻止管理员使用集中部署从 Office 应用商店分配外接程序。</span><span class="sxs-lookup"><span data-stu-id="b8607-167">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="b8607-168">若要防止用户使用 Microsoft 帐户登录，可以将登录限制为仅使用组织帐户。</span><span class="sxs-lookup"><span data-stu-id="b8607-168">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="b8607-169">有关详细信息，请参阅[Identity， authentication， and authorization in Office 2016。](/DeployOffice/security/identity-authentication-and-authorization-in-office)</span><span class="sxs-lookup"><span data-stu-id="b8607-169">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE]
> <span data-ttu-id="b8607-170">阻止用户访问 Office 商店也会阻止他们旁加载 [Office 外接程序进行测试](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="b8607-170">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="b8607-171">有关外接程序的最终用户体验的更多内容</span><span class="sxs-lookup"><span data-stu-id="b8607-171">More about the end user experience with add-ins</span></span>

<span data-ttu-id="b8607-172">部署外接程序后，最终用户可以开始在 Office 应用程序中使用它 (请参阅开始使用 [Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 外接程序) 。</span><span class="sxs-lookup"><span data-stu-id="b8607-172">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="b8607-173">外接程序将显示在外接程序支持的所有平台上。</span><span class="sxs-lookup"><span data-stu-id="b8607-173">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="b8607-p109">如果加载项支持加载项命令，则 Office 功能区上会显示命令。在以下示例中，显示" **引文** "加载项的" **搜索引文** "命令。</span><span class="sxs-lookup"><span data-stu-id="b8607-p109">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![具有搜索引文的 Office 功能区](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="b8607-177">如果部署的加载项不支持加载项命令，或者要查看所有部署的加载项，可以通过我的加载项 **查看**。</span><span class="sxs-lookup"><span data-stu-id="b8607-177">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="b8607-178">在 Word 2016、Excel 2016 或 PowerPoint 2016 中</span><span class="sxs-lookup"><span data-stu-id="b8607-178">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="b8607-179">选择 **" \> 插入我的外接程序"。**</span><span class="sxs-lookup"><span data-stu-id="b8607-179">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="b8607-180">选择 Office 加载项窗口中的" **由管理员管理** "选项卡。</span><span class="sxs-lookup"><span data-stu-id="b8607-180">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="b8607-181">双击先前部署的加载项（在本例中是" **引文** "）。</span><span class="sxs-lookup"><span data-stu-id="b8607-181">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="b8607-182">!["Office 加载项"页的"管理""托管"选项卡](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="b8607-182">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="b8607-183">在 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="b8607-183">In Outlook</span></span>

1. <span data-ttu-id="b8607-184">在"**主页"** 功能区上，选择 **"获取外接程序"。**</span><span class="sxs-lookup"><span data-stu-id="b8607-184">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="b8607-185">![Outlook 中的'应用商店'按钮](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="b8607-185">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="b8607-186">在 **左侧导航中选择** "管理员管理"。</span><span class="sxs-lookup"><span data-stu-id="b8607-186">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="b8607-187">了解更多</span><span class="sxs-lookup"><span data-stu-id="b8607-187">Learn more</span></span>

[<span data-ttu-id="b8607-188">在管理中心部署加载项</span><span class="sxs-lookup"><span data-stu-id="b8607-188">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

<span data-ttu-id="b8607-189">深入了解如何创建和构建 [Office 加载项](/office/dev/add-ins/overview/office-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="b8607-189">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="b8607-190">[使用集中部署 PowerShell cmdlet 管理外接程序](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="b8607-190">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md).</span></span>
  
[<span data-ttu-id="b8607-191">疑难解答：用户看不到外接程序</span><span class="sxs-lookup"><span data-stu-id="b8607-191">Troubleshoot: User not seeing add-ins</span></span>](/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="b8607-192">次要加载项和从 Microsoft Store 获取加载项</span><span class="sxs-lookup"><span data-stu-id="b8607-192">Minors and acquiring add-ins from the Microsoft Store</span></span>](./minors-and-acquiring-addins-from-the-store.md)