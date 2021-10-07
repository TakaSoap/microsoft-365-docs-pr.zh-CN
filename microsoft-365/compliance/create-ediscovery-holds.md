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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: 可以创建与核心电子数据展示案例相关联的保留，Microsoft 365调查或法律案件相关的内容。
ms.openlocfilehash: 0a5ac38afb649ab1972e7b7aee525dac9ab3b00e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195649"
---
# <a name="create-an-ediscovery-hold"></a>创建电子数据展示保留

可以使用核心电子数据展示案例创建保留，以保留与案例相关的内容。 你可以将正在调查Exchange邮箱OneDrive for Business帐户置于保留状态。 您还可以将与组、组和组关联的邮箱Microsoft Teams Office 365保留Yammer。 当您将内容位置保留时，内容将一直保留，直到您从保留中删除内容位置或删除保留。

创建电子数据展示保留后，保留最多可能需要 24 小时才能生效。

创建保留时，有以下选项可确定保留于指定内容位置的内容的范围：
  
- 创建一个无限期保留，其中指定位置中所有内容都置于保留状态。 或者，您可以创建基于查询的保留，其中仅将指定位置中与搜索查询匹配的内容置于保留状态。

- 指定一个日期范围，以仅保留在此日期范围内发送、接收或创建的内容。 或者，您可以将所有内容保留到指定位置，而不管内容何时发送、接收或创建。
  
## <a name="how-to-create-an-ediscovery-hold"></a>如何创建电子数据展示保留

创建与核心电子数据展示案例关联的电子数据展示保留：
  
1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心，</a>然后使用已分配有相应电子数据展示权限的用户帐户的凭据登录。

2. 在左侧导航窗格中，单击"全部 **显示**"，然后单击"**电子数据展示>核心"。**

3. 在 **"核心电子数据展示"** 页上，单击要创建保留的案例的名称。

4. 在案例 **的** 主页上，单击"保留 **"** 选项卡。
  
5. 在"**保留"页上**，单击"创建 **"。**

6. 在"**命名保留向导**"页上，为保留命名并添加可选说明，然后单击"下一步 **"。** 保留名称在你的组织中必须保持唯一。

7. 在 **"选择位置"** 向导页上，选择要保留的内容位置。 可以将邮箱、站点和公用文件夹置于保留状态。

    ![选择将其置于保留状态的内容位置。](../media/eDiscoveryHoldLocations.png)
  
   1. **Exchange 邮箱**：将切换设置为“**打开**”，然后单击“**选择用户、组或团队**”，以指定要置于保留状态的邮箱。 使用搜索框查找用户邮箱和通讯组（将组成员的邮箱置于保留状态）以置于保留状态。 还可以将 Microsoft 团队、组和组关联的邮箱Office 365保留Yammer邮箱。 有关将邮箱置于保留状态时保留的应用程序数据详细信息，请参阅存储在邮箱中用于 [电子数据展示的内容](what-is-stored-in-exo-mailbox.md)。

   2. **SharePoint 站点**：将切换设置为“**打开**”，然后单击“**选择站点** ”，以指定要置于保留状态的 SharePoint 站点和 OneDrive 帐户。 键入你想要置于保留状态的每个站点的 URL。 还可以为 Microsoft 团队、SharePoint 组或 Yammer 组添加 Office 365 URL。
  
   3. **Exchange 公用文件夹**：将切换设置为“**打开**”，从而把 Exchange Online 组织中的所有公用文件夹置于保留状态。 无法选择要置于保留状态的特定公用文件夹。 如果不想把公用文件夹置于保留状态，请让切换开关保持关闭。

   > [!NOTE]
   > 必须至少向保留项添加一个内容位置。 否则，电子数据展示保留统计信息将显示没有项目被保留。

8. 完成向保留添加位置后，单击"下一步 **"。**

