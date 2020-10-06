---
title: 表单处理概述
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 了解 Microsoft SharePoint Syntex 中的表单处理
ms.openlocfilehash: 9b5b9b1c54220037e1c10f2722a641b526592f84
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338609"
---
# <a name="form-processing-overview"></a><span data-ttu-id="02ac5-103">表单处理概述</span><span class="sxs-lookup"><span data-stu-id="02ac5-103">Form processing overview</span></span>

 ![AI 生成器](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="02ac5-105">Microsoft SharePoint Syntex 使用 Microsoft PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview)表单处理在 SharePoint 文档库中创建模型。</span><span class="sxs-lookup"><span data-stu-id="02ac5-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="02ac5-106">可使用 AI 生成器表单处理创建使用机器学习技术标识和提取结构化或半结构化文档（如表单和发票）中的键值对和表格数据的 AI 模型。</span><span class="sxs-lookup"><span data-stu-id="02ac5-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="02ac5-107">组织通常从多种来源（如邮件、传真、电子邮件等）接收大量发票。处理这些文档并手动将其输入到数据库中可能需要花费大量时间。</span><span class="sxs-lookup"><span data-stu-id="02ac5-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="02ac5-108">通过使用 AI 提取文档中的文本、键/值对和表格，表单处理可自动执行此过程。</span><span class="sxs-lookup"><span data-stu-id="02ac5-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="02ac5-109">有关表单处理方案示例的详细信息，请参阅 [SharePoint Syntex 采用：入门指南](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)。</span><span class="sxs-lookup"><span data-stu-id="02ac5-109">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="02ac5-110">例如，可以创建一个表单处理模型来标识上传到文档库的所有采购订单文档。</span><span class="sxs-lookup"><span data-stu-id="02ac5-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="02ac5-111">可从每个采购订单提取并显示对你非常重要的特定数据，如 *PO 编号*、 *日期*或*总成本*。</span><span class="sxs-lookup"><span data-stu-id="02ac5-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![文档库视图](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="02ac5-113">你也可以使用示例文件来训练模型，并定义将从表单提取的信息。</span><span class="sxs-lookup"><span data-stu-id="02ac5-113">You can also use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="02ac5-114">通过训练模型来学习文档的布局，它将学习如何从表单中的类似位置提取数据，因为它们具有类似的结构化布局。</span><span class="sxs-lookup"><span data-stu-id="02ac5-114">The layout of your document is learned by training your model, and it learns to extract your data from similar locations in your forms since they have a similar structured layout.</span></span> 

<span data-ttu-id="02ac5-115">至少需要 5 个表单文档才能开始操作。</span><span class="sxs-lookup"><span data-stu-id="02ac5-115">You need a minimum of five form documents to get started.</span></span> <span data-ttu-id="02ac5-116">AI 构建分析示例文件中的键 - 值对，然后手动识别可能没有检测到的键 - 值对。</span><span class="sxs-lookup"><span data-stu-id="02ac5-116">AI building analyzes your example files for key-value pairs, and then manually identifies the ones that may not have been detected.</span></span>  <span data-ttu-id="02ac5-117">可通过 AI 生成器测试示例文件的模型准确性。</span><span class="sxs-lookup"><span data-stu-id="02ac5-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="02ac5-118">训练和发布模型后，使用它来创建将文件上传到 SharePoint 文档库后运行的 [Power Automate 流程](https://docs.microsoft.com/power-automate/getting-started)。</span><span class="sxs-lookup"><span data-stu-id="02ac5-118">After you train and publish your model, use it to create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that runs after a file is uploaded to the SharePoint document library.</span></span> <span data-ttu-id="02ac5-119">然后提取模型中标识的数据。</span><span class="sxs-lookup"><span data-stu-id="02ac5-119">It then extracts data that has been identified in the model.</span></span> <span data-ttu-id="02ac5-120">提取的数据将显示在模型的文档库视图的列中。</span><span class="sxs-lookup"><span data-stu-id="02ac5-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="02ac5-121">你可以使用示例文件来训练模型，并定义将从表单提取的信息。</span><span class="sxs-lookup"><span data-stu-id="02ac5-121">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="02ac5-122">文档的布局通过培训你的模型获知。</span><span class="sxs-lookup"><span data-stu-id="02ac5-122">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="02ac5-123">只需 5 个表单文档即可开始操作。</span><span class="sxs-lookup"><span data-stu-id="02ac5-123">You only need five form documents to get started.</span></span> <span data-ttu-id="02ac5-124">AI 生成器将分析示例文件中的键 - 值对，你也可以手动识别可能没有检测到的键 - 值对。</span><span class="sxs-lookup"><span data-stu-id="02ac5-124">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="02ac5-125">可通过 AI 生成器测试示例文件的模型准确性。</span><span class="sxs-lookup"><span data-stu-id="02ac5-125">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="02ac5-126">训练并发布模型后，模型将创建 [Power Automate 流程](https://docs.microsoft.com/power-automate/getting-started)。</span><span class="sxs-lookup"><span data-stu-id="02ac5-126">After you train and publish your model, your model creates a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="02ac5-127">将文件上传到 SharePoint 文档库时将运行该流程，并提取模型中标识的数据。</span><span class="sxs-lookup"><span data-stu-id="02ac5-127">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="02ac5-128">提取的数据将显示在模型的文档库视图的列中。</span><span class="sxs-lookup"><span data-stu-id="02ac5-128">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="02ac5-129">Office 365 管理员需要为 SharePoint 文档库[启用表单处理](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) ，以便用户能够从中 [创建表单处理模型](create-a-form-processing-model.md)。</span><span class="sxs-lookup"><span data-stu-id="02ac5-129">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="02ac5-130">设置过程中或设置完成后，可在管理设置中选择网站。</span><span class="sxs-lookup"><span data-stu-id="02ac5-130">You can select the sites during setup, or after setup in your management settings.</span></span>



## <a name="see-also"></a><span data-ttu-id="02ac5-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02ac5-131">See Also</span></span>
  
[<span data-ttu-id="02ac5-132">Power Automate 流程</span><span class="sxs-lookup"><span data-stu-id="02ac5-132">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="02ac5-133">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="02ac5-133">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="02ac5-134">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="02ac5-134">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="02ac5-135">培训：使用 AI 生成器提高业务绩效</span><span class="sxs-lookup"><span data-stu-id="02ac5-135">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
