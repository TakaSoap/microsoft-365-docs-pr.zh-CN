---
title: 管理保留Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何对保管人及其数据源设置保留，以保留与事件相关的Advanced eDiscovery内容。
ms.custom:
- seo-marvel-mar2020
- admindeeplinkMAC
ms.openlocfilehash: 72b62623aa45ffadf43b371ad811373d4e383885
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207243"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>管理保留Advanced eDiscovery

您可以使用一个Advanced eDiscovery案例来创建保留，以保留可能与案例相关的内容。 使用Advanced eDiscovery保留功能，您可以保留保管人及其数据源。 此外，您还可以将邮箱和网站置于非OneDrive for Business保留。 还可以将组邮箱、SharePoint网站和 OneDrive for Business 网站置于保留Microsoft 365状态。 同样，可以将与邮箱关联的邮箱和网站置于保留Microsoft Teams。 当您将内容位置保留时，内容将一直保留，直到您释放保管人、删除特定数据位置或删除保留策略。

## <a name="manage-custodian-based-holds"></a>管理基于保管人的保留

在某些情况下，您可能具有一组已识别的保管人，并且已决定在案例期间保留其数据。 在Advanced eDiscovery，当这些保管人处于保留状态时，用户及其所选的数据源将自动添加到保管人保留策略。

查看保管人保留策略：

1. 在Microsoft 365 合规中心中，单击 **">高级**"以显示组织中事例的列表。

2. 转到" **源"** 选项卡，在你的案例中添加保管人。 若要了解如何在案例内添加保管人并Advanced eDiscovery保管人，请参阅向案例[添加保管人](add-custodians-to-case.md)。 如果已添加保管人并置于保留状态，请转到步骤 3。

3. 转到保留选项卡 **，** 然后单击 **CustodianHold \<HoldId>**。

4. 在飞出页面上，你可以看到策略的保留统计信息。 还可以执行类似将查询应用到基于保管人保留的操作。 有关创建保留查询和使用条件的信息，请参阅内容搜索的关键字查询 [和搜索条件](keyword-queries-and-search-conditions.md)。

## <a name="manage-non-custodial-holds"></a>管理非保留

创建保留时，可以使用以下选项来设置指定内容位置中保留的内容的范围：

- 创建一个无限期保留，其中所有内容都置于保留状态。 或者，您可以创建基于查询的保留，其中仅将与搜索查询匹配的内容置于保留状态。
  
- 您可以指定一个日期范围，以仅保留该日期范围内发送、接收或创建的内容。 或者，您可以保留所有内容，而不考虑何时发送、接收或创建内容。

若要为事件案例创建非Advanced eDiscovery保留：

1. 在Microsoft 365 合规中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">中</a>，单击 **">高级**"以显示组织中事例的列表。
  
2. 单击 **要** 创建保留的案例旁边的"打开"。
  
3. 在案例的主页中，单击"保留 **项"** 选项卡。
  
4. 在保留 **选项卡上** ，单击 **创建**。
  
5. 在" **命名保留"** 页上，为保留命名。 保留名称在你的组织中必须保持唯一。
 
6.  (可选) **在"说明** "框中，添加保留的说明。
  
7. 单击“下一步”。
  
