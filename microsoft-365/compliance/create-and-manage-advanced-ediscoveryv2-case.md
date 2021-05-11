---
title: 创建和管理Advanced eDiscovery事例Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 本文介绍如何创建和管理Advanced eDiscovery案例。 第一步是创建案例并开始使用Advanced eDiscovery功能。
ms.openlocfilehash: 95e88bb071476de1ed66b3ffaa8942f0a9df89c2
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311636"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a><span data-ttu-id="11f70-104">创建和管理Advanced eDiscovery案例</span><span class="sxs-lookup"><span data-stu-id="11f70-104">Create and manage an Advanced eDiscovery case</span></span>

<span data-ttu-id="11f70-105">在设置Advanced eDiscovery并将权限分配给将[](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions)管理事例的组织中电子数据展示管理员之后，下一步是创建和管理事例。</span><span class="sxs-lookup"><span data-stu-id="11f70-105">After setting up Advanced eDiscovery and [assigning permissions to eDiscovery managers](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) in your organization that will manage cases, the next step is to create and manage a case.</span></span>

<span data-ttu-id="11f70-106">本文还简要概述了法律案件或其他类型的调查Advanced eDiscovery案例管理工作流。</span><span class="sxs-lookup"><span data-stu-id="11f70-106">This article also provides a high-level overview of using cases to manage the Advanced eDiscovery workflow for a legal case or other types of investigations.</span></span>

## <a name="create-a-case"></a><span data-ttu-id="11f70-107">创建案例</span><span class="sxs-lookup"><span data-stu-id="11f70-107">Create a case</span></span>

<span data-ttu-id="11f70-108">完成以下步骤以创建案例并添加成员。</span><span class="sxs-lookup"><span data-stu-id="11f70-108">Complete the following steps to create a case and add members.</span></span> <span data-ttu-id="11f70-109">创建案例的用户将自动添加为成员。</span><span class="sxs-lookup"><span data-stu-id="11f70-109">The user who creates the case is automatically added as a member.</span></span> <span data-ttu-id="11f70-110">案例的成员可以在合规中心内访问Microsoft 365，并执行Advanced eDiscovery任务。</span><span class="sxs-lookup"><span data-stu-id="11f70-110">Members of the case can access the case in the Microsoft 365 compliance center and perform Advanced eDiscovery tasks.</span></span>

1. <span data-ttu-id="11f70-111">转到 <https://compliance.microsoft.com> ，然后使用已分配有电子数据展示权限的用户帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="11f70-111">Go to <https://compliance.microsoft.com> and sign in using the credentials for user account that has been assigned eDiscovery permissions.</span></span> <span data-ttu-id="11f70-112">组织管理角色组的成员还可以创建Advanced eDiscovery案例。</span><span class="sxs-lookup"><span data-stu-id="11f70-112">Members of the Organization Management role group can also create Advanced eDiscovery cases.</span></span>

2. <span data-ttu-id="11f70-113">在 Microsoft 365 合规中心的左侧导航窗格中，单击 **显示所有**，然后单击" **电子数据展示>高级**。</span><span class="sxs-lookup"><span data-stu-id="11f70-113">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

3. <span data-ttu-id="11f70-114">在 **"Advanced eDiscovery"** 页上，单击"事例 **"** 选项卡，然后单击"**创建事例"。**</span><span class="sxs-lookup"><span data-stu-id="11f70-114">On the **Advanced eDiscovery** page, click the **Cases** tab, and then click **Create a case**.</span></span>

4. <span data-ttu-id="11f70-115">在" **新建电子数据** 展示案例"飞出页面上，为案件 (一) ，然后键入可选的案例编号和说明。</span><span class="sxs-lookup"><span data-stu-id="11f70-115">On the **New eDiscovery case** flyout page, give the case a name (required), and then type an optional case number and description.</span></span> <span data-ttu-id="11f70-116">案例名称在组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="11f70-116">The case name must be unique in your organization.</span></span>

