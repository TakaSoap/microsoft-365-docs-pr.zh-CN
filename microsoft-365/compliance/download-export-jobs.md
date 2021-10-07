---
title: 将文档导出到组织的 Azure 存储 帐户
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: 将审阅集内的文档导出到Azure 存储帐户，然后使用Azure 存储资源管理器将文档下载到本地计算机。
ms.openlocfilehash: 8f3110ef386fd5c5d8adc641aa223435caf0da67
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203119"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a>将审阅集内的文档导出到Azure 存储帐户

当您从文档集中的审阅集中导出文档Advanced eDiscovery，您可以选择将其导出到组织Azure 存储管理的帐户。 如果使用此选项，文档将上载到Azure 存储位置。 导出文档后，可以访问文档 (，然后通过使用 Azure 存储资源管理器 将其下载到本地计算机或其他) 。 本文提供有关如何将文档导出到 Azure 存储 帐户的说明，以及如何使用 Azure 存储资源管理器 连接到 Azure 存储 位置以下载导出的文档。 有关此Azure 存储资源管理器，请参阅使用[Azure 存储资源管理器。](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)

## <a name="before-you-export-documents-from-a-review-set"></a>从审阅集导出文档之前

- 您需要为 Azure 存储 帐户提供共享访问签名 (SAS) 令牌，并提供存储帐户中特定容器的 URL，以便从审阅集导出文档。 例如，执行步骤 2 时 (，请务必将这些文件复制到文本文件) 文件

  - **SAS 令牌**：确保获取 SAS 令牌用于你的 Azure 存储 帐户 (而不是用于容器) 。 可以在应用程序内为帐户生成 SAS Azure 存储。 为此，请转到"Azure 存储帐户"，然后选择存储帐户边栏选项卡中"设置 **设置"** 下的"共享访问签名"。 生成 SAS 令牌时，使用默认设置并允许所有资源类型。

  - **容器 URL：** 需要创建一个容器以将审阅集文档上载到其中，然后获取容器 URL 的副本;例如， `https://ediscoverydata.blob.core.windows.net/exportdata` 。 若要获取 URL，请转到 Azure 存储 中的容器，然后选择容器边栏选项卡中 **"设置"** 部分下的"属性"。