9. 若要使用关键字或条件创建基于查询的保留，请完成以下步骤。 若要保留指定内容位置中所有的内容，请单击"下一 **步"。**

    ![使用关键字和条件创建基于查询的保留。](../media/eDiscoveryHoldQuery.png)
  
    1. 在" **关键字"下的** 框中，键入查询以仅保留与查询条件匹配的内容。 可以指定关键字、电子邮件属性或网站属性，如文件名。 您还可以使用更复杂的查询，这些查询使用布尔运算符，如 **AND** **、OR** 或 **NOT**。

    2. 单击 **"添加** 条件"可添加一个或多个条件以缩小对保留的查询范围。 每个条件向创建保留时创建和运行的 KQL 搜索查询添加一个子句。 例如，可以指定日期范围，以便保留在此日期范围内创建的电子邮件或网站文档。 条件在逻辑上连接到关键字查询 (AND 运算符) 关键字框中指定的 **关键字查询。** 这意味着项目必须满足关键字查询和要保留的条件。

    有关创建搜索查询和使用条件的信息，请参阅关键字 [查询和电子数据展示的搜索条件](keyword-queries-and-search-conditions.md)。

10. 配置基于查询的保留后，单击"下一 **步"。**

11. 查看你的设置 (并在必要时编辑) ，然后单击 **提交。**

## <a name="query-based-holds-placed-on-sites"></a>对网站进行基于查询的保留

在将基于查询电子数据展示的保留放在位于网站中的文档上时，请记住SharePoint事项：

- 基于查询的保留最初会保留网站中所有文档删除后的一小段时间。 这意味着在删除文档时，即使文档与基于查询的保留条件不匹配，文档也将移动到保留库。 但是，处理保留库的计时器作业将删除与基于查询的保留不匹配的已删除文档。 计时器作业定期运行，并将保留库中的所有文档与基于查询电子数据展示保留 (其他类型的保留和保留策略) 。 计时器作业将删除与基于查询的保留不匹配的文档，并保留执行这些操作的文档。

- 基于查询的保留不应用于执行目标保留，例如保留特定文件夹或网站中的文档，或通过使用其他基于位置的保留条件。 这样做可能会产生意外结果。 建议使用非基于位置的保留条件（如关键字、日期范围或其他文档属性）来保留网站文档。

## <a name="ediscovery-hold-statistics"></a>电子数据展示保留统计信息

创建电子数据展示保留后，有关新保留的信息将显示在所选保留的飞出页面上。 此信息包括邮箱数和处于保留状态的网站数，以及有关置于保留状态的内容的统计信息，例如置于保留状态的项目总数和大小以及上次计算保留统计信息的时间。 这些保留统计信息可帮助您确定要保留的与案例相关的内容量。
  
![保留统计信息。](../media/eDiscoveryHoldStatistics.png)
  
请牢记以下有关电子数据展示保留统计信息的事项：
  
- 保留项总数指示置于保留状态的所有内容源中的项目数。 如果已创建基于查询的保留，则此统计信息指示与查询匹配的项目数。

- 保留的项目数还包括在内容位置找到的未索引项目。 如果创建基于查询的保留，内容位置中所有未建立索引的项目将置于保留状态。 这包括不匹配基于查询的保留的搜索条件的未索引项和可能超出日期范围条件的未索引项。 这不同于运行搜索时发生的情况，即搜索结果中不包含与搜索查询不匹配或按日期范围条件排除的未索引项目。 有关未编制索引的项目详细信息，请参阅 [部分索引项](partially-indexed-items-in-content-search.md)。

- 可以通过单击"更新统计信息"重新运行计算当前保留项目数的搜索估计，获取最新的保留统计信息。

- 保留项目数会随着时间的推移而增加，这是正常的，因为其邮箱或网站置于保留状态的用户通常会在 SharePoint 和 OneDrive 中发送或接收新电子邮件和创建新文档。

- 如果Exchange邮箱、SharePoint 站点或 OneDrive 帐户移动到多地理位置环境中的不同区域，则保留统计信息中不会包含该网站的统计信息。 但仍保留这些位置中的内容。 此外，如果邮箱或网站移动到不同的区域，则保留项中显示的 SMTP 地址或 URL 将不会自动更新。 您必须编辑保留项并更新 URL 或 SMTP 地址，以便再次将内容位置包含在保留统计信息中

## <a name="search-locations-on-ediscovery-hold"></a>电子数据展示保留上的搜索位置

