---
title: 设备列表 CSV-文件
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 了解如何在 Microsoft 365 for business 中为 AutoPilot 创建 CSV 文件。
ms.openlocfilehash: 030fb96e9e60c792fb685af57d34eacd6670645a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399358"
---
# <a name="device-list-csv-file"></a>设备列表 CSV-文件

## <a name="device-list-csv-file-format"></a>设备列表 .csv 文件格式

若要通过 Windows Autopilot 管理和部署设备，您需要一个包含有关设备的特定信息的 .csv 文件。
  
设备列表文件中的列必须按指定的顺序包含以下标头：
  
- 列 A：设备序列号

- 列 B：留空

- 列 C：硬件哈希

可从硬件供应商获取此信息，也可以使用将生成 CSV 文件的 [G-et-WindowsAutoPilotInfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)获取。 

添加设备时，还需要将其添加到配置文件中。 配置文件用于将 AutoPilot 部署配置文件应用于一个或一组设备。
  
## <a name="related-articles"></a>相关文章

[适用于业务的 Microsoft 365 文档和资源](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Microsoft 365 商业版入门](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[管理 Microsoft 365 商业版](https://docs.microsoft.com/microsoft-365/business/manage)
  
