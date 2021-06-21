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
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 摘要：在政治宣传活动开发/测试环境中创建公共、专用、敏感和高度机密的 SharePoint Online 团队网站。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fcba6e2f3939115d6dfbaae80d322246bdeadee9
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029893"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="34679-103">在政治宣传活动开发/测试环境中创建团队网站</span><span class="sxs-lookup"><span data-stu-id="34679-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="34679-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="34679-104">**Applies to**</span></span>

- [<span data-ttu-id="34679-105">适用于 Office 365 计划 2 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="34679-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="34679-106">**摘要：** 在政治宣传活动开发/测试环境中创建公共、专用、敏感和高度机密的 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="34679-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span>

<span data-ttu-id="34679-p101">使用本文中的说明，这对 [Microsoft 针对政治宣传活动、非营利组织和其他敏捷性组织的安全指南](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)解决方案，创建包含四个不同类型的 SharePoint Online 团队网站的开发/测试环境。在标题为 **SharePoint 和 OneDrive for Business** 的主题 10 详细介绍了这些网站。</span><span class="sxs-lookup"><span data-stu-id="34679-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="34679-109">第 1 阶段：创建政治宣传活动开发/测试环境</span><span class="sxs-lookup"><span data-stu-id="34679-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="34679-110">首先，按照[为政治宣传运动开发/测试环境配置组和用户](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)中的说明，创建订阅、用户和组。</span><span class="sxs-lookup"><span data-stu-id="34679-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="34679-111">第 2 阶段：创建标签</span><span class="sxs-lookup"><span data-stu-id="34679-111">Phase 2: Create labels</span></span>

<span data-ttu-id="34679-112">此阶段将针对 SharePoint Online 团队网站文档文件夹的不同安全级别创建标签。</span><span class="sxs-lookup"><span data-stu-id="34679-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="34679-113">如有需要，请使用试用订阅的全局管理员帐户凭据登录 Microsoft 365 管理中心（<https://admin.microsoft.com>）。</span><span class="sxs-lookup"><span data-stu-id="34679-113">If needed, sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="34679-114">如需帮助，请参阅 [在何处登录 Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="34679-114">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="34679-115">在开始操作的 **主页** 页面中，单击“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="34679-115">From the **Home** page where you start, click **Show all**.</span></span> <span data-ttu-id="34679-116">在显示的 **管理中心** 部分中，单击“**合规性**”。</span><span class="sxs-lookup"><span data-stu-id="34679-116">In the **Admin centers** section that appears, click **Compliance**.</span></span>

3. <span data-ttu-id="34679-117">在 Microsoft 365 合规中心的 **主页** 页面上，转到“**解决方案**”部分 \>“**信息保护**”。</span><span class="sxs-lookup"><span data-stu-id="34679-117">From the **Home** page of the Microsoft 365 compliance center, go to the **Solutions** section \> **Information protection**.</span></span> <span data-ttu-id="34679-118">要直接转到“**信息保护**”页面，请使用 <https://compliance.microsoft.com//informationprotection>。</span><span class="sxs-lookup"><span data-stu-id="34679-118">To go directly to the **Information protection** page, use <https://compliance.microsoft.com//informationprotection>.</span></span>

4. <span data-ttu-id="34679-119">在“**信息保护**”页上，验证是否已选择“**标签**”标记，然后单击“![创建标签图标](../../media/m365-cc-sc-create-icon.png)”“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="34679-119">On the **Information protection** page, verify that the **Label** tag is selected, and then click  ![Create a label icon](../../media/m365-cc-sc-create-icon.png) **Create a label**.</span></span>

5. <span data-ttu-id="34679-120">将打开 **新敏感度标签** 向导。</span><span class="sxs-lookup"><span data-stu-id="34679-120">The **New sensitivity label** wizard opens.</span></span> <span data-ttu-id="34679-121">在 **名称和说明** 步骤中，输入以下值：</span><span class="sxs-lookup"><span data-stu-id="34679-121">On the **Name & description** step, enter the following values:</span></span>
   - <span data-ttu-id="34679-122">**名称**：类型 **内部**。</span><span class="sxs-lookup"><span data-stu-id="34679-122">**Name**: Type **Internal**.</span></span>
   - <span data-ttu-id="34679-123">**显示名称**</span><span class="sxs-lookup"><span data-stu-id="34679-123">**Display name**</span></span>
   - <span data-ttu-id="34679-124">**面向用户的说明**</span><span class="sxs-lookup"><span data-stu-id="34679-124">**Description for users**</span></span>

   <span data-ttu-id="34679-125">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="34679-125">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="34679-126">在“标签设置”窗格中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-126">On the **Label settings** pane, click **Next**.</span></span>

7. <span data-ttu-id="34679-127">在“查看设置”窗格中，单击“创建此标签”，然后单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="34679-127">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

8. <span data-ttu-id="34679-128">对以下标签重复步骤 5-8：</span><span class="sxs-lookup"><span data-stu-id="34679-128">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="34679-129">Private</span><span class="sxs-lookup"><span data-stu-id="34679-129">Private</span></span>
   - <span data-ttu-id="34679-130">敏感</span><span class="sxs-lookup"><span data-stu-id="34679-130">Sensitive</span></span>
   - <span data-ttu-id="34679-131">高度机密</span><span class="sxs-lookup"><span data-stu-id="34679-131">Highly Confidential</span></span>

9. <span data-ttu-id="34679-132">在“开始”>“标签”窗格中，单击“发布标签”。</span><span class="sxs-lookup"><span data-stu-id="34679-132">From the **Home > Labels** pane, click **Publish labels**.</span></span>

10. <span data-ttu-id="34679-133">在“选择要发布的标签”窗格中，单击“选择要发布的标签”。</span><span class="sxs-lookup"><span data-stu-id="34679-133">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

11. <span data-ttu-id="34679-134">在“选择标签”窗格中，单击“添加”并选择全部四个标签。</span><span class="sxs-lookup"><span data-stu-id="34679-134">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

12. <span data-ttu-id="34679-135">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="34679-135">Click **Done**.</span></span>

13. <span data-ttu-id="34679-136">在“选择要发布的标签”窗格中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-136">On the **Choose labels to publish** pane, click **Next**.</span></span>

14. <span data-ttu-id="34679-137">在“选择位置”窗格中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-137">On the **Choose locations** pane, click **Next**.</span></span>

15. <span data-ttu-id="34679-138">在“命名策略”窗格中，在“名称”中键入 **Campaign**，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-138">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

16. <span data-ttu-id="34679-139">在“查看设置”窗格中，单击“发布标签”，然后单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="34679-139">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="34679-140">第 3 阶段：创建 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="34679-140">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="34679-141">在此阶段中，你可以为与四种类型的 SharePoint Online 团队网站相对应的政治宣传活动创建和配置 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="34679-141">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="34679-142">宣传活动范围团队网站</span><span class="sxs-lookup"><span data-stu-id="34679-142">Campaign wide team site</span></span>

<span data-ttu-id="34679-143">要创建基线公共 SharePoint Online 团队网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="34679-143">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="34679-144">如果需要，请使用本地计算机上的浏览器，并使用全局管理员帐户登录管理中心 (<https://admin.microsoft.com>)。</span><span class="sxs-lookup"><span data-stu-id="34679-144">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="34679-145">在磁贴列表中，单击“SharePoint”。</span><span class="sxs-lookup"><span data-stu-id="34679-145">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="34679-146">在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”。</span><span class="sxs-lookup"><span data-stu-id="34679-146">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="34679-147">在“创建网站”页中，单击“团队网站”。</span><span class="sxs-lookup"><span data-stu-id="34679-147">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="34679-148">在“网站名称”中，键入 **Campaign wide**。</span><span class="sxs-lookup"><span data-stu-id="34679-148">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="34679-149">在“团队网站描述”中，键入 **SharePoint site for the entire campaign**。</span><span class="sxs-lookup"><span data-stu-id="34679-149">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="34679-150">在“隐私设置”中，选择“公用 - 组织中的任何人均可访问此网站”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-150">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="34679-151">在“希望添加哪些人员?”窗格中，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="34679-151">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="34679-152">接下来，针对内部标签配置宣传活动范围团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="34679-152">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="34679-153">在浏览器的“宣传活动范围 - 主页”标签页中，单击“文档”。</span><span class="sxs-lookup"><span data-stu-id="34679-153">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="34679-154">单击设置图标，然后单击“库设置”。</span><span class="sxs-lookup"><span data-stu-id="34679-154">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="34679-155">在“权限和管理”下，单击“向此库中的项应用标签”。</span><span class="sxs-lookup"><span data-stu-id="34679-155">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="34679-156">在“设置-应用标签”中，选择“内部”，然后单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="34679-156">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="34679-157">宣传活动项目 1 团队网站</span><span class="sxs-lookup"><span data-stu-id="34679-157">Campaign project 1 team site</span></span>

<span data-ttu-id="34679-158">要为宣传活动内的项目创建基线专用 SharePoint Online 团队网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="34679-158">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="34679-159">如果需要，请使用本地计算机上的浏览器，并使用全局管理员帐户登录管理中心 (<https://admin.microsoft.com>)。</span><span class="sxs-lookup"><span data-stu-id="34679-159">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="34679-160">在磁贴列表中，单击“SharePoint”。</span><span class="sxs-lookup"><span data-stu-id="34679-160">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="34679-161">在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”。</span><span class="sxs-lookup"><span data-stu-id="34679-161">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="34679-162">在“创建网站”页中，单击“团队网站”。</span><span class="sxs-lookup"><span data-stu-id="34679-162">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="34679-163">在“网站名称”中，键入 **Campaign project 1**。</span><span class="sxs-lookup"><span data-stu-id="34679-163">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="34679-164">在“团队网站描述”中，键入 **SharePoint site for Campaign project 1**。</span><span class="sxs-lookup"><span data-stu-id="34679-164">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="34679-165">在“隐私设置”中，选择“专用 - 仅成员可以访问此网站”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-165">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="34679-166">在“希望添加哪些人员?”窗格中，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="34679-166">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="34679-167">接下来，针对专用标签配置宣传活动项目 1 团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="34679-167">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="34679-168">在浏览器的“宣传活动项目 1 - 主页”标签页中，单击“文档”。</span><span class="sxs-lookup"><span data-stu-id="34679-168">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="34679-169">单击设置图标，然后单击“库设置”。</span><span class="sxs-lookup"><span data-stu-id="34679-169">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="34679-170">在“权限和管理”下，单击“向此库中的项应用标签”。</span><span class="sxs-lookup"><span data-stu-id="34679-170">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="34679-171">在“设置-应用标签”中，选择“专用”，然后单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="34679-171">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="34679-172">宣传活动营销团队网站</span><span class="sxs-lookup"><span data-stu-id="34679-172">Campaign marketing team site</span></span>

<span data-ttu-id="34679-173">要为宣传活动营销资源创建敏感级别的独立 SharePoint Online 团队网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="34679-173">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="34679-174">请使用本地计算机上的浏览器，并使用全局管理员帐户登录管理中心 (<https://admin.microsoft.com>)。</span><span class="sxs-lookup"><span data-stu-id="34679-174">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="34679-175">在磁贴列表中，单击“SharePoint”。</span><span class="sxs-lookup"><span data-stu-id="34679-175">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="34679-176">在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”。</span><span class="sxs-lookup"><span data-stu-id="34679-176">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="34679-177">在“创建网站”页中，单击“团队网站”。</span><span class="sxs-lookup"><span data-stu-id="34679-177">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="34679-178">在“团队网站名称”中，键入 **Campaign marketing**。</span><span class="sxs-lookup"><span data-stu-id="34679-178">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="34679-179">在“团队网站描述”中，键入 **SharePoint site for campaign marketing (sensitive)**。</span><span class="sxs-lookup"><span data-stu-id="34679-179">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="34679-180">在“隐私设置”中，选择“专用 - 仅成员可以访问此网站”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-180">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="34679-181">在“希望添加哪些人员?”窗格中，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="34679-181">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="34679-182">在浏览器上的新“宣传活动营销”标签页上，依次单击工具栏中的设置图标和“网站权限”。。</span><span class="sxs-lookup"><span data-stu-id="34679-182">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="34679-183">在“网站权限”窗格中，单击“高级权限设置”。</span><span class="sxs-lookup"><span data-stu-id="34679-183">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="34679-184">在浏览器的新“权限”标签页中，单击“访问请求设置”。</span><span class="sxs-lookup"><span data-stu-id="34679-184">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="34679-185">在“**访问请求设置**”对话框中，清楚“**允许成员共享网站和单独的文件和文件夹**”和“**允许成员邀请他人到网站成员组**”复选框，请在“**发送所有访问请求**”中键入 **ITAdmin1@**\<your organization name\>**.onmicrosoft.com**，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="34679-185">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="34679-186">单击列表中的“宣传活动营销成员”。</span><span class="sxs-lookup"><span data-stu-id="34679-186">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="34679-187">在“人员和组”页中，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="34679-187">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="34679-188">在“共享”对话框中，键入并选择 **Senior and strategic staff**，然后单击“共享”。</span><span class="sxs-lookup"><span data-stu-id="34679-188">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="34679-189">为“分析人员”组和 Regular1 用户帐户重复步骤 14 和 15。</span><span class="sxs-lookup"><span data-stu-id="34679-189">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="34679-190">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="34679-190">Click the back button on your browser.</span></span>

18. <span data-ttu-id="34679-191">单击列表中的“宣传活动营销所有者”。</span><span class="sxs-lookup"><span data-stu-id="34679-191">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="34679-192">在“人员和组”页中，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="34679-192">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="34679-193">在“共享”对话框中，键入并选择“IT staff”，然后单击“共享”。</span><span class="sxs-lookup"><span data-stu-id="34679-193">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="34679-194">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="34679-194">Click the back button on your browser.</span></span>

22. <span data-ttu-id="34679-195">关闭浏览器上的“人员和组”标签页，单击浏览器上的“宣传活动营销-主页”标签页，然后关闭“网站权限”窗格。。</span><span class="sxs-lookup"><span data-stu-id="34679-195">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="34679-196">权限的配置结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="34679-196">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="34679-197">**宣传活动营销-成员** SharePoint 组仅包含“高级和策略人员”组（其中包含 Candidate、ChiefOfStaff 和 Strategic1 用户帐户）； **宣传活动营销** 组（其中包含全局管理员用户帐户）、**分析人员** 组（其中包含 DataScientist1 用户帐户）和 **Regular1** 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="34679-197">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="34679-198">**宣传活动营销-所有者** SharePoint 组仅包含“IT staff”组（其中仅包含 ITAdmin1 和 ITAdmin2 用户帐户）。</span><span class="sxs-lookup"><span data-stu-id="34679-198">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="34679-199">**宣传活动营销-访问者** SharePoint 组不包含任何组或用户帐户。</span><span class="sxs-lookup"><span data-stu-id="34679-199">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="34679-200">成员不能修改网站级权限（此设置只能由“宣传活动营销-所有者”组的成员执行）。</span><span class="sxs-lookup"><span data-stu-id="34679-200">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="34679-201">其他用户帐户无法访问网站或其资源，但可以请求访问网站，将向 ITAdmin1 用户帐户邮箱发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="34679-201">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="34679-202">接下来，针对敏感标签配置宣传活动营销团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="34679-202">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="34679-203">在浏览器的“宣传活动营销 - 主页”标签页中，单击“文档”。</span><span class="sxs-lookup"><span data-stu-id="34679-203">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="34679-204">单击设置图标，然后单击“库设置”。</span><span class="sxs-lookup"><span data-stu-id="34679-204">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="34679-205">在“权限和管理”下，单击“向此库中的项应用标签”。</span><span class="sxs-lookup"><span data-stu-id="34679-205">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="34679-206">在“设置-应用标签”中，选择“敏感”，然后单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="34679-206">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="34679-p106">接下来，配置数据丢失防护 (DLP) 策略，以便用户在组织外共享关于含敏感标签的 SharePoint Online 团队网站的文档时进行通知。此 DLP 策略将应用于宣传活动营销网站中的资源。</span><span class="sxs-lookup"><span data-stu-id="34679-p106">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="34679-209">在浏览器的“Microsoft Office 主页”标签页中，单击“安全性与符合性”磁贴。</span><span class="sxs-lookup"><span data-stu-id="34679-209">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="34679-210">在浏览器的新“安全性与符合性”标签页中，单击“数据丢失防护”>“策略”。</span><span class="sxs-lookup"><span data-stu-id="34679-210">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="34679-211">在“数据丢失防护”窗格中，单击“+ 创建策略”。</span><span class="sxs-lookup"><span data-stu-id="34679-211">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="34679-212">在“从模板开始或创建自定义策略”窗格中，单击“自定义”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-212">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="34679-213">在“命名策略”窗格中，在“名称”中键入 **Sensitive label SharePoint Online team sites**，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-213">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="34679-214">在“选择位置”窗格中，单击“允许选择特定位置”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-214">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="34679-215">在位置列表中，禁用“Exchange 电子邮件”和“OneDrive 帐户位置”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-215">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="34679-216">在“自定义要保护的敏感信息类型”窗格中，单击“编辑”。</span><span class="sxs-lookup"><span data-stu-id="34679-216">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="34679-217">在“选择要保护的内容类型”窗格中，单击下拉框中的“添加”，然后单击“标签”。</span><span class="sxs-lookup"><span data-stu-id="34679-217">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="34679-218">在“标签”窗格中，单击“+ 添加”，选择“敏感”标签，然后依次单击“添加”和“完成”。</span><span class="sxs-lookup"><span data-stu-id="34679-218">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="34679-219">在“选择要保护的内容类型”窗格中，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="34679-219">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="34679-220">在“自定义要保护的敏感信息类型”窗格中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-220">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="34679-221">在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”。</span><span class="sxs-lookup"><span data-stu-id="34679-221">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="34679-222">在“自定义策略提示和电子邮件通知”窗格中，单击“自定义策略提示文本”。</span><span class="sxs-lookup"><span data-stu-id="34679-222">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="34679-223">在文本框中，键入或粘贴以下内容：</span><span class="sxs-lookup"><span data-stu-id="34679-223">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="34679-p107">要与组织外部的用户共享，请下载并打开文件。 依次单击“文件”、“保护文档”、“使用密码加密”，然后指定强密码。 通过单独的电子邮件或其他通信方式发送密码。</span><span class="sxs-lookup"><span data-stu-id="34679-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="34679-227">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="34679-227">Click **OK**.</span></span>

17. <span data-ttu-id="34679-228">在“如果检测到敏感信息，希望采取什么操作?”窗格中，取消勾选“阻止共享并将访问限于共享内容”复选框，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-228">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="34679-229">在“是否希望立即启用策略或先进行测试?”窗格中，单击“是，立即启用”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-229">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="34679-230">在“查看设置”窗格中，单击“创建”，然后单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="34679-230">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="34679-231">宣传活动策略团队网站</span><span class="sxs-lookup"><span data-stu-id="34679-231">Campaign strategy team site</span></span>

<span data-ttu-id="34679-232">若要针对宣传活动策略资源创建高度机密级别的独立 SharePoint Online 团队网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="34679-232">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="34679-233">如果需要，请使用本地计算机上的浏览器，并使用全局管理员帐户登录管理中心 (<https://admin.microsoft.com>)。</span><span class="sxs-lookup"><span data-stu-id="34679-233">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="34679-234">在磁贴列表中，单击“SharePoint”。</span><span class="sxs-lookup"><span data-stu-id="34679-234">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="34679-235">在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”。</span><span class="sxs-lookup"><span data-stu-id="34679-235">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="34679-236">在“创建网站”页中，单击“团队网站”。</span><span class="sxs-lookup"><span data-stu-id="34679-236">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="34679-237">在“团队网站名称”中，键入 **Campaign strategy**。</span><span class="sxs-lookup"><span data-stu-id="34679-237">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="34679-238">在“团队网站描述”中，键入 **SharePoint site for campaign strategy (highly confidential)**。</span><span class="sxs-lookup"><span data-stu-id="34679-238">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="34679-239">在“隐私设置”中，选择“专用 - 仅成员可以访问此网站”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-239">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="34679-240">在“希望添加哪些人员?”窗格中，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="34679-240">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="34679-241">在浏览器的新“宣传活动策略”标签页中，依次单击工具栏的设置图标和“网站权限”。</span><span class="sxs-lookup"><span data-stu-id="34679-241">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="34679-242">在“网站权限”窗格中，单击“高级权限设置”。</span><span class="sxs-lookup"><span data-stu-id="34679-242">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="34679-243">在浏览器的新“权限”标签页中，单击“访问请求设置”。</span><span class="sxs-lookup"><span data-stu-id="34679-243">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="34679-244">在“访问请求设置”对话框中，清除“允许成员共享网站和单独的文件和文件夹”和“允许成员邀请他人到网站成员组”（这样三个复选框全被清除），然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="34679-244">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="34679-245">单击列表中的“宣传活动策略成员”。</span><span class="sxs-lookup"><span data-stu-id="34679-245">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="34679-246">在“人员和组”页中，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="34679-246">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="34679-247">在“共享”对话框中，键入并选择 **Senior and strategic staff**，然后单击“共享”。</span><span class="sxs-lookup"><span data-stu-id="34679-247">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="34679-248">单击列表中的“宣传活动策略所有者”。</span><span class="sxs-lookup"><span data-stu-id="34679-248">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="34679-249">在“人员和组”页中，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="34679-249">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="34679-250">在“共享”对话框中，键入并选择“IT staff”，然后单击“共享”。</span><span class="sxs-lookup"><span data-stu-id="34679-250">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="34679-251">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="34679-251">Click the back button on your browser.</span></span>

20. <span data-ttu-id="34679-252">关闭浏览器上的“人员和组”标签页，单击浏览器上的“宣传活动策略-主页”标签页，然后关闭“网站权限”窗格。</span><span class="sxs-lookup"><span data-stu-id="34679-252">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="34679-253">权限的配置结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="34679-253">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="34679-254">**宣传活动策略-成员** SharePoint 组仅包含“高级和策略人员”组（其中仅包含 Candidate、ChiefOfStaff 和 Strategic1 用户帐户）和 **宣传活动策略** 组（其中仅包含全局管理员用户帐户）。</span><span class="sxs-lookup"><span data-stu-id="34679-254">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="34679-255">**宣传活动策略-所有者** SharePoint 组仅包含“IT staff”组（其中仅包含 ITAdmin1 和 ITAdmin2 用户帐户）。</span><span class="sxs-lookup"><span data-stu-id="34679-255">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="34679-256">**宣传活动策略-访问者** SharePoint 组不包含任何组或用户帐户。</span><span class="sxs-lookup"><span data-stu-id="34679-256">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="34679-257">成员不能修改网站级别权限（仅“宣传活动策略-所有者”组的成员才可进行修改）。</span><span class="sxs-lookup"><span data-stu-id="34679-257">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="34679-p108">其他用户帐户无法访问网站或其资源，也无法请求访问网站。网站的其他权限必须由全局管理员或“活动策略-所有者”组的成员履行。</span><span class="sxs-lookup"><span data-stu-id="34679-p108">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="34679-260">接下来，针对高度机密标签配置宣传活动策略团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="34679-260">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="34679-261">在浏览器的“宣传活动策略-主页”标签页中，单击“文档”。</span><span class="sxs-lookup"><span data-stu-id="34679-261">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="34679-262">单击设置图标，然后单击“库设置”。</span><span class="sxs-lookup"><span data-stu-id="34679-262">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="34679-263">在“权限和管理”下，单击“向此库中的项应用标签”。</span><span class="sxs-lookup"><span data-stu-id="34679-263">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="34679-264">在“设置-应用标签”中，选择“高度机密”，然后单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="34679-264">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="34679-p109">接下来，配置 DLP 策略，以便阻止用户在组织外共享关于含高度机密标签的 SharePoint Online 团队网站的文档。此 DLP 策略将应用于宣传活动策略网站中的资源。</span><span class="sxs-lookup"><span data-stu-id="34679-p109">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="34679-267">如果需要，请使用本地计算机上的浏览器，以及使用具有安全管理员或公司管理员角色的帐户登录管理中心 (<https://admin.microsoft.com>)。</span><span class="sxs-lookup"><span data-stu-id="34679-267">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="34679-268">在浏览器的“Microsoft Office 主页”标签页中，单击“安全性与符合性”磁贴。</span><span class="sxs-lookup"><span data-stu-id="34679-268">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="34679-269">在浏览器的新“安全性与符合性”标签页中，单击“数据丢失防护”>“策略”。</span><span class="sxs-lookup"><span data-stu-id="34679-269">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="34679-270">在“数据丢失防护”窗格中，单击“+ 创建策略”。</span><span class="sxs-lookup"><span data-stu-id="34679-270">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="34679-271">在“从模板开始或创建自定义策略”窗格中，单击“自定义”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-271">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="34679-272">在“命名策略”窗格中，在“名称”中键入 **Highly Confidential label SharePoint Online team sites**，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-272">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="34679-273">在“选择位置”窗格中，单击“允许选择特定位置”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-273">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="34679-274">在位置列表中，禁用“Exchange 电子邮件”和“OneDrive 帐户位置”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-274">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="34679-275">在“自定义要保护的敏感信息类型”窗格中，单击“编辑”。</span><span class="sxs-lookup"><span data-stu-id="34679-275">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="34679-276">在“选择要保护的内容类型”窗格中，单击下拉框中的“添加”，然后单击“标签”。</span><span class="sxs-lookup"><span data-stu-id="34679-276">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="34679-277">在“标签”窗格中，单击“+ 添加”，选择“高度机密”标签，然后依次单击“添加”和“完成”。</span><span class="sxs-lookup"><span data-stu-id="34679-277">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="34679-278">在“选择要保护的内容类型”窗格中，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="34679-278">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="34679-279">在“自定义要保护的敏感信息类型”窗格中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-279">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="34679-280">在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”。</span><span class="sxs-lookup"><span data-stu-id="34679-280">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="34679-281">在“自定义策略提示和电子邮件通知”窗格中，单击“自定义策略提示文本”。</span><span class="sxs-lookup"><span data-stu-id="34679-281">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="34679-282">在文本框中，键入或粘贴以下内容：</span><span class="sxs-lookup"><span data-stu-id="34679-282">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="34679-p110">要与组织外部的用户共享，请下载并打开文件。 依次单击“文件”、“保护文档”、“使用密码加密”，然后指定强密码。 通过单独的电子邮件或其他通信方式发送密码。</span><span class="sxs-lookup"><span data-stu-id="34679-p110">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="34679-286">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="34679-286">Click **OK**.</span></span>

18. <span data-ttu-id="34679-287">在“如果检测到敏感信息，希望采取什么操作?”窗格中，选择“需要业务理由进行重写”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-287">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="34679-288">在“是否希望立即启用策略或先进行测试?”窗格中，单击“是，立即启用”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="34679-288">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="34679-289">在“**查看设置**”窗格中，单击“**创建**”，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="34679-289">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="34679-290">请按照[使用 Microsoft 365 管理中心激活 Azure RMS](/information-protection/deploy-use/activate-office365) 中的说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="34679-290">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="34679-291">接下来，通过执行以下步骤，使用新作用域内策略以及保护和权限的子标签来配置 Azure 信息保护：</span><span class="sxs-lookup"><span data-stu-id="34679-291">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="34679-292">使用具有安全管理员或公司管理员角色的帐户登录到管理中心。</span><span class="sxs-lookup"><span data-stu-id="34679-292">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="34679-293">如需帮助，请参阅[如何登录到 Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="34679-293">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="34679-294">在浏览器的单独选项卡中，转到 Azure 门户 (<https://portal.azure.com>)。</span><span class="sxs-lookup"><span data-stu-id="34679-294">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="34679-295">在搜索窗格中，键入“**信息**”，然后单击“**Azure 信息保护**”。</span><span class="sxs-lookup"><span data-stu-id="34679-295">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="34679-296">单击“**标签**”。</span><span class="sxs-lookup"><span data-stu-id="34679-296">Click **Labels**.</span></span>

5. <span data-ttu-id="34679-297">右键单击“高度机密”标签，然后单击“添加子标签”。</span><span class="sxs-lookup"><span data-stu-id="34679-297">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="34679-298">在“名称”中键入“CampaignStrategy”，并在“描述”中键入“Label for documents in the Campaign strategy team site”。</span><span class="sxs-lookup"><span data-stu-id="34679-298">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="34679-299">在“为包含此标签的文档和电子邮件设置权限”中，单击“保护”。</span><span class="sxs-lookup"><span data-stu-id="34679-299">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="34679-300">在“保护”部分中，单击“Azure (云密钥)”。</span><span class="sxs-lookup"><span data-stu-id="34679-300">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="34679-301">在“保护”边栏选项卡中，在“保护设置”下，单击“+ 添加权限”。</span><span class="sxs-lookup"><span data-stu-id="34679-301">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="34679-302">在“添加权限”边栏选项卡的“指定用户和组”下，单击“+ 浏览目录”。</span><span class="sxs-lookup"><span data-stu-id="34679-302">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="34679-303">在“AAD 用户和组”窗格中，选择“高级和策略人员”，然后单击“选择”。</span><span class="sxs-lookup"><span data-stu-id="34679-303">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="34679-304">在“从预设或设置自定义中选择权限”下，单击“自定义”，然后依次单击“查看权限”、“编辑内容”、“保存”、“答复”和“全部答复”复选框。</span><span class="sxs-lookup"><span data-stu-id="34679-304">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="34679-305">单击“**确定**”两次。</span><span class="sxs-lookup"><span data-stu-id="34679-305">Click **OK** twice.</span></span>

14. <span data-ttu-id="34679-306">在“**子标签**”边栏选项卡上，单击“**保存**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="34679-306">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="34679-307">在“Azure 信息保护”边栏选项卡上，单击“策略”>“+ 添加新策略”。</span><span class="sxs-lookup"><span data-stu-id="34679-307">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="34679-308">在“名称”中键入“CampaignStrategy”，并在“描述”中键入“Documents in the Campaign strategy team site”。</span><span class="sxs-lookup"><span data-stu-id="34679-308">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="34679-309">单击“选择获取此策略的用户或组”>“用户/组”，然后选择“高层和策略人员”。</span><span class="sxs-lookup"><span data-stu-id="34679-309">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="34679-310">单击“**选择”\>“确定**”。</span><span class="sxs-lookup"><span data-stu-id="34679-310">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="34679-p112">单击“添加或删除标签”。在“策略: 添加或删除标签”窗格中，单击“CampaignStrategy”，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="34679-p112">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="34679-313">单击“保存”，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="34679-313">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="34679-314">现在，可以在这四个网站中创建文档，并使用各种用户帐户进行访问测试。</span><span class="sxs-lookup"><span data-stu-id="34679-314">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="34679-315">若要使用 Azure 信息保护和新标签保护文档，必须在测试计算机上 [安装 Azure 信息保护客户端](/information-protection/rms-client/install-client-app)，从管理中心安装 Office，然后使用试用订阅的“**高级和策略人员**”组中的帐户从 Microsoft Word 登录。</span><span class="sxs-lookup"><span data-stu-id="34679-315">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="34679-316">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34679-316">See Also</span></span>

[<span data-ttu-id="34679-317">Microsoft 针对政治宣传活动、非营利组织和其他敏捷性组织的安全指南</span><span class="sxs-lookup"><span data-stu-id="34679-317">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="34679-318">为政治宣传活动开发/测试环境配置组和用户</span><span class="sxs-lookup"><span data-stu-id="34679-318">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="34679-319">云采用测试实验室指南 (TLG)</span><span class="sxs-lookup"><span data-stu-id="34679-319">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="34679-320">Microsoft 365 解决方案和体系结构中心</span><span class="sxs-lookup"><span data-stu-id="34679-320">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)