5. <span data-ttu-id="11f70-117">单击 **"保存** "创建案例。</span><span class="sxs-lookup"><span data-stu-id="11f70-117">Click **Save** to create the case.</span></span>

   <span data-ttu-id="11f70-118">将新建一个 **case，设置** 显示新案例的"新建"选项卡。</span><span class="sxs-lookup"><span data-stu-id="11f70-118">The new case is created and the **Settings** tab in the new case is displayed.</span></span>

6. <span data-ttu-id="11f70-119">在 **"&"选项卡** 上的"设置权限 **"** 磁贴中，单击"选择 **"。**</span><span class="sxs-lookup"><span data-stu-id="11f70-119">In the **Access & permissions** tile on the **Settings** tab, click **Select**.</span></span>

7. <span data-ttu-id="11f70-120">在" **管理此案例** "飞出页面上的"管理成员 **"下**，单击 **"添加** "将成员添加到案例。</span><span class="sxs-lookup"><span data-stu-id="11f70-120">On the **Manage this case** flyout page, under **Manage members**, click **Add** to add members to the case.</span></span>

8. <span data-ttu-id="11f70-121">在人员列表中，选中要添加到案例的用户名旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="11f70-121">In the list of people, select the check box next to the names of the people that you want to add to the case.</span></span> <span data-ttu-id="11f70-122">如前所述，请确保你添加到案例的人已分配有适当的电子数据展示权限。</span><span class="sxs-lookup"><span data-stu-id="11f70-122">As previously explained, be sure that the people you add to the case have been assigned the appropriate eDiscovery permissions.</span></span>

9. <span data-ttu-id="11f70-123">选择要添加为案例成员的人后，单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="11f70-123">After you've selected the people to add as members of the case, click **Add**.</span></span>

10. <span data-ttu-id="11f70-124">在 **管理此案例** 弹出页面中， **保存** 以保存新的案例成员列表。</span><span class="sxs-lookup"><span data-stu-id="11f70-124">In the **Manage this case** flyout page, click **Save** to save the new list of case members.</span></span>

11. <span data-ttu-id="11f70-125">单击" **主页"** 选项卡以转到案例主页。</span><span class="sxs-lookup"><span data-stu-id="11f70-125">Click the **Home** tab to go to the case home page.</span></span>

## <a name="manage-the-workflow"></a><span data-ttu-id="11f70-126">管理工作流</span><span class="sxs-lookup"><span data-stu-id="11f70-126">Manage the workflow</span></span>

<span data-ttu-id="11f70-127">为了让你开始使用Advanced eDiscovery，下面是一个符合常见电子数据展示做法[的基本工作流](advanced-ediscovery-edrm.md)。</span><span class="sxs-lookup"><span data-stu-id="11f70-127">To get you started using Advanced eDiscovery, here's a basic workflow that aligns with [common eDiscovery practices](advanced-ediscovery-edrm.md).</span></span> <span data-ttu-id="11f70-128">在每个步骤中，我们还将重点介绍一些Advanced eDiscovery扩展的功能。</span><span class="sxs-lookup"><span data-stu-id="11f70-128">In each of these steps, we'll also highlight some extended Advanced eDiscovery functionality that you can explore.</span></span>

![Advanced eDiscovery工作流](../media/AeDWorkflow.png)

