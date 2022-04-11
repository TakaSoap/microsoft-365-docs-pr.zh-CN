---
title: 高级电子数据展示中的 Teams 工作流
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 了解如何在Advanced eDiscovery中保留、收集、审阅和导出Microsoft Teams中的内容。
ms.openlocfilehash: ecd114f9ea68cefb03e55453176a0c8b323620cc
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64758786"
---
# <a name="advanced-ediscovery-workflow-for-content-in-microsoft-teams"></a>Advanced eDiscovery Microsoft Teams中内容的工作流

本文提供了一组全面的过程、指南和最佳做法，用于使用Advanced eDiscovery从Microsoft Teams保存、收集、审阅和导出内容。 本文旨在帮助你优化电子数据展示工作流以Teams内容。

可以使用Advanced eDiscovery收集和处理五类Teams内容：

- **Teams 1：1 聊天**。 在两个人之间Teams对话中共享的聊天消息、帖子和附件。  Teams 1：1 聊天也称为 *对话*。

- **Teams群聊**。 在三人或三人以上的Teams对话中共享的聊天消息、帖子和附件。 也称为 *1：N* 聊天或 *群组对话*。

- **Teams通道**。 在标准Teams频道中共享的聊天消息、帖子、答复和附件。

- **专用频道**。 在专用Teams频道中共享的消息帖子、答复和附件。

- **共享通道**。 共享Teams通道中共享的消息帖子、答复和附件。

## <a name="where-teams-content-is-stored"></a>存储Teams内容的位置

在Advanced eDiscovery中管理Teams内容的先决条件是了解可在Advanced eDiscovery中收集、处理和审阅的Teams内容类型，以及该内容存储在Microsoft 365中的位置。 下表列出了Teams内容类型以及每个内容的存储位置。

|&nbsp;|聊天消息和帖子的位置|文件和附件的位置|
|---|---|---|
|Teams 1：1 聊天|1：1 聊天中的消息存储在所有聊天参与者的Exchange Online邮箱中。|在 1：1 聊天中共享的文件存储在共享文件的人员的OneDrive for Business帐户中。|
|Teams群聊|群聊中的消息存储在所有聊天参与者的Exchange Online邮箱中。|群聊中共享的文件存储在共享文件的人员的OneDrive for Business帐户中。|
|Teams 频道|所有频道邮件和帖子都存储在与团队关联的Exchange Online邮箱中。|频道中共享的文件存储在与团队关联的 SharePoint Online 网站中。|
|专用频道|在专用频道中发送的消息存储在专用频道的所有成员的Exchange Online邮箱中。|在专用频道中共享的文件存储在与专用频道关联的专用 SharePoint Online 站点中。|
|共享频道|在共享通道中发送的消息存储在与共享通道关联的系统邮箱中。<sup>1</sup>|共享通道中共享的文件存储在与共享通道关联的专用 SharePoint Online 站点中。|

> [!NOTE]
> <sup>1</sup> 若要搜索 (并保留在共享通道中发送的) 邮件，必须搜索或指定父团队的Exchange Online邮箱。

## <a name="create-a-case-for-teams-content"></a>为Teams内容创建事例

在Advanced eDiscovery中管理Teams内容的第一步是使用针对管理Teams内容而优化的新案例格式创建案例。 下面是将新事例格式用于Teams内容的好处：

- 支持会话线程，其中会话中包含响应项的其他消息会自动收集并添加到审阅集。

- Teams聊天会自动作为 HTML 脚本文件添加到审阅集。 在对话中共享的云附件也会添加到审阅集。 这有助于为具有响应项目的对话提供上下文，并减少基于聊天的内容生成的项总数。

- 可将最多 1 TB 的集合添加到审阅集，这样就可以在一个案例中收集和大量Teams内容。

有关增加大小写限制的详细信息，请参阅[使用Advanced eDiscovery中的新事例格式](advanced-ediscovery-new-case-format.md)。

