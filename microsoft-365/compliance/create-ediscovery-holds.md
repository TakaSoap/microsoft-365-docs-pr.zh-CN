---
title: 在核心电子数据展示事例中创建电子数据展示保留
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
description: 您可以创建与核心电子数据展示事例相关联的保留，以保留可能与调查相关的内容。
ms.openlocfilehash: c4f3b258fecde8b5a49a77585fe8f1d6cdfe2c11
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352249"
---
# <a name="create-an-ediscovery-hold"></a>创建电子数据展示保留

您可以使用核心电子数据展示事例来创建保留，以保留可能与事例相关的内容。 您可以在案例中对要调查的人员的 Exchange 邮箱和 OneDrive for business 帐户进行保留。 您还可以在与 Microsoft 团队、Office 365 组和 Yammer 组关联的邮箱和网站上放置保留。 将内容位置置于保留状态时，将保留内容，直到您从内容位置删除保留或删除保留。

创建电子数据展示保留后，可能需要长达24小时才能使保留生效。 

在创建保留时，您可以使用以下选项来限定在指定内容位置中保留的内容：
  
- 将所有内容置于保留状态时创建无限保留。 或者，您可以创建基于查询的保留，其中只有与搜索查询匹配的内容置于保留状态。

- 您可以指定一个日期范围，以仅保留在该日期范围内发送、接收或创建的内容。 或者，您可以保留所有内容，而无需考虑何时发送、接收或创建。

> [!NOTE]
> 您的组织中的所有核心电子数据展示案例最多可以有10000个电子数据展示保留。
  
## <a name="how-to-create-an-ediscovery-hold"></a>如何创建电子数据展示保留

创建与核心电子数据展示事例相关联的电子数据展示保留：
  
1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并使用已为其分配了相应电子数据展示权限的用户帐户的凭据登录。

2. 在 Microsoft 365 合规性中心的左侧导航窗格中，单击 "**全部显示**"，然后单击 "**电子数据展示 > 核心**"。

3. 在 "**核心电子数据展示**" 页上，选择要在其中创建保留的大小写，然后单击 "**打开事例**"。

4. 在该案例的**主页**上，单击 "**保留**" 选项卡。
  
5. 在 "**保留**" 页上，单击 "**创建**"。

6. 在 "**命名保留**向导" 页上，为保留名称并添加可选说明，然后单击 "**下一步**"。 保留名称在你的组织中必须保持唯一。

