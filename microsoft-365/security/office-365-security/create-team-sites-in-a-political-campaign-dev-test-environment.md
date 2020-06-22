---
title: 创建团队网站 - 政治宣传活动开发/测试环境
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 摘要：在政治宣传活动开发/测试环境中创建公共、专用、敏感和高度机密的 SharePoint Online 团队网站。
ms.openlocfilehash: d22ada823877d4c0996be942c379e12929242eaf
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755232"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="bdaec-103">在政治宣传活动开发/测试环境中创建团队网站</span><span class="sxs-lookup"><span data-stu-id="bdaec-103">Create team sites in a political campaign dev/test environment</span></span>

 <span data-ttu-id="bdaec-104">**摘要：** 在政治宣传活动开发/测试环境中创建公共、专用、敏感和高度机密的 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="bdaec-104">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
  
<span data-ttu-id="bdaec-105">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span><span class="sxs-lookup"><span data-stu-id="bdaec-105">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span> <span data-ttu-id="bdaec-106">These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="bdaec-106">These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>
  
## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="bdaec-107">第 1 阶段：创建政治宣传活动开发/测试环境</span><span class="sxs-lookup"><span data-stu-id="bdaec-107">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="bdaec-108">首先，按照[为政治宣传运动开发/测试环境配置组和用户](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)中的说明，创建订阅、用户和组。</span><span class="sxs-lookup"><span data-stu-id="bdaec-108">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>
  
## <a name="phase-2-create-labels"></a><span data-ttu-id="bdaec-109">第 2 阶段：创建标签</span><span class="sxs-lookup"><span data-stu-id="bdaec-109">Phase 2: Create labels</span></span>

<span data-ttu-id="bdaec-110">此阶段将针对 SharePoint Online 团队网站文档文件夹的不同安全级别创建标签。</span><span class="sxs-lookup"><span data-stu-id="bdaec-110">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>
  
1. <span data-ttu-id="bdaec-111">如有需要，请使用试用订阅的全局管理员帐户的凭据登录管理中心。</span><span class="sxs-lookup"><span data-stu-id="bdaec-111">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="bdaec-112">如需帮助，请参阅[在哪里登录 Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="bdaec-112">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="bdaec-113">在“Microsoft Office 主页”标签页中，单击“管理员”磁贴\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-113">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="bdaec-114">在浏览器的新“**Microsoft 365 管理中心**”标签页中，单击 **“管理中心”>“安全&amp;合规性”**。</span><span class="sxs-lookup"><span data-stu-id="bdaec-114">From the new **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="bdaec-115">在浏览器的新“主页 -安全&amp;合规性”\*\*\*\* 标签页中，单击“分类”>“标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-115">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="bdaec-116">在“主页”>“标签”窗格中，单击“创建标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-116">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="bdaec-117">在“命名标签”\*\*\*\* 窗格中，键入 **Internal**，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-117">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="bdaec-118">在“标签设置”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-118">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="bdaec-119">在“查看设置”\*\*\*\* 窗格中，单击“创建此标签”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-119">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="bdaec-120">对以下标签重复步骤 5-8：</span><span class="sxs-lookup"><span data-stu-id="bdaec-120">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="bdaec-121">Private</span><span class="sxs-lookup"><span data-stu-id="bdaec-121">Private</span></span>
    
  - <span data-ttu-id="bdaec-122">敏感</span><span class="sxs-lookup"><span data-stu-id="bdaec-122">Sensitive</span></span>
    
  - <span data-ttu-id="bdaec-123">高度机密</span><span class="sxs-lookup"><span data-stu-id="bdaec-123">Highly Confidential</span></span>
    
10. <span data-ttu-id="bdaec-124">在“开始”>“标签”窗格中，单击“发布标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-124">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="bdaec-125">在“选择要发布的标签”窗格中，单击“选择要发布的标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-125">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="bdaec-126">在“选择标签”窗格中，单击“添加”并选择全部四个标签\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-126">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="bdaec-127">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-127">Click **Done**.</span></span>
    
14. <span data-ttu-id="bdaec-128">在“选择要发布的标签”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-128">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="bdaec-129">在“选择位置”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-129">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="bdaec-130">在“命名策略”\*\*\*\* 窗格中，在“名称”中键入 \*\*Campaign\*\*\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-130">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="bdaec-131">在“查看设置”\*\*\*\* 窗格中，单击“发布标签”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-131">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="bdaec-132">第 3 阶段：创建 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="bdaec-132">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="bdaec-133">在此阶段中，你可以为与四种类型的 SharePoint Online 团队网站相对应的政治宣传活动创建和配置 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="bdaec-133">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>
  
### <a name="campaign-wide-team-site"></a><span data-ttu-id="bdaec-134">宣传活动范围团队网站</span><span class="sxs-lookup"><span data-stu-id="bdaec-134">Campaign wide team site</span></span>

<span data-ttu-id="bdaec-135">要创建基线公共 SharePoint Online 团队网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bdaec-135">To create a baseline public SharePoint Online team site, do the following:</span></span>
  
1. <span data-ttu-id="bdaec-136">如果需要，请使用本地计算机上的浏览器，并使用全局管理员帐户登录管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com))。</span><span class="sxs-lookup"><span data-stu-id="bdaec-136">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="bdaec-137">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-137">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="bdaec-138">在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-138">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="bdaec-139">在“创建网站”页中，单击“团队网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-139">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="bdaec-140">在“网站名称”\*\*\*\* 中，键入 **Campaign wide**。</span><span class="sxs-lookup"><span data-stu-id="bdaec-140">In **Site name**, type **Campaign wide**.</span></span> 
    
