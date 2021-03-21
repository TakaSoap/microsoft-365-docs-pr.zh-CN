---
title: 下载高级电子数据展示案例的导出作业
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
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-mar2020
description: 安装并使用 Azure 存储资源管理器下载从高级电子数据展示审阅集导出的文档。
ms.openlocfilehash: 0a73d157b2661202507883dd6542cdf6c6b482f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926618"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a><span data-ttu-id="df047-103">在高级电子数据展示案例中下载导出作业</span><span class="sxs-lookup"><span data-stu-id="df047-103">Download export jobs in an Advanced eDiscovery case</span></span>

<span data-ttu-id="df047-104">当你从高级电子数据展示案例中的审阅集中导出文档时，这些文档将上载到 Microsoft 提供的 Azure 存储位置或由你的组织管理的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="df047-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="df047-105">使用的 Azure 存储位置的类型取决于导出文档时选择的选项。</span><span class="sxs-lookup"><span data-stu-id="df047-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span>

<span data-ttu-id="df047-106">本文提供如何使用 Microsoft Azure 存储资源管理器连接到 Azure 存储位置以浏览和下载导出的文档的说明。</span><span class="sxs-lookup"><span data-stu-id="df047-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="df047-107">有关 Azure 存储资源管理器详细信息，请参阅 [快速入门：使用 Azure 存储资源管理器](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。</span><span class="sxs-lookup"><span data-stu-id="df047-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="df047-108">步骤 1：安装 Azure 存储资源管理器</span><span class="sxs-lookup"><span data-stu-id="df047-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="df047-109">第一步是下载并安装 Azure 存储资源管理器。</span><span class="sxs-lookup"><span data-stu-id="df047-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="df047-110">有关说明，请参阅 [Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="df047-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="df047-111">使用此工具可连接并下载步骤 3 中导出的文档。</span><span class="sxs-lookup"><span data-stu-id="df047-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="df047-112">步骤 2：从导出作业获取 SAS URL</span><span class="sxs-lookup"><span data-stu-id="df047-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="df047-113">下一步是获取创建导出作业以从审阅集导出文档时 (SAS) URL 的共享访问 [签名](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="df047-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="df047-114">你可以复制上传到 Microsoft 提供的 Azure 存储位置或由组织管理的 Azure 存储位置的文档的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="df047-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="df047-115">在任一情况下，使用 SAS URL 连接到步骤 3 中的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="df047-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="df047-116">在" **高级电子数据展示"** 页上，转到案例，然后单击"导出 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="df047-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="df047-117">在" **导出** "选项卡上，单击要下载的导出作业。</span><span class="sxs-lookup"><span data-stu-id="df047-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="df047-118">在飞出页面上的"位置 **"下**，复制显示的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="df047-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="df047-119">如有必要，你可以将其保存到文件，以便可以在步骤 3 中访问它。</span><span class="sxs-lookup"><span data-stu-id="df047-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![复制"位置"下显示的 SAS URL](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="df047-121">步骤 3：连接到 Azure 存储位置</span><span class="sxs-lookup"><span data-stu-id="df047-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="df047-122">最后一步是使用 Azure 存储资源管理器和 SAS URL 连接到 Azure 存储位置，并下载导出到本地计算机的文档。</span><span class="sxs-lookup"><span data-stu-id="df047-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1. <span data-ttu-id="df047-123">打开在步骤 1 中安装的 Azure 存储资源管理器。</span><span class="sxs-lookup"><span data-stu-id="df047-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="df047-124">单击" **添加帐户"** 图标。</span><span class="sxs-lookup"><span data-stu-id="df047-124">Click the **Add account** icon.</span></span> <span data-ttu-id="df047-125">或者，也可以右键单击"存储 **帐户"。**</span><span class="sxs-lookup"><span data-stu-id="df047-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![单击"添加帐户"图标](../media/AzureStorageConnect.png)

3. <span data-ttu-id="df047-127">在"**连接到 Azure 存储**"页上，单击"使用 SAS (URI) 共享访问签名 **"，然后单击"下一\*\*\*\*步"。**</span><span class="sxs-lookup"><span data-stu-id="df047-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![单击"使用 SAS (共享) URI"，然后单击"下一步"](../media/AzureStorageConnect2.png)

4. <span data-ttu-id="df047-129">在" **使用 SAS URI 附加** "页上，单击"URI"框中，然后粘贴在步骤 2 中获得的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="df047-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![将 SAS URL 粘贴到 URI 框中](../media/AzureStorageConnect3.png)

    <span data-ttu-id="df047-131">请注意，SAS URL 的一部分显示在"显示名称 **"** 框中。</span><span class="sxs-lookup"><span data-stu-id="df047-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="df047-132">这将用作在显示名称存储帐户下创建的容器的组。 </span><span class="sxs-lookup"><span data-stu-id="df047-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="df047-133">此名称包含高级电子数据展示案例的 ID 来自 和唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="df047-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="df047-134">你可以保留默认显示名称更改它。</span><span class="sxs-lookup"><span data-stu-id="df047-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="df047-135">如果更改它，则显示名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="df047-135">If you change it, the display name must be unique.</span></span>

5. <span data-ttu-id="df047-136">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="df047-136">Click **Next**.</span></span>

    <span data-ttu-id="df047-137">将显示 **"连接摘要** "页。</span><span class="sxs-lookup"><span data-stu-id="df047-137">The **Connection summary** page is displayed.</span></span>

    ![单击"连接摘要"页上的"连接"以连接到 Azure 存储位置](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="df047-139">在"**连接摘要"** 页上，查看连接信息，然后单击"连接 **"。**</span><span class="sxs-lookup"><span data-stu-id="df047-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span>

    <span data-ttu-id="df047-140">"Blob **容器"** 节点 **(打开的** 附加 ( >  **下)** \> 存储帐户"下。</span><span class="sxs-lookup"><span data-stu-id="df047-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![导出 Blob 容器节点中的作业](../media/AzureStorageConnect5.png)

    <span data-ttu-id="df047-142">它包含一个名为 的容器，显示名称步骤 4 中的步骤。</span><span class="sxs-lookup"><span data-stu-id="df047-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="df047-143">此容器包含已创建的每个导出作业的文件夹。</span><span class="sxs-lookup"><span data-stu-id="df047-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="df047-144">这些文件夹的命名 ID 与导出作业的 ID 相对应。</span><span class="sxs-lookup"><span data-stu-id="df047-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="df047-145">您可以在"作业"选项卡上 ("准备导出作业的数据"的) "支持信息"下找到这些导出的 ID 和 **导出名称**。 </span><span class="sxs-lookup"><span data-stu-id="df047-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="df047-146">双击导出作业文件夹以打开它。</span><span class="sxs-lookup"><span data-stu-id="df047-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="df047-147">将显示文件夹和导出报告的列表。</span><span class="sxs-lookup"><span data-stu-id="df047-147">A list of folders and export reports is displayed.</span></span>
   
    ![导出文件夹包含导出的文件和导出报告](../media/AzureStorageConnect6.png)

   <span data-ttu-id="df047-149">导出作业文件夹包含以下项目。</span><span class="sxs-lookup"><span data-stu-id="df047-149">The export job folder contains the following items.</span></span> <span data-ttu-id="df047-150">导出文件夹中的实际项目由创建导出作业时配置的导出选项确定。</span><span class="sxs-lookup"><span data-stu-id="df047-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="df047-151">有关详细信息，请参阅从 [审阅集导出文档](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="df047-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="df047-152">Export_load_file.csv：此 CSV 文件是包含有关每个导出文档的信息的详细导出报告。</span><span class="sxs-lookup"><span data-stu-id="df047-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="df047-153">文件由文档的每个元数据属性的列组成。</span><span class="sxs-lookup"><span data-stu-id="df047-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="df047-154">有关此报告中包含的元数据的列表和说明，请参阅 高级电子数据展示 中的文档元数据字段的表中的导出字段[名称列](document-metadata-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="df047-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>
    
    - <span data-ttu-id="df047-155">Summary.txt：包含导出摘要（包括导出统计信息）的文本文件。</span><span class="sxs-lookup"><span data-stu-id="df047-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="df047-156">Extracted_text_files：此文件夹包含每个导出文档的文本文件版本。</span><span class="sxs-lookup"><span data-stu-id="df047-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="df047-157">NativeFiles：此文件夹包含每个导出文档的本机文件版本。</span><span class="sxs-lookup"><span data-stu-id="df047-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="df047-158">Error_files：导出作业包含任何错误文件时，此文件夹包含以下项目：</span><span class="sxs-lookup"><span data-stu-id="df047-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="df047-159">ExtractionError.csv：此 CSV 文件包含未从父项正确提取的文件的可用元数据。</span><span class="sxs-lookup"><span data-stu-id="df047-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="df047-160">ProcessingError：此文件夹包含包含处理错误的文档。</span><span class="sxs-lookup"><span data-stu-id="df047-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="df047-161">此内容位于项目级别，这意味着如果附件有处理错误，则包含附件的文档也将包含在此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="df047-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="df047-162">若要导出导出中的内容，请选择导出文件夹，然后单击 **下载。**</span><span class="sxs-lookup"><span data-stu-id="df047-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="df047-163">指定要下载导出文件的位置，然后单击"选择文件夹"。</span><span class="sxs-lookup"><span data-stu-id="df047-163">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="df047-164">Azure 存储资源管理器开始导出过程。</span><span class="sxs-lookup"><span data-stu-id="df047-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="df047-165">下载导出项目的状态显示在"活动 **"窗格中。**</span><span class="sxs-lookup"><span data-stu-id="df047-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="df047-166">下载完成后将显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="df047-166">A message is displayed when the download is finished.</span></span>

    ![下载完成后将显示一条消息](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="df047-168">可以选择要下载的特定项目，而不是下载整个导出作业。</span><span class="sxs-lookup"><span data-stu-id="df047-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="df047-169">你可以双击某个项目进行查看，而不是下载项目。</span><span class="sxs-lookup"><span data-stu-id="df047-169">And instead of downloading items, you can double-click an item to view it.</span></span>