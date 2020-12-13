---
title: 运行进程模块，在高级电子数据展示中加载数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 了解如何使用安全合规中心 &amp; 访问高级电子数据展示并运行案例的流程模块。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64172c0198418dbb0ba4d01a5adbd5aaef4c3a3b
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662829"
---
# <a name="run-the-process-module-and-load-data-in-advanced-ediscovery-classic"></a><span data-ttu-id="4cfa2-103">运行流程模块，在高级电子数据展示和经典 (加载) </span><span class="sxs-lookup"><span data-stu-id="4cfa2-103">Run the Process module and load data in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="4cfa2-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="4cfa2-106">本节介绍高级电子数据展示流程模块的功能。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="4cfa2-107">除了文件数据之外，元数据（如文件类型、扩展名、位置或路径、创建日期和时间、作者、保管人和主题）还可以加载到高级电子数据展示中，并针对每个案例进行保存。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-107">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case.</span></span> <span data-ttu-id="4cfa2-108">某些元数据由高级电子数据展示计算，例如加载本机文件时。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-108">Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="4cfa2-109">高级电子数据展示提供系统元数据值，例如近重复分组或相关性分数。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-109">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores.</span></span> <span data-ttu-id="4cfa2-110">管理员可以添加其他元数据，如文件注释。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-110">Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="4cfa2-111">正在运行的进程</span><span class="sxs-lookup"><span data-stu-id="4cfa2-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="4cfa2-112">批处理号在进程期间分配给文件，以允许跟踪文件。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-112">Batch numbers are assigned to a file during Process to allow the tracking of files.</span></span> <span data-ttu-id="4cfa2-113">批处理号还允许标识用于重新处理选项的进程批处理。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-113">The batch number also enables identification of Process batches for reprocessing options.</span></span> <span data-ttu-id="4cfa2-114">其他筛选器可用于按批次编号和会话进行筛选。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-114">Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="4cfa2-115">执行以下步骤以运行 Process。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="4cfa2-116">[打开安全 &amp; 合规中心](go-to-the-securitycompliance-center.md) 。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-116">[Open the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="4cfa2-117">转到 **"搜索 &amp; 调查** \> **电子数据展示"，** 然后单击"**转到高级电子数据展示"。**</span><span class="sxs-lookup"><span data-stu-id="4cfa2-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="4cfa2-118">在高级电子数据展示中，在显示的事例页面中选择相应的事例，然后单击 **"转到事例"。**</span><span class="sxs-lookup"><span data-stu-id="4cfa2-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="4cfa2-119">在 **"** \> **准备** \> **进程设置**"中，从可用容器列表中选择一个容器。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![单击"进程"将搜索结果添加到案例](../media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="4cfa2-121">如果要 **将** 容器添加为种子文件或预标记文件，请单击"高级设置..."。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="4cfa2-122">使用种子文件加快针对低丰富度问题的培训 (通常为 2% 或更少) 。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-122">Use seed files to accelerate training for issues with low richness (usually 2%, or less).</span></span> <span data-ttu-id="4cfa2-123">对于种子文件，建议选择各种明显相关的文件，并处理每个问题大约 20-50 个种子 (种子文件过多可能会扭曲相关性结果) 。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-123">For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results).</span></span> <span data-ttu-id="4cfa2-124">种子文件应由将训练该问题的同一个人审阅。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-124">Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="4cfa2-125">使用预标记文件自动执行相关性培训。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-125">Use pre-tagged files to automate Relevance training.</span></span> <span data-ttu-id="4cfa2-126">应标记至少 1，500 个文件，并保持与非相关文件的相关比例与添加到相关性的集合中的比例相同。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-126">You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance.</span></span> <span data-ttu-id="4cfa2-127">应手动标记这些文件，并且您应该确信标记的质量。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-127">These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![用于处理批处理文件的"高级设置"页的屏幕截图](../media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="4cfa2-129">在 **"种子"** 部分：</span><span class="sxs-lookup"><span data-stu-id="4cfa2-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="4cfa2-130">选择 **"标记为种子文件** "以将容器标记为种子文件。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-130">Choose **Mark as seed files** to mark the container as seed files.</span></span> <span data-ttu-id="4cfa2-131">还需要从"For issue"下拉列表中选择按问题 **分配** 它们。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-131">You also need choose to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="4cfa2-132">从 **"标记** " **下拉列表** 中选择"相关 **"或"** 不相关"。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-132">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4cfa2-133">将文件设置为 **种子** 后，你无法将它们标记为 **预标记**。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="4cfa2-134">在 **"预标记文件"部分** ：</span><span class="sxs-lookup"><span data-stu-id="4cfa2-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="4cfa2-135">选择 **"标记为预标记文件"** 以将容器标记为预标记文件。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-135">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files.</span></span> <span data-ttu-id="4cfa2-136">还需要从"For issue"下拉列表中按问题 **分配** 它们。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-136">You also need to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="4cfa2-137">从 **"标记** " **下拉列表** 中选择"相关 **"或"** 不相关"。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-137">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4cfa2-138">将文件设置为预 **标记后**，不能将它们标记为 **种子**。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="4cfa2-139">在 **"电子邮件标记"** 部分。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-139">In the **Email tagging** section.</span></span> <span data-ttu-id="4cfa2-140">设置要标记为种子或预标记的已处理电子邮件的哪一部分。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-140">set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="4cfa2-141">若要开始，请单击"**进程"。**</span><span class="sxs-lookup"><span data-stu-id="4cfa2-141">To begin, click **Process**.</span></span> <span data-ttu-id="4cfa2-142">完成后，将显示进程结果。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-142">When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="4cfa2-143"> (可选) 如果需要将数据源分配给特定保管人，可以在保管人管理中添加和编辑保管人名称，在保管人分配中 \> 分配 **保管** \> **人**。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="4cfa2-144">如果添加到案例，可以再次处理。</span><span class="sxs-lookup"><span data-stu-id="4cfa2-144">If you add to the case, then you can process again.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4cfa2-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="4cfa2-145">Related topics</span></span>

[<span data-ttu-id="4cfa2-146">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="4cfa2-146">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="4cfa2-147">查看进程模块结果</span><span class="sxs-lookup"><span data-stu-id="4cfa2-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

