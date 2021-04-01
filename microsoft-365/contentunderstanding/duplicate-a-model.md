---
title: 在 Microsoft SharePoint Syntex 中复制模型
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 学习如何以及为什么在 Microsoft SharePoint Syntex 中复制模型。
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445947"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="95e4b-103">在 Microsoft SharePoint Syntex 中复制模型</span><span class="sxs-lookup"><span data-stu-id="95e4b-103">Duplicate a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="95e4b-104">如果需要创建新模型，并且明确现有模型与需要的模式非常相似，则复制文档理解模型可以节省时间和精力。</span><span class="sxs-lookup"><span data-stu-id="95e4b-104">Duplicating a document understanding model can save you time and effort if you need to create a new model, and know that an existing model is very similar to what you need.</span></span>

<span data-ttu-id="95e4b-105">例如，名为“合同”的现有模型对需要使用的相同文件进行分类。</span><span class="sxs-lookup"><span data-stu-id="95e4b-105">For example, an existing model named “Contracts” classifies the same files you need to work with.</span></span> <span data-ttu-id="95e4b-106">新模型将提取一些现有数据，但需要进行更新，以便提取额外数据。</span><span class="sxs-lookup"><span data-stu-id="95e4b-106">Your new model will extract some of the existing data, but will need to be updated to extract some additional data.</span></span> <span data-ttu-id="95e4b-107">不必从头开始创建和培训新模型，你可以使用复制模型功能创建“合同”模型的副本，这同时会复制所有关联的培训项目，例如示例文件和实体提取器。</span><span class="sxs-lookup"><span data-stu-id="95e4b-107">Instead of creating and training a new model from scratch, you can use the duplicate model feature to make a copy of the Contracts model, which will also copy all associated training items, such as example files and entity extractors.</span></span>

<span data-ttu-id="95e4b-108">复制模型时，在重命名之后(例如，重命名为“合同续订”)就可进行更新。</span><span class="sxs-lookup"><span data-stu-id="95e4b-108">When you duplicate the model, after you rename it (for example, to “Contract Renewals”), you can then make updates to it.</span></span> <span data-ttu-id="95e4b-109">例如，可以选择删除一些不需要的现有提取字段，然后训练模型提取新的字段(例如“续订日期”)。</span><span class="sxs-lookup"><span data-stu-id="95e4b-109">For example, you can choose to remove some of the existing extracted fields that you don’t need, and then train the model to extract a new one (for example, “Renewal date”).</span></span>

## <a name="duplicate-a-model"></a><span data-ttu-id="95e4b-110">复制模型</span><span class="sxs-lookup"><span data-stu-id="95e4b-110">Duplicate a model</span></span>

<span data-ttu-id="95e4b-111">请按照以下步骤复制文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="95e4b-111">Follow these steps to duplicate a document understanding model.</span></span>

1. <span data-ttu-id="95e4b-112">从内容中心中，选择“**模型**”，查看你的模型列表。</span><span class="sxs-lookup"><span data-stu-id="95e4b-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="95e4b-113">在“**模型**”页面，选择希望复制的模型。</span><span class="sxs-lookup"><span data-stu-id="95e4b-113">On the **Models** page, select the model you want to duplicate.</span></span>

3. <span data-ttu-id="95e4b-114">使用功能区或“**显示操作**”按钮(模型名称旁)，选择 **复制**。</span><span class="sxs-lookup"><span data-stu-id="95e4b-114">By using either the ribbon or the **Show actions** button (next to the model name), select **Duplicate**.</span></span></br>

    ![“模型”页面的屏幕截图显示了所选模型，其中突出显示“重复”选项。](../media/content-understanding/select-model-duplicate-both.png) </br>

4. <span data-ttu-id="95e4b-116">在“**复制模型**”面板上:</span><span class="sxs-lookup"><span data-stu-id="95e4b-116">On the **Duplicate model** panel:</span></span>

   <span data-ttu-id="95e4b-117">a.</span><span class="sxs-lookup"><span data-stu-id="95e4b-117">a.</span></span> <span data-ttu-id="95e4b-118">在“**名称**”下面，输入希望复制的模型的新名称。</span><span class="sxs-lookup"><span data-stu-id="95e4b-118">Under **Name**, enter the new name of the model that you want to duplicate.</span></span></br>

    ![屏幕截图显示了“复制”模型面板。](../media/content-understanding/duplicate-model-panel.png) </br>

   <span data-ttu-id="95e4b-120">b.</span><span class="sxs-lookup"><span data-stu-id="95e4b-120">b.</span></span> <span data-ttu-id="95e4b-121">在“**描述**”下，添加新模型的说明。</span><span class="sxs-lookup"><span data-stu-id="95e4b-121">Under **Description**, add a description of your new model.</span></span>

   <span data-ttu-id="95e4b-122">c.</span><span class="sxs-lookup"><span data-stu-id="95e4b-122">c.</span></span> <span data-ttu-id="95e4b-123">(可选)在“**高级设置**”下，选择是否希望关联现有[内容类型](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)。</span><span class="sxs-lookup"><span data-stu-id="95e4b-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span>

5. <span data-ttu-id="95e4b-124">选择“**复制**”。</span><span class="sxs-lookup"><span data-stu-id="95e4b-124">Select **Duplicate**.</span></span>

## <a name="see-also"></a><span data-ttu-id="95e4b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95e4b-125">See Also</span></span>
[<span data-ttu-id="95e4b-126">创建分类器</span><span class="sxs-lookup"><span data-stu-id="95e4b-126">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="95e4b-127">重命名模型</span><span class="sxs-lookup"><span data-stu-id="95e4b-127">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="95e4b-128">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="95e4b-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="95e4b-129">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="95e4b-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="95e4b-130">说明类型</span><span class="sxs-lookup"><span data-stu-id="95e4b-130">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="95e4b-131">应用模型</span><span class="sxs-lookup"><span data-stu-id="95e4b-131">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="95e4b-132">SharePoint 整合辅助功能模式</span><span class="sxs-lookup"><span data-stu-id="95e4b-132">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)