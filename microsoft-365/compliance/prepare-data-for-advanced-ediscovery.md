---
title: 准备高级电子数据展示的数据
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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: 了解如何使用安全 &amp; 合规中心准备数据以使用高级电子数据展示进行分析。
ms.openlocfilehash: 3c9d237a3a9c04a443730143998324a7831f2998
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936327"
---
# <a name="prepare-data-for-advanced-ediscovery-classic"></a><span data-ttu-id="cf564-103">为高级电子数据展示准备数据（经典）</span><span class="sxs-lookup"><span data-stu-id="cf564-103">Prepare data for Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="cf564-104">本主题介绍如何在高级电子数据展示（经典）中将内容搜索的结果加载到案例中。</span><span class="sxs-lookup"><span data-stu-id="cf564-104">This topic describes how to load the results of a Content Search in to a case in Advanced eDiscovery (classic).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="cf564-105">当我们继续对较新版本的高级电子数据展示进行投资时，我们将宣布停用高级电子数据展示（也称为*高级电子数据展示（经典）* 或*高级电子数据展示 v1.0*）。</span><span class="sxs-lookup"><span data-stu-id="cf564-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="cf564-106">如果仍在使用高级电子数据展示 v1.0，请尽快切换到[高级电子数据展示 v2.0](overview-ediscovery-20.md)（也称为 *Microsoft 365 中的高级电子数据展示解决方案*）。</span><span class="sxs-lookup"><span data-stu-id="cf564-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="cf564-107">高级电子数据展示 2.0 不仅包含高级电子数据展示 v1.0 中提供的类似功能，还提供了许多新功能，如保管人管理、沟通管理和审阅集。</span><span class="sxs-lookup"><span data-stu-id="cf564-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="cf564-108">若要了解停用高级电子数据展示 v1.0 的详细信息，请参阅[停用旧式电子数据展示工具](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。</span><span class="sxs-lookup"><span data-stu-id="cf564-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span>  
  
## <a name="step-1-prepare-data-for-advanced-ediscovery"></a><span data-ttu-id="cf564-109">步骤1：为高级电子数据展示准备数据</span><span class="sxs-lookup"><span data-stu-id="cf564-109">Step 1: Prepare data for Advanced eDiscovery</span></span>

<span data-ttu-id="cf564-110">若要使用高级电子数据展示分析数据，可以使用在 Microsoft 365 安全 &amp; 合规性中心（在 microsoft 365 安全合规中心的**内容搜索**页中列出）中运行的内容搜索结果 &amp; 或与电子数据展示事例关联的搜索（在安全合规性中心的**电子数据展示**页中列出 &amp; ）。</span><span class="sxs-lookup"><span data-stu-id="cf564-110">To analyze data with Advanced eDiscovery, you can use the results of a Content Search that you run in the Microsoft 365 Security &amp; Compliance Center (listed on the **Content search** page in the Microsoft 365 Security &amp; Compliance Center) or a search associated with an eDiscovery case (listed on the **eDiscovery** page in the Security &amp; Compliance Center).</span></span> 
  
