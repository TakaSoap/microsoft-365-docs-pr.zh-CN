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
description: 本文介绍了 Microsoft 365 中核心电子数据展示案例的限制。
ms.openlocfilehash: e18e1e6c1d9d7ecd78deaf267be72ccdc9d1ba5d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905884"
---
# <a name="limits-in-core-ediscovery"></a>核心电子数据展示中的限制

下表列出了与核心电子数据展示事例关联的核心电子数据展示事例和保留项的限制。 有关核心电子数据展示详细信息，请参阅核心 [电子数据展示概述](./get-started-core-ediscovery.md)。
    
  | 限制说明 | 限制 |
  |:-----|:-----|
  |组织的最大事例数。  <br/> |无限制  <br/> |
  |组织的最大案例保留数。  <br/> |10,000  <br/> |
  |单个案例保留中的最大邮箱数。 此限制包括用户邮箱总数，以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的邮箱总数。  <br/> |1,000  <br/> |
  |单个案例保留中的最大网站数。 此限制包括 OneDrive for Business 网站、SharePoint 网站以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的网站总数。  <br/> |100  <br/> |
  |核心电子数据展示主页上显示的最大事例数，以及事例中"保留项、搜索"和"导出"选项卡上显示的最大项目数。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> 若要查看超过 1，000 个事例、保留、搜索或导出的列表，可以使用相应的 Office 365 安全&合规性 PowerShell cmdlet：
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

有关与与核心电子数据展示案例相关的内容搜索和导出限制详细信息，请参阅内容搜索和 [核心电子数据展示的限制](limits-for-content-search.md)。