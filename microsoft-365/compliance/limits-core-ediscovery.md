---
title: 核心电子数据展示案例的限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文介绍 Microsoft 365 中的核心电子数据展示Microsoft 365。
ms.openlocfilehash: 82caa5214f777effb912ab1a2a3054b1e4432ae6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190697"
---
# <a name="limits-in-core-ediscovery"></a>核心电子数据展示中的限制

下表列出了与核心电子数据展示事例关联的核心电子数据展示事例和保留项的限制。 有关核心电子数据展示详细信息，请参阅 [核心电子数据展示概述](./get-started-core-ediscovery.md)。
    
  | 限制说明 | 限制 |
  |:-----|:-----|
  |组织的最大事例数。  <br/> |无限制  <br/> |
  |组织的最大案例保留数。  <br/> |10,000  <br/> |
  |单个案例保留中的最大邮箱数。 此限制包括用户邮箱总数，以及与组组、Microsoft Teams组Microsoft 365关联的Yammer邮箱。  <br/> |1,000  <br/> |
  |单个案例保留中的最大网站数。 此限制包括与 OneDrive for Business 组、SharePoint 组、Microsoft Teams 和 Yammer 组关联的网站Microsoft 365总数。  <br/> |100  <br/> |
  |核心电子数据展示主页上显示的最大事例数，以及事例中"保留项、搜索"和"导出"选项卡上显示的最大项目数。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup>若要查看超过 1，000 个事例、保留、搜索或导出的列表，可以使用相应的 Office 365 Security & Compliance PowerShell cmdlet：
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

有关与与核心电子数据展示案例关联的搜索和导出相关的限制详细信息，请参阅 [内容搜索和核心电子数据展示的限制](limits-for-content-search.md)。