<span data-ttu-id="cf564-111">有关在高级电子数据展示中准备分析搜索结果的详细步骤，请参阅[为高级电子数据展示准备搜索结果](prepare-search-results-for-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="cf564-111">For the detailed steps on preparing search results for analysis in Advanced eDiscovery, see [Prepare search results for Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf564-112">如果你的数据在 Microsoft 365 之外，并且想要将其导入到 Microsoft 365，以便在高级电子数据展示中准备和分析它，请参阅将[PST 文件导入到 Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365)和[存档第三方数据](https://www.microsoft.com/?ref=go)的概述。</span><span class="sxs-lookup"><span data-stu-id="cf564-112">If you have data outside of Microsoft 365 and want to import it to Microsoft 365 so that you can prepare and analyze it in Advanced eDiscovery, a see [Overview of importing PST files to Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365) and [Archiving third-party data](https://www.microsoft.com/?ref=go).</span></span> 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a><span data-ttu-id="cf564-113">步骤2：将搜索结果数据加载到高级电子数据展示中的案例</span><span class="sxs-lookup"><span data-stu-id="cf564-113">Step 2: Load search result data in to a case in Advanced eDiscovery</span></span>

<span data-ttu-id="cf564-114">准备好安全合规中心中的搜索结果 &amp; 进行分析之后，下一步是在高级电子数据展示中将搜索结果加载到一个案例中。</span><span class="sxs-lookup"><span data-stu-id="cf564-114">After you prepare the search results in the Security &amp; Compliance Center for analysis, the next step is to load the search results in to a case in Advanced eDiscovery.</span></span> <span data-ttu-id="cf564-115">有关更多详细信息，请参阅[运行 Process module](run-the-process-module-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="cf564-115">For more detailed information, see [Run the Process module](run-the-process-module-in-advanced-ediscovery.md).</span></span>
  
1. <span data-ttu-id="cf564-116">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="cf564-116">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="cf564-117">使用工作或学校帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="cf564-117">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="cf564-118">在安全与合规中心内，依次单击“搜索和调查”\*\*\*\* 和“电子数据展示”\*\*\*\*，以显示组织中的案件集列表。</span><span class="sxs-lookup"><span data-stu-id="cf564-118">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
4. <span data-ttu-id="cf564-119">在高级电子数据展示中，单击要在其中将数据加载到的事例旁边的 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="cf564-119">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
5. <span data-ttu-id="cf564-120">在此案件集的“**主页**”上，单击“**切换至高级电子数据展示**”。</span><span class="sxs-lookup"><span data-stu-id="cf564-120">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span> 
    
    ![单击 "切换到高级电子数据展示" 以在高级电子数据展示中打开事例](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="cf564-122">将显示 "**连接到高级电子数据展示**进度栏"。</span><span class="sxs-lookup"><span data-stu-id="cf564-122">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="cf564-123">当您连接到高级电子数据展示时，会在 "设置" 页上显示一个容器列表。</span><span class="sxs-lookup"><span data-stu-id="cf564-123">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![事例显示在高级电子数据展示](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="cf564-125">这些容器代表您在步骤1中的高级电子数据展示中准备进行分析的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="cf564-125">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="cf564-126">请注意，在安全合规中心的情况下，容器名称与内容搜索的名称相同 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="cf564-126">Note that the name of the container has the same name as the Content Search in the case in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="cf564-127">列表中的容器是您准备的容器。</span><span class="sxs-lookup"><span data-stu-id="cf564-127">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="cf564-128">如果其他用户为高级电子数据展示准备了搜索结果，则相应的容器将不会包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="cf564-128">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
6. <span data-ttu-id="cf564-129">若要在高级电子数据展示中将容器中的搜索结果数据加载到事例中，请选择一个容器，然后单击 "**处理**"。</span><span class="sxs-lookup"><span data-stu-id="cf564-129">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
<span data-ttu-id="cf564-130">将安全合规中心中的搜索结果 &amp; 添加到高级电子数据展示的事例中后，下一步是使用高级电子数据展示中的工具来分析和挑选与事例相关的数据。</span><span class="sxs-lookup"><span data-stu-id="cf564-130">After the search results from the Security &amp; Compliance Center are added to the case in Advanced eDiscovery, the next step is to use the tools in Advanced eDiscovery to analyze and cull the data that's relevant to the case.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cf564-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf564-131">See also</span></span>

[<span data-ttu-id="cf564-132">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="cf564-132">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="cf564-133">设置用户和案例</span><span class="sxs-lookup"><span data-stu-id="cf564-133">Set up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cf564-134">分析事例数据</span><span class="sxs-lookup"><span data-stu-id="cf564-134">Analyzing case data</span></span>](analyze-case-data-with-advanced-ediscovery.md)
  
[<span data-ttu-id="cf564-135">管理相关性设置</span><span class="sxs-lookup"><span data-stu-id="cf564-135">Managing Relevance setup</span></span>](manage-relevance-setup-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cf564-136">使用相关性模块</span><span class="sxs-lookup"><span data-stu-id="cf564-136">Using the Relevance module</span></span>](use-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cf564-137">导出事例数据</span><span class="sxs-lookup"><span data-stu-id="cf564-137">Exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)

