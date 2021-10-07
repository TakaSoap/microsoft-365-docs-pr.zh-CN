---
title: 导出内容搜索结果时禁用报告
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: 在本地Windows编辑注册表，以在从目录导出内容搜索的结果时禁用Microsoft 365 合规中心。
ms.openlocfilehash: bafdab1586b28239ddba7cf251704111731f2239
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163404"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>导出内容搜索结果时禁用报告

当您使用电子数据展示导出工具导出 Microsoft 365 合规中心 中的内容搜索结果时，该工具会自动创建和导出两个报告，其中包含有关导出内容的其他信息。 这些报告是Results.csv文件和 Manifest.xml 文件 (请参阅本主题中有关禁用导出报告的常见问题部分，了解这些报告[](#frequently-asked-questions-about-disabling-export-reports)的) 。 由于这些文件可能非常大，因此可以通过阻止导出这些文件来加快下载时间并节省磁盘空间。 为此，可以在Windows导出搜索结果的计算机上更改注册表。 如果要在以后包含报告，可以编辑注册表设置。 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>创建注册表设置以禁用导出报告

在您将用于导出结果的内容搜索的计算机上执行以下过程。
  
1. 关闭电子数据展示导出工具（如果已打开）。
    
2. 执行下列一个或两个步骤，具体取决于要禁用的导出报告。
    
    - **Results.csv**
    
      使用文件名后缀 .reg 将以下Windows保存到注册表文件中;例如，DisableResultsCsv.reg。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      使用文件名后缀 .reg 将以下Windows保存到注册表文件中;例如，DisableManifestXml.reg。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. 在Windows资源管理器中，单击或双击在之前步骤中创建的 .reg 文件。
    
4. 在"用户访问控制"窗口中，单击 **"是** "让注册表编辑器做出更改。 
    
5. 当系统提示继续时，单击"**是"。**
    
    注册表编辑器显示一条消息，指出已成功将设置添加到注册表中。
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>编辑注册表设置以重新启用导出报告

如果在上一过程中通过创建 .reg 文件禁用 Results.csv 和 Manifest.xml 报告，可以编辑这些文件以重新启用报告，以便随搜索结果一起导出报告。 同样，在您将用于导出结果的内容搜索的计算机上执行以下过程。
  
1. 关闭电子数据展示导出工具（如果已打开）。
    
2. 编辑在上一过程中创建的一个或两个 .reg 编辑文件。
    
    - **Results.csv**
    
        在"文件"中打开 disableResultsCsv.reg 记事本，将值更改为 `False` `True` ，然后保存该文件。 例如，编辑文件后，它如下所示：
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        在"文件"中打开 disableManifestXml.reg 记事本，将值更改为 `False` `True` ，然后保存该文件。 例如，编辑文件后，它如下所示：
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. 在Windows资源管理器"中，单击或双击在上一步中编辑的 .reg 文件。
    
4. 在"用户访问控制"窗口中，单击 **"是** "让注册表编辑器做出更改。 
    
5. 当系统提示继续时，单击"**是"。**
    
    注册表编辑器显示一条消息，指出已成功将设置添加到注册表中。
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>有关禁用导出报表的常见问题

 **报告Results.csvManifest.xml是什么？**
  
该Results.csv和Manifest.xml文件包含有关已导出内容的其他信息。
  
- **Results.csv** 一Excel文档，其中包含有关作为搜索结果下载的每个项目的信息。 对于电子邮件，结果日志包含有关每封邮件的信息，包括： 
    
  - 邮件在源邮箱中的位置（包括邮件位于主邮箱还是存档邮箱）。
    
  - 发送或接收邮件的日期。
    
  - 邮件的主题行。
    
  - 邮件的发件人和收件人。
    
  - 如果您在导出搜索结果时启用了重复数据删除，则邮件是否是重复邮件。 重复邮件将在 Parent **ItemId** 列中具有一个值，该值将邮件标识为重复邮件。 "Parent **ItemId"** 列中的值与导出的邮件的 **"Item DocumentId"** 列中的值相同。 
    
    对于来自SharePoint和OneDrive for Business的文档，结果日志包含有关每个文档的信息，包括：
    
  - 文档的 URL。
    
  - 文档所在的网站集的 URL 。
    
  - 上次修改文档的日期。
    
  - 文档的名称（位于结果日志中的主题列）。
    
- **Manifest.xml** 清单文件 (XML 格式) ，其中包含有关搜索结果中包括的每个项目的信息。 此报告中的信息与 Results.csv 报告相同，但采用电子数据发现参考模型 (EDRM) 。 有关 EDRM 详细信息，请转到 [https://www.edrm.net](https://www.edrm.net) 。
    
 **何时应禁用导出这些报告？**
  
这取决于你的特定需求。 许多组织不需要有关搜索结果的其他信息，也不需要这些报告。
  
 **在什么计算机上必须这样做？**
  
 您必须在运行电子数据展示导出工具的任何本地计算机上更改注册表设置。 
  
 **更改此设置后，是否必须重新启动计算机？**
  
否，无需重新启动计算机。 但是，如果电子数据展示导出工具正在运行，您必须关闭它，然后在更改注册表设置后重新启动它。
  
 **是否编辑了现有注册表项，或是否创建了新注册表项？**
  
第一次运行在本主题中的过程中创建的 .reg 文件时，会创建一个新的注册表项。 然后，每次更改并重新运行 .reg 编辑文件时，将编辑该设置。
