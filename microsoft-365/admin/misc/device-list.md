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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: 了解如何在 Microsoft 365 for business 中为 AutoPilot 创建 CSV 文件。
ms.openlocfilehash: b1154d639ba23180f637520750d94f00e997cfc4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627856"
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
  
[Microsoft 365 商业版入门](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[管理 Microsoft 365 商业版](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
