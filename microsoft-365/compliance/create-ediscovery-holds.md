---
title: 在核心电子数据展示案例中创建电子数据展示保留
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
description: 可以创建与核心电子数据展示案例关联的保留，以保留与调查相关的内容。
ms.openlocfilehash: 76ea455af0a7600cd901bdcdaeb0e4b15ef9bc43
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988146"
---
# <a name="create-an-ediscovery-hold"></a>创建电子数据展示保留

可以使用核心电子数据展示案例创建保留，以保留可能与案例相关的内容。 你可以将正在调查的用户的 Exchange 邮箱和 OneDrive for Business 帐户置于保留状态。 还可以将与 Microsoft Teams、Office 365 组和 Yammer 组关联的邮箱和网站置于保留状态。 当您将内容位置放在保留状态时，内容将一直保留，直到您从内容位置删除保留，或者一直保留到您删除保留。

创建电子数据展示保留后，保留最多可能需要 24 小时才能生效。 

创建保留时，可以使用以下选项来设置指定内容位置中保留的内容的范围：
  
- 创建一个无限保留，其中指定位置中所有内容都置于保留状态。 或者，您可以创建基于查询的保留，其中仅将与搜索查询匹配的指定位置中的内容置于保留状态。

- 可以指定一个日期范围，以仅保留该日期范围内发送、接收或创建的内容。 或者，您可以将所有内容保留到指定位置，而不管内容是何时发送、接收还是创建的。
  
## <a name="how-to-create-an-ediscovery-hold"></a>如何创建电子数据展示保留

创建与核心电子数据展示案例关联的电子数据展示保留：
  
1. 转到已分配有相应电子数据展示权限的用户帐户的凭据 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并登录。

2. 在 Microsoft 365 合规中心的左侧导航窗格中，单击"全部显示"，然后单击"电子数据展示>**核心。**

3. 在 **核心电子数据展示** 页面上，选择要创建保留的大小写，然后单击"**打开案例"。**

4. 在 **案例** 的主页上，单击"保留 **"** 选项卡。
  
5. 在"**保留"** 页上，单击"**创建"。**

6. 在"**命名保留向导**"页上，为保留命名并添加可选说明，然后单击"下一 **步"。** 保留名称在你的组织中必须保持唯一。

