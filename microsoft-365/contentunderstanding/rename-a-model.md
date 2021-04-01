---
title: 在 Microsoft SharePoint Syntex 中重命名模型
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
description: 学习如何以及为什么在 Microsoft SharePoint Syntex 中重命名模型。
ms.openlocfilehash: d0d17f040199b2e6b60bfc98d325f18b6de0b7f2
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445940"
---
# <a name="rename-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="c3d3a-103">在 Microsoft SharePoint Syntex 中重命名模型</span><span class="sxs-lookup"><span data-stu-id="c3d3a-103">Rename a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="c3d3a-104">有时，你可能希望重命名文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-104">At some point, you might want to rename a document understanding model.</span></span> <span data-ttu-id="c3d3a-105">一个常见示例是，在创建模型初稿时，你可能未对最终名称做过多思考(例如，你可能将模型命名为”AlexWilburModel1“)。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-105">A common example is when you create an initial draft of a model, you might not have given a lot of thought as to the final name (for example, you might have named it “AlexWilburModel1”).</span></span> <span data-ttu-id="c3d3a-106">当快完成模型并将其投入使用时，你发现取名为“合同续订”更加恰当，因而你希望重命名模型。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-106">As you come closer to finalizing the model and putting it to use, you realize that a more proper name would be “Contract Renewals,” and you want to rename it.</span></span>  

<span data-ttu-id="c3d3a-107">另一个示例是，你的组织决定使用不同名称引用流程或文档类型。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-107">Another example is when your organization makes a decision to refer to a process or document type by a different name.</span></span> <span data-ttu-id="c3d3a-108">例如，当你创建好模型并准备应用后，组织可能强制所有“合同”正式被称为“协议”。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-108">For example, after you create your model and are ready to apply it, your organization might mandate that all “Contracts” will now formally be referred to as “Agreements.”</span></span> <span data-ttu-id="c3d3a-109">如果需要，你可以选择将模型从“合同续订”重命名为“协议续订”。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-109">If needed, you can choose to rename your model from “Contract Renewals” to “Agreement Renewals.”</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3d3a-110">只有在文档理解模型尚未应用于文档库时，才可对其进行重命名。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-110">You can only rename a document understanding model if it has not been applied to a document library.</span></span> 

<span data-ttu-id="c3d3a-111">重命名模型同时也会重命名与之关联的[内容类型](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-111">Renaming a model also renames the [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that is associated with the model.</span></span>

## <a name="rename-a-model"></a><span data-ttu-id="c3d3a-112">重命名模型</span><span class="sxs-lookup"><span data-stu-id="c3d3a-112">Rename a model</span></span>

<span data-ttu-id="c3d3a-113">请按照以下步骤重命名文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-113">Follow these steps to rename a document understanding model.</span></span>

1. <span data-ttu-id="c3d3a-114">从内容中心中，选择“**模型**”，查看你的模型列表。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-114">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="c3d3a-115">在“**模型**”页面，选择希望重命名的模型。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-115">On the **Models** page, select the model you want to rename.</span></span>

3. <span data-ttu-id="c3d3a-116">使用功能区或“**显示操作**”按钮(模型名称旁)，选择 **重命名**。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-116">By using either the ribbon or the **Show actions** button (next to the model name), select **Rename**.</span></span> </br>

    ![“模型”页面的屏幕截图显示了所选的模型，其中突出显示了“重命名”选项。](../media/content-understanding/select-model-rename-both.png) </br>

4. <span data-ttu-id="c3d3a-118">在“**重命名模型**”面板中:</span><span class="sxs-lookup"><span data-stu-id="c3d3a-118">On the **Rename model** panel:</span></span>

   <span data-ttu-id="c3d3a-119">a.</span><span class="sxs-lookup"><span data-stu-id="c3d3a-119">a.</span></span> <span data-ttu-id="c3d3a-120">在“**新名称**”下面，输入希望重命名的模型的新名称。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-120">Under **New name**, enter the new name of the model that you want to rename.</span></span></br>

    ![屏幕截图显示了“重命名”模型面板。](../media/content-understanding/rename-model-panel.png) </br>

   <span data-ttu-id="c3d3a-122">b.</span><span class="sxs-lookup"><span data-stu-id="c3d3a-122">b.</span></span> <span data-ttu-id="c3d3a-123">(可选)在“**高级设置**”下，选择是否希望关联现有[内容类型](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span> <span data-ttu-id="c3d3a-124">如果选择“**使用现有内容类型**”，则将重命名模型，从而匹配所选的内容类型。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-124">If you choose **Use an existing content type**, the model will be renamed to match the selected content type.</span></span>

5. <span data-ttu-id="c3d3a-125">选择“**重命名**”。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-125">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3d3a-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3d3a-126">See Also</span></span>
[<span data-ttu-id="c3d3a-127">创建分类器</span><span class="sxs-lookup"><span data-stu-id="c3d3a-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="c3d3a-128">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="c3d3a-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="c3d3a-129">重命名提取程序</span><span class="sxs-lookup"><span data-stu-id="c3d3a-129">Rename an extractor</span></span>](rename-an-extractor.md)

[<span data-ttu-id="c3d3a-130">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="c3d3a-130">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="c3d3a-131">说明类型</span><span class="sxs-lookup"><span data-stu-id="c3d3a-131">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="c3d3a-132">应用模型</span><span class="sxs-lookup"><span data-stu-id="c3d3a-132">Apply a model</span></span>](apply-a-model.md) 