6. <span data-ttu-id="bdaec-141">在“团队网站描述”\*\*\*\* 中，键入 **SharePoint site for the entire campaign**。</span><span class="sxs-lookup"><span data-stu-id="bdaec-141">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>
    
7. <span data-ttu-id="bdaec-142">在“隐私设置”中，选择“公用 - 组织中的任何人均可访问此网站”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-142">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="bdaec-143">在“希望添加哪些人员?”窗格中，单击“完成”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-143">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="bdaec-144">接下来，针对内部标签配置宣传活动范围团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="bdaec-144">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>
  
1. <span data-ttu-id="bdaec-145">在浏览器的“宣传活动范围 - 主页”标签页中，单击“文档”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-145">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="bdaec-146">单击设置图标，然后单击“库设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-146">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="bdaec-147">在“权限和管理”下，单击“向此库中的项应用标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-147">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="bdaec-148">在“设置-应用标签”中，选择“内部”，然后单击“保存”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-148">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>
    
### <a name="campaign-project-1-team-site"></a><span data-ttu-id="bdaec-149">宣传活动项目 1 团队网站</span><span class="sxs-lookup"><span data-stu-id="bdaec-149">Campaign project 1 team site</span></span>

<span data-ttu-id="bdaec-150">要为宣传活动内的项目创建基线专用 SharePoint Online 团队网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bdaec-150">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>
  
1. <span data-ttu-id="bdaec-151">如果需要，请使用本地计算机上的浏览器，并使用全局管理员帐户登录管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com))。</span><span class="sxs-lookup"><span data-stu-id="bdaec-151">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="bdaec-152">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-152">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="bdaec-153">在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-153">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="bdaec-154">在“创建网站”页中，单击“团队网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-154">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="bdaec-155">在“网站名称”\*\*\*\* 中，键入 **Campaign project 1**。</span><span class="sxs-lookup"><span data-stu-id="bdaec-155">In **Site name**, type **Campaign project 1**.</span></span> 
    
6. <span data-ttu-id="bdaec-156">在“团队网站描述”\*\*\*\* 中，键入 **SharePoint site for Campaign project 1**。</span><span class="sxs-lookup"><span data-stu-id="bdaec-156">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>
    
7. <span data-ttu-id="bdaec-157">在“隐私设置”中，选择“专用 - 仅成员可以访问此网站”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-157">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="bdaec-158">在“希望添加哪些人员?”窗格中，单击“完成”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-158">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="bdaec-159">接下来，针对专用标签配置宣传活动项目 1 团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="bdaec-159">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>
  