若要创建案例，请执行以下操作：

1. 转到 <https://compliance.microsoft.com> 并登录。

2. 在Microsoft 365 合规中心的左侧导航窗格中，单击“电子 **数据展示”>“高级**”。

3. 在 **Advanced eDiscovery** 页上，单击“**事例**”选项卡，然后单击 **“创建事例**”。

   随即显示 **“新建电子数据展示”大小写** 浮出控件页。 “ **事例格式** ”部分提供使用新事例格式创建事例的选项。

   ![“新建电子数据展示”事例页上的“大大小写”选项。](..\media\AeDNewCaseFormat1.png)

4. 命名案例后，选择 **“新建** ”选项，然后单击 **“保存** ”创建事例。

## <a name="add-teams-custodial-data-sources-and-preserve-teams-content"></a>添加Teams保管数据源并保留Teams内容  

下一步是标识调查中的数据保管人用户，并将他们及其内容位置作为保管人添加到在上一部分中创建的案例。 添加保管人时，可以指定其邮箱和OneDrive帐户作为保管数据源。 还可以将Teams内容位置指定为保管人数据源，以便在调查期间快速将这些位置置于法定保留状态，以保留内容。 它还可轻松收集内容并将其添加到审阅集。

若要将保管人添加到案例并保留保管数据源，请执行以下操作：

1. 转到在上一部分中创建的Advanced eDiscovery案例，然后单击 **“数据源**”。

2. 在 **“数据源** ”页上，单击 **“添加数据源** > **”新保管人**。

3. 在 **“新建保管** 人”向导中，通过键入用户姓名或别名的第一部分，将一个或多个用户作为保管人添加到案例中。 找到正确的人员后，选择其姓名以将其添加到列表中。  

4. 展开每个保管人以查看已自动关联到保管人的主要数据源，并选择要关联到保管人的其他位置。

   ![保管人数据源。](..\media\TeamsCustodialDataLocations1.png)

