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
description: 安装并使用 Azure 存储资源管理器下载从高级电子数据展示中的审阅集导出的文档。
ms.openlocfilehash: 094dcb4ecc8b1ca73a7ec0238ed20b27d4c16e72
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751289"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a>在高级电子数据展示案例中下载导出作业

当您从高级电子数据展示案例中的审阅集中导出文档时，这些文档将上载到 Microsoft 提供的 Azure 存储位置或由组织管理的 Azure 存储位置。 所使用的 Azure 存储位置的类型取决于导出文档时选择的选项。

本文提供如何使用 Microsoft Azure 存储资源管理器连接到 Azure 存储位置以浏览和下载导出的文档的说明。 有关 Azure 存储资源管理器详细信息，请参阅 [快速入门：使用 Azure 存储资源管理器](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。

## <a name="step-1-install-the-azure-storage-explorer"></a>步骤 1：安装 Azure 存储资源管理器

第一步是下载并安装 Azure 存储资源管理器。 有关说明，请参阅 [Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。 使用此工具可连接并下载步骤 3 中导出的文档。

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>步骤 2：从导出作业获取 SAS URL

下一步是获取创建导出作业以从审阅集导出文档时 (SAS) URL 的共享访问 [签名](export-documents-from-review-set.md)。 你可以复制上载到 Microsoft 提供的 Azure 存储位置或由组织管理的 Azure 存储位置的文档的 SAS URL。 在任一情况下，都使用 SAS URL 连接到步骤 3 中的 Azure 存储位置。

1. 在 **"高级电子数据展示"** 页上，转到该案例，然后单击"导出 **"** 选项卡。

2. 在 **"导出** "选项卡上，单击要下载的导出作业。

3. 在飞出页面上的"位置 **"** 下，复制显示的 SAS URL。 如有必要，可以将其保存到文件，以便可以在步骤 3 中访问该文件。
 
   ![复制位置下显示的 SAS URL](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a>步骤 3：连接到 Azure 存储位置

最后一步是使用 Azure 存储资源管理器和 SAS URL 连接到 Azure 存储位置，并下载导出到本地计算机的文档。

1. 打开在步骤 1 中安装的 Azure 存储资源管理器。

2. 单击 **"添加帐户"** 图标。 或者，你可以右键单击 **"存储帐户"。**

   ![单击"添加帐户"图标](../media/AzureStorageConnect.png)

3. 在"**连接到 Azure** 存储"页上，单击"使用 SAS (**URI**) 共享访问签名，然后单击"下一 **步"。**

    ![单击"使用 SAS (URI) 共享访问签名，然后单击"下一步"](../media/AzureStorageConnect2.png)

4. 在" **使用 SAS URI** 附加"页上，单击 URI 框，然后粘贴在步骤 2 中获得的 SAS URL。 

    ![将 SAS URL 粘贴到 URI 框中](../media/AzureStorageConnect3.png)

    请注意，SAS URL 的一部分显示在"显示名称 **"** 框中。 这将用作在显示名称位置后在存储帐户下创建的容器的备份。  此名称由高级电子数据展示案例的 ID 和唯一标识符组成。 你可以保留默认显示名称更改它。 如果更改它，则显示名称必须是唯一的。

5. 单击“下一步”。

    将显示 **"连接摘要** "页。

    ![单击"连接摘要"页上的"连接"以连接到 Azure 存储位置](../media/AzureStorageConnect4.png)

6. 在"**连接摘要"** 页上，查看连接信息，然后单击"**连接"。**

    Blob **容器节点** (**打开** 的附加容器 ( >  **下)** \> Blob 容器节点。

    ![导出 Blob 容器节点中的作业](../media/AzureStorageConnect5.png)

    它包含使用步骤 4 显示名称命名的容器。 此容器包含已创建的每个导出作业的文件夹。 这些文件夹使用与导出作业的 ID 对应的 ID 命名。 您可以在"作业") 选项卡 (导出作业的每个准备数据在"支持信息"页上的"支持信息"下找到这些导出 (和导出名称。 

7. 双击导出作业文件夹以打开它。

   将显示文件夹和导出报告的列表。
   
    ![导出文件夹包含导出的文件和导出报告](../media/AzureStorageConnect6.png)

   导出作业文件夹包含以下项目。 导出文件夹中的实际项目由创建导出作业时配置的导出选项决定。 有关详细信息，请参阅从 [审阅集导出文档](export-documents-from-review-set.md)。

    - Export_load_file.csv：此 CSV 文件是包含有关每个导出文档的信息的详细导出报告。 文件由文档的每个元数据属性的列组成。 有关此报告中包含的元数据的列表和说明，请参阅高级电子数据展示中的"文档元数据"字段中表中"导出的字段名称["列](document-metadata-fields-in-advanced-ediscovery.md)。
    
    - Summary.txt：包含导出摘要（包括导出统计信息）的文本文件。
    
    - Extracted_text_files：此文件夹包含每个导出文档的文本文件版本。
     
    - NativeFiles：此文件夹包含每个导出文档的本机文件版本。
    
    - Error_files：当导出作业包含任何错误文件时，此文件夹包括以下项目： 
        
      - ExtractionError.csv：此 CSV 文件包含未正确从父项中提取的文件的可用元数据。
        
      - ProcessingError：此文件夹包含包含处理错误的文档。 此内容位于项目级别，这意味着如果附件有处理错误，则包含附件的文档也将包含在此文件夹中。
 
8. 若要导出导出中的内容，请选择导出文件夹，然后单击"下载 **"。**

9. 指定要下载导出文件的位置，然后单击"选择文件夹"。

    Azure 存储资源管理器开始导出过程。 下载导出的项目的状态显示在"活动" **窗格中** 。 下载完成后将显示一条消息。

    ![下载完成后将显示一条消息](../media/AzureStorageConnect8.png)

> [!NOTE]
> 可以选择要下载的特定项目，而不是下载整个导出作业。 你可以双击项目以查看项目，而不是下载项目。
