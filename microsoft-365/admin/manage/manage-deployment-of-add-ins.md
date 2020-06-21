---
title: 在管理中心中管理外接程序的部署
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
ms.openlocfilehash: 25a4cd4147f6388cdbd8982eb10624e7b7e8f6cb
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780117"
---
# <a name="manage-deployment-of-add-ins-in-the-microsoft-365-admin-center"></a><span data-ttu-id="620eb-103">在 Microsoft 365 管理中心管理加载项的部署</span><span class="sxs-lookup"><span data-stu-id="620eb-103">Manage deployment of add-ins in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="620eb-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="620eb-104">The admin center is changing.</span></span> <span data-ttu-id="620eb-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="620eb-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="620eb-106">Office 加载项可帮助用户个性化设置文档并加速访问 Web 上的信息（请参阅[开始使用 Office 加载项](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)）。</span><span class="sxs-lookup"><span data-stu-id="620eb-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="620eb-107">作为管理员，您可以为组织中的用户部署 Office 外接程序。</span><span class="sxs-lookup"><span data-stu-id="620eb-107">As an admin, you can deploy Office add-ins for the users in your organization.</span></span> <span data-ttu-id="620eb-108">您可以使用 Microsoft 365 管理中心中的集中部署功能来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="620eb-108">You can do this using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="620eb-109">集中部署是大多数管理员为将外接程序部署到组织内的用户和组的建议功能和功能最丰富的方式。</span><span class="sxs-lookup"><span data-stu-id="620eb-109">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> <span data-ttu-id="620eb-110">若要详细了解如何确定组织是否可以支持集中部署，请参阅[确定加载项的集中部署是否适用于你的组织](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="620eb-110">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
<span data-ttu-id="620eb-111">集中部署有以下优点：</span><span class="sxs-lookup"><span data-stu-id="620eb-111">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="620eb-112">全局管理员可以将外接程序直接分配给用户、通过一个组将加载项分配给多个用户，或分配给租户中的所有人。</span><span class="sxs-lookup"><span data-stu-id="620eb-112">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the tenant.</span></span>
    
- <span data-ttu-id="620eb-113">When the relevant Office application starts, the add-in automatically downloads for the user.</span><span class="sxs-lookup"><span data-stu-id="620eb-113">When the relevant Office application starts, the add-in automatically downloads for the user.</span></span> <span data-ttu-id="620eb-114">If the add-in supports add-in commands, the add-in automatically appears in the Ribbon within the Office application.</span><span class="sxs-lookup"><span data-stu-id="620eb-114">If the add-in supports add-in commands, the add-in automatically appears in the Ribbon within the Office application.</span></span>
    
- <span data-ttu-id="620eb-115">如果管理员关闭或删除加载项，或者从 Azure Active Directory 或将外接程序分配到的组中删除了用户，外接程序将不再显示给用户。</span><span class="sxs-lookup"><span data-stu-id="620eb-115">Add-ins will no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="620eb-116">对于 Word，Excel 和 PowerPoint 使用[Sharepoint 应用程序目录](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)将外接程序部署到本地环境中的用户，而无需连接到 Microsoft 365 和/或支持 SharePoint 外接程序。</span><span class="sxs-lookup"><span data-stu-id="620eb-116">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="620eb-117">> Outlook 使用 Exchange 控制面板在本地环境中部署，而无需连接到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="620eb-117">>  For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span> > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="620eb-118">部署 Office 外接程序的推荐方法</span><span class="sxs-lookup"><span data-stu-id="620eb-118">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="620eb-119">Consider rolling out add-ins in a phased approach to help ensure your add-in deployment goes smoothly.</span><span class="sxs-lookup"><span data-stu-id="620eb-119">Consider rolling out add-ins in a phased approach to help ensure your add-in deployment goes smoothly.</span></span> <span data-ttu-id="620eb-120">We recommend the following plan:</span><span class="sxs-lookup"><span data-stu-id="620eb-120">We recommend the following plan:</span></span>
  
1. <span data-ttu-id="620eb-121">Roll-out the add-in to a small set of business stakeholders and members of the IT department.</span><span class="sxs-lookup"><span data-stu-id="620eb-121">Roll-out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="620eb-122">Evaluate if the deployment was successful, and if so, move on to step 2.</span><span class="sxs-lookup"><span data-stu-id="620eb-122">Evaluate if the deployment was successful, and if so, move on to step 2.</span></span>
    
2. <span data-ttu-id="620eb-123">Roll-out to a larger set of individuals within the business who will be using the add-in.</span><span class="sxs-lookup"><span data-stu-id="620eb-123">Roll-out to a larger set of individuals within the business who will be using the add-in.</span></span> <span data-ttu-id="620eb-124">Again, evaluate results and, if all went well, go to the next step of a full deployment.</span><span class="sxs-lookup"><span data-stu-id="620eb-124">Again, evaluate results and, if all went well, go to the next step of a full deployment.</span></span>
    
