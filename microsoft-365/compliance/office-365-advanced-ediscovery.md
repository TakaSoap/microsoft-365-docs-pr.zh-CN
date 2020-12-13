---
title: 高级电子数据展示
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: fd53438a-a760-45f6-9df4-861b50161ae4
description: 了解高级电子数据展示如何帮助您分析数据、简化文档审阅和做出有效电子数据展示决策。
ms.openlocfilehash: f8ada5d377e72516ea42d8c5dc5680573daec717
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662817"
---
# <a name="advanced-ediscovery-classic"></a><span data-ttu-id="d79ee-103">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="d79ee-103">Advanced eDiscovery (classic)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d79ee-104">**高级电子数据 (经典) 将于 2020 年 12 月 31 日永久停用。**</span><span class="sxs-lookup"><span data-stu-id="d79ee-104">**Advanced eDiscovery (classic) will be permanently retired on December 31, 2020.**</span></span><br/>
> <span data-ttu-id="d79ee-105">随着我们继续投资较新版本的高级电子数据展示，我们宣布永久停用和删除高级电子数据展示或经典电子数据展示 (事例) 。</span><span class="sxs-lookup"><span data-stu-id="d79ee-105">As we continue to invest in newer versions of Advanced eDiscovery, we're announcing the permanent retirement and removal of cases and case data from Advanced eDiscovery (classic).</span></span>
> <span data-ttu-id="d79ee-106">如果仍在使用高级电子数据展示 (经典) ，也称为高级电子数据展示 *v1.0，* 请尽快将用法转换为高级电子数据展示 [v2.0](overview-ediscovery-20.md) (也称为 *Microsoft 365*) 中的高级电子数据展示解决方案。</span><span class="sxs-lookup"><span data-stu-id="d79ee-106">If you're still using Advanced eDiscovery (classic), also known as *Advanced eDiscovery v1.0*, please transition your usage to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span>  <span data-ttu-id="d79ee-107">在准备删除所有事例和事例数据时，可以通过从事例导出数据来 [存档事例数据](https://docs.microsoft.com/microsoft-365/compliance/export-results-in-advanced-ediscovery?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="d79ee-107">In preparation for the removal of all cases and case data, you can archive case data by [exporting data from a case](https://docs.microsoft.com/microsoft-365/compliance/export-results-in-advanced-ediscovery?view=o365-worldwide).</span></span>
> <span data-ttu-id="d79ee-108">高级电子数据展示 v2.0 包含高级电子数据展示 v1.0 中的类似功能，但也提供了许多新功能，如保管人管理、通信管理和审阅集。</span><span class="sxs-lookup"><span data-stu-id="d79ee-108">Advanced eDiscovery v2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="d79ee-109">若要了解有关高级电子数据展示 v1.0 之前的停用阶段，请参阅停用旧版 [电子数据展示工具](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。</span><span class="sxs-lookup"><span data-stu-id="d79ee-109">To learn more about the previous retirment phases of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span>

<span data-ttu-id="d79ee-110">使用高级电子数据展示，可以更好地了解数据并降低电子数据展示成本。</span><span class="sxs-lookup"><span data-stu-id="d79ee-110">With Advanced eDiscovery, you can better understand your data and reduce your eDiscovery costs.</span></span> <span data-ttu-id="d79ee-111">高级电子数据展示可帮助您分析非结构化数据、执行更有效的文档审阅，并做出减少电子数据展示数据的决策。</span><span class="sxs-lookup"><span data-stu-id="d79ee-111">Advanced eDiscovery helps you analyze unstructured data, perform more efficient document review, and make decisions to reduce data for eDiscovery.</span></span> <span data-ttu-id="d79ee-112">可以使用存储在 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft 365 组和 Microsoft Teams 中的数据。</span><span class="sxs-lookup"><span data-stu-id="d79ee-112">You can work with data stored in Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft 365 Groups, and Microsoft Teams.</span></span> <span data-ttu-id="d79ee-113">您可以在安全与合规中心执行电子数据展示搜索，以搜索组、单个邮箱和网站中的内容，然后使用高级电子数据展示分析搜索结果。</span><span class="sxs-lookup"><span data-stu-id="d79ee-113">You can perform an eDiscovery search in the security and compliance center to search for content in groups, individual mailboxes and sites, and then analyze the search results with Advanced eDiscovery.</span></span> <span data-ttu-id="d79ee-114">准备搜索结果以在高级电子数据展示中进行分析时，光学字符识别支持从图像提取文本。</span><span class="sxs-lookup"><span data-stu-id="d79ee-114">When you prepare search results for analysis in Advanced eDiscovery, Optical Character Recognition enables the extraction of text from images.</span></span> <span data-ttu-id="d79ee-115">此功能允许将高级电子数据展示的强大文本分析功能应用于图像文件。</span><span class="sxs-lookup"><span data-stu-id="d79ee-115">This feature allows the powerful text analytic capabilities of Advanced eDiscovery to be applied to image files.</span></span>
  
<span data-ttu-id="d79ee-116">高级电子数据展示通过识别冗余信息（具有近重复检测和电子邮件线程分析等功能）来简化并加快文档审阅过程。</span><span class="sxs-lookup"><span data-stu-id="d79ee-116">Advanced eDiscovery streamlines and speeds up the document review process by identifying redundant information with features like Near-duplicates detection and Email Thread analysis.</span></span> <span data-ttu-id="d79ee-117">相关性功能应用预测编码技术来标识相关文档。</span><span class="sxs-lookup"><span data-stu-id="d79ee-117">The Relevance feature applies predictive coding technology to identify relevant documents.</span></span> <span data-ttu-id="d79ee-118">高级电子数据展示从对示例文档的标记决策中学习，并应用统计和自学习技术来计算数据集中每个文档的相关性。</span><span class="sxs-lookup"><span data-stu-id="d79ee-118">Advanced eDiscovery learns from your tagging decisions on sample documents and applies statistical and self-learning techniques to calculate the relevance of each document in the data set.</span></span> <span data-ttu-id="d79ee-119">这样，您能够专注于关键文档、快速做出明智的案例策略决策、剔除数据以及确定审阅的优先级。</span><span class="sxs-lookup"><span data-stu-id="d79ee-119">This enables you to focus on key documents, make quick yet informed decisions on case strategy, cull data, and prioritize review.</span></span>
  
 <span data-ttu-id="d79ee-120">**为什么要使用高级电子数据展示？**</span><span class="sxs-lookup"><span data-stu-id="d79ee-120">**Why advanced eDiscovery?**</span></span> <span data-ttu-id="d79ee-121">高级电子数据展示基于 Office 365 中的一组现有电子数据展示功能构建。</span><span class="sxs-lookup"><span data-stu-id="d79ee-121">Advanced eDiscovery builds on the existing set of eDiscovery capabilities in Office 365.</span></span> <span data-ttu-id="d79ee-122">例如，您可以使用安全合规中心中的搜索功能对组织内所有内容源执行初始搜索，以确定并收集可能与特定法律案件相关的 &amp; 数据。</span><span class="sxs-lookup"><span data-stu-id="d79ee-122">For example, you can use the Search feature in the Security &amp; Compliance Center to perform an initial search of all the content sources in your organization to identify and collect the data that may be relevant to a specific legal case.</span></span> <span data-ttu-id="d79ee-123">然后，您可以通过应用高级电子数据展示的文本分析、机器学习和相关性/预测编码功能，对这些数据执行分析。</span><span class="sxs-lookup"><span data-stu-id="d79ee-123">Then you can perform analysis on that data by applying the text analytics, machine learning, and the Relevance/predictive coding capabilities of Advanced eDiscovery.</span></span> <span data-ttu-id="d79ee-124">这可以帮助您的组织快速处理数千封电子邮件、文档和其他类型的数据，以查找与特定项目最相关的项目</span><span class="sxs-lookup"><span data-stu-id="d79ee-124">This can help your organization quickly process thousands of email messages, documents, and other kinds of data to find those items that are most likely relevant to a specific</span></span> 
 
> [!NOTE]
> <span data-ttu-id="d79ee-125">高级电子数据展示需要具有高级合规性加载项的 Office 365 E3 或组织的 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="d79ee-125">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="d79ee-126">如果你没有该计划，并且想要试用高级电子数据展示，可以注册 [Office 365](https://go.microsoft.com/fwlink/p/?LinkID=698279)企业版 E5 试用版。</span><span class="sxs-lookup"><span data-stu-id="d79ee-126">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> <span data-ttu-id="d79ee-127">大小写。</span><span class="sxs-lookup"><span data-stu-id="d79ee-127">case.</span></span> <span data-ttu-id="d79ee-128">然后，可以将减少的数据集从 Office 365 导出以进一步查看。</span><span class="sxs-lookup"><span data-stu-id="d79ee-128">The reduced data set can then be exported out of Office 365 for further review.</span></span> 
  
## <a name="get-started"></a><span data-ttu-id="d79ee-129">入门</span><span class="sxs-lookup"><span data-stu-id="d79ee-129">Get started</span></span>

<span data-ttu-id="d79ee-130">开始使用高级电子数据展示的最快方式是在安全 & 合规中心创建案例并准备搜索结果，在高级电子数据展示中加载这些结果，然后运行 Express 分析来分析该案例数据，然后导出结果进行外部审阅。</span><span class="sxs-lookup"><span data-stu-id="d79ee-130">The quickest way to get started with Advanced eDiscovery is to create a case and prepare search results in Security & Compliance Center, load those results in Advanced eDiscovery, and then run Express analysis to analyze that case data and then export the results for external review.</span></span>
  
- <span data-ttu-id="d79ee-131">[快速概览](quick-setup-for-advanced-ediscovery.md) 高级电子数据展示工作流</span><span class="sxs-lookup"><span data-stu-id="d79ee-131">[Get a quick overview](quick-setup-for-advanced-ediscovery.md) of the Advanced eDiscovery workflow</span></span> 
    
- <span data-ttu-id="d79ee-132">[使用安全与](set-up-users-and-cases-in-advanced-ediscovery.md) 合规中心创建事例、分配电子数据展示权限和添加事例成员，为高级电子数据展示设置&事例</span><span class="sxs-lookup"><span data-stu-id="d79ee-132">[Set up users and cases](set-up-users-and-cases-in-advanced-ediscovery.md) for Advanced eDiscovery by creating a case, assigning eDiscovery permissions, and adding case members, all by using the Security & Compliance Center</span></span> 
    
- <span data-ttu-id="d79ee-133">[在高级电子数据展示中](prepare-data-for-advanced-ediscovery.md) 准备搜索数据并加载到案例</span><span class="sxs-lookup"><span data-stu-id="d79ee-133">[Prepare and load search data](prepare-data-for-advanced-ediscovery.md) in to the case in Advanced eDiscovery</span></span> 
    
- <span data-ttu-id="d79ee-134">[将非 Office 365](import-non-office-365-data-into-advanced-ediscovery.md) 数据加载到案例以在高级电子数据展示中对其进行分析</span><span class="sxs-lookup"><span data-stu-id="d79ee-134">[Load non-Office 365 data](import-non-office-365-data-into-advanced-ediscovery.md) in to a case to analyze it in Advanced eDiscovery</span></span> 
    
- <span data-ttu-id="d79ee-135">[使用快速](use-express-analysis-in-advanced-ediscovery.md) 分析快速分析案例数据，然后轻松导出结果</span><span class="sxs-lookup"><span data-stu-id="d79ee-135">[Use Express analysis](use-express-analysis-in-advanced-ediscovery.md) to quickly analyze the data in a case and then easily export the results</span></span> 
    
## <a name="analyze-data"></a><span data-ttu-id="d79ee-136">分析数据</span><span class="sxs-lookup"><span data-stu-id="d79ee-136">Analyze data</span></span>

<span data-ttu-id="d79ee-137">在高级电子数据展示中将搜索数据加载到案例后，你将使用分析模块开始分析它。</span><span class="sxs-lookup"><span data-stu-id="d79ee-137">After search data is loaded into the case in Advanced eDiscovery, you'll use the Analyze module to start analyzing it.</span></span> <span data-ttu-id="d79ee-138">分析过程的第一部分包括将文件组织成一组唯一文件、重复项和近 (也作为文档相似性) 。</span><span class="sxs-lookup"><span data-stu-id="d79ee-138">The first part of the analysis process consists of organizing files into groups of unique files, duplicates, and near-duplicates (also know as document similarity).</span></span> <span data-ttu-id="d79ee-139">然后，将数据重新组织到电子邮件线程和主题的分层结构组中，并（可选）设置忽略文本筛选器以从分析中排除某些文本。</span><span class="sxs-lookup"><span data-stu-id="d79ee-139">Then you organize the data again into hierarchically structured groups of email threads and themes and, optionally, set ignore text filters to exclude certain text from analysis.</span></span> <span data-ttu-id="d79ee-140">然后运行分析并查看结果。</span><span class="sxs-lookup"><span data-stu-id="d79ee-140">Then you run the analysis and view the results.</span></span>
  
- <span data-ttu-id="d79ee-141">[了解文档相似性](understand-document-similarity-in-advanced-ediscovery.md) ，以准备分析高级电子数据展示中的数据</span><span class="sxs-lookup"><span data-stu-id="d79ee-141">[Learn about document similarity](understand-document-similarity-in-advanced-ediscovery.md) to prepare you for analyzing data in Advanced eDiscovery</span></span> 
    
- <span data-ttu-id="d79ee-142">[设置接近重复](set-analyze-options-in-advanced-ediscovery.md) 项、主题和电子邮件线程的选项，然后运行分析模块</span><span class="sxs-lookup"><span data-stu-id="d79ee-142">[Set up the options](set-analyze-options-in-advanced-ediscovery.md) for near-duplicates, themes, and email threading and then run the Analyze module</span></span> 
    
- <span data-ttu-id="d79ee-143">[设置"忽略文本"筛选器](set-ignore-text-in-advanced-ediscovery.md) 以从分析中排除文本和文本字符串;运行相关性分析时，这些筛选器还将忽略文本</span><span class="sxs-lookup"><span data-stu-id="d79ee-143">[Set up Ignore Text filters](set-ignore-text-in-advanced-ediscovery.md) to exclude text and text strings from being analyzed; these filters will also ignore text when you run Relevance analysis</span></span> 
    
- <span data-ttu-id="d79ee-144">[查看分析](view-analyze-results-in-advanced-ediscovery.md) 过程的结果</span><span class="sxs-lookup"><span data-stu-id="d79ee-144">[View the results](view-analyze-results-in-advanced-ediscovery.md) of the analysis process</span></span> 
    
- <span data-ttu-id="d79ee-145">[配置分析](set-analyze-advanced-settings-in-advanced-ediscovery.md) 过程的高级设置</span><span class="sxs-lookup"><span data-stu-id="d79ee-145">[Configure advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for the analysis process</span></span> 
    
## <a name="set-up-relevance-training"></a><span data-ttu-id="d79ee-146">设置相关性培训</span><span class="sxs-lookup"><span data-stu-id="d79ee-146">Set up Relevance training</span></span>

<span data-ttu-id="d79ee-147">通过高级电子数据展示 (相关性) 预测编码功能，你可以根据你正在查找的内容对系统进行培训，方法为 (做出有关某些内容是否相关的决策) 一小组文档。</span><span class="sxs-lookup"><span data-stu-id="d79ee-147">Predictive coding (called Relevance) in Advanced eDiscovery lets you train the system on what you're looking for by letting you to make decisions (about whether something is relevant or not) on a small set of documents.</span></span>
  
- <span data-ttu-id="d79ee-148">[了解如何设置相关性培训](manage-relevance-setup-in-advanced-ediscovery.md) 、标记与案例相关的文件以及定义案例问题</span><span class="sxs-lookup"><span data-stu-id="d79ee-148">[Learn about setting up Relevance training](manage-relevance-setup-in-advanced-ediscovery.md) , tagging files that are relevant to a case, and defining case issues</span></span> 
    
- <span data-ttu-id="d79ee-149">[定义案例](define-issues-and-assign-users.md) 问题并将每个问题分配给将培训文件的用户</span><span class="sxs-lookup"><span data-stu-id="d79ee-149">[Define case issues](define-issues-and-assign-users.md) and assign each issue to a user who will train the files</span></span> 
    
- <span data-ttu-id="d79ee-150">[将导入的文件添加到将](set-up-loads-to-add-imported-files.md) 添加到相关性培训的当前负载或新负载中。</span><span class="sxs-lookup"><span data-stu-id="d79ee-150">[Add imported files to current or new load](set-up-loads-to-add-imported-files.md) that will be added to the Relevance training.</span></span> <span data-ttu-id="d79ee-151">负载是添加到案例，然后用于相关性培训的新文件批处理</span><span class="sxs-lookup"><span data-stu-id="d79ee-151">A load is a new batch of files that are added to a case and then used for Relevance training</span></span> 
    
- <span data-ttu-id="d79ee-152">[定义可添加到](define-highlighted-keywords-and-advanced-options.md) 相关性培训的突出显示关键字。</span><span class="sxs-lookup"><span data-stu-id="d79ee-152">[Define highlighted keywords](define-highlighted-keywords-and-advanced-options.md) that can be added to the Relevance training.</span></span> <span data-ttu-id="d79ee-153">这可帮助你更好地识别与案例相关的文件</span><span class="sxs-lookup"><span data-stu-id="d79ee-153">This helps you better identify files that are relevant to a case</span></span> 
    
## <a name="run-the-relevance-module"></a><span data-ttu-id="d79ee-154">运行相关性模块</span><span class="sxs-lookup"><span data-stu-id="d79ee-154">Run the Relevance module</span></span>

<span data-ttu-id="d79ee-155">设置培训后，即可运行相关性模块并评估培训设置的有效性。</span><span class="sxs-lookup"><span data-stu-id="d79ee-155">After set up training, you're ready to run the Relevance module and assess the effectiveness of the training settings.</span></span> <span data-ttu-id="d79ee-156">这可产生相关性排名，帮助你确定是否需要执行其他培训，或者是否已准备好开始标记与案例相关的文件。</span><span class="sxs-lookup"><span data-stu-id="d79ee-156">This results in a relevance ranking that helps you decide if you need to perform additional training or if you're ready to start tagging files as relevant to your case.</span></span>
  
- <span data-ttu-id="d79ee-157">[了解相关性过程以及](use-relevance-in-advanced-ediscovery.md) 基于示例文件集的评估、标记、跟踪和重新设置的迭代过程</span><span class="sxs-lookup"><span data-stu-id="d79ee-157">[Learn about the Relevance process](use-relevance-in-advanced-ediscovery.md) and the iterative process of assessment, tagging, tracking, and retraining based on sample set of files</span></span> 
    
- <span data-ttu-id="d79ee-158">[了解评估](assessment-in-relevance-in-advanced-ediscovery.md) ，其中熟悉案例的专家会审阅一组案例文件并确定相关性培训的有效性</span><span class="sxs-lookup"><span data-stu-id="d79ee-158">[Learn about assessment](assessment-in-relevance-in-advanced-ediscovery.md) , where an expert familiar with the case reviews a set of case files and determines the effectiveness of the Relevance training</span></span> 
    
- <span data-ttu-id="d79ee-159">[评估案例文件](tagging-and-assessment-in-advanced-ediscovery.md) 以计算 (设置) 的"丰富度"，然后将文件标记为与你的案例相关或不相关。</span><span class="sxs-lookup"><span data-stu-id="d79ee-159">[Assess case files](tagging-and-assessment-in-advanced-ediscovery.md) to calculate the effectiveness (called  \*richness) of training settings, and then tag files as relevant or not relevant to your case.</span></span> <span data-ttu-id="d79ee-160">这可以帮助您确定当前培训是否足够，或者您是否应调整培训设置。</span><span class="sxs-lookup"><span data-stu-id="d79ee-160">This helps you determine if the current training is sufficient or if you should adjust the training settings.</span></span> 
    
- <span data-ttu-id="d79ee-161">[在评估完成后执行](tagging-and-relevance-training-in-advanced-ediscovery.md) 相关性培训，然后再次将文件标记为与为案例定义的问题相关或不相关</span><span class="sxs-lookup"><span data-stu-id="d79ee-161">[Perform the relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md) after assessment is complete, and then once again tag files as relevant or not relevant to the issues you've defined for the case</span></span> 
    
- <span data-ttu-id="d79ee-162">[跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md) 过程，以确定相关性培训是否已实现评估目标 (称为\*稳定培训状态) 是否需要更多培训;还可以查看每个案例问题的相关性结果</span><span class="sxs-lookup"><span data-stu-id="d79ee-162">[Track the Relevance analysis](track-relevance-analysis-in-advanced-ediscovery.md) process to determine if Relevance training has achieved your assessment target (known as a  \*stable training status) or whether more training is needed; you can also view the Relevance results for each case issue</span></span> 
    
- <span data-ttu-id="d79ee-163">[根据相关性分析做出决策](decision-based-on-the-results-in-advanced-ediscovery.md) ，以确定可导出供审阅的结果案例文件集的大小</span><span class="sxs-lookup"><span data-stu-id="d79ee-163">[Make decisions based on Relevance analysis](decision-based-on-the-results-in-advanced-ediscovery.md) to determine the size of the resulting set of case files that can be exported for review</span></span> 
    
- <span data-ttu-id="d79ee-164">[测试相关性分析的质量](test-relevance-analysis-in-advanced-ediscovery.md) ，以验证在相关性过程中做出剔除决策</span><span class="sxs-lookup"><span data-stu-id="d79ee-164">[Test the quality of the Relevance analysis](test-relevance-analysis-in-advanced-ediscovery.md) to validate the culling decisions made during the Relevance process</span></span> 
    
## <a name="export-results"></a><span data-ttu-id="d79ee-165">导出结果</span><span class="sxs-lookup"><span data-stu-id="d79ee-165">Export results</span></span>

<span data-ttu-id="d79ee-166">在高级电子数据展示中分析案例数据的最后一步是导出分析结果以用于外部审阅。</span><span class="sxs-lookup"><span data-stu-id="d79ee-166">The final step in analyzing case data in Advanced eDiscovery is to export results of the analysis for external review.</span></span>
  
- [<span data-ttu-id="d79ee-167">了解如何导出案例数据</span><span class="sxs-lookup"><span data-stu-id="d79ee-167">Learn about exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="d79ee-168">导出事例数据</span><span class="sxs-lookup"><span data-stu-id="d79ee-168">Export case data</span></span>](export-results-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="d79ee-169">查看批处理历史记录和导出过去的结果</span><span class="sxs-lookup"><span data-stu-id="d79ee-169">View batch history and export past results</span></span>](view-batch-history-and-export-past-results.md)
    
- [<span data-ttu-id="d79ee-170">导出报告字段</span><span class="sxs-lookup"><span data-stu-id="d79ee-170">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
    
## <a name="other-advanced-ediscovery-tools"></a><span data-ttu-id="d79ee-171">其他高级电子数据展示工具</span><span class="sxs-lookup"><span data-stu-id="d79ee-171">Other Advanced eDiscovery tools</span></span>

<span data-ttu-id="d79ee-172">高级电子数据展示提供了除分析案例数据、相关性分析和导出数据之外的其他工具和功能。</span><span class="sxs-lookup"><span data-stu-id="d79ee-172">Advanced eDiscovery provides additional tools and capabilities beyond analyzing case data, relevance analysis, and exporting data.</span></span>
  
- [<span data-ttu-id="d79ee-173">运行高级电子数据展示报告</span><span class="sxs-lookup"><span data-stu-id="d79ee-173">Run Advanced eDiscovery reports</span></span>](run-reports-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="d79ee-174">定义案例和租户设置</span><span class="sxs-lookup"><span data-stu-id="d79ee-174">Define case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="d79ee-175">高级电子数据展示实用程序</span><span class="sxs-lookup"><span data-stu-id="d79ee-175">Advanced eDiscovery utilities</span></span>](use-advanced-ediscovery-utilities.md)
