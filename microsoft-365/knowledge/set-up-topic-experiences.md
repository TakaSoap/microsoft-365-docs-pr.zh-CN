---
title: 在 Microsoft 365 中设置主题体验
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何在 Microsoft 365 中设置主题体验
ms.openlocfilehash: df4dccead4b627a215ec7ebd11932aa0f2b6ac08
ms.sourcegitcommit: 18f95c4b7f74881b4a6ce71ad2ffa78a6ead5584
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731363"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a><span data-ttu-id="ba08f-103">在 Microsoft 365 中设置主题体验</span><span class="sxs-lookup"><span data-stu-id="ba08f-103">Set up topic experiences in Microsoft 365</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LBp7]  

</br>

<span data-ttu-id="ba08f-104">可以使用 Microsoft 365 管理中心设置和配置 [主题体验](topic-experiences-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ba08f-104">You can use the Microsoft 365 admin center to set up and configure [topic experiences](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="ba08f-105">规划在环境中设置和配置主题的最佳方法非常重要。</span><span class="sxs-lookup"><span data-stu-id="ba08f-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="ba08f-106">在开始本文 [中的过程之前](plan-topic-experiences.md) ，请务必先阅读"规划"主题体验。</span><span class="sxs-lookup"><span data-stu-id="ba08f-106">Be sure to read [Plan topic experiences](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="ba08f-107">您必须是全局管理员或 SharePoint 管理员才能访问 Microsoft 365 管理中心并设置主题体验。</span><span class="sxs-lookup"><span data-stu-id="ba08f-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

## <a name="set-up-topic-experiences"></a><span data-ttu-id="ba08f-108">设置主题体验</span><span class="sxs-lookup"><span data-stu-id="ba08f-108">Set up topic experiences</span></span>

<span data-ttu-id="ba08f-109">在 Microsoft 365 中设置主题体验</span><span class="sxs-lookup"><span data-stu-id="ba08f-109">To set up topic experiences in Microsoft 365</span></span>

1. <span data-ttu-id="ba08f-110">在 [Microsoft 365 管理中心](https://admin.microsoft.com)中，选择 **"** 设置"，然后查看"文件和 **内容"** 部分。</span><span class="sxs-lookup"><span data-stu-id="ba08f-110">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="ba08f-111">在"**文件和内容"部分**，单击 **"将人员连接到知识"。**</span><span class="sxs-lookup"><span data-stu-id="ba08f-111">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![将人员连接到知识](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="ba08f-113">在 **"将人员连接到知识** "页上， **单击"** 入门"以完成设置过程。</span><span class="sxs-lookup"><span data-stu-id="ba08f-113">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![开始行动](../media/k-get-started.png) 

4. <span data-ttu-id="ba08f-115">在 **"选择知识网络** 查找主题方式"页上，您将配置主题发现。</span><span class="sxs-lookup"><span data-stu-id="ba08f-115">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="ba08f-116">在 **"选择 SharePoint 主题源** "部分中，选择要在发现过程中作为主题源对哪些 SharePoint 网站进行爬网。</span><span class="sxs-lookup"><span data-stu-id="ba08f-116">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="ba08f-117">从以下项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="ba08f-117">Choose from:</span></span>
    - <span data-ttu-id="ba08f-118">**所有网站**：组织的所有 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="ba08f-118">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="ba08f-119">这包括当前和将来的网站。</span><span class="sxs-lookup"><span data-stu-id="ba08f-119">This includes current and future sites.</span></span>
    - <span data-ttu-id="ba08f-120">**全部，所选网站除外**：键入要排除的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="ba08f-120">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="ba08f-121">还可以上载要选择从发现中退出的网站列表。</span><span class="sxs-lookup"><span data-stu-id="ba08f-121">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="ba08f-122">将来创建的网站将包含为主题发现源。</span><span class="sxs-lookup"><span data-stu-id="ba08f-122">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="ba08f-123">**仅选定网站**：键入要包含的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="ba08f-123">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="ba08f-124">还可以上载网站列表。</span><span class="sxs-lookup"><span data-stu-id="ba08f-124">You can also upload a list of sites.</span></span> <span data-ttu-id="ba08f-125">将来创建的网站不会作为主题发现源包含在内。</span><span class="sxs-lookup"><span data-stu-id="ba08f-125">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="ba08f-126">**无网站**：不包括任何 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="ba08f-126">**No sites**: Do not include any SharePoint sites.</span></span>

    ![选择如何查找主题](../media/ksetup1.png) 
   
5. <span data-ttu-id="ba08f-128">在 **"按名称排除** 主题"部分，可以添加要从主题发现中排除的主题的名称。</span><span class="sxs-lookup"><span data-stu-id="ba08f-128">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="ba08f-129">使用此设置可防止敏感信息作为主题包含在内。</span><span class="sxs-lookup"><span data-stu-id="ba08f-129">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="ba08f-130">选项包括：</span><span class="sxs-lookup"><span data-stu-id="ba08f-130">The options are:</span></span>
    - <span data-ttu-id="ba08f-131">**不排除任何主题**</span><span class="sxs-lookup"><span data-stu-id="ba08f-131">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="ba08f-132">**按名称排除主题**</span><span class="sxs-lookup"><span data-stu-id="ba08f-132">**Exclude topics by name**</span></span>

    ![排除主题](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="ba08f-134"> (发现之后，知识管理员还可以排除主题中心) </span><span class="sxs-lookup"><span data-stu-id="ba08f-134">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="ba08f-135">如何按名称排除主题</span><span class="sxs-lookup"><span data-stu-id="ba08f-135">How to exclude topics by name</span></span>    

    <span data-ttu-id="ba08f-136">如果需要排除主题，请在选择"按名称排除主题"后，选择下载 .csv 模板，然后用要从发现结果中排除的主题列表更新它。</span><span class="sxs-lookup"><span data-stu-id="ba08f-136">If you need to exclude topics, after selecting **Exclude topics by name**, select download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![排除 CSV 模板中的主题](../media/exclude-topics-csv.png) 

    <span data-ttu-id="ba08f-138">在 CSV 模板中，输入有关要排除的主题的以下信息：</span><span class="sxs-lookup"><span data-stu-id="ba08f-138">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="ba08f-139">**名称**：键入要排除的主题的名称。</span><span class="sxs-lookup"><span data-stu-id="ba08f-139">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="ba08f-140">可通过 2 种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="ba08f-140">There are two ways to do this:</span></span>
        - <span data-ttu-id="ba08f-141">完全匹配：可以包括确切的名称或缩写词 (例如 *Contoso* 或 *ATL*) 。</span><span class="sxs-lookup"><span data-stu-id="ba08f-141">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="ba08f-142">部分匹配：可以排除其中具有特定单词的所有主题。</span><span class="sxs-lookup"><span data-stu-id="ba08f-142">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="ba08f-143">例如 *，arc* 将排除其中带弧字的所有主题，如 *弧形圆*、圆弧 *弧* 线或 *培训弧*。请注意，它将不会排除其中的文本作为单词的一部分包含的主题，如 *体系结构。*</span><span class="sxs-lookup"><span data-stu-id="ba08f-143">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="ba08f-144">**代表 (可选**) ：如果要排除首字母缩略词，请键入首字母缩写词代表的单词。</span><span class="sxs-lookup"><span data-stu-id="ba08f-144">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="ba08f-145">**MatchType-Exact/Partial：** 键入您输入的名称 *是精确匹配* 类型还是 *部分* 匹配类型。</span><span class="sxs-lookup"><span data-stu-id="ba08f-145">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="ba08f-146">完成并保存 .csv 文件后， **选择"浏览** "找到并选择它。</span><span class="sxs-lookup"><span data-stu-id="ba08f-146">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="ba08f-147">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="ba08f-147">Select **Next**.</span></span>

6. <span data-ttu-id="ba08f-148">在 **"谁可以看到主题** 以及他们在哪里可以看到主题"页上，将配置主题可见性。</span><span class="sxs-lookup"><span data-stu-id="ba08f-148">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="ba08f-149">在 **"谁可以看到** 知识网络设置中的主题"中，选择有权访问主题详细信息（如突出显示的主题、主题卡片、搜索中的主题答案和主题页）的哪些人员。</span><span class="sxs-lookup"><span data-stu-id="ba08f-149">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="ba08f-150">可以选择：</span><span class="sxs-lookup"><span data-stu-id="ba08f-150">You can select:</span></span>
    - <span data-ttu-id="ba08f-151">**我的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="ba08f-151">**Everyone in my organization**</span></span>
    - <span data-ttu-id="ba08f-152">**仅选定人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="ba08f-152">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="ba08f-153">**没人**</span><span class="sxs-lookup"><span data-stu-id="ba08f-153">**No one**</span></span>

    ![谁可以看到主题](../media/ksetup2.png)  

 > [!Note] 
 > <span data-ttu-id="ba08f-155">虽然此设置允许你选择组织的任何用户，但只有分配了主题体验许可证的用户才能查看主题。</span><span class="sxs-lookup"><span data-stu-id="ba08f-155">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="ba08f-156">在 **"主题管理的权限** "页中，选择能够创建、编辑或管理主题的用户。</span><span class="sxs-lookup"><span data-stu-id="ba08f-156">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="ba08f-157">在" **谁可以创建和编辑主题** "部分中，可以选择：</span><span class="sxs-lookup"><span data-stu-id="ba08f-157">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="ba08f-158">**我的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="ba08f-158">**Everyone in my organization**</span></span>
    - <span data-ttu-id="ba08f-159">**仅选定人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="ba08f-159">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="ba08f-160">**没人**</span><span class="sxs-lookup"><span data-stu-id="ba08f-160">**No one**</span></span>

    ![主题管理权限，可创建和编辑主题](../media/ksetup3.png) 

8. <span data-ttu-id="ba08f-162">在" **谁可以管理主题** "部分，可以选择：</span><span class="sxs-lookup"><span data-stu-id="ba08f-162">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="ba08f-163">**我的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="ba08f-163">**Everyone in my organization**</span></span>
    - <span data-ttu-id="ba08f-164">**仅选定人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="ba08f-164">**Only selected people or security groups**</span></span>

    ![主题管理的权限](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="ba08f-166">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="ba08f-166">Select **Next**.</span></span>

9. <span data-ttu-id="ba08f-167">在 **"创建主题中心** "页上，您可以创建可在其中查看主题页面并管理主题的主题中心网站。</span><span class="sxs-lookup"><span data-stu-id="ba08f-167">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="ba08f-168">在 **"网站名称"** 框中，键入主题中心的名称。</span><span class="sxs-lookup"><span data-stu-id="ba08f-168">In the **Site name** box, type a name for your Topic center.</span></span> <span data-ttu-id="ba08f-169">可以选择在"说明"框中键入 **简短** 说明。</span><span class="sxs-lookup"><span data-stu-id="ba08f-169">You can optionally type a short description in the **Description** box.</span></span> 

<span data-ttu-id="ba08f-170">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="ba08f-170">Select **Next**.</span></span>

   ![创建知识中心](../media/ksetup4.png)  

10. <span data-ttu-id="ba08f-172">在 **审查并完成** 页面上，可查看所选设置并选择进行更改。</span><span class="sxs-lookup"><span data-stu-id="ba08f-172">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="ba08f-173">如果对你的选择感到满意，请选择 **激活**。</span><span class="sxs-lookup"><span data-stu-id="ba08f-173">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="ba08f-174">将显示 **"已激活知识网络** "页，确认系统现在将开始分析所选网站的主题并创建知识中心网站。</span><span class="sxs-lookup"><span data-stu-id="ba08f-174">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="ba08f-175">选择 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="ba08f-175">Select **Done**.</span></span>

12. <span data-ttu-id="ba08f-176">你将返回到"将人员连接到 **知识"** 页面。</span><span class="sxs-lookup"><span data-stu-id="ba08f-176">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="ba08f-177">在此页面中，可选择 **管理**，对配置设置进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="ba08f-177">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![应用的设置](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="ba08f-179">分配许可证</span><span class="sxs-lookup"><span data-stu-id="ba08f-179">Assign licenses</span></span>

<span data-ttu-id="ba08f-180">配置主题体验后，必须为使用主题体验的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="ba08f-180">Once you have configured topic experiences, you must assign licenses for the users who will be using topic experiences.</span></span> <span data-ttu-id="ba08f-181">只有具有许可证的用户才能查看有关主题的信息，包括突出显示、主题卡片、主题页面和主题中心。</span><span class="sxs-lookup"><span data-stu-id="ba08f-181">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="ba08f-182">以分配许可证：</span><span class="sxs-lookup"><span data-stu-id="ba08f-182">To assign licenses:</span></span>

1. <span data-ttu-id="ba08f-183">在Microsoft 365 管理中心中，在 **用户** 下，点击 **活动用户**。</span><span class="sxs-lookup"><span data-stu-id="ba08f-183">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="ba08f-184">选择要给予许可的用户，然后单击 **管理产品许可证**。</span><span class="sxs-lookup"><span data-stu-id="ba08f-184">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="ba08f-185">选择 **分配更多**。</span><span class="sxs-lookup"><span data-stu-id="ba08f-185">Select **Assign more**.</span></span>

4. <span data-ttu-id="ba08f-186">在 **"许可证"** 下， **选择主题体验**。</span><span class="sxs-lookup"><span data-stu-id="ba08f-186">Under **Licenses**, select **Topic Experiences**.</span></span>

5. <span data-ttu-id="ba08f-187">在 **"应用**"下，确保 **已选择具有索引** 和 **主题体验的图形** 连接器搜索。</span><span class="sxs-lookup"><span data-stu-id="ba08f-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ba08f-188">![Microsoft 365 管理中心的 SharePoint Syntex 许可证](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="ba08f-188">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

6. <span data-ttu-id="ba08f-189">单击 **保存更改**。</span><span class="sxs-lookup"><span data-stu-id="ba08f-189">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="ba08f-190">管理主题体验</span><span class="sxs-lookup"><span data-stu-id="ba08f-190">Manage topic experiences</span></span>

<span data-ttu-id="ba08f-191">设置主题体验后，可以在 [Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)管理中心中更改在设置期间选择的设置。</span><span class="sxs-lookup"><span data-stu-id="ba08f-191">Once you have set up topic experiences, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="ba08f-192">请参阅以下引用：</span><span class="sxs-lookup"><span data-stu-id="ba08f-192">See the following references:</span></span>

- [<span data-ttu-id="ba08f-193">在 Microsoft 365 中管理主题发现</span><span class="sxs-lookup"><span data-stu-id="ba08f-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="ba08f-194">在 Microsoft 365 中管理主题可见性</span><span class="sxs-lookup"><span data-stu-id="ba08f-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="ba08f-195">在 Microsoft 365 中管理主题权限</span><span class="sxs-lookup"><span data-stu-id="ba08f-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="ba08f-196">在 Microsoft 365 中更改主题中心的名称</span><span class="sxs-lookup"><span data-stu-id="ba08f-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="ba08f-197">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba08f-197">See also</span></span>

[<span data-ttu-id="ba08f-198">主题体验概述</span><span class="sxs-lookup"><span data-stu-id="ba08f-198">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
