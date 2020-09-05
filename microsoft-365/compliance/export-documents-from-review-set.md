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
description: 了解如何从审阅集中选择和导出内容以进行演示文稿或外部审阅。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 855f1b8fef7a1df6ed86f058b71e5027851b5f0d
ms.sourcegitcommit: 37ce0658336bea7b27bf8d6aa759deadc97e7365
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2020
ms.locfileid: "47399170"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="88af2-103">从审阅集中导出文档</span><span class="sxs-lookup"><span data-stu-id="88af2-103">Export documents from a review set</span></span>

<span data-ttu-id="88af2-104">导出允许用户自定义下载包中包含的内容。</span><span class="sxs-lookup"><span data-stu-id="88af2-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="88af2-105">导出工具提供了具有以下设置的配置页：</span><span class="sxs-lookup"><span data-stu-id="88af2-105">The Export tool provides a configuration page with the following settings:</span></span>

![用于从审阅集中导出项目的选项](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="88af2-107">导出选项</span><span class="sxs-lookup"><span data-stu-id="88af2-107">Export options</span></span>

- <span data-ttu-id="88af2-108">导出名称：导出作业的名称。</span><span class="sxs-lookup"><span data-stu-id="88af2-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="88af2-109">说明：用于添加说明的自由文本字段。</span><span class="sxs-lookup"><span data-stu-id="88af2-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="88af2-110">导出这些文档：</span><span class="sxs-lookup"><span data-stu-id="88af2-110">Export these documents:</span></span>

  - <span data-ttu-id="88af2-111">仅选定文档-仅导出当前选定的文档。</span><span class="sxs-lookup"><span data-stu-id="88af2-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="88af2-112">审阅集内的所有文档-导出审阅集中的所有文档</span><span class="sxs-lookup"><span data-stu-id="88af2-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="88af2-113">元数据</span><span class="sxs-lookup"><span data-stu-id="88af2-113">Metadata</span></span>
  
  - <span data-ttu-id="88af2-114">加载文件-此文件包含每个文件的元数据。</span><span class="sxs-lookup"><span data-stu-id="88af2-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="88af2-115">有关包含哪些字段的详细信息，请参阅 [高级电子数据展示中的文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md) 。</span><span class="sxs-lookup"><span data-stu-id="88af2-115">see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) for more information about what fields are included.</span></span> <span data-ttu-id="88af2-116">此文件通常可由第三方电子数据展示工具引入。</span><span class="sxs-lookup"><span data-stu-id="88af2-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="88af2-117">标记-如果选择此选项，则会将标记信息包含在加载文件中。</span><span class="sxs-lookup"><span data-stu-id="88af2-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="88af2-118">内容</span><span class="sxs-lookup"><span data-stu-id="88af2-118">Content</span></span>
  
  - <span data-ttu-id="88af2-119">本机文件-选中此复选框可包含本机文件。</span><span class="sxs-lookup"><span data-stu-id="88af2-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="88af2-120">对话选项</span><span class="sxs-lookup"><span data-stu-id="88af2-120">Conversation options</span></span>
    
    - <span data-ttu-id="88af2-121">会话文件-导出会重建聊天消息。</span><span class="sxs-lookup"><span data-stu-id="88af2-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="88af2-122">此格式以类似于用户在本机应用程序中看到的内容的形式显示对话。</span><span class="sxs-lookup"><span data-stu-id="88af2-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="88af2-123">单个聊天邮件-在 Microsoft 365 中存储原始对话文件时将其导出。</span><span class="sxs-lookup"><span data-stu-id="88af2-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="88af2-124">选项</span><span class="sxs-lookup"><span data-stu-id="88af2-124">Options</span></span>

  - <span data-ttu-id="88af2-125">文本文件-包括已提取的本机文件的文本版本。</span><span class="sxs-lookup"><span data-stu-id="88af2-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="88af2-126">将编辑 natives 替换为转换后的 Pdf-如果在审阅过程中生成编辑 PDF 文件，则可使用这些文件进行导出。</span><span class="sxs-lookup"><span data-stu-id="88af2-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="88af2-127">您可以选择仅导出编辑 (的本机文件，而不选择此选项) 也可以选择此选项导出包含实际密文的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="88af2-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="88af2-128"> (导出内容的输出选项可通过 web 浏览器直接下载，也可发送到 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="88af2-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="88af2-129">前两个选项启用直接下载。 ) </span><span class="sxs-lookup"><span data-stu-id="88af2-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="88af2-130">如果可能) 文件以用户的本机应用程序中显示的原始目录结构的格式导出，则会将松散文件和 Pst (电子邮件添加到 Pst。</span><span class="sxs-lookup"><span data-stu-id="88af2-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="88af2-131">有关详细信息，请参阅 " [松散文件和 PST 导出结构](#loose-files-and-pst-export-structure) " 部分。</span><span class="sxs-lookup"><span data-stu-id="88af2-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="88af2-132">紧缩目录结构-导出文件并将其包含在下载内容中。</span><span class="sxs-lookup"><span data-stu-id="88af2-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="88af2-133">导出到 Azure 存储帐户的紧缩目录结构-文件将导出到您的组织的 Azure 存储 accouunt。</span><span class="sxs-lookup"><span data-stu-id="88af2-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage accouunt.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="88af2-134">松散文件和 PST 导出结构</span><span class="sxs-lookup"><span data-stu-id="88af2-134">Loose files and PST export structure</span></span>

