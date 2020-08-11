---
title: '设置知识管理 (预览)  '
description: 如何设置知识管理。
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: ba8cb8ceb3c98019099bfe5438d274c9d2b32280
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612544"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="7bd84-103">设置知识管理 (预览) </span><span class="sxs-lookup"><span data-stu-id="7bd84-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="7bd84-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="7bd84-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="7bd84-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="7bd84-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="7bd84-106">您可以使用 Microsoft 365 管理中心来设置和配置[知识管理](knowledge-management-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7bd84-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="7bd84-107">在您的环境中规划设置和配置知识管理的最佳方式是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="7bd84-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="7bd84-108">例如，你将需要考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="7bd84-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="7bd84-109">要分析主题的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="7bd84-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="7bd84-110">您想让主题对哪些用户可见。</span><span class="sxs-lookup"><span data-stu-id="7bd84-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="7bd84-111">您要授予其权限以管理主题中心中的主题的用户。</span><span class="sxs-lookup"><span data-stu-id="7bd84-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="7bd84-112">要授予在主题中心创建或编辑主题的权限的用户。</span><span class="sxs-lookup"><span data-stu-id="7bd84-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="7bd84-113">要为你的主题中心提供的名称。</span><span class="sxs-lookup"><span data-stu-id="7bd84-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="7bd84-114">您可能会发现，创建安全组以向用户分配查看主题、管理主题以及创建和编辑主题所需的权限非常有用。</span><span class="sxs-lookup"><span data-stu-id="7bd84-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="7bd84-115">管理员还可以在安装程序完成 Microsoft 365 管理中心中的知识管理设置[后随时更改所选的设置](manage-knowledge-network.md)。</span><span class="sxs-lookup"><span data-stu-id="7bd84-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="7bd84-116">Requirements</span><span class="sxs-lookup"><span data-stu-id="7bd84-116">Requirements</span></span> 
<span data-ttu-id="7bd84-117">您必须具有全局管理员或 SharePoint 管理员权限才能访问 Microsoft 365 管理中心并设置组织知识任务。</span><span class="sxs-lookup"><span data-stu-id="7bd84-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="7bd84-118">设置你的知识网络</span><span class="sxs-lookup"><span data-stu-id="7bd84-118">Set up your knowledge network</span></span>

<span data-ttu-id="7bd84-119">设置您的知识网络可指导您完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="7bd84-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="7bd84-120">主题发现：选择要从发现中排除的主题源和主题。</span><span class="sxs-lookup"><span data-stu-id="7bd84-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="7bd84-121">主题可见性：选择在 "搜索" 和 "主题" 页中可查看主题为突出显示的内容。</span><span class="sxs-lookup"><span data-stu-id="7bd84-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="7bd84-122">主题权限：选择谁可以创建、编辑和管理主题。</span><span class="sxs-lookup"><span data-stu-id="7bd84-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="7bd84-123">主题中心：创建你的主题中心。</span><span class="sxs-lookup"><span data-stu-id="7bd84-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="7bd84-124">查看：检查并应用你的设置。</span><span class="sxs-lookup"><span data-stu-id="7bd84-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="7bd84-125">若要设置您的知识网络，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7bd84-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="7bd84-126">在 Microsoft 365 管理中心 (admin.microsoft.com) 中，选择 "**设置**"，然后查看 "**组织知识库**" 部分。</span><span class="sxs-lookup"><span data-stu-id="7bd84-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="7bd84-127">在 "**组织知识**" 部分，单击 "**将人员连接到知识**"。</span><span class="sxs-lookup"><span data-stu-id="7bd84-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![将用户连接到知识](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="7bd84-129">在 "**将用户连接到知识**" 页上，单击 "**入门**" 以引导您完成设置过程。</span><span class="sxs-lookup"><span data-stu-id="7bd84-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![入门](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="7bd84-131">在 "**选择知识网络如何查找主题**" 页上，您将配置主题发现。</span><span class="sxs-lookup"><span data-stu-id="7bd84-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="7bd84-132">在 "**选择 SharePoint 主题源**" 部分，选择要在发现过程中将哪些 SharePoint 网站作为主题的源进行爬网。</span><span class="sxs-lookup"><span data-stu-id="7bd84-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="7bd84-133">这包括：</span><span class="sxs-lookup"><span data-stu-id="7bd84-133">This includes:</span></span></br>
    <span data-ttu-id="7bd84-134">a.</span><span class="sxs-lookup"><span data-stu-id="7bd84-134">a.</span></span> <span data-ttu-id="7bd84-135">**所有网站**：租户中的所有 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="7bd84-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="7bd84-136">这将捕获当前和未来的网站。</span><span class="sxs-lookup"><span data-stu-id="7bd84-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="7bd84-137">b.</span><span class="sxs-lookup"><span data-stu-id="7bd84-137">b.</span></span> <span data-ttu-id="7bd84-138">**所有（选定网站除外）**：键入要排除的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="7bd84-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="7bd84-139">您还可以上载要从发现中退出的网站列表。</span><span class="sxs-lookup"><span data-stu-id="7bd84-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="7bd84-140">在将来创建的网站将作为主题发现的源包括在内。</span><span class="sxs-lookup"><span data-stu-id="7bd84-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="7bd84-141">c.</span><span class="sxs-lookup"><span data-stu-id="7bd84-141">c.</span></span> <span data-ttu-id="7bd84-142">**仅选定网站**：键入要包含的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="7bd84-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="7bd84-143">您还可以上载网站列表。</span><span class="sxs-lookup"><span data-stu-id="7bd84-143">You can also upload a list of sites.</span></span> <span data-ttu-id="7bd84-144">将来创建的网站不会作为主题发现的源包括在内。</span><span class="sxs-lookup"><span data-stu-id="7bd84-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![选择如何查找主题](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="7bd84-146">在 "**按名称排除主题**" 部分，您可以选择包括您不想在已发现的结果中的主题的名称。</span><span class="sxs-lookup"><span data-stu-id="7bd84-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="7bd84-147">使用此设置可防止将敏感主题作为知识网络的一部分包括在内。</span><span class="sxs-lookup"><span data-stu-id="7bd84-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="7bd84-148">您的选项包括：</span><span class="sxs-lookup"><span data-stu-id="7bd84-148">Your options include:</span></span></br>
    <span data-ttu-id="7bd84-149">a.</span><span class="sxs-lookup"><span data-stu-id="7bd84-149">a.</span></span> <span data-ttu-id="7bd84-150">**不排除任何主题**</span><span class="sxs-lookup"><span data-stu-id="7bd84-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="7bd84-151">b.</span><span class="sxs-lookup"><span data-stu-id="7bd84-151">b.</span></span> <span data-ttu-id="7bd84-152">**Exclude 包含以下术语的主题**：如果您有不想让用户显示为知识网络的一部分的主题。</span><span class="sxs-lookup"><span data-stu-id="7bd84-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="7bd84-153">-下载提供的模板。</span><span class="sxs-lookup"><span data-stu-id="7bd84-153">- Download the provided template.</span></span>
   <span data-ttu-id="7bd84-154">-输入要排除的主题名称。</span><span class="sxs-lookup"><span data-stu-id="7bd84-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="7bd84-155">您必须将匹配类型指定为确切或部分匹配。</span><span class="sxs-lookup"><span data-stu-id="7bd84-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="7bd84-156">完全匹配意味着将排除符合确切术语的主题。</span><span class="sxs-lookup"><span data-stu-id="7bd84-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="7bd84-157">部分匹配是更严格的，这意味着将排除包含术语的主题。</span><span class="sxs-lookup"><span data-stu-id="7bd84-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="7bd84-158">例如，如果输入*doc*作为主题名称，则在*Docker*不会排除*doc 程序集*。</span><span class="sxs-lookup"><span data-stu-id="7bd84-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="7bd84-159">主题名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="7bd84-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="7bd84-160">-选择  **+**   以导入已完成的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="7bd84-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="7bd84-161">然后选择 "**上传**"。</span><span class="sxs-lookup"><span data-stu-id="7bd84-161">Then select **Upload**.</span></span> <span data-ttu-id="7bd84-162">如果您的文件已成功处理，您将看到绿色的复选标记。</span><span class="sxs-lookup"><span data-stu-id="7bd84-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="7bd84-163">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7bd84-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="7bd84-164">在 "**哪些用户可以查看主题及其在哪里可以看到它们**" 页上，您将配置主题可见性。</span><span class="sxs-lookup"><span data-stu-id="7bd84-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="7bd84-165">在 "**了解网络中的主题**" 设置中，选择谁将有权访问主题详细信息，如突出显示的主题、主题卡片、搜索中的主题答案和主题页面。</span><span class="sxs-lookup"><span data-stu-id="7bd84-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="7bd84-166">可以选择：</span><span class="sxs-lookup"><span data-stu-id="7bd84-166">You can select:</span></span></br>
    <span data-ttu-id="7bd84-167">a.</span><span class="sxs-lookup"><span data-stu-id="7bd84-167">a.</span></span> <span data-ttu-id="7bd84-168">**组织中的所有人**</span><span class="sxs-lookup"><span data-stu-id="7bd84-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="7bd84-169">b.</span><span class="sxs-lookup"><span data-stu-id="7bd84-169">b.</span></span> <span data-ttu-id="7bd84-170">**仅选定的人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="7bd84-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="7bd84-171">c.</span><span class="sxs-lookup"><span data-stu-id="7bd84-171">c.</span></span> <span data-ttu-id="7bd84-172">**没人**</span><span class="sxs-lookup"><span data-stu-id="7bd84-172">**No one**</span></span></br>

    ![谁可以查看主题](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="7bd84-174">虽然此设置允许您选择组织中的任何用户，但只有分配有知识管理许可证的用户才能查看主题。</span><span class="sxs-lookup"><span data-stu-id="7bd84-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="7bd84-175">在 "**主题管理权限**" 页中，选择能够创建、编辑或管理主题的用户。</span><span class="sxs-lookup"><span data-stu-id="7bd84-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="7bd84-176">在 "**可以创建和编辑主题的用户**" 部分，您可以选择：</span><span class="sxs-lookup"><span data-stu-id="7bd84-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="7bd84-177">a.</span><span class="sxs-lookup"><span data-stu-id="7bd84-177">a.</span></span> <span data-ttu-id="7bd84-178">**组织中的所有人**</span><span class="sxs-lookup"><span data-stu-id="7bd84-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="7bd84-179">b.</span><span class="sxs-lookup"><span data-stu-id="7bd84-179">b.</span></span> <span data-ttu-id="7bd84-180">**仅选定的人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="7bd84-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="7bd84-181">在 "**谁可以管理主题**" 部分，您可以选择：</span><span class="sxs-lookup"><span data-stu-id="7bd84-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="7bd84-182">a.</span><span class="sxs-lookup"><span data-stu-id="7bd84-182">a.</span></span> <span data-ttu-id="7bd84-183">**组织中的所有人**</span><span class="sxs-lookup"><span data-stu-id="7bd84-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="7bd84-184">b.</span><span class="sxs-lookup"><span data-stu-id="7bd84-184">b.</span></span> <span data-ttu-id="7bd84-185">**选定的人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="7bd84-185">**Selected people or security groups**</span></span></br>

    ![主题管理的权限](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="7bd84-187">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7bd84-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="7bd84-188">在 "**创建主题中心**" 页上，您可以创建您的主题中心网站，在该网站中可以查看主题页面，并且可以管理主题。</span><span class="sxs-lookup"><span data-stu-id="7bd84-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="7bd84-189">在 "**主题中心名称**" 框中，键入您的主题中心的名称。</span><span class="sxs-lookup"><span data-stu-id="7bd84-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="7bd84-190">您可以选择在 "**网站说明**" 框中键入简短说明。</span><span class="sxs-lookup"><span data-stu-id="7bd84-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="7bd84-191">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7bd84-191">Select **Next**.</span></span></br>

   ![创建知识中心](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="7bd84-193">在 "**检查和完成**" 页上，您可以查看选定的设置并选择进行更改。</span><span class="sxs-lookup"><span data-stu-id="7bd84-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="7bd84-194">如果您对所做的选择感到满意，请选择 "**激活**"。</span><span class="sxs-lookup"><span data-stu-id="7bd84-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![完成并查看](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="7bd84-196">将显示 "**知识网络已激活**" 页，确认系统将立即开始分析您选择的网站，了解主题并创建知识中心网站。</span><span class="sxs-lookup"><span data-stu-id="7bd84-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="7bd84-197">选择“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7bd84-197">Select **Done**.</span></span></br>

    ![Activated](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="7bd84-199">你将返回到 "**将人员连接到知识**" 页面。</span><span class="sxs-lookup"><span data-stu-id="7bd84-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="7bd84-200">在此页面中，您可以选择 "**管理**" 以对配置设置进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="7bd84-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![应用的设置](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="7bd84-202">安装完成后，管理员可以通过返回此页面随时[更改所选的知识管理设置](manage-knowledge-network.md)。</span><span class="sxs-lookup"><span data-stu-id="7bd84-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="7bd84-203">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bd84-203">See also</span></span>



  






