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
description: 了解如何在网站中保留、收集、查看和导出Microsoft Teams内容Advanced eDiscovery。
ms.openlocfilehash: 9565beea342fe9587195d632fdc94cdc746faf5e
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64568107"
---
# <a name="advanced-ediscovery-workflow-for-content-in-microsoft-teams"></a>Advanced eDiscovery工作流中的内容Microsoft Teams

本文提供了一套全面的过程、指南和最佳做法，以使用 Advanced eDiscovery保留、收集、审阅和导出来自Microsoft Teams。 本文的目标是帮助您优化电子数据展示工作流，以Teams内容。

您可以使用以下Teams收集并处理以下五类Advanced eDiscovery：

- **Teams一对一聊天**。 在两个人之间的对话中共享的聊天Teams帖子和附件。  Teams一对一聊天也称为 *对话*。

- **Teams群聊**。 在三个或多个人员之间Teams对话中共享的聊天消息、帖子和附件。 也称为 *1：N* 聊天或 *群组对话*。

- **Teams频道**。 在标准频道中共享的聊天消息、帖子、回复Teams附件。

- **私人频道**。 私人频道中共享的消息帖子、回复Teams附件。

- **共享频道**。 共享频道中共享的消息帖子、回复Teams附件。

## <a name="where-teams-content-is-stored"></a>存储Teams的位置

在 Advanced eDiscovery 中管理 Teams 内容的先决条件是了解可在 Advanced eDiscovery 中收集、处理和查看的 Teams 内容的类型，以及该内容在 Microsoft 365 中的存储位置。 下表列出了Teams类型以及存储每个内容类型的位置。

|&nbsp;|聊天消息和帖子的位置|文件和附件的位置|
|---|---|---|
|Teams一对一聊天|一对一聊天中的消息存储在所有Exchange Online参与者的邮箱中。|在一对一聊天中共享的文件存储在共享OneDrive for Business的用户帐户中。|
|Teams群聊|群聊中的消息存储在所有Exchange Online的邮箱中。|在群聊中共享的文件存储在共享OneDrive for Business的用户帐户中。|
|Teams 频道|所有频道消息和帖子都存储在与Exchange Online关联的邮箱中。|频道中共享的文件存储在与团队SharePoint Online 网站中。|
|专用频道|在私人频道中发送的邮件存储在Exchange Online频道所有成员的邮箱中。|私人频道中共享的文件存储在与专用SharePoint关联的专用联机网站中。|
|共享频道|共享通道中发送的邮件存储在与共享通道关联的系统邮箱中。<sup>1</sup>|共享频道中共享的文件存储在与共享SharePoint关联的专用联机网站中。|

> [!NOTE]
> <sup>1</sup> 若要搜索 (并) 共享频道中发送的邮件，您必须搜索或指定父团队Exchange Online邮箱。

## <a name="create-a-case-for-teams-content"></a>为内容创建Teams案例

管理 Teams 内容的第一Advanced eDiscovery是使用新案例格式创建一个案例，该格式已针对管理Teams内容进行了优化。 以下是对内容使用新大小写格式Teams好处：

- 支持对话线程，其中会自动收集同一对话中包含响应项目的其他消息，并添加到审阅集。

- Teams对话作为 HTML 脚本文件自动添加到审阅集。 对话中共享的云附件也会添加到审阅集。 这有助于为包含响应式项目的对话提供上下文，并减少基于聊天的内容产生的总项目数。

- 可以将高达 1 TB 的集合添加到审阅集中，这样一来，你可以收集并Teams大量内容。

有关增加的大小写限制的信息，请参阅使用新大小写[Advanced eDiscovery](advanced-ediscovery-new-case-format.md)。

创建案例：

1. 转到 <https://compliance.microsoft.com> 并登录。

2. 在导航窗格的左侧导航窗格中Microsoft 365 合规中心"**电子数据展示>高级"**。

3. 在"**Advanced eDiscovery**"页上，单击"事例 **"** 选项卡，然后单击"**创建事例"**。

   将显示 **"新建电子数据展示案例** "飞出页。 " **大小写** 格式"部分提供使用新大小写格式创建案例的选项。

   !["新建电子数据展示案例"页面上的"大案例"选项。](..\media\AeDNewCaseFormat1.png)

4. 命名案例后，选择" **新建"** 选项，然后单击 **"保存"** 以创建案例。

