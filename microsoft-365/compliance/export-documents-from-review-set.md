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
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>从高级电子数据展示中的审阅集导出文档

导出允许用户在从高级电子数据展示中的审阅集导出文档时自定义下载包中包含的内容。

从审阅集导出文档：

1. 在 Microsoft 365 合规中心，打开"高级电子数据展示"案例，选择"审阅集"选项卡，然后选择要导出的审阅集。

2. 在审阅集内，单击"操作 **导出**  >  **"。**

   "导出"工具显示包含用于配置导出的设置的飞出页。 默认情况下会选择某些选项，但可以更改这些选项。 有关可以配置的导出选项的说明，请参阅以下部分。

   ![用于从审阅集导出项目的配置选项](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. 配置导出后，单击" **导出** "开始导出过程。 根据在"输出选项"部分选择的选项，可以通过直接下载或组织的 Azure 存储帐户访问导出文件。

> [!NOTE]
> 导出作业在案例的生命周期内保留。 但是，您必须在导出作业完成后的 30 天内从导出作业下载内容。

## <a name="export-options"></a>导出选项

使用以下选项配置导出。

- **导出名称**：导出作业的名称。

- **说明**：要添加说明的自定义文本字段。

- **导出这些文档**

  - **仅选定文档**：此选项仅导出当前选定的文档。
  
  - **审阅集内的所有文档**：此选项导出审阅集内的所有文档。

- **元数据**
  
  - **加载文件**：此文件包含每个文件的元数据。 此文件通常由第三方电子数据展示工具进行使用。 有关包含哪些字段的信息，请参阅高级电子数据 [展示中的文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md)。
  
  - **标记**：选中后，标记信息将包含在加载文件中。

- **内容**
  
  - **本机文件**：选中此复选框以在审阅集内包含文档的本机文件。 如果选择导出本机文件，可以选择以下选项来导出聊天对话。
  
  - **对话选项**

    - **对话文件**：此选项导出重新构造的聊天对话。 此格式以类似于用户在本机应用程序中看到的内容的形式呈现对话。

    - **单个聊天消息**：此选项导出原始对话文件，因为它们存储在 Microsoft 365 中。

- **选项**

  - **文本文件 ：**- 此选项包括导出中的本机文件的提取文本版本。
  
  - **将修订的本机替换为转换的 PDF：** 如果在审阅期间生成修订的 PDF 文件，则这些文件可供导出。 可以选择不选择此选项 (导出已修订的本机文件) 也可以选择此选项以导出包含实际修订的 PDF 文件。

- **输出选项**：导出的内容可以直接通过 Web 浏览器下载，也可以发送到 Azure 存储帐户。 前两个选项支持直接下载。
  
  - **如果可能 (，** 将松散文件和 PTS 添加到 PST) ：文件以类似于用户本机应用程序中看到的原始目录结构的格式导出。  有关详细信息，请参阅 Loose [files and PST export structure部分](#loose-files-and-pst-export-structure) 。
  
  - **压缩目录结构**：导出文件并包含在下载中。
  
  - **导出到 Azure 存储帐户的** 压缩目录结构：文件将导出到组织的 Azure 存储帐户。 对于此选项，你必须提供 Azure 存储帐户中容器的 URL，以将文件导出到。 你还必须提供 Azure 存储帐户的共享访问签名 (SAS) 令牌。 有关详细信息，请参阅 [将审阅集内的文档导出到 Azure 存储帐户](download-export-jobs.md)。

以下各节介绍松散文件和压缩目录结构选项的文件夹结构。

### <a name="loose-files-and-pst-export-structure"></a>松散文件和 PST 导出结构

如果选择此导出选项，则导出的内容按以下结构进行组织：

- 根文件夹：名为 ExportName.zip
  
  - Export_load_file.csv：元数据文件。
  
  - Summary.csv：还包含导出统计信息的摘要文件。
  
  - Exchange：此文件夹包含来自 Exchange 的本机文件格式的所有内容。 如果选择了"将已修订的本机替换为转换后的 PDF"选项，本机文件将 **替换为修订的 PDF。**
  
  - SharePoint：此文件夹包含 SharePoint 中采用本机文件格式的所有本机内容。 如果选择了"将已修订的本机替换为转换后的 PDF"选项，本机文件将 **替换为修订的 PDF。**

### <a name="condensed-directory-structure"></a>压缩目录结构

- 根文件夹：此文件夹名为 ExportName.zip
  
  - Export_load_file.csv：元数据文件。
  
  - Summary.txt：还包含导出统计信息的摘要文件。
  
  - NativeFiles：此文件夹包含已导出的所有本机文件。 如果导出修订的 PDF 文件，则它们不会放入 PST 文件中。 相反，它们被添加到一个分隔的文件夹。
  
  - Error_files：如果导出中包含此文件夹，则此文件夹包含以下错误文件：

    - ExtractionError：包含未从父文件正确提取的任何可用文件的元数据的 CSV 文件。

    - ProcessingError：此文件包含包含处理错误的文档的列表。 此内容为项目级，这意味着如果附件导致处理错误，则包含附件的电子邮件将包含在此文件夹中。
  
  - Extracted_text_files：此文件夹包含处理过程中生成的所有提取的文本文件。
