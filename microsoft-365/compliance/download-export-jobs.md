---
title: 将文档导出到组织的 Azure 存储帐户
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
ms.custom: seo-marvel-mar2020
description: 将审阅集内的文档导出到 Azure 存储帐户，然后使用 Azure 存储资源管理器将其下载到本地计算机。
ms.openlocfilehash: dfb3892f31e857d4744f6da337c924efaa87ab11
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574702"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a><span data-ttu-id="4cd27-103">将审阅集内的文档导出到 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="4cd27-103">Export documents in a review set to an Azure Storage account</span></span>

<span data-ttu-id="4cd27-104">当你从高级电子数据展示案例中的审阅集中导出文档时，可以选择将它们导出到组织管理的 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="4cd27-104">When you export documents from a review set in an Advanced eDiscovery case, you have the option to export them to an Azure Storage account managed by your organization.</span></span> <span data-ttu-id="4cd27-105">如果使用此选项，文档将上载到 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="4cd27-105">If you used this option, the documents are uploaded to your Azure Storage location.</span></span> <span data-ttu-id="4cd27-106">导出文档后，可以访问文档 (，然后使用 Azure 存储资源管理器) 本地计算机或其他位置。</span><span class="sxs-lookup"><span data-stu-id="4cd27-106">After they are exported, you can access the documents (and download them to a local computer or other location) by using the Azure Storage Explorer.</span></span> <span data-ttu-id="4cd27-107">本文提供有关如何将文档导出到 Azure 存储帐户的说明，以及如何使用 Azure 存储资源管理器连接到 Azure 存储位置以下载导出的文档。</span><span class="sxs-lookup"><span data-stu-id="4cd27-107">This article provides instructions for how to export documents to your Azure Storage account and the use the Azure Storage Explorer to connect to an Azure Storage location to download the exported documents.</span></span> <span data-ttu-id="4cd27-108">有关 Azure 存储资源管理器详细信息，请参阅 [使用 Azure 存储资源管理器](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。</span><span class="sxs-lookup"><span data-stu-id="4cd27-108">For more information about Azure Storage Explorer, see [Use Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="before-you-export-documents-from-a-review-set"></a><span data-ttu-id="4cd27-109">从审阅集导出文档之前</span><span class="sxs-lookup"><span data-stu-id="4cd27-109">Before you export documents from a review set</span></span>

- <span data-ttu-id="4cd27-110">你需要为 Azure 存储帐户提供共享访问签名 (SAS) 令牌，并为存储帐户中的特定容器提供 URL，以便从审阅集导出文档。</span><span class="sxs-lookup"><span data-stu-id="4cd27-110">You need to provide a shared access signature (SAS) token for your Azure Storage account and the URL for a specific container in the storage account to export documents from a review set.</span></span> <span data-ttu-id="4cd27-111">例如，执行步骤 2 时 (，请务必将这些文件) 文本文件中</span><span class="sxs-lookup"><span data-stu-id="4cd27-111">Be sure to have these at hand (for example, copied to a text file) when you perform Step 2</span></span>

  - <span data-ttu-id="4cd27-112">**SAS 令牌**：请务必获取适用于 Azure 存储帐户的 SAS 令牌 (而不是用于容器) 。</span><span class="sxs-lookup"><span data-stu-id="4cd27-112">**SAS token**: Be sure to get the SAS token is for your Azure Storage account (and not for the container).</span></span> <span data-ttu-id="4cd27-113">可以在 Azure 存储中为帐户生成 SAS 令牌。</span><span class="sxs-lookup"><span data-stu-id="4cd27-113">You can generate an SAS token for your account in Azure Storage.</span></span> <span data-ttu-id="4cd27-114">为此，请转到 Azure 存储帐户，然后选择存储帐户边栏选项卡中的"设置 **"设置** 下的"共享访问签名"。</span><span class="sxs-lookup"><span data-stu-id="4cd27-114">To do this, go to the Azure Storage account, and select **Share access signature** under the **Settings** settings in the storage account blade.</span></span> <span data-ttu-id="4cd27-115">生成 SAS 令牌时，使用默认设置并允许所有资源类型。</span><span class="sxs-lookup"><span data-stu-id="4cd27-115">Use the default settings and allow all resource types when you generate the SAS token.</span></span>

  - <span data-ttu-id="4cd27-116">**容器 URL：** 需要创建一个容器以将审阅集文档上载到其中，然后获取容器 URL 的副本;例如， `https://ediscoverydata.blob.core.windows.net/exportdata` 。</span><span class="sxs-lookup"><span data-stu-id="4cd27-116">**Container URL**: You need to create a container to upload the review set documents to, and then get a copy of the URL for the container; for example, `https://ediscoverydata.blob.core.windows.net/exportdata`.</span></span> <span data-ttu-id="4cd27-117">若要获取 URL，请转到 Azure 存储中的容器，然后选择容器边栏选项卡中"设置 **"** 部分下的"属性"。</span><span class="sxs-lookup"><span data-stu-id="4cd27-117">To get the URL, go to the container in Azure Storage, and select **Properties** under the **Settings** section in the container blade.</span></span>

- <span data-ttu-id="4cd27-118">下载并安装 Azure 存储资源管理器。</span><span class="sxs-lookup"><span data-stu-id="4cd27-118">Download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="4cd27-119">有关说明，请参阅 [Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="4cd27-119">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="4cd27-120">使用此工具连接到 Azure 存储帐户中的容器，并下载在步骤 1 中导出的文档。</span><span class="sxs-lookup"><span data-stu-id="4cd27-120">You use this tool to connect to the container in your Azure Storage account and download the documents that you exported in Step 1.</span></span>

## <a name="step-1-export-the-documents-from-a-review-set"></a><span data-ttu-id="4cd27-121">步骤 1：从审阅集导出文档</span><span class="sxs-lookup"><span data-stu-id="4cd27-121">Step 1: Export the documents from a review set</span></span>

<span data-ttu-id="4cd27-122">第一步是创建导出作业以将文档从审阅集导出。</span><span class="sxs-lookup"><span data-stu-id="4cd27-122">The first step is to create an export job to export documents out of a review set.</span></span> <span data-ttu-id="4cd27-123">有关所有导出选项的详细说明，请参阅从 [审阅集导出文档](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd27-123">For more detailed instructions about all the export options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="4cd27-124">以下过程将突出显示用于将文档导出到组织的 Azure 存储帐户的设置。</span><span class="sxs-lookup"><span data-stu-id="4cd27-124">The following procedure highlights the settings to export documents to your organization's Azure Storage account.</span></span>

1. <span data-ttu-id="4cd27-125">在 Microsoft 365 合规中心，打开"高级电子数据展示"案例，选择"审阅集"选项卡，然后选择要导出的审阅集。</span><span class="sxs-lookup"><span data-stu-id="4cd27-125">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="4cd27-126">在审阅集内，单击"操作 **导出**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="4cd27-126">In the review set, click **Action** > **Export**.</span></span>

3. <span data-ttu-id="4cd27-127">在" **导出选项** "飞出页上，键入导出 (必需的) 和 () 选项的名称。</span><span class="sxs-lookup"><span data-stu-id="4cd27-127">On the **Export options** flyout page, type a name (required) and description (optional) for the export.</span></span>

4. <span data-ttu-id="4cd27-128">配置文档、元数据、内容和选项部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="4cd27-128">Configure the settings in the documents, metadata, content, and options sections.</span></span> <span data-ttu-id="4cd27-129">有关这些设置详细信息，请参阅从审阅 [集导出文档](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd27-129">For more information about these settings, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

5. <span data-ttu-id="4cd27-130">在" **输出选项** "部分，选择导出到 Azure 存储帐户的"压缩 **目录结构"** 选项。</span><span class="sxs-lookup"><span data-stu-id="4cd27-130">In the **Output options** section, select the **Condensed directory structure exported to your Azure Storage account** option.</span></span>

6. <span data-ttu-id="4cd27-131">将存储帐户的容器 URL 和 SAS 令牌粘贴到相应的字段中。</span><span class="sxs-lookup"><span data-stu-id="4cd27-131">Paste the container URL and the SAS token for your storage account in the corresponding fields.</span></span>

   ![将连接 URL 和 SAS 令牌粘贴到相应的字段中](../media/AzureStorageOutputOptions.png)

7. <span data-ttu-id="4cd27-133">单击 **"** 导出"创建导出作业。</span><span class="sxs-lookup"><span data-stu-id="4cd27-133">Click **Export** to create the export job.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="4cd27-134">步骤 2：从导出作业获取 SAS URL</span><span class="sxs-lookup"><span data-stu-id="4cd27-134">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="4cd27-135">下一步是获取在步骤 1 中创建导出作业后生成的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="4cd27-135">The next step is to obtain the SAS URL that's generated after you create the export job in Step 1.</span></span> <span data-ttu-id="4cd27-136">使用 SAS URL 连接到将审阅集文档导出到的 Azure 存储帐户中的容器。</span><span class="sxs-lookup"><span data-stu-id="4cd27-136">You use the SAS URL to connect to the container in your Azure Storage account that you exported the review set documents to.</span></span>

1. <span data-ttu-id="4cd27-137">在" **高级电子数据展示"** 页上，转到案例，然后单击"导出 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4cd27-137">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="4cd27-138">在" **导出** "选项卡上，单击要下载的导出作业。</span><span class="sxs-lookup"><span data-stu-id="4cd27-138">On the **Exports** tab, click the export job that you want to download.</span></span> <span data-ttu-id="4cd27-139">这是在步骤 1 中创建的导出作业。</span><span class="sxs-lookup"><span data-stu-id="4cd27-139">This is the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="4cd27-140">在飞出页面上的"位置 **"下**，复制显示的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="4cd27-140">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="4cd27-141">如有必要，你可以将其保存到文本文件，以便可以在步骤 3 中访问它。</span><span class="sxs-lookup"><span data-stu-id="4cd27-141">If necessary, you can save it to a text file so you can access it in Step 3.</span></span>

   ![复制"位置"下显示的 SAS URL](../media/eDiscoExportJob.png)

   > [!TIP]
   > <span data-ttu-id="4cd27-143">导出作业中显示的 SAS URL 是容器 URL 和 Azure 存储帐户的 SAS 令牌的串联。</span><span class="sxs-lookup"><span data-stu-id="4cd27-143">The SAS URL that's displayed in the export job is a concatenation of the container URL and the SAS token for your Azure Storage account.</span></span> <span data-ttu-id="4cd27-144">你可以从导出作业复制它，或者通过组合 URL 和 SAS 令牌自己创建它。</span><span class="sxs-lookup"><span data-stu-id="4cd27-144">You can copy it from the export job or create it yourself by combining the URL and the SAS token.</span></span>

## <a name="step-3-connect-to-the-azure-storage-container"></a><span data-ttu-id="4cd27-145">步骤 3：连接到 Azure 存储容器</span><span class="sxs-lookup"><span data-stu-id="4cd27-145">Step 3: Connect to the Azure Storage container</span></span>

<span data-ttu-id="4cd27-146">最后一步是使用 Azure 存储资源管理器和 SAS URL 连接到 Azure 存储帐户中的容器，将导出的文档下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="4cd27-146">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the container in your Azure Storage account and download the exported documents to a local computer.</span></span>

1. <span data-ttu-id="4cd27-147">启动你下载并安装的 Azure 存储资源管理器。</span><span class="sxs-lookup"><span data-stu-id="4cd27-147">Start the Azure Storage Explorer that you downloaded and installed.</span></span>

2. <span data-ttu-id="4cd27-148">单击" **打开连接对话框"** 图标。</span><span class="sxs-lookup"><span data-stu-id="4cd27-148">Click the **Open Connect Dialog** icon.</span></span>

   ![单击"添加帐户"图标](../media/AzureStorageConnect.png)

3. <span data-ttu-id="4cd27-150">在"**连接到 Azure 存储"页上**，单击 **"Blob 容器"。**</span><span class="sxs-lookup"><span data-stu-id="4cd27-150">On the **Connect to Azure Storage** page, click **Blob container**.</span></span>

4. <span data-ttu-id="4cd27-151">在"**选择身份验证方法**"页上，选择"SAS (**共享) "** 选项，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="4cd27-151">On the **Select Authentication Method** page, select the **Shared access signature (SAS)** option and then click **Next**.</span></span>

5. <span data-ttu-id="4cd27-152">在"**输入连接信息**"页上， (在"Blob 容器 SAS URL"框中的步骤 2) 导出作业获取的 **SAS URL。**</span><span class="sxs-lookup"><span data-stu-id="4cd27-152">On the **Enter Connection Info** page, paste the SAS URL (that you obtained in the export job in Step 2) in the **Blob Container SAS URL** box.</span></span>

    ![将 SAS URL 粘贴到 URI 框中](../media/AzureStorageConnect3.png)

    <span data-ttu-id="4cd27-154">请注意，容器名称显示在"显示名称 **"** 框中。</span><span class="sxs-lookup"><span data-stu-id="4cd27-154">Notice that the container name is displayed in the **Display name** box.</span></span> <span data-ttu-id="4cd27-155">可以编辑此名称。</span><span class="sxs-lookup"><span data-stu-id="4cd27-155">You can edit this name.</span></span>

6. <span data-ttu-id="4cd27-156">单击 **"下** 一步"**以显示摘要** 页，然后单击"连接 **"。**</span><span class="sxs-lookup"><span data-stu-id="4cd27-156">Click **Next** to display the **summary** page and then click **Connect**.</span></span>

    <span data-ttu-id="4cd27-157">"Blob **容器"** 节点 **(打开的** 附加 ( >  **下)** \> 存储帐户"下。</span><span class="sxs-lookup"><span data-stu-id="4cd27-157">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![导出 Blob 容器节点中的作业](../media/AzureStorageConnect5.png)

    <span data-ttu-id="4cd27-159">它包含一个名为 的容器，显示名称步骤 5 中的步骤。</span><span class="sxs-lookup"><span data-stu-id="4cd27-159">It contains a container named with the display name from step 5.</span></span> <span data-ttu-id="4cd27-160">此容器包含已下载到 Azure 存储帐户中的容器的每个导出作业的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4cd27-160">This container contains a folder for each export job that you've downloaded to the container in your Azure Storage account.</span></span> <span data-ttu-id="4cd27-161">这些文件夹的命名 ID 与导出作业的 ID 相对应。</span><span class="sxs-lookup"><span data-stu-id="4cd27-161">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="4cd27-162">您可以在"高级电子数据展示"案例的"作业"选项卡上列出的每个"准备导出数据"作业的 ("支持信息"下的"支持信息"下找到这些导出的) 和导出 ID 的名称。 </span><span class="sxs-lookup"><span data-stu-id="4cd27-162">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab in the Advanced eDiscovery case.</span></span>

7. <span data-ttu-id="4cd27-163">双击导出作业文件夹以打开它。</span><span class="sxs-lookup"><span data-stu-id="4cd27-163">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="4cd27-164">将显示文件夹和导出报告的列表。</span><span class="sxs-lookup"><span data-stu-id="4cd27-164">A list of folders and export reports is displayed.</span></span>

    ![导出文件夹包含导出的文件和导出报告](../media/AzureStorageConnect6.png)

8. <span data-ttu-id="4cd27-166">若要从导出作业导出所有内容，请单击向上箭头返回到导出作业文件夹，然后单击 **下载。**</span><span class="sxs-lookup"><span data-stu-id="4cd27-166">To export all contents from the export job, click the **Up** arrow to go back to the export job folder, and then click **Download**.</span></span>

9. <span data-ttu-id="4cd27-167">指定要下载导出文件的位置，然后单击"选择文件夹"。</span><span class="sxs-lookup"><span data-stu-id="4cd27-167">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="4cd27-168">Azure 存储资源管理器启动下载过程。</span><span class="sxs-lookup"><span data-stu-id="4cd27-168">The Azure Storage Explorer starts the download process.</span></span> <span data-ttu-id="4cd27-169">下载导出项目的状态显示在"活动 **"窗格中。**</span><span class="sxs-lookup"><span data-stu-id="4cd27-169">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="4cd27-170">下载完成后将显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="4cd27-170">A message is displayed when the download is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="4cd27-171">可以选择要下载和查看的特定项目，而不是在 Azure 存储资源管理器中下载整个导出作业。</span><span class="sxs-lookup"><span data-stu-id="4cd27-171">Instead of downloading the entire export job in Azure Storage Explorer, you can select specific items to download and view.</span></span>

## <a name="more-information"></a><span data-ttu-id="4cd27-172">更多信息</span><span class="sxs-lookup"><span data-stu-id="4cd27-172">More information</span></span>

- <span data-ttu-id="4cd27-173">导出作业文件夹包含以下项目。</span><span class="sxs-lookup"><span data-stu-id="4cd27-173">The export job folder contains the following items.</span></span> <span data-ttu-id="4cd27-174">导出文件夹中的实际项目由创建导出作业时配置的导出选项确定。</span><span class="sxs-lookup"><span data-stu-id="4cd27-174">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="4cd27-175">有关这些选项的详细信息，请参阅从审阅 [集导出文档](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd27-175">For more information about these options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

  - <span data-ttu-id="4cd27-176">Export_load_file.csv：此 CSV 文件是包含有关每个导出文档的信息的详细导出报告。</span><span class="sxs-lookup"><span data-stu-id="4cd27-176">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="4cd27-177">文件由文档的每个元数据属性的列组成。</span><span class="sxs-lookup"><span data-stu-id="4cd27-177">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="4cd27-178">有关此报告中包含的元数据的列表和说明，请参阅 高级电子数据展示 中的文档元数据字段的表中的导出字段[名称列](document-metadata-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd27-178">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>

  - <span data-ttu-id="4cd27-179">Summary.txt：包含导出摘要（包括导出统计信息）的文本文件。</span><span class="sxs-lookup"><span data-stu-id="4cd27-179">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>

  - <span data-ttu-id="4cd27-180">Extracted_text_files：此文件夹包含每个导出文档的文本文件版本。</span><span class="sxs-lookup"><span data-stu-id="4cd27-180">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>

  - <span data-ttu-id="4cd27-181">NativeFiles：此文件夹包含每个导出文档的本机文件版本。</span><span class="sxs-lookup"><span data-stu-id="4cd27-181">NativeFiles: This folder contains a native file version of each exported document.</span></span>

  - <span data-ttu-id="4cd27-182">Error_files：导出作业包含任何错误文件时，此文件夹包含以下项目：</span><span class="sxs-lookup"><span data-stu-id="4cd27-182">Error_files: This folder includes the following items when the export job contains any error files:</span></span>

    - <span data-ttu-id="4cd27-183">ExtractionError.csv：此 CSV 文件包含未从父项正确提取的文件的可用元数据。</span><span class="sxs-lookup"><span data-stu-id="4cd27-183">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>

    - <span data-ttu-id="4cd27-184">ProcessingError：此文件夹包含包含处理错误的文档。</span><span class="sxs-lookup"><span data-stu-id="4cd27-184">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="4cd27-185">此内容位于项目级别，这意味着如果附件有处理错误，则包含附件的文档也将包含在此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4cd27-185">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
