---
title: '设置知识管理 (预览)  '
description: 如何设置知识管理。
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: c7c30c0f8c1ec4cf8836547e2a23e1e2e6f4f783
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988919"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="fc0fb-103">设置知识管理 (预览) </span><span class="sxs-lookup"><span data-stu-id="fc0fb-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="fc0fb-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="fc0fb-105">[了解更多关于 Project Cortex的信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="fc0fb-106">您可以使用 Microsoft 365 管理中心来设置和配置 [知识管理](knowledge-management-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="fc0fb-107">在您的环境中规划设置和配置知识管理的最佳方式是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="fc0fb-108">例如，你将需要考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="fc0fb-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="fc0fb-109">要分析主题的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="fc0fb-110">您想让主题对哪些用户可见。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="fc0fb-111">您要授予其权限以管理主题中心中的主题的用户。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="fc0fb-112">要授予在主题中心创建或编辑主题的权限的用户。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="fc0fb-113">要为你的主题中心提供的名称。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="fc0fb-114">您可能会发现，创建安全组以向用户分配查看主题、管理主题以及创建和编辑主题所需的权限非常有用。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="fc0fb-115">管理员还可以在安装程序完成 Microsoft 365 管理中心中的知识管理设置 [后随时更改所选的设置](topic-experiences-discovery.md) 。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-115">An admin can also [make changes to your selected settings anytime after setup](topic-experiences-discovery.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="fc0fb-116">Requirements</span><span class="sxs-lookup"><span data-stu-id="fc0fb-116">Requirements</span></span> 
<span data-ttu-id="fc0fb-117">您必须具有全局管理员或 SharePoint 管理员权限才能访问 Microsoft 365 管理中心并设置组织知识任务。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="fc0fb-118">设置你的知识网络</span><span class="sxs-lookup"><span data-stu-id="fc0fb-118">Set up your knowledge network</span></span>

