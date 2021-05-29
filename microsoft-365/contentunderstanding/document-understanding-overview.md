---
title: 文档理解概述
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 获取 Microsoft SharePoint Syntex 中的文档理解概述。
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683819"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="525c7-103">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="525c7-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="525c7-104">文档理解使用人工智能 (AI) 模型自动对文件和提取信息进行分类。</span><span class="sxs-lookup"><span data-stu-id="525c7-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="525c7-105">它最适用于非结构化文档，例如字母或协定。</span><span class="sxs-lookup"><span data-stu-id="525c7-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="525c7-106">这些文档必须包含可以根据短语或图案进行识别的文本。</span><span class="sxs-lookup"><span data-stu-id="525c7-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="525c7-107">标识的文本将指定文件类型（分类）和要提取的内容（提取程序）。</span><span class="sxs-lookup"><span data-stu-id="525c7-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="525c7-108">有关文档理解方案示例的详细信息，请参阅 [SharePoint Syntex 采用：入门指南](./adoption-getstarted.md)。</span><span class="sxs-lookup"><span data-stu-id="525c7-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="525c7-109">文档理解模型在一种称为 *内容中心* 的 SharePoint 网站中创建和管理。</span><span class="sxs-lookup"><span data-stu-id="525c7-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="525c7-110">应用于 SharePoint 文档库时，该模型与内容类型关联，包含用于存储所提取信息的列。</span><span class="sxs-lookup"><span data-stu-id="525c7-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="525c7-111">你创建的内容类型存储在 SharePoint 内容类型库中。</span><span class="sxs-lookup"><span data-stu-id="525c7-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="525c7-112">也可以选择使用现有内容类型来使用其架构。</span><span class="sxs-lookup"><span data-stu-id="525c7-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="525c7-113">只读或密封的内容类型无法更新，因此不能在模型中使用。</span><span class="sxs-lookup"><span data-stu-id="525c7-113">Read-only or sealed content types cannot be updated, so they can't be used in a model.</span></span>

<span data-ttu-id="525c7-114">向文档理解模型添加 *分类器* 和 *提取器* 以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="525c7-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="525c7-115">分类器用于识别上载到文档库的文档并对其进行分类。</span><span class="sxs-lookup"><span data-stu-id="525c7-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="525c7-116">例如，一个分类器可通过“训练有素”来标识上载到库的所有 *合同续订* 文档。</span><span class="sxs-lookup"><span data-stu-id="525c7-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="525c7-117">当你创建分类器时，合同续订内容类型由你定义。</span><span class="sxs-lookup"><span data-stu-id="525c7-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="525c7-118">提取器从这些文档提取信息。</span><span class="sxs-lookup"><span data-stu-id="525c7-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="525c7-119">例如，对于文档库中标识的所有合同续订文档，将在视图中显示每个合同续订文档的 *服务开始日期* 和 *客户*。</span><span class="sxs-lookup"><span data-stu-id="525c7-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="525c7-120">可使用示例文件在模型中培训并测试分类器和提取器。</span><span class="sxs-lookup"><span data-stu-id="525c7-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="525c7-121">示例文件提供了有关尝试从文件识别和提取数据时要查找的内容的模型示例。</span><span class="sxs-lookup"><span data-stu-id="525c7-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="525c7-122">例如，你将使用公司使用的合同续订文档的示例来训练你的合同续订分类和提取器。</span><span class="sxs-lookup"><span data-stu-id="525c7-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="525c7-123">还可以使用示例文件来测试模型的有效性。</span><span class="sxs-lookup"><span data-stu-id="525c7-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="525c7-124">发布模型后，请使用内容中心将其应用到你有权访问的任何 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="525c7-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="file-limitations"></a><span data-ttu-id="525c7-125">文件限制</span><span class="sxs-lookup"><span data-stu-id="525c7-125">File limitations</span></span>

<span data-ttu-id="525c7-126">了解模型时，在通过光学字符识别 （OCR） 技术扫描 PDF、图像和 TIFF 文件时，包括当使用示例文件对模型进行训练时，以及针对文档库中的文件运行模型时。</span><span class="sxs-lookup"><span data-stu-id="525c7-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="525c7-127">请注意以下与 Microsoft Office 基于文本的文件和 OCR 扫描文件（PDF、图像或 TIFF）有关的差异：</span><span class="sxs-lookup"><span data-stu-id="525c7-127">Note the following differences with regard to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="525c7-128">Office 文件：截断为 64,000 个字符（在培训中以及针对文档库中的文件运行时）。</span><span class="sxs-lookup"><span data-stu-id="525c7-128">Office files: Truncated at 64,000 characters (in training and when run against files in a document library).</span></span>

