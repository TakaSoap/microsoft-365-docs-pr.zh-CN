---
title: 了解高级电子数据展示中的文档相似性
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 查看文档相似性值（两个文件的相似性最低级别）在高级电子数据展示中的工作方式。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22eb27e7afdc6ad37ea6fdcba9b64298906f1c35
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663311"
---
# <a name="understand-document-similarity-in-advanced-ediscovery-classic"></a><span data-ttu-id="745f7-103">了解高级电子数据展示和经典 (中的文档) </span><span class="sxs-lookup"><span data-stu-id="745f7-103">Understand document similarity in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="745f7-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="745f7-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="745f7-106">在高级电子数据展示中，文档相似性是将两个文档视为接近重复项所需的最低相似性级别。</span><span class="sxs-lookup"><span data-stu-id="745f7-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="745f7-107">对于大多数业务应用程序，建议使用 60%-75% 的相似性值。</span><span class="sxs-lookup"><span data-stu-id="745f7-107">For most business applications, it is recommended to use a Similarity value of 60%-75%.</span></span> <span data-ttu-id="745f7-108">对于 OCR (质量极差的光学字符识别) ，可以应用较低的相似性值。</span><span class="sxs-lookup"><span data-stu-id="745f7-108">For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="745f7-109">设置并运行给定案例后，不能更改相似性值。</span><span class="sxs-lookup"><span data-stu-id="745f7-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="745f7-110">在"近 (ND) 集内，可能有相似级别低于相似性阈值的文档。</span><span class="sxs-lookup"><span data-stu-id="745f7-110">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold.</span></span> <span data-ttu-id="745f7-111">对于要联接 ND 集的文档，ND 集合中必须至少有一个类似级别超过相似性的文档。</span><span class="sxs-lookup"><span data-stu-id="745f7-111">For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="745f7-112">例如，假定相似性设置为 80%，文档 F1 在 85% 级别类似于文档 F2，文档 F2 与文档 F3 的级别 90% 相似。</span><span class="sxs-lookup"><span data-stu-id="745f7-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="745f7-113">但是，文档 F1 可能类似于文档 F3，其级别仅为 70%，低于阈值。</span><span class="sxs-lookup"><span data-stu-id="745f7-113">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold.</span></span> <span data-ttu-id="745f7-114">尽管如此，在此例中，文档 F1、F2 和 F3 都显示在一个 ND 集合中。</span><span class="sxs-lookup"><span data-stu-id="745f7-114">Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set.</span></span> <span data-ttu-id="745f7-115">同样，使用 80% 的相似性值，我们可能创建了两个集，EquiSet-1 和 EquiSet-2。</span><span class="sxs-lookup"><span data-stu-id="745f7-115">Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2.</span></span> <span data-ttu-id="745f7-116">EquiSet-1 包含文档 E1 和 E2。</span><span class="sxs-lookup"><span data-stu-id="745f7-116">EquiSet-1 contains documents E1 and E2.</span></span> <span data-ttu-id="745f7-117">Equiset-2 包含文档 F1、F2 和 F3。</span><span class="sxs-lookup"><span data-stu-id="745f7-117">Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="745f7-118">类似级别如下所述：</span><span class="sxs-lookup"><span data-stu-id="745f7-118">The levels of resemblance are illustrated as follows:</span></span>
  
![文档相似性](../media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="745f7-120">假定现在插入了另一个文档 X1。</span><span class="sxs-lookup"><span data-stu-id="745f7-120">Assume that another document, X1, is now inserted.</span></span> <span data-ttu-id="745f7-121">X1 和 E3 之间的相似度为 87%。</span><span class="sxs-lookup"><span data-stu-id="745f7-121">The resemblance between X1 and E3 is 87%.</span></span> <span data-ttu-id="745f7-122">同样，X1 和 F1 之间的相似性为 92%。</span><span class="sxs-lookup"><span data-stu-id="745f7-122">Similarly, the resemblance between X1 and F1 is 92%.</span></span> <span data-ttu-id="745f7-123">因此，EquiSet -1、EquiSet -2 和 X1 现在组合到一个 ND 集。</span><span class="sxs-lookup"><span data-stu-id="745f7-123">As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![文档相似性](../media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="745f7-125">如果将任何两个文档分配给一个 ND 集，它们仍将一起保留在相同的 ND 集合中，即使向该集合中添加了其他文档或合并了这些文档集。</span><span class="sxs-lookup"><span data-stu-id="745f7-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="745f7-126">合并集后，当向集合中添加新文档时，数据透视文档可能会更改。</span><span class="sxs-lookup"><span data-stu-id="745f7-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="745f7-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="745f7-127">Related topics</span></span>

[<span data-ttu-id="745f7-128">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="745f7-128">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="745f7-129">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="745f7-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="745f7-130">设置忽略文本</span><span class="sxs-lookup"><span data-stu-id="745f7-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="745f7-131">设置 分析高级设置</span><span class="sxs-lookup"><span data-stu-id="745f7-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="745f7-132">查看分析结果</span><span class="sxs-lookup"><span data-stu-id="745f7-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