1. <span data-ttu-id="11f70-130">**[将保管](add-custodians-to-case.md)[人和非托管数据源添加到](non-custodial-data-sources.md)案例**。</span><span class="sxs-lookup"><span data-stu-id="11f70-130">**[Add custodians](add-custodians-to-case.md) and [non-custodial data sources](non-custodial-data-sources.md) to the case**.</span></span> <span data-ttu-id="11f70-131">创建案例后的第一步是添加保管人。</span><span class="sxs-lookup"><span data-stu-id="11f70-131">The first step after creating a case is to add custodians.</span></span> <span data-ttu-id="11f70-132">保管 *人* 是具有与案例相关的文档或电子文件的管理控制权限的人。</span><span class="sxs-lookup"><span data-stu-id="11f70-132">A *custodian* is a person having administrative control of a document or electronic file that may be relevant to the case.</span></span> <span data-ttu-id="11f70-133">此外，还可以添加不与特定用户关联但可能与案例相关的数据源。</span><span class="sxs-lookup"><span data-stu-id="11f70-133">Additionally, you can add data sources that aren't associated with a specific user but may be relevant to the case.</span></span>

   <span data-ttu-id="11f70-134">下面是在向案例 (保管人时) 可以执行某些操作：</span><span class="sxs-lookup"><span data-stu-id="11f70-134">Here are some things that happen (or that you can do) when you add custodians to a case:</span></span>

   - <span data-ttu-id="11f70-135">保管人 Exchange 邮箱、OneDrive 帐户以及保管人是其中成员的任何 Microsoft Teams 或 Yammer 组的数据可以"标记为"在案例内为诉讼数据。</span><span class="sxs-lookup"><span data-stu-id="11f70-135">Data in the custodian's Exchange mailbox, OneDrive account, and any Microsoft Teams or Yammer groups that the custodian is a member of can be "marked" as custodial data in the case.</span></span>
  
   - <span data-ttu-id="11f70-136">保管人数据通过称为高级 (过程 *对保管人数据重新* 编制) 。</span><span class="sxs-lookup"><span data-stu-id="11f70-136">Custodian data is reindexed (by a process called *Advanced indexing*).</span></span> <span data-ttu-id="11f70-137">这有助于在下一步中优化搜索。</span><span class="sxs-lookup"><span data-stu-id="11f70-137">This helps optimize searching for it in the next step.</span></span>
  
   - <span data-ttu-id="11f70-138">你可以将保管人数据保留。</span><span class="sxs-lookup"><span data-stu-id="11f70-138">You can place a hold on custodian data.</span></span> <span data-ttu-id="11f70-139">这将保留调查期间可能与案例相关的数据。</span><span class="sxs-lookup"><span data-stu-id="11f70-139">This preserves data that may be relevant to the case during the investigation.</span></span>
  
   - <span data-ttu-id="11f70-140">您可以将其他数据源与保管人 (例如，您可以将 SharePoint 站点或 Microsoft 365 组与保管人) 关联，以便可以重新索引、保留和搜索此数据，就像保管人邮箱或 OneDrive 帐户中的数据一样。</span><span class="sxs-lookup"><span data-stu-id="11f70-140">You can associate other data sources with a custodian (for example, you can associate a SharePoint site or Microsoft 365 Group with a custodian) so this data can be reindexed, placed on hold, and searched, just like the data in the custodian's mailbox or OneDrive account.</span></span>

   - <span data-ttu-id="11f70-141">您可以使用安全[中心中的](managing-custodian-communications.md)通信Advanced eDiscovery向保管人发送法定保留通知。</span><span class="sxs-lookup"><span data-stu-id="11f70-141">You can use the [communications workflow](managing-custodian-communications.md) in Advanced eDiscovery to send a legal hold notification to custodians.</span></span>

