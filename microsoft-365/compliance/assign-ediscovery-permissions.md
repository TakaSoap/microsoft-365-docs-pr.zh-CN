---
title: 在服务中分配电子数据展示Microsoft 365 合规中心
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
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: 分配使用电子数据展示管理程序执行与电子数据展示Microsoft 365 合规中心。
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
ms.openlocfilehash: d6515dc213fe6b89a9a638c9df8dcad63785967c
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2021
ms.locfileid: "60364551"
---
# <a name="assign-ediscovery-permissions-in-the-microsoft-365-compliance-center"></a>在服务中分配电子数据展示Microsoft 365 合规中心

如果您希望用户使用 Microsoft 365 合规中心 中任何与[](ediscovery.md)电子数据展示相关的工具，您必须为其分配适当的权限。 执行此操作的最简单方法是在合规中心的"权限"页上添加相应的角色组。  本主题介绍执行电子数据展示任务所需的权限。
  
Microsoft 365 合规中心中与电子数据展示相关的主要角色组称为 **"电子数据展示管理器"。** 此角色组中有两个子组。
  
- **电子数据展示** 管理器 - 电子数据展示管理员可使用电子数据展示搜索工具搜索组织中的内容位置，并执行各种与搜索相关的操作，如预览和导出搜索结果。 成员还可以在核心电子数据展示和 Advanced eDiscovery 创建和管理事例、向事例添加和删除成员、创建事例保留、运行与事例关联的搜索以及访问事例数据。 电子数据展示管理器只能访问和管理其创建的案例。 它们无法访问或管理由其他电子数据展示管理器创建的案例。
  
