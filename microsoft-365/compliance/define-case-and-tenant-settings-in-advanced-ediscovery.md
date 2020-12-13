---
title: 在高级电子数据展示中定义案例和租户设置
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 383809de-7f5e-4a1d-9098-c525f67b7a9a
description: 了解可以在高级电子数据展示的大小写级别定义的标签、跨模块和租户设置。
ms.openlocfilehash: e2f46a9339e2c134be505138aac6886cb1a2dd9a
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663047"
---
# <a name="define-case-and-tenant-settings-in-advanced-ediscovery-classic"></a>在高级电子数据展示和经典服务中定义 (和租户) 

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本主题介绍了高级电子数据展示案例和租户设置。
  
## <a name="case-settings"></a>案例设置

以下各节介绍可在案例级别定义的设置。
  
> [!NOTE]
> 如果当前在高级电子数据展示中未选择任何案例，则 **"案例设置** "选项卡处于非活动状态。 
  
### <a name="cross-module"></a>交叉模块

以下交叉模块设置是适用于高级电子数据展示模块的大小写选项。
  
- 登录后的默认页面：设置启动高级电子数据展示时要显示的默认页面。
    
- 文件显示名称：将在高级电子数据展示中显示以标识文件的文件标识符，作为文件标题/路径或电子邮件主题的高级电子数据展示显示名称的替代项。
    
1. 通过 **单击 Cogwheel** 图标打开" **设置"和** 实用程序。 打开 **"设置"和实用程序 \> "案例设置"** 选项卡 \> **"交叉"模块**。 
    
2. 从登录 **选项后的"默认"页** 中进行选择： 
    
  - **上一登录的最后一页**
    
  - **事例页面**
    
3. 单击“**保存**”。
    
## <a name="tenant-settings"></a>租户设置

本节介绍了高级电子数据展示租户设置。
  
### <a name="user-administration"></a>用户管理

用户管理选项在"设置用户 [和事例"中进行了介绍](set-up-users-and-cases-in-advanced-ediscovery.md)。
  
### <a name="event-log"></a>事件日志

事件日志在高级电子数据展示操作期间随时提供有关高级电子数据展示处理的元数据。 例如，它包括主要高级电子数据展示流程的开始时间 (导入、分析、相关性和导出) 以及结束时间和状态。 此日志可用于跟踪和排查数据处理活动并解决错误和警告。
  
1. 通过 **单击 Cogwheel** 图标打开" **设置"和** 实用程序。 
    
2. 在" **设置和实用程序 \> 租户设置"** 选项卡中，选择 **事件日志**。 将显示事件日志数据。
    
  - 若要按事例筛选日志输出，请从事例 **列表中选择事例。** 
    
  - 若要按列对日志进行排序，请单击列标题。 
    
  - 若要修改列顺序，请单击并拖动列标题。
    
  - 若要在日志页之间移动，请单击 **\>** 和 **\<** 图标。 
    
### <a name="system-information"></a>系统信息

高级电子数据展示版本系统信息和活动任务显示在"租户设置"选项卡中。
  
1. 通过 **单击 Cogwheel** 图标打开" **设置"和** 实用程序。 
    
2. 在 **"设置和实用程序 \> 租户设置"** 选项卡中，选择 **"系统信息"。** 将显示版本信息。
    
可通过单击租户信息下方的 **"** 刷新"图标来更新显示。 
  
## <a name="see-also"></a>另请参阅

[高级电子数据展示（经典）](office-365-advanced-ediscovery.md)
  
[使用实用程序](use-advanced-ediscovery-utilities.md)