8. 选择要保留的内容位置。 可以将邮箱、站点和公用文件夹置于保留状态。

   1. **Exchange电子邮件**- 单击 **"选择** 用户、组或团队"，然后再次单击"选择用户、组或团队"以指定要置于保留中的邮箱。 使用搜索框查找用户邮箱和通讯组（将组成员的邮箱置于保留状态）以置于保留状态。 还可以将组或 Microsoft 团队的关联邮箱Microsoft 365保留。 选中用户、组、团队复选框，单击 **"选择**"，然后单击"完成 **"。**
 
      > [!NOTE]
      > 单击" **选择用户、组或** 团队"指定要置于保留中的邮箱时，显示的邮箱选取器为空。 这种设计旨在增强性能。 若要将人员添加到此列表，在 (键入至少 3 个字符) 键入一个名称。

   1. **SharePoint网站**- 单击 **"选择** 网站"，然后单击"再次选择网站"以指定SharePoint OneDrive for Business保留的网站。 键入你想要置于保留状态的每个站点的 URL。 还可以为 SharePoint 组或 Microsoft Microsoft 365网站添加 URL。 单击 **"选择**"，然后单击"完成 **"。**

      > [!NOTE]
      > 用户的用户帐户的 URL OneDrive其用户主体名称 (UPN)  (例如 `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ，) 。 在极少数情况下，更改了某个人的 UPN，OneDrive URL 也会更改以合并新的 UPN。 如果用户的 OneDrive 帐户属于非注册保留，并且其 UPN 已更改，则需要更新保留并指向新的 OneDrive URL。 有关详细信息，请参阅 [UPN 更改如何影响 OneDrive URL](/onedrive/upn-changes)。

   1. **Exchange公用文件夹**- 将切换开关移动到"所有"位置，以将组织Exchange Online文件夹置于保留状态。 请注意，你无法选择要置于保留状态的特定公用文件夹。 如果不想将 **公用文件夹置于** 保留状态，将切换开关设置为"无"。

9. 完成向保留添加内容位置后，单击"下一 **步"。**
  
10. 若要创建具有条件的基于查询的保留，请完成以下操作。 否则，只需单击"下一 **步"。**
    
    - 在" **关键字"** 下的框中，在框中键入搜索查询，以便仅将满足搜索条件的内容置于保留状态。 可以指定关键字、邮件属性或文档属性，如文件名。 您还可以使用使用布尔运算符的更复杂的查询，如 AND、OR 或 NOT。 如果将关键字框留空，则位于指定内容位置的所有内容将置于保留状态。

    - 单击  **"** 添加条件"添加一个或多个条件以缩小保留的搜索查询范围。 每个条件向创建保留时创建和运行的 KQL 搜索查询添加一个子句。 例如，可以指定日期范围，以便保留在日期范围内创建的电子邮件或网站文档。 可通过使用 AND 运算符在逻辑上将条件连接至关键字查询（在关键字框中指定）。 这意味着项目必须满足关键字查询和要置于保留状态的条件。

     有关创建搜索查询和使用条件的信息，请参阅内容搜索的关键字查询和 [搜索条件](/office365/SecurityCompliance/keyword-queries-and-search-conditions)。

11. 配置基于查询的保留后，单击"下一 **步"。**

12. 查看设置，然后单击"创建 **此保留"。**

## <a name="view-hold-statistics"></a>查看保留统计信息

一段时间之后，有关新保留的信息将显示在所选保留的"保留 **"** 选项卡上的详细信息窗格中。 此信息包括邮箱数和处于保留状态的网站数，以及有关置于保留状态的内容的统计信息，例如置于保留状态的项目总数和大小以及上次计算保留统计信息的时间。 这些保留统计信息可帮助您确定与电子数据展示案例相关的保留内容量。

对于保留统计信息，请牢记以下事项：

- 保留项总数指示置于保留状态的所有内容源中的项目数。 如果已创建基于查询的保留，则此统计信息指示与查询匹配的项目数。
  
- 保留的项目数还包括在内容位置找到的未索引项目。 请注意，如果创建基于查询的保留，内容位置中所有未建立索引的项目将置于保留状态。 这包括不匹配基于查询的保留的搜索条件的未索引项和可能超出日期范围条件的未索引项。 这不同于运行内容搜索时发生的情况，即搜索结果中不包含与搜索查询不匹配或按日期范围条件排除的未索引项目。 有关未编制索引的项目详细信息，请参阅 Content [Search in Office 365 中的部分索引Office 365。](partially-indexed-items-in-content-search.md) 

- 可以通过单击"更新统计信息"重新运行计算当前保留项目数的搜索估计，获取最新的保留统计信息。

- 如有必要，请单击工具栏中的"刷新"以更新详细信息窗格中的保留统计信息。

- 保留项目数会随着时间的推移而增加，这是正常的，因为邮箱或网站置于保留状态的用户通常会发送或接收新电子邮件，并创建新的 SharePoint 和 OneDrive for Business 文档。

- 如果将SharePoint或OneDrive帐户移动到多地理位置环境中的不同区域，则保留统计信息中不会包含该网站的统计信息。 但是，网站中的内容仍将处于保留状态。 此外，如果将网站移动到其他区域，将不会更新在保留中显示的 URL。 您必须编辑保留并更新 URL。

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>将保留项Microsoft Teams组Office 365组

Microsoft Teams基于组Office 365构建。 因此，将它们置于保留状态Advanced eDiscovery非常相似。

- **如何将其他组Microsoft 365或Microsoft Teams映射到保管人？那么，将非 Microsoft 365 保留Microsoft Teams？** Microsoft Teams基于组Microsoft 365构建。 因此，在电子数据展示案例中将其置于保留状态非常相似。 将组和组置于保留Microsoft 365请记住Microsoft Teams事项。
  - 若要将位于Microsoft 365组Microsoft Teams中的内容置于保留状态，必须指定与组或SharePoint关联的邮箱和网站。
  
  - 在脚本 **中运行 Get-UnifiedGroup** cmdlet Exchange Online查看 Microsoft 365 组或 Microsoft 团队的属性。 这是获取与组或 Microsoft 团队Microsoft 365 URL 的一个好方法。 例如，以下命令显示名为“高层领导团队”的 Microsoft 365 组的选定属性：


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > 若要运行 Get-UnifiedGroup cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。

 - 在搜索用户的邮箱时，Microsoft 365的任何组或 Microsoft Team 用户将不会进行搜索。 同样，当您将Microsoft 365 Microsoft 团队保留时，只会将组邮箱和组网站置于保留状态;除非将OneDrive for Business添加为保管人或将其数据源置于保留状态，否则不会将其成员的邮箱和网站置于保留状态。 因此，如果需要将 Microsoft 365 组或 Microsoft Team 置于保留状态以保留特定保管人，请考虑将组网站和组邮箱映射到保管人 (请参阅在 Advanced eDiscovery) 中管理保管人。 如果Microsoft 365组或 Microsoft Team 无法归为单个保管人，请考虑将源添加到非托管保留。 
 
 - 若要获取组或 Microsoft 团队Microsoft 365列表，可以在"主页组"页上查看  >  [](https://go.microsoft.com/fwlink/p/?linkid=2052855)Microsoft 365 管理中心。 或者，可以在 Exchange Online PowerShell 中运行以下命令：

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > 若要运行 **Get-UnifiedGroupLinks** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。

- 属于团队频道的Microsoft Teams对话存储在与团队关联的邮箱中。 同样，团队成员在渠道中共享的文件将存储在团队的 SharePoint 网站上。 因此，您必须将 Microsoft Team 邮箱和 SharePoint网站置于保留状态，以在频道中保留对话和文件。
  
- 或者，属于聊天Microsoft Teams对话将存储在参与聊天的用户的邮箱中。  用户在聊天对话中共享的文件存储在共享OneDrive for Business用户的网站中。 因此，您必须将各个用户邮箱和OneDrive for Business网站置于保留状态，以在"聊天"列表中保留对话和文件。 
  
- 每个 Microsoft 团队或团队频道都包含一个 Wiki，用于做笔记和进行协作。 Wiki 内容将会自动保存至采用 .mht 格式的文件。 此文件存储在团队 SharePoint 网站的 Teams Wiki 数据文档库中。 您可以通过将团队的 SharePoint 网站置于保留状态，在 Wiki 中保留内容。

  > [!NOTE]
  > 在 2017 年 6 月 22 日 (将团队的 SharePoint 网站保留时，保留 Microsoft 团队或团队频道) 的功能。 如果团队网站保留，Wiki 内容将自该日期开始保留。 但是，如果团队网站已保留且 Wiki 内容在 2017 年 6 月 22 之前被删除，则 Wiki 内容不会保留。
