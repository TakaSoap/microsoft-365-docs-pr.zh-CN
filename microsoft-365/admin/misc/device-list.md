---
title: 设备列表 CSV 文件
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: 了解如何在 Microsoft 365 商业版中为 AutoPilot 创建 CSV 文件。
ms.openlocfilehash: 13d7fbffd8d6fbe1af0dde55a4e98688060d9da8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579214"
---
# <a name="device-list-csv-file"></a>设备列表 CSV 文件

## <a name="device-list-csv-file-format"></a>设备列表 .csv 文件格式

若要通过 Windows Autopilot 管理和部署设备，你需要一个包含有关设备的特定信息的 .csv 文件。
  
设备列表文件的列必须按指定顺序具有以下标题：
  
- 列 A：设备序列号

- 列 B：保留为空

- 列 C：硬件哈希

可从硬件供应商获取此信息，也可以使用将生成 CSV 文件的 [G-et-WindowsAutoPilotInfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)获取。 

添加设备时，还需要将它们添加到配置文件。 配置文件用于将 AutoPilot 部署配置文件应用于设备或一组设备。
  
## <a name="related-articles"></a>相关文章

[Microsoft 365 商业版文档和资源](../../business/index.yml)
  
[Microsoft 365 商业版入门](../../business/microsoft-365-business-overview.md)
  
[管理 Microsoft 365 商业版](../../business/manage.md)
