---
title: 使用 PowerShell 查看Microsoft 365许可证和服务
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
description: 介绍如何使用 PowerShell 查看有关Microsoft 365组织中可用的许可计划、服务和许可证的信息。
ms.openlocfilehash: 8b5ff01f15e4dea7a44b423609b6533cc5729a5f
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823885"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>使用 PowerShell 查看Microsoft 365许可证和服务

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

每个Microsoft 365订阅都包含以下元素：

- **许可计划** 这些也称为许可证计划或Microsoft 365计划。 许可计划定义可供用户使用的Microsoft 365服务。 Microsoft 365订阅可能包含多个许可计划。 将Microsoft 365 E3一个示例许可计划。
    
- **服务** 这些也称为服务计划。 服务是每个许可计划中提供的Microsoft 365产品、功能和功能，例如，Exchange Online和以前命名的Office 365 专业增强版) Microsoft 365 企业应用版 (。 可以从授予不同服务访问权限的不同许可计划向用户分配多个许可证。
    
- **许可证** 每个许可计划都包含你购买的许可证数。 将许可证分配给用户，以便用户可以使用许可计划定义的Microsoft 365服务。 每个用户帐户至少需要一个许可计划中的一个许可证，以便他们可以登录到Microsoft 365并使用这些服务。
    
可以使用 PowerShell Microsoft 365查看有关Microsoft 365组织中可用许可计划、许可证和服务的详细信息。 有关不同Office 365订阅中提供的产品、功能和服务的详细信息，请[参阅Office 365计划选项](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。


## <a name="use-the-microsoft-graph-powershell-sdk"></a>使用 Microsoft Graph PowerShell SDK

首先，[连接到Microsoft 365租户](/graph/powershell/get-started#authentication)。

阅读订阅许可证计划需要 Organization.Read.All 权限范围或[“List subscribedSkus”图形 API参考页](/graph/api/subscribedsku-list)中列出的其他权限之一。

```powershell
Connect-Graph -Scopes Organization.Read.All
```

若要查看有关当前许可计划和每个计划的可用许可证的摘要信息，请运行以下命令：
  
```powershell
Get-MgSubscribedSku | Select -Property Sku*, ConsumedUnits -ExpandProperty PrepaidUnits | Format-List
```

结果包含：
  
- **SkuPartNumber：** 显示组织的可用许可计划。 例如， `ENTERPRISEPACK` Office 365 企业版 E3 的许可证计划名称。
    
- **启用：** 为特定许可计划购买的许可证数。
    
- **ConsumedUnits：** 从特定许可计划分配给用户的许可证数。
    
若要查看所有许可证计划中提供的Microsoft 365服务的详细信息，请首先显示许可证计划的列表。

```powershell
Get-MgSubscribedSku
```

接下来，将许可证计划信息存储在变量中。

```powershell
$licenses = Get-MgSubscribedSku
```

接下来，在特定的许可证计划中显示服务。

```powershell
$licenses[<index>].ServicePlans
```

\<index> 是一个整数，指定命令显示 `Get-MgSubscribedSku | Select SkuPartNumber` 的许可证计划的行号减去 1。

例如，如果命令的 `Get-MgSubscribedSku | Select SkuPartNumber` 显示如下：

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

然后，用于显示 ENTERPRISEPREMIUM 许可证计划服务的命令如下：

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM 是第三行。 因此，索引值 (3 - 1) 或 2。

有关许可证计划的完整列表 (也称为产品名称) 、其包含的服务计划及其相应的友好名称，请参阅 [产品名称和服务计划标识符以获取许可](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先，[连接到Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
若要查看有关当前许可计划和每个计划的可用许可证的摘要信息，请运行以下命令：
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

结果包含：
  
- **SkuPartNumber：** 显示组织的可用许可计划。 例如， `ENTERPRISEPACK` Office 365 企业版 E3 的许可证计划名称。
    
- **启用：** 为特定许可计划购买的许可证数。
    
- **ConsumedUnits：** 从特定许可计划分配给用户的许可证数。
    
若要查看所有许可证计划中提供的Microsoft 365服务的详细信息，请首先显示许可证计划的列表。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

接下来，将许可证计划信息存储在变量中。

```powershell
$licenses = Get-AzureADSubscribedSku
```

接下来，在特定的许可证计划中显示服务。

```powershell
$licenses[<index>].ServicePlans
```

\<index> 是一个整数，指定命令显示 `Get-AzureADSubscribedSku | Select SkuPartNumber` 的许可证计划的行号减去 1。

例如，如果命令的 `Get-AzureADSubscribedSku | Select SkuPartNumber` 显示如下：

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

然后，用于显示 ENTERPRISEPREMIUM 许可证计划服务的命令如下：

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM 是第三行。 因此，索引值 (3 - 1) 或 2。

有关许可证计划的完整列表 (也称为产品名称) 、其包含的服务计划及其相应的友好名称，请参阅 [产品名称和服务计划标识符以获取许可](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先，[连接到Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

>[!Note]
>PowerShell 脚本可自动执行本主题中描述的过程。 具体而言，该脚本允许你查看和禁用Microsoft 365组织中的服务，包括Sway。 有关详细信息，请参阅[使用 PowerShell 禁用对Sway的访问](disable-access-to-sway-with-microsoft-365-powershell.md)。
>
    
若要查看有关当前许可计划和每个计划的可用许可证的摘要信息，请运行以下命令：
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。 若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。
>

结果包含以下信息：
  
- **AccountSkuId：** 使用语 `<CompanyName>:<LicensingPlan>`法显示组织的可用许可计划。  _\<CompanyName>_ 是注册Microsoft 365时提供的值，对于你的组织是唯一的。 每个 _\<LicensingPlan>_ 用户的值都是一样的。 例如，在值`litwareinc:ENTERPRISEPACK`中，公司名称和`litwareinc`许可计划名称`ENTERPRISEPACK`，即Office 365 企业版 E3 的系统名称。
    
- **ActiveUnits：** 为特定许可计划购买的许可证数。
    
- **WarningUnits：** 许可计划中尚未续订的许可证数，将在 30 天宽限期后过期。
    
- **ConsumedUnits：** 从特定许可计划分配给用户的许可证数。
    
若要查看所有许可证计划中提供的Microsoft 365服务的详细信息，请运行以下命令：
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

下表显示了Microsoft 365服务计划及其最常见服务的友好名称。 服务计划列表可能会有所不同。 
  
|**服务计划**|**说明**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure 权限管理 (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365 企业应用版 *以前命名的 (Office 365 专业增强版)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online 计划 2  <br/> |
   
有关许可证计划的完整列表 (也称为产品名称) 、其包含的服务计划及其相应的友好名称，请参阅 [产品名称和服务计划标识符以获取许可](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。

若要查看有关特定许可计划中提供的Microsoft 365服务的详细信息，请使用以下语法。
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

此示例演示 litwareinc：ENTERPRISEPACK (Office 365 企业版 E3) 许可计划中提供的服务。
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)