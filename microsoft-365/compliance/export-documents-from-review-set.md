---
title: 从审阅集中导出文档
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何从审阅集中选择和导出或下载内容以进行演示文稿或外部审阅。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 29c2224a1ce0a92bca3b2057352f6f82fdc7afde
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034090"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="78d2d-103">从审阅集中导出文档</span><span class="sxs-lookup"><span data-stu-id="78d2d-103">Export documents from a review set</span></span>

<span data-ttu-id="78d2d-104">您可以通过以下方法之一从审阅集导出演示文稿或外部审阅的内容：</span><span class="sxs-lookup"><span data-stu-id="78d2d-104">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="78d2d-105">下载文档</span><span class="sxs-lookup"><span data-stu-id="78d2d-105">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="78d2d-106">导出文档</span><span class="sxs-lookup"><span data-stu-id="78d2d-106">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="78d2d-107">从审阅集中下载文档</span><span class="sxs-lookup"><span data-stu-id="78d2d-107">Download documents from a review set</span></span>

<span data-ttu-id="78d2d-108">下载提供了一种从以本机格式的审阅集下载内容的简单方法。</span><span class="sxs-lookup"><span data-stu-id="78d2d-108">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="78d2d-109">它利用浏览器的数据传输功能，以便在下载准备就绪后会出现浏览器提示。</span><span class="sxs-lookup"><span data-stu-id="78d2d-109">It leverages the browser's data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="78d2d-110">使用此方法下载的文件将压缩到一个容器文件中，并将成为项目级文件。</span><span class="sxs-lookup"><span data-stu-id="78d2d-110">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="78d2d-111">这意味着，如果选择了附件，您将自动收到包含附件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="78d2d-111">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="78d2d-112">同样，如果您选择嵌入在 word 文档中的 excel 电子表格，您将收到嵌入 excel 电子表格的 word 文档。</span><span class="sxs-lookup"><span data-stu-id="78d2d-112">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="78d2d-113">已下载项目将保留上次修改日期，可将其视为文件属性。</span><span class="sxs-lookup"><span data-stu-id="78d2d-113">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="78d2d-114">若要从审阅集中下载内容，请先选择要下载的文件，然后选择 "操作" 菜单下的 "下载"。</span><span class="sxs-lookup"><span data-stu-id="78d2d-114">To download content from a review set, start by selecting the files you want to download then select "Download" under the Actions menu.</span></span>

![自动生成的计算机说明的屏幕截图](../media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="78d2d-116">从审阅集中导出文档</span><span class="sxs-lookup"><span data-stu-id="78d2d-116">Export documents from a review set</span></span>

<span data-ttu-id="78d2d-117">导出允许用户自定义下载包中包含的内容。</span><span class="sxs-lookup"><span data-stu-id="78d2d-117">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="78d2d-118">它提供具有以下设置的配置页：</span><span class="sxs-lookup"><span data-stu-id="78d2d-118">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="78d2d-119">元数据文件</span><span class="sxs-lookup"><span data-stu-id="78d2d-119">Metadata file</span></span>

<span data-ttu-id="78d2d-120">可以将其视为包含与导出文件相关联的元数据的 "加载文件"。</span><span class="sxs-lookup"><span data-stu-id="78d2d-120">This can be considered your "load file" that contains metadata associated with the files you export.</span></span> <span data-ttu-id="78d2d-121">有关元数据文件中可用的导出域的列表，请参阅[高级电子数据展示中的文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="78d2d-121">For a list of exported fields available in the metadata file, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="78d2d-122">此文件通常可由第三方工具引入。</span><span class="sxs-lookup"><span data-stu-id="78d2d-122">This file can typically be ingested by third-party tools.</span></span>

### <a name="tag-data"></a><span data-ttu-id="78d2d-123">标记数据</span><span class="sxs-lookup"><span data-stu-id="78d2d-123">Tag data</span></span>

<span data-ttu-id="78d2d-124">此内容将作为字段添加到元数据文件中。</span><span class="sxs-lookup"><span data-stu-id="78d2d-124">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="78d2d-125">它包含在审阅集中应用的所有标记信息。</span><span class="sxs-lookup"><span data-stu-id="78d2d-125">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="78d2d-126">文本文件</span><span class="sxs-lookup"><span data-stu-id="78d2d-126">Text files</span></span>

<span data-ttu-id="78d2d-127">可以为从评审集导出的每个文件生成文本文件。</span><span class="sxs-lookup"><span data-stu-id="78d2d-127">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="78d2d-128">通常，服务合作伙伴将这些文件作为 ingesting 数据的一部分由第三方工具提供。</span><span class="sxs-lookup"><span data-stu-id="78d2d-128">Often times these files are required by service partners as part of ingesting data into third-party tools.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="78d2d-129">编辑文件</span><span class="sxs-lookup"><span data-stu-id="78d2d-129">Redacted files</span></span>

<span data-ttu-id="78d2d-130">如果在审阅过程中生成编辑 PDF 文件，则这些文件在导出过程中可用。</span><span class="sxs-lookup"><span data-stu-id="78d2d-130">If redacted PDF files are generated during review, these files are available during export.</span></span> <span data-ttu-id="78d2d-131">您可以决定是仅导出本机文件，还是将需要密文的本机文件替换为包含实际密文的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="78d2d-131">You can decide whether to export native files only or to replace the native files that required redaction with the PDF files that contain the actual redactions.</span></span>

### <a name="export-location"></a><span data-ttu-id="78d2d-132">导出位置</span><span class="sxs-lookup"><span data-stu-id="78d2d-132">Export location</span></span>

<span data-ttu-id="78d2d-133">导出的内容将传递给 Microsoft 提供的 Azure blob，如果导出时提供了详细信息，则可以使用客户的 blob。</span><span class="sxs-lookup"><span data-stu-id="78d2d-133">Exported content is delivered to either a Microsoft provided Azure blob or a customer's blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="78d2d-134">导出结构</span><span class="sxs-lookup"><span data-stu-id="78d2d-134">Export structure</span></span>

<span data-ttu-id="78d2d-135">从审阅集导出内容时，将按以下结构组织内容。</span><span class="sxs-lookup"><span data-stu-id="78d2d-135">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="78d2d-136">根文件夹–下载 ID</span><span class="sxs-lookup"><span data-stu-id="78d2d-136">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="78d2d-137">Export\_load\_file .csv = metadata 文件</span><span class="sxs-lookup"><span data-stu-id="78d2d-137">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="78d2d-138">摘要 .txt = 带有导出统计信息的摘要文件</span><span class="sxs-lookup"><span data-stu-id="78d2d-138">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="78d2d-139">输入\_或本机\_文件 = 包含所有本机文件</span><span class="sxs-lookup"><span data-stu-id="78d2d-139">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="78d2d-140">错误\_文件 = 包含导出中包含的任何错误文件</span><span class="sxs-lookup"><span data-stu-id="78d2d-140">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="78d2d-141">ExtractionError –包含未从父文件正确提取的任何可用文件元数据的 csv</span><span class="sxs-lookup"><span data-stu-id="78d2d-141">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="78d2d-142">ProcessingError –包含处理错误的内容。</span><span class="sxs-lookup"><span data-stu-id="78d2d-142">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="78d2d-143">此内容是项目级别意味着，如果附件遇到处理错误，则包含附件的电子邮件将包含在此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="78d2d-143">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="78d2d-144">提取\_的\_文本文件 = 包含处理过程中生成的所有提取的文本文件。</span><span class="sxs-lookup"><span data-stu-id="78d2d-144">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>
