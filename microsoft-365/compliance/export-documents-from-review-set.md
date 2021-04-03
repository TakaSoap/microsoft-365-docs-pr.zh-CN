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
description: 了解如何从演示文稿或外部审阅的高级电子数据展示审阅集选择和导出内容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581012"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="62ed7-103">从高级电子数据展示中的审阅集导出文档</span><span class="sxs-lookup"><span data-stu-id="62ed7-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="62ed7-104">导出允许用户在从高级电子数据展示中的审阅集导出文档时自定义下载包中包含的内容。</span><span class="sxs-lookup"><span data-stu-id="62ed7-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="62ed7-105">从审阅集导出文档：</span><span class="sxs-lookup"><span data-stu-id="62ed7-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="62ed7-106">在 Microsoft 365 合规中心，打开"高级电子数据展示"案例，选择"审阅集"选项卡，然后选择要导出的审阅集。</span><span class="sxs-lookup"><span data-stu-id="62ed7-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="62ed7-107">在审阅集内，单击"操作 **导出**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="62ed7-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="62ed7-108">"导出"工具显示包含用于配置导出的设置的飞出页。</span><span class="sxs-lookup"><span data-stu-id="62ed7-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="62ed7-109">默认情况下会选择某些选项，但可以更改这些选项。</span><span class="sxs-lookup"><span data-stu-id="62ed7-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="62ed7-110">有关可以配置的导出选项的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="62ed7-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![用于从审阅集导出项目的配置选项](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="62ed7-112">配置导出后，单击" **导出** "开始导出过程。</span><span class="sxs-lookup"><span data-stu-id="62ed7-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="62ed7-113">根据在"输出选项"部分选择的选项，可以通过直接下载或组织的 Azure 存储帐户访问导出文件。</span><span class="sxs-lookup"><span data-stu-id="62ed7-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="62ed7-114">导出作业在案例的生命周期内保留。</span><span class="sxs-lookup"><span data-stu-id="62ed7-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="62ed7-115">但是，您必须在导出作业完成后的 30 天内从导出作业下载内容。</span><span class="sxs-lookup"><span data-stu-id="62ed7-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="62ed7-116">导出选项</span><span class="sxs-lookup"><span data-stu-id="62ed7-116">Export options</span></span>

<span data-ttu-id="62ed7-117">使用以下选项配置导出。</span><span class="sxs-lookup"><span data-stu-id="62ed7-117">Use the following options to configure the export.</span></span>

- <span data-ttu-id="62ed7-118">**导出名称**：导出作业的名称。</span><span class="sxs-lookup"><span data-stu-id="62ed7-118">**Export name**: Name of the export job.</span></span>

- <span data-ttu-id="62ed7-119">**说明**：要添加说明的自定义文本字段。</span><span class="sxs-lookup"><span data-stu-id="62ed7-119">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="62ed7-120">**导出这些文档**</span><span class="sxs-lookup"><span data-stu-id="62ed7-120">**Export these documents**</span></span>

  - <span data-ttu-id="62ed7-121">**仅选定文档**：此选项仅导出当前选定的文档。</span><span class="sxs-lookup"><span data-stu-id="62ed7-121">**Selected documents only**: This option exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="62ed7-122">**审阅集内的所有文档**：此选项导出审阅集内的所有文档。</span><span class="sxs-lookup"><span data-stu-id="62ed7-122">**All documents in the review set**: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="62ed7-123">**元数据**</span><span class="sxs-lookup"><span data-stu-id="62ed7-123">**Metadata**</span></span>
  
  - <span data-ttu-id="62ed7-124">**加载文件**：此文件包含每个文件的元数据。</span><span class="sxs-lookup"><span data-stu-id="62ed7-124">**Load file**: This file contains metadata for each file.</span></span> <span data-ttu-id="62ed7-125">此文件通常由第三方电子数据展示工具进行使用。</span><span class="sxs-lookup"><span data-stu-id="62ed7-125">This file can typically be ingested by third-party eDiscovery tools.</span></span> <span data-ttu-id="62ed7-126">有关包含哪些字段的信息，请参阅高级电子数据 [展示中的文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="62ed7-126">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>
  
  - <span data-ttu-id="62ed7-127">**标记**：选中后，标记信息将包含在加载文件中。</span><span class="sxs-lookup"><span data-stu-id="62ed7-127">**Tags**: When selected, tagging information is included in the load file.</span></span>

- <span data-ttu-id="62ed7-128">**内容**</span><span class="sxs-lookup"><span data-stu-id="62ed7-128">**Content**</span></span>
  
  - <span data-ttu-id="62ed7-129">**本机文件**：选中此复选框以在审阅集内包含文档的本机文件。</span><span class="sxs-lookup"><span data-stu-id="62ed7-129">**Native files**: Select this checkbox to include the native files of the documents in the review set.</span></span> <span data-ttu-id="62ed7-130">如果选择导出本机文件，可以选择以下选项来导出聊天对话。</span><span class="sxs-lookup"><span data-stu-id="62ed7-130">If you choose to export native files, you have the following options for how export chat conversations.</span></span>
  
  - <span data-ttu-id="62ed7-131">**对话选项**</span><span class="sxs-lookup"><span data-stu-id="62ed7-131">**Conversation options**</span></span>

    - <span data-ttu-id="62ed7-132">**对话文件**：此选项导出重新构造的聊天对话。</span><span class="sxs-lookup"><span data-stu-id="62ed7-132">**Conversation files**: This option exports reconstructed chat conversations.</span></span> <span data-ttu-id="62ed7-133">此格式以类似于用户在本机应用程序中看到的内容的形式呈现对话。</span><span class="sxs-lookup"><span data-stu-id="62ed7-133">This format presents conversations in a form that resembles what users see in the native application.</span></span>

    - <span data-ttu-id="62ed7-134">**单个聊天消息**：此选项导出原始对话文件，因为它们存储在 Microsoft 365 中。</span><span class="sxs-lookup"><span data-stu-id="62ed7-134">**Individual chat messages**: This option exports the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="62ed7-135">**选项**</span><span class="sxs-lookup"><span data-stu-id="62ed7-135">**Options**</span></span>

  - <span data-ttu-id="62ed7-136">**文本文件 ：**- 此选项包括导出中的本机文件的提取文本版本。</span><span class="sxs-lookup"><span data-stu-id="62ed7-136">**Text files**: - This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="62ed7-137">**将修订的本机替换为转换的 PDF：** 如果在审阅期间生成修订的 PDF 文件，则这些文件可供导出。</span><span class="sxs-lookup"><span data-stu-id="62ed7-137">**Replace redacted natives with converted PDFs**: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="62ed7-138">可以选择不选择此选项 (导出已修订的本机文件) 也可以选择此选项以导出包含实际修订的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="62ed7-138">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="62ed7-139">**输出选项**：导出的内容可以直接通过 Web 浏览器下载，也可以发送到 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="62ed7-139">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="62ed7-140">前两个选项支持直接下载。</span><span class="sxs-lookup"><span data-stu-id="62ed7-140">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="62ed7-141">**如果可能 (，** 将松散文件和 PTS 添加到 PST) ：文件以类似于用户本机应用程序中看到的原始目录结构的格式导出。</span><span class="sxs-lookup"><span data-stu-id="62ed7-141">**Loose files and PSTs (email is added to PSTs when possible)**: Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="62ed7-142">有关详细信息，请参阅 Loose [files and PST export structure部分](#loose-files-and-pst-export-structure) 。</span><span class="sxs-lookup"><span data-stu-id="62ed7-142">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="62ed7-143">**压缩目录结构**：导出文件并包含在下载中。</span><span class="sxs-lookup"><span data-stu-id="62ed7-143">**Condensed directory structure**: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="62ed7-144">**导出到 Azure 存储帐户的** 压缩目录结构：文件将导出到组织的 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="62ed7-144">**Condensed directory structure exported to your Azure Storage account**: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="62ed7-145">对于此选项，你必须提供 Azure 存储帐户中容器的 URL，以将文件导出到。</span><span class="sxs-lookup"><span data-stu-id="62ed7-145">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="62ed7-146">你还必须提供 Azure 存储帐户的共享访问签名 (SAS) 令牌。</span><span class="sxs-lookup"><span data-stu-id="62ed7-146">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="62ed7-147">有关详细信息，请参阅 [将审阅集内的文档导出到 Azure 存储帐户](download-export-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="62ed7-147">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

<span data-ttu-id="62ed7-148">以下各节介绍松散文件和压缩目录结构选项的文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="62ed7-148">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="62ed7-149">松散文件和 PST 导出结构</span><span class="sxs-lookup"><span data-stu-id="62ed7-149">Loose files and PST export structure</span></span>

<span data-ttu-id="62ed7-150">如果选择此导出选项，则导出的内容按以下结构进行组织：</span><span class="sxs-lookup"><span data-stu-id="62ed7-150">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="62ed7-151">根文件夹：名为 ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="62ed7-151">Root folder: This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="62ed7-152">Export_load_file.csv：元数据文件。</span><span class="sxs-lookup"><span data-stu-id="62ed7-152">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="62ed7-153">Summary.csv：还包含导出统计信息的摘要文件。</span><span class="sxs-lookup"><span data-stu-id="62ed7-153">Summary.csv: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="62ed7-154">Exchange：此文件夹包含来自 Exchange 的本机文件格式的所有内容。</span><span class="sxs-lookup"><span data-stu-id="62ed7-154">Exchange: This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="62ed7-155">如果选择了"将已修订的本机替换为转换后的 PDF"选项，本机文件将 **替换为修订的 PDF。**</span><span class="sxs-lookup"><span data-stu-id="62ed7-155">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="62ed7-156">SharePoint：此文件夹包含 SharePoint 中采用本机文件格式的所有本机内容。</span><span class="sxs-lookup"><span data-stu-id="62ed7-156">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="62ed7-157">如果选择了"将已修订的本机替换为转换后的 PDF"选项，本机文件将 **替换为修订的 PDF。**</span><span class="sxs-lookup"><span data-stu-id="62ed7-157">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="62ed7-158">压缩目录结构</span><span class="sxs-lookup"><span data-stu-id="62ed7-158">Condensed directory structure</span></span>

- <span data-ttu-id="62ed7-159">根文件夹：此文件夹名为 ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="62ed7-159">Root folder: This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="62ed7-160">Export_load_file.csv：元数据文件。</span><span class="sxs-lookup"><span data-stu-id="62ed7-160">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="62ed7-161">Summary.txt：还包含导出统计信息的摘要文件。</span><span class="sxs-lookup"><span data-stu-id="62ed7-161">Summary.txt: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="62ed7-162">NativeFiles：此文件夹包含已导出的所有本机文件。</span><span class="sxs-lookup"><span data-stu-id="62ed7-162">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="62ed7-163">如果导出修订的 PDF 文件，则它们不会放入 PST 文件中。</span><span class="sxs-lookup"><span data-stu-id="62ed7-163">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="62ed7-164">相反，它们被添加到一个分隔的文件夹。</span><span class="sxs-lookup"><span data-stu-id="62ed7-164">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="62ed7-165">Error_files：如果导出中包含此文件夹，则此文件夹包含以下错误文件：</span><span class="sxs-lookup"><span data-stu-id="62ed7-165">Error_files: This folder contains the following error files, if they are included in the export:</span></span>

    - <span data-ttu-id="62ed7-166">ExtractionError：包含未从父文件正确提取的任何可用文件的元数据的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="62ed7-166">ExtractionError: A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>

    - <span data-ttu-id="62ed7-167">ProcessingError：此文件包含包含处理错误的文档的列表。</span><span class="sxs-lookup"><span data-stu-id="62ed7-167">ProcessingError: This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="62ed7-168">此内容为项目级，这意味着如果附件导致处理错误，则包含附件的电子邮件将包含在此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="62ed7-168">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="62ed7-169">Extracted_text_files：此文件夹包含处理过程中生成的所有提取的文本文件。</span><span class="sxs-lookup"><span data-stu-id="62ed7-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>