- <span data-ttu-id="525c7-129">OCR 扫描的文件：存在 20 个页面限制。</span><span class="sxs-lookup"><span data-stu-id="525c7-129">OCR-scanned files: There's a 20-page limit.</span></span>  

### <a name="requirements"></a><span data-ttu-id="525c7-130">要求</span><span class="sxs-lookup"><span data-stu-id="525c7-130">Requirements</span></span>

<span data-ttu-id="525c7-131">OCR 处理最适用于满足下列要求的文档：</span><span class="sxs-lookup"><span data-stu-id="525c7-131">OCR processing works best on documents that meet the following requirements:</span></span>

- <span data-ttu-id="525c7-132">JPG、PNG 或 PDF 格式（文本或扫描）。</span><span class="sxs-lookup"><span data-stu-id="525c7-132">JPG, PNG, or PDF format (text or scanned).</span></span> <span data-ttu-id="525c7-133">最好使用文本嵌入的 PDF，因为字符提取和位置中不会存在任何错误。</span><span class="sxs-lookup"><span data-stu-id="525c7-133">Text-embedded PDFs are better, because there won't be any errors in character extraction and location.</span></span>

- <span data-ttu-id="525c7-134">如果 PDF 是密码锁定的，必须在提交前解除锁定。</span><span class="sxs-lookup"><span data-stu-id="525c7-134">If your PDFs are password-locked, you must remove the lock before submitting them.</span></span>

- <span data-ttu-id="525c7-135">每个集合用于培训的文档合并文件大小不得超过 50 MB，并且 PDF 文档不能超过 500 页。</span><span class="sxs-lookup"><span data-stu-id="525c7-135">The combined file size of the documents used for training per collection must not exceed 50 MB, and PDF documents shouldn't have more than 500 pages.</span></span>

- <span data-ttu-id="525c7-136">对于图像，尺寸必须在 50 × 50 到 10,000 × 10,000 像素之间。</span><span class="sxs-lookup"><span data-stu-id="525c7-136">For images, dimensions must be between 50 × 50 and 10,000 × 10,000 pixels.</span></span>
   > [!NOTE]
   > <span data-ttu-id="525c7-137">具有非常宽或特殊尺寸（例如平面图）的图像可能在 OCR 过程中截断，并且会失去准确性。</span><span class="sxs-lookup"><span data-stu-id="525c7-137">Images that are very wide or have odd dimensions (for example, floor plans) might get truncated in the OCR process and lose accuracy.</span></span>
 
- <span data-ttu-id="525c7-138">对于 PDF 文件，尺寸必须为最大 17 x 17 英寸，相当于 Legal 或 A3 纸张大小或更小。</span><span class="sxs-lookup"><span data-stu-id="525c7-138">For PDF files, dimensions must be at most 17 x 17 inches, corresponding to Legal or A3 paper sizes and smaller.</span></span>

- <span data-ttu-id="525c7-139">如果从纸质文档扫描，则扫描内容应为高质量图像。</span><span class="sxs-lookup"><span data-stu-id="525c7-139">If scanned from paper documents, scans should be high-quality images.</span></span>

- <span data-ttu-id="525c7-140">必须使用拉丁语字母（英文字符）。</span><span class="sxs-lookup"><span data-stu-id="525c7-140">Must use the Latin alphabet (English characters).</span></span>

> [!NOTE]
> <span data-ttu-id="525c7-141">AI 生成器当前不支持以下类型的表单处理输入数据：</span><span class="sxs-lookup"><span data-stu-id="525c7-141">AI Builder doesn't currently support the following types of form processing input data:</span></span><br><span data-ttu-id="525c7-142">- 复选框或单选按钮</span><span class="sxs-lookup"><span data-stu-id="525c7-142">- Check boxes or radio buttons</span></span><br><span data-ttu-id="525c7-143">- 签名</span><span class="sxs-lookup"><span data-stu-id="525c7-143">- Signatures</span></span><br><span data-ttu-id="525c7-144">- 可填充的 PDF</span><span class="sxs-lookup"><span data-stu-id="525c7-144">- Fillable PDFs</span></span>

