---
title: 创建和配置保留策略以自动保留或删除内容
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 使用保留策略，可主动决定是保留内容还是删除内容，亦或是先保留再删除内容；可将一个策略应用于整个组织，或应用于特定位置或用户；并能将策略应用于所有内容，或应用于满足特定条件的内容。
ms.openlocfilehash: 9974bebef9809647e7fb87f98f9d2f505baca4f3
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126503"
---
# <a name="create-and-configure-retention-policies"></a>创建和配置保留策略

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

使用保留策略来主动决定是保留内容还是删除内容 — 亦或是先保留再删除内容。 

透过将相同的保留设置依照位置如网站或信箱层级的内容进行指派，保留策略可让你工作的更有效率。 如果你不确定是使用保留策略还是保留标签，请参阅[保留策略和保留标签](retention.md#retention-policies-and-retention-labels)。

有关保留策略的保留工作方式的详细信息，请参阅[了解保留策略](retention.md)。

## <a name="before-you-begin"></a>准备工作

组织的全局管理员具有创建和编辑保留策略的完全权限。 如果你未以全局管理员的身份登录，请参阅[创建和管理保留策略和保留标签所需的权限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。

## <a name="create-and-configure-a-retention-policy"></a>创建和配置保留策略

虽然保留策略可支持多个位置，但你无法创建包含所有受支持位置的单个保留策略：
- Exchange 电子邮件
- SharePoint 网站
- OneDrive 帐户
- Microsoft 365 组
- Skype for Business
- Exchange 公用文件夹
- Teams 通道消息
- Teams 聊天

当您在创建保留策略时选择其中一个 Teams 位置时，其他位置将被自动排除。 因此，请依照你是否需要包含 Teams 地点来取决于要遵循的指示:

- [有关 Teams 位置的保留策略的说明](#retention-policy-for-teams-locations)
- [有关 Teams 以外位置的保留策略的说明](#retention-policy-for-locations-other-than-teams)

如果你有多个保留策略，但同时你又有使用保留标签，请参阅[保留原则或优先原则？](retention.md#the-principles-of-retention-or-what-takes-precedence)了解多个保留设置应用于同一内容时的结果。

### <a name="retention-policy-for-teams-locations"></a>Teams 位置的保留策略

1. 从 [Microsoft 365 合规中心](https://compliance.microsoft.com/)中，选择**策略** > **保留**。

2. 选择**新保留策略**创建新的保留策略。

3. 有关**保留内容、删除内容，还是同时删除**向导的页面，请指定保留和删除内容的配置选项。 
    
    你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。 有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。
    
    请勿选择 **使用高级保留设置** ，因为这并不支持 Teams 位置。 

4. 有关**选择位置**的页面，请选择**让我选择特定位置**。 然后切换 Teams 的一个或两个位置： **Teams 频道消息** 和 **Teams 聊天**。
     
    请注意，对于**Teams 频道消息**，将包括来自标准频道的消息，但不包括来自[专用频道](https://docs.microsoft.com/microsoftteams/private-channels)的消息。 保留策略目前不支持专用频道。
    
    默认情况下，所有团队都处于选中状态，但你可以通过指定要纳入的团队或团队来优化此设置。

5. 完成向导以保存设置。

有关 Teams 保留策略的详细信息，请参阅[Microsoft Teams 中的 保留策略](https://docs.microsoft.com/microsoftteams/retention-policies)来自 Teams 文档。

#### <a name="additional-retention-policy-needed-to-support-teams"></a>支持团队所需的其他保留策略

Teams 不只是聊天和频道消息。 如果你有从 Microsoft 365 组（以前称为 Office 365 组）创建的团队，则应另外使用 **Office 365 组**位置来配置包括该 Microsoft 365 组的保留策略。 此保留策略适用于组的邮箱、网站和文件中的内容。

如果你有团队网站未连接到 Microsoft 365 组，则需要一个包括 **SharePoint 网站**或 **OneDrive 帐户**位置的保留策略来保留和删除 Teams 中的文件：

- 聊天中共享的文件存储在共享文件的用户的 OneDrive 帐户中。 

- 上传到频道的文件存储在团队的 SharePoint 网站中。

> [!TIP]
> 当特定团队未连接到 Microsoft 365 组时，可以将保留策略应用于该特定团队的文件，方法是选择该团队的 SharePoint 网站以及该团队中用户的 OneDrive 帐户。

应用于 Microsoft 365 组、SharePoint 网站或 OneDrive 帐户的保留策略可能会先删除在 Teams 聊天或频道消息中引用的文件，然后再删除这些消息。 在这种情况下，该文件仍显示在 Teams 消息中，但当用户选择该文件时，将收到“找不到文件”错误。 此行为并非特定于保留策略，用户从 SharePoint 或 OneDrive 中手动删除文件时，也可能发生这种情况。


### <a name="retention-policy-for-locations-other-than-teams"></a>团队以外位置的保留策略

1. 从 [Microsoft 365 合规中心](https://compliance.microsoft.com/)中，选择**策略** > **保留**。

2. 选择**新保留策略**创建新的保留策略。

3. 有关**保留内容、删除内容，还是同时删除**向导的页面，请指定保留和删除内容的配置选项。 
    
    你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。 有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。
    
    然后，确定应将保留策略应用于所有内容还是满足特定条件的内容。 有关这些高级保留设置的详细信息，请参阅本页上的[用于识别满足特定条件的内容的高级设置](#advanced-settings-to-identify-content-that-meets-specific-conditions)。 

4. 对于“**选择位置**”页面，选择应将保留策略应用到组织中的所有受支持位置，还是想要指定位置。 如果选择特定位置，还可以指定包括和排除项。 
    
    有关在组织或特定位置的保留策略之间进行选择的详细信息，请参阅本页上的[将保留策略应用于整个组织或特定位置](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。
    
    特定于位置的信息：
    - [交换电子邮件和交换公共文件夹](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [SharePoint 网站和 OneDrive 账户](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Office 365 组](#configuration-information-for-microsoft-365-groups)
    - [Skype for Business](#configuration-information-for-skype-for-business)

5. 完成向导以保存设置。


#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a>Exchange 电子邮件和 Exchange 公用文件夹的配置信息

通过在邮箱级别应用保留设置，**Exchange 电子邮件**位置支持用户的电子邮件、日历和其他邮箱项的保留。

以下邮件项目包含在内：包含任何附件的邮件（包括草稿）、任务和日历项目（如果有结束日期）以及便签。 其中不包括不具备结束日期的任何联系人、任务和日历项目。 存储在邮箱中的其他项目（如 Skype 和 Teams 保存的消息）并不包含在其位置中。 这些项目有自己的保留位置。

即使 Microsoft 365 组有 Exchange 邮箱，涵盖整个 **Exchange 电子邮件**位置的保留策略也不会包含 Microsoft 365 组邮箱中的内容。 若要保留这些邮箱中的内容，请选择 **Office 365 组**的位置。

**Exchange 公用文件夹** 位置将保留设置应用于所有公共文件夹，并且不能在文件夹或邮箱级别应用。

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a>SharePoint 网站的配置信息和 OneDrive 帐户

选择 **SharePoint 网站**位置时，保留策略可以保留和删除在 SharePoint 通信网站的文件、未通过 Office 365 组连接的团队网站以及经典网站中的内容。 因为此选项不支持通过 Office 365 组连接的团队网站，所以请改用“**Office 365 组**”位置，该位置适用于该组的邮箱、站点和文件中的内容。

尽管保留策略应用于站点级别，但只有文档具有应用于其的保留设置。 保留设置不适用于站点内包括库、列表和文件夹的组织结构。 

如果为 SharePoint 网站或 OneDrive 账户指定位置，无需网站访问权限，且在**编辑位置**页上指定 URL 时不会进行任何验证。 不过，必须将 SharePoint 网站编入索引，系统会检查你指定的网站是否在向导结束时存在。

如果此检查失败，你会看到一条消息，指明无法验证你所输入的 URL，且只有在验证检查通过后，向导才会创建保留策略。 如果你看到此消息，请返回到向导，以更改 URL 或删除保留策略中的网站。

若要指定单个 OneDrive 帐户包含或排除的，URL 具有以下格式：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`

例如，对于 contoso 租户中用户名为“rsimone”的用户：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`

要验证租户的语法并标识用户的 URL，请参阅[获取组织中所有用户 OneDrive URL 的列表](https://docs.microsoft.com/onedrive/list-onedrive-urls)。

### <a name="configuration-information-for-microsoft-365-groups"></a>Microsoft 365 组的配置信息

若要保留或删除 Microsoft 365 组（以前称为 Office 365 组）的内容，请使用 **Office 365 组**位置。 即使 Microsoft 365 组有 Exchange 邮箱，涵盖整个 **Exchange 电子邮件**位置的保留策略也不会包含 Microsoft 365 组邮箱中的内容。 此外，尽管 **Exchange 电子邮件**位置最初允许你指定包括或排除组邮箱，但在尝试保存保留策略时，你将收到一条错误消息，表明“RemoteGroupMailbox”不是有效的 Exchange 位置选项。

应用于 Microsoft 365 组的保留策略包含组的邮箱和网站。 应用于 Microsoft 365 组的保留策略将保护由 Microsoft 365 组（包括 Microsoft Teams）创建的资源。

### <a name="configuration-information-for-skype-for-business"></a>Skype for Business 的配置信息

与 Exchange 电子邮件不同，将 Skype 位置的状态切换为“开”并不能添加所有用户，但启用相应位置后，就可以手动选择要保留哪些用户的对话：

![选择用于保留策略的 Skype 位置](../media/skype-location-retention-policies.png)
  
选择“选择用户”时，选择列标题中的“名称”**** 框可快速包含所有用户****。 但是，请务必了解每个用户在策略中都被算作一个特定的包含内容。 因此，当包括的用户超过 1,000 位时，会应用上一部分中所述的限制。 这里所说的选择所有 Skype 用户不同于组织范围的策略在默认情况下包含所有 Skype 用户。 
  
![用于选择 Skype 用户的页](../media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
请注意，Outlook 中的“对话历史记录”**** 文件夹是一项与 Skype 存档无关的功能。“对话历史记录”**** 可以由最终用户禁用，但 Skype 存档是通过将 Skype 对话副本存储在用户无法访问但电子数据展示可访问的隐藏文件夹中而完成。


## <a name="settings-for-retaining-and-deleting-content"></a>保留和删除内容的设置

通过在保留策略中选择保留和删除内容的设置，保留策略将在指定的时间段内具有以下配置之一：

- 仅保留
- 保留后删除
- 仅删除

### <a name="retaining-content-for-a-specific-period-of-time"></a>将内容保留一段特定时间

配置保留策略时，可选择无限期地保留内容，也可将内容保留特定天数、月数或年限。 内容的保留期限是从内容创建的时间开始计算，而不是从应用保留策略的时间开始计算。 可以选择根据内容创建的时间或（针对 OneDrive 和 SharePoint）最后一次修改内容的时间来计算保留期限。

示例：
  
- SharePoint：如果希望将某个网站集中的内容自上次修改以来保留七年，并且该网站集中的某个文档在六年内未进行修改，则该文档在不修改的情况下将仅再保留 1 年。 如果再次对该文档进行编辑，则会根据最新修改日期计算文档期限，并将再保留 7 年。
  
- Exchange：如果想将邮箱中的内容保留七年，而有封邮件是六年前发送的，则该邮件将只再保留一年。 对于 Exchange 内容，期限基于传入电子邮件的接收日期或传出电子邮件的发送日期。 根据最后一次修改的时间来保留内容这一方式只适用于 OneDrive 和 SharePoint 中的网站内容。
  
保留期结束后，选择是否要永久删除内容：
  
![用于设置内容保留的页](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a>删除超过特定年限的内容

保留策略既可以先保留再删除内容，也可以删除旧内容，而不保留它。
  
如果保留策略删除内容，请务必了解为保留策略指定的时间期限是从文件创建或修改时开始计算，而不是从策略分配时开始计算。
  
![内容删除设置](../media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
例如，假设创建了一个保留策略 - 该策略会在三年后删除内容，然后将该策略分配到所有 OneDrive 帐户，这些帐户中含有许多四五年前创建的内容。 在这种情况下，第一次分配保留策略后将会有许多内容被删除。 为此，请务必了解删除内容的保留策略会对内容造成重大影响。 
  
因此，首次将保留策略分配到网站集之前，应先考虑现有内容的年限，以及保留策略可能会对此内容产生的影响。我们还建议在分配策略前向用户传达新策略，让用户有时间评估策略可能会产生的影响。请注意，在创建保留策略前检查策略设置时会看到以下警告。
  
![内容删除警告](../media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-to-identify-content-that-meets-specific-conditions"></a>用于识别满足特定条件的内容的高级设置

保留策略可应用于其中所含位置上的全部内容，你也可以选择将保留策略只应用于包含特定关键字或[特定类型敏感信息](what-the-sensitive-information-types-look-for.md)的内容。
  
![高级保留选项](../media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="identify-content-that-contains-specific-keywords"></a>识别包含特定关键字的内容

可以只对满足特定条件的内容应用保留策略，然后只对这些内容执行保留操作。 可用的条件支持将保留策略应用于包含特定字词或短语的内容。 你可以使用 AND、OR 和 NOT 等搜索运算符优化查询。 有关这些运算符的详细信息，请参阅[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。
  
即将支持添加可搜索属性（例如，**subject:**）。
  
基于查询的保留策略使用搜索索引来标识内容。
  
![查询编辑器](../media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="identify-content-that-contains-sensitive-information"></a>识别包含敏感信息的内容

也可以只对包含[特定类型的敏感信息](what-the-sensitive-information-types-look-for.md)的内容应用保留策略。 例如，可以选择只对纳税人识别号、社会保障号或护照号等包含个人信息的内容应用独特的保留要求。
  
![用于选择敏感信息类型的页](../media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
注意：
  
- 敏感信息的高级保留设置不适用于 Exchange 公用文件夹或 Skype for Business，因为这些位置不支持敏感信息类型。
    
- Exchange Online 使用邮件流规则（也称为传输规则）来识别敏感信息，因此这种方式仅适用于传输过程中的邮件，而不适用于已存储在邮箱中的所有邮件。 对于 Exchange Online，这意味着保留策略可以识别敏感信息，并且只对邮箱应用策略**之后**收到的邮件执行保留操作。 上一部分所述的基于查询的保留不受此限制，因为它是通过使用搜索索引来识别内容的。 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a>将保留策略应用于整个组织或特定位置

可以将保留策略轻松地应用于整个组织、位置整体，或只应用于特定位置或用户。
  
### <a name="org-wide-policy"></a>组织范围策略

保留策略的最强大功能之一是，它可以应用于 Microsoft 365 中的所有位置，包括：
  
- Exchange 电子邮件
    
- SharePoint 网站集
    
- OneDrive 帐户
    
- Microsoft 365 组
    
- Exchange 公用文件夹
    

![用于选择所有位置的选项](../media/retention-policies-all-locations.png)

组织范围保留策略的其他重要功能包括：
  
- 策略可包含任意多个邮箱或网站。
    
- 对于 Exchange，在保留策略应用后新建的任何邮箱都会自动继承策略。
  
### <a name="a-policy-that-applies-to-entire-locations"></a>应用于位置整体的策略

选择位置时，可以轻松包含或排除整体位置，例如 Exchange 电子邮件或 OneDrive 帐户。 若要执行此操作，将该位置的“**状态**”切换为开或者关。 
  
与组织范围的策略相同，如果策略应用到任意组合的整体位置，则可应用策略的邮箱数或网站数不存在限制。 

例如，如果对所有的 Exchange 电子邮件和所有的 SharePoint 网站应用策略，则无论网站和邮箱的数量有多少，都会对其应用策略。 并且对于 Exchange，在应用策略后创建的任何新邮箱都将自动继承该策略。

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>包含或排除特定位置、用户或组的策略

你还可以将保留策略应用于特定用户、特定 Microsoft 365 组或特定网站。 若要执行此操作，请将该位置的“**状态**”切换为开，然后使用链接来包含或排除特定用户、Microsoft 365 组或者网站。 
  
但是，如果保留策略包括或排除的特定位置超过 1,000 个，则使用此配置会有一些限制：
  
- 保留策略的最大数量：
    - 1,000 个邮箱
    - 1,000 个 Microsoft 365 组
    - 1000 个用户的 Teams 私人聊天
    - 100 个网站（OneDrive 或 SharePoint）

租户支持的最大策略数：10,000。 这些项目包括保留策略、保留标签策略和自动应用保留策略。

如果你的保留策略可能受到这些限制，请选择适用于整个位置的配置选项，或使用组织范围的策略。

## <a name="updating-retention-policies"></a>更新保留策略

如果你编辑保留策略，并且内容已遵循保留策略中的原始设置，则除了新识别的内容之外，更新后的设置将自动应用于此内容。

此更新通常非常快，但可能需要数天。 完成跨 Microsoft 365 位置的策略复制后，你将看到 Microsoft 365 合规中心中的保留策略状态从“**打开（挂起）**”变为“**打开（成功）**”。

## <a name="lock-a-retention-policy-by-using-powershell"></a>使用 PowerShell 锁定保留策略

如果需要使用“[保留锁定](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)”来满足法规要求，则必须使用 PowerShell。

1. [连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

2. 运行 `Get-RetentionCompliancePolicy`，列出保留策略并查找要锁定的策略的名称。
    
   ![PowerShell 中的保留策略列表](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. 若要在保留策略上启用保留锁定，请运行 `Set-RetentionCompliancePolicy` 并将 `RestrictiveRetention` 参数设置为 true。 例如：

   ```powershell
   Set-RetentionCompliancePolicy -Identity "<Name of Policy>" – RestrictiveRetention $true
   ```
   
   ![PowerShell 中的 RestrictiveRetention 参数](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
   运行该 cmdlet 后，请选择“**全是**”：
    
   ![用于确认你要在 PowerShell 中锁定保留策略的提示](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

现在，为保留策略提供了“保留锁定”功能。 如果运行 `Get-RetentionCompliancePolicy`，则 `RestrictiveRetention` 参数将设置为 true。 例如：

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

![已在 PowerShell 中显示所有参数的锁定策略](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