在 [核心电子](search-for-content-in-core-ediscovery.md) 数据展示案例中搜索内容时，您可以快速配置搜索，以仅搜索已置于与该案例关联的保留的内容位置。

选择 **"置于保留状态** 的位置"选项以搜索已置于保留状态的所有内容位置。 如果案例包含多个电子数据展示保留，则选择此选项时将搜索所有保留的内容位置。 此外，如果内容位置被置于基于查询的保留状态，则在您运行搜索时将仅搜索与保留查询匹配的项目。 换句话说，只有与保留条件与搜索条件匹配的内容与搜索结果一起返回。 例如，如果用户被置于基于查询的保留案例，并保留了特定日期之前发送或创建的项，则只会搜索这些项目。 这是通过 AND 运算符连接案例保留查询和搜索 **查询完成的。**

以下是在搜索电子数据展示保留上的位置时需要记住的其他一些内容：

- 如果内容位置是同一情况下多个保留项的一部分，则当您使用"所有案例内容"选项搜索该内容位置时，保留查询由 **OR** 运算符组合使用。 同样，如果内容位置是两个不同的保留项的一部分，其中一个基于查询，另一个是一个无限保留 (其中所有内容都置于保留状态) ，则由于无限保留，所有内容都是搜索。

- 如果将搜索配置为搜索保留位置，然后通过添加或删除位置或更改保留查询) 在 (中更改电子数据展示保留，则搜索配置将随这些更改一起更新。 但是，您必须在保留更改后重新运行搜索以更新搜索结果。

- 如果电子数据展示案例的单个位置上放置了多个电子数据展示保留，并且您选择搜索处于保留状态的位置，则该搜索查询的最大关键字数为 500。 这是因为搜索使用 **OR** 运算符将所有基于查询的保留项组合在一起。 如果组合保留查询和搜索查询中关键字超过 500 个，则搜索邮箱中所有内容，而不只是搜索与基于查询的大小写匹配的内容。

- 如果电子数据展示保留的状态为 On **(Pending) ，** 则仍可在打开保留时搜索保留位置。

## <a name="preserve-content-in-microsoft-teams"></a>保留内容Microsoft Teams

属于 microsoft Microsoft Teams对话存储在与 Microsoft 团队关联的邮箱中。 同样，团队成员在渠道中共享的文件将存储在团队的 SharePoint 网站上。 因此，您必须将团队邮箱和 SharePoint网站置于电子数据展示保留状态，以在频道中保留对话和文件。

或者，属于 Teams (中称为一对一聊天或 *一对* N群聊) 的对话将存储在参与聊天的用户的邮箱中。 用户在聊天对话中共享的文件存储在共享OneDrive的用户的用户帐户中。 因此，您必须将单个用户邮箱和OneDrive帐户添加到电子数据展示保留中，以保留聊天列表中的对话和文件。 除了将团队邮箱和网站置于保留状态之外，还建议将 Microsoft Team 成员的邮箱置于保留状态。

> [!NOTE]
> 如果您的组织具有 Exchange 混合部署 (或者您的组织将本地 Exchange 组织与 Office 365) 同步，并且已启用 Microsoft Teams，则本地用户可以使用 Teams 聊天应用程序并参与一对一聊天和一对 N 群聊。 这些对话存储在与本地用户关联的基于云的存储中。 如果将本地用户置于电子数据展示保留Teams，基于云的存储中的聊天内容将保留。 有关详细信息，请参阅 [搜索本地用户的 Teams 聊天数据](search-cloud-based-mailboxes-for-on-premises-users.md)。

有关保留内容Teams，请参阅将Microsoft Teams或团队合法[保留。](/MicrosoftTeams/legal-hold)

### <a name="preserve-card-content"></a>保留卡片内容

同样，Teams 频道、1：1 聊天和 1：N 群聊中的应用生成的卡片内容存储在邮箱中，在将邮箱置于电子数据展示保留时将保留。 *卡片* 是一个 UI 容器，用于存放内容短片。 卡片可以有多个属性和附件，还可以包括触发卡片操作按钮。 有关详细信息，请参阅 [卡片](/microsoftteams/platform/task-modules-and-cards/what-are-cards)。 和其他 Teams 内容一样，卡片内容的存储位置由卡片用在何处来确定。 用于 Teams 频道中的卡片内容存储在 Teams 组邮箱中。 一对一和一对多聊天的卡片内容存储在聊天参与者的邮箱中。

### <a name="preserve-meeting-and-call-information"></a>保留会议信息和呼叫信息

呼叫频道中的会议和呼叫的摘要Teams也存储在拨入会议或呼叫的用户的邮箱中。 在用户邮箱上设置电子数据展示保留时，也会保留此内容。

### <a name="preserve-content-in-private-channels"></a>保留私人频道中的内容

从 2020 年 2 月开始，我们还启用在私人频道中保留内容的能力。 由于私人频道聊天存储在聊天参与者的邮箱中，因此将用户邮箱置于电子数据展示保留将保留私人频道聊天。 此外，如果在 2020 年 2 月之前将用户邮箱置于电子数据展示保留状态，则此保留现在将自动应用于存储在该邮箱中的私人频道邮件。 还支持保留在私人频道中共享的文件。

### <a name="preserve-wiki-content"></a>保留 Wiki 内容

每个团队或团队频道还包含用于做笔记和进行协作的 Wiki。 Wiki 内容将会自动保存至采用 .mht 格式的文件。 此文件存储在团队 SharePoint 网站的 Teams Wiki 数据文档库中。 通过将团队的网站添加到电子数据展示保留，SharePoint Wiki 内容。

> [!NOTE]
> 在 2017 年 6 月 22 日 (将团队的 SharePoint 网站保留时，可以保留团队或团队频道) Wiki 内容。 如果团队网站保留，Wiki 内容将自该日期开始保留。 但是，如果团队网站在 2017 年 6 月 22 日之前被保留，且 Wiki 内容已删除，则 Wiki 内容不会保留。

### <a name="office-365-groups"></a>Office 365 组

Teams基于组Office 365构建。 因此，将Office 365组置于电子数据展示保留状态与将Teams置于保留状态类似。

在电子数据展示保留上同时Teams Office 365组时，请记住以下事项：

- 如前所述，若要将 Teams 和 Office 365 组的内容置于保留状态，您必须指定与组或SharePoint关联的邮箱和网站。

- 在 **PowerShell 中运行 Get-UnifiedGroup** cmdlet [Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)查看组Teams组Office 365属性。 这是获取与团队或组关联的网站的 URL Office 365方法。 例如，以下命令显示名为高层领导团队的 Office 365 组的选定属性：

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > 若要运行 **Get-UnifiedGroup** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。 
  
- 搜索用户的邮箱时，将不会搜索该用户Office 365组的任何团队或组。 同样，当您将团队或Office 365组置于电子数据展示保留中时，只会将组邮箱和组网站置于保留状态。 除非将OneDrive for Business添加到电子数据展示保留中，否则不会将其置于保留状态。 因此，如果出于法律原因Office 365团队或组，请考虑将团队或OneDrive成员的邮箱和帐户添加到同一保留中。

- 若要获取团队或 Office 365 组的成员列表，可以在"组"页上查看Microsoft 365 管理中心。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a> 或者，可以在 Exchange Online PowerShell 中运行以下命令：

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > 若要运行 **Get-UnifiedGroupLinks** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。

## <a name="preserve-content-in-onedrive-accounts"></a>保留帐户OneDrive内容

若要收集组织中 OneDrive for Business 网站的 URL 列表，以便可以将其添加到与电子数据展示案例关联的保留或搜索中，请参阅创建组织中所有 OneDrive 位置[的列表](/onedrive/list-onedrive-urls)。 本文中的脚本创建一个文本文件，其中包含组织中所有OneDrive列表。 若要运行此脚本，必须安装并使用 SharePoint Online Management Shell。 请务必将你组织的 MySite 域的 URL 附加到你想要搜索的每个 OneDrive 网站。 这是包含你所有的 OneDrive 的域；例如，`https://contoso-my.sharepoint.com`。 下面是用户的 OneDrive 网站的 URL 示例：`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。

> [!IMPORTANT]
> 用户的用户帐户的 URL OneDrive其用户主体名称 (UPN)  (例如 `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ，) 。 在极少数情况下，更改了某个人的 UPN，OneDrive URL 也会更改以合并新的 UPN。 如果用户的 OneDrive 帐户是电子数据展示保留的一部分，旧帐户和 UPN 已更改，则需要更新保留，并且必须更新保留并添加用户的新 OneDrive URL 并删除旧 URL。 有关详细信息，请参阅 [UPN 更改如何影响 OneDrive URL](/onedrive/upn-changes)。

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>从电子数据展示保留中删除内容位置