3. <span data-ttu-id="620eb-125">全面向目标受众用户推出加载项。</span><span class="sxs-lookup"><span data-stu-id="620eb-125">Full rollout to target audience of users.</span></span>
    
<span data-ttu-id="620eb-126">根据目标受众的规模，可能需要添加或移除推出步骤。</span><span class="sxs-lookup"><span data-stu-id="620eb-126">Depending on the size of the target audience, you may want to add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="620eb-127">使用管理中心部署 Office 外接程序</span><span class="sxs-lookup"><span data-stu-id="620eb-127">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="620eb-128">在开始之前，请参阅[确定加载项的集中部署是否适用于你的组织](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="620eb-128">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

  
1. <span data-ttu-id="620eb-129">在管理中心中，转到 "**设置** \> **外接程序**" 页。</span><span class="sxs-lookup"><span data-stu-id="620eb-129">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span>
    
2. <span data-ttu-id="620eb-130">在页面顶部选择 "**部署加载项**"。</span><span class="sxs-lookup"><span data-stu-id="620eb-130">Select **Deploy Add-in** at the top of the page.</span></span> <span data-ttu-id="620eb-131">在 "概述" 页上，选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="620eb-131">On the overview page, select **Next**.</span></span>
    
3. <span data-ttu-id="620eb-132">选择一个选项，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="620eb-132">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="620eb-133">如果选择了从 Office 应用商店添加加载项的选项，现在可以将加载项选择。</span><span class="sxs-lookup"><span data-stu-id="620eb-133">If you selected the option to add an add-in from the Office Store, you can now make your add-in selection.</span></span> <span data-ttu-id="620eb-134">请注意，可以按" **建议** "、" **评级** "或" **名称** "查看可用加载项。</span><span class="sxs-lookup"><span data-stu-id="620eb-134">Notice that you can view available add-ins via categories of **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="620eb-135">仅可从 Office Store 添加免费加载项。</span><span class="sxs-lookup"><span data-stu-id="620eb-135">Only free add-ins are available to add from the Office Store.</span></span> <span data-ttu-id="620eb-136">目前尚不支持付费加载项。</span><span class="sxs-lookup"><span data-stu-id="620eb-136">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="620eb-137">选择你的外接程序后，你将需要同意一些其他条款和条件才能继续。</span><span class="sxs-lookup"><span data-stu-id="620eb-137">Once you've selected your add-in, you will need to agree to some additional terms and conditions in order to proceed.</span></span> <br/><br/> <span data-ttu-id="620eb-138">注意：通过 Office 应用商店选项，无需你的干预，即可自动将对外接程序的更新和增强提供给用户。</span><span class="sxs-lookup"><span data-stu-id="620eb-138">NOTE: With the Office Store option, updates and enhancements to the add-in will automatically be made available to users without your intervention.</span></span>

5. <span data-ttu-id="620eb-139">在下一页上，选择 "**所有人**"、"**特定用户/组**" 或 "**仅我**" 以指定要向其部署加载项的用户。</span><span class="sxs-lookup"><span data-stu-id="620eb-139">On the next page, select **Everyone**, **Specific users/groups** or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="620eb-140">使用搜索框查找要向其部署加载项的用户或组。</span><span class="sxs-lookup"><span data-stu-id="620eb-140">Use the Search box to find the users or groups who you want to deploy the add-in to.</span></span> <br/><span data-ttu-id="620eb-141">注意：了解适用于外接程序的其他状态。</span><span class="sxs-lookup"><span data-stu-id="620eb-141">NOTE: Learn about the other states that apply to an add-in.</span></span> <span data-ttu-id="620eb-142">请参阅本主题后面的[加载项状态](#add-in-states)。</span><span class="sxs-lookup"><span data-stu-id="620eb-142">See [Add-in states](#add-in-states) later in this topic.</span></span>
  
6. <span data-ttu-id="620eb-143">选择“部署”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="620eb-143">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="620eb-144">部署外接程序后，将显示绿色计时周期。</span><span class="sxs-lookup"><span data-stu-id="620eb-144">A green tick will appear when the add-in has been deployed.</span></span> <span data-ttu-id="620eb-145">您可以按照页面上的说明测试外接程序是否已成功部署。</span><span class="sxs-lookup"><span data-stu-id="620eb-145">You can follow the on-page instructions to test that the add-in has deployed successfully.</span></span>

> [!NOTE]
> <span data-ttu-id="620eb-146">用户可能需要重新启动 Office 以查看应用程序功能区上显示的外接程序图标。</span><span class="sxs-lookup"><span data-stu-id="620eb-146">Users may need to relaunch Office to see the add-in icon appear on the ribbon of app.</span></span> <span data-ttu-id="620eb-147">Outlook 外接程序最长可能需要24小时才能显示在用户的功能区上。</span><span class="sxs-lookup"><span data-stu-id="620eb-147">Outlook add-ins can take up to 24 hours to appear on users' ribbons.</span></span>
    
8. <span data-ttu-id="620eb-148">完成后，选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="620eb-148">When finished, select **Next**.</span></span> <span data-ttu-id="620eb-149">如果只部署到自己的，则可以选择 "**更改谁有权访问外接程序**"，以便将其部署到更多用户。</span><span class="sxs-lookup"><span data-stu-id="620eb-149">If you've deployed to just yourself, you can select **Change who has access to add-in** in order to deploy to more users.</span></span>



<span data-ttu-id="620eb-150">如果您已将外接程序部署到您的组织的成员之外，请按照显示的说明进行操作，以便有效地宣布加载项的部署。</span><span class="sxs-lookup"><span data-stu-id="620eb-150">If you've deployed the add-in to members of your organization other than yourself, follow the instructions displayed in order to effectively announce the deployment of the add-in.</span></span> <br/><span data-ttu-id="620eb-151">现在，你可以在 Microsoft 365 中看到你的外接程序和其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="620eb-151">You now see your add-in along with other apps in Microsoft 365.</span></span>
  
<span data-ttu-id="620eb-152">最好通知向其部署了加载项的用户和组，以便他们知道加载项可用。</span><span class="sxs-lookup"><span data-stu-id="620eb-152">It's a good idea to inform the users and groups who you deployed the add-in to so that they know that it's available.</span></span> <span data-ttu-id="620eb-153">可以向他们发送电子邮件，说明何时以及如何使用加载项，并说明加载项可以如何帮助他们更好地完成工作。</span><span class="sxs-lookup"><span data-stu-id="620eb-153">Consider sending an email to them that describes when and how to use the add-in and explains how the add-in can help them do their job better.</span></span> <span data-ttu-id="620eb-154">包含或链接到相关帮助内容或 Faq，如果用户在外接程序中遇到任何问题，则可能会有帮助。</span><span class="sxs-lookup"><span data-stu-id="620eb-154">Include or link to relevant Help content or FAQs that might help if users have any problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="620eb-155">为用户和组分配加载项时的注意事项</span><span class="sxs-lookup"><span data-stu-id="620eb-155">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="620eb-156">Admins can assign an add-in to everyone or to specific users and groups.</span><span class="sxs-lookup"><span data-stu-id="620eb-156">Admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="620eb-157">Each option has implications:</span><span class="sxs-lookup"><span data-stu-id="620eb-157">Each option has implications:</span></span>
  
- <span data-ttu-id="620eb-158">**Everyone**: As the name implies, this option assigns the add-in to every user in the tenant.</span><span class="sxs-lookup"><span data-stu-id="620eb-158">**Everyone**: As the name implies, this option assigns the add-in to every user in the tenant.</span></span> <span data-ttu-id="620eb-159">Use this option sparingly and only for add-ins that are truly universal to your organization.</span><span class="sxs-lookup"><span data-stu-id="620eb-159">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="620eb-160">**Users**: If you assign an add-in to an individual user, then to deploy the add-in to a new user, you will need to first add that user.</span><span class="sxs-lookup"><span data-stu-id="620eb-160">**Users**: If you assign an add-in to an individual user, then to deploy the add-in to a new user, you will need to first add that user.</span></span> <span data-ttu-id="620eb-161">The same goes for removing users.</span><span class="sxs-lookup"><span data-stu-id="620eb-161">The same goes for removing users.</span></span> 
    
- <span data-ttu-id="620eb-162">**Groups**: If you assign an add-in to a group, users who are added to the group will automatically be assigned the add-in.</span><span class="sxs-lookup"><span data-stu-id="620eb-162">**Groups**: If you assign an add-in to a group, users who are added to the group will automatically be assigned the add-in.</span></span> <span data-ttu-id="620eb-163">And, when a user is removed from a group, the user loses access to the add-in.</span><span class="sxs-lookup"><span data-stu-id="620eb-163">And, when a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="620eb-164">In either case, no additional action is required from you as the admin.</span><span class="sxs-lookup"><span data-stu-id="620eb-164">In either case, no additional action is required from you as the admin.</span></span> 

- <span data-ttu-id="620eb-165">**仅限我**：如果只向自己分配加载项，则会将外接程序仅分配给您的帐户。</span><span class="sxs-lookup"><span data-stu-id="620eb-165">**Just me**: If you assign an add-in to just yourself, this assigns the add-in to only your account.</span></span> <span data-ttu-id="620eb-166">如果您希望先测试加载项，这是理想之选。</span><span class="sxs-lookup"><span data-stu-id="620eb-166">This is ideal if you wish to test out the add-in first.</span></span>
    
<span data-ttu-id="620eb-167">适合您的组织的选项取决于您的配置。</span><span class="sxs-lookup"><span data-stu-id="620eb-167">The option that is right for your organization depends on your configuration.</span></span> <span data-ttu-id="620eb-168">但是，建议通过组进行分配。</span><span class="sxs-lookup"><span data-stu-id="620eb-168">However, we recommend making assignments via groups.</span></span> <span data-ttu-id="620eb-169">作为管理员，可能会发现通过组管理加载项以及控制组成员身份更为轻松，而不是每次都更改分配的用户。</span><span class="sxs-lookup"><span data-stu-id="620eb-169">As an admin, you might find it easier to manage add-ins using groups and control the membership of those groups rather than having to change the users assigned each time.</span></span> <span data-ttu-id="620eb-170">另一方面，在某些情况下，可能需要限制少数用户的访问权限，从而针对特定用户进行分配。</span><span class="sxs-lookup"><span data-stu-id="620eb-170">On the other hand, in some situations, you may want to restrict access to a very small set of users and therefore make assignments to specific users.</span></span> <span data-ttu-id="620eb-171">因此，需要手动管理分配的用户。</span><span class="sxs-lookup"><span data-stu-id="620eb-171">As a result, you will need to manage the assigned users manually.</span></span>
  
### <a name="add-in-states"></a><span data-ttu-id="620eb-172">加载项状态</span><span class="sxs-lookup"><span data-stu-id="620eb-172">Add-in states</span></span>

<span data-ttu-id="620eb-173">外接程序可以处于 "**打开**" 或 "**关闭**" 状态。</span><span class="sxs-lookup"><span data-stu-id="620eb-173">An add-in can either be in the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="620eb-174">**状态**</span><span class="sxs-lookup"><span data-stu-id="620eb-174">**State**</span></span>|<span data-ttu-id="620eb-175">**状态出现的原因**</span><span class="sxs-lookup"><span data-stu-id="620eb-175">**How the state occurs**</span></span>|<span data-ttu-id="620eb-176">**影响**</span><span class="sxs-lookup"><span data-stu-id="620eb-176">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="620eb-177">**Active**</span><span class="sxs-lookup"><span data-stu-id="620eb-177">**Active**</span></span>  <br/> |<span data-ttu-id="620eb-178">管理员上载了加载项，并将其分配给用户或组。</span><span class="sxs-lookup"><span data-stu-id="620eb-178">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="620eb-179">分配了加载项的用户和组可在相关客户端中看到它。</span><span class="sxs-lookup"><span data-stu-id="620eb-179">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="620eb-180">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="620eb-180">**Turned off**</span></span>  <br/> |<span data-ttu-id="620eb-181">管理员已禁用加载项。</span><span class="sxs-lookup"><span data-stu-id="620eb-181">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="620eb-182">分配了外接程序的用户和组无法再访问它。</span><span class="sxs-lookup"><span data-stu-id="620eb-182">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="620eb-183">如果外接程序的状态更改为"可用"，则用户和组将再次有权访问它。</span><span class="sxs-lookup"><span data-stu-id="620eb-183">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="620eb-184">**已删除**</span><span class="sxs-lookup"><span data-stu-id="620eb-184">**Deleted**</span></span>  <br/> |<span data-ttu-id="620eb-185">管理员已删除加载项。</span><span class="sxs-lookup"><span data-stu-id="620eb-185">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="620eb-186">分配了加载项的用户和组无法再访问它。</span><span class="sxs-lookup"><span data-stu-id="620eb-186">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="620eb-187">如果没有人再使用加载项，请考虑删除外接程序。</span><span class="sxs-lookup"><span data-stu-id="620eb-187">Consider deleting an add-in if no one is using it any more.</span></span> <span data-ttu-id="620eb-188">如果仅在一年的特定时间段使用加载项，那么可以选择关闭加载项。</span><span class="sxs-lookup"><span data-stu-id="620eb-188">Turning off an add-in may make sense if an add-in is used only during specific times of the year.</span></span>
  
### <a name="security-of-office-add-ins"></a><span data-ttu-id="620eb-189">Office 加载项的安全性</span><span class="sxs-lookup"><span data-stu-id="620eb-189">Security of Office add-ins</span></span>

<span data-ttu-id="620eb-190">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic.</span><span class="sxs-lookup"><span data-stu-id="620eb-190">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic.</span></span> <span data-ttu-id="620eb-191">Add-ins can range in their capabilities.</span><span class="sxs-lookup"><span data-stu-id="620eb-191">Add-ins can range in their capabilities.</span></span> <span data-ttu-id="620eb-192">For example, add-ins can:</span><span class="sxs-lookup"><span data-stu-id="620eb-192">For example, add-ins can:</span></span>
  
- <span data-ttu-id="620eb-193">显示数据。</span><span class="sxs-lookup"><span data-stu-id="620eb-193">Display data.</span></span>
    
- <span data-ttu-id="620eb-194">读取用户文档以提供上下文服务。</span><span class="sxs-lookup"><span data-stu-id="620eb-194">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="620eb-195">从用户文档读取数据并向用户文档写入数据，以便向该用户提供价值。</span><span class="sxs-lookup"><span data-stu-id="620eb-195">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="620eb-196">若要详细了解 Office 加载项的类型和功能，请参阅 [Office Add-ins platform overview](https://go.microsoft.com/fwlink/p/?linkid=846362)（Office 加载项平台概述），尤其是"Anatomy of an Office Add-in"（Office 加载项分析）一节。</span><span class="sxs-lookup"><span data-stu-id="620eb-196">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://go.microsoft.com/fwlink/p/?linkid=846362), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="620eb-197">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest.</span><span class="sxs-lookup"><span data-stu-id="620eb-197">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest.</span></span> <span data-ttu-id="620eb-198">A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level.</span><span class="sxs-lookup"><span data-stu-id="620eb-198">A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level.</span></span> <span data-ttu-id="620eb-199">For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).</span><span class="sxs-lookup"><span data-stu-id="620eb-199">For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).</span></span>
  
<span data-ttu-id="620eb-200">When updating a manifest, the typical changes are to an add-in's icon and text.</span><span class="sxs-lookup"><span data-stu-id="620eb-200">When updating a manifest, the typical changes are to an add-in's icon and text.</span></span> <span data-ttu-id="620eb-201">Occasionally, add-in commands change.</span><span class="sxs-lookup"><span data-stu-id="620eb-201">Occasionally, add-in commands change.</span></span> <span data-ttu-id="620eb-202">However, the permissions of the add-in do not change.</span><span class="sxs-lookup"><span data-stu-id="620eb-202">However, the permissions of the add-in do not change.</span></span> <span data-ttu-id="620eb-203">The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span><span class="sxs-lookup"><span data-stu-id="620eb-203">The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="620eb-204">加载项更新的情况如下：</span><span class="sxs-lookup"><span data-stu-id="620eb-204">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="620eb-205">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes.</span><span class="sxs-lookup"><span data-stu-id="620eb-205">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes.</span></span> <span data-ttu-id="620eb-206">The next time the relevant Office applications start, the add-in will update.</span><span class="sxs-lookup"><span data-stu-id="620eb-206">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="620eb-207">The web application can change at any time.</span><span class="sxs-lookup"><span data-stu-id="620eb-207">The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="620eb-208">管理员无需删除 LOB 加载项即可进行更新。</span><span class="sxs-lookup"><span data-stu-id="620eb-208">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="620eb-209">在 "外接程序" 部分中，管理员只需单击 LOB 外接程序，然后选择右下角的 "**更新" 按钮**即可。</span><span class="sxs-lookup"><span data-stu-id="620eb-209">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="620eb-210">仅当新外接程序的版本大于现有加载项的版本时，更新才有效。</span><span class="sxs-lookup"><span data-stu-id="620eb-210">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="620eb-211">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment.</span><span class="sxs-lookup"><span data-stu-id="620eb-211">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment.</span></span> <span data-ttu-id="620eb-212">The next time the relevant Office applications start, the add-in will update.</span><span class="sxs-lookup"><span data-stu-id="620eb-212">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="620eb-213">The web application can change at any time.</span><span class="sxs-lookup"><span data-stu-id="620eb-213">The web application can change at any time.</span></span> 

### <a name="edit-add-in-access"></a><span data-ttu-id="620eb-214">编辑外接访问</span><span class="sxs-lookup"><span data-stu-id="620eb-214">Edit Add-in access</span></span>

<span data-ttu-id="620eb-215">部署后，管理员还可以修改用户对加载项的访问权限。</span><span class="sxs-lookup"><span data-stu-id="620eb-215">Post deployment, admins can also modify the user access to add-ins.</span></span>

1. <span data-ttu-id="620eb-216">在 "管理中心" 中，转到 "**设置**  >  **服务" & "加载项**" 页面。</span><span class="sxs-lookup"><span data-stu-id="620eb-216">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="620eb-217">选择部署的加载项。</span><span class="sxs-lookup"><span data-stu-id="620eb-217">Select the deployed add-in.</span></span>

3. <span data-ttu-id="620eb-218">单击 "**有权访问**" 下的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="620eb-218">Click on **Edit** under **Who has Access**.</span></span>
4. <span data-ttu-id="620eb-219">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="620eb-219">Save the changes.</span></span>
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="620eb-220">通过在所有客户端（Outlook 除外）中关闭 Office 应用商店来阻止外接程序下载</span><span class="sxs-lookup"><span data-stu-id="620eb-220">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="620eb-221">Outlook 外接程序安装由[不同的进程](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)进行管理。</span><span class="sxs-lookup"><span data-stu-id="620eb-221">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="620eb-222">作为组织，您可能希望阻止从 Office 应用商店下载新的 Office 加载项。</span><span class="sxs-lookup"><span data-stu-id="620eb-222">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="620eb-223">这可与集中部署结合使用，以确保仅向组织中的用户部署组织批准的外接程序。</span><span class="sxs-lookup"><span data-stu-id="620eb-223">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="620eb-224">若要关闭加载项获取，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="620eb-224">To turn off add-in acquisition:</span></span>
  
1. <span data-ttu-id="620eb-225">在管理中心，转到“**设置**”\> [服务和加载项](https://go.microsoft.com/fwlink/p/?linkid=2053743)页面。</span><span class="sxs-lookup"><span data-stu-id="620eb-225">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>
    
3. <span data-ttu-id="620eb-226">选择 "**用户拥有的应用和服务**"。</span><span class="sxs-lookup"><span data-stu-id="620eb-226">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="620eb-227">清除 "允许用户访问 Office 应用商店" 选项。</span><span class="sxs-lookup"><span data-stu-id="620eb-227">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="620eb-228">这将阻止所有用户从存储中获取以下外接程序。</span><span class="sxs-lookup"><span data-stu-id="620eb-228">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="620eb-229">Word、Excel 和 PowerPoint 2016 的外接程序来自：</span><span class="sxs-lookup"><span data-stu-id="620eb-229">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="620eb-230">Windows</span><span class="sxs-lookup"><span data-stu-id="620eb-230">Windows</span></span>
    
  - <span data-ttu-id="620eb-231">Mac</span><span class="sxs-lookup"><span data-stu-id="620eb-231">Mac</span></span>
    
  - <span data-ttu-id="620eb-232">Office</span><span class="sxs-lookup"><span data-stu-id="620eb-232">Office</span></span>
    
    
- <span data-ttu-id="620eb-233">从**AppSource**中开始的收购</span><span class="sxs-lookup"><span data-stu-id="620eb-233">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="620eb-234">Microsoft 365 中的外接程序</span><span class="sxs-lookup"><span data-stu-id="620eb-234">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="620eb-235">尝试访问应用商店的用户将看到以下消息：**抱歉，Microsoft 365 已配置为阻止单独获取 Office 应用商店外接程序。**</span><span class="sxs-lookup"><span data-stu-id="620eb-235">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="620eb-236">以下版本提供了对 Office 应用商店关闭的支持：</span><span class="sxs-lookup"><span data-stu-id="620eb-236">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="620eb-237">Windows： 16.0.9001-当前可用。</span><span class="sxs-lookup"><span data-stu-id="620eb-237">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="620eb-238">Mac： 16.10.18011401-当前可用。</span><span class="sxs-lookup"><span data-stu-id="620eb-238">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="620eb-239">iOS： 2.9.18010804-当前可用。</span><span class="sxs-lookup"><span data-stu-id="620eb-239">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="620eb-240">Web 当前可用。</span><span class="sxs-lookup"><span data-stu-id="620eb-240">The web - Currently available.</span></span>
    
<span data-ttu-id="620eb-241">这不会阻止管理员使用集中部署从 Office 应用商店分配外接程序。</span><span class="sxs-lookup"><span data-stu-id="620eb-241">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="620eb-242">若要阻止用户使用 Microsoft 帐户登录，可以将登录限制为仅使用组织帐户。</span><span class="sxs-lookup"><span data-stu-id="620eb-242">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="620eb-243">有关详细信息，请参阅[此处](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="620eb-243">For more information, look [here](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="620eb-244">向应用商店中的未成年人和收购外接程序</span><span class="sxs-lookup"><span data-stu-id="620eb-244">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="620eb-245">一般数据保护条例（GDPR）是一种欧洲联合法规，生效时间可能为25，2018。</span><span class="sxs-lookup"><span data-stu-id="620eb-245">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="620eb-246">它向用户提供对其数据的权限并加以保护。</span><span class="sxs-lookup"><span data-stu-id="620eb-246">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="620eb-247">GDPR 的其中一个方面是，未成年人的个人数据不能发送给其家长或监护人尚未批准的当事人。</span><span class="sxs-lookup"><span data-stu-id="620eb-247">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="620eb-248">定义为次要的特定年龄取决于个人所在的区域。</span><span class="sxs-lookup"><span data-stu-id="620eb-248">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="620eb-249">具有关于家长同意的法令法规的地区包括美国、韩国、英国和欧盟。</span><span class="sxs-lookup"><span data-stu-id="620eb-249">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="620eb-250">对于这些区域，将阻止（通过 Azure Active Directory）从存储中获取任何新的 Office 外接程序，并运行之前获取的外接程序。</span><span class="sxs-lookup"><span data-stu-id="620eb-250">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="620eb-251">对于没有法令法规的国家/地区，将不提供下载限制。</span><span class="sxs-lookup"><span data-stu-id="620eb-251">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="620eb-252">根据 Azure Active Directory 中指定的数据，将用户确定为次要用户。</span><span class="sxs-lookup"><span data-stu-id="620eb-252">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="620eb-253">租户管理员负责声明法律年龄组和该用户的家长同意。</span><span class="sxs-lookup"><span data-stu-id="620eb-253">The tenant admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="620eb-254">如果父/监护人同意使用特定的外接程序，则租户管理员可以使用集中部署将该外接程序部署到所有已同意的未成年人。</span><span class="sxs-lookup"><span data-stu-id="620eb-254">If the parent/guardian consents to a minor using a specific add-In, then the tenant admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="620eb-255">若要符合 GDPR 的要求，您需要确保在学校/组织中部署以下 Office 内部版本之一。</span><span class="sxs-lookup"><span data-stu-id="620eb-255">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
  
 <span data-ttu-id="620eb-256">**对于 Word、Excel、PowerPoint 和 Project**：</span><span class="sxs-lookup"><span data-stu-id="620eb-256">**For Word, Excel, PowerPoint, and Project**:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="620eb-257">**平台**</span><span class="sxs-lookup"><span data-stu-id="620eb-257">**Platform**</span></span> <br/> |<span data-ttu-id="620eb-258">**内部版本号**</span><span class="sxs-lookup"><span data-stu-id="620eb-258">**Build number**</span></span> <br/> |
|<span data-ttu-id="620eb-259">适用于企业的 Microsoft 365 应用（当前频道）</span><span class="sxs-lookup"><span data-stu-id="620eb-259">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="620eb-260">9001.2138</span><span class="sxs-lookup"><span data-stu-id="620eb-260">9001.2138</span></span>   <br/> |
|<span data-ttu-id="620eb-261">适用于企业的 Microsoft 365 应用（半年企业频道）</span><span class="sxs-lookup"><span data-stu-id="620eb-261">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="620eb-262">8431.2159</span><span class="sxs-lookup"><span data-stu-id="620eb-262">8431.2159</span></span>  <br/> |
|<span data-ttu-id="620eb-263">Office 2016 for Windows</span><span class="sxs-lookup"><span data-stu-id="620eb-263">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="620eb-264">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="620eb-264">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="620eb-265">Office 2013 for Windows</span><span class="sxs-lookup"><span data-stu-id="620eb-265">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="620eb-266">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="620eb-266">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="620eb-267">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="620eb-267">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="620eb-268">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="620eb-268">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="620eb-269">Office 网页版</span><span class="sxs-lookup"><span data-stu-id="620eb-269">Office for the web</span></span>  <br/> |<span data-ttu-id="620eb-270">不适用</span><span class="sxs-lookup"><span data-stu-id="620eb-270">N/A</span></span>  <br/> |
   
 <span data-ttu-id="620eb-271">**对于 Outlook**：</span><span class="sxs-lookup"><span data-stu-id="620eb-271">**For Outlook**:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="620eb-272">**平台**</span><span class="sxs-lookup"><span data-stu-id="620eb-272">**Platform**</span></span> <br/> |<span data-ttu-id="620eb-273">**内部版本号**</span><span class="sxs-lookup"><span data-stu-id="620eb-273">**Build number**</span></span> <br/> |
|<span data-ttu-id="620eb-274">适用于 Windows 的 Outlook 2016 （MSI）</span><span class="sxs-lookup"><span data-stu-id="620eb-274">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="620eb-275">生成不 TBD</span><span class="sxs-lookup"><span data-stu-id="620eb-275">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="620eb-276">适用于 Windows 的 Outlook 2016 （C2R）</span><span class="sxs-lookup"><span data-stu-id="620eb-276">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="620eb-277">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="620eb-277">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="620eb-278">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="620eb-278">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="620eb-279">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="620eb-279">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="620eb-280">适用于 iOS 的 Outlook mobile</span><span class="sxs-lookup"><span data-stu-id="620eb-280">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="620eb-281">2.75.0</span><span class="sxs-lookup"><span data-stu-id="620eb-281">2.75.0</span></span>  <br/> |
|<span data-ttu-id="620eb-282">Outlook mobile for Android</span><span class="sxs-lookup"><span data-stu-id="620eb-282">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="620eb-283">2.2.145</span><span class="sxs-lookup"><span data-stu-id="620eb-283">2.2.145</span></span>  <br/> |
|<span data-ttu-id="620eb-284">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="620eb-284">Outlook.com</span></span>  <br/> |<span data-ttu-id="620eb-285">不适用</span><span class="sxs-lookup"><span data-stu-id="620eb-285">N/A</span></span>  <br/> |
   
 <span data-ttu-id="620eb-286">**Office 2013 要求**</span><span class="sxs-lookup"><span data-stu-id="620eb-286">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="620eb-287">Word、Excel 和 PowerPoint 2013 for Windows 将支持相同的次要检查（如果已启用 Active Directory 身份验证库（ADAL））。</span><span class="sxs-lookup"><span data-stu-id="620eb-287">Word, Excel, and PowerPoint 2013 for Windows will support the same minor checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="620eb-288">有两种合规性选项，如下所述。</span><span class="sxs-lookup"><span data-stu-id="620eb-288">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="620eb-289">**启用 ADAL**。</span><span class="sxs-lookup"><span data-stu-id="620eb-289">**Enable ADAL**.</span></span> <span data-ttu-id="620eb-290">本文介绍如何为 Office 2013 启用 ADAL：使用适用[于 office 客户端的 Microsoft 365 新式验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。</span><span class="sxs-lookup"><span data-stu-id="620eb-290">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="620eb-291">您还需要将注册表项设置为启用 ADAL，如在[Windows 设备上为 Office 2013 启用新式验证](../security-and-compliance/enable-modern-authentication.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="620eb-291">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="620eb-292">此外，还需要为 Office 2013 安装以下四月份更新：</span><span class="sxs-lookup"><span data-stu-id="620eb-292">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="620eb-293">Office 2013 安全更新说明：4月10日，2018</span><span class="sxs-lookup"><span data-stu-id="620eb-293">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="620eb-294">2018年4月3日，Office 2013 更新（KB4018333）</span><span class="sxs-lookup"><span data-stu-id="620eb-294">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="620eb-295">**不启用 ADAL**。</span><span class="sxs-lookup"><span data-stu-id="620eb-295">**Don't enable ADAL**.</span></span> <span data-ttu-id="620eb-296">如果无法在 Office 2013 中启用 ADAL，我们建议使用组策略关闭 office 客户端的存储。</span><span class="sxs-lookup"><span data-stu-id="620eb-296">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the office clients.</span></span> <span data-ttu-id="620eb-297">有关如何关闭 "Office 相关应用程序" 设置的信息位于[此处](https://technet.microsoft.com/library/cc178992.aspx)。</span><span class="sxs-lookup"><span data-stu-id="620eb-297">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>
    
## <a name="end-user-experience-with-add-ins"></a><span data-ttu-id="620eb-298">加载项最终用户体验</span><span class="sxs-lookup"><span data-stu-id="620eb-298">End user experience with add-ins</span></span>

<span data-ttu-id="620eb-299">Now that you've deployed the add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="620eb-299">Now that you've deployed the add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="620eb-300">The add-in will appear on all platforms that the add-in supports.</span><span class="sxs-lookup"><span data-stu-id="620eb-300">The add-in will appear on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="620eb-301">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span><span class="sxs-lookup"><span data-stu-id="620eb-301">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="620eb-302">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span><span class="sxs-lookup"><span data-stu-id="620eb-302">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![带有搜索引文的 Office 功能区](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="620eb-304">如果部署的外接程序不支持外接程序命令，或者如果您想要查看所有部署的加载项，可以通过**我的外接**程序查看它们。</span><span class="sxs-lookup"><span data-stu-id="620eb-304">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="620eb-305">在 Word 2016、Excel 2016 或 PowerPoint 2016 中</span><span class="sxs-lookup"><span data-stu-id="620eb-305">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="620eb-306">选择\*\* \> "插入我的外接程序"\*\*。</span><span class="sxs-lookup"><span data-stu-id="620eb-306">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="620eb-307">选择 Office 加载项窗口中的" **由管理员管理** "选项卡。</span><span class="sxs-lookup"><span data-stu-id="620eb-307">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="620eb-308">双击先前部署的加载项（在本例中是" **引文** "）。</span><span class="sxs-lookup"><span data-stu-id="620eb-308">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="620eb-309">!["Office 外接程序" 页的 "管理托管" 选项卡](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="620eb-309">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="620eb-310">在 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="620eb-310">In Outlook</span></span>

1. <span data-ttu-id="620eb-311">在 "**主页**" 功能区上，选择 "**获取外接程序**"。</span><span class="sxs-lookup"><span data-stu-id="620eb-311">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="620eb-312">![Outlook 中的'应用商店'按钮](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="620eb-312">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="620eb-313">在左侧导航中选择 "**管理员管理**"。</span><span class="sxs-lookup"><span data-stu-id="620eb-313">Select **Admin-managed** in the left nav.</span></span>

## <a name="delete-the-add-in"></a><span data-ttu-id="620eb-314">删除加载项</span><span class="sxs-lookup"><span data-stu-id="620eb-314">Delete the add-in</span></span>

<span data-ttu-id="620eb-315">您还可以删除已部署的外接程序。</span><span class="sxs-lookup"><span data-stu-id="620eb-315">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="620eb-316">在 "管理中心" 中，转到 "**设置**  >  **服务" & "加载项**" 页面。</span><span class="sxs-lookup"><span data-stu-id="620eb-316">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="620eb-317">选择部署的加载项。</span><span class="sxs-lookup"><span data-stu-id="620eb-317">Select the deployed add-in.</span></span>

3. <span data-ttu-id="620eb-318">单击 "**删除加载项**"。</span><span class="sxs-lookup"><span data-stu-id="620eb-318">Click on **Delete Add-In**.</span></span> <span data-ttu-id="620eb-319">移除右下角的外接端按钮。</span><span class="sxs-lookup"><span data-stu-id="620eb-319">Remove the Add-in button on the bottom right corner.</span></span>
4. <span data-ttu-id="620eb-320">验证您的选择，然后选择 "**删除外接程序**"。</span><span class="sxs-lookup"><span data-stu-id="620eb-320">Validate your selections, and choose **Remove add-in**.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="620eb-321">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="620eb-321">Learn more</span></span>

<span data-ttu-id="620eb-322">深入了解如何创建和构建 [Office 加载项](https://go.microsoft.com/fwlink/p/?linkid=846362)。</span><span class="sxs-lookup"><span data-stu-id="620eb-322">Learn more about creating and building [Office Add-ins](https://go.microsoft.com/fwlink/p/?linkid=846362).</span></span>
  
<span data-ttu-id="620eb-323">[使用集中部署 PowerShell cmdlet 管理外接程序](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="620eb-323">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="620eb-324">疑难解答：用户看不到外接程序</span><span class="sxs-lookup"><span data-stu-id="620eb-324">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
