---
title: 在高级电子数据展示中管理保留
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何在保管人及其数据源中放置保留，以保留适用于高级电子数据展示事例的相关内容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9f540877626d01652912038d69a83598af55ba1d
ms.sourcegitcommit: ff1af42b036bfdf75729db8c78f10cf4642616ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2020
ms.locfileid: "44477158"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>在高级电子数据展示中管理保留

您可以使用高级电子数据展示事例来创建保留，以保留可能与您的案例相关的内容。 使用高级电子数据展示保留功能，可以将保留在保管人及其数据源上。 此外，还可以将非 custodial 保留置于邮箱和 OneDrive for business 网站上。 您还可以在组邮箱、SharePoint 网站和 OneDrive for business 网站上放置 Microsoft 365 组的保留项。 同样，您可以在与 Microsoft 团队关联的邮箱和网站上放置保留。 将内容位置置于保留状态时，将保留内容，直到您释放保管人、删除特定的数据位置或完全删除保留策略。

## <a name="manage-custodian-based-holds"></a>管理基于保管人的保留

在某些情况下，您可能有一组已确定的保管人，并决定在这种情况下保留其数据。 在高级电子数据展示中，当这些保管人置于保留状态时，用户及其选择的数据源将自动添加到保管人保留策略中。

若要查看保管人保留策略，请执行以下操作：

1. 在 Microsoft 365 合规性中心中，单击 "**电子数据展示 > 高级**" 以显示组织中的案例列表。
   
2. 转到 "**保管人**" 选项卡，在你的事例中添加保管人。 若要了解如何在高级电子数据展示事例中添加和将保管人置于保留状态，请参阅[将保管人添加到高级电子数据展示事例](add-custodians-to-case.md)。 如果你已添加了保管人并将其置于保留状态，请转到步骤3。
   
3. 转到 "**保留**" 选项卡，然后单击 " **CustodianHold \<HoldId> **"。
   