### <a name="supported-file-types"></a><span data-ttu-id="525c7-145">支持的文件类型</span><span class="sxs-lookup"><span data-stu-id="525c7-145">Supported file types</span></span>

<span data-ttu-id="525c7-146">了解文档模型支持以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="525c7-146">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="525c7-147">doc</span><span class="sxs-lookup"><span data-stu-id="525c7-147">doc</span></span>
- <span data-ttu-id="525c7-148">docx</span><span class="sxs-lookup"><span data-stu-id="525c7-148">docx</span></span>
- <span data-ttu-id="525c7-149">eml</span><span class="sxs-lookup"><span data-stu-id="525c7-149">eml</span></span>
- <span data-ttu-id="525c7-150">Heic</span><span class="sxs-lookup"><span data-stu-id="525c7-150">heic</span></span>
- <span data-ttu-id="525c7-151">Heif</span><span class="sxs-lookup"><span data-stu-id="525c7-151">heif</span></span>
- <span data-ttu-id="525c7-152">htm</span><span class="sxs-lookup"><span data-stu-id="525c7-152">htm</span></span>
- <span data-ttu-id="525c7-153">html</span><span class="sxs-lookup"><span data-stu-id="525c7-153">html</span></span>
- <span data-ttu-id="525c7-154">jpeg</span><span class="sxs-lookup"><span data-stu-id="525c7-154">jpeg</span></span>
- <span data-ttu-id="525c7-155">jpg</span><span class="sxs-lookup"><span data-stu-id="525c7-155">jpg</span></span>
- <span data-ttu-id="525c7-156">markdown</span><span class="sxs-lookup"><span data-stu-id="525c7-156">markdown</span></span>
- <span data-ttu-id="525c7-157">md</span><span class="sxs-lookup"><span data-stu-id="525c7-157">md</span></span>
- <span data-ttu-id="525c7-158">msg</span><span class="sxs-lookup"><span data-stu-id="525c7-158">msg</span></span>
- <span data-ttu-id="525c7-159">pdf</span><span class="sxs-lookup"><span data-stu-id="525c7-159">pdf</span></span>
- <span data-ttu-id="525c7-160">png</span><span class="sxs-lookup"><span data-stu-id="525c7-160">png</span></span>
- <span data-ttu-id="525c7-161">ppt</span><span class="sxs-lookup"><span data-stu-id="525c7-161">ppt</span></span>
- <span data-ttu-id="525c7-162">pptx</span><span class="sxs-lookup"><span data-stu-id="525c7-162">pptx</span></span>
- <span data-ttu-id="525c7-163">rtf</span><span class="sxs-lookup"><span data-stu-id="525c7-163">rtf</span></span>
- <span data-ttu-id="525c7-164">tif</span><span class="sxs-lookup"><span data-stu-id="525c7-164">tif</span></span>
- <span data-ttu-id="525c7-165">tiff</span><span class="sxs-lookup"><span data-stu-id="525c7-165">tiff</span></span>
- <span data-ttu-id="525c7-166">txt</span><span class="sxs-lookup"><span data-stu-id="525c7-166">txt</span></span>
- <span data-ttu-id="525c7-167">xls</span><span class="sxs-lookup"><span data-stu-id="525c7-167">xls</span></span>
- <span data-ttu-id="525c7-168">xlsx</span><span class="sxs-lookup"><span data-stu-id="525c7-168">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="525c7-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="525c7-169">See Also</span></span>
[<span data-ttu-id="525c7-170">创建分类器</span><span class="sxs-lookup"><span data-stu-id="525c7-170">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="525c7-171">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="525c7-171">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="525c7-172">创建内容中心</span><span class="sxs-lookup"><span data-stu-id="525c7-172">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="525c7-173">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="525c7-173">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="525c7-174">应用模型</span><span class="sxs-lookup"><span data-stu-id="525c7-174">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="525c7-175">文档理解与表单处理模型之间的差异</span><span class="sxs-lookup"><span data-stu-id="525c7-175">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="525c7-176">表单处理概述</span><span class="sxs-lookup"><span data-stu-id="525c7-176">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="525c7-177">SharePoint 整合辅助功能模式</span><span class="sxs-lookup"><span data-stu-id="525c7-177">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)