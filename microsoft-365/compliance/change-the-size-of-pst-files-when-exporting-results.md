---
title: 导出电子数据展示搜索结果时更改 PST 文件的大小
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 导出电子数据展示搜索结果时，可以更改下载到计算机中的 PST 文件的默认大小。
ms.openlocfilehash: 76f15e590e1a12468f197f81a1963c9bce06c65008e0570df7bbbaf77b2e9d52
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53851511"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>导出电子数据展示搜索结果时更改 PST 文件的大小

使用电子数据展示导出工具从不同的 Microsoft 电子数据展示工具导出电子数据展示搜索的电子邮件结果时，可以导出的 PST 文件的默认大小为 10 GB。 如果要更改此默认大小，可以在Windows导出搜索结果的计算机上编辑注册表。 这样做的一个原因是，PST 文件可以容纳在可移动媒体（如 DVD、光盘或 USB 驱动器）上。 
  
> [!NOTE]
> 使用安全 & 合规中心、Exchange Online 中的 In-Place 电子数据展示和 SharePoint Online 中的电子数据展示中心中的内容搜索工具时，电子数据展示导出工具用于导出搜索结果。
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>创建注册表设置以在导出电子数据展示搜索结果时更改 PST 文件的大小

在您将用于导出电子数据展示搜索结果的计算机上执行以下过程。
  
1. 关闭电子数据展示导出工具（如果已打开）。 
    
2. 使用文件名后缀 .reg 将以下文本保存到 Window 注册表文件中;例如，PstExportSize.reg。 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    在以上示例中，该值  `PstSizeLimitInBytes` 设置为 1，073，741，824 字节或大约 1 GB。 下面是设置的其他一些示例  `PstSizeLimitInBytes` 值。 
    
    |**大小（以 GB (.)**|**大小（以字节为单位）**|
    |:-----|:-----|
    |0.7 GB (700 MB)   <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. 在导出搜索结果，然后保存文件时，将该值更改为所需 PST 文件 `PstSizeLimitInBytes` 的最大大小。 
    
4. 在Windows资源管理器中，单击或双击在之前步骤中创建的 .reg 文件。
    
5. 在"用户访问控制"窗口中，单击 **"是** "让注册表编辑器做出更改。 
    
6. 当系统提示继续时，单击"**是"。**
    
    注册表编辑器显示一条消息，指出已成功将设置添加到注册表中。
    
7. 可以重复步骤 3 - 6 来更改注册表  `PstSizeLimitInBytes` 设置的值。 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>有关在导出电子数据展示搜索结果时更改 PST 文件默认大小的常见问题

 **为什么默认大小为 10 GB？**
  
默认大小 10 GB 基于客户反馈;10 GB 是一个 PST 中的最佳内容量与最小文件损坏率之间的良好平衡。
  
 **我应该增加还是减小 PST 文件的默认大小？**
  
客户倾向于减小大小限制，以便搜索结果适合可实际发至组织中其他位置的可移动媒体。 建议不要增大默认大小，因为大于 10 GB 的 PST 文件可能有损坏问题。
  
 **在什么计算机上必须这样做？**
  
您需要在运行电子数据展示导出工具的任何本地计算机上更改注册表设置。
  
 **更改此设置后，是否必须重新启动计算机？**
  
否，无需重新启动计算机。 但是，如果电子数据展示导出工具正在运行，你必须关闭它，在更改此设置后重新启动它。
  
 **是否编辑了现有注册表项，或是否创建了新注册表项？**
  
在首次运行您在此过程中创建的 .reg 文件时，会创建一个新的注册表项。 然后，每次更改并重新运行 .reg 编辑文件时，将编辑该设置。