7. 在 **"内容位置"** 页上，选择要保留的内容位置。 可以将邮箱、网站和公用文件夹置于保留状态。

    ![选择将其置于保留状态的内容位置](../media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   1. **邮箱位置** - 单击 **"** 选择用户、组或团队"，然后再次单击"选择用户、组或 **团队** "以指定要置于保留中的邮箱。 使用搜索框查找用户邮箱和通讯 (以将要置于保留状态) 的组成员的邮箱置于保留状态。 还可以将 Microsoft Team、Office 365 组或 Yammer 组的关联邮箱置于保留状态。 选中用户、组、团队复选框，单击 **"选择**"，然后单击"**完成"。**

   1. **网站位置** - 单击 **"选择网站"，** 然后 **再次单击"** 选择网站"以指定要保留的 SharePoint 和 OneDrive 帐户。 键入要保留的每个网站的 URL。 还可以为 Microsoft Team、Office 365 组或 Yammer 组添加 SharePoint 网站的 URL。 单击 **"** 选择"，然后单击"**完成"。**
  
   1. **Exchange 公用文件夹。** 将切换开关切换控件移到"所有"位置以将 Exchange Online 组织的所有公用文件夹 ![ ](../media/scc-toggle-on.png) 置于保留状态。  无法选择要置于保留状态的特定公用文件夹。 如果你不希望将公用文件夹置于保留状态，将切换开关设置为"无"。

   > [!NOTE]
   > 您必须向保留项中添加至少一个内容位置。 否则，电子数据展示保留静态将显示没有项目被保留。

8. 完成向保留添加内容位置后，单击"下一 **步"。**

9. 若要创建具有条件的基于查询的保留，请完成以下操作。 否则，若要保留指定内容位置中所有的内容，请单击"下一 **步"。**

    ![创建具有条件的基于查询的保留](../media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    1. 在" **关键字"** 下的框中，键入搜索查询，以便仅保留满足搜索条件的内容。 可以指定关键字、电子邮件属性或文档属性，如文件名。 您还可以使用使用布尔运算符的更复杂的查询，如 **AND** **、OR** 或 **NOT。**

    1. 单击 **"添加** 条件"可添加一个或多个条件以缩小保留的搜索查询范围。 每个条件都会向 KQL 搜索查询添加一个子句，该查询在您创建保留时创建并运行。 例如，您可以指定日期范围，以便保留在日期范围内创建的电子邮件或网站文档。 条件在逻辑上连接到关键字查询 (AND 运算符指定的 **关键字) 框中****指定。** 这意味着项必须满足关键字查询和要保留的条件。

    有关创建搜索查询和使用条件的信息，请参阅内容搜索的关键字查询 [和搜索条件](keyword-queries-and-search-conditions.md)。

10. 配置基于查询的保留后，单击"下一 **步"。**

11. 查看设置 (并在必要时编辑) ，然后单击"创建 **此保留"。**

## <a name="query-based-holds-placed-on-site-documents"></a>对网站文档进行基于查询的保留

对 SharePoint 网站中的文档进行基于查询电子数据展示的保留时，请记住以下事项：

- 基于查询的保留最初会保留网站中所有文档删除后的一小段时间。 这意味着在删除文档时，即使文档与基于查询的保留条件不匹配，文档也将移动到保留库。 但是，处理保留库的计时器作业将删除与基于查询的保留不匹配的已删除文档。 计时器作业定期运行，并将保留库中的所有文档与基于查询电子数据展示的保留项 (其他类型的保留和保留策略) 。 计时器作业将删除与基于查询的保留不匹配的文档，并保留这些文档。

- 基于查询的保留不应用于执行目标保留，如将文档保留到特定文件夹或网站中，或者通过使用其他基于位置的保留条件。 这样做可能会产生意外结果。 我们建议使用非基于位置的保留条件（如关键字、日期范围或其他文档属性）来保留网站文档。

## <a name="ediscovery-hold-statistics"></a>电子数据展示保留统计信息

创建电子数据展示保留后，有关新保留的信息将显示在所选保留的飞出页上。 此信息包括处于保留状态邮箱和网站的数量以及有关已置于保留状态的内容的统计信息，例如置于保留状态的项目总数和大小以及上次计算保留统计信息的时间。 这些保留统计信息可帮助您确定与案例相关的保留内容量。
  
![保留统计信息](../media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
请记住以下有关电子数据展示保留统计信息的事项：
  
- 保留项总数指示置于保留状态的所有内容源中的项目数。 如果已创建基于查询的保留，则此统计信息指示与查询匹配的项数。

- 保留的项目数还包括在内容位置找到的未索引项目。 如果创建基于查询的保留，则内容位置中所有未建立索引的项目将置于保留状态。 这包括与基于查询的保留的搜索条件不匹配的未索引项，以及可能超出日期范围条件的未索引项。 这不同于运行搜索时发生的情况，即搜索结果中不包含与搜索查询不匹配或由日期范围条件排除的未索引项目。 有关未编制索引的项目详细信息，请参阅部分 [索引项](partially-indexed-items-in-content-search.md)。

- 可以通过单击"更新统计信息"重新运行计算当前保留项目数的搜索估计，获取最新的保留统计信息。

- 由于邮箱或网站置于保留状态的用户通常会在 SharePoint 和 OneDrive 中发送或接收新电子邮件，并创建新文档，因此保留项目数会随着时间的推移而增加，这是正常的。

- 如果将 Exchange 邮箱、SharePoint 站点或 OneDrive 帐户移动到多地理位置环境中的不同区域，则保留统计信息中不会包含该网站的统计信息。 但是，这些位置中的内容仍将保留。 此外，如果将邮箱或网站移动到其他区域，则保留项中显示的 SMTP 地址或 URL 将不会自动更新。 您必须编辑保留项并更新 URL 或 SMTP 地址，以便内容位置再次包含在保留统计信息中

## <a name="search-locations-on-ediscovery-hold"></a>电子数据展示保留上的搜索位置

在 [核心电子](search-for-content-in-core-ediscovery.md) 数据展示案例中搜索内容时，您可以快速配置搜索，以仅搜索已置于与该案例关联的保留的内容位置。

![保留位置](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)

选择 **"保留位置** "选项以搜索已置于保留状态的所有内容位置。 如果案例包含多个电子数据展示保留，则选择此选项时将搜索所有保留的内容位置。 此外，如果将内容位置置于基于查询的保留中，则在您运行搜索时，将仅搜索与保留查询匹配的项。 换句话说，只有与保留条件与搜索条件匹配的内容与搜索结果一起返回。 例如，如果将用户置于基于查询的保留案例，以保留特定日期之前发送或创建的项，则只会搜索这些项目。 这是通过通过 AND 运算符连接案例保留查询 **和搜索查询** 完成的。

以下是在搜索电子数据展示保留上的位置时需要记住的其他一些内容：

- 如果内容位置是同一情况中多个保留项的一部分，则当您使用全部案例内容选项搜索该内容位置时，保留查询由 **OR** 运算符组合。 同样，如果内容位置是两个不同保留项的一部分，其中一个基于查询，另一个是一个无限保留 (其中所有内容都置于保留状态) ，则由于无限保留，所有内容都将被搜索。

- 如果将搜索配置为搜索保留位置，然后通过添加或删除位置或更改保留查询) 更改 (的情况下更改电子数据展示保留，则使用这些更改更新搜索配置。 但是，您必须在保留更改后重新运行搜索以更新搜索结果。

- 如果电子数据展示案例的单个位置上放置了多个电子数据展示保留，并且您选择搜索保留位置，则该搜索查询的最大关键字数为 500。 这是因为搜索使用 **OR** 运算符将所有基于查询的保留组合在一起。 如果组合保留查询和搜索查询中关键字超过 500 个，则搜索邮箱中所有内容，而不只是与基于查询的大小写匹配的内容。

- 如果电子数据展示保留的状态为"打开 **"，** 则仍可在打开保留时搜索处于保留状态的位置。

## <a name="preserve-content-in-microsoft-teams"></a>保留 Microsoft Teams 中的内容

属于 Microsoft Teams 频道的对话存储在与 Microsoft 团队关联的邮箱中。 同样，团队成员在渠道中共享的文件将存储在团队的 SharePoint 网站上。 因此，您必须将团队邮箱和 SharePoint 网站置于电子数据展示保留状态，才能在频道中保留对话和文件。

或者，作为 Teams 聊天列表一部分的对话 (称为 *1：1* 聊天或 *1：N* 群聊) 存储在参与聊天的用户的邮箱中。 用户在聊天对话中共享的文件存储在共享文件的用户的 OneDrive 帐户中。 因此，您必须将单个用户邮箱和 OneDrive 帐户添加到电子数据展示保留，以保留聊天列表中的对话和文件。 除了将团队邮箱和网站置于保留状态外，还建议将 Microsoft 团队成员的邮箱置于保留状态。

> [!IMPORTANT]
> 在基于云的组织中，参与 Teams 中聊天列表一部分的对话的用户必须具有 Exchange Online 邮箱，才能在邮箱置于电子数据展示保留时保留聊天对话。 这是因为属于聊天列表的对话存储在聊天参与者的基于云的邮箱中。 如果聊天参与者没有 Exchange Online 邮箱，将无法保留这些聊天对话。 例如，在 Exchange 混合部署中，具有本地邮箱的用户可能能够参与 Teams 中聊天列表的一部分的对话。 但在这种情况下，无法保留这些对话中的内容，因为这些用户没有可置于保留状态的基于云的邮箱。

有关保留 Teams 内容的信息，请参阅将[Microsoft Teams 用户或团队合法保留。](https://docs.microsoft.com/MicrosoftTeams/legal-hold)

### <a name="preserve-card-content"></a>保留卡片内容

同样，Teams 频道、1：1 聊天和 1：N 群聊中的应用生成的卡片内容存储在邮箱中，在将邮箱置于电子数据展示保留时将保留。 *卡片* 是包含简短内容的 UI 容器。 卡片可以有多个属性和附件，并且可以包含触发卡片操作按钮。 有关详细信息，[请参阅卡片。](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards) 与其他 Teams 内容一样，卡片内容的存储位置基于卡片的使用位置。 Teams 频道中使用的卡片内容存储在 Teams 组邮箱中。 1：1 和 1xN 聊天的卡片内容存储在聊天参与者的邮箱中。

### <a name="preserve-meeting-and-call-information"></a>保留会议信息和呼叫信息

Teams 频道中的会议和呼叫的摘要信息也存储在拨入会议或呼叫的用户的邮箱中。 在用户邮箱上设置电子数据展示保留时，也会保留此内容。

### <a name="preserve-content-in-private-channels"></a>保留私人频道中的内容

从 2020 年 2 月开始，我们还启用在私人频道中保留内容的能力。 由于私人频道聊天存储在聊天参与者的邮箱中，因此将用户邮箱置于电子数据展示保留将保留私人频道聊天。 此外，如果在 2020 年 2 月之前将用户邮箱置于电子数据展示保留中，则此保留现在将自动应用于存储在该邮箱中的私人频道邮件。 还支持保留私人频道中共享的文件。

### <a name="preserve-wiki-content"></a>保留 Wiki 内容

每个团队或团队频道还包含用于笔记记录与协作的 Wiki。 Wiki 内容将会自动保存至采用 .mht 格式的文件。 此文件存储在团队 SharePoint 网站的 Teams Wiki 数据文档库中。 您可以通过将团队的 SharePoint 网站添加到电子数据展示保留来保留 Wiki 内容。

> [!NOTE]
> 在 2017 年 6 月 22 日发布 (将团队的 SharePoint 网站保留时，可以保留团队或团队频道的 Wiki) 。 如果团队网站被保留，Wiki 内容将自该日期开始保留。 但是，如果工作组网站被保留，且 Wiki 内容在 2017 年 6 月 22 日之前被删除，则 Wiki 内容不会保留。

### <a name="office-365-groups"></a>Office 365 组

Teams 基于 Office 365 组构建。 因此，将 Office 365 组置于电子数据展示保留状态与将 Teams 内容置于保留状态类似。

将 Teams 和 Office 365 组置于电子数据展示保留时，请记住以下事项：

- 如前所述，若要将 Teams 和 Office 365 组中的内容置于保留状态，必须指定与组或团队关联的邮箱和 SharePoint 网站。

- 在 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中运行 **Get-UnifiedGroup** cmdlet 以查看 Teams 和 Office 365 组的属性。 这是获取与团队或 Office 365 组关联的网站的 URL 的一个好方法。 例如，以下命令显示名为高层领导团队的 Office 365 组的选定属性：

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > 若要运行 **Get-UnifiedGroup** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。 
  
- 搜索用户的邮箱时，不会搜索该用户是其中成员的任何团队或 Office 365 组。 同样，当您将团队或 Office 365 组置于电子数据展示保留中时，仅将组邮箱和组网站置于保留状态。 除非将组成员的邮箱和 OneDrive for Business 网站显式添加到电子数据展示保留中，否则不会将其置于保留状态。 因此，如果出于法律原因必须将团队或 Office 365 组置于保留状态，请考虑将团队或团队成员的邮箱和 OneDrive 帐户添加到同一保留状态。

- 若要获取团队或 Office 365 组的成员列表，可以在 Microsoft 365管理中心的"组"页上查看属性。 或者，可以在 Exchange Online PowerShell 中运行以下命令：

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > 若要运行 **Get-UnifiedGroupLinks** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。

## <a name="preserve-content-in-onedrive-accounts"></a>在 OneDrive 帐户内保留内容

若要收集组织中 OneDrive for Business 网站的 URL 列表，以便你可以将其添加到与电子数据展示案例关联的保留或搜索中，请参阅"创建组织中所有 [OneDrive](https://docs.microsoft.com/onedrive/list-onedrive-urls)位置的列表"。 本文中的脚本将创建一个文本文件，其中包含组织中所有 OneDrive 网站的列表。 若要运行此脚本，必须安装并使用 SharePoint Online Management Shell。 请务必将你组织的 MySite 域的 URL 附加到你想要搜索的每个 OneDrive 网站。 这是包含你所有的 OneDrive 的域；例如，`https://contoso-my.sharepoint.com`。 下面是用户的 OneDrive 网站的 URL 示例：`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。

> [!IMPORTANT]
> 用户的 OneDrive 帐户的 URL 包括其用户主体名称 (UPN)  (例如 `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ，) 。 在极少数情况下，更改了某个人的 UPN，其 OneDrive URL 也将更改以合并新的 UPN。 如果用户的 OneDrive 帐户是电子数据展示保留的一部分，旧帐户和 UPN 已更改，则需要更新保留，并且必须更新保留并添加用户的新 OneDrive URL 并删除旧 URL。 有关详细信息，请参阅 [UPN 更改如何影响 OneDrive URL](https://docs.microsoft.com/onedrive/upn-changes)。

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>从电子数据展示保留中删除内容位置

从电子数据展示保留中删除邮箱、SharePoint 站点或 OneDrive 帐户后，将 *应用延迟* 保留。 这意味着实际删除保留将延迟 30 天，以防止从内容位置 (数据) 数据。 这使管理员有机会搜索或恢复将在删除电子数据展示保留后清除的内容。 延迟保留对邮箱和网站的工作方式的详细信息有所不同。

- **邮箱：** 在托管文件夹助理下次处理邮箱并检测到已删除电子数据展示保留时，邮箱上将设置延迟保留。 具体来说，当托管文件夹助理将下列邮箱属性之一设置为 True 时，会向邮箱应用延迟 **保留**：

   - **DelayHoldApplied：** 此属性适用于用户邮箱 (Outlook 和 Outlook 网页) 生成的电子邮件相关内容。

   - **DelayReleaseHoldApplied：** 此属性适用于非 Outlook (（如 Microsoft Teams、Microsoft Forms 和 Microsoft Yammer) ，存储在用户邮箱中）生成的基于云的内容。 Microsoft 应用生成的云数据通常存储在用户邮箱的隐藏文件夹中。

   如果对邮箱 (设置了延迟保留，当以前的任一属性设置为 **True**) 时，该邮箱仍被视为处于无限期保留状态，就像邮箱处于诉讼保留一样。 30 天后，延迟保留过期，Microsoft 365 将自动尝试删除延迟保留 (，将 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 **False**) 以便删除该保留。 在将其中任一属性设置为 **False** 后，将在托管文件夹助理下次处理邮箱时清除标记为删除的相应项目。

   有关详细信息，请参阅[管理延迟保留的邮箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。

- **SharePoint 和 OneDrive 网站：** 从电子数据展示保留中删除网站后，保留库中保留的任何 SharePoint 或 OneDrive 内容不会在 30 天延迟保留期内删除。 这类似于从保留策略中释放网站时发生的情况。 此外，在 30 天延迟保留期间，无法手动删除保留库中的此内容。 

   有关详细信息，请参阅 [发布保留策略](retention.md#releasing-a-policy-for-retention)。

关闭核心电子数据展示案例时，还会将延迟保留应用于保留的内容位置，因为关闭案例时将关闭保留。 有关关闭案例详细信息，请参阅"关闭、重新打开和 [删除核心电子数据展示"案例](close-reopen-delete-core-ediscovery-cases.md)。

## <a name="ediscovery-hold-limits"></a>电子数据展示保留限制

下表列出了电子数据展示事例和事例保留的限制。

  | 限制说明 | 限制 |
  |:-----|:-----|
  |组织的最大事例数  <br/> |无限制  <br/> |
  |组织的最大电子数据展示保留数  <br/> |10,000  <br/> |
  |单个电子数据展示保留中的最大邮箱数  <br/> |1,000  <br/> |
  |单个电子数据展示保留中 SharePoint 和 OneDrive for Business 网站的最大数量  <br/> |100  <br/> |
  |电子数据展示主页上显示的最大事例数，以及事例中"保留、搜索"和"导出"选项卡上显示的最大项目数。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> 若要查看超过 1，000 个事例、保留、搜索或导出的列表，可以使用相应的 Office 365 安全与合规 PowerShell & cmdlet：
   >
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