2. <span data-ttu-id="11f70-142">**[从数据源中收集相关内容](create-draft-collection.md)**。</span><span class="sxs-lookup"><span data-stu-id="11f70-142">**[Collect relevant content from data sources](create-draft-collection.md)**.</span></span> <span data-ttu-id="11f70-143">将保管人和非托管数据源添加到案例后，使用内置集合工具搜索这些数据源中可能与案例相关的内容。</span><span class="sxs-lookup"><span data-stu-id="11f70-143">After you add custodians and non-custodial data sources to a case, use the built-in collections tool to search these data sources for content that may be relevant to the case.</span></span> <span data-ttu-id="11f70-144">您可以使用关键字、属性和条件来构建搜索查询[](building-search-queries.md)，这些查询使用与案例最相关的数据返回搜索结果。</span><span class="sxs-lookup"><span data-stu-id="11f70-144">You use keywords, properties, and conditions to [build search queries](building-search-queries.md) that return search results with the data that's most likely relevant to the case.</span></span> <span data-ttu-id="11f70-145">还可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="11f70-145">You can also:</span></span>

   - <span data-ttu-id="11f70-146">查看 [可帮助您](collection-statistics-reports.md) 优化集合以缩小结果范围的集合统计信息。</span><span class="sxs-lookup"><span data-stu-id="11f70-146">View [collection statistics](collection-statistics-reports.md) that may help you refine a collection to narrow the results.</span></span>

   - <span data-ttu-id="11f70-147">预览集合示例，以快速验证是否找到相关数据。</span><span class="sxs-lookup"><span data-stu-id="11f70-147">Preview a sample of the collection to quickly verify whether the relevant data is being found.</span></span>

   - <span data-ttu-id="11f70-148">修改查询并重新运行集合。</span><span class="sxs-lookup"><span data-stu-id="11f70-148">Revise a query and rerun the collection.</span></span>

3. <span data-ttu-id="11f70-149">**[将集合提交到审阅集](commit-draft-collection.md)**。</span><span class="sxs-lookup"><span data-stu-id="11f70-149">**[Commit collection to a review set](commit-draft-collection.md)**.</span></span> <span data-ttu-id="11f70-150">配置并验证搜索返回所需数据后，下一步是将搜索结果添加到审阅集。</span><span class="sxs-lookup"><span data-stu-id="11f70-150">Once you've configured and verified that a search returns the desired data, the next step is to add the search results to a review set.</span></span> <span data-ttu-id="11f70-151">向审阅集添加数据时，项目会从原始位置复制到安全Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="11f70-151">When you add data to a review set, items are copied from their original location to a secure Azure Storage location.</span></span> <span data-ttu-id="11f70-152">再次对数据进行索引索引，以在审阅和分析审阅集内的项目时优化数据，以便进行全面而快速的搜索。</span><span class="sxs-lookup"><span data-stu-id="11f70-152">The data is reindexed again to optimize it for thorough and fast searches when reviewing and analyzing items in the review set.</span></span> <span data-ttu-id="11f70-153">此外，您还可以[将非Office 365数据添加到审阅集](load-non-office-365-data-into-a-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="11f70-153">Additionally, you can also [add non-Office 365 data into a review set](load-non-office-365-data-into-a-review-set.md).</span></span>

   <span data-ttu-id="11f70-154">还有一种特殊类型的审阅集，你可以将数据添加到 ，称为对话 *审阅集*。</span><span class="sxs-lookup"><span data-stu-id="11f70-154">There's also a special kind of review set that you can add data to, called a *conversation review set*.</span></span> <span data-ttu-id="11f70-155">这些类型的评论集提供了对话重建功能，可以重新构造、审阅和导出线程对话，如 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="11f70-155">These types of reviews sets provide conversation reconstruction capabilities to reconstruct, review, and export threaded conversations like those in Microsoft Teams.</span></span> <span data-ttu-id="11f70-156">有关详细信息，请参阅 [审阅高级 eDiscovery 中的对话](conversation-review-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="11f70-156">For more information, see [Review conversations in Advanced eDiscovery](conversation-review-sets.md).</span></span>

