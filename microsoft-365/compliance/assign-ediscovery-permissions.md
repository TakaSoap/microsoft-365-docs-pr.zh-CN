---
title: 在安全与合规中心&电子数据展示权限
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
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: 使用安全与合规中心分配执行与电子数据展示&所需的权限。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f4271d7cc7a9c9239aadb8ca2357e000f4f45e80
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682603"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>在安全与合规中心&电子数据展示权限

如果希望用户使用 Office 365 安全与合规中心或 Microsoft 365 合规中心内任何与电子数据展示相关的工具，必须为其分配适当的权限。 & [](ediscovery.md) 执行此操作的最简单方法是在安全与合规中心的"权限"页上&相应的角色组。  本主题介绍使用安全与合规中心执行与电子数据展示和内容搜索&所需的权限。
  
安全与合规中心中与电子数据展示&相关的主要角色组称为 **电子数据展示管理器**。 此角色组内有两个子组。
  
- **电子** 数据展示管理员 - 电子数据展示管理员可使用安全 & 合规中心中的内容搜索工具搜索组织的内容位置，并执行各种与搜索相关的操作，如预览和导出搜索结果。 成员还可以在核心电子数据展示和高级电子数据展示中创建和管理事例、向事例添加和删除成员、创建事例保留、运行与事例关联的搜索以及访问事例数据。 电子数据展示管理员只能访问和管理他们创建的情况。 他们无法访问或管理由其他电子数据展示管理员创建事例。
  
