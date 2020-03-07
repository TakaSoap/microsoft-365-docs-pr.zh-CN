---
title: 为 Office 365 高级电子数据展示准备搜索结果
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: 了解如何在 Office 365 的 Security & 合规性中心中准备内容搜索结果，以使用高级电子数据展示工具进行进一步分析。
ms.openlocfilehash: 01a09da78198c31ff88b0e539ae9b149b2fbdd02
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557852"
---
# <a name="prepare-search-results-for-advanced-ediscovery-classic"></a><span data-ttu-id="b1177-103">准备高级电子数据展示的搜索结果（经典）</span><span class="sxs-lookup"><span data-stu-id="b1177-103">Prepare search results for Advanced eDiscovery (classic)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1177-104">随着我们继续在较新版本的高级电子数据展示中进行投资，我们宣布退出 Office 365 高级电子数据展示，也称为*高级电子数据展示（经典）* 或*高级电子数据展示 v1.0 1.0*。</span><span class="sxs-lookup"><span data-stu-id="b1177-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Office 365 Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="b1177-105">如果仍在使用高级电子数据展示 v1.0，请尽快切换到[高级电子数据展示 v2.0](overview-ediscovery-20.md)（也称为 *Microsoft 365 中的高级电子数据展示解决方案*）。</span><span class="sxs-lookup"><span data-stu-id="b1177-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="b1177-106">高级电子数据展示 2.0 不仅包含高级电子数据展示 v1.0 中提供的类似功能，还提供了许多新功能，如保管人管理、沟通管理和审阅集。</span><span class="sxs-lookup"><span data-stu-id="b1177-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="b1177-107">若要了解停用高级电子数据展示 v1.0 的详细信息，请参阅[停用旧式电子数据展示工具](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。</span><span class="sxs-lookup"><span data-stu-id="b1177-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 

<span data-ttu-id="b1177-108">成功运行与安全 & 合规中心中的电子数据展示事例关联的搜索后，您可以使用 Office 365 高级电子数据展示为进一步分析准备搜索结果，这样您可以分析大型的非结构化数据集，并减少与合法事例相关的数据量。</span><span class="sxs-lookup"><span data-stu-id="b1177-108">After a search that's associated with an eDiscovery case in the Security & Compliance Center is successfully run, you can prepare the search results for further analysis with Office 365 Advanced eDiscovery, which lets you analyze large, unstructured data sets and reduce the amount of data that's relevant to a legal case.</span></span> <span data-ttu-id="b1177-109">高级电子数据展示功能包括：</span><span class="sxs-lookup"><span data-stu-id="b1177-109">Advanced eDiscovery features include:</span></span>
  
- <span data-ttu-id="b1177-110">**光学字符识别**-当您为高级电子数据展示准备搜索结果时，光学字符识别（OCR）功能会自动从图像中提取文本，并将其包含在加载到高级电子数据展示的搜索结果中进行分析。</span><span class="sxs-lookup"><span data-stu-id="b1177-110">**Optical character recognition** - When you prepare search results for Advanced eDiscovery, optical character recognition (OCR) functionality automatically extracts text from images, and includes this with the search results that are loaded in to Advanced eDiscovery for analysis.</span></span> <span data-ttu-id="b1177-111">稀疏文件、电子邮件附件和嵌入图像支持 OCR。</span><span class="sxs-lookup"><span data-stu-id="b1177-111">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="b1177-112">这使您可以将高级电子数据展示的文本分析功能（临近重复项、电子邮件线程、主题和预测编码）应用于图像文件中的文本内容。</span><span class="sxs-lookup"><span data-stu-id="b1177-112">This allows you to apply the text analytic capabilities of Advanced eDiscovery (near-duplicates, email threading, themes, and predictive coding) to the text content in image files.</span></span> <span data-ttu-id="b1177-113">高级电子数据展示 OCR 支持图像文件的以下格式：</span><span class="sxs-lookup"><span data-stu-id="b1177-113">Advanced eDiscovery OCR supports the following formats for image files:</span></span>

    - <span data-ttu-id="b1177-114">GIF</span><span class="sxs-lookup"><span data-stu-id="b1177-114">GIF</span></span>
    - <span data-ttu-id="b1177-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="b1177-115">JPEG</span></span>
    - <span data-ttu-id="b1177-116">.JPG</span><span class="sxs-lookup"><span data-stu-id="b1177-116">JPG</span></span>
    - <span data-ttu-id="b1177-117">PNG</span><span class="sxs-lookup"><span data-stu-id="b1177-117">PNG</span></span>
    - <span data-ttu-id="b1177-118">TIFF</span><span class="sxs-lookup"><span data-stu-id="b1177-118">TIFF</span></span>
    