4. <span data-ttu-id="11f70-157">**查看和分析审阅集内的数据**。</span><span class="sxs-lookup"><span data-stu-id="11f70-157">**Review and analyze data in a review set**.</span></span> <span data-ttu-id="11f70-158">现在数据已位于审阅集内，您可以使用各种工具和功能来查看和分析案例数据，目的是将数据集减少为与正在调查的案例最相关的数据。</span><span class="sxs-lookup"><span data-stu-id="11f70-158">Now that data is in a review set, you can use a wide-variety of tools and capabilities to view and analyze the case data with the goal of reducing the data set to what is most relevant to the case you're investigating.</span></span> <span data-ttu-id="11f70-159">以下是您可以在此过程期间使用的一些工具和功能的列表。</span><span class="sxs-lookup"><span data-stu-id="11f70-159">Here's a list of some tools and capabilities that you can use during this process.</span></span>

   - <span data-ttu-id="11f70-160">[查看文档](view-documents-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="11f70-160">[View documents](view-documents-in-review-set.md).</span></span> <span data-ttu-id="11f70-161">这包括查看审阅集内每个文档的元数据，以及查看其本机版本或文本版本的文档。</span><span class="sxs-lookup"><span data-stu-id="11f70-161">This includes viewing the metadata for each document in a review set, and viewing the document in its native version or text version.</span></span>

   - <span data-ttu-id="11f70-162">[创建查询和筛选器](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="11f70-162">[Create queries and filters](review-set-search.md).</span></span> <span data-ttu-id="11f70-163">您可以使用各种搜索条件创建搜索查询 (包括搜索所有文件元数据属性 [) ](document-metadata-fields-in-advanced-ediscovery.md) 以进一步优化案例数据，以及将案例数据剔除到与案例最相关的内容。</span><span class="sxs-lookup"><span data-stu-id="11f70-163">You create search queries using various search criteria (including the ability to search all [file metadata properties](document-metadata-fields-in-advanced-ediscovery.md)) to further refine and cull the case data to what is most relevant to the case.</span></span> <span data-ttu-id="11f70-164">您还可以使用审阅集筛选器将其他条件快速应用于搜索查询的结果，以进一步优化这些结果。</span><span class="sxs-lookup"><span data-stu-id="11f70-164">You can also use review set filters to quickly apply other conditions to the results of a search query to further refine those results.</span></span> 

   - <span data-ttu-id="11f70-165">[创建和使用标记](tagging-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="11f70-165">[Create and use tags](tagging-documents.md).</span></span> <span data-ttu-id="11f70-166">可以将标记应用于审阅集内的文档，以确定哪些文档是响应 (还是对案例) 无响应，然后在创建搜索查询以包含或排除带标记的文档时使用这些标记。</span><span class="sxs-lookup"><span data-stu-id="11f70-166">You can apply tags to documents in a review set to identify which are responsive (or non-responsive to the case) and then use those tags when creating search queries to include or exclude the tagged documents.</span></span> <span data-ttu-id="11f70-167">您还可以标记以确定要导出的文档。</span><span class="sxs-lookup"><span data-stu-id="11f70-167">You can also tagging to determine which documents to export.</span></span>

   - <span data-ttu-id="11f70-168">[批注和修订文档](view-documents-in-review-set.md#annotate-view)。</span><span class="sxs-lookup"><span data-stu-id="11f70-168">[Annotate and redact documents](view-documents-in-review-set.md#annotate-view).</span></span> <span data-ttu-id="11f70-169">可以在评论中使用该批注工具为文档添加批注，将文档中的内容修订为工作产品。</span><span class="sxs-lookup"><span data-stu-id="11f70-169">You can use the annotation tool in a review to annotate documents and redact content in documents as work product.</span></span> <span data-ttu-id="11f70-170">我们在审阅期间生成批注或修订文档的 PDF 版本，以减少导出未修改的本机版本文档的风险。</span><span class="sxs-lookup"><span data-stu-id="11f70-170">We generate a PDF version of an annotated or redacted document during review to reduce the risk of exporting the unredacted native version of the document.</span></span>

   - <span data-ttu-id="11f70-171">[分析案例数据](analyzing-data-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="11f70-171">[Analyze case data](analyzing-data-in-review-set.md).</span></span> <span data-ttu-id="11f70-172">Advanced eDiscovery中的分析功能很强大。</span><span class="sxs-lookup"><span data-stu-id="11f70-172">The analytics functionality in Advanced eDiscovery is powerful.</span></span> <span data-ttu-id="11f70-173">对审阅集内的数据运行分析后，我们执行分析，如接近重复检测、电子邮件线程和主题，可帮助减少必须查看的文档量。</span><span class="sxs-lookup"><span data-stu-id="11f70-173">After you run analytics on the data in review set, we perform analysis such as near duplicate detection, email threading, and themes that can help reduce the volume of documents that you have to review.</span></span> <span data-ttu-id="11f70-174">我们还生成了一个分析报告，汇总了运行分析的结果。</span><span class="sxs-lookup"><span data-stu-id="11f70-174">We also generate an Analytics reports that summarize the result of running analytics.</span></span> <span data-ttu-id="11f70-175">如前所述，运行分析还会运行 [律师-客户特权检测模型](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)。</span><span class="sxs-lookup"><span data-stu-id="11f70-175">As previously explained, running analytics also runs [the attorney-client privilege detection model](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model).</span></span>

5. <span data-ttu-id="11f70-176">**导出和下载案例数据**。</span><span class="sxs-lookup"><span data-stu-id="11f70-176">**Export and download case data**.</span></span> <span data-ttu-id="11f70-177">收集、审阅和分析案件集数据后的最后一步是，将Advanced eDiscovery导出到外部审查中，或供调查团队外部人员审阅。</span><span class="sxs-lookup"><span data-stu-id="11f70-177">A final step after collecting, reviewing, and analyzing case data is to export it out of Advanced eDiscovery for external review or for review by people outside of the investigation team.</span></span> <span data-ttu-id="11f70-178">导出数据的过程包含两个步骤。</span><span class="sxs-lookup"><span data-stu-id="11f70-178">Exporting data is a two-step process.</span></span> <span data-ttu-id="11f70-179">第一步是将数据从[](export-documents-from-review-set.md)审阅集中导出，并复制到其他 Azure 存储 位置 (Microsoft 提供的位置或由组织管理的位置) 。</span><span class="sxs-lookup"><span data-stu-id="11f70-179">The first step is to [export](export-documents-from-review-set.md) data out of the review set and copy it to a different Azure Storage location (one provided by Microsoft or one managed by your organization).</span></span> <span data-ttu-id="11f70-180">然后，Azure 存储资源管理器[将数据](download-export-jobs.md)下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="11f70-180">Then you use Azure Storage Explorer to [download](download-export-jobs.md) the data to a local computer.</span></span> <span data-ttu-id="11f70-181">除了导出的数据文件之外，导出包的 包含还包含导出报告、摘要报表和错误报告。</span><span class="sxs-lookup"><span data-stu-id="11f70-181">In addition to the exported data files, the contains of the export package also contains an export report, a summary report, and an error report.</span></span>

## <a name="advanced-ediscovery-architecture"></a><span data-ttu-id="11f70-182">Advanced eDiscovery体系结构</span><span class="sxs-lookup"><span data-stu-id="11f70-182">Advanced eDiscovery architecture</span></span>

<span data-ttu-id="11f70-183">下面的体系结构图显示了单地理位置环境和多地理位置环境中 Advanced eDiscovery 端到端工作流，以及与电子发现参考模型一致的端到端[数据流](overview-ediscovery-20.md#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)。</span><span class="sxs-lookup"><span data-stu-id="11f70-183">Here's an architecture diagram that shows the Advanced eDiscovery end-to-end workflow in a single-geo environment and in a multi-geo environment, and the end-to-end data flow that's aligned with the [Electronic Discovery Reference Model](overview-ediscovery-20.md#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model).</span></span>

<span data-ttu-id="11f70-184">[![模型海报：Advanced eDiscovery体系结构Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="11f70-184">[![Model poster: Advanced eDiscovery Architecture in Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)</span></span>

[<span data-ttu-id="11f70-185">以图像视图</span><span class="sxs-lookup"><span data-stu-id="11f70-185">View as an image</span></span>](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[<span data-ttu-id="11f70-186">下载为 PDF 文件</span><span class="sxs-lookup"><span data-stu-id="11f70-186">Download as a PDF file</span></span>](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[<span data-ttu-id="11f70-187">下载为Visio文件</span><span class="sxs-lookup"><span data-stu-id="11f70-187">Download as a Visio file</span></span>](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
