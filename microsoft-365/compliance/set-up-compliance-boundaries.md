---
title: 设置电子数据展示调查的合规性边界
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
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 了解如何使用合规性边界创建逻辑边界，以控制电子数据展示管理员可在 Microsoft 365 中搜索的用户内容位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe6df03491350c33416021523f276e203a416fc9
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099732"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>设置电子数据展示调查的合规性边界

使用核心电子数据展示或高级电子数据展示管理调查时，可以应用本文中的指南。

合规性边界在组织中创建逻辑边界，以控制用户内容位置 (如电子数据展示管理员可以搜索的邮箱、OneDrive 帐户和 SharePoint) 网站）。 此外，合规性边界还控制谁可以访问用于管理组织中法律、人力资源或其他调查电子数据展示事例。 对于必须尊重地理板和法规的跨国公司以及政府（通常分为不同的机构）来说，通常需要合规性边界。 在 Microsoft 365 中，合规性边界可帮助你在使用电子数据展示事例执行内容搜索和管理调查时满足这些要求。
  
我们使用下图中的示例说明合规性边界如何工作。
  
![合规性边界由搜索权限筛选器组成，这些筛选器控制对控制电子数据展示事例访问权限的机构和管理角色组的访问权限](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
在此例中，Contoso LTD 是一个包含两家子公司（Fourth Coffee 和 Coho Winery）的组织。 业务要求电子数据展示经理和调查人员只能搜索其机构中的 Exchange 邮箱、OneDrive 帐户和 SharePoint 网站。 此外，电子数据展示管理员和调查人员只能查看其机构中的电子数据展示事例，并且只能访问他们作为成员的情况。 下面说明合规性边界如何满足这些要求。
  
- 内容搜索中的搜索权限筛选功能控制电子数据展示管理员和调查人员可以搜索的内容位置。 这意味着 Fourth Coffee 机构中的电子数据展示管理人员和调查人员只能搜索 Fourth Coffee 子公司中的内容位置。 相同的限制适用于 Coho Winery 子公司。

    角色组控制谁可以在安全与合规中心内&电子数据展示事例。 这意味着电子数据展示管理员和调查人员只能查看其机构中的电子数据展示事例。

- 角色组还控制谁可以将成员分配给电子数据展示案例。 这意味着电子数据展示管理员和调查人员只能将成员分配给自己是其成员的事例。

以下是设置合规性边界的过程：
  
[步骤 1：确定要定义机构的用户属性](#step-1-identify-a-user-attribute-to-define-your-agencies)

[步骤 2：向 Microsoft 支持人员提出将用户属性同步到 OneDrive 帐户的请求](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[步骤 3：为每个机构创建角色组](#step-3-create-a-role-group-for-each-agency)

[步骤 4：创建搜索权限筛选器以强制实施合规性边界](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[步骤 5：为机构内调查创建电子数据展示案例](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>设置合规性边界之前

在步骤 1) 中标识为 (的 Azure Active Directory (Azure AD) 属性可以成功同步到步骤 2) 中的用户的 OneDrive 帐户 (之前，必须满足以下先决条件：

- 必须为用户分配 Exchange Online 许可证和 SharePoint Online 许可证。

- 用户邮箱的大小必须至少为 10 MB。 如果用户邮箱小于 10 MB，用于定义机构的属性不会同步到用户的 OneDrive 帐户。

- 合规性边界和用于创建搜索权限筛选器的属性要求将 Azure Active Directory (Azure AD) 属性同步到用户邮箱。 若要验证想要使用的属性已同步，请运行 Exchange Online PowerShell 中的 [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) cmdlet。 此 cmdlet 的输出显示同步到 Exchange Online 的 Azure AD 属性。

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>步骤 1：确定要定义机构的用户属性

第一步是选择要用于定义你的机构的 Azure AD 属性。 此属性用于创建搜索权限筛选器，该筛选器限制电子数据展示管理员仅搜索分配了此属性的特定值的用户的内容位置。 例如，假设 Contoso 决定使用 **Department** 属性。 Fourth Coffee 子公司中用户的此属性的值为 ，Coho Winery 子公司的用户的值为  `FourthCoffee` `CohoWinery` 。 在步骤 4 中，使用此对 ( `attribute:value`  例如 *Department：FourthCoffee*) 来限制电子数据展示管理员可以搜索的用户内容位置。 
  
以下是可用于合规性边界的 Azure AD 用户属性列表：
  
- Company

- CustomAttribute1 - CustomAttribute15

- 部门

- 办公室

- C (两个字母的国家/地区代码) <sup>*</sup>

  > [!NOTE]
  > <sup>*</sup> 此属性映射到在 Exchange Online PowerShell 中运行 **Get-User** cmdlet 返回的 CountryOrRegion 属性。 此 cmdlet 返回本地化的国家/地区名称，该名称从两个字母的国家/地区代码翻译。 有关详细信息，请参阅 [Set-User](https://docs.microsoft.com/powershell/module/exchange/set-user) cmdlet 参考文章中的 CountryOrRegion 参数说明。

虽然更多用户属性可用，特别是对于 Exchange 邮箱，但上面列出的属性是 OneDrive 当前唯一支持的属性。
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>步骤 2：向 Microsoft 支持人员提出将用户属性同步到 OneDrive 帐户的请求

下一步是向 Microsoft 支持部门提出请求，以将你在步骤 1 中选择的 Azure AD 属性同步到组织的所有 OneDrive 帐户。 发生此同步后， (属性及其值) 在步骤 1 中选择的属性将映射到隐藏的托管属性 `ComplianceAttribute` 。 使用此属性在步骤 4 中为 OneDrive 创建搜索权限筛选器。
  
向 Microsoft 支持人员提交请求时，请包含以下信息：
  
- 组织的默认域名

- 步骤 1 中的 Azure AD (的名称) 

- 支持请求用途的以下标题或说明："启用 OneDrive for Business Synchronization with Azure AD for Compliance Security Filters"。 这有助于将请求路由到实现请求电子数据展示工程团队。

进行工程更改并将属性同步到 OneDrive 后，Microsoft 支持会向您发送更改的生成号和估计的部署日期。 在提交支持请求后，部署过程通常需要 4-6 周。
  
> [!IMPORTANT]
> 您可以在部署此属性更改之前完成步骤 3 到步骤 5。 但在部署属性同步之前，运行内容搜索不会从搜索权限筛选器中指定的 OneDrive 帐户返回文档。
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>步骤 3：为每个机构创建角色组

下一步是在安全与合规中心&与机构一致的角色组。 建议您通过复制内置电子数据展示管理员组、添加相应的成员以及删除可能不适合您需求的角色来创建角色组。 有关电子数据展示相关角色详细信息，请参阅 [Office 365](assign-ediscovery-permissions.md)安全与合规中心&电子数据展示权限。
  
若要创建角色组，请转到安全与合规中心中的"权限"页面，并为每个机构的每个团队创建一个角色组，这些团队将使用合规性边界和电子数据展示事例来管理调查。 &
  
使用 Contoso 合规性边界方案，需要创建四个角色组，并添加每个角色组的适当成员。
  
- Fourth Coffee eDiscovery Managers

- Fourth Coffee 检查人员

- Coho Winery 电子数据展示管理员

- Coho Winery 调查人员
  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>步骤 4：创建搜索权限筛选器以强制实施合规性边界

为每个机构创建角色组后，下一步是创建搜索权限筛选器，将每个角色组关联到其特定机构并定义合规性边界本身。 您需要为每个机构创建一个搜索权限筛选器。 有关创建安全权限筛选器的信息，请参阅"为内容搜索配置[权限筛选"。](permissions-filtering-for-content-search.md)
  
下面是用于创建用于合规性边界的搜索权限筛选器的语法。

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

以下是命令中每个参数的说明：
  
- `FilterName`：指定筛选器的名称。 使用描述或标识筛选器所使用的机构的名称。

- `Users`：指定将此筛选器应用于他们执行的内容搜索操作的用户或组。 对于合规性边界，此参数 (在步骤 3) 创建筛选器的代理中创建的角色组。 请注意，这是一个多值参数，因此可以包含一个或多个角色组，用逗号分隔。

- `Filters`：指定筛选器的搜索条件。 对于合规性边界，定义以下筛选器。 每个内容位置都适用于一个内容位置。 

    - `Mailbox`：指定参数中定义的角色组可以搜索  `Users` 的邮箱。 对于合规性边界  *，ComplianceAttribute*  与在步骤 1 中标识的属性相同  *，AttributeValue*  指定了机构。 此筛选器允许角色组的成员仅搜索特定机构中的邮箱;例如 `"Mailbox_Department -eq 'FourthCoffee'"` ，。 

    - `Site`：指定参数中定义的角色组可以搜索的 OneDrive `Users` 帐户。 对于 OneDrive 筛选器，请使用实际的字符串  `ComplianceAttribute` 。 这会映射到你在步骤 1 中标识的同一属性，并且由于你在步骤 2 中提交的支持请求而同步到 OneDrive 帐户; *AttributeValue*  指定机构。 此筛选器允许角色组的成员仅搜索特定机构中的 OneDrive 帐户;例如  `"Site_ComplianceAttribute -eq 'FourthCoffee'"` ，。

    - `Site_Path`：指定参数中定义的角色组可以搜索的 SharePoint  `Users` 网站。 *SharePointURL* 指定角色组的成员可以搜索的代理中的网站。 例如，`"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`。 请注意， `Site` `Site_Path` 和筛选器由 **-or 运算符** 连接。

     > [!NOTE]
     > 参数的语法 `Filters` 包括筛选器 *列表*。 筛选器列表是包含邮箱筛选器和网站筛选器（用逗号分隔）的筛选器。 在上一示例中，请注意，逗号分隔 **Mailbox_ComplianceAttribute和****Site_ComplianceAttribute**： `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"` 。 在运行内容搜索期间处理此筛选器时，会从筛选器列表中创建两个搜索权限筛选器：一个邮箱筛选器和一个网站筛选器。 使用筛选器列表的替代方法是为每个机构创建两个单独的搜索权限筛选器：一个搜索权限筛选器用于邮箱属性，一个筛选器用于网站属性。 无论哪种情况，结果都相同。 优先使用筛选器列表或创建单独的搜索权限筛选器。

- `Action`：指定应用筛选器的合规性搜索操作的类型。 例如，仅在参数中定义的角色组的成员运行内容搜索时  `-Action Search` `Users` 应用筛选器。 在这种情况下，导出搜索结果时不会应用筛选器。 对于合规性边界，请使用  `-Action All` 以便筛选器适用于所有搜索操作。 

    有关内容搜索操作的列表，请参阅"配置内容搜索的权限筛选"中的"New-ComplianceSecurityFilter" [部分](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)。

下面是将创建以支持 Contoso 合规性边界方案的两个搜索权限筛选器的示例。 这两个示例均包括逗号分隔的筛选器列表，其中邮箱和网站筛选器包含在同一搜索权限筛选器中，用逗号分隔。
  
### <a name="fourth-coffee"></a>Fourth Coffee

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>步骤 5：为机构内调查创建电子数据展示案例

最后一步是在 Microsoft 365 合规中心中创建核心电子数据展示案例或高级电子数据展示案例，然后将在步骤 3 中创建的角色组添加为该案例的成员。 这导致使用合规性边界有两个重要特征：
  
- 只有添加到案例的角色组的成员才能在安全与合规中心查看和访问&案例。 例如，如果 Fourth Coffee 检查人员角色组是案例的唯一成员，则 Fourth Coffee 电子数据展示管理员角色组 (的成员或任何其他角色组) 的成员将无法查看或访问该案例。

- 当分配给案例的角色组的成员运行与案例关联的搜索时，他们只能搜索其代理 (该内容位置由你在步骤 4.) 中创建的搜索权限筛选器定义。

若要创建案例并分配成员：

1. 转到 Microsoft  365合规中心的核心电子数据展示或高级电子数据展示页面并创建一个案例。

2. 在事例列表中，单击您创建的事例的名称。

3. 在"**管理此案例"** 飞出页的"**管理角色组"下**，单击 ![ "添加"图标 ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) 。

    ![将角色组添加为电子数据展示案例的成员](../media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. 在角色组列表中，选择在步骤 3 中创建的角色组之一，然后单击"**添加"。**

5. 在 **"** 管理此案例 **"飞出上** 单击"保存"以保存更改。

> [!NOTE]
向案例添加角色组时，只能添加作为成员的角色组。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>在多地理位置环境中搜索和导出内容

搜索权限筛选器还可用于控制内容路由到何处进行导出，以及搜索 SharePoint 多地理位置环境中的内容位置时可以搜索 [的数据中心](https://go.microsoft.com/fwlink/?linkid=860840)。
  
- **导出搜索结果：** 可以从特定数据中心从 Exchange 邮箱、SharePoint 网站和 OneDrive 帐户导出搜索结果。 这意味着您可以指定搜索结果将导出到的数据中心位置。

    将 **Region** 参数用于 **New-ComplianceSecurityFilter** 或 **Set-ComplianceSecurityFilter** cmdlet，以创建或更改将通过哪个数据中心路由导出。
  
    |**参数值**|**数据中心位置**|
    |:-----|:-----|
    |NAM  <br/> |北美 (数据中心位于美国)   <br/> |
    |EUR  <br/> |欧洲  <br/> |
    |APC  <br/> |亚太地区  <br/> |
    |CAN <br/> |加拿大|
    |||

- **路由内容搜索：** 可以将 SharePoint 网站和 OneDrive 帐户的内容搜索路由到附属数据中心。 这意味着您可以指定将运行搜索的数据中心位置。

    对 Region 参数使用以下值之一来控制在搜索 SharePoint 网站和 OneDrive 帐户时将运行搜索的数据中心位置。 
  
    |**参数值**|**SharePoint 的数据中心路由位置**|
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
    |功能区  <br/> |美国  <br/> |
    |NOR  <br/> |欧洲 |
    |BRA  <br/> |北美数据中心 |
    |||

   如果不为搜索权限筛选器指定 **Region** 参数，将搜索组织的主要 SharePoint 区域。 搜索结果将导出到最近的数据中心。

   为了简化概念 **，Region** 参数控制用于搜索 SharePoint 和 OneDrive 中内容的数据中心。 这不适用于在 Exchange 中搜索内容，因为 Exchange 内容搜索不受数据中心的地理位置限制。 此外，相同的 **Region** 参数值也可能规定通过该导出的数据中心。 这通常是控制跨地理平台移动数据所必需的。

> [!NOTE]
> 如果使用的是高级电子数据展示， **则 Region** 参数不控制从中导出数据的区域。 数据从组织的主数据中心导出。 此外，搜索 SharePoint 和 OneDrive 中的内容不受数据中心的地理位置限制。 搜索所有数据中心。 有关高级电子数据展示详细信息，请参阅 Microsoft [365](overview-ediscovery-20.md)中的高级电子数据展示解决方案概述。

下面是为合规性边界创建搜索权限筛选器时使用 **Region** 参数的示例。 这假定 Fourth Coffee 子公司位于北美，Coho Winery 位于欧洲。 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

在多地理位置环境中搜索和导出内容时，请记住以下事项。
  
- **Region** 参数不控制 Exchange 邮箱的搜索。 搜索邮箱时，将搜索所有数据中心。 若要限制搜索 Exchange 邮箱的范围，在创建或更改搜索权限筛选器时，请使用 **Filters** 参数。 

- 如果电子数据展示管理员必须跨多个 SharePoint 区域进行搜索，则需要为此电子数据展示管理员创建一个不同的用户帐户，以在搜索权限筛选器中用于指定 SharePoint 网站或 OneDrive 帐户所在的区域。 有关设置此设置的信息，请参阅内容搜索中的"在 SharePoint 多地理位置环境中搜索 [内容"部分](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment)。

- 在 SharePoint 和 OneDrive 中搜索内容时 **，Region** 参数将搜索引导到电子数据展示管理员将在其中执行电子数据展示调查的主位置或附属位置。 如果电子数据展示管理员在搜索权限筛选器中指定的区域之外搜索 SharePoint 和 OneDrive 网站，则不返回任何搜索结果。

- 导出搜索结果时，所有内容位置 (包括 Exchange、Skype for Business、SharePoint、OneDrive 以及可以使用内容搜索工具) 搜索的其他服务中的内容将上载到由 **Region** 参数指定的数据中心中的 Azure 存储位置。 这通过不允许内容跨受控边界导出来帮助组织保持合规性。 如果在搜索权限筛选器中未指定任何区域，内容将上载到组织的主数据中心。

- 您可以编辑现有的搜索权限筛选器，以通过运行以下命令添加或更改区域：

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>使用 SharePoint 中心网站的合规性边界

[SharePoint 中心网站](https://docs.microsoft.com/sharepoint/dev/features/hub-site/hub-site-overview) 通常与电子数据展示合规性边界遵循的相同地理或机构边界保持一致。 这意味着您可以使用中心网站的站点 ID 属性创建合规性边界。 为此，请使用 SharePoint Online PowerShell 中的 [Get-SPOHubSite](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spohubsite#examples) cmdlet 获取中心网站的 SiteId，然后使用部门 ID 属性的此值创建搜索权限筛选器。

使用以下语法为 SharePoint 中心网站创建搜索权限筛选器：

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

下面是为 Coho Winery 代理中心网站创建搜索权限筛选器的示例：

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>合规性边界限制

管理电子数据展示事例和使用合规性边界的调查时，请记住以下限制。
  
- 创建和运行搜索时，可以选择机构外部的内容位置。 但是，由于搜索权限筛选器，搜索结果中不包含来自这些位置的内容。

- 合规性边界不适用于电子数据展示事例中的保留。 这意味着一个代理中的电子数据展示管理员可以将不同机构中的用户放在保留状态。 但是，如果电子数据展示管理员搜索被置于保留状态的用户的内容位置，将强制实施合规性边界。 这意味着电子数据展示管理员将无法搜索用户的内容位置，即使他们能够将用户放在保留状态。

    此外，保留统计信息仅适用于机构中的内容位置。

- 搜索权限筛选器不适用于 Exchange 公用文件夹。

## <a name="more-information"></a>更多信息

- 如果邮箱已取消授权或软删除，Azure AD 属性将不再同步到邮箱。 如果在删除邮箱时对邮箱进行了保留，则保留在邮箱中的内容仍受合规性边界或搜索权限筛选器的限制，该筛选器基于上次在删除邮箱之前同步 Azure AD 属性的时间。 

    此外，如果用户的邮箱已取消许可或软删除，则用户邮箱和 OneDrive 帐户之间的同步将停止。 OneDrive 帐户的合规性属性的最后一个标记值将保持有效。

- 合规性属性每七天从用户的 Exchange 邮箱同步到其 OneDrive 帐户。 如前所述，此同步仅在为用户分配 Exchange Online 和 SharePoint Online 许可证且用户的邮箱至少为 10 MB 时发生。

- 如果针对用户邮箱和 OneDrive 帐户实现的合规性边界和搜索权限筛选器，则建议您不要删除用户的邮箱，而不要删除其 OneDrive 帐户。 换句话说，如果删除用户的邮箱，则还应删除用户的 OneDrive 帐户。

- 在某些情况下， (返回员工) 用户可能拥有两个或多个 OneDrive 帐户。 在这些情况下，将仅同步与 Azure AD 中的用户关联的主 OneDrive 帐户。

- 合规性边界和搜索权限筛选器取决于对 Exchange、OneDrive 和 SharePoint 中的内容标记的属性以及此标记内容的后续索引。 

- 建议不要将排除筛选器 (例如，在基于内容的合规性边界) 搜索权限 `-not()` 筛选器中。 如果未对具有最近更新的属性的内容编制索引，则使用排除筛选器可能会获得意外结果。 

## <a name="frequently-asked-questions"></a>常见问题解答

**谁可以使用 (cmdlet 和 New-ComplianceSecurityFilter cmdlet 创建和管理Set-ComplianceSecurityFilter筛选器) ？**
  
若要创建、查看和修改搜索权限筛选器，您必须是安全与合规中心内组织&组的成员。
  
**如果将电子数据展示管理员分配给跨多个机构的多个角色组，他们如何在一个代理或另一个代理中搜索内容？**
  
电子数据展示管理员可以将参数添加到其搜索查询中，以将搜索限制为特定机构。 例如，如果组织已指定 **CustomAttribute10** 属性来区分机构，他们可以将以下内容追加到搜索查询中，以搜索特定机构中的邮箱和 OneDrive  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>` 帐户：
  
**如果在搜索权限筛选器中用作合规性属性的值发生更改，会发生什么情况？**
  
如果更改了筛选器中使用的属性值，则搜索权限筛选器最多需要三天才能强制实施合规性边界。 例如，在 Contoso 方案中，假设 Fourth Coffee 机构中的用户被转移到 Coho Winery 机构。 因此，用户对象上的 **Department** 属性的值从 *FourthCoffee* 更改为 *CohoWinery。* 在这种情况下，Fourth Coffee 电子数据展示和资金将在属性更改后最多三天获取该用户的搜索结果。 同样，Coho Winery 电子数据展示管理员和调查人员最多需要三天才能获得用户的搜索结果。
  
**电子数据展示管理员能否从两个单独的合规性边界查看内容？**
  
可以，通过将电子数据展示管理器添加到对两个机构具有可见性的角色组来搜索 Exchange 邮箱时，可以完成此操作。 但是，在搜索 SharePoint 网站和 OneDrive 帐户时，电子数据展示管理员只能在机构位于同一区域或地理位置时搜索不同合规性边界中的内容。 **注意：** 此网站限制不适用于高级电子数据展示，因为搜索 SharePoint 和 OneDrive 中的内容不受地理位置限制。
  
**搜索权限筛选器是否适用于电子数据展示案例保留、Microsoft 365 保留策略或 DLP？**
  
否，目前不是。
  
**如果指定一个控制内容导出位置的区域，但该区域中没有 SharePoint 组织，我能否仍搜索 SharePoint？**
  
如果组织中不存在搜索权限筛选器中指定的区域，将搜索默认区域。
  
**可以在组织中创建的搜索权限筛选器的最大数量是什么？**
  
对可在组织中创建的搜索权限筛选器的数量没有限制。 但是，当搜索权限筛选器超过 100 个时，搜索性能将受到影响。 若要尽可能减少组织中搜索权限筛选器的数量，请创建尽可能将 Exchange、SharePoint 和 OneDrive 的规则合并到单个搜索权限筛选器中的筛选器。