7. 在 "**内容位置**" 页上，选择要置于保留状态的内容位置。 您可以将邮箱、网站和公用文件夹置于保留状态。

    ![选择将其置于保留状态的内容位置](../media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   a. **邮箱位置**-单击 "**选择用户、组或团队**"，然后再次单击 "**选择用户、组或团队**" 以指定要置于保留状态的邮箱。 使用搜索框查找用户邮箱和通讯组（在组成员的邮箱上放置保留）以使其处于保留状态。 您还可以在 Microsoft 团队、Office 365 组或 Yammer 组的关联邮箱上放置保留。 选中 "用户、组、团队" 复选框，单击 "**选择**"，然后单击 "**完成**"。

   b. **网站位置**-单击 "**选择网站**"，然后单击 "再次**选择网站**" 以指定要置于保留状态的 SharePoint 和 OneDrive 帐户。 键入要置于保留状态的每个网站的 URL。 您还可以为 Microsoft 团队、Office 365 组或 Yammer 组添加 SharePoint 网站的 URL。 单击 "**选择**"，然后单击 "**完成**"。
  
   c. **Exchange 公用文件夹。** 将切换开关切换 ![ 控件移 ](../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 到 "**所有**位置"，将 Exchange Online 组织中的所有公用文件夹置于保留状态。 您不能选择将特定的公用文件夹置于保留状态。 如果您不希望对公用文件夹进行保留，则将切换开关设置为 "**无**"。

8. 将内容位置添加到保留后，请单击 "**下一步**"。

9. 若要创建基于查询的保留条件，请完成以下。 否则，若要保留指定内容位置中的所有内容，请单击 "**下一步**"

    ![创建基于查询的保留条件](../media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    a. 在 "**关键字**" 下的框中，键入搜索查询，以便仅保留满足搜索条件的内容。 您可以指定关键字、电子邮件属性或文档属性，如文件名。 您还可以使用更复杂的查询，这些查询使用布尔运算符，例如**AND**、 **or**或**NOT**。

    b. 单击 "**添加条件**" 以添加一个或多个条件以缩小保留的搜索查询。 每个条件都会向在创建保留时创建并运行的 KQL 搜索查询中添加一个子句。 例如，可以指定日期范围，以使在日期范围内创建的电子邮件或网站文档置于保留状态。 条件以逻辑方式连接到关键字查询（在 "**关键字**" 框中指定） **AND**运算符。 这意味着项目必须同时满足关键字查询和要保留的条件。

    有关创建搜索查询和使用条件的详细信息，请参阅[用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。

10. 配置基于查询的保留后，单击 "**下一步**"。

11. 查看您的设置（如有必要，请进行编辑），然后单击 "**创建此保留**"。

## <a name="ediscovery-hold-statistics"></a>电子数据展示保留统计信息

创建电子数据展示保留后，有关新保留的信息将显示在所选保留的弹出页面上。 此信息包括保留的邮箱数和网站数以及有关保留内容的统计信息，如置于保留状态的项目总数和最后一次计算保留统计信息的时间。 这些保留统计信息可帮助您确定保留与案例相关的内容的数量。
  
![保留统计信息](../media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
请记住以下有关电子数据展示保留统计信息的事项：
  
- "保留中的项目总数" 表示处于保留状态的所有内容源中的项目数。 如果已创建基于查询的保留，则此统计信息指示与查询匹配的项目数。

- 保留项的数目还包括在内容位置找到的未编制索引的项目。 如果创建基于查询的保留，则内容位置中的所有未编制索引的项目都将置于保留状态。 这包括未编制索引的项目，这些项目不符合基于查询的保留和未编制索引项目的搜索条件，这些项目可能超出了日期范围条件。 这与运行搜索时出现的情况不同，搜索结果中不包含不符合搜索查询的非索引项或由日期范围条件排除的非索引项。 有关未编制索引的项目的详细信息，请参阅[部分索引项目](partially-indexed-items-in-content-search.md)。

- 您可以通过单击 "**更新统计信息**" 来重新运行搜索估计来计算保留的当前项目数，以获取最新的保留统计信息。

- 由于邮箱或网站处于保留状态的用户通常是在 SharePoint 和 OneDrive 中发送或接收新电子邮件并创建新文档，因此保留的项目数正常。

- 如果 Exchange 邮箱、SharePoint 网站或 OneDrive 帐户移动到多地理位置环境中的其他区域，则该网站的统计信息将不会包含在保留统计信息中。 但仍会保留这些位置中的内容。 此外，如果邮箱或网站移到其他区域，则保留中显示的 SMTP 地址或 URL 将不会自动更新。 您必须编辑保留并更新 URL 或 SMTP 地址，以便内容位置再次包含在保留统计信息中

## <a name="search-locations-on-ediscovery-hold"></a>电子数据展示保留中的搜索位置

当您在核心电子数据展示事例中[搜索内容](search-for-content-in-core-ediscovery.md)时，您可以快速将搜索配置为仅搜索与事例相关联的保留项上已放置的内容位置。

![位置、保留位置](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)

选择 "**保留位置**" 选项可搜索置于保留状态的所有内容位置。 如果事例包含多个电子数据展示保留，则当您选择此选项时，将搜索所有保留中的内容位置。 此外，如果内容位置放置在基于查询的保留中，则当您运行搜索时，将只搜索与保留查询匹配的项目。 换言之，只有与保留条件和搜索条件相匹配的内容随搜索结果一起返回。 例如，如果将用户置于基于查询的案例保留中，以保留在特定日期之前已发送或创建的项目，则只会搜索这些项目。 这是通过使用**and**运算符连接事例保留查询和搜索查询来实现的。

以下是在电子数据展示保留中搜索位置时要记住的一些其他事项：

- 如果内容位置是同一大小写中的多个保留的一部分，则当您使用 "全部事例内容" 选项搜索该内容位置时，保留查询将由**OR**运算符组合。 同样，如果内容位置是两个不同保留的一部分，其中一个是基于查询的，另一个是无限保留（所有内容都置于保留状态），则所有内容都是由于无限保留而进行搜索的。

- 如果将搜索配置为在保留范围内搜索位置，然后在此情况下更改电子数据展示保留（通过添加或删除位置或更改保留查询），则会使用这些更改更新搜索配置。 但是，在更改保留后，必须重新运行搜索以更新搜索结果。

- 如果将多个电子数据展示保留放在电子数据展示事例中的单个位置上，并选择搜索保留的位置，则该搜索查询的最大关键字数为500。 这是因为搜索将使用**OR**运算符组合所有基于查询的保留。 如果在组合保留查询和搜索查询中有500个以上的关键字，则会搜索邮箱中的所有内容，而不仅仅是与基于查询的事例匹配的内容。 
    
- 如果电子数据展示保留状态为 "**开启**"，则您仍可以在保留处于打开状态时在保留位置搜索。

## <a name="preserve-content-in-microsoft-teams"></a>保留 Microsoft 团队中的内容

属于 Microsoft 团队渠道的对话存储在与 Microsoft 团队相关联的邮箱中。 同样，团队成员在渠道中共享的文件将存储在团队的 SharePoint 网站上。 因此，您必须在电子数据展示保留中放置工作组邮箱和 SharePoint 网站，以保留频道中的对话和文件。

或者，在团队中作为聊天列表一部分的对话（称为*1:1 聊天*或*1： N 组聊天*）存储在参与聊天的用户的邮箱中。 在聊天对话中，用户共享的文件存储在共享该文件的用户的 OneDrive 帐户中。 因此，您必须将单个用户邮箱和 OneDrive 帐户添加到电子数据展示保留，以便在聊天列表中保留对话和文件。 除了将工作组邮箱和网站置于保留状态之外，最好还是将 Microsoft 团队成员的邮箱置于保留状态。

从2020年2月起，我们启用了在专用频道中保留内容的功能。 由于专用通道聊天存储在聊天参与者的邮箱中，因此将用户邮箱放在电子数据展示保留中将保留专用通道聊天。 此外，如果用户邮箱位于2020年2月之前的电子数据展示保留中，则该保留现在将自动应用于存储在该邮箱中的专用通道邮件。 此外，还支持保留在专用通道中共享的文件。

有关保留团队内容的详细信息，请参阅[将 Microsoft 团队用户或团队置于法定保留状态](https://docs.microsoft.com/MicrosoftTeams/legal-hold)。
    
> [!IMPORTANT]
> 在基于云的组织中，参与加入团队对话的用户必须具有 Exchange Online 邮箱，才能在将邮箱放在电子数据展示保留中时保留聊天对话。 这是因为聊天列表中的对话存储在聊天参与者的基于云的邮箱中。 如果聊天参与者没有 Exchange Online 邮箱，将无法保留这些聊天对话。 例如，在 Exchange 混合部署中，具有本地邮箱的用户可能 ght 能够参与属于团队中的聊天列表的对话。 但在这种情况下，无法保留这些对话中的内容，因为这些用户没有可置于保留状态的基于云的邮箱。
  
每个团队或团队频道还包含用于笔记记录和协作的 Wiki。 Wiki 内容将会自动保存至采用 .mht 格式的文件。 此文件存储在团队 SharePoint 网站的 Teams Wiki 数据文档库中。 您可以通过将团队的 SharePoint 网站添加到电子数据展示保留来保留 wiki 内容。
    
> [!NOTE]
> 为团队或团队频道保留 Wiki 内容的功能（在将团队的 SharePoint 网站置于保留状态时）在2017年6月22日发布。 如果工作组网站处于保留状态，则会在该日期开始保留 Wiki 内容。 但是，如果工作组网站处于保留状态，并且在6月 22 2017 日之前删除了 Wiki 内容，则不会保留 Wiki 内容。

### <a name="office-365-groups"></a>Office 365 组

团队是基于 Office 365 组构建的。 因此，在电子数据展示保留中放置 Office 365 组类似于将团队内容置于保留状态。

在电子数据展示保留中放置团队和 Office 365 组时，请记住以下事项：

- 如前所述，若要将位于团队和 Office 365 组中的内容置于保留状态，则必须指定与组或团队关联的邮箱和 SharePoint 网站。

- 在[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中运行**remove-unifiedgroup** Cmdlet，以查看团队和 Office 365 组的属性。 如果要获取与团队或 Office 365 组关联的网站的 URL，这是一种很好的方法。 例如，以下命令显示名为高层领导团队的 Office 365 组的选定属性：

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > 若要运行 **Get-UnifiedGroup** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。 
  
- 在搜索用户的邮箱时，不会搜索用户是其成员的任何团队或 Office 365 组。 同样，当您在电子数据展示保留中放置团队或 Office 365 组时，仅将组邮箱和组网站置于保留状态。 除非将组成员的邮箱和 OneDrive for Business 网站明确添加到电子数据展示保留，否则不会将其置于保留状态。 因此，如果由于法律原因您必须将团队或 Office 365 组置于保留状态，请考虑在同一保留中添加工作组成员或组成员的邮箱和 OneDrive 帐户。

- 若要获取团队或 Office 365 组成员的列表，您可以在 Microsoft 365 管理中心的 "**组**" 页上查看属性。 或者，可以在 Exchange Online PowerShell 中运行以下命令： 
    
    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > 若要运行 **Get-UnifiedGroupLinks** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。

## <a name="onedrive-accounts"></a>OneDrive 帐户

若要收集组织中的 OneDrive for business 网站的 Url 列表，以便可以将其添加到与电子数据展示事例关联的保留或搜索，请参阅[创建组织中所有 OneDrive 位置的列表](https://docs.microsoft.com/onedrive/list-onedrive-urls)。 本文中的脚本创建一个文本文件，该文件包含组织中所有 OneDrive 站点的列表。 若要运行此脚本，必须安装并使用 SharePoint Online Management Shell。 请务必将你组织的 MySite 域的 URL 附加到你想要搜索的每个 OneDrive 网站。 这是包含你所有的 OneDrive 的域；例如，`https://contoso-my.sharepoint.com`。 下面是用户的 OneDrive 网站的 URL 示例：`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。

> [!IMPORTANT]
> 用户的 OneDrive 帐户的 URL 包括其用户主体名称（UPN）（例如 `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ）。 在极少数情况下，某人的 UPN 发生更改时，其 OneDrive URL 也将更改为包含新的 UPN。 如果用户的 OneDrive 帐户是电子数据展示保留的一部分（旧的和其 UPN 的更改），则需要更新保留，并且必须更新保留，然后添加用户的新 OneDrive URL 并删除旧的旧 URL。 有关详细信息，请参阅 [UPN 更改如何影响 OneDrive URL](https://docs.microsoft.com/onedrive/upn-changes)。

## <a name="ediscovery-hold-limits"></a>电子数据展示保留限制

下表列出了电子数据展示事例和事例保留的限制。
    
  |**限制说明**|**限制**|
  |:-----|:-----|
  |组织的最大事例数  <br/> |无限制  <br/> |
  |组织的电子数据展示保留的最大数量  <br/> |10,000  <br/> |
  |单个电子数据展示保留中的最大邮箱数  <br/> |1,000  <br/> |
  |单个电子数据展示保留中的 SharePoint 和 OneDrive for business 网站的最大数量  <br/> |100  <br/> |
  |在电子数据展示主页上显示的最大事例数，以及在某个事例中的保留、搜索和导出选项卡上显示的最大项目数。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup>若要查看超过1000个事例、保留、搜索或导出的列表，您可以使用相应的 Office 365 安全性 & 合规性 PowerShell cmdlet：<br/> [Get-compliancecase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [New-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)