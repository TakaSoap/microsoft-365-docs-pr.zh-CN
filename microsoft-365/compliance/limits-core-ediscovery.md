---
title: 核心电子数据展示案例中的限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文介绍Microsoft 365中核心电子数据展示案例的限制。
ms.openlocfilehash: 2d920fbe5973d07b7da656d6247038ab785bbe5c
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64822641"
---
# <a name="limits-in-core-ediscovery"></a>核心电子数据展示中的限制

下表列出了核心电子数据展示案例的限制，以及与核心电子数据展示案例相关联的保留。 有关核心电子数据展示的详细信息，请参阅 [核心电子数据展示概述](./get-started-core-ediscovery.md)。
    
  | 限制说明 | 限制 |
  |:-----|:-----|
  |组织的最大案例数。  <br/> |无限制  <br/> |
  |组织保留的最大案例数。  <br/> |10,000  <br/> |
  |单个事例保留中的最大邮箱数。 此限制包括用户邮箱总数，以及与Microsoft 365 组、Microsoft Teams和Yammer组关联的邮箱。  <br/> |1,000  <br/> |
  |单个事例保留中的最大站点数。 此限制包括OneDrive for Business网站、SharePoint站点以及与Microsoft 365 组、Microsoft Teams 和Yammer组关联的站点总数。  <br/> |100  <br/> |
  |核心电子数据展示主页上显示的最大事例数，以及事例中“保留”、“搜索”和“导出”选项卡上显示的最大项数。 <sup>1</sup> |1,000|

   > [!NOTE]
   > <sup>1</sup> 若要查看超过 1，000 个案例、保留、搜索或导出的列表，可以使用相应的Office 365安全&符合性 PowerShell cmdlet：
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

有关与与核心电子数据展示案例关联的搜索和导出的限制的详细信息，请参阅 [“内容搜索限制”和“核心电子数据展示](limits-for-content-search.md)”。