1. <span data-ttu-id="bdaec-160">在浏览器的“宣传活动项目 1 - 主页”标签页中，单击“文档”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-160">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="bdaec-161">单击设置图标，然后单击“库设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-161">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="bdaec-162">在“权限和管理”下，单击“向此库中的项应用标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-162">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="bdaec-163">在“设置-应用标签”中，选择“专用”，然后单击“保存”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-163">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>
    
### <a name="campaign-marketing-team-site"></a><span data-ttu-id="bdaec-164">宣传活动营销团队网站</span><span class="sxs-lookup"><span data-stu-id="bdaec-164">Campaign marketing team site</span></span>

<span data-ttu-id="bdaec-165">要为宣传活动营销资源创建敏感级别的独立 SharePoint Online 团队网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bdaec-165">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>
  
1. <span data-ttu-id="bdaec-166">请使用本地计算机上的浏览器，并使用全局管理员帐户登录管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com))。</span><span class="sxs-lookup"><span data-stu-id="bdaec-166">Using a browser on your local computer, sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="bdaec-167">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-167">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="bdaec-168">在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-168">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="bdaec-169">在“创建网站”页中，单击“团队网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-169">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="bdaec-170">在“团队网站名称”\*\*\*\* 中，键入 **Campaign marketing**。</span><span class="sxs-lookup"><span data-stu-id="bdaec-170">In **Team site name**, type **Campaign marketing**.</span></span>
    
6. <span data-ttu-id="bdaec-171">在“团队网站描述”\*\*\*\* 中，键入 **SharePoint site for campaign marketing (sensitive)**。</span><span class="sxs-lookup"><span data-stu-id="bdaec-171">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>
    
7.  <span data-ttu-id="bdaec-172">在“隐私设置”中，选择“专用 - 仅成员可以访问此网站”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-172">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="bdaec-173">在“希望添加哪些人员?”窗格中，单击“完成”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-173">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="bdaec-174">在浏览器上的新“宣传活动营销”标签页上，依次单击工具栏中的设置图标和“网站权限”。\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-174">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="bdaec-175">在“网站权限”窗格中，单击“高级权限设置”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="bdaec-176">在浏览器的新“权限”标签页中，单击“访问请求设置”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-176">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="bdaec-177">在“访问请求设置”\*\*\*\* 对话框中，取消勾选“允许成员共享网站和单独的文件和文件夹”\*\*\*\* 和“允许成员邀请他人到网站成员组”\*\*\*\* 复选框，在“发送所有访问请求”中键入 **ITAdmin1@**<your organization name> \*\*.onmicrosoft.com\*\*\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-177">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**<your organization name> **.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>
    
13. <span data-ttu-id="bdaec-178">单击列表中的“宣传活动营销成员”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-178">Click **Campaign marketing Members** in the list.</span></span>
    
14. <span data-ttu-id="bdaec-179">在“人员和组”页中，单击“新建”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-179">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="bdaec-180">在“共享”\*\*\*\* 对话框中，键入并选择 **Senior and strategic staff**，然后单击“共享”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-180">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="bdaec-181">为“分析人员”\*\*\*\* 组和 Regular1\*\*\*\* 用户帐户重复步骤 14 和 15。</span><span class="sxs-lookup"><span data-stu-id="bdaec-181">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>
    
17. <span data-ttu-id="bdaec-182">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="bdaec-182">Click the back button on your browser.</span></span>
    
18. <span data-ttu-id="bdaec-183">单击列表中的“宣传活动营销所有者”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-183">Click **Campaign marketing Owners** in the list.</span></span>
    
19. <span data-ttu-id="bdaec-184">在“人员和组”页中，单击“新建”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-184">On the **People and Groups** page, click **New**.</span></span>
    
20. <span data-ttu-id="bdaec-185">在“共享”\*\*\*\* 对话框中，键入并选择“IT staff”\*\*\*\*，然后单击“共享”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-185">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
21. <span data-ttu-id="bdaec-186">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="bdaec-186">Click the back button on your browser.</span></span>
    
