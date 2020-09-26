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
ms.openlocfilehash: b3be21d4c90c861c83acf612e9aadc373189f7ba
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285358"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>在高级电子数据展示中从审阅集中导出文档

导出允许用户自定义下载包中包含的内容。 导出工具提供了具有以下设置的配置页：

![用于从审阅集中导出项目的选项](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a>导出选项

- 导出名称：导出作业的名称。

- 说明：用于添加说明的自由文本字段。

- 导出这些文档：

  - 仅选定文档-仅导出当前选定的文档。
  
  - 审阅集内的所有文档-导出审阅集中的所有文档

- 元数据
  
  - 加载文件-此文件包含每个文件的元数据。 有关包含哪些字段的详细信息，请参阅 [高级电子数据展示中的文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md) 。 此文件通常可由第三方电子数据展示工具引入。
  
  - 标记-如果选择此选项，则会将标记信息包含在加载文件中。

- 内容
  
  - 本机文件-选中此复选框可包含本机文件。
  
  - 对话选项
    
    - 会话文件-导出会重建聊天消息。 此格式以类似于用户在本机应用程序中看到的内容的形式显示对话。
    
    - 单个聊天邮件-在 Microsoft 365 中存储原始对话文件时将其导出。

- 选项

  - 文本文件-包括已提取的本机文件的文本版本。
  
  - 将编辑 natives 替换为转换后的 Pdf-如果在审阅过程中生成编辑 PDF 文件，则可使用这些文件进行导出。 您可以选择仅导出编辑 (的本机文件，而不选择此选项) 也可以选择此选项导出包含实际密文的 PDF 文件。

-  (导出内容的输出选项可通过 web 浏览器直接下载，也可发送到 Azure 存储帐户。 前两个选项启用直接下载。 ) 
  
  - 如果可能) 文件以用户的本机应用程序中显示的原始目录结构的格式导出，则会将松散文件和 Pst (电子邮件添加到 Pst。  有关详细信息，请参阅 " [松散文件和 PST 导出结构](#loose-files-and-pst-export-structure) " 部分。
  
  - 紧缩目录结构-导出文件并将其包含在下载内容中。
  
  - 导出到 Azure 存储帐户的紧缩目录结构-文件将导出到您的组织的 Azure 存储 accouunt。

## <a name="loose-files-and-pst-export-structure"></a>松散文件和 PST 导出结构

如果选择此导出选项，则导出的内容将按以下结构进行组织：

- 根文件夹–命名 ExportName.zip 中的此文件夹
  
  - Export_load_file.csv 元数据文件。
  
  - Summary.csv-也包含导出统计信息的摘要文件。
  
  - Exchange-此文件夹包含本机文件格式的 Exchange 中的所有内容。 如果选择 "将 **编辑 Natives 替换为转换的 pdf** " 选项，Natives 文件将被替换为编辑 pdf。
  
  - SharePoint = 此文件夹以本机文件格式包含来自 SharePoint 的所有本机内容。 如果选择 "将 **编辑 Natives 替换为转换的 pdf** " 选项，Natives 文件将被替换为编辑 pdf。

## <a name="condensed-directory-structure"></a>紧缩目录结构

- 根文件夹-此文件夹命名为 ExportName.zip
  
  - Export_load_file.csv 元数据文件。
  
  - Summary.txt-也包含导出统计信息的摘要文件。
  
  - Input_or_native_files-此文件夹包含导出的所有本机文件。 如果您导出编辑 PDF 文件，则它们不会放入 PST 文件中。 相反，它们将被添加到一个单独的文件夹中。
  
  - Error_files-此文件夹包含以下错误文件（如果导出中包含这些文件）：
    
    - ExtractionError. 一个 CSV 文件，其中包含未从父文件正确提取的任何可用的文件元数据。
    
    - ProcessingError –此文件包含有处理错误的文档列表。 此内容是项目级的，这意味着如果附件导致处理错误，则包含附件的电子邮件将包含在此文件夹中。
  
  - Extracted_text_files-此文件夹包含在处理过程中生成的所有提取的文本文件。

> [!NOTE]
> 导出作业在案例的生命周期内保留，并且在不删除该事例的情况下可进行下载。
