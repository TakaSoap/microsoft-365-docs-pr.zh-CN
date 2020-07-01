---
title: 快速设置高级电子数据展示
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: 了解如何从安全与合规中心访问高级电子数据展示，并查看使用高级电子数据展示的典型工作流。
ms.openlocfilehash: 5bd183f0f5f1c2f091fb374aab1e54f191665ce6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936255"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a><span data-ttu-id="6e378-103">快速设置高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="6e378-103">Quick setup Advanced eDiscovery (classic)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e378-104">当我们继续对较新版本的高级电子数据展示进行投资时，我们将宣布停用高级电子数据展示（也称为*高级电子数据展示（经典）* 或*高级电子数据展示 v1.0*）。</span><span class="sxs-lookup"><span data-stu-id="6e378-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="6e378-105">如果仍在使用高级电子数据展示 v1.0，请尽快切换到[高级电子数据展示 v2.0](overview-ediscovery-20.md)（也称为 *Microsoft 365 中的高级电子数据展示解决方案*）。</span><span class="sxs-lookup"><span data-stu-id="6e378-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="6e378-106">高级电子数据展示 2.0 不仅包含高级电子数据展示 v1.0 中提供的类似功能，还提供了许多新功能，如保管人管理、沟通管理和审阅集。</span><span class="sxs-lookup"><span data-stu-id="6e378-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="6e378-107">若要了解停用高级电子数据展示 v1.0 的详细信息，请参阅[停用旧式电子数据展示工具](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。</span><span class="sxs-lookup"><span data-stu-id="6e378-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 

<span data-ttu-id="6e378-108">阅读本设置部分，Microsoft 365 安全与合规中心电子数据展示管理员可了解如何开始使用高级电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="6e378-108">This setup section shows an Microsoft 365 Security &amp; Compliance Center eDiscovery manager how to get started with Advanced eDiscovery.</span></span> <span data-ttu-id="6e378-109">若要更好地理解本部分，需要对这两种工具都有一定的了解。</span><span class="sxs-lookup"><span data-stu-id="6e378-109">A working knowledge of both is assumed.</span></span>
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a><span data-ttu-id="6e378-110">访问高级电子数据展示中的案件集</span><span class="sxs-lookup"><span data-stu-id="6e378-110">Accessing a case in Advanced eDiscovery</span></span>

<span data-ttu-id="6e378-111">You access Advanced eDiscovery from the Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="6e378-111">You access Advanced eDiscovery from the Security &amp; Compliance Center.</span></span> <span data-ttu-id="6e378-112">You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="6e378-112">You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery.</span></span> <span data-ttu-id="6e378-113">For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="6e378-113">For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span></span> 
  
<span data-ttu-id="6e378-114">若要转到高级电子数据展示中的案件集，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6e378-114">To go to a case in Advanced eDiscovery:</span></span> 
  