22. <span data-ttu-id="bdaec-187">关闭浏览器上的“人员和组”标签页，单击浏览器上的“宣传活动营销-主页”标签页，然后关闭“网站权限”窗格。\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-187">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="bdaec-188">权限的配置结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="bdaec-188">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="bdaec-189">**宣传活动营销-成员** SharePoint 组仅包含“高级和策略人员”\*\*\*\* 组（其中包含 Candidate、ChiefOfStaff 和 Strategic1 用户帐户）； **宣传活动营销**组（其中包含全局管理员用户帐户）、**分析人员**组（其中包含 DataScientist1 用户帐户）和 **Regular1** 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bdaec-189">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>
    
- <span data-ttu-id="bdaec-190">**宣传活动营销-所有者** SharePoint 组仅包含“IT staff”\*\*\*\* 组（其中仅包含 ITAdmin1 和 ITAdmin2 用户帐户）。</span><span class="sxs-lookup"><span data-stu-id="bdaec-190">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="bdaec-191">**宣传活动营销-访问者** SharePoint 组不包含任何组或用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bdaec-191">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="bdaec-192">成员不能修改网站级权限（此设置只能由“宣传活动营销-所有者”\*\*\*\* 组的成员执行）。</span><span class="sxs-lookup"><span data-stu-id="bdaec-192">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>
    
- <span data-ttu-id="bdaec-193">其他用户帐户无法访问网站或其资源，但可以请求访问网站，将向 ITAdmin1 用户帐户邮箱发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="bdaec-193">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>
    
<span data-ttu-id="bdaec-194">接下来，针对敏感标签配置宣传活动营销团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="bdaec-194">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="bdaec-195">在浏览器的“宣传活动营销 - 主页”标签页中，单击“文档”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-195">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="bdaec-196">单击设置图标，然后单击“库设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-196">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="bdaec-197">在“权限和管理”下，单击“向此库中的项应用标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-197">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="bdaec-198">在“设置-应用标签”中，选择“敏感”，然后单击“保存”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-198">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>
    
<span data-ttu-id="bdaec-199">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization.</span><span class="sxs-lookup"><span data-stu-id="bdaec-199">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization.</span></span> <span data-ttu-id="bdaec-200">This DLP policy will apply to resources in the Campaign marketing site.</span><span class="sxs-lookup"><span data-stu-id="bdaec-200">This DLP policy will apply to resources in the Campaign marketing site.</span></span>
  
1. <span data-ttu-id="bdaec-201">在浏览器的“Microsoft Office 主页”\*\*\*\* 标签页中，单击“安全&amp;合规性”\*\*\*\* 磁贴。</span><span class="sxs-lookup"><span data-stu-id="bdaec-201">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="bdaec-202">在浏览器的新“安全&amp;合规性”\*\*\*\* 标签页中，单击“数据丢失防护”>“策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-202">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="bdaec-203">在“数据丢失防护”窗格中，单击“+ 创建策略”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-203">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="bdaec-204">在“从模板开始或创建自定义策略”\*\*\*\* 窗格中，单击“自定义”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-204">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="bdaec-205">在“命名策略”\*\*\*\* 窗格中，在“名称”中键入 \*\*Sensitive label SharePoint Online team sites\*\*\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-205">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="bdaec-206">在“选择位置”窗格中，单击“允许选择特定位置”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-206">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="bdaec-207">在位置列表中，禁用“Exchange 电子邮件”\*\*\*\* 和“OneDrive 帐户位置”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-207">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="bdaec-208">在“自定义要保护的敏感信息类型”窗格中，单击“编辑”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-208">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="bdaec-209">在“选择要保护的内容类型”\*\*\*\* 窗格中，单击下拉框中的“添加”\*\*\*\*，然后单击“标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-209">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="bdaec-210">在“标签”\*\*\*\* 窗格中，单击“+ 添加”\*\*\*\*，选择“敏感”\*\*\*\* 标签，然后依次单击“添加”\*\*\*\* 和“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-210">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="bdaec-211">在“选择要保护的内容类型”窗格中，单击“保存”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-211">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="bdaec-212">在“自定义要保护的敏感信息类型”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-212">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="bdaec-213">在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-213">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="bdaec-214">在“自定义策略提示和电子邮件通知”窗格中，单击“自定义策略提示文本”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-214">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="bdaec-215">在文本框中，键入或粘贴以下内容：</span><span class="sxs-lookup"><span data-stu-id="bdaec-215">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="bdaec-216">To share with a user outside the organization, download the file and then open it.</span><span class="sxs-lookup"><span data-stu-id="bdaec-216">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="bdaec-217">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span><span class="sxs-lookup"><span data-stu-id="bdaec-217">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="bdaec-218">Send the password in a separate email or other means of communication.</span><span class="sxs-lookup"><span data-stu-id="bdaec-218">Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="bdaec-219">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-219">Click **OK**.</span></span>
    