## <a name="add-teams-custodial-data-sources-and-preserve-teams-content"></a>添加Teams源并保留Teams内容  

下一步是识别作为调查数据保管人的用户，并添加他们及其内容位置作为你在上一部分中创建案例的保管人。 添加保管人时，可以指定其邮箱和OneDrive帐户作为安全数据源。 您还可以将Teams位置指定为保管人数据源，以快速将这些位置放在法定保留状态，以在调查期间保留内容。 它还可轻松收集内容并将其添加到审阅集。

若要将保管人添加到案例并保留现有数据源：：

1. 转到上Advanced eDiscovery中创建的"数据源"案例，然后单击"**数据源"**。

2. 在" **数据源"页上** ，单击 **"添加数据源** > **""添加新保管人"**。

3. 在 **"新建** 保管人"向导中，键入用户名或别名的第一部分，将一个或多个用户作为保管人添加到案例。 找到正确的人员后，选择其姓名以将其添加到列表中。  

4. 展开每个保管人以查看已自动与保管人关联的主数据源，并选择要与保管人关联的其他位置。

   ![保管人数据源。](..\media\TeamsCustodialDataLocations1.png)

5. 遵循以下指南为内容添加Teams数据源。 单击 **"** 编辑"添加数据位置。

   - **邮箱**。 默认情况下选择保管人邮箱。 保持选中状态以添加 (，) 一对一聊天、群聊和私人频道聊天保留为聊天数据。

   - **OneDrives**。 默认情况下，将OneDrive保管人的帐户。 保持选中状态以添加 (并保留) 一对一聊天和群聊中共享的文件作为聊天数据。

   - **SharePoint**。 添加SharePoint保管人是其中成员的任何私人或共享频道关联的网站，以添加 (并保留) 作为在频道中共享的文件的托管数据。 单击 **"** 编辑"，然后添加与专用SharePoint或共享通道关联的网站 URL。 若要了解如何查找用户是成员的私人频道和共享频道，请参阅专用频道和共享 [频道电子数据展示](/microsoftteams/ediscovery-investigation#ediscovery-of-private-and-shared-channels)。

   - **Teams**。 添加保管人为成员的团队，以添加 (并保留) 作为所有频道消息和共享到 Teams 文件的数据。 这包括为保管人是其中一个成员的共享频道的父团队添加邮箱。 单击" **编辑"** 时，与保管人是成员的每个团队关联的邮箱和网站将显示在列表中。 选择要与保管人关联的团队。 必须同时选择每个团队的相应邮箱和网站。

   > [!NOTE]
   > 您还可以将保管人不是保管人Teams成员的邮箱和网站添加为保管人数据位置。 为此，**可单击"** Exchange"旁边的SharePoint，然后添加与团队关联的邮箱和网站。

6. 添加保管人并配置托管数据源后，单击"下一步"以显示"**保留设置"** 页。

   默认情况下，将显示保管人列表，并选中"保留"列中的复选框。 这表示将保留您与每个保管人关联的数据源。 保留选中这些复选框以保留此数据。

7. 在" **保留设置"** 页上，单击 **"下** 一步"查看保管人设置。 单击 **"** 提交"将保管人添加到案例。

有关在应用程序中添加和保留数据源Advanced eDiscovery，请参阅：

- [将保管人添加到Advanced eDiscovery案例](add-custodians-to-case.md)

- [向事件案例添加非Advanced eDiscovery数据源](non-custodial-data-sources.md)

## <a name="collect-teams-content-and-add-to-review-set"></a>收集Teams内容并添加到审阅集

将保管人添加到案例并保留保管人数据源中的内容后，工作流的下一步是搜索与调查相关的 Teams 内容，并将其添加到审阅集以进一步查看和分析。 尽管通常将 Teams 内容与其他 Microsoft 365 服务（如 Exchange 中的电子邮件）和 SharePoint 中的文档一起收集，但本节将专门侧重于收集集合中的 Teams 内容。 可以创建其他集合，以收集要Teams审阅集中的非内容。

收集案例Teams内容时，工作流有两个步骤：

1. **创建草稿集合**。  第一步是创建 *草稿集合*，这是与搜索条件匹配的项目的估计值。 您可以查看与搜索查询匹配的结果的信息，例如找到的项目总数和大小、找到它们的不同数据源，以及有关搜索查询的统计信息。 还可以预览集合返回的项目示例。 使用这些统计信息，您可以更改搜索查询并尽可能多次重新运行草稿集合，以缩小结果范围，直到您满意地收集与案例相关的内容。

2. **将草稿集合提交到审阅集**。 对草稿集合的结果感到满意后，可以将该集合提交到审阅集。 提交草稿集合时，集合返回的项目将添加到审阅集，用于审阅、分析和导出。

还可以选择在您创建和运行该集合时不运行草稿集合，也不将集合结果直接添加到审阅集。

若要创建一组Teams内容：

1. 转到上Advanced eDiscovery中将保管人添加到的托管人案例，然后单击"集合 **"**。

2. 在" **集合"** 页上，选择 **"新建集合** > **""标准集合"**。

3. 键入一个 (集合) 和 (可选) 的名称。

4. 在 **"Ial 数据源"** 页上，单击 **"选择** 保管人"以选择已添加到案例的保管人。

   案例保管人列表显示在"选择保管 **人** "飞出页面上。

5. 选择一个或多个保管人，然后单击"添加 **"**。

   将特定保管人添加到集合后，将显示每个保管人的特定数据源的列表。 这些是向案例添加保管人时配置的数据源。 默认情况下，选择所有保管人数据源。 这包括Teams保管人关联的任何渠道或渠道。

   建议在收集内容时执行以下操作Teams操作：

   - 通过取消选中OneDrive保管人" ("列中的复选框，从集合范围内删除保管人OneDrive帐户) 。 这将阻止收集附加到一对一聊天和群聊的重复文件。 将草稿集合提交到审阅集时，会自动从集合中发现的每个对话收集云附件。 通过使用此方法 (OneDrive 帐户作为集合) 的一部分，附加到 1：1 和群聊的文件将分组在共享的对话中。

   - 取消选中"其他网站"列中的复选框，以删除SharePoint共享或共享通道中共享的文件的网站。 这样做可消除收集附加到私人或共享频道对话的重复文件，因为这些云附件会在你提交草稿集合时自动添加到审阅集中，并分组到他们共享的对话中。

