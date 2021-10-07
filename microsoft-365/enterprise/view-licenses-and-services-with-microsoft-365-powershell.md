---
title: 使用 PowerShell Microsoft 365许可证和服务
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: 介绍如何使用 PowerShell 查看有关组织中可用的许可计划、服务和许可证Microsoft 365的信息。
ms.openlocfilehash: 3b90596c68e3beadcc2b33ef59ff9c3503b84f8a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195265"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>使用 PowerShell Microsoft 365许可证和服务

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

每个Microsoft 365订阅都由以下元素组成：

- **许可计划** 这些也称为许可证计划或Microsoft 365计划。 许可计划定义Microsoft 365可用的服务。 你的Microsoft 365订阅可能包含多个许可计划。 例如，许可计划Microsoft 365 E3。
    
- **服务** 这些也称为服务计划。 服务是Microsoft 365许可计划中提供的主要产品、特性和功能，例如Exchange Online和Microsoft 365 企业应用版 (名称Office 365 专业增强版) 。 可以从授予不同服务访问权限的不同许可计划向用户分配多个许可证。
    
- **许可证** 每个许可计划都包含你购买的许可证数量。 你向用户分配许可证，以便Microsoft 365许可计划定义的服务。 每个用户帐户至少需要一个许可计划中的一个许可证，以便他们可以登录到Microsoft 365并使用服务。
    
可以使用 PowerShell for Microsoft 365查看有关组织中可用许可计划、许可证和服务Microsoft 365的详细信息。 有关不同订阅中提供的产品、功能和服务Office 365，请参阅Office 365[选项"。](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
若要查看有关当前许可计划以及每个计划的可用许可证的摘要信息，请运行以下命令：
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

结果包含：
  
- **SkuPartNumber：** 显示组织的可用许可计划。 例如， `ENTERPRISEPACK` 是 E3 的许可证Office 365 企业版名称。
    
- **已启用：** 你为特定许可计划购买的许可证数量。
    
- **ConsumedUnits：** 从特定许可计划向用户分配的许可证数。
    
若要查看有关所有许可证Microsoft 365中可用的服务的详细信息，请首先显示许可证计划的列表。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

接下来，将许可证计划信息存储在变量中。

```powershell
$licenses = Get-AzureADSubscribedSku
```

接下来，显示特定许可证计划中的服务。

```powershell
$licenses[<index>].ServicePlans
```

\<index> 是一个整数，用于指定显示命令后许可证计划的行号，减 `Get-AzureADSubscribedSku | Select SkuPartNumber` 1。

例如，如果命令的显示 `Get-AzureADSubscribedSku | Select SkuPartNumber` 方式为：

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

然后，显示 ENTERPRISEPREMIUM 许可证计划的服务的命令为：

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM 是第三行。 因此，索引值是 (3 - 1) 2。

有关许可证计划的完整列表 (产品名称) 包括的服务计划及其对应的友好名称，请参阅许可的产品名称和服务计划 [标识符](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

>[!Note]
>PowerShell 脚本可自动执行本主题中描述的过程。 具体而言，该脚本允许你查看和禁用 Microsoft 365 中的服务，包括 Sway。 有关详细信息，请参阅使用 [PowerShell 禁用对 Sway 的访问](disable-access-to-sway-with-microsoft-365-powershell.md)。
>
    
若要查看有关当前许可计划以及每个计划的可用许可证的摘要信息，请运行以下命令：
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。 若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。
>

结果包含以下信息：
  
- **AccountSkuId：** 使用 语法 显示组织的可用许可计划 `<CompanyName>:<LicensingPlan>` 。  _\<CompanyName>_ 是当你在组织中注册时Microsoft 365的值，并且对于你的组织是唯一的。 _\<LicensingPlan>_ 该值对于每个人都是相同的。 例如，在值 中，公司名称为 ，许可计划名称 为 ，这是 `litwareinc:ENTERPRISEPACK` `litwareinc` E3 Office 365 企业版 `ENTERPRISEPACK` 名称。
    
- **ActiveUnits：** 你为特定许可计划购买的许可证数量。
    
- **WarningUnits：** 未续订且将在 30 天宽限期后过期的许可计划中许可证数量。
    
- **ConsumedUnits：** 从特定许可计划向用户分配的许可证数。
    
若要查看有关所有许可证Microsoft 365中可用的服务的详细信息，请运行以下命令：
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

下表显示了最常见的Microsoft 365服务计划及其友好名称。 服务计划列表可能会有所不同。 
  
|**服务计划**|**说明**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure 权限管理 (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |*Microsoft 365 企业应用版 (之前名为 Office 365 专业增强版)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online 计划 2  <br/> |
   
有关许可证计划的完整列表 (产品名称) 包括的服务计划及其对应的友好名称，请参阅许可的产品名称和服务计划 [标识符](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。

若要查看有关特定Microsoft 365计划中可用的服务的详细信息，请使用以下语法。
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

此示例显示了 litwareinc：ENTERPRISEPACK (Office 365 企业版 E3) 计划中可用的服务。
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)