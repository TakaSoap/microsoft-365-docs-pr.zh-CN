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
description: 使用保留策略可以非常高效地控制用户使用电子邮件、文档和对话生成的内容。 保留所需内容并删除不需要的内容。
ms.openlocfilehash: b992452cffbe7fa2df5e7ad02726ca337fbe0f45
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816844"
---
# <a name="create-and-configure-retention-policies"></a>创建和配置保留策略

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

使用保留策略来主动决定是保留内容还是删除内容 — 亦或是先保留再删除内容。 

透过将相同的保留设置依照位置如网站或信箱层级的内容进行指派，保留策略可让你工作的更有效率。 如果你不确定是使用保留策略还是保留标签，请参阅[保留策略和保留标签](retention.md#retention-policies-and-retention-labels)。

有关保留策略和保留的工作方式的详细信息，请参阅[了解保留策略和保留标签](retention.md)。

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

2. 选择“**新保留策略**”来开始“创建保留策略向导”，并命名新的保留策略。

3. 在“**选择要应用策略的位置**” 页面上，选择 Teams 的一个或两个位置：“**Teams 频道消息**”和“**Teams 聊天**”。
     
    请注意，对于**Teams 频道消息**，将包括来自标准频道的消息，但不包括来自[专用频道](https://docs.microsoft.com/microsoftteams/private-channels)的消息。 保留策略目前不支持专用频道。
    
    默认情况下，[所有团队和所有用户](#a-policy-that-applies-to-entire-locations)会被选择，但你但是你可以通过选择[“**选择**”和“**排除**” 选项](#a-policy-with-specific-inclusions-or-exclusions)”来进行优化。

4. 有关**保留内容、删除内容，还是同时删除**向导的页面，请指定保留和删除内容的配置选项。
    
    你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。 有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。
    
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

2. 选择“**新保留策略**”来开始“创建保留策略向导”，并命名新的保留策略。

3. 在“**选择位置**”页面，切换打开或关闭除 Teams 位置之外的任何位置。 对于每个位置，可将其保持为默认的“[将策略应用到整个位置](#a-policy-that-applies-to-entire-locations)”，或者“[指定所包含的和所排除的](#a-policy-with-specific-inclusions-or-exclusions)”。 
    
    特定于位置的信息：
    - [交换电子邮件和交换公共文件夹](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [SharePoint 网站和 OneDrive 账户](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Office 365 组](#configuration-information-for-microsoft-365-groups)
    - [Skype for Business](#configuration-information-for-skype-for-business)

4. 有关**保留内容、删除内容，还是同时删除**向导的页面，请指定保留和删除内容的配置选项。
    
    你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。 有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。

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

如果在创建组时选择了某个团队网站或之后向该组添加了一个团队网站，则 Microsoft 365 组应用的保留策略将包括组邮箱和团队网站。 存储在团队网站中的文件与此位置有关，但 Teams 聊天或 Teams 频道与此位置无关，它们拥有自己的保留策略位置。

### <a name="configuration-information-for-skype-for-business"></a>Skype for Business 的配置信息

与 Exchange 电子邮件不同，将 Skype 位置的状态切换为“开”并不能添加所有用户，但启用相应位置后，就必须手动选择要保留哪些用户的对话：

![选择用于保留策略的 Skype 位置](../media/skype-location-retention-policies.png)
  
当你选择“**选择用户**”时，可通过选择“**全选**”框来快速包含所有用户。 但是，请务必了解每个用户在策略中都被算作一个特定的包含内容。 因此，如果通过选择“**全选**”框来包含 1000 名用户，则与手动选择要包含的 1000 名用户相同，这是 Skype for Business 所支持的最大上限。

请注意，Outlook 中的“**对话历史记录**”文件夹是一个与 Skype 存档没有任何关系的功能。 最终用户可以关闭“**对话历史记录**”，但是 Skype 的存档功能是将 Skype 对话的副本存储到隐藏的文件夹。电子数据展示可以访问该文件夹，但用户不可以。

## <a name="settings-for-retaining-and-deleting-content"></a>保留和删除内容的设置

通过在保留策略中选择保留和删除内容的设置，保留策略将在指定的时间段内具有以下配置之一：

- 仅保留
    
    对于此配置，请选择“**将项目保留至特定时间段**”和“**保留期结束：不执行任何操作**”。 或者，选择“**永久保留项目**”。

- 保留后删除
    
    对于此配置，请选择“**将项目保留至特定时间段**”和“**保留期结束：自动删除项目**”。

- 仅删除
    
    对于此配置，请选择“**仅在达到特定年龄时删除项目”**。

### <a name="retaining-content-for-a-specific-period-of-time"></a>将内容保留一段特定时间

配置保留策略时，可选择将内容保留至特定天数、月数或年限。 或者，永久保留项目。

配置保留策略时，可选择无限期地保留内容，也可将内容保留特定天数、月数或年限。 保留期限是从内容创建的时间开始计算，而不是从应用保留策略的时间开始计算。 

对于保留期的开始，你还可以选择内容创建的时间，或者上次修改内容的时间（仅支持文件和 SharePoint、OneDrive 和 Office 365 位置）。

示例：
  
- SharePoint：如果希望将某个网站集中的项目自上次修改以来保留七年，并且该网站集中的某个文档在六年内未进行修改，则该文档在不修改的情况下将仅再保留 1 年。 如果再次对该文档进行编辑，则会根据最新修改日期计算文档期限，并将再保留 7 年。
  
- Exchange：如果想将邮箱中的项目保留七年，而有封邮件是六年前发送的，则该邮件将只再保留一年。 对于 Exchange 项目，期限基于传入电子邮件的接收日期或传出电子邮件的发送日期。 根据最后一次修改的时间来保留项目这一方式只适用于 OneDrive 和 SharePoint 中的网站内容。
  
保留期结束后，选择是否要永久删除内容：
  
![用于设置内容保留的页](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a>删除超过特定年限的内容

保留策略既可以先保留再删除项目，也可以不保留即删除旧项目。
  
在这两种情况下，如果保留策略删除项目，请务必了解为保留策略指定的时间期限是从项目创建或修改时开始计算，而不是从策略分配时开始计算。

因此首次分配保留策略前，尤其是当该策略会删除项目时，请先考虑现有内容的年龄，以及该策略对该内容有何影响。 在分配策略之前，你还需要与用户就新的策略进行沟通，以便其有时间评估可能的影响。

### <a name="a-policy-that-applies-to-entire-locations"></a>应用于位置整体的策略

选择位置时（Skype for Business 除外），当位置的状态是“**开启**”时，默认设置是“**全部**”。
  
如果将保留策略应用于整个位置的任意组合，则不会限制该策略可以包含的收件人、网站、帐户和组等数量。 

例如，如果对所有的 Exchange 电子邮件和所有的 SharePoint 网站应用策略，则无论网站和收件人的数量有多少，都会对其应用策略。 并且对于 Exchange，在应用策略后创建的任何新邮箱都将自动继承该策略。

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>包含或排除特定位置、用户或组的策略

你还可以将保留策略应用于特定用户、特定 Microsoft 365 组或特定网站。 若要执行此操作，请确保该位置的“**状态**”为“**开启**”，然后使用链接来包含或排除特定用户、Microsoft 365 组或者网站。 
  
但是，如果保留策略包含或排除的特定对象超过 1,000 个，则使用此配置会有一些限制：
  
- 保留策略的最大数量：
    - 1,000 个邮箱
    - 1,000 个 Microsoft 365 组
    - 1000 个用户的 Teams 私人聊天
    - 100 个网站（OneDrive 或 SharePoint）

租户支持的最大策略数：10,000。 这些项目包括保留策略、保留标签策略和自动应用保留策略。

如果你的保留策略可能受到这些限制，请选择适用于整个位置的配置选项。

> [!WARNING]
> 如果你配置了包含项，然后删除了最后一项，则配置会将位置的设置还原为“**所有**”。  保存策略之前，请确保这是你期望的配置。
> 
> 例如，如果你指定了一个 要在根据配置删除数据的保留策略中包含的 SharePoint 网站，然后删除了这个网站，那么默认情况下，所有 SharePoint 网站都将受到永久删除数据的保留策略的约束。 这同样适用于针对 Exchange 收件人、OneDrive 帐户和 Teams 聊天用户等进行包含设置。
> 
> 在这种情况下，如果不希望“**所有**”这一位置设置受制于保留策略，请关闭位置。 或者，指定将不受该策略约束的排除项。

## <a name="updating-retention-policies"></a>更新保留策略

如果你编辑保留策略，并且项目已遵循保留策略中的原始设置，则除了新识别的项目之外，更新后的设置将自动应用于此项目。

此更新通常非常快，但可能需要数天。 完成跨 Microsoft 365 位置的策略复制后，你将看到 Microsoft 365 合规中心中的保留策略状态从“**打开（挂起）**”变为“**打开（成功）**”。

## <a name="lock-a-retention-policy-by-using-powershell"></a>使用 PowerShell 锁定保留策略

如果需要使用“[保留锁定](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)”来满足法规要求，则必须使用 PowerShell。 由于管理员无法在应用保留锁定后禁用或删除保留策略，因此 UI 中不提供启用此功能，以防意外配置。

具有任何配置的所有保留策略均支持“保留锁定”。 但是，在使用以下 PowerShell 命令时，你会注意到 **Workload** 参数始终显示 **Exchange、SharePoint、OneDriveForBusines、Skype、ModernGroup**，而不是策略中配置的实际工作负载。 这只是显示问题。

1. [连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

2. 运行 [Get-RetentionCompliancePolicy](https://powershell/module/exchange/get-retentioncompliancepolicy)，列出保留策略并查找要锁定的策略的名称。 例如：
    
   ![PowerShell 中的保留策略列表](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. 若要对保留策略应用保留锁定，请运行带有保留策略名称的 [Set-RetentionCompliancePolicy]( ) cmdlet，并将 *RestrictiveRetention* 参数设置为 true：
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    例如：
    
    ![PowerShell 中的 RestrictiveRetention 参数](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     出现提示时，请阅读并通过输入**Y**确认这个配置随附的限制：
    
   ![用于确认你要在 PowerShell 中锁定保留策略的提示](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

现在，为保留策略提供了“保留锁定”功能。 若要确认，请再次运行 `Get-RetentionCompliancePolicy`，但指定保留策略名称并显示策略参数：

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

应看到 **RestrictiveRetention** 设置为 **True**。 例如：

![已在 PowerShell 中显示所有参数的锁定策略](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

