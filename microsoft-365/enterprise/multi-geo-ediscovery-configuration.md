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
ms.localizationpriority: medium
ms.collection: Strat_SP_gtc
description: 了解如何使用 Region 参数配置电子数据展示，以在多地理位置的附属Microsoft 365使用。
ms.openlocfilehash: b0366470984abbdc0ed0b3e407ca8ef6b5a5743f
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2022
ms.locfileid: "63400932"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 多地理位置电子数据展示配置

[Advanced eDiscovery功能](../compliance/overview-ediscovery-20.md)允许多地理位置电子数据展示管理员搜索所有地理位置，而无需使用"区域"安全筛选器。 数据将导出到多地理位置租户的中心位置的 Azure 实例。 对保管人应用保留时也会出现此情况，但是，如果没有"区域"安全筛选器，不会显示保留内的保留统计信息。 显示 0 的保留统计信息并不意味着，只要保留状态显示"打开"状态， (成功) 。

如果没有高级电子数据展示功能，多地理位置租户的电子数据展示管理员或管理员将只能在该租户的中心位置执行电子数据展示。 为了支持对附属位置执行电子数据展示，可通过 PowerShell 获取名为"Region"的新合规性安全筛选器参数。 其中心位置位于北美、欧洲或亚太地区的租户可以使用此参数。 Advanced eDiscovery中心位置不在北美、欧洲或亚太地区，并且需要跨附属地理位置执行电子数据展示的租户，建议使用此配置。 

Microsoft 365 全局管理员必须分配电子数据展示管理员权限，以允许其他人执行电子数据展示，并为其适用的合规性安全筛选器分配"Region"参数，以将执行电子数据展示的区域指定为附属位置，否则，不会为附属位置执行任何电子数据展示。 每个用户仅支持一个"区域"安全筛选器，因此所有区域都需要在同一安全筛选器内。

当为特定附属位置设置电子数据展示管理者或管理员角色时，电子数据展示管理者或管理员将只能对位于该附属位置的 SharePoint 网站和 OneDrive 网站执行电子数据展示搜索操作。如果电子数据展示管理者或管理员尝试搜索指定附属位置以外的 SharePoint 或 OneDrive 网站，将不返回任何结果。此外，当某个附属位置的电子数据展示管理者或管理员触发导出时，数据将导出到该地区的 Azure 实例。通过禁止跨受控界限导出内容，将有助于组织保持合规性。

> [!NOTE]
> 如果需要电子数据展示管理者搜索多个 SharePoint 附属位置，将需要为电子数据展示管理者创建另一个用户帐户，以指定 OneDrive 或 SharePoint 网站所在的备用附属位置。

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

针对区域设置合规性安全筛选器：

1. [连接到 Microsoft 365 安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)

2. 使用以下语法：

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   例如：

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

请参阅 [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) 一文了解其他参数和语法。