1. <span data-ttu-id="6e378-115">[转到安全与合规中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="6e378-115">[Go to the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="6e378-116">在安全与合规中心内，依次单击“搜索和调查”\*\*\*\* 和“电子数据展示”\*\*\*\*，以显示组织中的案件集列表。</span><span class="sxs-lookup"><span data-stu-id="6e378-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
3. <span data-ttu-id="6e378-117">在“电子数据展示”\*\*\*\* 页上，单击要在高级电子数据展示中转到的案件集旁边的“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6e378-117">On the **eDiscovery** page, click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span>
    
4. <span data-ttu-id="6e378-118">在此案件集的“**主页**”上，单击“**切换至高级电子数据展示**”。</span><span class="sxs-lookup"><span data-stu-id="6e378-118">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span>
    
    <span data-ttu-id="6e378-119">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span><span class="sxs-lookup"><span data-stu-id="6e378-119">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="6e378-120">When you're connected, the case is opened in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="6e378-120">When you're connected, the case is opened in Advanced eDiscovery.</span></span> 
    
## <a name="workflow"></a><span data-ttu-id="6e378-121">工作流</span><span class="sxs-lookup"><span data-stu-id="6e378-121">Workflow</span></span>

<span data-ttu-id="6e378-122">下图展示了在安全与合规中心和高级电子数据展示中管理和使用电子数据展示案件集的常用工作流。</span><span class="sxs-lookup"><span data-stu-id="6e378-122">The following diagram illustrates the common workflow for managing and using eDiscovery cases in the Security &amp; Compliance Center and Advanced eDiscovery.</span></span>
  
![图中显示了包含四个设置阶段的高级电子数据展示工作流，包括设置用户和案件集、标识案件集数据、导出和处理，然后是分析和导出到本地计算机这两个阶段。](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
<span data-ttu-id="6e378-124">This setup section describes the first four steps in the workflow.</span><span class="sxs-lookup"><span data-stu-id="6e378-124">This setup section describes the first four steps in the workflow.</span></span> <span data-ttu-id="6e378-125">For a description of the other steps in the workflow, see the following.</span><span class="sxs-lookup"><span data-stu-id="6e378-125">For a description of the other steps in the workflow, see the following.</span></span>
  
## <a name="analyze"></a><span data-ttu-id="6e378-126">分析</span><span class="sxs-lookup"><span data-stu-id="6e378-126">Analyze</span></span>

<span data-ttu-id="6e378-127">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results.</span><span class="sxs-lookup"><span data-stu-id="6e378-127">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results.</span></span> <span data-ttu-id="6e378-128">Analyze functionality can be customized by the user in order to achieve enhanced results.</span><span class="sxs-lookup"><span data-stu-id="6e378-128">Analyze functionality can be customized by the user in order to achieve enhanced results.</span></span> 
  
## <a name="relevance-setup-and-relevance"></a><span data-ttu-id="6e378-129">相关性设置和相关性</span><span class="sxs-lookup"><span data-stu-id="6e378-129">Relevance Setup and Relevance</span></span>

<span data-ttu-id="6e378-130">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process.</span><span class="sxs-lookup"><span data-stu-id="6e378-130">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process.</span></span> <span data-ttu-id="6e378-131">Calculates and displays interim results while monitoring statistical validity of the process.</span><span class="sxs-lookup"><span data-stu-id="6e378-131">Calculates and displays interim results while monitoring statistical validity of the process.</span></span> <span data-ttu-id="6e378-132">Displays the results to facilitate in making review decisions.</span><span class="sxs-lookup"><span data-stu-id="6e378-132">Displays the results to facilitate in making review decisions.</span></span> 
  
## <a name="export"></a><span data-ttu-id="6e378-133">导出</span><span class="sxs-lookup"><span data-stu-id="6e378-133">Export</span></span>

<span data-ttu-id="6e378-134">[导出案件集数据](export-case-data-in-advanced-ediscovery.md)：可导出高级电子数据展示内容和结果，以供外部审阅。</span><span class="sxs-lookup"><span data-stu-id="6e378-134">[Exporting case data](export-case-data-in-advanced-ediscovery.md) Enables the exporting of Advanced eDiscovery content and results for external review.</span></span> 
  
## <a name="report"></a><span data-ttu-id="6e378-135">报告</span><span class="sxs-lookup"><span data-stu-id="6e378-135">Report</span></span>

<span data-ttu-id="6e378-136">[生成报告](run-reports-in-advanced-ediscovery.md)：可生成与高级电子数据展示处理相关的选定报告。</span><span class="sxs-lookup"><span data-stu-id="6e378-136">[Running reports](run-reports-in-advanced-ediscovery.md) Enables the generation of selected reports related to Advanced eDiscovery processing.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6e378-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e378-137">See also</span></span>

[<span data-ttu-id="6e378-138">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="6e378-138">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="6e378-139">设置用户和案件集</span><span class="sxs-lookup"><span data-stu-id="6e378-139">Setting up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6e378-140">准备数据</span><span class="sxs-lookup"><span data-stu-id="6e378-140">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)