- <span data-ttu-id="b1177-119">**接近重复的检测**-使您能够更高效地构建数据审核，这样一人可以查看一组相似的文档。</span><span class="sxs-lookup"><span data-stu-id="b1177-119">**Near-duplicate detection** - Lets you structure your data review more efficiently, so one person reviews a group of similar documents.</span></span> <span data-ttu-id="b1177-120">这有助于防止多个审阅者查看同一文档的不同版本。</span><span class="sxs-lookup"><span data-stu-id="b1177-120">This helps prevent multiple reviewers from having to view different versions of the same document.</span></span> 
    
- <span data-ttu-id="b1177-121">**电子邮件线程处理**-帮助您标识电子邮件线程中的唯一邮件，以便只关注每封邮件中的新信息。</span><span class="sxs-lookup"><span data-stu-id="b1177-121">**Email threading** - Helps you identify the unique messages in an email thread so you can focus on only the new information in each message.</span></span> <span data-ttu-id="b1177-122">在电子邮件线索中，第二封邮件包含第一封邮件。</span><span class="sxs-lookup"><span data-stu-id="b1177-122">In an email thread, the second message contains the first message.</span></span> <span data-ttu-id="b1177-123">同样，后续邮件也包含以前的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="b1177-123">Likewise, later messages contain all the previous messages.</span></span> <span data-ttu-id="b1177-124">电子邮件线程消除了在电子邮件线程中完整查看每封邮件的需求。</span><span class="sxs-lookup"><span data-stu-id="b1177-124">Email threading removes the need to review every message in its entirety in an email thread.</span></span> 
    
- <span data-ttu-id="b1177-125">**主题**-帮助您获得有关数据的有价值的见解，而不仅仅是关键字搜索统计信息。</span><span class="sxs-lookup"><span data-stu-id="b1177-125">**Themes** - Help you get valuable insight about your data beyond just keyword search statistics.</span></span> <span data-ttu-id="b1177-126">主题帮助调查通过对相关文档进行分组，以便您可以在上下文中查看文档。</span><span class="sxs-lookup"><span data-stu-id="b1177-126">Themes help investigations by grouping related documents so you can look at the documents in context.</span></span> <span data-ttu-id="b1177-127">使用主题时，您可以查看一组文档的相关主题，确定任何重叠，然后确定相关数据的各个部分。</span><span class="sxs-lookup"><span data-stu-id="b1177-127">When using themes, you can view the related themes for a set of documents, determine any overlap, and then identify cross-sections of related data.</span></span> 
    
- <span data-ttu-id="b1177-128">**预测编码**-通过允许您在一小组文档上做出决定（有关是否有相关的信息），让您对系统进行培训。</span><span class="sxs-lookup"><span data-stu-id="b1177-128">**Predictive coding** - Lets you train the system on what you're looking for, by allowing you to make decisions (about whether something is relevant or not) on a small set of documents.</span></span> <span data-ttu-id="b1177-129">然后，高级电子数据展示在分析数据集中的所有文档时应用该学习（基于您的指导）。</span><span class="sxs-lookup"><span data-stu-id="b1177-129">Advanced eDiscovery then applies that learning (based on your guidance) when analyzing all of the documents in the data set.</span></span> <span data-ttu-id="b1177-130">根据该学习，高级电子数据展示会提供相关性排名，以便您可以根据最可能与案例相关的文档来决定要查看哪些文档。</span><span class="sxs-lookup"><span data-stu-id="b1177-130">Based on that learning, Advanced eDiscovery provides a relevance ranking so you can decide which documents to review based on what document are the most likely to be relevant to the case.</span></span> 
    
