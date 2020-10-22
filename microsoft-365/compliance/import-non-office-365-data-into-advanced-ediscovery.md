---
title: 导入非 Microsoft 365 内容以实现高级电子数据展示分析
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
description: 操作方法：将未存储在 Microsoft 365 中的内容导入到 Azure blob 中，以便可以使用 AeD 对其进行分析
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be30daa35770247a9dd342b88093872083075547
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636949"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>导入非 Microsoft 365 内容以获取高级电子数据展示 (经典) 分析

并非所有可能需要使用高级电子数据展示进行分析的文档都会在 Microsoft 365 中生存。 使用高级电子数据展示中的非 Microsoft 365 内容导入功能，可以将不在 Microsoft (365 中运行的文档（PST 文件) 除外）上载到链接的 Azure 存储 blob，并使用高级电子数据展示分析这些文档的情况。 此过程向您演示如何将非 Microsoft 365 文档转换为高级电子数据展示以进行分析。
  
> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
> [!NOTE]
> 您可以购买非 Microsoft 365 内容的高级电子数据展示数据存储附加订阅。 这仅适用于要使用高级电子数据展示进行分析的内容。 按照 [为 Microsoft 365 for Business 购买或编辑加载](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) 项中的步骤进行操作，并购买高级电子数据展示存储加载项。 
  
## <a name="requirements-to-upload-non-office-365-content"></a>上载非 Office 365 内容的要求

如以下过程所述，使用 "上载非 Office 365" 功能需要具备以下条件：
  
- 具有高级合规性外接程序或 E5 订阅的 Office 365 E3。
    
- 将上载其非 Office 365 内容的所有保管人必须具有具有高级合规性附加或 E5 许可证的 E3。
    
- 现有电子数据展示事例。
    
- 将上载的所有文件都收集到每个保管人都有一个文件夹的文件夹中，文件夹的名称  *alias@domainname*  的格式。 *Alias@domainname*必须是用户 Office 365 别名和域。 您可以将所有  *alias@domainname*  文件夹收集到一个根文件夹中。 根文件夹只能包含  *alias@domainname*  文件夹，根文件夹中必须没有松散文件。
    
- 既可以是电子数据展示管理器，也可以是电子数据展示管理员的帐户。
    
- 在有权访问非 Office 365 内容文件夹结构的计算机上安装了[Microsoft Azure 存储工具](https://aka.ms/downloadazcopy)。 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>将非 Office 365 内容上载到高级电子数据展示


1. 作为电子数据展示管理器或电子数据展示管理员，打开 **电子数据展示**，并打开将向其上载非 Office 365 数据的大小写。 如果您需要创建一个事例，请参阅 [在安全 &amp; 合规中心中管理电子数据展示事例](ediscovery-cases.md)。
    
2. 单击 " **切换到高级电子数据展示**"。

3. 从菜单中选择 " **查看集** "。

4. 选择现有的审阅集或选择 " **添加审阅集**"。

5. 选择 " **管理审阅集**"。

6. 在非 Office 365 数据卡中，选择 " **查看上载**"。

7. 选择 " **上载文件** " 以启动文件上载向导。

8. 第一个选项卡为 **1。准备步骤**。 选择 " **下一步：上传文件**"。

9. **2。"上载文件**" 选项卡系统会提示您下载 AzCopy.exe （如果尚未执行此操作），然后提供文件位置的路径。 例如， `C:\Upload`  将为您提供执行 AzCopy.exe 的命令。 使用 `C:\Upload` ，你将看到：

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. 打开命令提示符窗口并执行 AzCopy.exe 命令，将数据导入到 Azure 中。 加载所有数据后，选择 " **下一步：处理文件**"。

11. 下一个选项卡为 **3。处理文件** ，您将在其中看到具有相关数据的保管人，还将向您显示正在导入的数据的进度。
        
    有关 Azcopy 语法的详细信息，请参阅 [使用 Windows 上的 Azcopy 传输数据](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。 
    
    有关高级电子数据展示处理的更多详细信息，请参阅 [在高级电子数据展示 (经典) 中运行 Process module and load data ](run-the-process-module-and-load-data-in-advanced-ediscovery.md)。 
    
    > [!IMPORTANT]
    > 每个用户必须有一个根文件夹，并且该文件夹名称必须为 <b>alias@domainname</b>  格式。 
   
    > [!IMPORTANT]
    > 在高级电子数据展示中成功处理容器后，您将无法再将新内容添加到 Azure 中的 SAS 存储。 如果要收集其他内容，并且想要将其添加到高级电子数据展示分析的事例中，则必须创建一个新的 **非 Office 365 数据** 容器，并重复此过程。 
  
    > [!NOTE]
    > 如果  *由于文件夹命名问题而导致容器未成功处理*  ，并且您随后解决了这些问题，您仍需使用本文中的过程创建一个新的容器，并重新连接和上传。
