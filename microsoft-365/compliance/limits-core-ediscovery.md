---
title: 核心电子数据展示事例的限制
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
description: 本文介绍了 Microsoft 365 核心电子数据展示事例的限制。
ms.openlocfilehash: 6224ce5ecb8fc0439e43ab5e1362f8a618194202
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358510"
---
# <a name="limits-in-core-ediscovery"></a>核心电子数据展示中的限制

下表列出了与核心电子数据展示事例相关联的核心电子数据展示事例和保留的限制。 有关核心电子数据展示的详细信息，请参阅 [核心电子数据展示概述](ediscovery-cases.md)。
    
  |**限制说明**|**限制**|
  |:-----|:-----|
  |组织的最大事例数  <br/> |无限制  <br/> |
  |组织的最大事例保留数  <br/> |10,000  <br/> |
  |单个事例保留中的最大邮箱数  <br/> |1,000  <br/> |
  |单个事例保留中的 SharePoint 和 OneDrive for business 网站的最大数量  <br/> |100  <br/> |
  |显示在核心电子数据展示主页上的最大事例数，以及在某一事例中的保留、搜索和导出选项卡上显示的最大项目数。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> 若要查看超过1000个事例、保留、搜索或导出的列表，您可以使用相应的 Office 365 安全性 & 合规性 PowerShell cmdlet：<br/> [Get-compliancecase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [New-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