17. <span data-ttu-id="bdaec-220">在“如果检测到敏感信息，希望采取什么操作?”\*\*\*\* 窗格中，取消勾选“阻止共享并将访问限于共享内容”\*\*\*\* 复选框，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-220">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>
    
18. <span data-ttu-id="bdaec-221">在“是否希望立即启用策略或先进行测试?”\*\*\*\* 窗格中，单击“是，立即启用”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-221">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="bdaec-222">在“查看设置”\*\*\*\* 窗格中，单击“创建”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-222">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
### <a name="campaign-strategy-team-site"></a><span data-ttu-id="bdaec-223">宣传活动策略团队网站</span><span class="sxs-lookup"><span data-stu-id="bdaec-223">Campaign strategy team site</span></span>

<span data-ttu-id="bdaec-224">若要针对宣传活动策略资源创建高度机密级别的独立 SharePoint Online 团队网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bdaec-224">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>
  
1. <span data-ttu-id="bdaec-225">如果需要，请使用本地计算机上的浏览器，并使用全局管理员帐户登录管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com))。</span><span class="sxs-lookup"><span data-stu-id="bdaec-225">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="bdaec-226">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-226">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="bdaec-227">在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-227">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="bdaec-228">在“创建网站”页中，单击“团队网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-228">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="bdaec-229">在“团队网站名称”\*\*\*\* 中，键入 **Campaign strategy**。</span><span class="sxs-lookup"><span data-stu-id="bdaec-229">In **Team site name**, type **Campaign strategy**.</span></span>
    
6. <span data-ttu-id="bdaec-230">在“团队网站描述”\*\*\*\* 中，键入 **SharePoint site for campaign strategy (highly confidential)**。</span><span class="sxs-lookup"><span data-stu-id="bdaec-230">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>
    
7.  <span data-ttu-id="bdaec-231">在“隐私设置”中，选择“专用 - 仅成员可以访问此网站”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-231">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="bdaec-232">在“希望添加哪些人员?”窗格中，单击“完成”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-232">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="bdaec-233">在浏览器的新“宣传活动策略”\*\*\*\* 标签页中，依次单击工具栏的设置图标和“网站权限”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-233">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="bdaec-234">在“网站权限”窗格中，单击“高级权限设置”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-234">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="bdaec-235">在浏览器的新“权限”标签页中，单击“访问请求设置”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-235">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="bdaec-236">在“访问请求设置”对话框中，清除“允许成员共享网站和单独的文件和文件夹”和“允许成员邀请他人到网站成员组”（这样三个复选框全被清除），然后单击“确定”\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-236">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
13. <span data-ttu-id="bdaec-237">单击列表中的“宣传活动策略成员”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-237">Click **Campaign strategy Members** in the list.</span></span>
    
14. <span data-ttu-id="bdaec-238">在“人员和组”页中，单击“新建”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-238">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="bdaec-239">在“共享”\*\*\*\* 对话框中，键入并选择 **Senior and strategic staff**，然后单击“共享”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-239">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="bdaec-240">单击列表中的“宣传活动策略所有者”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-240">Click **Campaign strategy Owners** in the list.</span></span>
    
