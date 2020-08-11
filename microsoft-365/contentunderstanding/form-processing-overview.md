---
title: '表单处理概述 (预览) '
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 Project Cortex 中的表单处理。
ms.openlocfilehash: dbea06cdf2dbb232a7ea48c78d7ea968dd18b9c0
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612722"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="10e7e-103">表单处理概述 (预览) </span><span class="sxs-lookup"><span data-stu-id="10e7e-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="10e7e-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="10e7e-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="10e7e-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="10e7e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="10e7e-106">Project Cortex 使用 Microsoft PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview)表单处理在 SharePoint 文档库中创建模型。</span><span class="sxs-lookup"><span data-stu-id="10e7e-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="10e7e-107">您可以使用 AI 生成器表单处理创建 AI 模型，这些模型使用机器学习技术来识别和提取结构化或半结构化文档（如窗体和发票）中的键值对和表数据。</span><span class="sxs-lookup"><span data-stu-id="10e7e-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like form and invoices.</span></span>

<span data-ttu-id="10e7e-108">通常情况下，公司会收到大量的发票以及来自各种来源（如邮件、传真、电子邮件或亲自）的发票。</span><span class="sxs-lookup"><span data-stu-id="10e7e-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="10e7e-109">处理这些文档并手动将其输入数据库可能需要花费大量时间。</span><span class="sxs-lookup"><span data-stu-id="10e7e-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="10e7e-110">通过使用 AI 提取文档中的文本、键/值对和表，表单处理将自动执行此过程。</span><span class="sxs-lookup"><span data-stu-id="10e7e-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="10e7e-111">例如，您可以创建一个表单处理模型，该模型将标识上载到文档库的所有采购订单文档。</span><span class="sxs-lookup"><span data-stu-id="10e7e-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="10e7e-112">从每个采购订单中，您可以提取并显示对您很重要的特定数据，如*PO 号*、*日期*或*总成本*。</span><span class="sxs-lookup"><span data-stu-id="10e7e-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="10e7e-113">您可以使用示例文件来培训模型，并定义要从表单中提取的信息。</span><span class="sxs-lookup"><span data-stu-id="10e7e-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="10e7e-114">您的文档的布局通过培训您的模型来了解。</span><span class="sxs-lookup"><span data-stu-id="10e7e-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="10e7e-115">您只需五个表单文档即可开始。</span><span class="sxs-lookup"><span data-stu-id="10e7e-115">You only need five form documents to get started.</span></span> <span data-ttu-id="10e7e-116">AI 建筑物将分析有关键值对的示例文件，还可以手动识别可能未检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="10e7e-116">AI building will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="10e7e-117">通过 AI 生成器，您可以在示例文件上测试模型的准确性。</span><span class="sxs-lookup"><span data-stu-id="10e7e-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="10e7e-118">在训练和发布模型之后，使用它创建一个在将文件上传到 SharePoint 文档库时运行的[电源自动化流](https://docs.microsoft.com/power-automate/getting-started)，并提取模型中已标识的数据。</span><span class="sxs-lookup"><span data-stu-id="10e7e-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that will run when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="10e7e-119">提取的数据将显示在模型的文档库视图中的列中。</span><span class="sxs-lookup"><span data-stu-id="10e7e-119">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="10e7e-120">Office 365 管理员需要为 SharePoint 文档库[启用表单处理](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding)，以便用户能够在其中[创建表单处理模型](create-a-form-processing-model.md)。</span><span class="sxs-lookup"><span data-stu-id="10e7e-120">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="10e7e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10e7e-121">See Also</span></span>
  
[<span data-ttu-id="10e7e-122">电源自动化文档</span><span class="sxs-lookup"><span data-stu-id="10e7e-122">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="10e7e-123">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="10e7e-123">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="10e7e-124">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="10e7e-124">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="10e7e-125">培训：使用 AI 生成器改进业务绩效</span><span class="sxs-lookup"><span data-stu-id="10e7e-125">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




