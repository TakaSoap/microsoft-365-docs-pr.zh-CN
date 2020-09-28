---
title: 表单处理概述
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 Microsoft SharePoint Syntex 中的表单处理
ms.openlocfilehash: 518bc13017762bbe21420a81726e89c9c327834d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295172"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="db6dd-103">表单处理概述 (预览) </span><span class="sxs-lookup"><span data-stu-id="db6dd-103">Form Processing overview (Preview)</span></span>

<span data-ttu-id="db6dd-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="db6dd-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="db6dd-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="db6dd-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="db6dd-106">Project Cortex 使用 Microsoft PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview) 表单处理在 SharePoint 文档库中创建模型。</span><span class="sxs-lookup"><span data-stu-id="db6dd-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="db6dd-107">您可以使用 AI 生成器表单处理创建 AI 模型，这些模型使用机器学习技术来识别和提取结构化或半结构化文档（如表单和发票）中的键值对和表数据。</span><span class="sxs-lookup"><span data-stu-id="db6dd-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="db6dd-108">使用 AI 生成器表单处理创建 AI 模型，该模型利用机器学习 (ML) 技术来识别和提取结构化或半结构化文档（例如表单和发票）中的键值对和表数据。</span><span class="sxs-lookup"><span data-stu-id="db6dd-108">Use AI Builder form processing to create AI models that utilize machine learning (ML) technology to identify and extract key-value pairs and table data from structured or semi-structured documents, such as form and invoices.</span></span>

<span data-ttu-id="db6dd-109">组织通常从各种源（如邮件、传真、电子邮件等）接收大量发票。处理这些文档并手动将其输入数据库可能需要花费大量时间。</span><span class="sxs-lookup"><span data-stu-id="db6dd-109">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="db6dd-110">通过使用 AI 提取文档中的文本、键/值对和表，表单处理可以自动执行此过程。</span><span class="sxs-lookup"><span data-stu-id="db6dd-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

<span data-ttu-id="db6dd-111">例如，您可以创建一个表单处理模型，用于标识上载到文档库的所有采购订单文档。</span><span class="sxs-lookup"><span data-stu-id="db6dd-111">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="db6dd-112">您可以从每个采购订单提取并显示对您很重要的特定数据，如 *PO 号*、 *日期*或 *总成本*。</span><span class="sxs-lookup"><span data-stu-id="db6dd-112">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="db6dd-113">您还可以使用示例文件来培训您的模型，并定义要从表单中提取的信息。</span><span class="sxs-lookup"><span data-stu-id="db6dd-113">You can also use sample files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="db6dd-114">您的文档的布局通过培训您的模型来了解。</span><span class="sxs-lookup"><span data-stu-id="db6dd-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="db6dd-115">至少需要5个表单文档才能开始。</span><span class="sxs-lookup"><span data-stu-id="db6dd-115">You need a minimum of five form documents to get started.</span></span> <span data-ttu-id="db6dd-116">AI 生成分析关键字值对的示例文件，然后手动标识可能未检测到的示例文件。</span><span class="sxs-lookup"><span data-stu-id="db6dd-116">AI building analyzes your sample files for key-value pairs, and then manually identifies the ones that may not have been detected.</span></span>  <span data-ttu-id="db6dd-117">通过 AI 生成器，您可以在示例文件上测试模型的准确性。</span><span class="sxs-lookup"><span data-stu-id="db6dd-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="db6dd-118">在训练和发布模型后，使用它创建在将文件上传到 SharePoint 文档库后运行的 [电源自动化流](https://docs.microsoft.com/power-automate/getting-started) 。</span><span class="sxs-lookup"><span data-stu-id="db6dd-118">After you train and publish your model, use it to create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that runs after a file is uploaded to the SharePoint document library.</span></span> <span data-ttu-id="db6dd-119">然后，它提取在模型中标识的数据。</span><span class="sxs-lookup"><span data-stu-id="db6dd-119">It then extracts data that has been identified in the model.</span></span> <span data-ttu-id="db6dd-120">提取的数据将显示在模型的文档库视图中的列中。</span><span class="sxs-lookup"><span data-stu-id="db6dd-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="db6dd-121">您可以使用示例文件来培训您的模型，并定义要从表单中提取的信息。</span><span class="sxs-lookup"><span data-stu-id="db6dd-121">You use sample files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="db6dd-122">您的文档的布局通过培训您的模型来了解。</span><span class="sxs-lookup"><span data-stu-id="db6dd-122">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="db6dd-123">您只需五个表单文档即可开始。</span><span class="sxs-lookup"><span data-stu-id="db6dd-123">You only need five form documents to get started.</span></span> <span data-ttu-id="db6dd-124">AI 生成器将分析示例文件的键值对，也可以手动识别可能未检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="db6dd-124">AI Builder will analyze your sample files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="db6dd-125">通过 AI 生成器，您可以在示例文件上测试模型的准确性。</span><span class="sxs-lookup"><span data-stu-id="db6dd-125">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="db6dd-126">在训练和发布模型后，使用它可以创建 [电源自动化流](https://docs.microsoft.com/power-automate/getting-started)。</span><span class="sxs-lookup"><span data-stu-id="db6dd-126">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="db6dd-127">将文件上传到 SharePoint 文档库时，会运行流，并提取模型中标识的数据。</span><span class="sxs-lookup"><span data-stu-id="db6dd-127">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="db6dd-128">提取的数据将显示在模型的文档库视图中的列中。</span><span class="sxs-lookup"><span data-stu-id="db6dd-128">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="db6dd-129">Office 365 管理员需要为 SharePoint 文档库 [启用表单处理](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) ，以便用户能够在其中 [创建表单处理模型](create-a-form-processing-model.md) 。</span><span class="sxs-lookup"><span data-stu-id="db6dd-129">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>

## <a name="see-also"></a><span data-ttu-id="db6dd-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db6dd-130">See Also</span></span>
  
[<span data-ttu-id="db6dd-131">电源自动化文档</span><span class="sxs-lookup"><span data-stu-id="db6dd-131">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="db6dd-132">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="db6dd-132">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="db6dd-133">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="db6dd-133">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="db6dd-134">培训：使用 AI 生成器改进业务绩效</span><span class="sxs-lookup"><span data-stu-id="db6dd-134">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