- **电子** 数据展示管理员 - 电子数据展示管理员是电子数据展示管理员角色组的成员，可以执行与电子数据展示管理员可以执行相同的内容搜索和案例管理相关任务。 此外，电子数据展示管理员可以：
  
  - 访问安全与合规中心电子数据展示和高级 **电子** 数据展示页面上&的所有事例。

  - 访问组织中任何案例的高级电子数据展示中的案例数据。
  
  - 在将自己添加为该案例的成员后，管理任何电子数据展示案例。
  
  请参阅 ["详细信息"](#more-information) 部分，了解您可能希望在组织中使用电子数据展示管理员的原因。

> [!NOTE]
> 若要使用高级电子数据展示分析用户数据， (必须分配有) Office 365 E5 或 Microsoft 365 E5 许可证。 或者，拥有 Office 365 E1 或 Office 365 或 Microsoft 365 E3 许可证的用户也可以分配有 Microsoft 365 E5 合规性或 Microsoft 365 电子数据展示和审核加载项许可证。 分配为事例的成员并使用高级电子数据展示收集、查看和分析数据的管理员、合规部官员或法律人员不需要 E5 许可证。 有关高级电子数据展示许可详细信息，请参阅 [高级电子数据展示入门](get-started-with-advanced-ediscovery.md)。
  
## <a name="confirm-your-roles"></a>确认角色

- 您必须是组织管理角色组的成员或分配有"角色管理"角色，才能在安全与合规中心&电子数据展示权限。

- 您可以使用 &安全与合规中心 PowerShell 中的 [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember) cmdlet 将启用邮件的安全组添加为电子数据展示管理员角色组中的电子数据展示管理员子组的成员。 但是，无法将已启用邮件的安全组添加到电子数据展示管理员子组。 有关详细信息，请参阅 ["详细信息"](#more-information) 部分。 
  
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>在安全与合规中心&电子数据展示权限

1. 转到 [https://protection.office.com](https://protection.office.com)。
  
2. 使用工作或学校帐户进行登录。
  
3. 在安全与合规中心的左窗格中，选择"权限"，然后选择电子数据展示管理器 **旁边的复选框**。 
  
4. 在 **电子数据展示管理器** 飞出页上，根据要分配电子数据展示权限执行下列操作之一。
  
    **若要使用户成为电子数据展示管理员：** 在 **电子数据展示管理器旁边，** 选择"编辑 **"。** 在 **"选择电子数据展示管理器**"部分，选择"选择 **电子数据展示** 管理器"超链接，然后选择" ![ 添加图标 ](../media/ITPro-EAC-AddIcon.gif) **"。** 选择要添加 (或) 电子数据展示管理员的用户，然后选择"添加 **"。** 添加完用户后，选择"完成 **"。** 然后，在 **"编辑选择电子数据** 展示管理器"飞出页上，选择"保存"以将更改保存到电子数据展示管理员成员身份。
  
    **若要使用户成为电子数据展示管理员，** 在 **电子数据展示管理器旁边，** 选择"编辑 **"。** 在"**选择电子数据展示** 管理员"部分中的"**电子数据** 展示管理员"下，选择"选择 **电子数据** 展示管理员"，选择"编辑"，然后选择"添加 ![ 图标 ](../media/ITPro-EAC-AddIcon.gif) **"。** 选择要添加 (或) 电子数据展示管理员的用户，然后 **添加**。  添加完用户后，选择"完成 **"。** 然后，在 **"编辑选择电子数据** 展示管理员"飞出页上，选择"保存"以将更改保存到电子数据展示管理员成员身份。
  
> [!NOTE]
> 您还可以使用 **Add-eDiscoveryCaseAdmin** cmdlet 使用户成为电子数据展示管理员。 但是，必须先为用户分配"案例管理"角色，然后才能使用此 cmdlet 将其作为电子数据展示管理员。 有关详细信息，请参阅 [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217)。 
  
在安全与合规中心&"权限"页上，您还可以通过将用户电子数据展示相关权限添加到合规性管理员、组织管理和审阅者角色组来分配这些权限。 有关分配给其中每个角色组的与电子数据展示相关的 RBAC 角色的说明，请参阅与电子数据展示相关的 [RBAC](#rbac-roles-related-to-ediscovery) 角色部分。

## <a name="rbac-roles-related-to-ediscovery"></a>与电子数据展示相关的 RBAC 角色

下表列出了安全与合规中心内与电子数据展示相关的 RBAC 角色&并指示默认情况下每个角色分配到的内置角色组。
  
|**角色**|**合规性管理员**|**电子数据展示管理员&管理员**|**组织管理**|**Reviewer**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|案例管理 <br/> |![复选标记](../media/checkmark.png) <br/> |![复选标记](../media/checkmark.png) <br/> |![复选标记](../media/checkmark.png) <br/> | <br/> |
|通信 <br/> | <br/> |![复选标记](../media/checkmark.png) <br/> | <br/> | <br/> |
|合规性搜索 <br/> |![复选标记](../media/checkmark.png) <br/> |![复选标记](../media/checkmark.png) <br/> |![复选标记](../media/checkmark.png) <br/> | <br/> |
|Custodian <br/> | <br/> |![复选标记](../media/checkmark.png) <br/> | <br/> | <br/> |
|导出 <br/> | <br/> |![复选标记](../media/checkmark.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![复选标记](../media/checkmark.png) <br/> |![复选标记](../media/checkmark.png) <br/> |![复选标记](../media/checkmark.png) <br/> | <br/> |
|预览 <br/>  | <br/> |![复选标记](../media/checkmark.png) <br/> | <br/> | <br/> |
|审阅 <br/>  | <br/> |![复选标记](../media/checkmark.png) <br/> | <br/> |![复选标记](../media/checkmark.png) <br/> |
|RMS 解密 <br/>  ||![复选标记](../media/checkmark.png) <br/> |||
|搜索和清除 <br/> | <br/> | <br/> |![复选标记](../media/checkmark.png)           <br/> | <br/> |
||||
  
以下各节介绍上表中列出的每个与电子数据展示相关的 RBAC 角色。

### <a name="case-management"></a>案例管理

此角色允许用户在安全与合规中心创建、编辑、删除和控制对核心电子数据展示和高级电子数据展示&访问。 如前所述，必须先为用户分配"案例管理"角色，然后才能使用 **Add-eDiscoveryCaseAdmin** cmdlet 将其用作电子数据展示管理员。

有关详细信息，请参阅：

- [核心电子数据展示入门](get-started-core-ediscovery.md)

- [高级电子数据展示入门](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>通信

此角色允许用户管理与高级电子数据展示案例中标识的保管人的所有通信。 这包括创建保留通知、保留提醒以及向管理上报。 用户还可以跟踪保管人确认保留通知，并管理对保管人门户的访问，每个保管人使用该门户跟踪被识别为保管人的情况的通信。

有关详细信息，请参阅["使用高级电子数据展示中的通信"。](managing-custodian-communications.md)

### <a name="compliance-search"></a>合规性搜索

此角色允许用户在安全 & 合规中心中运行内容搜索工具，以搜索邮箱和公用文件夹、SharePoint Online 网站、OneDrive for Business 网站、Skype for Business 对话、Microsoft 365 组、Microsoft Teams 和 Yammer 组。 此角色允许用户估计搜索结果并创建导出报告，但需要其他角色才能启动内容搜索操作，如预览、导出或删除搜索结果。

分配了"合规性搜索"角色但没有"预览"角色的用户可以预览已由分配有预览角色的用户启动预览操作搜索的结果。 创建初始预览操作后，没有"预览"角色的用户可在最多两周内预览结果。

同样，分配有"合规性搜索"角色但没有"导出"角色的用户可以下载由分配有导出角色的用户启动导出操作搜索的结果。 没有导出角色的用户可在创建初始导出操作后最多两周内下载搜索结果。 此后，他们无法下载结果，除非具有导出角色的人重新启动导出。

有关详细信息，请参阅 [Office 365](content-search.md)中的内容搜索。

### <a name="custodian"></a>Custodian

此角色允许用户标识和管理高级电子数据展示事例的保管人，并使用 Azure Active Directory 和其他来源的信息查找与保管人关联的数据源。 用户可以将邮箱、SharePoint 网站和 Teams 等其他数据源与案例的保管人关联。 用户还可以对与保管人关联的数据源进行法定保留，以在案例上下文中保留内容。

有关详细信息，请参阅["使用高级电子数据展示中的保管人"。](managing-custodians.md)

### <a name="export"></a>导出

该角色允许用户将内容搜索的结果导出到本地计算机。 它还允许他们准备搜索结果以在高级电子数据展示中进行分析。

有关导出搜索结果详细信息，请参阅从安全与合规中心& [搜索结果](export-search-results.md)。

### <a name="hold"></a>Hold

此角色允许用户在邮箱、公用文件夹、站点、Skype for Business 对话和 Microsoft 365 组中保留内容。 当内容处于保留状态时，内容所有者仍可修改或删除原始内容，但内容将一直保留，直到保留被删除或保留期到期。

有关保留信息，请参阅：

- [在核心电子数据展示中创建保留](create-ediscovery-holds.md) 

- [在高级电子数据展示中创建保留](add-custodians-to-case.md#step-4-place-custodians-on-hold)

### <a name="preview"></a>预览

此角色允许用户查看从内容搜索返回的项目列表。 他们还可以打开和查看列表中的每个项目以查看其内容。

### <a name="review"></a>审阅

此角色允许用户访问高级电子数据展示 ([经典](office-365-advanced-ediscovery.md))  (也了解为高级电子数据展示 *v1*) 。 此角色的主要用途是为用户提供访问高级电子数据展示 (经典) 。 分配了此角色的用户可以在安全与合规中心内电子数据展示&并打开事例列表。 在安全与合规中心内访问案例后，他们可以选择"切换到高级电子数据展示"，以访问和分析高级电子数据展示或经典 (中) 。 &  此角色不允许用户预览与案例关联的内容搜索结果，或执行其他内容搜索或案例管理任务。

> [!NOTE]
> 目前，分配有审阅角色 (或审阅者角色组) 的成员的用户无法访问 [Microsoft 365](overview-ediscovery-20.md) (高级电子数据展示 *v2.0*) 中的数据。 若要将成员添加到高级电子数据展示 v2.0 中的案例，以便他们可以查看案例数据，用户必须是电子数据展示管理员角色组的成员。

### <a name="rms-decrypt"></a>RMS 解密

此角色允许用户在预览搜索结果和导出受权限保护的解密电子邮件时查看受权限保护的电子邮件。 当用户将加密文件附加到电子数据展示搜索结果中包含的电子邮件时，此角色还允许用户查看 (并导出) 使用 [Microsoft](encryption.md) 加密技术加密的文件。 此外，此角色允许用户查看和查询已添加到高级电子数据展示审阅集的加密电子邮件附件。 有关电子数据展示中的解密功能详细信息，请参阅 Microsoft [365 电子数据展示工具中的解密](ediscovery-decryption.md)。

### <a name="search-and-purge"></a>搜索和清除

此角色允许用户执行与内容搜索条件相匹配的数据批量删除。 有关详细信息，请参阅["在组织中搜索和删除电子邮件"。](search-for-and-delete-messages-in-your-organization.md)

## <a name="more-information"></a>详细信息

- **为什么要创建电子数据展示管理员？** 如前所述，电子数据展示管理员是电子数据展示管理员角色组的成员，可以查看和访问您组织中的所有电子数据展示事例。 访问所有电子数据展示事例这一功能有两个重要用途：

  - 如果作为电子数据展示事例唯一成员的人离开了公司，就没有人（包括组织管理角色组的成员或电子数据展示管理员角色组的另一个成员）能够访问该电子数据展示事例，因为他们不是事例的成员。 在这种情况下，将无法访问事例中的数据。 但是，由于电子数据展示管理员可以访问组织的所有电子数据展示事例，他们可以查看事例，并添加自己或其他电子数据展示管理员作为事例的成员。

  - 由于电子数据展示管理员可以查看和访问所有核心电子数据展示和高级电子数据展示事例，因此他们可以审核并监督所有事例和相关合规性搜索。 这有助于防止任何滥用合规性搜索或电子数据展示事例。 此外，由于电子数据展示管理员可以访问合规性搜索结果中的潜在敏感信息，因此您应该限制电子数据展示管理员的数量。

- **能否将组添加为电子数据展示管理员角色组的成员？** 如前所述，您可以使用安全与合规中心 PowerShell 中的 **Add-RoleGroupMember** cmd & let 将启用邮件的安全组添加为电子数据展示管理员角色组中的电子数据展示管理员子组的成员。 例如，可以运行以下命令将启用邮件的安全组添加到电子数据展示管理器角色组。 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    不支持 Exchange 通讯组和 Microsoft 365 组。 必须使用启用邮件的安全组，可以使用此命令在 Exchange Online PowerShell 中 `New-DistributionGroup -Type Security` 创建该组。 您还可以创建启用邮件的安全组 (，) Exchange 管理中心或 Microsoft 365 管理中心添加成员。 创建后最多可能需要 60 分钟，才能向电子数据展示管理员角色组添加新的启用邮件的安全性。 

    如前所述，无法通过使用安全与合规中心 PowerShell 中的 **Add-eDiscoveryCaseAdmin** cmd & let 使启用邮件的安全组成为电子数据展示管理员。 只能将单个用户添加为电子数据展示管理员。

    此外，无法将启用邮件的安全组添加为案例的成员。
