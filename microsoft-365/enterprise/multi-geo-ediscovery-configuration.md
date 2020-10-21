---
title: 配置 Microsoft 365 多地理位置电子数据展示
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: 了解如何使用 Region 参数配置电子数据展示，以便在 Microsoft 365 多地理位置的附属位置使用。
ms.openlocfilehash: d1d66a9e7953b540e318c8364bdcb8d72654b482
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636801"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 多地理位置电子数据展示配置

[高级电子数据展示功能](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) 允许多地理电子数据展示管理员搜索所有信息，而无需使用 "区域" 安全筛选器。 将数据导出到多地理位置租户的中央位置的 Azure 实例。 

如果没有高级电子数据展示功能，则多地理位置租户的电子数据展示管理者或管理员将能够仅在该租户的中心位置执行电子数据展示。 若要支持对附属位置进行电子数据展示的能力，可通过 PowerShell 获取一个新的合规性安全筛选器参数，名为 "Region"。 此参数可由其中心位置在北美、欧洲或亚太地区的租户使用。 对于其中心位置不在北美、欧洲或亚太地区且需要跨卫星地理位置执行电子数据展示的租户，建议使用高级电子数据展示。 

Microsoft 365 全局管理员必须分配电子数据展示管理者权限，以允许其他人员执行电子数据展示，并在其适用的合规性安全筛选器中分配“Region”参数，以便将要进行电子数据展示的区域指定为附属位置，否则，不会对该附属位置执行任何电子数据展示。

当为特定附属位置设置电子数据展示管理者或管理员角色时，电子数据展示管理者或管理员将只能对位于该附属位置的 SharePoint 网站和 OneDrive 网站执行电子数据展示搜索操作。如果电子数据展示管理者或管理员尝试搜索指定附属位置以外的 SharePoint 或 OneDrive 网站，将不返回任何结果。此外，当某个附属位置的电子数据展示管理者或管理员触发导出时，数据将导出到该地区的 Azure 实例。通过禁止跨受控界限导出内容，将有助于组织保持合规性。

> [!NOTE]
> 如果需要电子数据展示管理者搜索多个 SharePoint 附属位置，将需要为电子数据展示管理者创建另一个用户帐户，以指定 OneDrive 或 SharePoint 网站所在的备用附属位置。

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

针对区域设置合规性安全筛选器：

1. [连接到 Microsoft 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. 使用以下语法：

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   例如：

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

请参阅 [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter) 一文了解其他参数和语法。
