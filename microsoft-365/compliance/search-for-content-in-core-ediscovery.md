---
title: 在核心电子数据展示案例中搜索内容
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
search.appverid:
- MOE150
- MET150
description: 搜索可能与核心电子数据展示案例相关的内容。
ms.openlocfilehash: 57ea95458df568de3687e1b0d38a70991b09a850
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/30/2021
ms.locfileid: "61643357"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a>搜索核心电子数据展示案例中的内容

创建核心电子数据展示案例并保留该案例的关注人员后，可以创建并运行一个或多个搜索，以查找与案例相关的内容。 与核心电子数据展示案例关联的搜索不会在"内容"搜索页上Microsoft 365 合规中心。  这些搜索将列在与 **搜索** 关联的核心电子数据展示案例的"搜索"页面上。 这也意味着与案例关联的搜索只能由案例成员访问。

创建核心电子数据展示搜索：
  
1. 转到 ，然后使用用户帐户的凭据登录，该帐户已分配有相应的电子数据展示权限，并且是案例 <https://compliance.microsoft.com> 的成员。

2. 在导航窗格的左侧导航 **Microsoft 365 合规中心，单击**"全部显示"，然后单击"电子数据展示>**核心"。**

3. 在"**核心电子数据展示**"页上，选择要创建关联搜索的案例，然后单击"打开 **案例"。**

4. 在案例 **的主页** 上，单击"搜索 **"** 选项卡，然后单击"新建 **搜索"。**

   ![单击"新建搜索"以创建核心电子数据展示搜索。](../media/CoreeDiscoverySearch1.png)

5. 在 **"新建搜索** "向导中，键入搜索的名称和帮助标识搜索的可选说明。 搜索名称在你的组织中必须保持唯一。

6. 在“**位置**”页面上，选择你希望搜索的内容位置。 可以搜索邮箱、站点和公用文件夹。

    ![选择将其置于保留状态的内容位置。](../media/ContentSearchLocations.png)
  
   1. **Exchange 邮箱**：将切换设置为“**打开**”，然后单击“**选择用户、组或团队**”，以指定要置于保留状态的邮箱。 使用搜索框查找用户邮箱和通讯组（将组成员的邮箱置于保留状态）以置于保留状态。 可以搜索与 Microsoft Team（适用于频道消息）、Office 365 组和 Yammer 组关联的邮箱。 有关存储在邮箱中的应用程序数据的详细信息，请参阅 [存储在邮箱中的电子数据展示内容](what-is-stored-in-exo-mailbox.md)。

   2. **SharePoint 站点**：将切换设置为“**打开**”，然后单击“**选择站点** ”，以指定要置于保留状态的 SharePoint 站点和 OneDrive 帐户。 键入你想要置于保留状态的每个站点的 URL。 还可以为 Microsoft Team、Office 365 组或 Yammer 组添加 SharePoint 站点的 URL。
  
   3. **Exchange 公用文件夹**：将切换设置为“**打开**”，从而把 Exchange Online 组织中的所有公用文件夹置于保留状态。 无法选择要置于保留状态的特定公用文件夹。 如果不想把公用文件夹置于保留状态，请让切换开关保持关闭。
  
   4. 选中此复选框，以搜索本地用户的 Teams 内容。 例如，如果你搜索组织中的所有 Exchange 邮箱并选中此复选框，用于存储本地用户的 Teams 聊天数据的基于云的存储将包括在搜索范围内。 有关详细信息，请参阅[搜索本地用户的 Teams 聊天数据](search-cloud-based-mailboxes-for-on-premises-users.md)。

7. 在“**定义搜索条件**”页面上，键入关键字查询，并在必要时将条件添加到搜索查询。

   ![配置搜索查询。](../media/ContentSearchQuery.png)

   1. 指定关键字、邮件属性（例如发送和接收日期）或文档属性（例如文件名或上次更改文档的日期）。 可以使用采用布尔运算符的更复杂查询，例如 **AND**、**OR**、**NOT** 和 **NEAR**。 如果将关键字框留空，则指定内容位置中的所有内容都将包括在搜索结果中。 有关详细信息，请参阅[适用于电子数据展示的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。

   2. 或者，可以单击“**显示关键字列表**”复选框，然后在每一行键入一个关键字。 如果执行此操作，则每行上的关键字将由逻辑运算符连接 (**c:s**)，类似于所创建的搜索创建中的 **OR** 运算符功能。

      为什么使用关键字列表？ 可以获取与每个关键字匹配的项数量的统计信息。 这可以帮助你快速标识哪些关键字最有效和最无效。 还可以在行中使用关键字短语（使用括号包围）。 有关关键字列表和搜索统计信息的详细信息，请参阅[获取搜索的关键字统计信息](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)。

      > [!NOTE]
      > 为了帮助减少因海量关键字列表导致的问题，已将关键字列表中的最大行数限制为 20 行。

   3. 也可以添加搜索条件以缩小搜索范围并返回更精确的结果集。每个条件可以将一个子句添加到开始搜索时创建并运行的搜索查询中。条件在逻辑上通过一个与 **AND** 运算符功能类似的逻辑运算符 (**c:c**) 连接到关键字查询 (在关键字框中指定)。这意味着项目需要同时满足关键字查询以及一个或多个条件才能出现在结果中。这就是条件帮助缩小结果范围的原理。有关可在搜索查询中使用的条件的列表和说明，请参阅 [搜索条件](keyword-queries-and-search-conditions.md#search-conditions)。

8. 查看搜索设置（并在必要时进行编辑），然后提交搜索以开始搜索。

完成搜索后，您可以预览搜索结果。 如有必要，请单击 **"搜索"****页上** 的"刷新"以显示您创建的搜索。

## <a name="more-information-about-searching-content-locations"></a>有关搜索内容位置详细信息

- 单击" **选择用户、组或** 团队"以指定要搜索的邮箱时，显示的邮箱选取器为空。 这种设计旨在增强性能。 若要将收件人添加到此列表，请单击"选择用户、组或团队"，在搜索框中键入至少三个字符 () ，选中名称旁边的复选框，然后单击"选择 **"。**

- 您可以将非活动邮箱、Microsoft Teams、Yammer 组Office 365组和通讯组添加到要搜索的邮箱列表中。 不支持动态通讯组。 如果您添加Microsoft Teams组Yammer组"或"Office 365组"，将搜索组或团队邮箱;不搜索该组成员的邮箱。

- 若要将网站添加到搜索，请打开切换，然后单击选择 **网站**。 键入要搜索的每个网站的 URL。 还可以为 Microsoft 团队、SharePoint组或 Office 365 组添加 Yammer URL。
