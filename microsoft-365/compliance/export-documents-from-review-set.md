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
description: 了解如何选择和导出演示文稿或外部Advanced eDiscovery审阅集的内容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a174c147da6e424891508bad484f45f4a5d308b6
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461395"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="f4e99-103">从审阅集导出文档Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f4e99-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="f4e99-104">导出允许用户在从 Advanced eDiscovery 审阅集导出文档时自定义下载包中包含的Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="f4e99-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="f4e99-105">从审阅集导出文档：</span><span class="sxs-lookup"><span data-stu-id="f4e99-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="f4e99-106">在Microsoft 365 合规中心中，打开Advanced eDiscovery"案例，选择"审阅集"选项卡，然后选择要导出的审阅集。</span><span class="sxs-lookup"><span data-stu-id="f4e99-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="f4e99-107">在审阅集内，单击"操作 **导出**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="f4e99-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="f4e99-108">"导出"工具显示包含用于配置导出的设置的飞出页。</span><span class="sxs-lookup"><span data-stu-id="f4e99-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="f4e99-109">默认情况下会选择某些选项，但可以更改这些选项。</span><span class="sxs-lookup"><span data-stu-id="f4e99-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="f4e99-110">有关可以配置的导出选项的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="f4e99-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![用于从审阅集导出项目的配置选项](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="f4e99-112">配置导出后，单击" **导出** "开始导出过程。</span><span class="sxs-lookup"><span data-stu-id="f4e99-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="f4e99-113">根据在"输出选项"部分选择的选项，可以通过直接下载或组织的"导出Azure 存储文件。</span><span class="sxs-lookup"><span data-stu-id="f4e99-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="f4e99-114">导出作业在案例的生命周期内保留。</span><span class="sxs-lookup"><span data-stu-id="f4e99-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="f4e99-115">但是，您必须在导出作业完成后的 30 天内从导出作业下载内容。</span><span class="sxs-lookup"><span data-stu-id="f4e99-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="f4e99-116">导出选项</span><span class="sxs-lookup"><span data-stu-id="f4e99-116">Export options</span></span>

<span data-ttu-id="f4e99-117">使用以下选项配置导出。</span><span class="sxs-lookup"><span data-stu-id="f4e99-117">Use the following options to configure the export.</span></span> <span data-ttu-id="f4e99-118">并非所有选项都允许用于某些输出选项，最重要的是，导出到 PST 格式时不允许导出文本文件和修订的 PDF。</span><span class="sxs-lookup"><span data-stu-id="f4e99-118">Not all options are allowed for some output options, most notably, export of text files and redacted PDFs are not allowed when exporting to the PST format.</span></span>

- <span data-ttu-id="f4e99-119">**导出名称**：导出作业的名称。</span><span class="sxs-lookup"><span data-stu-id="f4e99-119">**Export name**: Name of the export job.</span></span> <span data-ttu-id="f4e99-120">这将用于命名将下载的 ZIP 文件。</span><span class="sxs-lookup"><span data-stu-id="f4e99-120">This will be used to name the ZIP files that will be downloaded.</span></span>

- <span data-ttu-id="f4e99-121">**说明**：要添加说明的自定义文本字段。</span><span class="sxs-lookup"><span data-stu-id="f4e99-121">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="f4e99-122">**导出这些文档**</span><span class="sxs-lookup"><span data-stu-id="f4e99-122">**Export these documents**</span></span>

  - <span data-ttu-id="f4e99-123">仅选定文档：此选项仅导出当前选定的文档。</span><span class="sxs-lookup"><span data-stu-id="f4e99-123">Selected documents only: This option exports only the documents that are currently selected.</span></span> <span data-ttu-id="f4e99-124">此选项仅在审阅集内选择项目时可用。</span><span class="sxs-lookup"><span data-stu-id="f4e99-124">This option is only available when items are selected in a review set.</span></span>
  
  - <span data-ttu-id="f4e99-125">所有已筛选文档：此选项导出活动筛选器中的文档。</span><span class="sxs-lookup"><span data-stu-id="f4e99-125">All filtered documents: This option exports the documents in an active filter.</span></span> <span data-ttu-id="f4e99-126">此选项仅在筛选器应用于审阅集时可用。</span><span class="sxs-lookup"><span data-stu-id="f4e99-126">This option is only available when a filter is applied to the review set.</span></span>
  
  - <span data-ttu-id="f4e99-127">审阅集内的所有文档：此选项导出审阅集内的所有文档。</span><span class="sxs-lookup"><span data-stu-id="f4e99-127">All documents in the review set: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="f4e99-128">**输出选项**：导出的内容可以直接通过 Web 浏览器下载，也可以发送到 Azure 存储 帐户。</span><span class="sxs-lookup"><span data-stu-id="f4e99-128">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="f4e99-129">前两个选项支持直接下载。</span><span class="sxs-lookup"><span data-stu-id="f4e99-129">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="f4e99-130">仅报告：仅创建摘要和加载文件。</span><span class="sxs-lookup"><span data-stu-id="f4e99-130">Reports only: Only the summary and load file are created.</span></span>
  
  - <span data-ttu-id="f4e99-131">如果可能 (，将松散文件和 PTS 添加到 PST) ：文件以类似于用户本机应用程序中看到的原始目录结构的格式导出。</span><span class="sxs-lookup"><span data-stu-id="f4e99-131">Loose files and PSTs (email is added to PSTs when possible): Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="f4e99-132">有关详细信息，请参阅 Loose [files and PST export structure部分](#loose-files-and-pst-export-structure) 。</span><span class="sxs-lookup"><span data-stu-id="f4e99-132">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="f4e99-133">压缩目录结构：导出文件并包含在下载中。</span><span class="sxs-lookup"><span data-stu-id="f4e99-133">Condensed directory structure: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="f4e99-134">导出到您的 Azure 存储 帐户的压缩目录结构：文件将导出到您组织的 Azure 存储 帐户。</span><span class="sxs-lookup"><span data-stu-id="f4e99-134">Condensed directory structure exported to your Azure Storage account: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="f4e99-135">对于此选项，你必须为要导出文件的 Azure 存储 帐户中的容器提供 URL。</span><span class="sxs-lookup"><span data-stu-id="f4e99-135">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="f4e99-136">还必须为帐户的 SAS (提供共享) 签名Azure 存储令牌。</span><span class="sxs-lookup"><span data-stu-id="f4e99-136">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="f4e99-137">有关详细信息，请参阅将审阅集[内的文档导出到Azure 存储帐户。](download-export-jobs.md)</span><span class="sxs-lookup"><span data-stu-id="f4e99-137">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

- <span data-ttu-id="f4e99-138">**Include**</span><span class="sxs-lookup"><span data-stu-id="f4e99-138">**Include**</span></span>
  
  - <span data-ttu-id="f4e99-139">标记：选中后，标记信息将包含在加载文件中。</span><span class="sxs-lookup"><span data-stu-id="f4e99-139">Tags: When selected, tagging information is included in the load file.</span></span>
  
  - <span data-ttu-id="f4e99-140">文本文件：此选项包括导出中的本机文件的提取文本版本。</span><span class="sxs-lookup"><span data-stu-id="f4e99-140">Text files: This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="f4e99-141">将修订的本机替换为转换后的 PDF：如果在审阅过程中生成了修订的 PDF 文件，则这些文件可供导出。</span><span class="sxs-lookup"><span data-stu-id="f4e99-141">Replace redacted natives with converted PDFs: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="f4e99-142">可以选择不选择此选项 (导出已修订的本机文件) 也可以选择此选项以导出包含实际修订的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="f4e99-142">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

<span data-ttu-id="f4e99-143">以下各节介绍松散文件和压缩目录结构选项的文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="f4e99-143">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span> <span data-ttu-id="f4e99-144">导出将分区到 ZIP 文件中，未压缩内容的最大大小为 75 GB。</span><span class="sxs-lookup"><span data-stu-id="f4e99-144">Exports are partitioned into ZIP files with a maximum size of uncompressed content of 75 GB.</span></span> <span data-ttu-id="f4e99-145">如果导出大小小于 75 GB，则导出将包含摘要文件和单个 ZIP 文件。</span><span class="sxs-lookup"><span data-stu-id="f4e99-145">If the export size is less than 75 GB, the export will consist of a summary file and a single ZIP file.</span></span> <span data-ttu-id="f4e99-146">对于超过 75 GB 的未压缩数据的导出，将创建多个 ZIP 文件。</span><span class="sxs-lookup"><span data-stu-id="f4e99-146">For exports larger than 75 GB of uncompressed data, multiple ZIP files will be created.</span></span> <span data-ttu-id="f4e99-147">下载后，可以将 ZIP 文件解压缩到单个位置以重新创建完整导出。</span><span class="sxs-lookup"><span data-stu-id="f4e99-147">Once downloaded, the ZIP files can be uncompressed into a single location to recreate the full export.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="f4e99-148">松散文件和 PST 导出结构</span><span class="sxs-lookup"><span data-stu-id="f4e99-148">Loose files and PST export structure</span></span>

<span data-ttu-id="f4e99-149">如果选择此导出选项，则导出的内容按以下结构进行组织：</span><span class="sxs-lookup"><span data-stu-id="f4e99-149">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="f4e99-150">Summary.csv：包括从审阅集导出的内容摘要</span><span class="sxs-lookup"><span data-stu-id="f4e99-150">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="f4e99-151">根文件夹：此文件夹的名称为 [Export Name] x z.zip，并且将针对每个 ZIP 文件分区重复此文件夹。</span><span class="sxs-lookup"><span data-stu-id="f4e99-151">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="f4e99-152">Export_load_file_xz.csv元数据文件。</span><span class="sxs-lookup"><span data-stu-id="f4e99-152">Export_load_file_x of z.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="f4e99-153">警告和错误 x z.csv：此文件包含有关尝试从审阅集导出时遇到的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="f4e99-153">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>
  
  - <span data-ttu-id="f4e99-154">Exchange：此文件夹包含 PST Exchange中存储的所有内容。</span><span class="sxs-lookup"><span data-stu-id="f4e99-154">Exchange: This folder contains all content from Exchange stored in PST files.</span></span> <span data-ttu-id="f4e99-155">此选项不能包含修订的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="f4e99-155">Redacted PDF files cannot be included with this option.</span></span> <span data-ttu-id="f4e99-156">如果在审阅集内选择了附件，将导出附加附件的父电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f4e99-156">If an attachment is selected in the review set, the parent email will be exported with the attachment attached.</span></span>
  
  - <span data-ttu-id="f4e99-157">SharePoint：此文件夹包含本地SharePoint的所有本机内容。</span><span class="sxs-lookup"><span data-stu-id="f4e99-157">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="f4e99-158">此选项不能包含修订的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="f4e99-158">Redacted PDF files cannot be included with this option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="f4e99-159">压缩目录结构</span><span class="sxs-lookup"><span data-stu-id="f4e99-159">Condensed directory structure</span></span>

- <span data-ttu-id="f4e99-160">Summary.csv：包括从审阅集导出的内容摘要</span><span class="sxs-lookup"><span data-stu-id="f4e99-160">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="f4e99-161">根文件夹：此文件夹的名称为 [Export Name] x z.zip，并且将针对每个 ZIP 文件分区重复此文件夹。</span><span class="sxs-lookup"><span data-stu-id="f4e99-161">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="f4e99-162">Export_load_file_xz.csv：元数据文件，还包括 ZIP 文件中存储的每个文件的位置。</span><span class="sxs-lookup"><span data-stu-id="f4e99-162">Export_load_file_x of z.csv: The metadata file and also includes the location of each file that is stored in the ZIP file.</span></span>
  
  - <span data-ttu-id="f4e99-163">警告和错误 x z.csv：此文件包含有关尝试从审阅集导出时遇到的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="f4e99-163">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>

  - <span data-ttu-id="f4e99-164">NativeFiles：此文件夹包含已导出的所有本机文件。</span><span class="sxs-lookup"><span data-stu-id="f4e99-164">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="f4e99-165">如果选择了"将已修订的本机替换为转换后的 PDF"选项，本机文件将 *替换为修订的 PDF。*</span><span class="sxs-lookup"><span data-stu-id="f4e99-165">Natives files are replaced with redacted PDFs if you selected the *Replace redacted natives with converted PDFs* option.</span></span>
  
  - <span data-ttu-id="f4e99-166">Error_files：此文件夹包含具有提取错误或其他处理错误的文件。</span><span class="sxs-lookup"><span data-stu-id="f4e99-166">Error_files: This folder contains files that had either extraction or other processing error.</span></span> <span data-ttu-id="f4e99-167">这些文件将放置在单独的文件夹中，包括 ExtractionError 或 ProcessingError。</span><span class="sxs-lookup"><span data-stu-id="f4e99-167">The files will be placed into separate folders, either ExtractionError or ProcessingError.</span></span> <span data-ttu-id="f4e99-168">这些文件在加载文件中列出。</span><span class="sxs-lookup"><span data-stu-id="f4e99-168">These files are listed in the load file.</span></span>

  - <span data-ttu-id="f4e99-169">Extracted_text_files：此文件夹包含处理过程中生成的所有提取的文本文件。</span><span class="sxs-lookup"><span data-stu-id="f4e99-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a><span data-ttu-id="f4e99-170">导出到您的帐户的压缩Azure 存储结构</span><span class="sxs-lookup"><span data-stu-id="f4e99-170">Condensed directory structure exported to your Azure Storage Account</span></span>

<span data-ttu-id="f4e99-171">此选项使用与 *压缩* 目录结构相同的常规结构，但是不会压缩内容，并且数据将保存到Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="f4e99-171">This option uses the same general structure as the *Condensed directory structure*, however the contents is not zipped and the data is saved to your Azure Storage account.</span></span> <span data-ttu-id="f4e99-172">此选项通常在使用第三方电子数据展示提供程序时使用。</span><span class="sxs-lookup"><span data-stu-id="f4e99-172">This option is generally used when working with a third-party eDiscovery provider.</span></span> <span data-ttu-id="f4e99-173">有关如何使用此选项的详细信息，请参阅将审阅集内的文档[导出到Azure 存储帐户。](download-export-jobs.md)</span><span class="sxs-lookup"><span data-stu-id="f4e99-173">For details about how to use this option, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>