6. 如果之前按照步骤将内容添加Teams保管人数据源，可以跳过此步骤并选择"下一步 **"**。 否则，在"非查询数据源"向导页上，可以选择包含 Teams 内容的非查询数据源，这些内容您可能已添加到案例以在集合中搜索。

7. 如果之前按照步骤将内容添加Teams保管人数据源，可以跳过此步骤并选择"下一步 **"**。 否则，在 **"其他位置"** 向导页上，您可以添加其他数据源以在集合中搜索。 例如，可以添加未添加为未添加为托管数据源或非托管数据源的团队的邮箱和网站。 否则，请选择 **"下一步** "并跳过此步骤。

8. 在"**条件** 向导"页上，将搜索查询配置为从Teams向导页上指定的数据源收集内容。 可以使用各种关键字和搜索条件来缩小集合的范围。 有关详细信息，请参阅生成 [集合的搜索查询](building-search-queries.md)。

   为了帮助确保最全面的聊天Teams对话集合 (包括一对一、组和频道) 使用"类型"条件并选择"即时消息"**选项**。 我们还建议包括日期范围或多个关键字，以将集合的范围缩小到与调查相关的项目。 下面是使用"类型"和"日期"选项 **的示例查询****的** 屏幕截图：

   ![用于收集内容Teams查询。](..\media\TeamsConditionsQueryType.png)

