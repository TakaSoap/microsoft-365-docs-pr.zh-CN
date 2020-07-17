---
title: 在管理中心中管理外接程序
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
ms.openlocfilehash: caaea8404c099f56704d21684323a4b20e61f52d
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103086"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="8a053-103">在管理中心中管理外接程序</span><span class="sxs-lookup"><span data-stu-id="8a053-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8a053-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="8a053-104">The admin center is changing.</span></span> <span data-ttu-id="8a053-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="8a053-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="8a053-106">Office 加载项可帮助您对文档进行个性化设置，并简化访问 web 上的信息的方式 (请参阅[开始使用 Office 加载项](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)) 。</span><span class="sxs-lookup"><span data-stu-id="8a053-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="8a053-107">在管理员为组织中的用户部署外接程序后，管理员可以关闭或打开、编辑、删除和管理对外接程序的访问的外接程序。</span><span class="sxs-lookup"><span data-stu-id="8a053-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="8a053-108">有关从管理中心安装外接程序的详细信息，请参阅[在管理中心部署外接程序](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="8a053-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="8a053-109">加载项状态</span><span class="sxs-lookup"><span data-stu-id="8a053-109">Add-in states</span></span>

<span data-ttu-id="8a053-110">外接程序可以处于 "**打开**" 或 "**关闭**" 状态。</span><span class="sxs-lookup"><span data-stu-id="8a053-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="8a053-111">**状态**</span><span class="sxs-lookup"><span data-stu-id="8a053-111">**State**</span></span>|<span data-ttu-id="8a053-112">**状态出现的原因**</span><span class="sxs-lookup"><span data-stu-id="8a053-112">**How the state occurs**</span></span>|<span data-ttu-id="8a053-113">**影响**</span><span class="sxs-lookup"><span data-stu-id="8a053-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8a053-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="8a053-114">**Active**</span></span>  <br/> |<span data-ttu-id="8a053-115">管理员上载了加载项，并将其分配给用户或组。</span><span class="sxs-lookup"><span data-stu-id="8a053-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="8a053-116">分配了加载项的用户和组可在相关客户端中看到它。</span><span class="sxs-lookup"><span data-stu-id="8a053-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="8a053-117">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="8a053-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="8a053-118">管理员已禁用加载项。</span><span class="sxs-lookup"><span data-stu-id="8a053-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="8a053-119">分配了外接程序的用户和组无法再访问它。</span><span class="sxs-lookup"><span data-stu-id="8a053-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="8a053-120">如果外接程序的状态更改为"可用"，则用户和组将再次有权访问它。</span><span class="sxs-lookup"><span data-stu-id="8a053-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="8a053-121">**已删除**</span><span class="sxs-lookup"><span data-stu-id="8a053-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="8a053-122">管理员已删除加载项。</span><span class="sxs-lookup"><span data-stu-id="8a053-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="8a053-123">分配了加载项的用户和组无法再访问它。</span><span class="sxs-lookup"><span data-stu-id="8a053-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="8a053-124">如果没有人再使用加载项，请考虑删除外接程序。</span><span class="sxs-lookup"><span data-stu-id="8a053-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="8a053-125">例如，如果外接程序仅在一年的特定时间内使用，则关闭外接程序可能会有意义。</span><span class="sxs-lookup"><span data-stu-id="8a053-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="8a053-126">删除外接程序</span><span class="sxs-lookup"><span data-stu-id="8a053-126">Delete an add-in</span></span>

<span data-ttu-id="8a053-127">您还可以删除已部署的外接程序。</span><span class="sxs-lookup"><span data-stu-id="8a053-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="8a053-128">在 "管理中心" 中，转到 "**设置**  >  **服务" & "加载项**" 页面。</span><span class="sxs-lookup"><span data-stu-id="8a053-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="8a053-129">选择部署的加载项。</span><span class="sxs-lookup"><span data-stu-id="8a053-129">Select the deployed add-in.</span></span>

3. <span data-ttu-id="8a053-130">单击 "**删除加载项**"。</span><span class="sxs-lookup"><span data-stu-id="8a053-130">Click on **Delete Add-In**.</span></span> <span data-ttu-id="8a053-131">移除右下角的外接端按钮。</span><span class="sxs-lookup"><span data-stu-id="8a053-131">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="8a053-132">验证您的选择，然后选择 "**删除外接程序**"。</span><span class="sxs-lookup"><span data-stu-id="8a053-132">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="8a053-133">编辑外接访问</span><span class="sxs-lookup"><span data-stu-id="8a053-133">Edit add-in access</span></span>

<span data-ttu-id="8a053-134">部署后，管理员还可以管理用户对外接程序的访问。</span><span class="sxs-lookup"><span data-stu-id="8a053-134">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="8a053-135">在 "管理中心" 中，转到 "**设置**  >  **服务" & "加载项**" 页面。</span><span class="sxs-lookup"><span data-stu-id="8a053-135">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="8a053-136">选择部署的加载项。</span><span class="sxs-lookup"><span data-stu-id="8a053-136">Select the deployed add-in.</span></span>

3. <span data-ttu-id="8a053-137">单击 "**有权访问**" 下的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="8a053-137">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="8a053-138">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8a053-138">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="8a053-139">通过在除 Outlook) 之外的所有客户端中关闭 Office 应用商店来阻止加载项下载 (</span><span class="sxs-lookup"><span data-stu-id="8a053-139">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="8a053-140">Outlook 外接程序安装由[不同的进程](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)进行管理。</span><span class="sxs-lookup"><span data-stu-id="8a053-140">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="8a053-141">作为组织，您可能希望阻止从 Office 应用商店下载新的 Office 加载项。</span><span class="sxs-lookup"><span data-stu-id="8a053-141">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="8a053-142">这可与集中部署结合使用，以确保仅向组织中的用户部署组织批准的外接程序。</span><span class="sxs-lookup"><span data-stu-id="8a053-142">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="8a053-143">**关闭外接的获取**</span><span class="sxs-lookup"><span data-stu-id="8a053-143">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="8a053-144">在管理中心，转到“**设置**”\> [服务和加载项](https://go.microsoft.com/fwlink/p/?linkid=2053743)页面。</span><span class="sxs-lookup"><span data-stu-id="8a053-144">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>
    
3. <span data-ttu-id="8a053-145">选择 "**用户拥有的应用和服务**"。</span><span class="sxs-lookup"><span data-stu-id="8a053-145">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="8a053-146">清除 "允许用户访问 Office 应用商店" 选项。</span><span class="sxs-lookup"><span data-stu-id="8a053-146">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="8a053-147">这将阻止所有用户从存储中获取以下外接程序。</span><span class="sxs-lookup"><span data-stu-id="8a053-147">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="8a053-148">Word、Excel 和 PowerPoint 2016 的外接程序来自：</span><span class="sxs-lookup"><span data-stu-id="8a053-148">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="8a053-149">Windows</span><span class="sxs-lookup"><span data-stu-id="8a053-149">Windows</span></span>
    
  - <span data-ttu-id="8a053-150">Mac</span><span class="sxs-lookup"><span data-stu-id="8a053-150">Mac</span></span>
    
  - <span data-ttu-id="8a053-151">Office</span><span class="sxs-lookup"><span data-stu-id="8a053-151">Office</span></span>
    
    
- <span data-ttu-id="8a053-152">从**AppSource**中开始的收购</span><span class="sxs-lookup"><span data-stu-id="8a053-152">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="8a053-153">Microsoft 365 中的外接程序</span><span class="sxs-lookup"><span data-stu-id="8a053-153">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="8a053-154">尝试访问应用商店的用户将看到以下消息：**抱歉，Microsoft 365 已配置为阻止单独获取 Office 应用商店外接程序。**</span><span class="sxs-lookup"><span data-stu-id="8a053-154">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="8a053-155">以下版本提供了对 Office 应用商店关闭的支持：</span><span class="sxs-lookup"><span data-stu-id="8a053-155">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="8a053-156">Windows： 16.0.9001-当前可用。</span><span class="sxs-lookup"><span data-stu-id="8a053-156">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="8a053-157">Mac： 16.10.18011401-当前可用。</span><span class="sxs-lookup"><span data-stu-id="8a053-157">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="8a053-158">iOS： 2.9.18010804-当前可用。</span><span class="sxs-lookup"><span data-stu-id="8a053-158">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="8a053-159">Web 当前可用。</span><span class="sxs-lookup"><span data-stu-id="8a053-159">The web - Currently available.</span></span>
    
<span data-ttu-id="8a053-160">这不会阻止管理员使用集中部署从 Office 应用商店分配外接程序。</span><span class="sxs-lookup"><span data-stu-id="8a053-160">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="8a053-161">若要阻止用户使用 Microsoft 帐户登录，可以将登录限制为仅使用组织帐户。</span><span class="sxs-lookup"><span data-stu-id="8a053-161">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="8a053-162">有关详细信息，请参阅[Office 2016 中的标识、身份验证和授权](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8a053-162">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="8a053-163">有关外接程序的最终用户体验的详细信息</span><span class="sxs-lookup"><span data-stu-id="8a053-163">More about the end user experience with add-ins</span></span>

<span data-ttu-id="8a053-164">部署加载项后，最终用户可以开始在 Office 应用程序中使用它 (请参阅[开始使用 Office 加载项](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)) 。</span><span class="sxs-lookup"><span data-stu-id="8a053-164">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="8a053-165">外接程序将显示在外接程序支持的所有平台上。</span><span class="sxs-lookup"><span data-stu-id="8a053-165">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="8a053-p107">如果加载项支持加载项命令，则 Office 功能区上会显示命令。在以下示例中，显示" **引文** "加载项的" **搜索引文** "命令。</span><span class="sxs-lookup"><span data-stu-id="8a053-p107">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![带有搜索引文的 Office 功能区](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="8a053-169">如果部署的外接程序不支持外接程序命令，或者如果您想要查看所有部署的加载项，可以通过**我的外接**程序查看它们。</span><span class="sxs-lookup"><span data-stu-id="8a053-169">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="8a053-170">在 Word 2016、Excel 2016 或 PowerPoint 2016 中</span><span class="sxs-lookup"><span data-stu-id="8a053-170">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="8a053-171">选择\*\* \> "插入我的外接程序"\*\*。</span><span class="sxs-lookup"><span data-stu-id="8a053-171">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="8a053-172">选择 Office 加载项窗口中的" **由管理员管理** "选项卡。</span><span class="sxs-lookup"><span data-stu-id="8a053-172">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="8a053-173">双击先前部署的加载项（在本例中是" **引文** "）。</span><span class="sxs-lookup"><span data-stu-id="8a053-173">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="8a053-174">!["Office 外接程序" 页的 "管理托管" 选项卡](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="8a053-174">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="8a053-175">在 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="8a053-175">In Outlook</span></span>

1. <span data-ttu-id="8a053-176">在 "**主页**" 功能区上，选择 "**获取外接程序**"。</span><span class="sxs-lookup"><span data-stu-id="8a053-176">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="8a053-177">![Outlook 中的'应用商店'按钮](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="8a053-177">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="8a053-178">在左侧导航中选择 "**管理员管理**"。</span><span class="sxs-lookup"><span data-stu-id="8a053-178">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="8a053-179">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="8a053-179">Learn more</span></span>

[<span data-ttu-id="8a053-180">在管理中心部署外接程序</span><span class="sxs-lookup"><span data-stu-id="8a053-180">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="8a053-181">深入了解如何创建和构建 [Office 加载项](https://go.microsoft.com/fwlink/p/?linkid=846362)。</span><span class="sxs-lookup"><span data-stu-id="8a053-181">Learn more about creating and building [Office Add-ins](https://go.microsoft.com/fwlink/p/?linkid=846362).</span></span>
  
<span data-ttu-id="8a053-182">[使用集中部署 PowerShell cmdlet 管理外接程序](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="8a053-182">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="8a053-183">疑难解答：用户看不到外接程序</span><span class="sxs-lookup"><span data-stu-id="8a053-183">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="8a053-184">来自 Microsoft Store 的未成年人和收购外接程序</span><span class="sxs-lookup"><span data-stu-id="8a053-184">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)