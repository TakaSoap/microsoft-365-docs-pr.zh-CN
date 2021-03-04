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
description: 了解如何从演示文稿或外部审阅的审阅集选择和导出内容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a2ca8e2f400d9f257549e59305d1fd56586185e2
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423643"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="60f13-103">从高级电子数据展示中的审阅集导出文档</span><span class="sxs-lookup"><span data-stu-id="60f13-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="60f13-104">导出允许用户自定义下载包中包含的内容。</span><span class="sxs-lookup"><span data-stu-id="60f13-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="60f13-105">导出工具提供具有以下设置的配置页：</span><span class="sxs-lookup"><span data-stu-id="60f13-105">The Export tool provides a configuration page with the following settings:</span></span>

![用于从审阅集导出项目的选项](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="60f13-107">导出选项</span><span class="sxs-lookup"><span data-stu-id="60f13-107">Export options</span></span>

- <span data-ttu-id="60f13-108">导出名称：导出作业的名称。</span><span class="sxs-lookup"><span data-stu-id="60f13-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="60f13-109">说明：要添加说明的自定义文本字段。</span><span class="sxs-lookup"><span data-stu-id="60f13-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="60f13-110">导出以下文档：</span><span class="sxs-lookup"><span data-stu-id="60f13-110">Export these documents:</span></span>

  - <span data-ttu-id="60f13-111">仅选定文档 - 仅导出当前选择的文档。</span><span class="sxs-lookup"><span data-stu-id="60f13-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="60f13-112">审阅集内的所有文档 - 导出审阅集内的所有文档</span><span class="sxs-lookup"><span data-stu-id="60f13-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="60f13-113">Metadata</span><span class="sxs-lookup"><span data-stu-id="60f13-113">Metadata</span></span>
  
  - <span data-ttu-id="60f13-114">加载文件 - 此文件包含每个文件的元数据。</span><span class="sxs-lookup"><span data-stu-id="60f13-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="60f13-115">有关包含哪些字段的信息，请参阅高级电子数据展示中的 [文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="60f13-115">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="60f13-116">此文件通常由第三方电子数据展示工具进行提供。</span><span class="sxs-lookup"><span data-stu-id="60f13-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="60f13-117">标记 - 选中后，标记信息将包含在加载文件中。</span><span class="sxs-lookup"><span data-stu-id="60f13-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="60f13-118">内容</span><span class="sxs-lookup"><span data-stu-id="60f13-118">Content</span></span>
  
  - <span data-ttu-id="60f13-119">本机文件 - 选中此复选框可包含本机文件。</span><span class="sxs-lookup"><span data-stu-id="60f13-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="60f13-120">对话选项</span><span class="sxs-lookup"><span data-stu-id="60f13-120">Conversation options</span></span>
    
    - <span data-ttu-id="60f13-121">对话文件 - 导出重新构建的聊天消息。</span><span class="sxs-lookup"><span data-stu-id="60f13-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="60f13-122">此格式以类似于用户在本机应用程序中看到的内容的形式呈现对话。</span><span class="sxs-lookup"><span data-stu-id="60f13-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="60f13-123">单个聊天消息 - 导出存储在 Microsoft 365 中的原始对话文件。</span><span class="sxs-lookup"><span data-stu-id="60f13-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="60f13-124">选项</span><span class="sxs-lookup"><span data-stu-id="60f13-124">Options</span></span>

  - <span data-ttu-id="60f13-125">文本文件 - 包括本机文件的提取文本版本。</span><span class="sxs-lookup"><span data-stu-id="60f13-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="60f13-126">将修订的本机文件替换为转换后的 PDF - 如果在审阅期间生成修订的 PDF 文件，则这些文件可供导出。</span><span class="sxs-lookup"><span data-stu-id="60f13-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="60f13-127">可以选择仅导出已修订的本机文件 (不选择此选项) 也可以选择此选项以导出包含实际修订的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="60f13-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="60f13-128">导出 (的输出选项可通过 Web 浏览器直接下载，也可以发送到 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="60f13-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="60f13-129">前两个选项支持直接下载。) </span><span class="sxs-lookup"><span data-stu-id="60f13-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="60f13-130">如果可能 (，将松散文件和 PTS 添加到) PTS - 以类似于用户本机应用程序中看到的原始目录结构的格式导出文件。</span><span class="sxs-lookup"><span data-stu-id="60f13-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="60f13-131">有关详细信息，请参阅 ["Loose 文件和 PST 导出结构"](#loose-files-and-pst-export-structure) 部分。</span><span class="sxs-lookup"><span data-stu-id="60f13-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="60f13-132">压缩目录结构 - 导出文件并包含在下载中。</span><span class="sxs-lookup"><span data-stu-id="60f13-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="60f13-133">导出到 Azure 存储帐户的压缩目录结构 - 文件导出到组织的 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="60f13-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage account.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="60f13-134">松散文件和 PST 导出结构</span><span class="sxs-lookup"><span data-stu-id="60f13-134">Loose files and PST export structure</span></span>

<span data-ttu-id="60f13-135">如果选择此选项，导出的内容将按以下结构进行组织：</span><span class="sxs-lookup"><span data-stu-id="60f13-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="60f13-136">根文件夹 – 此文件夹的名称为 ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="60f13-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="60f13-137">Export_load_file.csv - 元数据文件。</span><span class="sxs-lookup"><span data-stu-id="60f13-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="60f13-138">Summary.csv - 还包含导出统计信息的摘要文件。</span><span class="sxs-lookup"><span data-stu-id="60f13-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="60f13-139">Exchange - 此文件夹包含来自 Exchange 的本机文件格式的所有内容。</span><span class="sxs-lookup"><span data-stu-id="60f13-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="60f13-140">如果选择"将已修订的本机文件替换为转换后的 PDF"选项，则本机文件 **将替换为修订的 PDF。**</span><span class="sxs-lookup"><span data-stu-id="60f13-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="60f13-141">SharePoint = 此文件夹包含 SharePoint 中采用本机文件格式的所有本机内容。</span><span class="sxs-lookup"><span data-stu-id="60f13-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="60f13-142">如果选择"将已修订的本机文件替换为转换后的 PDF"选项，则本机文件 **将替换为修订的 PDF。**</span><span class="sxs-lookup"><span data-stu-id="60f13-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="60f13-143">压缩目录结构</span><span class="sxs-lookup"><span data-stu-id="60f13-143">Condensed directory structure</span></span>

- <span data-ttu-id="60f13-144">根文件夹 - 此文件夹ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="60f13-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="60f13-145">Export_load_file.csv - 元数据文件。</span><span class="sxs-lookup"><span data-stu-id="60f13-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="60f13-146">Summary.txt - 还包含导出统计信息的摘要文件。</span><span class="sxs-lookup"><span data-stu-id="60f13-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="60f13-147">Input_or_native_files - 此文件夹包含导出的所有本机文件。</span><span class="sxs-lookup"><span data-stu-id="60f13-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="60f13-148">如果导出修订的 PDF 文件，则它们不会放入 PST 文件中。</span><span class="sxs-lookup"><span data-stu-id="60f13-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="60f13-149">相反，它们被添加到一个分隔的文件夹。</span><span class="sxs-lookup"><span data-stu-id="60f13-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="60f13-150">Error_files - 如果导出中包含此文件夹，则此文件夹包含以下错误文件：</span><span class="sxs-lookup"><span data-stu-id="60f13-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="60f13-151">ExtractionError。</span><span class="sxs-lookup"><span data-stu-id="60f13-151">ExtractionError.</span></span> <span data-ttu-id="60f13-152">包含未正确从父文件提取的任何可用文件的元数据的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="60f13-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="60f13-153">ProcessingError – 此文件包含包含处理错误的文档列表。</span><span class="sxs-lookup"><span data-stu-id="60f13-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="60f13-154">此内容为项目级别，这意味着如果附件导致处理错误，则包含附件的电子邮件将包含在此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="60f13-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="60f13-155">Extracted_text_files - 此文件夹包含处理时生成的所有提取的文本文件。</span><span class="sxs-lookup"><span data-stu-id="60f13-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="60f13-156">导出作业在案例的生命周期内保留。</span><span class="sxs-lookup"><span data-stu-id="60f13-156">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="60f13-157">但是，您必须在导出作业完成后的 30 天内从导出作业下载内容。</span><span class="sxs-lookup"><span data-stu-id="60f13-157">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>
