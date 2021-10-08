---
title: 在组织中搜索并删除电子邮件
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 使用 Microsoft 365 合规中心中的搜索和清除功能搜索和删除组织中所有邮箱的电子邮件。
ms.openlocfilehash: 33c65cb61be14d72631fd3a272b68f2dad2ffea6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60204223"
---
# <a name="search-for-and-delete-email-messages"></a>搜索和删除电子邮件

**本文适用于管理员。你是否尝试在邮箱中查找要删除的项目？请参阅 [使用“即时搜索”查找邮件或项目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**。

你可以使用内容搜索功能在组织的所有邮箱中搜索并删除电子邮件。这可以帮助你查找并删除可能有害或高风险的电子邮件，如：

- 包含危险附件或病毒的邮件

- 网络仿冒邮件

- 包含敏感数据的邮件

> [!CAUTION]
> 搜索和清除是一项强大的功能，允许分配有必要权限的任意用户从组织的邮箱中删除电子邮件。

## <a name="before-you-begin"></a>准备工作

- 本文中所述的搜索和清除工作流不会从 Microsoft Teams 中删除聊天消息或其他内容。 如果在步骤 2 中创建的内容搜索返回 Microsoft Teams 中的项目，则在清除步骤 3 中的项目时不会删除这些项目。

- 若要创建并运行内容搜索，你必须是 **电子数据展示管理员** 角色组的成员，或者在 Microsoft 365 合规中心被分配有“**合规性搜索**”角色。若要删除邮件，你必须是 **组织管理** 角色组的成员，或在合规中心被分配有“**搜索并清除**”角色。有关将用户添加到角色组的详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。

  > [!NOTE]
  > Exchange Online 和 Microsoft 365 安全与合规中心中都存在 **组织管理** 角色组。 这些角色组都是独立的角色组，授予不同的权限。 作为 Exchange Online 中 **组织管理** 的成员，并没有授予删除邮件的必要权限。 如果未向你分配安全与合规中心的 **搜索并清除** 角色（直接分配或通过 **组织管理** 等角色组分配），则当你运行 **New-ComplianceSearchAction** cmdlet 时，将在步骤 3 中收到错误消息“找不到与参数名称‘清除’相匹配的参数”。

- 你必须使用安全与合规中心 PowerShell 删除邮件。 请参阅 [步骤 1](#step-1-connect-to-security--compliance-center-powershell) ，了解如何连接的说明。

- 每个邮箱一次最多可以删除 10 个项目。因为搜索和删除邮件的功能是用作事件响应工具，此限制有助于确保从邮箱中快速删除邮件。此功能并不是为了清理用户邮箱。

- 在内容搜索中，可通过搜索和清除操作删除其项目的最大邮箱数为 50,000。 如果搜索（在 [步骤 2](#step-2-create-a-content-search-to-find-the-message-to-delete) 中创建）到超过 50,000 个邮箱，则清除操作（在步骤 3 中创建）将失败。 如果将搜索配置为包括组织内的所有邮箱，则单次搜索中一般有可能搜索到超过 50,000 个邮箱。 即使包含匹配搜索查询项目的邮箱数量少于 50,000 个，这一限制仍然适用。 请参阅 [详细信息](#more-information) 部分，以获取关于使用搜索权限筛选器在超过 50,000 个邮箱中搜索和清除项目的指南。

- 本文中所述的步骤只能用于删除 Exchange Online 邮箱和公用文件夹中的项目。 无法将其用于删除 SharePoint 或 OneDrive for Business 网站中的内容。

- 使用本文中的程序，无法删除高级电子数据展示案例中的审阅集中的电子邮件项目。 这是因为审阅集中的项目存储在 Azure 存储位置，而不是实时服务中。 这意味着，这些内容无法通过在步骤 1 中创建的内容搜索返回。 若要删除某个审阅集中的项目，必须删除包含该审阅集的高级电子数据展示案例。 有关详细信息，请参阅[关闭或删除高级电子数据展示案例](close-or-delete-case.md)。

## <a name="step-1-connect-to-security--compliance-center-powershell"></a>步骤 1：连接到安全与合规中心 PowerShell

第一步是为组织连接到安全与合规中心 PowerShell。 有关分步说明，请参阅[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

## <a name="step-2-create-a-content-search-to-find-the-message-to-delete"></a>步骤 2：创建内容搜索以查找要删除的邮件

第二步是创建并运行内容搜索以查找想要从组织的邮箱中删除的邮件。你可以通过使用 Microsoft 365 合规中心或在安全与合规 PowerShell 中运行 **New-ComplianceSearch** 和 **Start-ComplianceSearch** cmdlets 来创建搜索。与此搜索的查询匹配的邮件将通过在 [步骤 3](#step-3-delete-the-message) 中运行 **New-ComplianceSearchAction -Purge** 命令进行删除。有关创建内容搜索和配置搜索查询的详细信息，请参阅下列主题：

- [Office 365 中的内容搜索](content-search.md)

- [内容搜索的关键字查询](keyword-queries-and-search-conditions.md)

- [New-ComplianceSearch](/powershell/module/exchange/New-ComplianceSearch)

- [Start-ComplianceSearch](/powershell/module/exchange/Start-ComplianceSearch)

> [!NOTE]
> 在此步骤中创建的内容搜索中搜索的内容位置不能包含 SharePoint 或 OneDrive for Business 网站。 只能在内容搜索中包含将用于电子邮件的邮箱和公用文件夹。 如果内容搜索包含网站，则在运行 **New-ComplianceSearchAction** cmdlet 时，你将在步骤 3 中收到错误消息。

### <a name="tips-for-finding-messages-to-remove"></a>查找要删除的邮件的提示

搜索查询的目标是将搜索结果的范围缩小到仅包含您想要删除的邮件。以下是一些提示：

- 如果你知道邮件的主题行中使用的确切文本或短语，请在搜索查询中使用 **主题** 属性。

- 如果你知道邮件的确切日期（或日期范围），请搜索查询中包括 **接收日期** 属性。

- 如果你知道邮件的发件人，请在搜索查询中包括 **收件人** 属性。

- 预览搜索结果以验证搜索是否仅返回你想要删除的邮件。

- 使用搜索估计统计信息（显示在 Microsoft 365 合规中心的搜索细节窗格中，或使用 [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch) cmdlet）以获得结果总数。

以下是查找可疑电子邮件的两个查询示例。

- 此查询返回用户在 2016 年 4 月 13 日至 2016 年 4 月 14 日之间收到的邮件，而且包含主题行中的单词“操作”和“必需”。

  ```powershell
  (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
  ```

- 此查询返回由 chatsuwloginsset12345@outlook.com 发送的邮件，而且包含主题行中的完全匹配的短语“更新您的帐户信息”。

  ```powershell
  (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
  ```

下面是使用查询创建和开始搜索的示例，方法是运行 **New-ComplianceSearch** 和 **Start-ComplianceSearch** cmdlet 来搜索组织中的所有邮箱：

```powershell
$Search=New-ComplianceSearch -Name "Remove Phishing Message" -ExchangeLocation All -ContentMatchQuery '(Received:4/13/2016..4/14/2016) AND (Subject:"Action required")'
Start-ComplianceSearch -Identity $Search.Identity
```

## <a name="step-3-delete-the-message"></a>步骤 3：删除邮件

创建并优化内容搜索以返回要删除的邮件后，最后一步是运行安全与合规中心 PowerShell 内的 **New-ComplianceSearchAction -Purge** 命令来删除邮件。 可对邮件进行软删除或硬删除。 软删除的邮件将移至用户的“可恢复的项目”文件夹并保留，直到已删除项目的保留期到期。 硬删除的邮件被标记为从邮箱中永久删除，并在托管文件夹助理下次处理邮箱时永久删除。 如果为邮箱启用了单个项目恢复，则在已删除项目的保留期到期后，将永久删除硬删除的项目。 如果邮箱处于保留状态，则会保留已删除的邮件，直到该项目的保留期到期或从邮箱中删除保留为止。

> [!NOTE]
> 如前所述，运行 **New-ComplianceSearchAction -Purge** 命令时，不会删除内容搜索返回的 Microsoft Teams 中的项。

要运行以下命令来删除邮件，请确保你已 [连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

### <a name="soft-delete-messages"></a>软删除邮件

在以下示例中，该命令软删除名为“删除网络钓鱼邮件”由内容搜索返回的搜索结果。

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

### <a name="hard-delete-messages"></a>硬删除邮件

要硬删除由“删除网络钓鱼邮件”内容搜索返回的项目，需要运行以下命令：

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

当你运行之前的命令以软删除或硬删除邮件时，由 *SearchName* 参数指定的搜索就是你在步骤 1 中创建的内容搜索。

有关详细信息，请参阅 [New-ComplianceSearchAction](/powershell/module/exchange/New-ComplianceSearchAction)。

## <a name="more-information"></a>详细信息

- **如何获取有关搜索和删除操作的状态？**

  运行 **Get-ComplianceSearchAction** 以获取删除操作的状态。运行 **New-ComplianceSearchAction** cmdlet 时创建的对象将使用以下格式命名：`<name of Content Search>_Purge`。

- **删除邮件后会发生什么情况？**

  使用 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` 命令删除的邮件将移至“清除”文件夹，用户无法访问这些邮件。 将邮件移至“清除”文件夹后，如果为邮箱启用了单个项目恢复，则会在已删除的邮件保留期内保留邮件。 （在 Microsoft 365 中，创建新邮箱时将默认启用单个项目恢复。）已删除项目的保留期到期后，邮件将标记为永久删除，并在托管文件夹助手下次处理邮箱时从 Microsoft 365 中清除。

  如果使用 `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` 命令，则邮件将移动到用户的"可恢复邮件"文件夹中的"删除"文件夹。它不会立即从 Microsoft 365 中清除。在为邮箱配置的已删除邮件保留期内，用户可以恢复“已删除邮件”文件夹中的邮件。此保留期过期（或如果用户在过期之前清除邮件）后，邮件将移动到“清除”文件夹，用户无法再访问该邮件。进入“清除”文件夹后，如果启用了邮箱的单个邮件恢复，则邮件将在邮箱配置的已删除邮件保留期内继续保留。（在 Microsoft 365 中，创建新邮箱时会默认启用单个邮件恢复。）已删除邮件保留期到期后，邮件将被标记为永久删除，并将在下次托管文件夹助理处理邮箱时从 Microsoft 365 中清除。

- **如果必须删除超过 50,000 个邮箱中的邮件，该怎么办？**

  如前文所述，可以对最多 50,000 个邮箱执行搜索和清除操作（即使包含匹配搜索查询项目的邮箱数量少于 50,000）。 如果必须对超过 50,000 个邮箱执行搜索和清除操作，请考虑创建临时搜索权限筛选器，这会将要搜索的邮箱数减少到不超过 50,000 个。 例如，如果你的组织包含不同部门、州或国家/地区的邮箱，则可以基于其中一个邮箱属性创建邮箱搜索权限筛选器，以搜索组织内的邮箱子集。 创建搜索权限筛选器后，将创建搜索（如步骤 1 中所述），然后删除邮件（如步骤 3 中所述）。 然后，你可以编辑筛选器以搜索和清除不同邮箱集中的邮件。 有关创建搜索权限筛选器的详细信息，请参阅[配置内容搜索的权限筛选](permissions-filtering-for-content-search.md)。

- **是否会删除搜索结果中包含的未编制索引的项目？**

  不会，New-ComplianceSearchAction -Purge 命令不会删除未编制索引的项目。

- **如果从处于就地保留或诉讼保留状态的邮箱中删除邮件或为邮件分配 Microsoft 365 保留策略，会发生什么情况？**

  清除邮件并将其移动到 Purges 文件夹后，邮件将一直保留到保留持续时间过期。如果保留持续时间不受限制，则将保留项目，直到删除保留或更改保留持续时间。

- **为什么在不同的安全与合规中心角色组之间划分搜索和删除工作流？**

  如前所述，必须是电子数据展示管理员角色组的成员或者分配有合规性搜索管理角色的用户才能搜索邮箱。若要删除邮件，必须是组织管理角色组的成员，或分配有“搜索并清除”管理角色。这就使得可以控制哪些人可以搜索组织中的邮箱以及哪些人可以删除邮件。