- <span data-ttu-id="b1177-131">**导出数据以供审阅应用程序**-在完成分析并减小数据集后，您可以从高级电子数据展示和 Office 365 导出数据。</span><span class="sxs-lookup"><span data-stu-id="b1177-131">**Exporting data for review applications**  - You can export data from Advanced eDiscovery and Office 365 after you've completed your analysis and reduced the data set.</span></span> <span data-ttu-id="b1177-132">导出包包含一个 CSV 文件，其中包含导出的内容和分析元数据中的属性。</span><span class="sxs-lookup"><span data-stu-id="b1177-132">The export package includes a CSV file that contains the properties from the exported content and analytics metadata.</span></span> <span data-ttu-id="b1177-133">然后，可以将此导出包导入到电子数据展示审阅应用程序中。</span><span class="sxs-lookup"><span data-stu-id="b1177-133">This export package can then be imported to an eDiscovery review application.</span></span> 
    
## <a name="before-you-begin"></a><span data-ttu-id="b1177-134">准备工作</span><span class="sxs-lookup"><span data-stu-id="b1177-134">Before you begin</span></span>

- <span data-ttu-id="b1177-135">若要使用高级电子数据展示分析用户的数据，必须为用户（数据管理员）分配 Office 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="b1177-135">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="b1177-136">或者，可以为具有 Office 365 E1 或 E3 许可证的用户分配高级电子数据展示独立许可证。</span><span class="sxs-lookup"><span data-stu-id="b1177-136">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="b1177-137">分配给案例并使用高级电子数据展示分析数据的管理员和合规性监察官不需要 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="b1177-137">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="b1177-138">您必须是电子数据展示管理器或安全 & 合规性中心中的电子数据展示管理员才能为高级电子数据展示准备搜索结果。</span><span class="sxs-lookup"><span data-stu-id="b1177-138">You have to be an eDiscovery Manager or an eDiscovery Administrator in the Security & Compliance Center to prepare search results for Advanced eDiscovery.</span></span> <span data-ttu-id="b1177-139">电子数据展示经理是电子数据展示管理员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="b1177-139">An eDiscovery Manager is a member of the eDiscovery Manager role group.</span></span> <span data-ttu-id="b1177-140">电子数据展示管理员也是电子数据展示管理员角色组的成员，但该成员已分配有其他电子数据展示权限。</span><span class="sxs-lookup"><span data-stu-id="b1177-140">An eDiscovery Administrator is also member of the eDiscovery Manager role group, but has been assigned additional eDiscovery privileges.</span></span> <span data-ttu-id="b1177-141">有关分配电子数据展示管理员权限的说明，请参阅[电子数据展示事例](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)中的步骤1。</span><span class="sxs-lookup"><span data-stu-id="b1177-141">For instructions about assigning eDiscovery Administrator permissions, see Step 1 in [eDiscovery cases](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a><span data-ttu-id="b1177-142">步骤1：为高级电子数据展示准备搜索结果</span><span class="sxs-lookup"><span data-stu-id="b1177-142">Step 1: Prepare search results for Advanced eDiscovery</span></span>

<span data-ttu-id="b1177-143">您可以准备与电子数据展示事例相关联的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="b1177-143">You can prepare the results of a search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="b1177-144">在为高级电子数据展示准备搜索结果时，数据将上传并临时存储在 Microsoft 云中的唯一 Windows Azure 存储区域中。</span><span class="sxs-lookup"><span data-stu-id="b1177-144">When you prepare search results for Advanced eDiscovery, the data is uploaded and temporarily stored in a unique Windows Azure storage area in the Microsoft cloud.</span></span> <span data-ttu-id="b1177-145">在这种情况中，OCR 功能会从搜索结果中的图像中提取文本。</span><span class="sxs-lookup"><span data-stu-id="b1177-145">It's at this point that the OCR functionality extracts text from images in the search results.</span></span> <span data-ttu-id="b1177-146">在[第2步](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery)中，此文本和其他搜索结果数据将加载到高级电子数据展示的案例中。</span><span class="sxs-lookup"><span data-stu-id="b1177-146">In [Step 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery), this text and the other search results data is loaded in to the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="b1177-147">在安全 & 合规性中心中，单击 "**电子数据** \>展示**电子数据**展示" 以显示组织中的案例列表。</span><span class="sxs-lookup"><span data-stu-id="b1177-147">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="b1177-148">在高级电子数据展示中，单击要为分析准备搜索结果的事例旁边的 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="b1177-148">Click **Open** next to the case that you want to prepare search results for analysis in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="b1177-149">在该案例的**主页**上，单击 "**搜索**"，然后选择 "搜索"。</span><span class="sxs-lookup"><span data-stu-id="b1177-149">On the **Home** page for the case, click **Search**, and then select the search.</span></span>
    
4. <span data-ttu-id="b1177-150">在详细信息窗格中，在 "**使用高级电子数据展示分析结果**" 下，单击 "**准备结果以供分析**"。</span><span class="sxs-lookup"><span data-stu-id="b1177-150">In the details pane, under **Analyze results with Advanced eDiscovery**, click **Prepare results for analysis**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b1177-151">如果搜索结果超过 7 天，将会提示你更新搜索结果。</span><span class="sxs-lookup"><span data-stu-id="b1177-151">If the search results are older than 7 days, you will be prompted to update the search results.</span></span> 
  
5. <span data-ttu-id="b1177-152">在“准备进行分析的结果”\*\*\*\* 页面上，请执行以下操作： </span><span class="sxs-lookup"><span data-stu-id="b1177-152">On the **Prepare results for analysis** page, do the following:</span></span> 
    
    - <span data-ttu-id="b1177-153">选择为高级电子数据展示中的分析准备已编制索引的项目、已编制索引和未编制索引的项目或仅索引项目。</span><span class="sxs-lookup"><span data-stu-id="b1177-153">Choose to prepare indexed items, indexed and unindexed items, or only unindexed items for analysis in Advanced eDiscovery.</span></span>
    
    - <span data-ttu-id="b1177-154">选择是否包含在 SharePoint 上找到的符合搜索条件的所有版本的文档。</span><span class="sxs-lookup"><span data-stu-id="b1177-154">Choose whether to include all versions of documents found on SharePoint that met the search criteria.</span></span> <span data-ttu-id="b1177-155">仅当搜索的内容源包含网站时才会显示此选项。</span><span class="sxs-lookup"><span data-stu-id="b1177-155">This option appears only if the content sources for the search includes sites.</span></span>
    
    - <span data-ttu-id="b1177-156">指定在准备过程完成且数据已准备好在高级电子数据展示中进行处理时，您是否希望向某人发送（或复制）通知邮件。</span><span class="sxs-lookup"><span data-stu-id="b1177-156">Specify whether you want a notification message sent (or copied) to a person when the preparation process is completed and the data is ready to be processed in Advanced eDiscovery.</span></span>
    
6. <span data-ttu-id="b1177-157">单击“准备”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b1177-157">Click **Prepare**.</span></span>
    
    <span data-ttu-id="b1177-158">搜索结果已准备好使用高级电子数据展示进行分析。</span><span class="sxs-lookup"><span data-stu-id="b1177-158">The search results are prepared for analysis with Advanced eDiscovery.</span></span>
    
7. <span data-ttu-id="b1177-159">在 "详细信息" 窗格中，单击 "**检查准备状态**" 以显示有关准备过程的信息。</span><span class="sxs-lookup"><span data-stu-id="b1177-159">In the details pane, click **Check preparation status** to display information about the preparation process.</span></span> <span data-ttu-id="b1177-160">准备过程完成后，可以转到高级电子数据展示中的案例以处理数据以进行分析。</span><span class="sxs-lookup"><span data-stu-id="b1177-160">When the preparation process is finished, you can go to the case in Advanced eDiscovery to process the data for analysis.</span></span> 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a><span data-ttu-id="b1177-161">步骤2：将搜索结果数据添加到高级电子数据展示中的事例</span><span class="sxs-lookup"><span data-stu-id="b1177-161">Step 2: Add the search results data to the case in Advanced eDiscovery</span></span>
<span data-ttu-id="b1177-162"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="b1177-162"><a name="step2"> </a></span></span>

<span data-ttu-id="b1177-163">准备完成后，下一步是转到高级电子数据展示，并将搜索结果数据（已上载到 Microsoft 云中的 Azure 存储区域）发送到高级电子数据展示中的情况。</span><span class="sxs-lookup"><span data-stu-id="b1177-163">When the preparation is finished, the next step is to go to Advanced eDiscovery and load the search results data (which have been uploaded to an Azure storage area in the Microsoft cloud ) to the case in Advanced eDiscovery.</span></span> <span data-ttu-id="b1177-164">如前所述，若要访问高级电子数据展示，您必须是安全 & 合规性中心中的电子数据展示管理员或高级电子数据展示中的管理员。</span><span class="sxs-lookup"><span data-stu-id="b1177-164">As previously explained, to access Advanced eDiscovery you have to be an eDiscovery Administrator in the Security & Compliance Center or an administrator in Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b1177-165">根据电子数据展示搜索结果的大小不同，在高级电子数据展示中可将来自安全性 & 合规中心的数据用于添加到高级电子数据展示中的事例的时间。</span><span class="sxs-lookup"><span data-stu-id="b1177-165">The time it takes for the data from the Security & Compliance Center to be available to add to a case in Advanced eDiscovery varies, depending on the size of the results from the eDiscovery search.</span></span> 
  
1. <span data-ttu-id="b1177-166">在安全 & 合规性中心中，单击 "**电子数据** \>展示**电子数据**展示" 以显示组织中的案例列表。</span><span class="sxs-lookup"><span data-stu-id="b1177-166">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="b1177-167">在高级电子数据展示中，单击要在其中将数据加载到的事例旁边的 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="b1177-167">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="b1177-168">在此案件集的“主页”\*\*\*\* 上，单击“高级电子数据展示”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b1177-168">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![单击 "切换到高级电子数据展示" 以在高级电子数据展示中打开事例](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="b1177-170">将显示 "**连接到高级电子数据展示**进度栏"。</span><span class="sxs-lookup"><span data-stu-id="b1177-170">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="b1177-171">当您连接到高级电子数据展示时，会在 "设置" 页上显示一个容器列表。</span><span class="sxs-lookup"><span data-stu-id="b1177-171">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![事例显示在高级电子数据展示](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="b1177-173">这些容器代表您在步骤1中的高级电子数据展示中准备进行分析的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="b1177-173">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="b1177-174">请注意，在安全 & 合规中心的情况下，容器名称与搜索的名称相同。</span><span class="sxs-lookup"><span data-stu-id="b1177-174">Note that the name of the container has the same name as the search in the case in the Security & Compliance Center.</span></span> <span data-ttu-id="b1177-175">列表中的容器是您准备的容器。</span><span class="sxs-lookup"><span data-stu-id="b1177-175">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="b1177-176">如果其他用户为高级电子数据展示准备了搜索结果，则相应的容器将不会包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="b1177-176">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
4. <span data-ttu-id="b1177-177">若要在高级电子数据展示中将容器中的搜索结果数据加载到事例中，请选择一个容器，然后单击 "**处理**"。</span><span class="sxs-lookup"><span data-stu-id="b1177-177">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="b1177-178">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b1177-178">Next steps</span></span>

<span data-ttu-id="b1177-179">将电子数据展示搜索的结果添加到事例之后，下一步是使用高级电子数据展示工具来分析数据，并确定对特定法律案例做出响应的内容。</span><span class="sxs-lookup"><span data-stu-id="b1177-179">After the results of an eDiscovery search are added to a case, the next step is to use the Advanced eDiscovery tools to analyze the data and identify the content that's responsive to a specific legal case.</span></span> <span data-ttu-id="b1177-180">有关使用高级电子数据展示的信息，请参阅[高级电子数据展示（经典）](office-365-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="b1177-180">For information about using Advanced eDiscovery, see [Advanced eDiscovery (classic)](office-365-advanced-ediscovery.md).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="b1177-181">更多信息</span><span class="sxs-lookup"><span data-stu-id="b1177-181">More information</span></span>

<span data-ttu-id="b1177-182">在准备高级电子数据展示中的分析时，搜索结果中包含的任何 RMS 加密的电子邮件都将被解密。</span><span class="sxs-lookup"><span data-stu-id="b1177-182">Any RMS-encrypted email messages that are included in the search results will be decrypted when you prepare them for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="b1177-183">默认情况下，将为电子数据展示管理器角色组的成员启用此解密功能。</span><span class="sxs-lookup"><span data-stu-id="b1177-183">This decryption capability is enabled by default for members of the eDiscovery Manager role group.</span></span> <span data-ttu-id="b1177-184">这是因为将 RMS 解密管理角色分配给此角色组。</span><span class="sxs-lookup"><span data-stu-id="b1177-184">This is because the RMS Decrypt management role is assigned to this role group.</span></span> <span data-ttu-id="b1177-185">请记住以下有关解密电子邮件的事项：</span><span class="sxs-lookup"><span data-stu-id="b1177-185">Keep the following things in mind about decrypting email messages:</span></span>
  
- <span data-ttu-id="b1177-186">目前，此解密功能不包括 SharePoint 和 OneDrive for business 网站中的加密内容。</span><span class="sxs-lookup"><span data-stu-id="b1177-186">Currently, this decryption capability doesn't include encrypted content from SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="b1177-187">导出 RMS 加密的电子邮件时，只会对其进行解密。</span><span class="sxs-lookup"><span data-stu-id="b1177-187">Only RMS-encrypted email messages will be decrypted when you export them.</span></span>
    
- <span data-ttu-id="b1177-188">如果 RMS 加密的电子邮件包含同样加密的附件（如文档或其他电子邮件），则仅对顶级电子邮件进行解密。</span><span class="sxs-lookup"><span data-stu-id="b1177-188">If an RMS-encrypted email message has an attachment (such as a document or another email message) that's also encrypted, only the top-level email message will be decrypted.</span></span>
    
- <span data-ttu-id="b1177-189">如果需要防止某人在为高级电子数据展示中的分析准备搜索结果时对受 RMS 加密的邮件进行解密，则必须创建自定义角色组（通过复制内置的电子数据展示管理器角色组），然后删除 RMS从自定义角色组中解密管理角色。</span><span class="sxs-lookup"><span data-stu-id="b1177-189">If you need to prevent someone from decrypting RMS-encrypted messages when preparing search results for analysis in Advanced eDiscovery, you'll have to create a custom role group (by copying the built-in eDiscovery Manager role group) and then remove the RMS Decrypt management role from the custom role group.</span></span> <span data-ttu-id="b1177-190">然后，将您不想将邮件解密的人员添加为自定义角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="b1177-190">Then add the person who you don't want to decrypt messages as a member of the custom role group.</span></span>