- 下载并安装Azure 存储资源管理器。 有关说明，请参阅[Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。 使用此工具连接到 Azure 存储 帐户中的容器，并下载在步骤 1 中导出的文档。

## <a name="step-1-export-the-documents-from-a-review-set"></a>步骤 1：从审阅集导出文档

第一步是创建导出作业以将文档从审阅集导出。 有关所有导出选项的详细说明，请参阅从 [审阅集导出文档](export-documents-from-review-set.md)。 以下过程将突出显示用于将文档导出到组织的 Azure 存储 帐户的设置。

1. 在Microsoft 365 合规中心中，打开Advanced eDiscovery"案例，选择"审阅集"选项卡，然后选择要导出的审阅集。

2. 在审阅集内，单击"**操作导出**  >  **"。**

3. 在" **导出选项** "飞出页上，键入导出 (必需的) 和 () 选项的名称。

4. 配置文档、元数据、内容和选项部分中的设置。 有关这些设置详细信息，请参阅从 [审阅集导出文档](export-documents-from-review-set.md)。

5. 在"**输出选项**"部分，选择导出到您的"压缩目录Azure 存储 **选项**。

6. 将存储帐户的容器 URL 和 SAS 令牌粘贴到相应的字段中。

   ![将连接 URL 和 SAS 令牌粘贴到相应的字段中。](../media/AzureStorageOutputOptions.png)

7. 单击 **"** 导出"创建导出作业。

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>步骤 2：从导出作业获取 SAS URL

下一步是获取在步骤 1 中创建导出作业后生成的 SAS URL。 使用 SAS URL 连接到将审阅集Azure 存储导出到的帐户中的容器。

1. 在 **"Advanced eDiscovery"** 页上，转到案例，然后单击"导出 **"** 选项卡。

2. 在 **导出** 选项卡上，点击要下载的导出作业。 这是在步骤 1 中创建的导出作业。

3. 在飞出页面上的"位置 **"下**，复制显示的 SAS URL。 如有必要，你可以将其保存到文本文件，以便可以在步骤 3 中访问它。

   ![复制"位置"下显示的 SAS URL。](../media/eDiscoExportJob.png)

   > [!TIP]
   > 导出作业中显示的 SAS URL 是容器 URL 和您的 Azure 存储 令牌的串联。 你可以从导出作业复制它，或者通过组合 URL 和 SAS 令牌自己创建它。

## <a name="step-3-connect-to-the-azure-storage-container"></a>步骤 3：连接到Azure 存储容器

最后一步是使用 Azure 存储资源管理器 和 SAS URL 连接到 Azure 存储 帐户中的容器，将导出的文档下载到本地计算机。

1. 启动Azure 存储资源管理器下载并安装的文件。

2. 单击"**打开连接对话框"** 图标。

   ![单击"添加帐户"图标。](../media/AzureStorageConnect.png)

3. 在"要 **连接"Azure 存储，** 单击 **"Blob 容器"。**

4. 在"**选择身份验证方法**"页上，选择"SAS (**共享) "** 选项，然后单击"下一 **步"。**

5. 在"**输入连接信息**"页上， (在"Blob 容器 SAS URL"框中的步骤 2) 导出作业中获得的 **SAS URL。**

    ![将 SAS URL 粘贴到 URI 框中。](../media/AzureStorageConnect3.png)

    请注意，容器名称显示在"显示名称 **"** 框中。 可以编辑此名称。

6. 单击 **"下** 一步"**显示摘要** 页，然后单击 **"连接"。**

    将 **打开"连接** ("存储" ("下的"blob)   >   \> 节点。

    ![导出 Blob 容器节点中的作业。](../media/AzureStorageConnect5.png)

    它包含一个名为 的容器，显示名称步骤 5 中的步骤。 此容器包含已下载到每个导出作业的文件夹，该导出作业下载到 Azure 存储 帐户。 这些文件夹的命名 ID 与导出作业的 ID 相对应。 您可以在 Advanced eDiscovery 案例的"作业"选项卡上列出的每个"准备导出数据"作业的"支持"页面上的"支持信息"下找到这些导出 (和导出) 的名称。 

7. 双击导出作业文件夹以打开它。

   将显示文件夹和导出报告的列表。

    ![导出文件夹包含导出的文件和导出报告。](../media/AzureStorageConnect6.png)

8. 若要从导出作业导出所有内容，请单击向上箭头返回到导出作业文件夹，然后单击 **下载。**

9. 指定要用于下载导出文件的位置，然后点击选择文件夹。

    下载Azure 存储资源管理器启动下载过程。 下载导出项目的状态显示在"活动 **"窗格中。** 下载完成后将显示一条消息。

> [!NOTE]
> 可以选择要下载和查看的特定项目，而不是在 Azure 存储资源管理器 中下载整个导出作业。

## <a name="more-information"></a>更多信息

- 导出作业文件夹包含以下项目。 导出文件夹中的实际项目由创建导出作业时配置的导出选项确定。 有关这些选项的详细信息，请参阅从 [审阅集导出文档](export-documents-from-review-set.md)。

  - Export_load_file.csv：此 CSV 文件是包含有关每个导出文档的信息的详细导出报告。 文件由文档的每个元数据属性的列组成。 有关此报告中包含的元数据的列表和说明，请参阅文档元数据字段中的表的导出字段名称列[Advanced eDiscovery。](document-metadata-fields-in-advanced-ediscovery.md)

  - Summary.txt：包含导出摘要（包括导出统计信息）的文本文件。

  - Extracted_text_files：此文件夹包含每个导出文档的文本文件版本。

  - NativeFiles：此文件夹包含每个导出文档的本机文件版本。

  - Error_files：导出作业包含任何错误文件时，此文件夹包含以下项目：

    - ExtractionError.csv：此 CSV 文件包含未从父项正确提取的文件的可用元数据。

    - ProcessingError：此文件夹包含包含处理错误的文档。 此内容位于项目级别，这意味着如果附件有处理错误，则包含附件的文档也将包含在此文件夹中。
