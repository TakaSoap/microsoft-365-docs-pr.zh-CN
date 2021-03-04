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
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>从高级电子数据展示中的审阅集导出文档

导出允许用户自定义下载包中包含的内容。 导出工具提供具有以下设置的配置页：

![用于从审阅集导出项目的选项](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a>导出选项

- 导出名称：导出作业的名称。

- 说明：要添加说明的自定义文本字段。

- 导出以下文档：

  - 仅选定文档 - 仅导出当前选择的文档。
  
  - 审阅集内的所有文档 - 导出审阅集内的所有文档

- Metadata
  
  - 加载文件 - 此文件包含每个文件的元数据。 有关包含哪些字段的信息，请参阅高级电子数据展示中的 [文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md)。 此文件通常由第三方电子数据展示工具进行提供。
  
  - 标记 - 选中后，标记信息将包含在加载文件中。

- 内容
  
  - 本机文件 - 选中此复选框可包含本机文件。
  
  - 对话选项
    
    - 对话文件 - 导出重新构建的聊天消息。 此格式以类似于用户在本机应用程序中看到的内容的形式呈现对话。
    
    - 单个聊天消息 - 导出存储在 Microsoft 365 中的原始对话文件。

- 选项

  - 文本文件 - 包括本机文件的提取文本版本。
  
  - 将修订的本机文件替换为转换后的 PDF - 如果在审阅期间生成修订的 PDF 文件，则这些文件可供导出。 可以选择仅导出已修订的本机文件 (不选择此选项) 也可以选择此选项以导出包含实际修订的 PDF 文件。

- 导出 (的输出选项可通过 Web 浏览器直接下载，也可以发送到 Azure 存储帐户。 前两个选项支持直接下载。) 
  
  - 如果可能 (，将松散文件和 PTS 添加到) PTS - 以类似于用户本机应用程序中看到的原始目录结构的格式导出文件。  有关详细信息，请参阅 ["Loose 文件和 PST 导出结构"](#loose-files-and-pst-export-structure) 部分。
  
  - 压缩目录结构 - 导出文件并包含在下载中。
  
  - 导出到 Azure 存储帐户的压缩目录结构 - 文件导出到组织的 Azure 存储帐户。

## <a name="loose-files-and-pst-export-structure"></a>松散文件和 PST 导出结构

如果选择此选项，导出的内容将按以下结构进行组织：

- 根文件夹 – 此文件夹的名称为 ExportName.zip
  
  - Export_load_file.csv - 元数据文件。
  
  - Summary.csv - 还包含导出统计信息的摘要文件。
  
  - Exchange - 此文件夹包含来自 Exchange 的本机文件格式的所有内容。 如果选择"将已修订的本机文件替换为转换后的 PDF"选项，则本机文件 **将替换为修订的 PDF。**
  
  - SharePoint = 此文件夹包含 SharePoint 中采用本机文件格式的所有本机内容。 如果选择"将已修订的本机文件替换为转换后的 PDF"选项，则本机文件 **将替换为修订的 PDF。**

## <a name="condensed-directory-structure"></a>压缩目录结构

- 根文件夹 - 此文件夹ExportName.zip
  
  - Export_load_file.csv - 元数据文件。
  
  - Summary.txt - 还包含导出统计信息的摘要文件。
  
  - Input_or_native_files - 此文件夹包含导出的所有本机文件。 如果导出修订的 PDF 文件，则它们不会放入 PST 文件中。 相反，它们被添加到一个分隔的文件夹。
  
  - Error_files - 如果导出中包含此文件夹，则此文件夹包含以下错误文件：
    
    - ExtractionError。 包含未正确从父文件提取的任何可用文件的元数据的 CSV 文件。
    
    - ProcessingError – 此文件包含包含处理错误的文档列表。 此内容为项目级别，这意味着如果附件导致处理错误，则包含附件的电子邮件将包含在此文件夹中。
  
  - Extracted_text_files - 此文件夹包含处理时生成的所有提取的文本文件。

> [!NOTE]
> 导出作业在案例的生命周期内保留。 但是，您必须在导出作业完成后的 30 天内从导出作业下载内容。
