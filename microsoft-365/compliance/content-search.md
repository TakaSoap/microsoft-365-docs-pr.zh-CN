---
title: 在 Microsoft 365 合规中心中创建并运行内容搜索
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: 使用合规中心中的内容搜索电子数据展示工具，搜索各种 Microsoft 365 服务中的内容。
ms.openlocfilehash: 68270466625cc5f9b76359ae7697536956c727aa
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/30/2021
ms.locfileid: "61643380"
---
# <a name="create-a-content-search"></a>创建内容搜索

可以使用 Microsoft 365 合规中心中的内容搜索电子数据展示工具来搜索就地内容，例如组织中的电子邮件、文档和即时消息会话。 使用此工具搜索以下基于云的 Microsoft 365 数据源中的内容：
  
- Exchange Online 邮箱

- SharePoint Online 网站和 OneDrive for Business 帐户

- Microsoft Teams

- Microsoft 365 组

- Yammer 组

运行搜索后，内容位置的数量和搜索结果的估计数量将会显示在搜索弹出页面上。 可以快速查看统计信息，例如具有与搜索查询匹配的最多项的内容位置。 运行搜索后，可预览结果或将其导出到本地计算机。

## <a name="before-you-run-a-search"></a>运行搜索之前

- 若要访问 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心</a>的“内容搜索”工具页面（以运行搜索和预览并导出结果），管理员、合规专员或电子数据展示管理员必须是 Microsoft 365 合规中心的电子数据展示管理员角色组中的成员。有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。

- 在 Exchange 混合部署中，无法使用内容搜索工具来搜索本地邮箱。 只能使用该工具搜索基于云的邮箱。

## <a name="create-and-run-a-search"></a>创建并运行搜索
  
1. 转到 <https://compliance.microsoft.com>，并使用已分配相应权限的帐户凭据进行登录。

2. 在 Microsoft 365 合规中心的左侧导航窗格中，单击“**内容搜索**”。

3. 在“**内容搜索**”页面，单击“**新建搜索**”。

4. 键入搜索名称以及帮助标识搜索的可选描述。 搜索名称在你的组织中必须保持唯一。

5. 在“**位置**”页面上，选择你希望搜索的内容位置。 可以搜索邮箱、站点和公用文件夹。

    ![选择将其置于保留状态的内容位置。](../media/ContentSearchLocations.png)
  
   1. **Exchange 邮箱**：将切换设置为“**打开**”，然后单击“**选择用户、组或团队**”，以指定要置于保留状态的邮箱。 使用搜索框查找用户邮箱和通讯组。 可以搜索与 Microsoft Team（适用于频道消息）、Office 365 组和 Yammer 组关联的邮箱。 有关存储在邮箱中的应用程序数据的详细信息，请参阅 [存储在邮箱中的电子数据展示内容](what-is-stored-in-exo-mailbox.md)。

   2. **SharePoint 站点**：将切换设置为“**打开**”，然后单击“**选择站点** ”，以指定要置于保留状态的 SharePoint 站点和 OneDrive 帐户。 键入你想要置于保留状态的每个站点的 URL。 还可以为 Microsoft Team、Office 365 组或 Yammer 组添加 SharePoint 站点的 URL。
  
   3. **Exchange 公用文件夹**：将切换设置为“**打开**”，从而把 Exchange Online 组织中的所有公用文件夹置于保留状态。 无法选择要置于保留状态的特定公用文件夹。 如果不想把公用文件夹置于保留状态，请让切换开关保持关闭。
  
   4. 选中此复选框，以搜索本地用户的 Teams 内容。 例如，如果你搜索组织中的所有 Exchange 邮箱并选中此复选框，用于存储本地用户的 Teams 聊天数据的基于云的存储将包括在搜索范围内。 有关详细信息，请参阅[搜索本地用户的 Teams 聊天数据](search-cloud-based-mailboxes-for-on-premises-users.md)。

6. 在“**定义搜索条件**”页面上，键入关键字查询，并在必要时将条件添加到搜索查询。

   ![配置搜索查询。](../media/ContentSearchQuery.png)

   1. 指定关键字、邮件属性（例如发送和接收日期）或文档属性（例如文件名或上次更改文档的日期）。 可以使用采用布尔运算符的更复杂查询，例如 **AND**、**OR**、**NOT** 和 **NEAR**。 如果将关键字框留空，则指定内容位置中的所有内容都将包括在搜索结果中。 有关详细信息，请参阅[适用于电子数据展示的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。

   2. 或者，可以单击“**显示关键字列表**”复选框，然后在每一行键入一个关键字。 如果执行此操作，则每行上的关键字将由逻辑运算符连接 (**c:s**)，类似于所创建的搜索创建中的 **OR** 运算符功能。

      为什么使用关键字列表？ 可以获取与每个关键字匹配的项数量的统计信息。 这可以帮助你快速标识哪些关键字最有效和最无效。 还可以在行中使用关键字短语（使用括号包围）。 有关关键字列表和搜索统计信息的详细信息，请参阅[获取搜索的关键字统计信息](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)。

      > [!NOTE]
      > 为了帮助减少因海量关键字列表导致的问题，已将关键字列表中的最大行数限制为 20 行。

   3. 也可以添加搜索条件以缩小搜索范围并返回更精确的结果集。每个条件可以将一个子句添加到开始搜索时创建并运行的搜索查询中。条件在逻辑上通过一个与 **AND** 运算符功能类似的逻辑运算符 (**c:c**) 连接到关键字查询 (在关键字框中指定)。这意味着项目需要同时满足关键字查询以及一个或多个条件才能出现在结果中。这就是条件帮助缩小结果范围的原理。有关可在搜索查询中使用的条件的列表和说明，请参阅 [搜索条件](keyword-queries-and-search-conditions.md#search-conditions)。

7. 查看搜索设置（并在必要时进行编辑），然后提交搜索以开始搜索。
  
若要再次访问此内容搜索或者访问“**内容搜索**”页面上列出的其他内容搜索，请选择搜索，然后单击“**打开**”。

## <a name="next-steps"></a>后续步骤

以下是创建并运行内容搜索后要执行的后续步骤列表。

- [预览搜索结果](preview-ediscovery-search-results.md)

- [查看搜索结果的统计信息](view-keyword-statistics-for-content-search.md)

- [导出搜索结果](export-search-results.md)

- [导出搜索报告](export-a-content-search-report.md)

## <a name="more-information"></a>详细信息

有关内容搜索（例如搜索各种 Microsoft 365 服务中的内容）的详细信息，请参阅[内容搜索的功能引用](content-search-reference.md)。
