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
description: 了解如何在适用于企业Microsoft 365 AutoPilot 创建 CSV 文件。
ms.openlocfilehash: bc67e32d834ec8fde13386fb02ef1368ca3757cef47e78575d00a3e3d2fc6db3
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53824115"
---
# <a name="device-list-csv-file"></a>设备列表 CSV 文件

## <a name="device-list-csv-file-format"></a>设备列表.csv文件格式

若要通过 Autopilot Windows和部署设备，你需要一个.csv设备特定信息的文件。
  
设备列表文件的列必须按指定顺序具有以下标题：
  
- 列 A：设备序列号

- 列 B：保留为空

- 列 C：硬件哈希

可从硬件供应商获取此信息，也可以使用将生成 CSV 文件的 [G-et-WindowsAutoPilotInfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)获取。 

添加设备时，还需要将它们添加到配置文件。 配置文件用于将 AutoPilot 部署配置文件应用于设备或一组设备。
  
## <a name="related-articles"></a>相关文章

[Microsoft 365文档和资源](../../business/index.yml)
  
[企业Microsoft 365入门](../../business/microsoft-365-business-overview.md)
  
[管理Microsoft 365企业部署](../../business/manage.md)