17. <span data-ttu-id="bdaec-241">在“人员和组”页中，单击“新建”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-241">On the **People and Groups** page, click **New**.</span></span>
    
18. <span data-ttu-id="bdaec-242">在“共享”\*\*\*\* 对话框中，键入并选择“IT staff”\*\*\*\*，然后单击“共享”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-242">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
19. <span data-ttu-id="bdaec-243">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="bdaec-243">Click the back button on your browser.</span></span>
    
20. <span data-ttu-id="bdaec-244">关闭浏览器上的“人员和组”标签页，单击浏览器上的“宣传活动策略-主页”标签页，然后关闭“网站权限”窗格\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-244">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="bdaec-245">权限的配置结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="bdaec-245">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="bdaec-246">**宣传活动策略-成员** SharePoint 组仅包含“高级和策略人员”\*\*\*\* 组（其中仅包含 Candidate、ChiefOfStaff 和 Strategic1 用户帐户）和**宣传活动策略**组（其中仅包含全局管理员用户帐户）。</span><span class="sxs-lookup"><span data-stu-id="bdaec-246">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="bdaec-247">**宣传活动策略-所有者** SharePoint 组仅包含“IT staff”\*\*\*\* 组（其中仅包含 ITAdmin1 和 ITAdmin2 用户帐户）。</span><span class="sxs-lookup"><span data-stu-id="bdaec-247">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="bdaec-248">**宣传活动策略-访问者** SharePoint 组不包含任何组或用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bdaec-248">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="bdaec-249">成员不能修改网站级别权限（仅“宣传活动策略-所有者”\*\*\*\* 组的成员才可进行修改）。</span><span class="sxs-lookup"><span data-stu-id="bdaec-249">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>
    
- <span data-ttu-id="bdaec-250">Other user accounts cannot access the site or its resources or request access to the site.</span><span class="sxs-lookup"><span data-stu-id="bdaec-250">Other user accounts cannot access the site or its resources or request access to the site.</span></span> <span data-ttu-id="bdaec-251">Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span><span class="sxs-lookup"><span data-stu-id="bdaec-251">Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>
    
<span data-ttu-id="bdaec-252">接下来，针对高度机密标签配置宣传活动策略团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="bdaec-252">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>
  
1. <span data-ttu-id="bdaec-253">在浏览器的“宣传活动策略-主页”标签页中，单击“文档”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-253">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="bdaec-254">单击设置图标，然后单击“库设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-254">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="bdaec-255">在“权限和管理”下，单击“向此库中的项应用标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-255">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="bdaec-256">在“设置-应用标签”中，选择“高度机密”，然后单击“保存”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-256">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>
    
<span data-ttu-id="bdaec-257">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization.</span><span class="sxs-lookup"><span data-stu-id="bdaec-257">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization.</span></span> <span data-ttu-id="bdaec-258">This DLP policy will apply to resources in the Campaign strategy site.</span><span class="sxs-lookup"><span data-stu-id="bdaec-258">This DLP policy will apply to resources in the Campaign strategy site.</span></span>
  
