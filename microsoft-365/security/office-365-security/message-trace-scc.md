---
title: 安全与合规中心内的消息跟踪
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 管理员可以使用安全与合规中心中的&跟踪来了解消息发生了什么。
ms.openlocfilehash: c6e1f8f9280c84ab6ff6a1572d902ed1d4d4caa3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827047"
---
# <a name="message-trace-in-the-security--compliance-center"></a>安全与合规中心内的消息跟踪

## <a name="message-trace-features"></a>邮件跟踪功能

安全邮件在&邮件通过 Exchange Online 组织时，遵循电子邮件。 您可以确定邮件是否被接收、拒绝、延迟或由服务传递。 它还显示邮件在到达最终状态之前对邮件所执行的操作。

安全与合规中心中的&跟踪改进了 Exchange 管理中心网站原始 (的) 。 您可以使用邮件跟踪中的信息有效回答有关邮件所发生事情的用户问题、解决邮件流问题并验证策略更改。

> [!NOTE]
>
> - 若要执行邮件跟踪，您需要是组织管理角色组、合规性管理或技术支持角色组的成员。 有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。
>
> - 结果中显示的邮件的最大数量取决于您选择的报告类型 (请参阅" [选择报告类型"](#choose-report-type) 部分，了解详细信息页面) 。 Exchange Online PowerShell [中的 Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) cmdlet 或独立 EOP PowerShell 将返回结果中的所有邮件。

## <a name="open-message-trace"></a>打开邮件跟踪

1. 打开"&安全与合规中心 <https://protection.office.com> "。

2. 展开 **"邮件流**"，然后选择"邮件**跟踪"。**

## <a name="message-trace-page"></a>邮件跟踪页面

从此处，你可以通过单击"开始跟踪"按钮 **启动新的默认** 跟踪。 这将搜索过去两天的所有发件人和收件人的所有邮件。 或者，您可以使用可用查询类别之一来运行这些查询，或者按自己的查询作为起点：

- **默认查询**：Microsoft 365 提供的内置查询。

- **自定义查询：** 组织中的管理员保存的查询以供将来使用。

- **自动保存的查询**：最近十个最近运行的查询。 此列表可以让你从中断位置轻松地开始。

在此页面上，还 **是你已** 提交请求的可下载报告部分，以及报告本身（如果有可供下载）。

## <a name="options-for-a-new-message-trace"></a>新邮件跟踪选项

### <a name="filter-by-senders-and-recipients"></a>按发件人和收件人进行筛选

默认值是**所有发件人和****所有收件人**，但可以使用下列字段筛选结果：

- **由这些人员**：单击此字段可从组织中选择一个或多个发件人。 还可以开始键入名称，然后按您键入的内容筛选列表中的项，这与搜索页的表现在外观很相当。

- **对这些用户**：单击此字段可选择组织中的一个或多个收件人。

> [!NOTE]
> 您还可以键入外部发件人和收件人的电子邮件地址。 例如，支持通配 (通 `*@contoso.com`) ，但您不能同时在同一字段中使用多个通配符条目。 <br/><br/> 您可粘贴多个发件人或收件人列表，中以分号 `;` () 。 空格 `\s` () 、回车符或下 `\r` () 或下 `\n` () 。

### <a name="time-range"></a>时间范围

默认值为 2 天 **，** 但可以指定长达 90 天的日期/时间范围。 在使用日期/时间范围时，请考虑以下问题：

- 默认情况下，使用时间线在 **滑块视图中** 选择时间范围。 只能选择显示的日期或时间设置。 尝试选择两个值之间的间隙，会将开始/结束气泡与最匹配的显示设置相加。

  ![安全与合规中心新邮件跟踪中的滑&时间范围](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  但是，您还可以切换到自定义**视图，** 在该视图中你可以指定**开始日期****和结束**日期值 (包括时间) ），还可以选择日期/时间范围**Time zone**的时区。 请注意， **时区** 设置同时适用于查询输入和查询结果。

  ![安全与合规中心新邮件跟踪中的&时间范围](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  10 天或更短时，可将结果作为"摘要报告" **即时** 提供。 如果你指定的时间范围甚至少于 10 天，结果将延迟，因为它们只能作为可下载的 CSV 文件提供， (**增强**摘要或扩展报告) 。 **Extended**

  有关其他报告类型的详细信息，请参阅本主题 [中的"选择报告](#choose-report-type) 类型"部分。

  **注意**：已使用存档的邮件跟踪数据准备了增强的摘要报告和扩展报告，在下载报告之前可能需要几个小时。 根据其他管理员也同时提交了报告请求的数量，您可能还会注意到一些延迟，然后再处理您的排队的请求。

- 在滑块视图中 **保存查询可** 保存相对时间范围 (例如，从今天开始的 3 天时) 。 在自定义视图中保存 **查询可** 节省绝对日期/时间范围 (例如，2018-05-06 13：00 至 2018-05-08 18：00) 。

### <a name="more-search-options"></a>更多搜索选项

#### <a name="delivery-status"></a>传递状态

您可以将默认值 **保持选中状态** ，或者你可以选择以下值之一来筛选结果：

- **已发送**：该邮件已成功送达到目标。

- **挂起**：正尝试或重新尝试传递邮件。

- **展开**：在传递至组中的单个成员之前展开通讯组收件人。

- **失败**：未传递邮件。

- **已隔离：邮件**被 (如垃圾邮件、批量邮件或网络钓鱼邮件) 。 有关详细信息，请参阅 [EOP 中隔离的电子邮件](quarantine-email-messages.md)。

- **已被筛选为**垃圾邮件：已将邮件标识为垃圾邮件，被拒绝 (隔离) 。

- **获取状态：** 最近是由 Microsoft 365 收到的，但尚未使用其他任何状态数据。 在几分钟内重新查看。

**注意**："**挂起"、"****隔离"** 和"**筛选为垃圾邮件"** 的值仅可用于少于 10 天的搜索。 此外，实际传递状态与报告的传递状态之间可能存在 5 到 10 分钟的延迟。

#### <a name="message-id"></a>邮件 ID

这是 Internet 邮件 ID (在邮件头的 **Message-ID：** 头字段) 中找到，亦称为"客户端 ID"列表。 用户可以为您提供此值来调查特定邮件。

该值在邮件生存期内是常量。 对于在 Microsoft 365 或 Exchange 中创建的邮件，该值的格式为，包括以所使用的角 `<GUID@ServerFQDN>` \< \> () 。 例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。 其他邮件系统可能使用不同的语法或值。 此值应唯一，但并非所有电子邮件系统都严格遵循此要求。 如果 **来自外部源** 的传入邮件不存在或为空，则为该保留的值是任意值。

使用消息 **ID** 筛选结果时，请确保包含完整字符串，包括任何角括号。

#### <a name="direction"></a>Direction

您可以将默认值设置为 **"所有"默认值，** 或者 **选择发送到您** 组织 (收件人的入站邮件 **) 或从** 组织 (中的用户发送的出站邮件) 来筛选结果。

#### <a name="original-client-ip-address"></a>原始客户端 IP 地址

你可以通过客户端 IP 地址处理结果，调查发送大量垃圾邮件或恶意软件的受损计算机。 尽管邮件可能来自多个发件人，但很可能由同一台计算机生成所有邮件。

**注意**：客户端 IP 地址信息仅可查看 10 天，并且仅在**可下载**的 CSV**Extended**文件的增强 (报告或扩展报告) 。

### <a name="choose-report-type"></a>选择报表类型

可用的报告类型包括：

- **摘要**：如果时间范围小于 10 天，并且不需要其他筛选选项，则可用。 单击"搜索"后，结果将立即 **可用**。 报告最多返回 20000 个结果。

- **增强摘要**或**扩展**：这些报告仅可下载为可下载的 CSV 文件，并需要以下一个或多个筛选选项（与时间范围无处不论 **）：这些人员**、**发送给这些人员**、或**消息 ID。** 可以为发件人或收件人使用通配 (例如 \* ，@contoso.com) 。 增强摘要报告将返回多达 50000 个结果。 "扩展"报告最多返回 1000 个结果。

**注意**：

- 增强的摘要和扩展报告是使用存档的邮件跟踪数据准备的，并且在下载报告之前可能需要几个小时。 根据其他管理员也同时提交了报告请求的数量，您也可能会注意到在处理队列中的请求之前出现了延迟。

- 虽然可以为任何日期/时间范围选择增强摘要或扩展报告，但通常，最后四小时存档的数据还未可用于这两种类型的报告。

单击" **下一步**"时，会看到摘要页，其中列出了所选的筛选选项、该报告的唯一 (可编辑) 标题以及在邮件跟踪完成后收到通知的电子邮件地址 (也可编辑，并且必须是组织的接受的域) 之一。 单击 **"准备** 报告"提交邮件跟踪。 在主 **"邮件跟踪** "页面上，您可以在"可下载的报告"部分 **看到报告的** 状态。

有关在不同报告类型中返回的信息的详细信息，请参阅下一节。

## <a name="message-trace-results"></a>邮件跟踪结果

不同的报告类型返回不同级别的信息。 不同报告中提供的信息在以下各节中进行了介绍。

### <a name="summary-report-output"></a>摘要报告输出

运行邮件跟踪后，将按最近一次跟踪的降序排序结果，按降序 (排序) 。

![安全与合规中心内的邮件跟踪的摘要&结果](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

摘要报告包含以下信息：

- **日期**：服务收到邮件的日期及时间（使用配置的 UTC 时区）。

- **发件人**：发件人完全* (域* @ *domain*) 。

- **收件人**：收件人电子邮件地址。 对于发送给多个收件人的邮件，每个收件人每行对应一行。 如果收件人是通讯组、动态通讯组或已启用邮件的安全组，则该组将第一个收件人，然后组中的每个成员分别位于单独的行。

- **Subject：** 邮件主题的前 256 个字符 **：** 字段。

- **状态**："送达状态"部分中 [描述了这些](#delivery-status) 值。

默认情况下，前 250 个结果已加载并就可用。 向下滚动时，随后会有轻微暂停，因为会加载下一批结果。 可以单击"全部加载"，以将**Load all**所有结果加载到最多 10，000 个，而不是滚动。

您可以单击列标题，按该列中的值以升序或降序对结果进行排序。

可以单击 **"筛选结果** "，按一个或多个列筛选结果。

选择一个或多个行后，可通过单击"导出结果"，然后选择"**导出**所有结果、导出**已**加载结果"或"导出**Export loaded results****"选择来导出结果**。

#### <a name="find-related-records-for-this-message"></a>查找此邮件的相关记录

相关邮件记录是共享同一个邮件 ID 的记录。 请记住，甚至在两个人员之间发送的一封邮件也可以生成多个记录。 邮件受通讯组扩展、转发、邮件流规则 (也称为传输规则 (等）影响的) 记录数目增加。

选中行的复选框后，可以通过以下方法查找邮件的相关记录：单击出现的 **"查找相关**按钮"，或通过选择"**此**邮件索引的更多查找 ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **相关) 。**

有关邮件 ID 的详细信息，请参阅本主题前面的"邮件 ID"部分。

#### <a name="message-trace-details"></a>邮件跟踪详细信息

在摘要报告输出中，可以使用下列任一方法查看有关邮件的详细信息：

- 选择与 (行之外的任何其他行中的任意) 。

- 选中此行的复选框，然后单击"更多选项**更多选项'** ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **更多选项' 邮件详细信息"。**

   ![在安全与合规中心内双击摘要报告邮件跟踪中的&的详细信息](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

邮件跟踪详细信息包含摘要报告中不存在的以下附加信息：

- **邮件事件**：本节包含的分类有助于对邮件执行的操作进行分类。 **你可能会遇到的一些更** 有趣的事件包括：

  - **接收**：服务已收到邮件。

  - **发送**：服务发送邮件。

  - **失败**：邮件无法送达。

  - **传递**：邮件已送达到邮箱。

  - **展开**：邮件已发送到展开的通讯组。

  - **转**移：由于内容转换、邮件收件人限制或代理原因，收件人被移动到分条邮件。

  - **延迟**：邮件传递延迟，稍后可能重试。

  - **已解决**：邮件已基于 Active Directory 查找重定向到新的收件人地址。 当发生这种情况时，原始收件人地址会被列在邮件跟踪中的单独一行，包括邮件的最终传递状态。

  注意：

  - 一封成功送达的邮件将在邮件跟踪中 **生成** 多个事件条目。

  - 此列表并不试图十分混解。 有关更多事件的说明，请参阅 [邮件跟踪日志中的事件类型](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)。 请注意，此链接Exchange Server (Exchange) 主题。

- **详细信息**：此节包含下列详细信息：

  - **邮件 ID：** 此值在本主题前面的"邮件 [ID"](#message-id) 部分中说明。 例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。

  - **邮件大小**

  - **自 IP：** 发送邮件的计算机的 IP 地址。 对于从 Exchange Online 发送的出站邮件，该值是空值。

  - **To IP：** 该服务尝试递送邮件的 IP 地址或地址。 如果邮件有多个收件人，则会显示这些内容。 对于发送到 Exchange Online 的入站邮件，该值是空值。

### <a name="enhanced-summary-reports"></a>增强的摘要报告

最近 (已) 汇总报告中提供"开始"邮件 **跟踪** 的"可下载报告"部分。 报告中包含以下信息：

- **origin_timestamp：** <sup>*</sup> 服务使用配置的 UTC 时区获取邮件的最初日期和时间。

- **sender_address：** 发件人的电子邮件地址 (*域* @ *) 。*

- **Recipient_status：** 向收件人传递邮件的状态。 如果邮件发送至多个收件人，将显示所有收件人和每个收件人的相应状态，格式如下 \<*email address*\> ## \<*status*\> ：。 例如：

  - **##Receive，发送** 表示服务已接收邮件，并发送到预定的目标地址。

  - **##Receive，失败** 表示服务已接收邮件，但传递到预定的目标失败。

  - **##Receive，** 传递表示服务已接收邮件，并且传递给收件人的邮箱。

- **message_subject：** 邮件"主题"字段中的前 256 **个** 字符。

- **total_bytes：** 邮件大小（以字节为单位），包括附件。

- **message_id：** 此值在本主题前面介绍的"邮件 [ID"](#message-id) 部分中所述。 例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。

- **network_message_id：** 唯一的邮件 ID 值，因分类或通讯组扩展而创建，在所有邮件副本中均保持有效。 示例值为 `1341ac7b13fb42ab4d4408cf7f55890f` 。

- **original_client_ip：** 发件人客户端的 IP 地址。

- **方向性：** 指示是发送的是发送到组织的入站 (1) 还是从组织发送出站邮件 (2) 步。

- **connector_id：** 源或目的地连接器的名称。 有关 Exchange Online 中的连接器的详细信息，请参阅 [在 Office 365 中使用连接器配置邮件流](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

- **delivery_priority：** <sup>*</sup> 邮件发送的优先级**是高、****低****还是普**通优先级。

<sup>*</sup>这些属性只提供于增强摘要报告。

### <a name="extended-reports"></a>扩展的报表

邮件 (开始) 中的"可下载报告" **部分** 提供已完成的已完成报告。 增强报告的大部分信息都适用于扩展报告中的 (例如，**除origin_timestamp和delivery_priority) 。** **delivery_priority** 下面其他信息只适用于扩展报告：

- **client_ip：** 提交邮件的电子邮件服务器或消息客户端的 IP 地址。

- **client_hostname：** 提交邮件的电子邮件服务器或消息客户端的主机名或 FQDN。

- **server_ip：** 源或目标服务器的 IP 地址。

- **server_hostname：** 目标服务器的主机名或 FQDN。

- **source_context：** 与源字段关联的 **额外** 信息。 例如：

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **source：** 负责事件的 Exchange Online 组件。 例如：

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id**：这些对应于此 **邮件部分** 的"查找相关记录"中 [说明的](#find-related-records-for-this-message) Message 事件值。

- **internal_message_id：** 由当前正在处理该邮件的 Exchange Online 服务器分配的邮件标识符。

- **recipient_address：** 邮件收件人的电子邮件地址。 多个电子邮件地址通过分号字符 (;) 分隔。

- **recipient_count：** 邮件中的收件人总数。

- **related_recipient_address：** 与 `EXPAND` 此 `REDIRECT` 一起 `RESOLVE` 使用，使用和事件显示与该邮件相关联的其他收件人电子邮件地址。

- **参考**：此字段包含特定类型事件的其他信息。 例如：

  - **DSN：** 包含报告链接，如果 **DSN 是在事件发生** 之后生成的，则 message_id该报告链接为相关传递状态通知 (也称为 DSN、未送达报告、NDR 或退回邮件消息) 。 如果这是 DSN 邮件，则该 **字段message_id** 为其生成 DSN 的原始邮件的有效值。

  - **EXPAND**： **包含related_recipient_address** 的电子邮件的字段值。

  - **RECEIVE**：如果邮件 **message_id** 由其他过程（如收件箱规则箱 (过程）生成，可能包含相关) 。

  - **SEND**：包含 **任意 internal_message_id** DSN 邮件的 internal_message_id 值。

  - **TRANSFER：****包含被分 (** 外的邮件的internal_message_id个值，例如通过内容转换、邮件收件人限制或代理) 。

  - **MAILBOXRULE**：包含 **internal_message_id** 收件箱规则生成出站邮件的入站邮件的字段值。

    对于其他类型的事件，此字段通常为空。

- **return_path：** 由发送邮件的 MAIL **FROM** 命令所指定的返回电子邮件地址。 尽管此字段从不为空，但它可以有表示为的空发件人地址值 `<>` 。

- **message_info：** 有关邮件的其他信息。 例如：

  - 针对和事件的日期-时间（UTC） `DELIVER` `SEND` 消息。 开始日期-时间是邮件第一次进入 Exchange Online 组织的时间。 UTC 日期-时间以 ISO 8601 日期时间格式表示 `yyyy-mm-ddThh:mm:ss.fffZ` ：，其中 `yyyy` = 年， `mm` = 月， `dd` = 日， 指示时间 `T` 组件的开始， `hh` = 小时， = 分钟， = 秒， = 秒的分数， `mm` `ss` 表示表示 UTC 的另 `fff` `Z` `Zulu` 一种方式。

  - 身份验证错误。 例如，您可能看到 `11a` 身份验证出错时所使用的验证的值和身份验证类型。

- **tenant_id：** 一个 GUID 值，表示 Exchange Online (例如 `39238e87-b5ab-4ef6-a559-af54c6b07b42` ，) 。

- **original_server_ip：** 原始服务器的 IP 地址。

- **custom_data：** 包含与特定事件类型相关的数据。 有关详细信息，请参阅以下各部分。

#### <a name="custom_data-values"></a>custom_data值

由 **custom_data** Exchange `AGENTINFO` Online 代理使用事件的索引字段来记录邮件处理详细信息。 以下部分中介绍了一些更有趣的代理。

#### <a name="spam-filter-agent"></a>垃圾邮件筛选器代理

**"custom_data**以垃圾邮件筛选器 `S:SFA` 代理开始的邮件值。 下表介绍了关键详细信息：

****

|值|说明|
|---|---|
|`SFV=NSPM`|邮件被标记为非垃圾邮件并发送给预期收件人。|
|`SFV=SPM`|邮件被反垃圾邮件筛选功能和 (内容筛选功能）被) 。|
|`SFV=BLK`|跳过筛选但阻止邮件，因为它是由已阻止发件人发送。|
|`SFV=SKS`|邮件在被反垃圾邮件筛选处理之前被标记为垃圾邮件。 这包括符合以下邮件流程规则条件（也称为传输规则）的邮件：自动将邮件标记为垃圾邮件并规避其他所有筛选。|
|`SCL=<number>`|有关不同的 SCL 值及其含义的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。|
|`PCL=<number>`|邮件的仿冒可能性等级 (PCL) 值。可按照[垃圾邮件可信度](spam-confidence-levels.md)中介绍 SCL 值的方式对这些值做出解释。  |
|`DI=SB`|已阻止邮件发件人。|
|`DI=SQ`|邮件已隔离。|
|`DI=SD`|邮件已删除。|
|`DI=SJ`|邮件已发送至收件人的"垃圾邮件"文件夹。|
|`DI=SN`|邮件已通过正常出站传送池路由。|
|`DI=SO`|邮件已通过高风险传送池路由。 有关详细信息，请参阅[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)。|
|`SFS=[a]|SFS=[b]`|说明匹配此垃圾邮件规则。|
|`IPV=CAL`|邮件已获得垃圾邮件筛选器的允许，因为 IP 地址已在连接筛选器的 IP 允许列表中指定。|
|`H=<EHLOstring>`|连接电子邮件服务器的 HELO 或 EHLO 字符串。|
|`PTR=<ReverseDNS>`|发送 IP 地址的 PTR 记录，也被称为反向 DNS 地址。|
|

筛选 **custom_data** 如下所示的邮件的示例搜索值：

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>恶意软件筛选器代理

**"custom_data**数值来自 `S:AMA` 恶意软件筛选器代理。 下表介绍了关键详细信息：

****

|值|说明|
|---|---|
|`AMA=SUM|v=1|` 或 `AMA=EV|v=1`|已确定此邮件包含恶意软件。 `SUM` 指示恶意软件可能已由任意数量的引擎检测到。 `EV` 指示特定引擎检测到恶意软件。 引擎检测到恶意软件后，将触发后续操作。|
|`Action=r`|邮件已被替换。|
|`Action=p`|邮件已被忽略。|
|`Action=d`|邮件已被延迟。|
|`Action=s`|邮件已删除。|
|`Action=st`|邮件已被忽略。|
|`Action=sy`|邮件已被忽略。|
|`Action=ni`|邮件已被拒绝。|
|`Action=ne`|邮件已被拒绝。|
|`Action=b`|邮件已被阻止。|
|`Name=<malware>`|已检测到的恶意软件的名称。|
|`File=<filename>`|恶意软件中包含的文件名称。|
|

包含 **custom_data** 的邮件的示例用户示例如下所示：

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>传输规则代理

一 **custom_data** 值来自 `S:TRA` 邮件流规则代理，亦称为 (规则代理"的") 。 下表介绍了关键详细信息：

****

|值|说明|
|---|---|
|`ETR|ruleId=<guid>`|匹配的规则 ID。|
|`St=<datetime>`|规则匹配时的日期和时间（UTC 时间）。|
|`Action=<ActionDefinition>`|应用的操作。 有关可取操作的列表，请参阅 [Exchange Online 中的邮件流规则操作](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。|
|`Mode=<Mode>`|规则模式。 有效值为：<ul><li>**强制**：将强制实施规则的所有操作。</li><li>**在使用策略提示的情况下测试：** 将发送所有策略提示操作，但不会作用于其他强制实施操作。</li><li>**在不使用策略提示**的情况下测试：将在活动中列出日志文件但不会以任何方式通知发件人，也不会作用于强制实施操作。</li></ul>|
|

示例 **custom_data** 符合邮件流规则条件的邮件的示例如下：

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
