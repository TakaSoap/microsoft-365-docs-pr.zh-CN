---
title: 核心电子数据展示案例中的限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文介绍了 Microsoft 365 中的核心电子数据展示案例中的限制。
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799659"
---
# <a name="limits-in-core-ediscovery"></a>核心电子数据展示中的限制

下表列出了与核心电子数据展示事例关联的核心电子数据展示事例和保留的限制。 有关核心电子数据展示详细信息，请参阅 [核心电子数据展示概述](ediscovery-cases.md)。
    
  | 限制说明 | 限制 |
  |:-----|:-----|
  |组织的最大事例数  <br/> |无限制  <br/> |
  |组织的最大案例保留数  <br/> |10,000  <br/> |
  |单个案例保留中的最大邮箱数  <br/> |1,000  <br/> |
  |单个案例保留中 SharePoint 和 OneDrive for Business 网站的最大数量  <br/> |100  <br/> |
  |核心电子数据展示主页上显示的最大事例数，以及事例中的保留、搜索和导出选项卡上显示的最大项目数。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> 若要查看超过 1，000 个事例、保留、搜索或导出的列表，可以使用相应的 Office 365 安全与合规 PowerShell & cmdlet：
   > 
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

有关与核心电子数据展示案例关联的内容搜索和导出相关的限制详细信息，请参阅内容搜索和核心 [电子数据展示的限制](limits-for-content-search.md)。