5. 请遵循以下准则为Teams内容添加托管数据源。 单击 **“编辑** ”以添加数据位置。

   - **邮箱**。 默认情况下会选择保管人的邮箱。 保留此选项以添加 (并保留) 1：1 聊天、群聊和私人频道聊天作为保管数据。

   - **OneDrives**. 默认情况下，将选择保管人的OneDrive帐户。 保留此选项以添加 (并保留在 1：1 聊天和群聊中共享的) 文件作为保管数据。

   - **SharePoint**。 添加与保管人所属的任何专用或共享通道关联的SharePoint站点，以添加 (并保留) 作为在通道中共享的文件的保管数据。 单击 **“编辑**”，然后添加与专用频道或共享频道关联的SharePoint网站的 URL。 若要了解如何查找用户所属的专用和共享频道，请参阅 [专用和共享频道的电子数据展示](/microsoftteams/ediscovery-investigation#ediscovery-of-private-and-shared-channels)。

   - **Teams**。 添加保管人所属的团队，以添加 (并保留) 作为所有通道消息和共享到Teams通道的所有文件的保管数据。 这包括为保管人所属的共享通道的父团队添加邮箱。 单击 **“编辑**”时，与保管人所属的每个团队关联的邮箱和网站将显示在列表中。 选择要与保管人关联的团队。 必须为每个团队选择相应的邮箱和网站。

   > [!NOTE]
   > 还可以添加保管人不是保管人数据位置成员的Teams的邮箱和网站。 为此，请单击 **Exchange** 旁边的“**编辑****”并SharePoint**，然后添加与团队关联的邮箱和网站。

6. 添加保管人并配置保管数据源后，单击 **“下一步** ”以显示 **“保留设置”** 页。

   将显示保管人列表，默认情况下会选中 **“保留** ”列中的复选框。 这表明将保留在与每个保管人关联的数据源上。 选择这些复选框以保留此数据。

7. 在 **“保留设置”页上** ，单击 **“下一步** ”查看保管人设置。 单击 **“提交** ”将保管人添加到案例中。

有关在Advanced eDiscovery案例中添加和保留数据源的详细信息，请参阅：

- [将保管人添加到Advanced eDiscovery案例](add-custodians-to-case.md)

- [将非托管数据源添加到Advanced eDiscovery案例](non-custodial-data-sources.md)

## <a name="collect-teams-content-and-add-to-review-set"></a>收集Teams内容并添加到审阅集

将保管人添加到案例并保留保管人数据源中的内容后，工作流中的下一步是搜索与调查相关的Teams内容，并将其添加到审阅集以供进一步审查和分析。 虽然通常将Teams内容与其他Microsoft 365服务（如Exchange中的电子邮件和SharePoint中的文档）中的内容一起收集，但本部分将特别侧重于收集集合中Teams内容。 可以创建收集非Teams内容以添加到审阅集的其他集合。

为案例收集Teams内容时，工作流中有两个步骤：

1. **创建草稿集合**。  第一步是创建草 *稿集合*，这是与搜索条件匹配的项的估计值。 可以查看有关与搜索查询匹配的结果的信息，例如找到的项目总数和大小、找到它们的不同数据源以及有关搜索查询的统计信息。 还可以预览集合返回的项的示例。 使用这些统计信息，可以更改搜索查询并根据需要重新运行草稿集合，以缩小结果范围，直到你确信你正在收集与案例相关的内容。

2. **将草稿集合提交到审阅集**。 对草稿集合的结果感到满意后，可以将集合提交到审阅集。 提交草稿集合时，集合返回的项将添加到评审集以供审阅、分析和导出。

还可以选择在创建和运行集合时，不运行草稿集合并将集合结果直接添加到审阅集。

若要创建Teams内容的集合，请执行以下操作：

1. 转到在上一部分中添加了保管人Advanced eDiscovery案例，然后单击 **“集合**”。

2. 在 **“集合”页上**，选择 **“新建 collectionStandard** >  **集合**”。

3. 为集合键入所需的名称 () 和说明 (可选) 。

4. 在 **“保管数据源** ”页上，单击 **“选择保管人** ”以选择已添加到案例中的保管人。

   案例保管人列表显示在 **“选择保管人** ”浮出控件页上。

5. 选择一个或多个保管人，然后单击 **“添加**”。

   将特定保管人添加到集合后，将显示每个保管人特定数据源的列表。 这些是在将保管人添加到案例时配置的数据源。 默认情况下，将选择所有保管人数据源。 这包括与保管人关联的任何Teams或频道。

   我们建议在收集Teams内容时执行以下操作：

   - 通过取消为每个保管人) 取消选中保管人OneDrive列中的复选框，从集合范围 (删除保管人的 **OneDrive** 帐户。 这可以防止收集附加到 1：1 聊天和群聊的重复文件。 将草稿集合提交到审阅集时，会自动从集合中的每个会话收集云附件。 通过使用此方法 (而不是在集合) 中搜索OneDrive帐户，附加到 1：1 和群聊的文件会在共享的对话中分组。

   - 取消选中 **“其他网站**”列中的复选框，删除包含在专用频道或共享通道中共享的文件的SharePoint站点。 这样做可以消除收集附加到专用或共享频道对话的重复文件，因为在提交草稿集合时，这些云附件会自动添加到审阅集，并将其分组到共享的对话中。

6. 如果之前遵循了将Teams内容添加为保管人数据源的步骤，则可以跳过此步骤并选择 **“下一步**”。 否则，在 **“非托管数据源** 向导”页上，可以选择包含可能已添加到案例中以在集合中搜索的Teams内容的非托管数据源。

7. 如果之前遵循了将Teams内容添加为保管人数据源的步骤，则可以跳过此步骤并选择 **“下一步**”。 否则，在 **“其他位置** 向导”页上，可以添加其他数据源以在集合中进行搜索。 例如，可以为未添加为保管或非保管数据源的团队添加邮箱和网站。 否则，请选择 **“下一步** ”并跳过此步骤。

8. 在 **“条件**”向导页上，将搜索查询配置为从在上一向导页上指定的数据源收集Teams内容。 可以使用各种关键字和搜索条件缩小集合的范围。 有关详细信息，请参阅 [集合的生成搜索查询](building-search-queries.md)。

   为了帮助确保最全面的Teams聊天对话集合 (包括 1：1、组和频道聊天，) 使用 **“类型**”条件并选择 **“即时消息**”选项。 我们还建议包括日期范围或几个关键字，以将集合的范围缩小到与调查相关的项目。 下面是使用 **“类型** 和 **日期** ”选项的示例查询的屏幕截图：

   ![用于收集Teams内容的查询。](..\media\TeamsConditionsQueryType.png)

9. 在 **“保存草稿”或“收集** 向导”页上，根据是要创建草稿集合还是将集合提交到审阅集，请执行下列操作之一。

   ![保存草稿集合或提交集合。](..\media\TeamsDraftCommitCollection.png)

   1. **将集合另存为草稿**。 选择此选项可创建草稿集合。 如前所述，草稿集合不会将集合结果添加到审阅集。 它返回与收集范围中数据源的搜索查询匹配的搜索结果的估计值。 这使你有机会查看 [集合统计信息和报表[ (collection-statistics-reports.md) ] 并编辑和重新运行草稿集合。 如果对草稿集合的结果感到满意，可以将其提交到审阅集。 有关详细信息，请参阅 [“创建草稿集合](create-draft-collection.md)”。

   2. **收集项目并添加到审阅集**。 选择此选项以运行集合，然后将结果添加到审阅集。 可以将集合添加到新的或现有的审阅集。 默认情况下会选择用于收集上下文Teams会话消息 (也称为 *对话线程*) 和收集云附件的选项，不能取消选择。 由于最初为Teams内容创建事例时使用的新事例格式，这些选项会自动应用。 有关将集合提交到审阅集的详细信息，请参阅 [将草稿集合提交到审阅集](commit-draft-collection.md)。

10. 配置完集合后，提交集合以创建草稿集合或收集项，并将其添加到审阅集。

   完成将集合添加到审阅集的过程后，“ **集合** ”选项卡上集合的状态值将设置为 **“已提交**”。

## <a name="review-teams-content-in-a-review-set"></a>审阅Teams审阅集中的内容

将Teams内容的集合添加到审阅集后，下一步是查看内容是否与调查相关，并在必要时将其扑杀。 查看Teams内容的一个重要先决条件是了解Advanced eDiscovery在将聊天对话和附件添加到审阅集时如何处理Teams聊天对话和附件。 这种对Teams内容的处理会导致以下三种情况：

- **[分组](#grouping)**。 如何将Teams对话的消息、帖子和答复分组在一起并在审阅集中显示。 这还包括在聊天对话中提取的附件，并在会话中进行分组。

- **[脚本会话线程](#transcript-conversation-threading)**。 Advanced eDiscovery如何确定要收集的对话中的其他内容，以提供与集合条件匹配的项的上下文。

- **[重复删除](#deduplication-of-teams-content)**。 Advanced eDiscovery如何处理重复Teams内容。

- **[元数据](#metadata-for-teams-content)**。 收集内容并添加到审阅集后，Advanced eDiscovery添加到Teams内容的元数据属性。

了解分组、会话线程、重复数据删除和Teams元数据将有助于优化Teams内容的审阅和分析。 本部分还提供了[查看审阅集中Teams内容的提示](#tips-for-viewing-teams-content-in-a-review-set)。

### <a name="grouping"></a>分组

将Teams聊天对话中的内容添加到审阅集时，会在 HTML 脚本文件中聚合来自对话的消息、帖子和答复。 单个聊天会话可以有多个脚本文件。 这些脚本文件的一个重要功能是将Teams内容呈现为连续对话，而不是单独 (或单独) 消息。 这有助于为在上一步中与集合的搜索条件匹配的项提供上下文，并减少收集到审阅集中的项目数。 脚本和关联的项目可以按 *家庭* 或 *会话* 分组。 同一系列中的项对 **FamilyId** 元数据属性具有相同的值。 同一对话中的项对 **ConversationId** 元数据属性具有相同的值。

下表描述了不同类型的Teams聊天内容如何按家庭和聊天进行分组。

|Teams内容类型|按家庭分组|按对话分组|
|---|---|---|
|Teams 1：1 和群聊|脚本及其所有附件和提取的项共享相同的 **FamilyId**。 每个脚本都有唯一 **的 FamilyId**。|同一对话中的所有脚本文件及其家庭项目共享相同的 **ConversationId**。 这包括以下项： <ul><li>共享同一 **ConversationId** 的所有脚本的所有提取项和附件。</li><li>同一聊天对话的所有脚本</li><li>每个脚本的所有保管人副本</li><li>来自同一聊天对话的后续集合的脚本</li></ul> <br/> 对于Teams 1：1 和群组聊天对话，你可能有多个脚本文件，每个文件对应于对话中的不同时间范围。 由于这些脚本文件来自与同一参与者的同一对话，因此它们共享相同的 **ConversationId**。|
|标准、专用和共享频道聊天|每个帖子以及所有答复和附件都保存到自己的脚本中。 此脚本及其所有附件和提取的项共享相同的 **FamilyId**。|每个帖子及其附件和提取的项都有唯一 **的 ConversationId**。 如果有来自同一帖子的后续集合或新答复，则这些集合生成的增量脚本也将具有相同的 **ConversationId**。|

使用审阅集命令栏中的 **组** 控件查看按家庭或聊天分组的Teams内容。

![命令栏中的组控件。](..\media\TeamsGroupControl.png)

- 选择 **“组系列”附件** 以查看按家庭分组的Teams内容。 每个脚本文件显示在审阅集项目列表中的一行上。 附件嵌套在项下。

- 选择 **分组Teams或Yammer对话** 以查看按对话分组的Teams内容。 每个对话都显示在审阅集项目列表中的行上。 脚本文件和附件嵌套在顶级对话下。

> [!NOTE]
> 云附件与它们显示的对话进行分组。 此分组是通过分配与文件附加到的消息的脚本文件相同的 **FamilyId** 和消息中出现的会话相同的 **ConversationId** 来完成的。 这意味着，如果云附件的多个副本附加到不同的对话，则可以将其添加到审阅集。

#### <a name="viewing-transcript-files-for-conversations"></a>查看对话的脚本文件

查看审阅集中的脚本文件时，某些消息以紫色突出显示。 突出显示的消息取决于要查看的脚本的保管人副本。 例如，在 User4 和 User2 之间的 1：1 聊天中，查看从 User4 邮箱收集的脚本时，User4 发布的邮件以紫色突出显示。 当你查看 User2 的同一对话的脚本时，User2 发布的消息以紫色突出显示。 此突出显示行为基于相同的Teams客户端体验，其中用户的帖子在Teams客户端中以紫色突出显示。

以下屏幕截图显示了Teams客户端中的对话示例和审阅集中同一对话的脚本文件。 脚本文件中的紫色突出显示表示脚本是从 User2 的邮箱中收集的。

##### <a name="conversation-in-teams-client"></a>Teams客户端中的对话

![审阅集中的脚本文件中显示的对话。](..\media\TeamsClient1.png)

##### <a name="conversation-in-transcript-file"></a>脚本文件中的对话

![Teams客户端中显示的相同对话。](..\media\TeamsTranscript1.png)

### <a name="transcript-conversation-threading"></a>脚本对话线程

Advanced eDiscovery中新案例格式的对话线程功能可帮助你识别与可能与调查相关的项相关的上下文内容。 此功能生成不同的对话视图，其中包括前面的聊天消息，并在集合期间关注与搜索查询匹配的项。 借助此功能，可以高效快速地查看 (Microsoft Teams中称为 *线程对话*) 的完整聊天对话。 如上所述，当Advanced eDiscovery将Teams内容添加到审阅集时，聊天会在 HTML 脚本文件中重新构造。

下面是Advanced eDiscovery用于包含其他消息和答复脚本文件的逻辑，这些邮件和答复脚本文件提供与收集查询 (集合查询匹配，) 收集Teams内容时使用的 *响应项*。 不同的线程行为基于聊天类型和用于收集响应项的搜索查询。 有两种常见的集合方案：

- 使用搜索参数的查询，例如关键字和属性：值对

- 仅使用日期范围的查询

|Teams内容类型|具有搜索参数的查询|具有日期范围的查询|
|---|---|---|
|Teams 1：1 和群聊|响应项前 12 小时和响应项后 12 小时发布的邮件与单个脚本文件中的响应项分组。|24 小时窗口中的消息分组在单个脚本文件中。|
|标准、专用和共享Teams频道聊天|每个包含响应项和所有相应答复的帖子都分组在单个脚本文件中。|每个包含响应项和所有相应答复的帖子都分组在单个脚本文件中。|

### <a name="deduplication-of-teams-content"></a>删除Teams内容

以下列表描述了将Teams内容收集到审阅集中时重复 (和重复) 行为。

- 添加到审阅集的每个脚本文件应是一对一映射到数据位置中存储的内容。 这意味着Advanced eDiscovery不会收集已添加到审阅集的任何Teams内容。 如果已在审阅集中收集聊天消息，Advanced eDiscovery不会将同一数据位置中的相同消息添加到后续集合中的审阅集。

- 对于 1：1 和群聊，邮件副本存储在每个对话参与者的邮箱中。 使用不同的元数据收集不同参与者邮箱中存在的同一对话的副本。 因此，会话的每个实例被视为唯一的，并将其引入单独的脚本文件中的审阅集。 因此，如果 1：1 或群聊的所有参与者都作为事例中的保管人添加并包含在集合范围内，则将同一保护) 的每个脚本 (副本添加到审阅集中，并将与同一 **ConversationId** 组合在一起。 每个副本都与相应的保管人相关联。 **提示**：审阅集列表中的“ **保管人** ”列标识相应脚本文件的保管人。

- 在来自同一对话的项的后续集合中，只有之前未收集的增量内容添加到审阅集，并通过将同一 **ConversationId**) 与以前从同一对话收集的脚本共享来分组 (。 下面是此行为的示例：

   1. 集合 A 在 User1 和 User2 之间的对话中收集消息，并添加到审阅集。

   2. 集合 B 从同一对话收集消息，但自运行集合 A 以来，User1 和 User2 之间有新消息。

   3. 仅将集合 B 中的新消息添加到审阅集。 这些消息将添加到单独的脚本文件中，但新脚本由同一 **ConversationId** 与集合 A 中的脚本分组。

   此行为适用于所有类型的Teams聊天。

### <a name="metadata-for-teams-content"></a>Teams内容的元数据

在包含数千或数百万项的大型审阅集中，可能很难将评审范围缩小到Teams内容。 为了帮助你关注Teams内容，有特定于Teams内容的元数据属性。 可以使用这些属性来组织审阅列表中的列，并[配置筛选器和查询](review-set-search.md)，以优化Teams内容的审阅。 从Advanced eDiscovery导出Teams内容时，也会包含这些元数据属性，以帮助你在导出后或第三方电子数据展示工具中组织和查看内容。

下表介绍了Teams内容的元数据属性。

|元数据属性|说明|
|---|---|
|ContainsEditedMessage|指示脚本文件是否包含已编辑的消息。 查看脚本文件时，会标识已编辑的消息。|
|ConversationId|一个 GUID，用于标识与该项目关联的会话。 同一对话中的脚本文件和附件对此属性具有相同的值。|
|对话名称|脚本文件或附件关联的会话的名称。 对于Teams 1：1 和群聊，此属性的值是会话的所有参与者的 UPN 串联。 例如，`User3 <User3@contoso.onmicrosoft.com>,User4 <User4@contoso.onmicrosoft.com>,User2 <User2@contoso.onmicrosoft.com>`。 Teams频道 (标准、私人和共享) 聊天使用以下格式的对话名称： `<Team name>,<Channel name>` 例如，`eDiscovery vNext, General`。|
|ConversationType|指示团队聊天的类型。 对于Teams 1：1 和群聊，此属性的值为 `Group`。 对于标准、专用和共享的频道聊天，值为 `Channel`。|
|Date|脚本文件中第一条消息的时间戳。|
|FamilyId|标识聊天会话的脚本文件的 GUID。 附件将具有与包含文件附加到的消息的脚本文件相同的此属性值。|
|FileClass|指示该类型的内容。 Teams聊天中的项具有该值`Conversation`。 相比之下，Exchange电子邮件具有该值`Email`。|
|MessageKind|消息类型属性。 Teams内容具有该值`microsoftteams , im`。|
|收件人|在脚本对话中收到消息的所有用户的列表。|
|TeamsChannelName|脚本的Teams通道名称。|

有关其他Advanced eDiscovery元数据属性的说明，请参阅[Advanced eDiscovery中的“文档元数据”字段](document-metadata-fields-in-Advanced-eDiscovery.md)。

## <a name="export-teams-content"></a>导出Teams内容

查看并剔除审阅集中Teams内容后，可以导出包含对调查做出响应的内容的脚本文件。 Teams内容没有任何特定的导出设置。 每个脚本文件导出为 HTML 消息文件。 此文件还包含隐藏的 CDATA 标记，其中包含单个聊天消息的所有元数据。 导出Teams内容时，将包含上一部分中讨论的元数据属性。  

每个脚本文件都引用在负载文件中，并且可以使用负载文件中Export_native_path字段中的相对路径进行定位。 脚本文件位于根导出文件夹的“对话”文件夹中。

## <a name="tips-for-viewing-teams-content-in-a-review-set"></a>查看审阅集中Teams内容的使用技巧

下面是查看审阅集中Teams内容的一些提示和最佳做法。

- 使用命令栏中的 **“自定义列**”控件添加和组织列，以优化Teams内容的审阅。

  ![使用“编辑列浮出控件”页添加、删除和组织列。](..\media\EditReviewSetColumns.png)

   可以添加和删除对Teams内容有用的列。 还可以通过在“编辑列浮出”页中拖放列来对 **列** 的顺序进行排序。 还可以对列进行排序，以便对Teams内容进行排序，其中对排序的列具有相似值。

- 有助于查看Teams内容的有用列包括 **保管人**、**收件人和****文件类型** 或 **消息类型**。

- 使用Teams相关属性[的筛选器](review-set-search.md)快速显示Teams内容。 上一部分中所述的大部分元数据属性都有筛选器。

## <a name="reference-guide"></a>参考指南

下面是使用Microsoft Teams Advanced eDiscovery的快速参考指南。 本指南汇总了使用Advanced eDiscovery从Microsoft Teams保存、收集、审阅和导出内容的要点。

![用于Microsoft Teams的Advanced eDiscovery参考指南的缩略图。](../media/AeDTeamsReferenceGuide-thumbnail.png)

[下载为 PDF 文件](https://download.microsoft.com/download/9/e/4/9e4eec6f-c476-452f-b414-4bd4b5c39dca/AeDTeamsReferenceGuide.pdf)