- **电子数据展示** 管理员 - 电子数据展示管理员是电子数据展示管理员角色组的成员，可以执行电子数据展示管理员可执行的与内容搜索和案例管理相关的任务。 此外，电子数据展示管理员可以：
  
  - 访问核心电子数据展示中列出的所有事例，Advanced eDiscovery **页面中** Microsoft 365 合规中心。

  - 在高级电子数据展示中访问组织中任何事例的事例数据。
  
  - 将其自己添加为任何电子数据展示事例的成员后管理这些事例。
  
  - 从电子数据展示案例中删除成员。 只有电子数据展示管理员可以从案例中删除成员。 作为电子数据展示管理器子组的成员的用户无法从案例中删除成员，即使用户创建了案例。
  
  出于可能想要在组织中使用电子数据展示管理员的原因，请参阅 [详细信息](#more-information)。

> [!NOTE]
> 若要使用 Advanced eDiscovery 分析用户的数据， (数据) 必须分配有Office 365 E5或Microsoft 365 E5许可证。 或者，也可以为具有 Office 365 E1 或 Office 365 或 Microsoft 365 E3 许可证的用户分配 Microsoft 365 E5 合规 或 Microsoft 365 电子数据展示和审核加载项许可证。 分配为事例的成员并使用 Advanced eDiscovery 收集、查看和分析数据的管理员、合规部官员或法律人员不需要 E5 许可证。 有关许可Advanced eDiscovery，请参阅订阅[和](overview-ediscovery-20.md#subscriptions-and-licensing)Advanced eDiscovery。
  
## <a name="before-you-assign-permissions"></a>分配权限之前

- 您必须是组织管理角色组的成员，或分配有 Role Management 角色，才能在 Microsoft 365 合规中心 中分配电子数据展示权限。

- 您可以使用安全 & 合规中心 PowerShell 中的 [Add-RoleGroupMember](/powershell/module/exchange/Add-RoleGroupMember) cmdlet 将启用邮件的安全组添加为电子数据展示管理员角色组中的电子数据展示管理员子组的成员。 但是，不能将启用邮件的安全组添加到电子数据展示管理员子组。 有关详细信息，请参阅 [详细信息](#more-information)。
  
## <a name="assign-ediscovery-permissions"></a>分配电子数据展示权限

1. 转到 <https://compliance.microsoft.com> ，然后使用可分配权限的帐户登录。
  
2. 在左窗格中，选择"**权限"。**

3. 在"权限&**角色"** 页上的"合规性 **中心"下**，单击"角色 **"。**

4. 在"**合规性中心角色"** 页上，选择 **"电子数据展示管理器"。**
  
5. 在 **"电子数据展示管理器** "飞出页面上，根据要分配电子数据展示权限执行下列操作之一。
  
    **若要使用户成为电子数据展示管理员：** 在"**电子数据展示管理器"旁边，选择**"编辑 **"。** 在" **选择电子数据展示管理器** "向导页上，单击" ![ 添加图标"。](../media/ITPro-EAC-AddIcon.gif) **添加** 。 选择要添加 (或) 电子数据展示管理员的用户，然后选择"添加 **"。** 添加完用户后，选择"完成 **"。** 然后，在"**编辑选择电子数据** 展示管理器"向导页上，选择"保存"以保存对电子数据展示管理员成员身份的更改。
  
    **若要使用户成为电子数据展示管理员：** 在"**电子数据展示管理员"旁边，选择**"编辑 **"。** 在" **选择电子数据展示管理员"** 页上，单击" ![ 添加图标"。](../media/ITPro-EAC-AddIcon.gif) **添加** 。 选择要添加 (或) 电子数据展示管理员的用户，然后选择"添加 **"。**  添加完用户后，选择"完成 **"。** 然后，在"**编辑选择电子数据** 展示管理员"向导页上，选择"保存"以保存对电子数据展示管理员成员身份的更改。
  
> [!NOTE]
> 您还可以使用 **Add-eDiscoveryCaseAdmin** cmdlet 使用户成为电子数据展示管理员。 但是，必须先为用户分配案例管理角色，然后才能使用此 cmdlet 将其作为电子数据展示管理员。 有关详细信息，请参阅 [Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin)。 
  
在"**权限**"页上Microsoft 365 合规中心，您还可以通过将用户添加到合规性管理员、组织管理和审阅者角色组来分配与电子数据展示相关的权限。 有关分配给其中每个角色组与电子数据展示相关的 RBAC 角色的说明，请参阅 [与电子数据展示相关的 RBAC 角色](#rbac-roles-related-to-ediscovery)。

## <a name="rbac-roles-related-to-ediscovery"></a>与电子数据展示相关的 RBAC 角色

下表列出了 Microsoft 365 合规中心 中与电子数据展示相关的 RBAC 角色，并指示默认情况下每个角色分配到的内置角色组。
  
| Role | 合规管理员 | 电子数据展示管理员&管理员 | 组织管理 | Reviewer |
|:-----|:-----:|:-----:|:-----:|:-----:|
|案例管理 <br/> |![复选标记。](../media/checkmark.png) <br/> |![复选标记。](../media/checkmark.png) <br/> |![复选标记。](../media/checkmark.png) <br/> | <br/> |
|通信 <br/> | <br/> |![复选标记。](../media/checkmark.png) <br/> | <br/> | <br/> |
|合规性搜索 <br/> |![复选标记。](../media/checkmark.png) <br/> |![复选标记。](../media/checkmark.png) <br/> |![复选标记。](../media/checkmark.png) <br/> | <br/> |
|Custodian <br/> | <br/> |![复选标记。](../media/checkmark.png) <br/> | <br/> | <br/> |
|导出 <br/> | <br/> |![复选标记。](../media/checkmark.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![复选标记。](../media/checkmark.png) <br/> |![复选标记。](../media/checkmark.png) <br/> |![复选标记。](../media/checkmark.png) <br/> | <br/> |
|预览 <br/>  | <br/> |![复选标记。](../media/checkmark.png) <br/> | <br/> | <br/> |
|审阅 <br/>  | <br/> |![复选标记。](../media/checkmark.png) <br/> | <br/> |![复选标记](../media/checkmark.png) <br/> |
|RMS 解密 <br/>  ||![复选标记](../media/checkmark.png) <br/> |||
|搜索和清除 <br/> | <br/> | <br/> |![复选标记](../media/checkmark.png)           <br/> | <br/> |
||||
  
以下各节介绍上表中列出的每个与电子数据展示相关的 RBAC 角色。

### <a name="case-management"></a>案例管理

此角色允许用户创建、编辑、删除和控制对核心电子数据展示和Advanced eDiscovery事例Microsoft 365 合规中心。 如前所述，必须先为用户分配案例管理角色，然后才能使用 **Add-eDiscoveryCaseAdmin** cmdlet 将其用作电子数据展示管理员。

有关更多信息，请参阅：

- [核心电子数据展示入门](get-started-core-ediscovery.md)

- [高级电子数据展示入门](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>通信

此角色允许用户管理与案例内标识的保管人Advanced eDiscovery通信。 这包括创建保留通知、保留提醒和上报管理。 用户还可以跟踪保管人对保留通知的确认，并管理对保管人门户的访问，每个保管人使用该门户跟踪被识别为保管人的情况的通信。

有关详细信息，请参阅使用 Advanced eDiscovery[中的通信](managing-custodian-communications.md)。

### <a name="compliance-search"></a>合规性搜索

此角色允许用户在 Microsoft 365 合规中心 中运行内容搜索工具，以搜索邮箱和公用文件夹、SharePoint Online 网站、OneDrive for Business 网站、Skype for Business对话Microsoft 365组，和 Microsoft Teams，Yammer组。 此角色允许用户估计搜索结果并创建导出报告，但需要其他角色才能启动内容搜索操作，如预览、导出或删除搜索结果。

在内容搜索和核心电子数据展示中，分配有合规性搜索角色但没有预览角色的用户可以预览已由分配有 Preview 角色的用户启动预览操作搜索的结果。 创建初始预览操作后，没有 Preview 角色的用户可在最多两周内预览结果。

同样，内容搜索和核心电子数据展示中分配有合规性搜索角色但没有导出角色的用户可以下载搜索的结果，其中导出操作是由分配有导出角色的用户启动的。 没有 Export 角色的用户可在创建初始导出操作后最多两周内下载搜索结果。 此后，他们无法下载结果，除非具有导出角色的人重新启动导出。

预览和导出搜索结果的两周宽限期 (没有相应的搜索和导出角色) 不适用于Advanced eDiscovery。 必须为用户分配"预览"和"导出"角色，以预览和导出Advanced eDiscovery。

### <a name="custodian"></a>Custodian

此角色允许用户识别和管理Advanced eDiscovery保管人，并使用来自Azure Active Directory源的信息查找与保管人关联的数据源。 用户可以将其他数据源（如邮箱、SharePoint网站）Teams保管人关联。 用户还可以对与保管人关联的数据源设置法定保留，以在案例上下文中保留内容。

有关详细信息，请参阅使用 Advanced eDiscovery 中的[保管人](managing-custodians.md)。

### <a name="export"></a>导出

该角色允许用户将内容搜索的结果导出到本地计算机。 它还允许他们准备搜索结果以在 Advanced eDiscovery 中进行分析。

有关导出搜索结果的信息，请参阅 Export [search results from Microsoft 365 合规中心](export-search-results.md)。

### <a name="hold"></a>Hold

此角色允许用户将内容置于邮箱、公用文件夹、网站、Skype for Business对话Microsoft 365组中。 当内容处于保留状态时，内容所有者仍然可以修改或删除原始内容，但内容将被保留，直到保留被删除或保留到期。

有关保留详细信息，请参阅：

- [在核心电子数据展示中创建保留](create-ediscovery-holds.md) 

- [在"管理"中Advanced eDiscovery](add-custodians-to-case.md)

### <a name="preview"></a>预览

此角色允许用户查看从内容搜索返回的项目列表。 他们还可以打开并查看列表中的每个项目以查看其内容。

### <a name="review"></a>审阅

此角色允许用户访问 Advanced eDiscovery[中的审阅Advanced eDiscovery。](overview-ediscovery-20.md) 分配了此角色的用户可以在他们作为成员>电子数据展示Microsoft 365 合规中心 **高级**"页面上查看和打开事例列表。 用户访问案例后Advanced eDiscovery，可以选择"审阅集"来访问案例数据。  此角色不允许用户预览与案例关联的集合搜索的结果，或执行其他搜索或案例管理任务。 具有此角色的用户只能访问审阅集内的数据。

### <a name="rms-decrypt"></a>RMS 解密

此角色允许用户在预览搜索结果和导出受权限保护的解密电子邮件时查看受权限保护的电子邮件。 当用户将加密文件附加到电子数据展示搜索结果中包含的电子邮件时，此角色还允许用户查看 (并导出) 使用 [Microsoft](encryption.md) 加密技术加密的文件。 此外，此角色还允许用户查看和查询添加到邮件审阅集的加密Advanced eDiscovery。 有关电子数据展示中的解密功能详细信息，请参阅解密[Microsoft 365电子数据展示工具。](ediscovery-decryption.md)

### <a name="search-and-purge"></a>搜索和清除

此角色允许用户执行与内容搜索条件匹配的批量删除数据。 有关详细信息，请参阅在 [组织中搜索和删除电子邮件](search-for-and-delete-messages-in-your-organization.md)。

## <a name="adding-role-groups-as-members-of-ediscovery-cases"></a>将角色组添加为电子数据展示事例的成员

可以将角色组添加为核心电子数据展示和Advanced eDiscovery事例的成员，以便角色组的成员可以在分配的情况下访问和执行任务。 分配给角色组的角色定义角色组的成员可以执行哪些任务。 然后将角色组添加为案例的成员后，成员可以访问和执行特定情况下的任务。 有关将角色组添加为事例成员的信息，请参阅：

- [核心电子数据展示入门](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

- [在事件案例中添加Advanced eDiscovery成员](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

记住这一点后，必须知道，如果角色组中添加或删除了角色，该角色组将会自动删除为角色组的成员，以防该角色组是其中的成员。 这样做的原因是保护组织避免无意中向案件的成员提供其他权限。 同样，如果删除了某个角色组，则它将从它作为成员的所有事例中删除。

在向可能是电子数据展示事例成员的角色组添加或删除角色之前，可以在安全 & 合规性 [PowerShell](/powershell/exchange/connect-to-scc-powershell) 中运行以下命令，获取角色组是其中成员的情况列表。 更新角色组后，将角色组添加回这些事例的成员。

### <a name="get-a-list-of-core-ediscovery-cases-a-role-group-is-assigned-to"></a>获取角色组分配到的核心电子数据展示事例列表

```powershell
Get-ComplianceCase -RoleGroup "Name of role group"
```

### <a name="get-a-list-of-advanced-ediscovery-cases-a-role-group-is-assigned-to"></a>获取角色Advanced eDiscovery分配到的情况列表

```powershell
Get-ComplianceCase -RoleGroup "Name of role group" -CaseType AdvancedEdiscovery
```

## <a name="more-information"></a>详细信息

- **为什么要创建电子数据展示管理员？** 如前所述，电子数据展示管理员是电子数据展示管理员角色组的成员，可以查看和访问您组织中的所有电子数据展示事例。 访问所有电子数据展示事例这一功能有两个重要用途：

  - 如果作为电子数据展示事例唯一成员的人离开了公司，就没有人（包括组织管理角色组的成员或电子数据展示管理员角色组的另一个成员）能够访问该电子数据展示事例，因为他们不是事例的成员。 在这种情况下，将无法访问事例中的数据。 但是，因为电子数据展示管理员可以访问组织的所有电子数据展示事例，他们可以查看事例，并添加自己或其他电子数据展示管理员作为事例的成员。

  - 由于电子数据展示管理员可以查看和访问所有核心电子数据展示Advanced eDiscovery事例，因此他们可以审核和监视所有事例以及关联的合规性搜索。 这有助于防止任何滥用合规性搜索或电子数据展示事例的行为。 此外，因为电子数据展示管理员可以访问合规性搜索的结果中的潜在敏感信息，所以您应该限制电子数据展示管理员的数量。

- **能否将组添加为电子数据展示管理员角色组的成员？** 如前所述，您可以使用安全 & 合规中心 PowerShell 中的 **Add-RoleGroupMember** cmdlet 将启用邮件的安全组添加为电子数据展示管理员角色组中电子数据展示管理员子组的成员。 例如，可以运行以下命令将启用邮件的安全组添加到电子数据展示管理员角色组。 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Exchange不支持Microsoft 365通讯组和通讯组。 必须使用启用邮件的安全组，可通过运行 在 powerShell Exchange Online创建 `New-DistributionGroup -Type Security` 该组。 您还可以创建启用邮件的安全组 (，) 管理中心Exchange或[Microsoft 365 管理中心。](https://go.microsoft.com/fwlink/p/?linkid=2024339) 创建后，可能需要 60 分钟才能将启用邮件的新安全性添加到电子数据展示管理员角色组。 

    此外，如前所述，无法通过使用安全与合规中心 PowerShell 中的 **Add-eDiscoveryCaseAdmin** cmdlet 将启用邮件的安全组&电子数据展示管理员。 只能将单个用户添加为电子数据展示管理员。

    此外，无法将启用邮件的安全组添加为案例的成员。
