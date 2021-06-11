---
title: 设置 Microsoft Viva 主题
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: 了解如何设置 Microsoft Viva 主题
ms.openlocfilehash: c6997e5f5a6793468dfe3392ffc2037b319844ad
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893760"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="978d7-103">设置 Microsoft Viva 主题</span><span class="sxs-lookup"><span data-stu-id="978d7-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="978d7-104">可以使用管理Microsoft 365设置和配置[主题](topic-experiences-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="978d7-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="978d7-105">规划在环境中设置和配置主题的最佳方法非常重要。</span><span class="sxs-lookup"><span data-stu-id="978d7-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="978d7-106">在开始本文中的过程之前，请务必阅读 Plan [for Microsoft Viva](plan-topic-experiences.md) Topics。</span><span class="sxs-lookup"><span data-stu-id="978d7-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="978d7-107">您必须订阅[Viva 主题](https://www.microsoft.com/microsoft-viva/topics)，并且必须是全局管理员或 SharePoint管理员才能访问 Microsoft 365中心并设置主题。</span><span class="sxs-lookup"><span data-stu-id="978d7-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="978d7-108">如果你已配置SharePoint托管[设备](/sharepoint/control-access-from-unmanaged-devices)，请确保从托管设备设置主题。</span><span class="sxs-lookup"><span data-stu-id="978d7-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="978d7-109">视频演示</span><span class="sxs-lookup"><span data-stu-id="978d7-109">Video demonstration</span></span>

<span data-ttu-id="978d7-110">此视频演示在 Microsoft 365 中设置主题的过程。</span><span class="sxs-lookup"><span data-stu-id="978d7-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="assign-licenses"></a><span data-ttu-id="978d7-111">分配许可证</span><span class="sxs-lookup"><span data-stu-id="978d7-111">Assign licenses</span></span>

<span data-ttu-id="978d7-112">必须为使用主题的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="978d7-112">You must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="978d7-113">只有具有许可证的用户才能查看有关主题的信息，包括突出显示、主题卡片、主题页面和主题中心。</span><span class="sxs-lookup"><span data-stu-id="978d7-113">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="978d7-114">以分配许可证：</span><span class="sxs-lookup"><span data-stu-id="978d7-114">To assign licenses:</span></span>

1. <span data-ttu-id="978d7-115">在Microsoft 365 管理中心中，在 **用户** 下，点击 **活动用户**。</span><span class="sxs-lookup"><span data-stu-id="978d7-115">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="978d7-116">选择要许可的用户，然后单击"许可证 **和应用"。**</span><span class="sxs-lookup"><span data-stu-id="978d7-116">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="978d7-117">在 **"许可证"** 下，**选择"Viva 主题"。**</span><span class="sxs-lookup"><span data-stu-id="978d7-117">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="978d7-118">在 **"应用"** 下 **，Graph"索引连接器搜索 ("Viva** 主题) "和 **"Viva** 主题"。</span><span class="sxs-lookup"><span data-stu-id="978d7-118">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="978d7-119">![Microsoft Viva 管理中心Microsoft 365主题许可证](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="978d7-119">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="978d7-120">单击 **保存更改**。</span><span class="sxs-lookup"><span data-stu-id="978d7-120">Click **Save changes**.</span></span>

<span data-ttu-id="978d7-121">分配许可证后，用户可能需要一小时才能访问主题。</span><span class="sxs-lookup"><span data-stu-id="978d7-121">It may take up to an hour for users to get access to Topics after the licenses are assigned.</span></span>

## <a name="set-up-topics"></a><span data-ttu-id="978d7-122">设置主题</span><span class="sxs-lookup"><span data-stu-id="978d7-122">Set up Topics</span></span>

> [!Note]
> <span data-ttu-id="978d7-123">首次启用主题发现时，可能需要两周才能在"管理主题"视图中显示所有建议的主题。</span><span class="sxs-lookup"><span data-stu-id="978d7-123">The first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="978d7-124">主题发现将在新内容或内容更新时继续。</span><span class="sxs-lookup"><span data-stu-id="978d7-124">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="978d7-125">在 Viva 主题评估新信息时，组织中的建议主题数量通常有波动。</span><span class="sxs-lookup"><span data-stu-id="978d7-125">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

