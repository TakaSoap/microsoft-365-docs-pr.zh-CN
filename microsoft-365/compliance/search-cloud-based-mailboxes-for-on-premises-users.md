---
title: 搜索本地用户基于云的邮箱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 在 Exchange 混合部署中，使用安全与合规中心中的内容搜索工具搜索并导出本地用户的 MicrosoftTeams 聊天数据（称为 1xN 聊天）。
ms.openlocfilehash: ab523c0d2d334d3d2366711e241b3bafa2e0002f
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352115"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users"></a>搜索本地用户基于云的邮箱

如果你的组织具有 Exchange 混合部署（或者贵组织已将本地 Exchange 组织与 Office 365 同步），并且已启用 Microsoft Teams，则用户可以使用 Teams 聊天应用程序进行即时消息传递。 对于基于云的用户，Teams 聊天数据（也称为 *1xN 聊天*）将保存到其基于云的主邮箱中。 当本地用户使用 Teams 聊天应用程序时，其主邮箱位于本地。 为了绕开此限制，Microsoft 发布了一项新功能，其中创建了基于云的存储区域（称为本地用户基于云的邮箱），用于存储本地用户的 Teams 聊天数据。 这让你能够使用安全与合规中心中的内容搜索工具来搜索并导出本地用户的 Teams 聊天数据。 
  
以下是设置本地用户基于云的邮箱的要求和限制：
  
- 本地目录服务（如 Active Directory）中的用户帐户必须与 Azure Active Directory（Microsoft 365 中的目录服务）同步。 这意味着将在 Microsoft 365 中创建一个邮件用户帐户，并将该帐户与其主邮箱位于本地组织中的用户相关联。

- 必须为其主邮箱位于本地组织中的用户分配 Microsoft Teams 许可证和 Exchange Online 计划 1 许可证（最低要求）。

- 本地用户基于云的邮箱仅用于存储 Teams 聊天数据。 本地用户不能以任何方式登录或访问基于云的邮箱。 它不能用于发送或接收电子邮件。 