1. <span data-ttu-id="bdaec-259">如果需要，请使用本地计算机上的浏览器，以及使用具有安全管理员或公司管理员角色的帐户登录管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com))。</span><span class="sxs-lookup"><span data-stu-id="bdaec-259">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="bdaec-260">在浏览器的“**Microsoft Office 主页**”标签页中，单击“**安全与合规**”磁贴。</span><span class="sxs-lookup"><span data-stu-id="bdaec-260">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
3. <span data-ttu-id="bdaec-261">在浏览器的新“安全&amp;合规性”\*\*\*\* 标签页中，单击“数据丢失防护”>“策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-261">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
4. <span data-ttu-id="bdaec-262">在“数据丢失防护”窗格中，单击“+ 创建策略”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-262">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
5. <span data-ttu-id="bdaec-263">在“从模板开始或创建自定义策略”\*\*\*\* 窗格中，单击“自定义”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-263">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="bdaec-264">在“命名策略”\*\*\*\* 窗格中，在“名称”中键入 \*\*Highly Confidential label SharePoint Online team sites\*\*\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-264">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="bdaec-265">在“选择位置”窗格中，单击“允许选择特定位置”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-265">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="bdaec-266">在位置列表中，禁用“Exchange 电子邮件”\*\*\*\* 和“OneDrive 帐户位置”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-266">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
9. <span data-ttu-id="bdaec-267">在“自定义要保护的敏感信息类型”窗格中，单击“编辑”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-267">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
10. <span data-ttu-id="bdaec-268">在“选择要保护的内容类型”\*\*\*\* 窗格中，单击下拉框中的“添加”\*\*\*\*，然后单击“标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-268">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
11. <span data-ttu-id="bdaec-269">在“标签”\*\*\*\* 窗格中，单击“+ 添加”\*\*\*\*，选择“高度机密”标签\*\*\*\*，然后依次单击“添加”\*\*\*\* 和“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-269">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
12. <span data-ttu-id="bdaec-270">在“选择要保护的内容类型”窗格中，单击“保存”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-270">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
13. <span data-ttu-id="bdaec-271">在“自定义要保护的敏感信息类型”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-271">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="bdaec-272">在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-272">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
15. <span data-ttu-id="bdaec-273">在“自定义策略提示和电子邮件通知”窗格中，单击“自定义策略提示文本”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-273">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
16. <span data-ttu-id="bdaec-274">在文本框中，键入或粘贴以下内容：</span><span class="sxs-lookup"><span data-stu-id="bdaec-274">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="bdaec-275">To share with a user outside the organization, download the file and then open it.</span><span class="sxs-lookup"><span data-stu-id="bdaec-275">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="bdaec-276">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span><span class="sxs-lookup"><span data-stu-id="bdaec-276">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="bdaec-277">Send the password in a separate email or other means of communication.</span><span class="sxs-lookup"><span data-stu-id="bdaec-277">Send the password in a separate email or other means of communication.</span></span>
    
17. <span data-ttu-id="bdaec-278">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-278">Click **OK**.</span></span>
    
18. <span data-ttu-id="bdaec-279">在“如果检测到敏感信息，希望采取什么操作?”\*\*\*\* 窗格中，选择“需要业务理由进行重写”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-279">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="bdaec-280">在“是否希望立即启用策略或先进行测试?”\*\*\*\* 窗格中，单击“是，立即启用”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-280">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
20. <span data-ttu-id="bdaec-281">在“**查看设置**”窗格中，单击“**创建**”，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="bdaec-281">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="bdaec-282">请按照[使用 Microsoft 365 管理中心激活 Azure RMS](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) 中的说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="bdaec-282">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>
  
<span data-ttu-id="bdaec-283">接下来，通过执行以下步骤，使用新作用域内策略以及保护和权限的子标签来配置 Azure 信息保护：</span><span class="sxs-lookup"><span data-stu-id="bdaec-283">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>
  