<span data-ttu-id="978d7-126">设置主题</span><span class="sxs-lookup"><span data-stu-id="978d7-126">To set up Topics</span></span>
1. <span data-ttu-id="978d7-127">在管理 [Microsoft 365，](https://admin.microsoft.com)选择"**设置**"，然后查看"**文件和内容"** 部分。</span><span class="sxs-lookup"><span data-stu-id="978d7-127">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="978d7-128">在"**文件和内容"** 部分，单击连接 **人员了解知识"。**</span><span class="sxs-lookup"><span data-stu-id="978d7-128">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![连接人员了解知识](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="978d7-130">在 **"连接人员到知识"页上**，单击"开始"以完成设置过程。</span><span class="sxs-lookup"><span data-stu-id="978d7-130">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![入门](../media/k-get-started.png) 

4. <span data-ttu-id="978d7-132">在" **选择 Viva 主题如何查找** 主题"页上，您将配置主题发现。</span><span class="sxs-lookup"><span data-stu-id="978d7-132">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="978d7-133">在"**选择SharePoint** 源"部分，选择将在发现SharePoint哪些网站作为主题的源进行爬网。</span><span class="sxs-lookup"><span data-stu-id="978d7-133">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="978d7-134">从以下项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="978d7-134">Choose from:</span></span>
    - <span data-ttu-id="978d7-135">**所有网站**：组织内的所有 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="978d7-135">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="978d7-136">这其中包括当前和未来的网站。</span><span class="sxs-lookup"><span data-stu-id="978d7-136">This includes current and future sites.</span></span>
    - <span data-ttu-id="978d7-137">**全部，所选网站除外**：键入要排除的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="978d7-137">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="978d7-138">还可以上载想要从发现中退出的网站列表。</span><span class="sxs-lookup"><span data-stu-id="978d7-138">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="978d7-139">将来创建的网站将包含为主题发现源。</span><span class="sxs-lookup"><span data-stu-id="978d7-139">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="978d7-140">**仅选定网站**：键入要包含的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="978d7-140">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="978d7-141">您还可以上载网站列表。</span><span class="sxs-lookup"><span data-stu-id="978d7-141">You can also upload a list of sites.</span></span> <span data-ttu-id="978d7-142">将不包含未来创建的网站作为发现源。</span><span class="sxs-lookup"><span data-stu-id="978d7-142">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="978d7-143">**无网站**：不包含任何 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="978d7-143">**No sites**: Do not include any SharePoint sites.</span></span>

    ![选择如何查找主题](../media/ksetup1.png) 
   
5. <span data-ttu-id="978d7-145">在" **按名称排除** 主题"部分，可以添加要从主题发现中排除的主题的名称。</span><span class="sxs-lookup"><span data-stu-id="978d7-145">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="978d7-146">使用此设置可防止敏感信息作为主题包含在内。</span><span class="sxs-lookup"><span data-stu-id="978d7-146">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="978d7-147">选项包括：</span><span class="sxs-lookup"><span data-stu-id="978d7-147">The options are:</span></span>
    - <span data-ttu-id="978d7-148">**不排除任何主题**</span><span class="sxs-lookup"><span data-stu-id="978d7-148">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="978d7-149">**按名称排除主题**</span><span class="sxs-lookup"><span data-stu-id="978d7-149">**Exclude topics by name**</span></span>

    ![排除主题](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="978d7-151"> (发现之后，知识管理员还可以排除主题中心) </span><span class="sxs-lookup"><span data-stu-id="978d7-151">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="978d7-152">如何按名称排除主题</span><span class="sxs-lookup"><span data-stu-id="978d7-152">How to exclude topics by name</span></span>    

    <span data-ttu-id="978d7-153">如果需要排除主题，在选择"按名称排除主题"后，下载 .csv 模板，然后使用要从发现结果中排除的主题列表更新该模板。</span><span class="sxs-lookup"><span data-stu-id="978d7-153">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![排除 CSV 模板中的主题](../media/exclude-topics-csv.png) 

    <span data-ttu-id="978d7-155">在 CSV 模板中，输入与要排除的主题相关的以下信息：</span><span class="sxs-lookup"><span data-stu-id="978d7-155">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="978d7-156">**名称**：键入要排除的主题的名称。</span><span class="sxs-lookup"><span data-stu-id="978d7-156">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="978d7-157">可以通过两种方式来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="978d7-157">There are two ways to do this:</span></span>
        - <span data-ttu-id="978d7-158">完全匹配：可以包含确切的名称或缩写词 (例如 *Contoso* 或 *ATL*) 。</span><span class="sxs-lookup"><span data-stu-id="978d7-158">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="978d7-159">部分匹配：可以排除其中包含特定单词的所有主题。</span><span class="sxs-lookup"><span data-stu-id="978d7-159">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="978d7-160">例如 *，arc 将* 排除包含单词 *arc* 的所有主题，如弧 *形圆*、*弧* 形圆或 *培训弧*。请注意，它将不会排除将文本作为单词的一部分包含的主题，例如体系结构 *。*</span><span class="sxs-lookup"><span data-stu-id="978d7-160">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="978d7-161">**代表 (可选**) ：如果要排除首字母缩写词，请键入首字母缩写词代表的单词。</span><span class="sxs-lookup"><span data-stu-id="978d7-161">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="978d7-162">**MatchType-Exact/Partial**：键入您输入 *的名称是精确* 匹配类型还是 *部分* 匹配类型。</span><span class="sxs-lookup"><span data-stu-id="978d7-162">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="978d7-163">完成并保存文件后，.csv **浏览找到并选择** 它。</span><span class="sxs-lookup"><span data-stu-id="978d7-163">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="978d7-164">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="978d7-164">Select **Next**.</span></span>

6. <span data-ttu-id="978d7-165">在Who **主题及其** 可在何处看到这些主题页面，您将配置主题可见性。</span><span class="sxs-lookup"><span data-stu-id="978d7-165">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="978d7-166">在Who **主题** 设置中，可以选择谁有权访问主题详细信息，例如突出显示的主题、主题卡片、搜索中的主题答案和主题页面。</span><span class="sxs-lookup"><span data-stu-id="978d7-166">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="978d7-167">可以选择：</span><span class="sxs-lookup"><span data-stu-id="978d7-167">You can select:</span></span>
    - <span data-ttu-id="978d7-168">**我的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="978d7-168">**Everyone in my organization**</span></span>
    - <span data-ttu-id="978d7-169">**仅选定人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="978d7-169">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="978d7-170">**没人**</span><span class="sxs-lookup"><span data-stu-id="978d7-170">**No one**</span></span>

    ![Who主题](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="978d7-172">虽然此设置允许你选择组织的任何用户，但只有分配了主题体验许可证的用户才能查看主题。</span><span class="sxs-lookup"><span data-stu-id="978d7-172">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="978d7-173">在" **主题管理的权限** "页中，选择能够创建、编辑或管理主题的用户。</span><span class="sxs-lookup"><span data-stu-id="978d7-173">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="978d7-174">在 **"Who主题"部分**，可以选择：</span><span class="sxs-lookup"><span data-stu-id="978d7-174">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="978d7-175">**我的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="978d7-175">**Everyone in my organization**</span></span>
    - <span data-ttu-id="978d7-176">**仅选定人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="978d7-176">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="978d7-177">**没人**</span><span class="sxs-lookup"><span data-stu-id="978d7-177">**No one**</span></span>

    ![主题管理权限，可以创建和编辑主题](../media/ksetup3.png) 

8. <span data-ttu-id="978d7-179">在 **"Who主题"部分中**，可以选择：</span><span class="sxs-lookup"><span data-stu-id="978d7-179">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="978d7-180">**我的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="978d7-180">**Everyone in my organization**</span></span>
    - <span data-ttu-id="978d7-181">**仅选定人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="978d7-181">**Only selected people or security groups**</span></span>

    ![主题管理的权限](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="978d7-183">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="978d7-183">Select **Next**.</span></span>

9. <span data-ttu-id="978d7-184">在 **"创建主题中心** "页上，您可以创建主题中心网站，可在其中查看主题页面并管理主题。</span><span class="sxs-lookup"><span data-stu-id="978d7-184">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="978d7-185">在" **网站名称"** 框中，键入主题中心的名称。</span><span class="sxs-lookup"><span data-stu-id="978d7-185">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="978d7-186">可以选择在"说明"框中键入 **简短** 说明。</span><span class="sxs-lookup"><span data-stu-id="978d7-186">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="978d7-187">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="978d7-187">Select **Next**.</span></span>

   ![创建知识中心](../media/ksetup4.png)  

10. <span data-ttu-id="978d7-189">在 **审查并完成** 页面上，可查看所选设置并选择进行更改。</span><span class="sxs-lookup"><span data-stu-id="978d7-189">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="978d7-190">如果对你的选择感到满意，请选择 **激活**。</span><span class="sxs-lookup"><span data-stu-id="978d7-190">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="978d7-191">将显示 **"Viva 主题已激活** "页，确认系统现在开始分析所选主题网站并创建主题中心网站。</span><span class="sxs-lookup"><span data-stu-id="978d7-191">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="978d7-192">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="978d7-192">Select **Done**.</span></span>

12. <span data-ttu-id="978d7-193">你将返回到你的连接 **人员到知识** 页面。</span><span class="sxs-lookup"><span data-stu-id="978d7-193">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="978d7-194">在此页面中，可选择 **管理**，对配置设置进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="978d7-194">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![设置应用](../media/ksetup7.png)    

## <a name="manage-topic-experiences"></a><span data-ttu-id="978d7-196">管理主题体验</span><span class="sxs-lookup"><span data-stu-id="978d7-196">Manage topic experiences</span></span>

<span data-ttu-id="978d7-197">设置主题后，可以在管理中心中更改在设置Microsoft 365[的设置](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)。</span><span class="sxs-lookup"><span data-stu-id="978d7-197">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="978d7-198">请参阅以下参考：</span><span class="sxs-lookup"><span data-stu-id="978d7-198">See the following references:</span></span>

- [<span data-ttu-id="978d7-199">在 Microsoft Viva 主题中管理主题发现</span><span class="sxs-lookup"><span data-stu-id="978d7-199">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="978d7-200">在 Microsoft Viva 主题中管理主题可见性</span><span class="sxs-lookup"><span data-stu-id="978d7-200">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="978d7-201">在 Microsoft Viva 主题中管理主题权限</span><span class="sxs-lookup"><span data-stu-id="978d7-201">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="978d7-202">在 Microsoft Viva 主题中更改主题中心的名称</span><span class="sxs-lookup"><span data-stu-id="978d7-202">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="978d7-203">另请参阅</span><span class="sxs-lookup"><span data-stu-id="978d7-203">See also</span></span>

[<span data-ttu-id="978d7-204">主题体验概述</span><span class="sxs-lookup"><span data-stu-id="978d7-204">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