- 你必须向 Microsoft 支持人员提交请求，以使贵组织能够在本地用户基于云的邮箱中搜索 Teams 聊天数据。 请参阅本文中的[向 Microsoft 支持人员提交启用此功能的请求](#filing-a-request-with-microsoft-support-to-enable-this-feature)部分。 

> [!NOTE]
> Teams 频道对话始终存储在与 Teams 关联的基于云的邮箱中。 这意味着您可以使用内容搜索来搜索频道对话，而无需提交支持请求。 有关搜索 Teams 频道对话的详细信息，请参阅[搜索 Microsoft Teams 和 Microsoft 365 组](content-search.md#searching-microsoft-teams-and-microsoft-365-groups)。
  
## <a name="how-it-works"></a>工作原理

如果已启用 Microsoft Teams 的用户拥有本地邮箱，并且其用户帐户/标识已同步到云端，则 Microsoft 将创建基于云的邮箱来存储 1xN Teams 聊天数据。 将 Teams 聊天数据存储在基于云的邮箱中后，系统会将其编入索引以供搜索。 这让你能够使用内容搜索（以及与电子数据展示事例关联的搜索）来搜索、预览和导出本地用户的 Teams 聊天数据。 你还可以使用安全与合规中心 PowerShell 中的 **\*ComplianceSearch** cmdlet 来搜索本地用户的 Teams 聊天数据。 
  
下图显示了搜索、预览和导出本地用户的 Teams 聊天数据的工作流。
  
![Microsoft Teams 中的本地用户基于云的存储空间](../media/EHAMShard1.png)
  
除了此新功能之外，你仍可以使用内容搜索在基于云的 SharePoint 网站和与每个 Microsoft Team 关联的 Exchange 邮箱中搜索、预览和导出 Teams 内容，以及在基于云的用户的 Exchange Online 邮箱中搜索、预览和导出 1xN Teams 聊天数据。

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a>向 Microsoft 支持人员提交启用此功能的请求

你必须向 Microsoft 支持人员提交请求，以使贵组织能够使用安全与合规中心中的图形用户界面来搜索本地用户基于云的邮箱中的 Teams 聊天数据。 此功能在安全与合规中心 PowerShell 中提供。 无需提交支持请求即可使用 PowerShell 来搜索本地用户的 Teams 聊天数据。
  
向 Microsoft 支持人员提交请求时，请包含以下信息：
  
- 组织的默认域名。

- 组织的租户名称和租户 ID。 可在 Azure Active Directory 门户中找到这些信息（位于“**管理**”\>“**属性**下）。 请参阅[查找 Microsoft 365 租户 ID](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)。

- 可在支持请求中使用以下标题或说明：“为本地用户启用应用程序内容搜索”。 这有助于将请求传送到将实现请求的电子数据展示工程团队。

执行工程更改后，Microsoft 支持人员将向你发送预计的部署日期。 在提交支持请求后，部署过程通常需要 2 到 3 周的时间。
  
### <a name="what-happens-after-this-feature-is-enabled"></a>启用此功能后会发生什么情况？

在组织中部署此功能后，将在安全与合规中心中的内容搜索以及与电子数据展示事例关联的搜索中进行以下更改：
  
- 在内容搜索的“**位置**”下方添加“**为本地用户添加 Office 应用内容**”复选框。

    ![向内容搜索 UI 添加“为本地用户添加 Office 应用内容”复选框](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- 本地用户显示在内容位置选取器中，你可以使用它选择要搜索的用户邮箱。

## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>搜索本地用户基于云的邮箱中的 Teams 聊天内容

启用此功能后，可使用安全与合规中心中的内容搜索来搜索本地用户基于云的邮箱中的 Teams 聊天数据。
  
1. 在安全与合规中心，转到“**搜索**”\>“**内容搜索**”

2. 在“**搜索**”页面上，单击“![添加”图标](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif)“**新建搜索**”。

    如前文所述，“**为本地用户添加 Office 应用内容**”复选框显示在“**位置**”下方。 它在默认情况下处于选中状态。

3. 创建关键字查询并为搜索查询添加条件（如有必要）。 若要仅搜索 Teams 聊天数据，可在“**关键字**”框中添加以下查询：

    ```text
    kind:im
    ```

4. 目前，可在“**位置**”下选择以下选项之一：

    - **所有位置**：选择此选项可搜索组织中所有用户的邮箱。 选中该复选框时，还将搜索本地用户的所有基于云的邮箱。

    - **特定位置**：选择此选项，然后单击“**修改**”\> 选择用户、组或团队以搜索特定邮箱。 如前文所述，位置选取器可用于搜索本地用户。

5. 保存并运行搜索。 可像预览任何其他搜索结果一样预览本地用户基于云的邮箱中的任何搜索结果。 你还可以将搜索结果（包括任何 Teams 聊天数据）导出到 PST 文件。 有关详细信息，请参阅： 

    - [创建搜索](content-search.md#create-a-search)

    - [预览搜索结果](content-search.md#preview-search-results)

    - [导出内容搜索结果](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>使用 PowerShell 搜索本地用户基于云的邮箱中的 Teams 聊天数据

你可以使用安全与合规中心 PowerShell 中的 **New-ComplianceSearch** 和 **Set-ComplianceSearch** cmdlet 来搜索本地用户基于云的邮箱。 如前文所述，无需提交支持请求即可使用 PowerShell 来搜索本地用户的 Teams 聊天数据。 
  
1. [连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

2. 运行以下 PowerShell 命令以创建用于搜索本地用户基于云的邮箱的内容搜索。

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    *IncludeUserAppContent* 参数用于为由 *ExchangeLocation* 参数指定的一个或多个用户指定基于云的邮箱。 *AllowNotFoundExchangeLocationsEnabled* 允许本地用户使用基于云的邮箱。 使用此参数的 `$true` 值时，搜索不会在运行之前尝试验证邮箱是否存在。 这是搜索本地用户基于云的邮箱所必需的，因为这些类型的邮箱无法解析为常规邮箱。

    以下示例在 Sara Davis 基于云的邮箱中搜索包含关键字“redstone”的 Teams 聊天（它们是即时消息），Sara Davis 是 Contoso 组织内的本地用户。
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   创建搜索后，请务必使用 **Start-ComplianceSearch** cmdlet 运行搜索。 
  
有关使用这些 cmdlet 的详细信息，请参阅：
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/set-compliancesearch)

- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>已知问题

- 目前，你可以在本地用户基于云的邮箱中搜索、预览和导出内容。 你还可以将本地用户基于云的邮箱置于与电子数据展示事例关联的保留中，并将 Teams 聊天或频道消息的保留策略应用于本地用户基于云的邮箱。 但是，目前无法将其他内容位置（如 Exchange 邮箱和 SharePoint 网站）的保留策略应用于本地用户基于云的邮箱。

## <a name="frequently-asked-questions"></a>常见问题

 **本地用户基于云的邮箱位于何处？**
  
基于云的邮箱是在与组织相同的数据中心中创建并存储的。
  
 **除了提交支持请求以外，还有其他要求吗？**
  
 如前文所述，必须将具有本地邮箱的用户标识同步到基于云的组织，以便为 Office 365 中的每个本地用户帐户创建对应的邮件用户帐户。 你的组织还必须具有 Office 365 企业版订阅，例如 Office 365 企业版 E1、E3 或 E5 订阅。
  
 **如果将用户的本地邮箱迁移到云，是否有丢失 Teams 聊天数据的风险？**
  
否。 将本地用户的主邮箱迁移到云后，该用户的 Teams 聊天数据将迁移到其基于云的新主邮箱中。
  
 **是否可以为本地用户应用电子数据展示保留或保留策略？**
  
可以。 你可以将 Team 聊天和频道消息的电子数据展示保留或保留策略应用于本地用户基于云的邮箱。
  
 **在组织提交启用此功能的请求之前，内容搜索是否可以找到本地用户较早的 Teams 聊天？**
  
Microsoft 从 2018 年 1 月 31 日开始存储本地用户的 Teams 聊天数据。 因此，如果自此日期以来在 Active Directory 和 Azure Active Directory 之间同步了本地 Teams 用户的标识，则他们的 Teams 聊天数据存储在基于云的邮箱中，并且可使用内容搜索进行搜索。 此外，Microsoft 正致力于将 2018 年 1 月 31 日之前的 Teams 聊天数据存储在本地用户基于云的邮箱中。 即将提供与此相关的详细信息。

 **本地用户是否需要许可证才能将 Teams 聊天数据存储在基于云的邮箱中？**
  
是。 若要将本地用户的 Teams 聊天数据存储在基于云的邮箱中，必须在 Office 365（或 Microsoft 365）中为该用户分配 Microsoft Teams 许可证和 Exchange Online 计划许可证。
