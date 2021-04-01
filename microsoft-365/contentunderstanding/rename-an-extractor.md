---
title: 在 Microsoft SharePoint Syntex 中重命名提取程序
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
description: 了解如何以及为什么在 Microsoft SharePoint Syntex 中重命名提取程序。
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445938"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="55e86-103">在 Microsoft SharePoint Syntex 中重命名提取程序</span><span class="sxs-lookup"><span data-stu-id="55e86-103">Rename an extractor in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="55e86-104">有时，如果希望用不同的名称引用提取的数据字段，可能需要重命名提取程序。</span><span class="sxs-lookup"><span data-stu-id="55e86-104">At some point, you might need to rename an extractor if you want to refer to an extracted data field by a different name.</span></span> <span data-ttu-id="55e86-105">例如，你的组织决定更改合同文档，并在文档中将“Customer” 称为 “Client”。</span><span class="sxs-lookup"><span data-stu-id="55e86-105">For example, your organization decides to make changes to their contract documents, and refers to “customers” as “clients” in their documents.</span></span> <span data-ttu-id="55e86-106">如果你正在模型中提取 “Customer” 字段，可以选择将其重命名为 “Client”。</span><span class="sxs-lookup"><span data-stu-id="55e86-106">If you were extracting a “Customer” field in your model, you can choose to rename it to “Client.”</span></span>

<span data-ttu-id="55e86-107">将更新后的模型同步到 SharePoint 文档库时，文档库视图中将显示新的 “Client” 列。</span><span class="sxs-lookup"><span data-stu-id="55e86-107">When you sync your updated model to your SharePoint document library, you will see a new “Client” column in your document library view.</span></span> <span data-ttu-id="55e86-108">对于过往活动，视图将保留 “Customer” 列，但对于模型处理的所有新文档，将更新新的 “Client” 列。</span><span class="sxs-lookup"><span data-stu-id="55e86-108">Your view will retain the “Customer” column for past activity, but will update the new “Client” column for all new documents that are processed by your model.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="55e86-109">请确保将更新后的模型同步到之前应用于显示新列名称的文档库。</span><span class="sxs-lookup"><span data-stu-id="55e86-109">Make sure to sync your updated model to the document libraries where you had previously applied it for the new column name to display.</span></span> 

## <a name="rename-an-extractor"></a><span data-ttu-id="55e86-110">重命名提取程序</span><span class="sxs-lookup"><span data-stu-id="55e86-110">Rename an extractor</span></span>

<span data-ttu-id="55e86-111">请按照以下步骤重命名实体提取程序。</span><span class="sxs-lookup"><span data-stu-id="55e86-111">Follow these steps to rename an entity extractor.</span></span>

1. <span data-ttu-id="55e86-112">从内容中心中，选择“**模型**”，查看你的模型列表。</span><span class="sxs-lookup"><span data-stu-id="55e86-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="55e86-113">在“**模型**”页面的“**名称**”列中，选择希望为其重命名提取程序的模型。</span><span class="sxs-lookup"><span data-stu-id="55e86-113">On the **Models** page, in the **Name** column, select the model for which you want to rename an extractor.</span></span>

3. <span data-ttu-id="55e86-114">在“**实体提取程序**”下面，选择希望重命名的提取程序的名称，然后选择“**重命名**”。</span><span class="sxs-lookup"><span data-stu-id="55e86-114">Under **Entity extractors**, select the name of the extractor you want to rename, and then select **Rename**.</span></span></br>

    ![实体提取程序部分的屏幕截图显示了所选的提取程序，其中突出显示“重命名”选项。](../media/content-understanding/entity-extractor-rename.png) </br>

4. <span data-ttu-id="55e86-116">在“**重命名提取程序**”面板中:</span><span class="sxs-lookup"><span data-stu-id="55e86-116">On the **Rename entity extractor** panel:</span></span>

   <span data-ttu-id="55e86-117">a.</span><span class="sxs-lookup"><span data-stu-id="55e86-117">a.</span></span> <span data-ttu-id="55e86-118">在“**名称**”下面，输入提取程序的新名称。</span><span class="sxs-lookup"><span data-stu-id="55e86-118">Under **New name**, enter the new name of the extractor.</span></span></br>

    ![屏幕截图显示了“实体”提取程序面板。](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   <span data-ttu-id="55e86-120">b.</span><span class="sxs-lookup"><span data-stu-id="55e86-120">b.</span></span> <span data-ttu-id="55e86-121">(可选)在“**高级设置**”下，选择是否希望关联现有站网站栏。</span><span class="sxs-lookup"><span data-stu-id="55e86-121">(Optional) Under **Advanced settings**, select whether you want to associate an existing site column.</span></span>

5. <span data-ttu-id="55e86-122">选择“**重命名**”。</span><span class="sxs-lookup"><span data-stu-id="55e86-122">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="55e86-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55e86-123">See Also</span></span>
[<span data-ttu-id="55e86-124">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="55e86-124">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="55e86-125">创建分类器</span><span class="sxs-lookup"><span data-stu-id="55e86-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="55e86-126">重命名模型</span><span class="sxs-lookup"><span data-stu-id="55e86-126">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="55e86-127">说明类型</span><span class="sxs-lookup"><span data-stu-id="55e86-127">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="55e86-128">创建提取程序时利用术语库分类</span><span class="sxs-lookup"><span data-stu-id="55e86-128">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="55e86-129">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="55e86-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="55e86-130">应用模型</span><span class="sxs-lookup"><span data-stu-id="55e86-130">Apply a model</span></span>](apply-a-model.md) 
