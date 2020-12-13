---
title: 导入非 Microsoft 365 内容进行高级电子数据展示分析
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: 如何将未存储在 Microsoft 365 中的内容导入 Azure blob，以便使用 AeD 进行分析的步骤
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 03220e6baf16662ad8dfa970ef4d7077d08b0826
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662897"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>导入非 Microsoft 365 内容进行高级电子数据展示 (经典) 分析

并非所有可能需要使用高级电子数据展示分析的文档都将在 Microsoft 365 中提供。 借助高级电子数据展示中的非 Microsoft 365 内容导入功能，可以将不居住在 Microsoft 365 (但 PST 文件) 以外的文档上载到案例链接的 Azure 存储 blob 中，然后使用高级电子数据展示对其进行分析。 此过程演示如何将非 Microsoft 365 文档引入高级电子数据展示进行分析。
  
> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
> [!NOTE]
> 你可以为非 Microsoft 365 内容购买高级电子数据展示数据存储附加订阅。 这专用于使用高级电子数据展示进行分析的内容。 按照购买或编辑 [Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) 商业版加载项中的步骤操作，并购买高级电子数据展示存储加载项。 
  
## <a name="requirements-to-upload-non-office-365-content"></a>上载非 Office 365 内容的要求

如此过程所述，使用上载非 Office 365 功能需要具备：
  
- 具有高级合规性加载项或 E5 订阅的 Office 365 E3。
    
- 将上载非 Office 365 内容的所有保管人必须具有具有高级合规性加载项的 E3 或 E5 许可证。
    
- 现有电子数据展示案例。
    
- 所有用于上载的文件都收集到文件夹中，其中每个保管人有一个文件夹，并且文件夹的名称采用以下格式 *alias@domainname。* 用户  *alias@domainname*  用户 Office 365 别名和域。 你可以将  *所有alias@domainname文件夹*  收集到根文件夹中。 根文件夹只能包含alias@domainname文件夹，根文件夹中不得有松散文件。
    
- 作为电子数据展示管理员或电子数据展示管理员的帐户。
    
- [Microsoft Azure 存储工具](https://aka.ms/downloadazcopy) 安装在有权访问非 Office 365 内容文件夹结构的计算机上。 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>将非 Office 365 内容上载到高级电子数据展示


1. 作为电子数据展示管理员或电子数据展示管理员，打开 **电子** 数据展示，并打开非 Office 365 数据将上载到的案例。 如果需要创建事例，请参阅安全合规中心中的"管理电子数据展示[ &amp; 事例"。](ediscovery-cases.md)
    
2. 单击 **"切换到高级电子数据展示"。**

3. 从 **菜单中选择** "审阅集"。

4. 选择现有审阅集或选择 **"添加审阅集"。**

5. 选择 **"管理审阅集"。**

6. 在"非 Office 365 数据卡"中，选择 **"查看上载"。**

7. 选择 **"上载文件** "以启动文件上载向导。

8. 第一个选项卡为 **1。准备步骤**。 选择 **"下一步： 上载文件"。**

9. 在 **2."上载** 文件"选项卡将提示你AzCopy.exe下载文件，如果尚未下载，然后提供文件位置的路径。 例如， `C:\Upload`  将为您提供命令以执行AzCopy.exe。 使用 `C:\Upload` 时，你将看到：

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. 打开命令提示符窗口并执行AzCopy.exe命令将数据导入 Azure。 加载所有数据后，选择"下一 **步： 处理文件"。**

11. 下一个选项卡为 **3。处理** 文件，你将看到具有与其关联的数据的保管人，并且还会显示正在导入的数据的进度。
        
    有关 Azcopy 语法详细信息，请参阅 Windows 上的 [AzCopy 传输数据](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。 
    
    有关高级电子数据展示处理的更多详细信息，请参阅"运行流程"模块，并加载经典电子数据展示 ([数据) 。 ](run-the-process-module-and-load-data-in-advanced-ediscovery.md) 
    
    > [!IMPORTANT]
    > 每个用户必须有一个根文件夹，并且文件夹名称必须采用 alias@domainname<b>格式。</b> 
   
    > [!IMPORTANT]
    > 在高级电子数据展示中成功处理容器后，你将不再能够将新内容添加到 Azure 中的 SAS 存储。 如果收集其他内容，并且要将其添加到高级电子数据展示分析案例，则必须创建新的非 **Office 365** 数据容器并重复此过程。 
  
    > [!NOTE]
    > 如果容器  *由于文件夹*  命名问题而未成功处理，然后修复问题，则仍必须新建容器，然后使用本文中的过程重新连接和上载。
