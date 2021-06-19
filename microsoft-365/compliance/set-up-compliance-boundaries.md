---
title: 设置电子数据展示调查的合规性边界
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 了解如何使用合规性边界创建逻辑边界，以控制电子数据展示管理员可在 Microsoft 365 中搜索的用户内容位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 23ff50b9cd0ab0178962f7be9f1cedfbd6a7a1f7
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022338"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>设置电子数据展示调查的合规性边界

使用核心电子数据展示或电子数据展示来管理调查时，Advanced eDiscovery本文中的指南。

合规性边界在组织中创建逻辑边界 (如电子数据展示管理员可搜索的邮箱、OneDrive 帐户和 SharePoint 网站) 用户内容位置。 此外，合规性边界还控制谁可以访问用于管理组织中法律、人力资源或其他调查电子数据展示事例。 对于必须尊重地理机构和法规的跨国公司以及政府（通常分为不同的机构）来说，通常需要合规性边界。 在Microsoft 365中，合规性边界可帮助您在使用电子数据展示事例执行内容搜索和管理调查时满足这些要求。
  
我们使用下图中的示例说明合规性边界如何工作。
  
![合规性边界由搜索权限筛选器组成，用于控制对控制电子数据展示事例访问权限的机构和管理角色组的访问权限](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
在此例中，Contoso LTD 是由 Fourth Coffee 和 Coho Winery 这两个子公司组成的组织。 业务要求电子数据展示的经理和调查人员只能搜索其Exchange邮箱、OneDrive帐户SharePoint网站。 此外，电子数据展示管理员和调查人员只能查看其机构中的电子数据展示事例，并且只能访问他们作为成员的情况。 此外，在此方案中，调查人员无法将内容位置保留或导出案例的内容。 下面将说明合规性边界如何满足这些要求。
  
- 内容搜索中的搜索权限筛选功能控制电子数据展示管理员和研究人员可以搜索的内容位置。 这意味着 Fourth Coffee 公司中的电子数据展示管理者和员工只能搜索 Fourth Coffee 子公司中的内容位置。 共同的限制适用于 Coho Winery 子公司。

- [角色组](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery) 为合规性边界提供以下功能：

  - 控制哪些人可以看到电子数据展示事例Microsoft 365 合规中心。 这意味着电子数据展示管理者和管理员只能看到其机构中的电子数据展示事例。

  - 控制谁可以将成员分配给电子数据展示案例。 这意味着电子数据展示管理者和管理员只能向自己作为成员的事例分配成员。

  - 通过添加或删除分配特定权限的角色，控制成员可以执行与电子数据展示相关的任务。

以下是设置合规性边界的过程：
  
[步骤 1：标识要定义机构的用户属性](#step-1-identify-a-user-attribute-to-define-your-agencies)

[步骤 2：为每个机构创建角色组](#step-2-create-a-role-group-for-each-agency)

[步骤 3：创建搜索权限筛选器以强制实施合规性边界](#step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[步骤 4：为机构内调查创建电子数据展示案例](#step-4-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>设置合规性边界之前

- 必须为用户分配Exchange Online许可证。 若要验证这一点，请使用 Exchange Online PowerShell 中的[Get-User](/powershell/module/exchange/get-user) cmdlet。

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>步骤 1：标识要定义机构的用户属性

第一步是选择要用于定义机构的属性。 此属性用于创建搜索权限筛选器，该筛选器限制电子数据展示管理员仅搜索分配了此属性的特定值的用户的内容位置。 例如，假设 Contoso 决定使用 **Department** 属性。 Fourth Coffee 子公司中用户的此属性的值为  `FourthCoffee`  ，Coho Winery 子公司的用户的值为 `CohoWinery` 。 在步骤 3 中，使用此对 ( `attribute:value`  例如 *Department：FourthCoffee*) 来限制电子数据展示管理员可以搜索的用户内容位置。 
  
下面是可用于合规性边界的用户属性的一些示例：
  
- 公司

- CustomAttribute1 - CustomAttribute15

- 部门

- 办公室

- CountryOrRegion (两个字母的国家/地区代码) 

有关完整列表，请参阅受支持的邮箱筛选器 [的完整列表](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties)。

## <a name="step-2-create-a-role-group-for-each-agency"></a>步骤 2：为每个机构创建角色组

下一步是在安全与合规中心&与机构一致的角色组。 建议创建角色组，复制内置电子数据展示管理者组，添加适当的成员，并删除可能不适合你的角色。 有关与电子数据展示相关的角色详细信息，请参阅分配 [电子数据展示权限](assign-ediscovery-permissions.md)。
  
若要创建角色组，请转到 安全与合规中心 中的 **权限** 页面，并为每个将使用合规性边界电子数据展示事例管理调查的团队创建角色组。
  
使用 Contoso 合规性边界方案，需要创建四个角色组，并添加每个角色组的适当成员。
  
- Fourth Coffee 电子数据展示管理者

- Fourth Coffee 调查员

- Coho Winery 电子数据展示经理

- Coho Winery Wines
  
为满足 Contoso 合规性边界方案的要求，还将从调查人员角色组中删除保留和导出角色，以防止调查人员对内容位置进行保留并从案例导出内容。

## <a name="step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>步骤 3：创建搜索权限筛选器以强制实施合规性边界

为每个机构创建角色组后，下一步是创建搜索权限筛选器，将每个角色组关联到其特定机构并定义合规性边界本身。 你需要为每个机构创建一个搜索权限筛选器。 有关创建安全权限筛选器的信息，请参阅配置内容 [搜索的权限筛选](permissions-filtering-for-content-search.md)。
  
下面是用于创建用于合规性边界的搜索权限筛选器的语法。

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'" -Action <Action>
```

下面是命令中每个参数的说明：
  
- `FilterName`：指定筛选器的名称。 使用描述或标识筛选器所使用的机构的名称。

- `Users`：指定应用此筛选器的用户或组，这些用户或组将执行搜索操作。 对于合规性边界，此参数 (在步骤 3) 中创建筛选器的代理中创建的角色组。 请注意，这是一个多值参数，因此可以包含一个或多个角色组，用逗号分隔。

- `Filters`：指定筛选器的搜索条件。 对于合规性边界，定义以下筛选器。 每一个都适用于一个内容位置。

    - `Mailbox`：指定在参数中OneDrive角色组可以搜索的邮箱 `Users` 或邮箱帐户。 此筛选器允许角色组的成员仅搜索邮箱或OneDrive机构中的帐户;例如， `"Mailbox_Department -eq 'FourthCoffee'"` 。

    - `Site_Path`：指定SharePoint中定义的角色组可以搜索的网站 `Users` 。 *SharePointURL* 指定角色组的成员可以搜索的代理中的网站。 例如，`"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`。 请注意， `Site` `Site_Path` 和 筛选器由 **-or 运算符** 连接。

     > [!NOTE]
     > 参数的语法 `Filters` 包括筛选器 *列表*。 筛选器列表是包含邮箱筛选器和网站路径筛选器（用逗号分隔）的筛选器。 在上一个示例中，请注意逗号分隔 **Mailbox_MailboxPropertyName和****Site_Path：** `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'"` 。 在运行内容搜索期间处理此筛选器时，会从筛选器列表中创建两个搜索权限筛选器：一个邮箱筛选器和一个SharePoint筛选器。 使用筛选器列表的替代方法是为每个机构创建两个单独的搜索权限筛选器：一个搜索权限筛选器用于邮箱属性，一个筛选器用于SharePoint网站属性。 在任一情况下，结果都相同。 优先使用筛选器列表或创建单独的搜索权限筛选器。

- `Action`：指定应用筛选器的搜索操作的类型。 例如，仅在参数中定义的角色组的成员运行搜索  `-Action Search` 时 `Users` 应用筛选器。 在这种情况下，导出搜索结果时不会应用筛选器。 对于合规性边界，请使用  `-Action All` ，以便筛选器适用于所有搜索操作。 

    有关搜索操作的列表，请参阅配置内容搜索的权限筛选中的"New-ComplianceSecurityFilter" [部分](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)。

下面是为支持 Contoso 合规性边界方案而创建的两个搜索权限筛选器的示例。 这两个示例包括逗号分隔的筛选器列表，列表中包括邮箱和网站筛选器在同一搜索权限筛选器中，并用逗号分隔。
  
### <a name="fourth-coffee"></a>Fourth Coffee

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-4-create-an-ediscovery-case-for-intra-agency-investigations"></a>步骤 4：为机构内调查创建电子数据展示案例

最后一步是在 Microsoft 365 合规中心 中创建核心电子数据展示案例或 Advanced eDiscovery 案例，然后将在步骤 2 中创建的角色组添加为该案例的成员。 这导致使用合规性边界有两个重要特征：
  
- 只有添加到案例的角色组的成员才能在安全与合规中心内查看&案例。 例如，如果 Fourth Coffee 检查人员角色组是案例的唯一成员，则 Fourth Coffee 电子数据展示管理员角色组 (的成员或任何其他角色组) 的成员将不能查看或访问该案例。

- 当分配给案例的角色组的成员运行与案例关联的搜索时，他们只能搜索其机构 (该位置由你在步骤 3.) 中创建的搜索权限筛选器定义。

若要创建案例并分配成员：

1. 转到"**核心电子数据****展示或** Advanced eDiscovery"页面中Microsoft 365 合规中心创建一个案例。

2. 在事例列表中，单击您创建的事例的名称。

3. 将角色组作为成员添加到案例。 有关说明，请参阅以下文章之一：

   - [向核心电子数据展示案例添加成员](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

   - [将成员添加到Advanced eDiscovery案例](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> 向案例添加角色组时，只能添加作为成员的角色组。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>在多地理位置环境中搜索和导出内容

通过搜索权限筛选器，还可以控制内容在导出的路由位置，以及搜索内容位置时可以搜索的数据中心SharePoint Multi-Geo[位置](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)。
  
- **导出搜索结果：** 可以从特定数据中心导出Exchange邮箱、SharePoint网站OneDrive帐户。 这意味着您可以指定搜索结果将导出到的数据中心位置。

    使用 **New-ComplianceSecurityFilter** 或 **Set-ComplianceSecurityFilter** cmdlet 的 **Region** 参数创建或更改导出将通过哪个数据中心。
  
    |**参数值**|**数据中心位置**|
    |:-----|:-----|
    |NAM  <br/> |北美 (数据中心位于美国)   <br/> |
    |EUR  <br/> |欧洲  <br/> |
    |APC  <br/> |亚太地区  <br/> |
    |CAN <br/> |加拿大|
    |||

- **路由内容搜索：** 你可以将网站和SharePoint的内容OneDrive路由到附属数据中心。 这意味着您可以指定将运行搜索的数据中心位置。

    使用 **Region** 参数的下列值之一来控制搜索将在其中运行的数据中心位置，该位置SharePoint网站和OneDrive帐户。 
  
    |**参数值**|**数据中心路由位置SharePoint**|
    |:-----|:-----|
    |NAM  <br/> |美国  <br/> |
    |EUR  <br/> |欧洲  <br/> |
    |APC  <br/> |亚太地区  <br/> |
    |CAN  <br/> |美国  <br/> |
    |AUS  <br/> |亚太地区  <br/> |
    |KOR  <br/> |组织的默认数据中心  <br/> |
    |GBR  <br/> |欧洲  <br/> |
    |JPN  <br/> |亚太地区  <br/> |
    |IND  <br/> |亚太地区  <br/> |
    |一百万  <br/> |美国  <br/> |
    |NOR  <br/> |欧洲 |
    |BRA  <br/> |北美数据中心 |
    |||

   如果不为搜索权限筛选器指定 **Region** 参数，将搜索组织SharePoint区域。 搜索结果将导出到最近的数据中心。

   为了简化概念 **，Region** 参数控制用于搜索 SharePoint 和 OneDrive 中的内容的数据中心。 这不适用于搜索网站中的内容Exchange Exchange内容搜索不受数据中心的地理位置限制。 此外，相同的 **Region** 参数值可能还指示通过导出的数据中心。 这通常是控制跨地理平台移动数据所必需的。

> [!NOTE]
> 如果您使用的是 Advanced eDiscovery，**则 Region** 参数不控制导出数据的区域。 数据从组织的主数据中心导出。 此外，搜索 SharePoint 和 OneDrive 中的内容不受数据中心的地理位置限制。 搜索所有数据中心。 有关解决方案Advanced eDiscovery，请参阅 Advanced eDiscovery[中的](overview-ediscovery-20.md)Microsoft 365。

下面是为合规性边界创建搜索权限筛选器时使用 **Region** 参数的示例。 这假定 Fourth Coffee 子公司位于北美，Coho Winery 位于欧洲。 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

在多地理位置环境中搜索和导出内容时，请记住以下事项。
  
- **Region** 参数不控制 Exchange 邮箱的搜索。 搜索邮箱时，将搜索所有数据中心。 若要限制搜索Exchange的范围，在创建或更改搜索权限筛选器时，请使用 **Filters** 参数。

- 如果电子数据展示管理员需要跨多个 SharePoint 区域进行搜索，则需要为电子数据展示管理员创建一个不同的用户帐户，以在搜索权限筛选器中用于指定 SharePoint 站点或 OneDrive 帐户所在的区域。 有关设置此设置的信息，请参阅内容搜索中的"在SharePoint Multi-Geo环境中[搜索内容"部分](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment)。

- 在搜索 SharePoint 和 OneDrive 中的内容时 **，Region** 参数将搜索引导到电子数据展示管理员将在其中执行电子数据展示调查的主位置或附属位置。 如果电子数据展示SharePoint搜索OneDrive搜索权限筛选器中指定的区域之外的所有网站，则不返回任何搜索结果。

- 导出搜索结果时，所有内容位置 (包括 Exchange、Skype for Business、SharePoint、OneDrive 以及可以使用内容搜索工具) 搜索的其他服务中的内容将上载到数据中心中由 **Region** 参数指定的 Azure 存储空间 位置。 这可帮助组织通过不允许跨受控边界导出内容来保持合规性。 如果在搜索权限筛选器中未指定任何区域，内容将上载到组织的主数据中心。

- 您可以编辑现有的搜索权限筛选器，以通过运行以下命令添加或更改区域：

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>使用中心网站的合规性SharePoint边界

[SharePoint中心网站](/sharepoint/dev/features/hub-site/hub-site-overview)通常与电子数据展示合规性边界遵循的相同地理或机构边界保持一致。 这意味着您可以使用中心网站的站点 ID 属性创建合规性边界。 为此，请使用 SharePoint Online PowerShell 中的[Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) cmdlet 获取中心网站的 SiteId，然后使用部门 ID 属性的此值创建搜索权限筛选器。

使用以下语法为中心网站创建SharePoint筛选器：

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

下面是为 Coho Winery 代理中心网站创建搜索权限筛选器的示例：

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>合规性边界限制

管理电子数据展示事例和使用合规性边界的调查时，请记住以下限制。
  
- 创建和运行搜索时，可选择公司外部的内容位置。 但是由于搜索权限筛选器，因此这些位置的内容不包含在搜索结果中。

- 合规性边界不适用于电子数据展示事例中的保留。 这意味着一个公司中的电子数据展示管理者可以将用户放在不同的公司中保留。 但是，如果电子数据展示管理器搜索已保留用户的内容位置，将实施合规性边界。 这意味着电子数据展示管理器无法搜索用户的内容位置，即使他们能够保留用户。

    此外，保留统计信息仅适用于公司中的内容位置。

- 如果您分配了搜索权限筛选器 (邮箱或网站筛选器) 并且您尝试导出包含组织中所有 SharePoint 网站的搜索的未索引项目，您将收到以下错误消息： `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied` 。 如果分配了搜索权限筛选器，并且希望从 SharePoint 导出未索引的项目，您必须重新运行搜索并包括要搜索的特定 SharePoint 网站。 否则，只能从包含所有网站索引项的搜索中导出SharePoint项。 有关导出搜索结果时的选项的详细信息，请参阅导出 [内容搜索结果](export-search-results.md#step-1-prepare-search-results-for-export)。

- 搜索权限筛选器未应用于 Exchange 公用文件夹。

## <a name="more-information"></a>更多信息

- 如果邮箱已取消许可或软删除，则不再在合规性边界内考虑用户。 如果在删除邮箱时将其置于保留状态，则保留在邮箱中的内容仍受合规性边界或搜索权限筛选器限制。

- 如果为用户实现了合规性边界和搜索权限筛选器，则建议您不要删除用户的邮箱，而不要删除其OneDrive帐户。 换句话说，如果您删除用户的邮箱，则还应删除用户的 OneDrive 帐户，因为 mailbox_RecipientFilter 用于强制执行 OneDrive 的搜索权限筛选器。

- 合规性边界和搜索权限筛选器取决于在 Exchange、OneDrive 和 SharePoint 中的内容上标记的属性，以及此标记内容的后续索引。

- 建议不要将排除筛选器 (例如，在基于内容的合规性) 搜索 `-not()` 权限筛选器中使用。 如果未对具有最近更新的属性的内容编制索引，则使用排除筛选器可能会获得意外结果。

## <a name="frequently-asked-questions"></a>常见问题解答

**谁可以使用 (cmdlet 和 New-ComplianceSecurityFilter cmdlet Set-ComplianceSecurityFilter和管理) ？**
  
若要创建、查看和修改搜索权限筛选器，您必须是 Microsoft 365 合规中心中组织管理角色组的成员。
  
**如果将电子数据展示管理员分配给跨多个机构的多个角色组，如何搜索一个机构或另一个机构中的内容？**
  
电子数据展示管理员可以将参数添加到其搜索查询中，以将搜索限制到特定机构。 例如，如果组织已指定 **CustomAttribute10** 属性来区分机构，他们可以将以下内容追加到搜索查询中，以搜索特定机构中的邮箱和 OneDrive 帐户  `CustomAttribute10:<value>` ：。
  
**如果用作搜索权限筛选器中的合规性属性的值发生更改，会发生什么情况？**
  
如果更改了筛选器中使用的属性的值，则搜索权限筛选器最多需要三天才能强制实施合规性边界。 例如，在 Contoso 方案中，假设 Fourth Coffee 机构中的用户被转移到 Coho Winery 代理。 因此，用户对象上的 **Department** 属性的值从 *FourthCoffee* 更改为 *CohoWinery*。 在这种情况下，Fourth Coffee 电子数据展示和电子商务将在属性更改后的最多三天内获取该用户的搜索结果。 同样，Coho Winery 电子数据展示管理员和调查人员最多需要三天的时间才能获取用户的搜索结果。
  
**电子数据展示管理员能否从两个单独的合规性边界查看内容？**
  
可以，在搜索 Exchange 邮箱时，可以通过将电子数据展示管理员添加到对两个机构都可见的角色组来完成此操作。 但是，在搜索 SharePoint 网站和 OneDrive 帐户时，只有在机构位于同一区域或地理位置时，电子数据展示管理员才能搜索不同合规性边界内的内容。 **注意：** 此网站限制不适用于高级电子数据展示，因为搜索 SharePoint 和 OneDrive 中的内容不受地理位置限制。
  
**搜索权限筛选器是否适用于电子数据展示案例保留、Microsoft 365 保留策略或 DLP？**
  
否，此时不会。
  
**如果指定一个控制内容导出位置的区域，但该区域中没有 SharePoint 组织，我能否仍搜索 SharePoint？**
  
如果搜索权限筛选器中指定的区域在你的组织中不存在，将搜索默认区域。
  
**可以在组织中创建的搜索权限筛选器的最大数量是什么？**
  
对可以在组织中创建的搜索权限筛选器的数量没有限制。 但是，当搜索权限筛选器超过 100 个时，搜索性能将受到影响。 若要尽可能减少组织中搜索权限筛选器的数量，请创建尽可能将 Exchange、SharePoint 和 OneDrive 的规则合并到单个搜索权限筛选器中的筛选器。