将邮箱、SharePoint站点或OneDrive从电子数据展示保留中删除后，将 *应用延迟* 保留。 这意味着保留的实际删除延迟 30 天，以防止数据被永久删除 (从内容) 清除。 这使管理员有机会搜索或恢复将在删除电子数据展示保留后清除的内容。 延迟保留对邮箱和网站的工作方式的详细信息有所不同。

- **邮箱：** 下次托管文件夹助理处理邮箱并检测已删除电子数据展示保留时，邮箱将设置延迟保留。 具体来说，当托管文件夹助理将下列邮箱属性之一设置为 True 时，将延迟保留应用于 **邮箱**：

   - **DelayHoldApplied：** 此属性适用于用户 (邮箱Outlook Outlook 网页版) 邮箱中存储的电子邮件相关内容。

   - **DelayReleaseHoldApplied：** 此属性 (适用于非 Outlook 应用（如 Microsoft Teams、Microsoft Forms 和 Microsoft Yammer) ）生成的基于云的内容Yammer) 存储在用户邮箱中。 Microsoft 应用生成的云数据通常存储在用户邮箱的隐藏文件夹中。

   如果对邮箱 (设置了延迟保留，则当以前的任一属性设置为 **True**) 时，该邮箱仍被视为处于无限期保留状态，就像邮箱处于诉讼保留一样。 30 天后，延迟保留过期，Microsoft 365 将自动尝试删除延迟保留 (，将 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 **False**) 以便删除该保留。 在将其中任一属性设置为 **False** 后，将在托管文件夹助理下次处理邮箱时清除标记为删除的相应项目。

   有关详细信息，请参阅[管理延迟保留的邮箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。

- **SharePoint和OneDrive网站：** 从SharePoint电子数据展示保留OneDrive后，保留库中保留的任何内容或内容不会在 30 天延迟保留期内删除。 这类似于从保留策略中释放网站时发生的情况。 此外，在 30 天延迟保留期间，无法手动删除保留库中的此内容。 

   有关详细信息，请参阅 [发布保留策略](retention.md#releasing-a-policy-for-retention)。

关闭核心电子数据展示案例时，延迟保留也会应用于保留的内容位置，因为关闭案例时将关闭保留。 有关关闭案例的信息，请参阅关闭、 [重新打开和删除核心电子数据展示案例](close-reopen-delete-core-ediscovery-cases.md)。

## <a name="ediscovery-hold-limits"></a>电子数据展示保留限制

下表列出了电子数据展示事例和事例保留的限制。

  | 限制说明 | 限制 |
  |:-----|:-----|
  |组织的最大事例数。  <br/> |无限制  <br/> |
  |组织的最大电子数据展示保留数。  <br/> |10,000  <br/> |
  |单个电子数据展示保留中的最大邮箱数。 此限制包括用户邮箱总数，以及与组、Microsoft 365组Microsoft Teams组Yammer邮箱。  <br/> |1,000  <br/> |
  |单个电子数据展示保留中的最大网站数。 此限制包括与 OneDrive for Business 组、SharePoint 组、Microsoft Teams 组Microsoft 365关联的网站Yammer总数。  <br/> |100  <br/> |
  |电子数据展示主页上显示的最大事例数，以及事例中"保留项、搜索"和"导出"选项卡上显示的最大项目数。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup>若要查看超过 1，000 个事例、保留、搜索或导出的列表，可以使用相应的 Office 365 Security & Compliance PowerShell cmdlet：
   >
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)