<span data-ttu-id="fc0fb-119">设置您的知识网络可指导您完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="fc0fb-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="fc0fb-120">主题发现：选择要从发现中排除的主题源和主题。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="fc0fb-121">主题可见性：选择在 "搜索" 和 "主题" 页中可查看主题为突出显示的内容。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="fc0fb-122">主题权限：选择谁可以创建、编辑和管理主题。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="fc0fb-123">主题中心：创建你的主题中心。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="fc0fb-124">查看：检查并应用你的设置。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="fc0fb-125">若要设置您的知识网络，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fc0fb-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="fc0fb-126">在 Microsoft 365 管理中心 (admin.microsoft.com) 中，选择 " **设置** "，然后查看 " **组织知识库** " 部分。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup** , and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="fc0fb-127">在 " **组织知识** " 部分，单击 " **将人员连接到知识** "。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![将用户连接到知识](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="fc0fb-129">在 " **将用户连接到知识** " 页上，单击 " **入门** " 以引导您完成设置过程。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![入门](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="fc0fb-131">在 " **选择知识网络如何查找主题** " 页上，您将配置主题发现。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="fc0fb-132">在 " **选择 SharePoint 主题源** " 部分，选择要在发现过程中将哪些 SharePoint 网站作为主题的源进行爬网。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="fc0fb-133">这包括：</span><span class="sxs-lookup"><span data-stu-id="fc0fb-133">This includes:</span></span></br>
    <span data-ttu-id="fc0fb-134">a.</span><span class="sxs-lookup"><span data-stu-id="fc0fb-134">a.</span></span> <span data-ttu-id="fc0fb-135">**所有网站** ：租户中的所有 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-135">**All sites** : All SharePoint sites in your tenant.</span></span> <span data-ttu-id="fc0fb-136">这将捕获当前和未来的网站。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="fc0fb-137">b.</span><span class="sxs-lookup"><span data-stu-id="fc0fb-137">b.</span></span> <span data-ttu-id="fc0fb-138">**所有（选定网站除外）** ：键入要排除的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-138">**All, except selected sites** : Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="fc0fb-139">您还可以上载要从发现中退出的网站列表。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="fc0fb-140">在将来创建的网站将作为主题发现的源包括在内。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="fc0fb-141">c.</span><span class="sxs-lookup"><span data-stu-id="fc0fb-141">c.</span></span> <span data-ttu-id="fc0fb-142">**仅选定网站** ：键入要包含的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-142">**Only selected sites** : Type the names of the sites you want to include.</span></span> <span data-ttu-id="fc0fb-143">您还可以上载网站列表。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-143">You can also upload a list of sites.</span></span> <span data-ttu-id="fc0fb-144">将来创建的网站不会作为主题发现的源包括在内。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![选择如何查找主题](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="fc0fb-146">在 " **按名称排除主题** " 部分，您可以选择包括您不想在已发现的结果中的主题的名称。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="fc0fb-147">使用此设置可防止将敏感主题作为知识网络的一部分包括在内。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="fc0fb-148">您的选项包括：</span><span class="sxs-lookup"><span data-stu-id="fc0fb-148">Your options include:</span></span></br>
    <span data-ttu-id="fc0fb-149">a.</span><span class="sxs-lookup"><span data-stu-id="fc0fb-149">a.</span></span> <span data-ttu-id="fc0fb-150">**不排除任何主题**</span><span class="sxs-lookup"><span data-stu-id="fc0fb-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="fc0fb-151">b.</span><span class="sxs-lookup"><span data-stu-id="fc0fb-151">b.</span></span> <span data-ttu-id="fc0fb-152">**按名称排除主题** ：如果您有不希望用户作为知识网络的一部分向用户显示的主题。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-152">**Exclude topics by name** :  If you have topics you don’t want shown to users as part of the knowledge network.</span></span></br>

    ![排除主题](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="fc0fb-154">如何按名称排除主题</span><span class="sxs-lookup"><span data-stu-id="fc0fb-154">How to exclude topics by name</span></span>    

    <span data-ttu-id="fc0fb-155">如果您需要排除主题，请在 **按名称选择排除主题** 后，选择 " **下载 .csv 模板"** 。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-155">If you need to exclude topics, after selecting **Exclude topics by name** , select **Download the .csv template**.</span></span> <span data-ttu-id="fc0fb-156">使用 Excel。CSV 模板，以包含要从发现结果中排除的主题的列表。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-156">Use the Excel .CSV template to include a list of topics that you want to exclude from your discovery results.</span></span>

    ![在 CSV 模板中排除主题](../media/content-understanding/csv1.png) </br>

    <span data-ttu-id="fc0fb-158">在 CSV 模板中，输入以下有关要排除的主题的信息：</span><span class="sxs-lookup"><span data-stu-id="fc0fb-158">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="fc0fb-159">**名称** ：键入要排除的主题的名称。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-159">**Name** : Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="fc0fb-160">可通过 2 种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="fc0fb-160">There are two ways to do this:</span></span></br>
        - <span data-ttu-id="fc0fb-161">完全匹配：可以包含确切的名称或首字母缩写词 (例如， *Contoso* 或 *ATL* ) 。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-161">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL* ).</span></span></br>
        - <span data-ttu-id="fc0fb-162">部分匹配：您可以排除包含特定字词的所有主题。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-162">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="fc0fb-163">例如， *arc* 将排除其中的单词 *弧* 的所有主题，如 *arc 圆* 、 *等离子弧形焊接* 或 *定型弧* 。请注意，它不会排除在其中包含作为单词的一部分的文本的主题，如 *体系结构* 。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-163">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle* , *Plasma arc welding* , or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span></br>
    - <span data-ttu-id="fc0fb-164">**扩展 (可选)** ：如果要排除首字母缩略词，请键入首字母缩略词代表的词语。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-164">**Expansion (optional)** : If you want to exclude an acronym, type the words the acronym stands for.</span></span></br>
    - <span data-ttu-id="fc0fb-165">**MatchType-exact/partial** ：键入您输入的名称是否是 *确切* 的或 *部分* 匹配的类型。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-165">**MatchType-Exact/Partial** : Type whether the name you entered was an *exact* or *partial* match type.</span></span></br>

    <span data-ttu-id="fc0fb-166">完成并保存 CSV 模板文件后，选择 " **浏览** " 以找到并选中它。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-166">After you've completed and saved your CSV template file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="fc0fb-167">选择 **下一步** 。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-167">Select **Next**.</span></span></br>

6. <span data-ttu-id="fc0fb-168">在 " **哪些用户可以查看主题及其在哪里可以看到它们** " 页上，您将配置主题可见性。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-168">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="fc0fb-169">在 " **了解网络中的主题** " 设置中，选择谁将有权访问主题详细信息，如突出显示的主题、主题卡片、搜索中的主题答案和主题页面。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-169">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="fc0fb-170">可以选择：</span><span class="sxs-lookup"><span data-stu-id="fc0fb-170">You can select:</span></span></br>
    <span data-ttu-id="fc0fb-171">a.</span><span class="sxs-lookup"><span data-stu-id="fc0fb-171">a.</span></span> <span data-ttu-id="fc0fb-172">**组织中的所有人**</span><span class="sxs-lookup"><span data-stu-id="fc0fb-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="fc0fb-173">b.</span><span class="sxs-lookup"><span data-stu-id="fc0fb-173">b.</span></span> <span data-ttu-id="fc0fb-174">**仅选定的人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="fc0fb-174">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="fc0fb-175">c.</span><span class="sxs-lookup"><span data-stu-id="fc0fb-175">c.</span></span> <span data-ttu-id="fc0fb-176">**没人**</span><span class="sxs-lookup"><span data-stu-id="fc0fb-176">**No one**</span></span></br>

    ![谁可以查看主题](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="fc0fb-178">虽然此设置允许您选择组织中的任何用户，但只有分配有知识管理许可证的用户才能查看主题。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-178">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="fc0fb-179">在 " **主题管理权限** " 页中，选择能够创建、编辑或管理主题的用户。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-179">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="fc0fb-180">在 " **可以创建和编辑主题的用户** " 部分，您可以选择：</span><span class="sxs-lookup"><span data-stu-id="fc0fb-180">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="fc0fb-181">a.</span><span class="sxs-lookup"><span data-stu-id="fc0fb-181">a.</span></span> <span data-ttu-id="fc0fb-182">**组织中的所有人**</span><span class="sxs-lookup"><span data-stu-id="fc0fb-182">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="fc0fb-183">b.</span><span class="sxs-lookup"><span data-stu-id="fc0fb-183">b.</span></span> <span data-ttu-id="fc0fb-184">**仅选定的人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="fc0fb-184">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="fc0fb-185">在 " **谁可以管理主题** " 部分，您可以选择：</span><span class="sxs-lookup"><span data-stu-id="fc0fb-185">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="fc0fb-186">a.</span><span class="sxs-lookup"><span data-stu-id="fc0fb-186">a.</span></span> <span data-ttu-id="fc0fb-187">**组织中的所有人**</span><span class="sxs-lookup"><span data-stu-id="fc0fb-187">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="fc0fb-188">b.</span><span class="sxs-lookup"><span data-stu-id="fc0fb-188">b.</span></span> <span data-ttu-id="fc0fb-189">**选定的人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="fc0fb-189">**Selected people or security groups**</span></span></br>

    ![主题管理的权限](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="fc0fb-191">选择 **下一步** 。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-191">Select **Next**.</span></span></br>
9. <span data-ttu-id="fc0fb-192">在 " **创建主题中心** " 页上，您可以创建您的主题中心网站，在该网站中可以查看主题页面，并且可以管理主题。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-192">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="fc0fb-193">在 " **主题中心名称** " 框中，键入您的主题中心的名称。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-193">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="fc0fb-194">您可以选择在 " **网站说明** " 框中键入简短说明。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-194">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="fc0fb-195">选择 **下一步** 。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-195">Select **Next**.</span></span></br>

   ![创建知识中心](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="fc0fb-197">在 **审查并完成** 页面上，可查看所选设置并选择进行更改。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-197">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="fc0fb-198">如果对你的选择感到满意，请选择 **激活** 。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-198">If you are satisfied with your selections, select **Activate**.</span></span>

    ![完成并查看](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="fc0fb-200">将显示 " **知识网络已激活** " 页，确认系统将立即开始分析您选择的网站，了解主题并创建知识中心网站。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-200">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="fc0fb-201">选择“ **完成** ”。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-201">Select **Done**.</span></span></br>

    ![Activated](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="fc0fb-203">你将返回到 " **将人员连接到知识** " 页面。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-203">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="fc0fb-204">在此页面中，可选择 **管理** ，对配置设置进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-204">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![应用的设置](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="fc0fb-206">安装完成后，管理员可以通过返回此页面随时 [更改所选的知识管理设置](topic-experiences-discovery.md) 。</span><span class="sxs-lookup"><span data-stu-id="fc0fb-206">After setup, an admin can [make changes to your selected knowledge management settings](topic-experiences-discovery.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="fc0fb-207">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc0fb-207">See also</span></span>



  