1. <span data-ttu-id="bdaec-284">使用具有安全管理员或公司管理员角色的帐户登录到管理中心。</span><span class="sxs-lookup"><span data-stu-id="bdaec-284">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="bdaec-285">如需帮助，请参阅[如何登录到 Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="bdaec-285">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="bdaec-286">在浏览器的单独标签页中，转到 Azure 门户 ([https://portal.azure.com](https://portal.azure.com))。</span><span class="sxs-lookup"><span data-stu-id="bdaec-286">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
4. <span data-ttu-id="bdaec-287">在搜索窗格中，键入“**信息**”，然后单击“**Azure 信息保护**”。</span><span class="sxs-lookup"><span data-stu-id="bdaec-287">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="bdaec-288">单击“**标签**”。</span><span class="sxs-lookup"><span data-stu-id="bdaec-288">Click **Labels**.</span></span>
    
6. <span data-ttu-id="bdaec-289">右键单击“高度机密”\*\*\*\* 标签，然后单击“添加子标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-289">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="bdaec-290">在“名称”\*\*\*\* 中键入“CampaignStrategy”\*\*\*\*，并在“描述”\*\*\*\* 中键入“Label for documents in the Campaign strategy team site”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-290">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>
    
8. <span data-ttu-id="bdaec-291">在“为包含此标签的文档和电子邮件设置权限”\*\*\*\* 中，单击“保护”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-291">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="bdaec-292">在“保护”部分中，单击“Azure (云密钥)”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-292">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="bdaec-293">在“保护”边栏选项卡中，在“保护设置”下，单击“+ 添加权限”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-293">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>
    
11. <span data-ttu-id="bdaec-294">在“添加权限”\*\*\*\* 边栏选项卡的“指定用户和组”\*\*\*\* 下，单击“+ 浏览目录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-294">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>
    
12. <span data-ttu-id="bdaec-295">在“AAD 用户和组”\*\*\*\* 窗格中，选择“高级和策略人员”\*\*\*\*，然后单击“选择”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-295">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>
    
13. <span data-ttu-id="bdaec-296">在“从预设或设置自定义中选择权限”\*\*\*\* 下，单击“自定义”\*\*\*\*，然后依次单击“查看权限”\*\*\*\*、“编辑内容”\*\*\*\*、“保存”\*\*\*\*、“答复”\*\*\*\* 和“全部答复”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="bdaec-296">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="bdaec-297">单击“**确定**”两次。</span><span class="sxs-lookup"><span data-stu-id="bdaec-297">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="bdaec-298">在“**子标签**”边栏选项卡上，单击“**保存**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="bdaec-298">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="bdaec-299">在“Azure 信息保护”\*\*\*\* 边栏选项卡上，单击“策略”>“+ 添加新策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-299">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="bdaec-300">在“名称”\*\*\*\* 中键入“CampaignStrategy”\*\*\*\*，并在“描述”\*\*\*\* 中键入“Documents in the Campaign strategy team site”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-300">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>
    
18. <span data-ttu-id="bdaec-301">单击“选择获取此策略的用户或组”\*\*\*\*>“用户/组”，然后选择“高层和策略人员”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-301">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>
    
19. <span data-ttu-id="bdaec-302">单击“选择”>“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-302">Click **Select > OK**.</span></span>

20. <span data-ttu-id="bdaec-303">Click **Add or remove labels**.</span><span class="sxs-lookup"><span data-stu-id="bdaec-303">Click **Add or remove labels**.</span></span> <span data-ttu-id="bdaec-304">In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdaec-304">In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>   

21. <span data-ttu-id="bdaec-305">单击“保存”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bdaec-305">Click **Save**, and then click **OK**.</span></span>
  
<span data-ttu-id="bdaec-306">现在，可以在这四个网站中创建文档，并使用各种用户帐户进行访问测试。</span><span class="sxs-lookup"><span data-stu-id="bdaec-306">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span> 
  
<span data-ttu-id="bdaec-307">若要使用 Azure 信息保护和新标签保护文档，必须在测试计算机上[安装 Azure 信息保护客户端](https://docs.microsoft.com/information-protection/rms-client/install-client-app)，从管理中心安装 Office，然后使用试用订阅的“**高级和策略人员**”组中的帐户从 Microsoft Word 登录。</span><span class="sxs-lookup"><span data-stu-id="bdaec-307">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bdaec-308">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdaec-308">See Also</span></span>

[<span data-ttu-id="bdaec-309">Microsoft 针对政治宣传活动、非营利组织和其他敏捷性组织的安全指南</span><span class="sxs-lookup"><span data-stu-id="bdaec-309">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="bdaec-310">为政治宣传活动开发/测试环境配置组和用户</span><span class="sxs-lookup"><span data-stu-id="bdaec-310">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)
  
[<span data-ttu-id="bdaec-311">云采用测试实验室指南 (TLG)</span><span class="sxs-lookup"><span data-stu-id="bdaec-311">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="bdaec-312">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="bdaec-312">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