4. 在弹出页面中，可以看到策略的 "保留统计信息"。 您还可以执行将查询应用于基于保管人的保留等操作。 有关创建保留查询和使用条件的详细信息，请参阅[用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。
 
## <a name="manage-non-custodial-holds"></a>管理非 custodial 保留

在创建保留时，您可以使用以下选项来限定指定内容位置中保留的内容：

- 将所有内容置于保留状态时创建无限保留。 或者，您可以创建基于查询的保留，其中只有与搜索查询匹配的内容置于保留状态。
  
- 您可以指定一个日期范围，以仅保存在该日期范围内发送、接收或创建的内容。 或者，您可以保留所有内容，而无需考虑何时发送、接收或创建。

若要为高级电子数据展示事例创建非 custodial 保留：

1. 在 Microsoft 365 合规性中心中，单击 "**电子数据展示 > 高级**" 以显示组织中的案例列表。
  
2. 单击要在其中创建保留的事例旁边的 "**打开**"。
  
3. 在该事例的主页中，单击 "**保留**" 选项卡。
  
4. 在 "**保留**" 选项卡上，单击 "**创建**"。
  
5. 在 "**命名你的保留**" 页上，为保留保留一个名称。 保留名称在你的组织中必须保持唯一。
 
6. Optional在 "**说明**" 框中，添加保留的说明。
  
7. 单击“**下一步**”。
  
8. 选择要置于保留状态的内容位置。 您可以将邮箱、网站和公用文件夹置于保留状态。

   a. **Exchange 电子邮件**-单击 "**选择用户、组或团队**"，然后再次单击 "**选择用户、组或团队**" 以指定要置于保留状态的邮箱。 使用搜索框查找用户邮箱和通讯组（在组成员的邮箱上放置保留）以使其处于保留状态。 您还可以在 Microsoft 365 组或 Microsoft 团队的关联邮箱上放置保留。 选中 "用户、组、团队" 复选框，单击 "**选择**"，然后单击 "**完成**"。
 
    > [!NOTE]
    > 当您单击 "**选择用户、组或团队**以指定要置于保留状态的邮箱" 时，显示的邮箱选取器为空。 这种设计旨在增强性能。 若要将人员添加到此列表，请在搜索框中键入一个名称（至少3个字符）。

    b. **SharePoint 网站**-单击 "**选择网站**"，然后单击 "再次**选择网站**" 以指定 SharePoint 和 OneDrive for business 网站置于保留状态。 键入要置于保留状态的每个网站的 URL。 您还可以为 Microsoft 365 组或 Microsoft 团队添加 SharePoint 网站的 URL。 单击 "**选择**"，然后单击 "**完成**"。
    
     有关将 Microsoft 365 组和 Microsoft 团队置于保留状态的提示，请参阅**FAQ**部分。

    > [!NOTE]
    > 用户的 OneDrive 帐户的 URL 包括其用户主体名称（UPN）（例如 `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ）。 在极少数情况下，某人的 UPN 发生更改时，其 OneDrive URL 也将更改为包含新的 UPN。 如果用户的 OneDrive 帐户是非 custodial 保留的一部分，并且其 UPN 已更改，则需要更新保留，并指向新的 OneDrive URL。 有关详细信息，请参阅 [UPN 更改如何影响 OneDrive URL](https://docs.microsoft.com/onedrive/upn-changes)。

     c. **Exchange 公用文件夹**-将切换开关移动到 "所有位置"，将 Exchange Online 组织中的所有公用文件夹置于保留状态。 请注意，不能选择将特定的公用文件夹置于保留状态。 如果您不希望对公用文件夹进行保留，则将切换开关设置为 "**无**"。

9. 将内容位置添加到保留后，请单击 "**下一步**"。
  
10. 若要创建基于查询的保留条件，请完成以下。 否则，只需单击 "**下一步**"。
    
    - 在 "**关键字**" 下的框中，在框中键入搜索查询，以便在保留时仅放置符合搜索条件的内容。 您可以指定关键字、邮件属性或文档属性，如文件名。 您还可以使用更复杂的查询，这些查询使用布尔运算符，例如 AND、OR 或 NOT。 如果将 "关键字" 框留空，则位于指定内容位置的所有内容都将置于保留状态。

    - 单击 "**添加**条件" 以添加一个或多个条件以缩小保留的搜索查询。 每个条件都会向在创建保留时创建并运行的 KQL 搜索查询中添加一个子句。 例如，您可以指定日期范围，以使在日期范围内创建的电子邮件或网站文档置于保留状态。 可通过使用 AND 运算符在逻辑上将条件连接至关键字查询（在关键字框中指定）。 这意味着项目必须同时满足关键字查询和要置于保留状态的条件。

     有关创建搜索查询和使用条件的详细信息，请参阅[用于内容搜索的关键字查询和搜索条件](https://docs.microsoft.com/office365/SecurityCompliance/keyword-queries-and-search-conditions)。

11. 配置基于查询的保留后，单击 "**下一步**"。

12. 查看您的设置，然后单击 "**创建此保留**"。

## <a name="view-hold-statistics"></a>查看保留统计信息

一段时间后，有关新保留的信息将显示在所选保留的 "**保留**" 选项卡上的 "详细信息" 窗格中。 此信息包括保留的邮箱数和网站数以及有关保留内容的统计信息，如置于保留状态的项目总数和最后一次计算保留统计信息的时间。 这些保留统计信息可帮助您确定与电子数据展示事例相关的内容的数量。

有关保留统计信息，请记住以下几点：

- "保留中的项目总数" 表示处于保留状态的所有内容源中的项目数。 如果已创建基于查询的保留，则此统计信息指示与查询匹配的项目数。
  
- 保留项的数目还包括在内容位置找到的未编制索引的项目。 请注意，如果创建基于查询的保留，则内容位置中的所有未编制索引的项目都将置于保留状态。 这包括未编制索引的项目，这些项目不符合基于查询的保留和未编制索引项目的搜索条件，这些项目可能超出了日期范围条件。 这与运行内容搜索时发生的情况不同，在这种情况下，搜索结果中不包含与搜索查询不匹配或由日期范围条件排除的非索引项目。 有关未编制索引的项目的详细信息，请参阅[在 Office 365 中的内容搜索中的部分索引项目](partially-indexed-items-in-content-search.md)。 

- 您可以通过单击 "更新统计信息" 来重新运行计算处于保留状态的当前项目数的搜索估计值，以获取最新的保留统计信息。

- 如有必要，请单击工具栏中的 "刷新" 以更新详细信息窗格中的保留统计信息。

- 由于邮箱或网站处于保留状态的用户通常是发送或接收新电子邮件，以及创建新的 SharePoint 和 OneDrive for business 文档，因此保留的项目数正常。

- 如果将 SharePoint 网站或 OneDrive 帐户移动到多地理位置环境中的其他区域，则该网站的统计信息将不会包含在保留统计信息中。 但是，网站中的内容仍处于保留状态。 此外，如果将网站移动到其他区域，则不会更新保留中显示的 URL。 您必须编辑保留并更新 URL。

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>将 Microsoft 团队和 Office 365 组置于保留状态

Microsoft 团队基于 Office 365 组构建。 因此，在高级电子数据展示中将其置于保留状态非常相似。 

- **如何将其他 Microsoft 365 组或 Microsoft 团队网站映射到保管人？在 Microsoft 365 组和 Microsoft 团队中放置非 Custodial 保留会怎么样？** Microsoft 团队构建在 Microsoft 365 组之上。 因此，在电子数据展示事例中将其置于保留状态非常相似。 将 Microsoft 365 组和 Microsoft 团队置于保留状态时，请记住以下事项。
  - 若要将位于 Microsoft 365 组和 Microsoft 团队中的内容置于保留状态，您必须指定与组或团队关联的邮箱和 SharePoint 网站。
  
  - 在 Exchange Online 中运行**remove-unifiedgroup** cmdlet，以查看 Microsoft 365 组或 microsoft 团队的属性。 若要获取与 Microsoft 365 组或 Microsoft 团队相关联的网站的 URL，这是一种很好的方法。 例如，以下命令显示名为“高层领导团队”的 Microsoft 365 组的选定属性：


    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > 若要运行 Get-UnifiedGroup cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。

 - 在搜索用户的邮箱时，不会搜索用户是其成员的任何 Microsoft 365 组或 Microsoft 团队。 同样，在置入 Microsoft 365 组或 Microsoft 团队时，只有组邮箱和组网站处于保留状态。除非将组成员的邮箱和 OneDrive for Business 网站明确添加为保管人或将其数据源放置，否则它们不会置于保留状态。 因此，如果需要将 Microsoft 365 组或 Microsoft 团队置于保留状态以供特定保管人使用，请考虑将组网站和组邮箱映射到保管人（请参阅在高级电子数据展示中管理保管人）。 如果 Microsoft 365 组或 Microsoft 团队不属于单个管理员，请考虑将该源添加到非 custodial 保留中。 
 
 - 若要获取 Microsoft 365 组或 Microsoft 团队成员的列表，您可以在 Microsoft 365 管理中心的 "家庭 > 组" 页上查看属性。 或者，可以在 Exchange Online PowerShell 中运行以下命令：

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > 若要运行 **Get-UnifiedGroupLinks** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。

- 属于 Microsoft 团队渠道的频道会话存储在与团队相关联的邮箱中。 同样，团队成员在渠道中共享的文件将存储在团队的 SharePoint 网站上。 因此，您必须将 Microsoft 团队邮箱和 SharePoint 网站置于保留状态，以在频道中保留对话和文件。
  
- 或者，在 Microsoft 团队中作为聊天列表一部分的对话存储在用户参与聊天的用户的邮箱中。  用户在聊天对话中共享的文件存储在共享该文件的用户的 OneDrive for Business 网站中。 因此，您必须将单独的用户邮箱和 OneDrive for Business 网站置于保留状态，以便在聊天列表中保留对话和文件。 
  
- 每个 Microsoft 团队或团队频道都包含用于笔记记录和协作的 Wiki。 Wiki 内容将会自动保存至采用 .mht 格式的文件。 此文件存储在团队 SharePoint 网站的 Teams Wiki 数据文档库中。 您可以通过将团队的 SharePoint 网站置于保留状态，使 Wiki 中的内容处于保留状态。

  > [!NOTE]
  > 为 Microsoft 团队或团队频道保留 Wiki 内容的功能（在将团队的 SharePoint 网站置于保留状态时）发布在2017年6月22日。 如果工作组网站处于保留状态，则会在该日期开始保留 Wiki 内容。 但是，如果工作组网站处于保留状态，并且在6月 22 2017 日之前删除了 Wiki 内容，则不会保留 Wiki 内容。