9. 在" **保存草稿或** 收集向导"页上，执行下列操作之一，具体取决于是创建草稿集合还是将集合提交到审阅集。

   ![保存草稿集合或提交集合。](..\media\TeamsDraftCommitCollection.png)

   1. **将集合另存为草稿**。 选择此选项可创建草稿集合。 如前所述，草稿集合不会将集合结果添加到审阅集。 它返回与集合范围内数据源的搜索查询相匹配的搜索结果的估计值。 这样，您有机会查看 [集合统计信息和报告[ (collection-statistics-reports.md) ]，并编辑和重新运行草稿集合。 如果对草稿集合的结果感到满意，可以提交到审阅集。 有关详细信息，请参阅 [创建草稿集合](create-draft-collection.md)。

   2. **收集项目并添加到审阅集**。 选择此选项可运行集合，然后将结果添加到审阅集。 可以将该集合添加到新的或现有的审阅集。 默认情况下，选择用于收集上下文Teams对话消息 (也称为对话线程) 以及收集云附件的选项，且无法取消选择。 由于最初为内容创建案例时所使用的新大小写格式，这些选项Teams应用。 有关将集合提交到审阅集详细信息，请参阅 [将草稿集合提交到审阅集](commit-draft-collection.md)。

10. 配置完集合后，提交集合以创建草稿集合或收集项目并将其添加到审阅集。

   在将集合添加到审阅集的过程完成时，"集合"选项卡上的集合的状态值将设置为 **"已提交"**。

## <a name="review-teams-content-in-a-review-set"></a>查看Teams审阅集内的内容

将内容Teams集合添加到审阅集后，下一步是查看内容，了解其与调查的相关性，并在必要时进行剔除。 查看聊天内容的一个重要Teams是了解在Advanced eDiscovery聊天Teams附件时如何处理聊天对话和附件。 对内容Teams处理会导致以下三个结果：

- **[分组](#grouping)**。 邮件、帖子和回复Teams对话组合在一起并呈现在审阅集。 这还包括聊天对话中的附件在对话中提取和分组。

- **[脚本对话线程](#transcript-conversation-threading)**。 如何Advanced eDiscovery对话中要收集的其他内容，以提供与集合条件匹配的项的上下文。

- **[重复数据删除](#deduplication-of-teams-content)**。 如何处理Advanced eDiscovery内容Teams重复。

- **[元数据](#metadata-for-teams-content)**。 元数据属性Advanced eDiscovery并添加到Teams审阅集后添加到内容。

了解分组、对话线程、重复数据删除Teams元数据将帮助您优化对内容进行审阅Teams分析。 本节还具有[查看审阅Teams内容的技巧](#tips-for-viewing-teams-content-in-a-review-set)。

### <a name="grouping"></a>分组

当来自Teams对话的内容添加到审阅集时，来自对话的消息、帖子和回复将聚合在 HTML 脚本文件中。 单个聊天对话可以有多个脚本文件。 这些脚本文件的一个重要功能是，将Teams内容呈现为连续对话，而不是以单个 (或单独的) 消息。 这有助于为符合上一步中集合的搜索条件的项目提供上下文，并减少收集到审阅集中的项目数。 脚本和相关项目可以按系列或对话 *进行分组*。 同一系列中的项将具有相同的 **FamilyId** 元数据属性的值。 同一对话中的项目将具有相同的 **ConversationId** 元数据属性的值。

下表介绍了聊天内容的不同类型的Teams如何按系列和对话进行分组。

|Teams内容类型|按系列分组|按对话分组|
|---|---|---|
|Teams一对一和群聊|脚本及其所有附件和提取的项目共享相同的 **FamilyId**。 每个脚本都有唯一 **的 FamilyId**。|同一对话中所有转录文件及其系列项目共享同一 **ConversationId**。 这包括以下项目： <ul><li>共享同一 **ConversationId** 的所有脚本的所有提取的项目和附件。</li><li>同一聊天对话的所有脚本</li><li>每个脚本的所有保管人副本</li><li>来自同一聊天对话的后续集合的脚本</li></ul> <br/> 对于Teams一对一和群聊对话，您可能有多个脚本文件，每个脚本文件对应于对话中的不同时间范围。 由于这些脚本文件来自与相同参与者的同一对话，因此它们共享相同的 **ConversationId**。|
|标准、私人和共享频道聊天|每个帖子以及所有回复和附件都保存到其自己的脚本中。 此脚本及其所有附件和提取的项目共享相同的 **FamilyId**。|每个帖子及其附件和提取的项目都有唯一 **的 ConversationId**。 如果有来自同一帖子的后续集合或新回复，则从这些集合生成的增量脚本也将具有相同的 **ConversationId**。|

使用 **审阅** 集的命令栏中的"组"控件，Teams系列或对话分组的内容。

![命令栏中的组控件。](..\media\TeamsGroupControl.png)

- 选择 **"组系列附件**"Teams按系列分组的内容。 每个脚本文件都显示在审阅集项列表中的一行上。 附件嵌套在项目下。

- 选择 **"Teams或Yammer对话**"以查看Teams按对话分组的内容。 每个对话都显示在审阅集项目列表中的一行上。 脚本文件和附件嵌套在顶级对话下。

> [!NOTE]
> 云附件按它们显示的对话进行分组。 通过分配与文件所附加到的邮件的脚本文件相同的 **FamilyId** 和消息显示的对话的 **ConversationId** ，可以完成此分组。 这意味着，如果云附件附加到不同的对话，则可能会将多个云附件副本添加到审阅集。

#### <a name="viewing-transcript-files-for-conversations"></a>查看对话的脚本文件

查看审阅集的脚本文件时，某些消息以紫色突出显示。 突出显示的邮件取决于您正在查看的脚本的保管人副本。 例如，在 User4 和 User2 之间的一对一聊天中，查看从 User4 邮箱收集的脚本时，User4 发布的消息会以紫色突出显示。 查看同一对话的 User2 脚本时，User2 发布的消息以紫色突出显示。 此突出显示行为基于相同的Teams体验，其中用户的文章在客户端中以紫色Teams突出显示。

以下屏幕截图显示了 Teams 客户端中的会话示例和审阅集内同一对话的脚本文件。 脚本文件中紫色突出显示表示脚本从 User2 的邮箱中收集。

##### <a name="conversation-in-teams-client"></a>客户端Teams对话

![审阅集的脚本文件中显示的对话。](..\media\TeamsClient1.png)

##### <a name="conversation-in-transcript-file"></a>脚本文件中的对话

![客户端中显示的相同Teams对话。](..\media\TeamsTranscript1.png)

### <a name="transcript-conversation-threading"></a>脚本对话线程

新案例格式的对话线程功能Advanced eDiscovery可帮助你识别与调查相关的项目相关的上下文内容。 此功能生成不同的对话视图，其中包括在收集期间匹配搜索查询的项之前和之后的聊天消息。 此功能允许你高效快速地查看名为 (*对话) 对话* Microsoft Teams。 如前文所介绍，聊天对话在 HTML 脚本文件中重新构建Advanced eDiscovery内容Teams审阅集时。

下面是 Advanced eDiscovery 用于包含其他消息和回复脚本文件的逻辑，这些消息和回复脚本文件提供与集合查询 *(（称为* 响应项目) 收集内容时Teams匹配）。 不同的线程行为基于聊天类型和用于收集响应项目的搜索查询。 有两种常见的集合方案：

- 使用搜索参数（如关键字和 property：value 对）的查询

- 仅使用日期范围的查询

|Teams内容类型|使用搜索参数的查询|具有日期范围的查询|
|---|---|---|
|Teams一对一和群聊|响应项目在响应项目前 12 小时和 12 小时后发布的邮件在单个脚本文件中与响应项目分组在一起。|24 小时窗口中的邮件在单个脚本文件中进行分组。|
|标准、专用和共享Teams频道聊天|每个包含响应项目和所有相应回复的帖子都分组在一个脚本文件中。|每个包含响应项目和所有相应回复的帖子都分组在一个脚本文件中。|

### <a name="deduplication-of-teams-content"></a>重复数据删除Teams内容

以下列表介绍了在将内容收集到审阅 (时) 删除重复Teams重复行为。

- 添加到审阅集的每个脚本文件应是存储于数据位置的内容的一对一映射。 这意味着Advanced eDiscovery不会收集Teams审阅集的任何内容。 如果已在审阅集中收集聊天消息，Advanced eDiscovery不会将同一数据位置中的相同消息添加到后续集合中的审阅集中。

- 对于一对一和群聊，消息副本存储在每个对话参与者的邮箱中。 将使用不同的元数据收集不同参与者邮箱中的同一对话的副本。 因此，会话的每个实例都被视为唯一的，并进入单独的脚本文件中审阅集。 因此，如果一对一或群组聊天的所有参与者均添加为案例的保管人并包含在集合范围内，则相同用户) 的每个脚本 (的副本将添加到审阅集，并使用相同的 **ConversationId** 进行分组。 每个副本都与相应的保管人关联。 **提示**：审阅集列表中的 **Custodian** 列标识相应脚本文件的保管人。

- 在同一对话中的项目的后续集合中，仅将之前未收集的增量内容添加到审阅集，并分组 (，方式为将同一 **ConversationId**) 与以前从同一对话收集的脚本共享。 下面是此行为的一个示例：

   1. 集合 A 在 User1 和 User2 之间的对话中收集邮件并添加到审阅集。

   2. 集合 B 从同一对话中收集邮件，但自运行集合 A 以来，User1 和 User2 之间有新邮件。

   3. 只有集合 B 中的新邮件会添加到审阅集中。 这些消息将添加到单独的脚本文件中，但新脚本通过同一 **ConversationId** 与集合 A 中的脚本分组。

   此行为适用于聊天Teams类型。

### <a name="metadata-for-teams-content"></a>内容Teams元数据

在包含数千或数百万个项目的大型审阅集内，可能很难将审阅范围缩小到Teams内容。 为了帮助你重点关注内容Teams，有一些特定于内容Teams属性。 可以使用这些属性来组织审阅列表中的列，并配置筛选器和查询以[](review-set-search.md)优化对内容Teams审阅。 当您从 Advanced eDiscovery 导出内容时，Teams元数据属性也包括在内，以帮助您组织和查看导出后或第三方电子数据展示工具中的内容。

下表介绍了内容内容的元数据Teams属性。

|Metadata 属性|说明|
|---|---|
|ContainsEditedMessage|指示脚本文件是否包含已编辑的邮件。 查看转录文件时，将标识已编辑的消息。|
|ConversationId|标识项目关联的对话的 GUID。 同一对话中的脚本文件和附件对此属性的值相同。|
|对话名称|脚本文件或附件关联的对话的名称。 对于Teams 1：1 和群聊，此属性的值是连接会话的所有参与者的 UPN。 例如，`User3 <User3@contoso.onmicrosoft.com>,User4 <User4@contoso.onmicrosoft.com>,User2 <User2@contoso.onmicrosoft.com>`。 Teams频道 (、私人和共享) 聊天使用以下格式作为对话名称：`<Team name>,<Channel name>`。例如，`eDiscovery vNext, General`。|
|ConversationType|指示团队聊天的类型。 对于Teams 1：1 和群聊，此属性的值为 `Group`。 对于标准、私人和共享频道聊天，值为 `Channel`。|
|Date|脚本文件中第一封邮件的时间戳。|
|FamilyId|标识聊天对话的脚本文件的 GUID。 附件的此属性的值与包含文件所附加到的邮件的转录文件相同。|
|FileClass|指示该类型的内容。 来自Teams项具有值 `Conversation`。 相比之下，Exchange电子邮件具有值 `Email`。|
|MessageKind|邮件类型属性。 Teams内容具有值 `microsoftteams , im`。|
|收件人|在脚本对话中收到消息的所有用户的列表。|
|TeamsChannelName|脚本Teams的频道名称。|

有关元数据属性Advanced eDiscovery的说明，请参阅文档中[的文档元数据Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md)。

## <a name="export-teams-content"></a>导出Teams内容

查看并剔除审阅Teams的内容后，可以导出包含响应调查的内容的转录文件。 对于内容，没有任何特定的导出Teams设置。 每个脚本文件导出为 HTML 邮件文件。 此文件还包含隐藏的 CDATA 标记，其中包含单个聊天消息的所有元数据。 导出内容时，包含上一节中讨论的Teams属性。  

每个脚本文件在加载文件中引用，并且可以使用加载文件的 Export_native_path 字段中的相对路径找到。 脚本文件位于根导出文件夹的 Conversations 文件夹中。

## <a name="tips-for-viewing-teams-content-in-a-review-set"></a>使用技巧查看Teams审阅集内容的内容

下面是查看审阅集内内容Teams提示和最佳做法。

- 使用 **命令栏中** 的"自定义列"控件可添加和组织列，以优化对Teams审阅。

  ![使用"编辑列"飞出页可添加、删除和组织列。](..\media\EditReviewSetColumns.png)

   您可以添加和删除对内容Teams列。 You can also sequence the order of columns by dragging and dropping them in the **Edit column** flyout page. 还可以对列进行排序，以Teams排序列的类似值对内容进行分组。

- 有助于查看邮件内容的有用Teams **包括 Custodian**、**Recipients** 和 **File type** 或 **Message kind**。

- 使用[与](review-set-search.md)Teams属性的筛选器快速显示Teams内容。 存在针对上一节中所述大部分元数据属性的筛选器。

## <a name="reference-guide"></a>参考指南

下面是使用 Advanced eDiscovery for Microsoft Teams 的快速参考指南。 本指南总结了使用 Advanced eDiscovery保留、收集、审阅和导出内容的关键Microsoft Teams。

![有关使用 Advanced eDiscovery for Microsoft Teams 的参考指南缩略图。](../media/AeDTeamsReferenceGuide-thumbnail.png)

[下载为 PDF 文件](https://download.microsoft.com/download/9/e/4/9e4eec6f-c476-452f-b414-4bd4b5c39dca/AeDTeamsReferenceGuide.pdf)
