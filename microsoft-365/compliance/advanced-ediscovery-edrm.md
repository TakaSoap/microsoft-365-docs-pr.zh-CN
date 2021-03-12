---
title: 高级电子数据展示与 EDRM 的对齐方式
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- m365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 中高级电子数据展示的内置工作流与电子数据展示模型 EDRM (概述的电子数据展示) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2e7886eb67a58b43e9fb638fafb358fd9ee832c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727485"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a><span data-ttu-id="85ce1-103">电子数据展示与电子数据展示参考模型保持一致</span><span class="sxs-lookup"><span data-stu-id="85ce1-103">Advanced eDiscovery alignment with the Electronic Discovery Reference Model</span></span>

<span data-ttu-id="85ce1-104">Microsoft 365 中高级电子数据展示的内置工作流与电子数据展示模型 EDRM (概述的电子数据展示) 。</span><span class="sxs-lookup"><span data-stu-id="85ce1-104">The built-in workflow of Advanced eDiscovery in Microsoft 365 aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span>

![电子数据发现参考模型 (EDRM) ](../media/EDRMv1.png)

<span data-ttu-id="85ce1-106"> (图像源的edrm.net。</span><span class="sxs-lookup"><span data-stu-id="85ce1-106">(Image source courtesy of edrm.net.</span></span> <span data-ttu-id="85ce1-107">源图像在 Creative Commons Attribution 3.0 未ported License.) </span><span class="sxs-lookup"><span data-stu-id="85ce1-107">The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="85ce1-108">高级电子数据展示在高级别上如何支持 EDRM 工作流：</span><span class="sxs-lookup"><span data-stu-id="85ce1-108">At a high level, here's how Advanced eDiscovery supports the EDRM workflow:</span></span>

- <span data-ttu-id="85ce1-109">**标识。**</span><span class="sxs-lookup"><span data-stu-id="85ce1-109">**Identification.**</span></span> <span data-ttu-id="85ce1-110">在确定了调查感兴趣的潜在人员后，可以添加他们作为保管人 (也称为数据保管人，因为他们可能拥有与调查) 高级电子数据展示案例有关的信息。</span><span class="sxs-lookup"><span data-stu-id="85ce1-110">After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to an Advanced eDiscovery case.</span></span> <span data-ttu-id="85ce1-111">将用户添加为保管人后，可轻松保留、收集和查看保管人文档。</span><span class="sxs-lookup"><span data-stu-id="85ce1-111">After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="85ce1-112">**保留。**</span><span class="sxs-lookup"><span data-stu-id="85ce1-112">**Preservation.**</span></span> <span data-ttu-id="85ce1-113">为了保留和保护与调查相关的数据，高级电子数据展示允许您对与案例保管人关联的数据源进行合法保留。</span><span class="sxs-lookup"><span data-stu-id="85ce1-113">To preserve and protect data that's relevant to an investigation, Advanced eDiscovery lets you place a legal hold on the data sources associated with the custodians in a case.</span></span> <span data-ttu-id="85ce1-114">还可以将非安全数据放在保留状态。</span><span class="sxs-lookup"><span data-stu-id="85ce1-114">You can also place non-custodial data on hold.</span></span> <span data-ttu-id="85ce1-115">高级电子数据展示还内置了通信工作流，因此你可以向保管人发送合法保留通知并跟踪其确认。</span><span class="sxs-lookup"><span data-stu-id="85ce1-115">Advanced eDiscovery also has a built-in communications workflow so you can send legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="85ce1-116">**集合。**</span><span class="sxs-lookup"><span data-stu-id="85ce1-116">**Collection.**</span></span> <span data-ttu-id="85ce1-117">标识 (并保留) 调查相关的数据源后，可以使用高级电子数据展示搜索中的内置搜索工具，从可能与案例相关的主要数据源 () 和非实时数据源（如果适用）中收集实时数据。</span><span class="sxs-lookup"><span data-stu-id="85ce1-117">After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="85ce1-118">**处理。**</span><span class="sxs-lookup"><span data-stu-id="85ce1-118">**Processing.**</span></span> <span data-ttu-id="85ce1-119">收集与案例相关的所有数据后，下一步是处理该数据以进一步查看和分析。</span><span class="sxs-lookup"><span data-stu-id="85ce1-119">After you've collected all data relevant to the case, the next step is process it for further review and analysis.</span></span> <span data-ttu-id="85ce1-120">在高级电子数据展示中，你在收集阶段标识的就地数据将复制到 Azure 存储位置 (称为审阅集 *) ，* 它提供案例数据的静态视图。</span><span class="sxs-lookup"><span data-stu-id="85ce1-120">In Advanced eDiscovery, the in-place data that you identified in the collection phase is copied to an Azure Storage location (called a *review set*), which provides you with a static view of the case data.</span></span> 

- <span data-ttu-id="85ce1-121">**查看。**</span><span class="sxs-lookup"><span data-stu-id="85ce1-121">**Review.**</span></span> <span data-ttu-id="85ce1-122">将数据添加到审阅集后，您可以查看特定文档并运行其他查询，以将数据减少为与案例最相关的内容。</span><span class="sxs-lookup"><span data-stu-id="85ce1-122">After data has been added to a review set, you can view specific documents and run additional queries to reduce the data to what is most relevant to the case.</span></span> <span data-ttu-id="85ce1-123">此外，还可以为特定文档添加批注和标记。</span><span class="sxs-lookup"><span data-stu-id="85ce1-123">Also, can annotate and tag specific documents.</span></span>

- <span data-ttu-id="85ce1-124">**分析。**</span><span class="sxs-lookup"><span data-stu-id="85ce1-124">**Analysis.**</span></span> <span data-ttu-id="85ce1-125">高级电子数据展示提供了集成的分析工具，可帮助你进一步从你确定与调查不相关的审阅集剔除数据。</span><span class="sxs-lookup"><span data-stu-id="85ce1-125">Advanced eDiscovery provides integrated analytics tool that helps you further cull data from the review set that you determine isn't relevant to the investigation.</span></span> <span data-ttu-id="85ce1-126">除了减少数据量外，高级电子数据展示还可以帮助您节省法律审阅成本，通过组织内容使审阅过程更加轻松和高效。</span><span class="sxs-lookup"><span data-stu-id="85ce1-126">In addition to reducing the volume of relevant data, Advance eDiscovery also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="85ce1-127">**生产和\*\*\*\*演示。**</span><span class="sxs-lookup"><span data-stu-id="85ce1-127">**Production** and **Presentation.**</span></span> <span data-ttu-id="85ce1-128">准备就绪后，可以从审阅集导出文档进行法律审阅。</span><span class="sxs-lookup"><span data-stu-id="85ce1-128">When you're ready, you can export documents from a review set for legal review.</span></span> <span data-ttu-id="85ce1-129">您可以以本机格式或 EDRM 指定格式导出文档，以便它们可以导入到第三方审阅应用程序中。</span><span class="sxs-lookup"><span data-stu-id="85ce1-129">You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="more-information"></a><span data-ttu-id="85ce1-130">更多信息</span><span class="sxs-lookup"><span data-stu-id="85ce1-130">More information</span></span>

<span data-ttu-id="85ce1-131">若要开始使用高级电子数据展示，请参阅：</span><span class="sxs-lookup"><span data-stu-id="85ce1-131">To get started using Advanced eDiscovery, see:</span></span>

- [<span data-ttu-id="85ce1-132">设置高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="85ce1-132">Set up Advanced eDiscovery</span></span>](get-started-with-advanced-ediscovery.md)

- [<span data-ttu-id="85ce1-133">创建和管理高级电子数据展示案例</span><span class="sxs-lookup"><span data-stu-id="85ce1-133">Create and manage an Advanced eDiscovery case</span></span>](create-and-manage-advanced-ediscoveryv2-case.md)