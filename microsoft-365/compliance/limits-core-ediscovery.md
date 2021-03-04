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
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文介绍 Microsoft 365 中核心电子数据展示案例的限制。
ms.openlocfilehash: 2699e9b2511c742bb295f69611a976f6a3955980
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423443"
---
# <a name="limits-in-core-ediscovery"></a>核心电子数据展示中的限制

下表列出了核心电子数据展示事例的限制，以及与核心电子数据展示事例相关联的保留项。 有关核心电子数据展示详细信息，请参阅 [核心电子数据展示概述](ediscovery-cases.md)。
    
  | 限制说明 | 限制 |
  |:-----|:-----|
  |组织的最大事例数。  <br/> |无限制  <br/> |
  |组织的最大案例保留数。  <br/> |10,000  <br/> |
  |单个案例保留中的最大邮箱数。 此限制包括用户邮箱总数以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的邮箱。  <br/> |1,000  <br/> |
  |单个案例保留中的最大网站数。 此限制包括 OneDrive for Business 网站、SharePoint 网站以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的网站的组合总数。  <br/> |100  <br/> |
  |核心电子数据展示主页上显示的最大事例数，以及事例中"保留、搜索"和"导出"选项卡上显示的最大项目数。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> 若要查看超过 1，000 个事例、保留、搜索或导出的列表，可以使用相应的 Office 365 安全与合规 PowerShell & Cmdlet：
   > 
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

有关与核心电子数据展示案例相关的内容搜索和导出限制详细信息，请参阅内容搜索和 [核心电子数据展示的限制](limits-for-content-search.md)。