<span data-ttu-id="88af2-135">如果选择此导出选项，则导出的内容将按以下结构进行组织：</span><span class="sxs-lookup"><span data-stu-id="88af2-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="88af2-136">根文件夹–命名 ExportName.zip 中的此文件夹</span><span class="sxs-lookup"><span data-stu-id="88af2-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="88af2-137">Export_load_file.csv 元数据文件。</span><span class="sxs-lookup"><span data-stu-id="88af2-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="88af2-138">Summary.csv-也包含导出统计信息的摘要文件。</span><span class="sxs-lookup"><span data-stu-id="88af2-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="88af2-139">Exchange-此文件夹包含本机文件格式的 Exchange 中的所有内容。</span><span class="sxs-lookup"><span data-stu-id="88af2-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="88af2-140">如果选择 "将 **编辑 Natives 替换为转换的 pdf** " 选项，Natives 文件将被替换为编辑 pdf。</span><span class="sxs-lookup"><span data-stu-id="88af2-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="88af2-141">SharePoint = 此文件夹以本机文件格式包含来自 SharePoint 的所有本机内容。</span><span class="sxs-lookup"><span data-stu-id="88af2-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="88af2-142">如果选择 "将 **编辑 Natives 替换为转换的 pdf** " 选项，Natives 文件将被替换为编辑 pdf。</span><span class="sxs-lookup"><span data-stu-id="88af2-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="88af2-143">紧缩目录结构</span><span class="sxs-lookup"><span data-stu-id="88af2-143">Condensed directory structure</span></span>

- <span data-ttu-id="88af2-144">根文件夹-此文件夹命名为 ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="88af2-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="88af2-145">Export_load_file.csv 元数据文件。</span><span class="sxs-lookup"><span data-stu-id="88af2-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="88af2-146">Summary.txt-也包含导出统计信息的摘要文件。</span><span class="sxs-lookup"><span data-stu-id="88af2-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="88af2-147">Input_or_native_files-此文件夹包含导出的所有本机文件。</span><span class="sxs-lookup"><span data-stu-id="88af2-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="88af2-148">如果您导出编辑 PDF 文件，则它们不会放入 PST 文件中。</span><span class="sxs-lookup"><span data-stu-id="88af2-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="88af2-149">相反，它们将被添加到一个单独的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="88af2-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="88af2-150">Error_files-此文件夹包含以下错误文件（如果导出中包含这些文件）：</span><span class="sxs-lookup"><span data-stu-id="88af2-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="88af2-151">ExtractionError.</span><span class="sxs-lookup"><span data-stu-id="88af2-151">ExtractionError.</span></span> <span data-ttu-id="88af2-152">一个 CSV 文件，其中包含未从父文件正确提取的任何可用的文件元数据。</span><span class="sxs-lookup"><span data-stu-id="88af2-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="88af2-153">ProcessingError –此文件包含有处理错误的文档列表。</span><span class="sxs-lookup"><span data-stu-id="88af2-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="88af2-154">此内容是项目级的，这意味着如果附件导致处理错误，则包含附件的电子邮件将包含在此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="88af2-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="88af2-155">Extracted_text_files-此文件夹包含在处理过程中生成的所有提取的文本文件。</span><span class="sxs-lookup"><span data-stu-id="88af2-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="88af2-156">导出作业在案例的生命周期内保留，并且在不删除该事例的情况下可进行下载。</span><span class="sxs-lookup"><span data-stu-id="88af2-156">Export jobs are retained for the life of the case and can be downloaded as long as the case isn't deleted.</span></span>
