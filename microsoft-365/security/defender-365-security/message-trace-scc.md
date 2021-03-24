---
title: 安全与合规中心内的消息跟踪
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 管理员可以使用安全与合规中心&跟踪来了解邮件发生了什么。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 78a7a2bda41f721b9e2084615b9eca1e70cf1f35
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055213"
---
# <a name="message-trace-in-the-security--compliance-center"></a>安全与合规中心内的消息跟踪

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="message-trace-features"></a>邮件跟踪功能

安全与合规中心&跟踪电子邮件在通过 Exchange Online 组织时跟踪。 您可以确定服务是否接收、拒绝、延迟或传递了邮件。 它还显示在邮件达到最终状态之前对邮件采取的操作。

安全与合规&中心内的邮件跟踪功能在 (Exchange 管理中心和 EAC) 中提供的原始邮件跟踪功能) 。 您可以使用邮件跟踪中的信息有效回答用户有关邮件发生的情况的问题、解决邮件流问题并验证策略更改。

> [!NOTE]
>
> - 若要执行邮件跟踪，您必须是组织管理、合规性管理或技术支持角色组的成员。 有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。
>
> - 结果中显示的邮件的最大数量取决于您选择的报告类型 ("选择报告类型"部分了解详细信息) 。 [](#choose-report-type) Exchange Online PowerShell 或独立 EOP PowerShell 中的 [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet 在结果中返回所有邮件。

## <a name="open-message-trace"></a>打开邮件跟踪

1. 在 打开安全&合规中心 <https://protection.office.com> 。

2. 展开 **"邮件流**"，然后选择"**邮件跟踪"。**

## <a name="message-trace-page"></a>邮件跟踪页

从此处，可以通过单击"启动跟踪"按钮来 **启动新的默认** 跟踪。 这将搜索过去两天内所有发件人和收件人的所有邮件。 或者，您可以使用可用查询类别中的其中一个存储的查询，并像现在一样运行它们，或者将它们用作您自己的查询的起点：

- **默认查询**：Microsoft 365 提供的内置查询。

- **自定义查询**：由组织中管理员保存供将来使用的查询。

- **自动保存的查询**：最近运行的十个查询。 此列表使你能够轻松从你离开的地方继续操作。

此页面还包括针对已提交请求的可下载报告部分，以及可供下载时的报告本身。

## <a name="options-for-a-new-message-trace"></a>新邮件跟踪的选项

### <a name="filter-by-senders-and-recipients"></a>按发件人和收件人筛选

默认值为" **所有发件人"** 和" **所有** 收件人"，但可以使用以下字段筛选结果：

- **通过这些人员**：单击此字段以从组织选择一个或多个发件人。 还可以开始键入名称，列表中的项目将按键入的内容进行筛选，与搜索页面的行为方式很类似。

- **对于这些人员**：单击此字段可选择您的组织中的一个或多个收件人。

> [!NOTE]
>
> - 您还可以键入外部发件人和收件人的电子邮件地址。 支持通配符 (例如，) ，但不能同时在同一字段中使用多个 `*@contoso.com` 通配符条目。
>
> - 您可以粘贴多个发件人或收件人列表，这些列表用分号 `;` () 。 空格 `\s` () 、回车符 () 或 `\r` 下一 `\n` () 。

### <a name="time-range"></a>时间范围

默认值为 **2 天**，但可以指定最多 90 天的日期/时间范围。 使用日期/时间范围时，请考虑这些问题：

- 默认情况下，使用时间线在 **Slider** 视图中选择时间范围。 只能选择显示的一个或多个时间设置。 尝试选择一个介于两者之间的值将起始/结束气泡贴靠到最近显示的设置。

  ![安全与合规中心内新邮件跟踪中的滑块&范围](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  但是，您也可以切换到"自定义"视图，可在其中指定开始日期和结束日期值 (包括) ，还可以选择日期/时间范围的时区。  请注意， **时区** 设置适用于查询输入和查询结果。

  ![安全与合规中心内新邮件跟踪中的&范围](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  在 10 天或更近的时间，结果可立即作为摘要 **报告** 提供。 如果指定的时间范围甚至超过 10 天，结果将延迟，因为它们仅作为可下载的 CSV 文件 (增强摘要或扩展报告) 。  

  有关不同报告类型的信息，请参阅本文中的选择报告[](#choose-report-type)类型部分。

  > [!NOTE]
  > 增强摘要和扩展报告是使用存档的邮件跟踪数据准备的，可能需要几个小时才能下载报告。 根据多少其他管理员还在同一时间提交了报告请求，您可能还注意到在处理队列请求之前有延迟。

- 在 Slider 视图中 **保存** 查询可保存相对 (例如，从今天开始 3) 。 在 **自定义视图中保存** 查询可保存绝对日期/时间范围 (例如，2018-05-06 13：00 至 2018-05-08 18：00) 。

### <a name="more-search-options"></a>更多搜索选项

#### <a name="delivery-status"></a>传递状态

您可以将默认值 **"全部"** 保留为选中状态，也可以选择下列值之一来筛选结果：

- **已** 传递：邮件已成功传递到预期目标。

- **挂起**：正在尝试或重新尝试传递邮件。

- **展开**：在将通讯组收件人发送给该组的单个成员之前展开。

- **失败**：邮件未送达。

- **已隔离**：邮件被隔离 (垃圾邮件、批量邮件或网络钓鱼邮件) 。 有关详细信息，请参阅 [EOP 中的隔离电子邮件](quarantine-email-messages.md)。

- **筛选为垃圾邮件**：邮件被标识为垃圾邮件，并且被拒绝或阻止 (未隔离) 。

- **获取状态：** 此邮件最近由 Microsoft 365 接收，但尚没有其他状态数据可用。 请几分钟后重新检查。

> [!NOTE]
> 值 **Pending、Quarantined** 和 **Filter as spam** 仅适用于少于 10 天的搜索。 此外，实际和报告的传递状态之间可能有 5 到 10 分钟的延迟。

#### <a name="message-id"></a>邮件 ID

This is the internet message ID (also known as the Client ID) that's found in the **Message-ID：** header field in the message header. 用户可以为您提供此值以调查特定邮件。

该值在邮件生存期内是常量。 对于在 Microsoft 365 或 Exchange 中创建的邮件，该值的格式为 ，包括尖括号 `<GUID@ServerFQDN>` \< \> () 。 例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。 其他邮件系统可能使用不同的语法或值。 此值应该是唯一的，但并非所有电子邮件系统都严格遵循此要求。 如果 **Message-ID：** 头字段不存在或对于来自外部源的传入邮件为空，则分配一个任意值。

使用消息 **ID** 筛选结果时，请确保包含完整字符串，包括任何尖括号。

#### <a name="direction"></a>Direction

可以将默认值"全部"保留为选中状态，也可以选择"发送到组织中收件人的入站 **(** 邮件") 或"从组织用户发送的出站 **(** 邮件") 以筛选结果。

#### <a name="original-client-ip-address"></a>原始客户端 IP 地址

你可以按客户端 IP 地址提交结果，以调查发送大量垃圾邮件或恶意软件的黑客计算机。 虽然邮件可能看起来来自多个发件人，但同一台计算机很可能生成所有邮件。

> [!NOTE]
> 客户端 IP 地址信息仅在 10 天内可用，并且仅在增强摘要或扩展报告中可用， (可下载的 CSV) 。 

### <a name="choose-report-type"></a>选择报告类型

可用的报告类型包括：

- **摘要：** 如果时间范围小于 10 天且不需要其他筛选选项，则可用。 在单击"搜索"后，结果几乎会立即 **提供**。 报告最多返回 20000 个结果。

- **增强****摘要或扩展**：这些报告仅作为可下载的 CSV 文件提供，并且需要以下一个或多个筛选选项，而不考虑时间范围：按这些人员、收件人或邮件 **ID。** 您可以对发件人或收件人使用通配符 (例如 \* @contoso.com) 。 增强摘要报告最多返回 50000 个结果。 扩展报告最多返回 1000 个结果。

> [!NOTE]
>
> - 增强摘要和扩展报告是使用存档的邮件跟踪数据准备的，可能需要几个小时才能下载报告。 根据多少其他管理员还在同一时间提交了报告请求，你还可能会注意到排队请求开始处理之前有延迟。
>
> - 尽管您可以为任意日期/时间范围选择"增强摘要"或"扩展报告"，但通常，这两种类型的报告通常不会提供过去四小时的存档数据。
>
> - 可下载报告的最大大小为 500 MB。 如果可下载的报告超过 500 MB，则不能打开 Excel 或记事本中的报表。

单击"下一步"时，将显示一个摘要页，其中列出了所选的筛选选项、报告的唯一 (可编辑) 标题，以及邮件跟踪完成 (且可编辑且必须在你的组织的接受域) 之一中时收到通知的电子邮件地址。 单击 **"准备报告** "提交邮件跟踪。 在主 **"邮件跟踪"** 页上，您可以在"可下载的报告"部分查看 **报告** 的状态。

有关不同报告类型中返回的信息详细信息，请参阅下一节。

## <a name="message-trace-results"></a>邮件跟踪结果

不同的报告类型返回不同级别的信息。 以下各节介绍了不同报告中的信息。

### <a name="summary-report-output"></a>摘要报告输出

运行邮件跟踪后，将列出结果，并按最近的第一次 (日期/时间) 。

![安全与合规中心内邮件跟踪&摘要报告结果](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

摘要报告包含以下信息：

- **日期**：服务使用配置的 UTC 时区接收邮件的日期和时间。

- **发件人**：别名域的发件人 ( @ *电子邮件地址) 。*

- **收件人**：收件人的电子邮件地址。 对于发送给多个收件人的邮件，每个收件人有一行。 如果收件人是通讯组、动态通讯组或启用邮件的安全组，则该组将是第一个收件人，然后该组的每个成员位于单独的行上。

- **主题**：邮件的 **Subject：** 字段的前 256 个字符。

- **状态**：这些值在"传递状态 ["部分](#delivery-status) 进行介绍。

默认情况下，前 250 个结果已加载且随时可用。 向下滚动时，加载下一批结果时，会稍微暂停。 你可以单击"全部加载"以加载最多 10，000 个结果，而不是滚动。

您可以单击列标题以按该列中的值以升序或降序对结果进行排序。

可以单击 **"筛选结果** "按一列或多列筛选结果。

You can export the results after you've selected one or more rows by clicking **Export results** and then selecting Export **all results**， Export loaded **results**， or **Export selected**.

#### <a name="find-related-records-for-this-message"></a>查找此邮件的相关记录

相关邮件记录是共享相同邮件 ID 的记录。 请记住，即使在两个人之间发送的单个邮件也可以生成多个记录。 当邮件受通讯组扩展、转发、邮件流规则（也称为传输规则 (传输规则等影响）时，记录) 增加。

选中行的复选框后，可以通过单击出现的"查找相关"按钮或选择"更多选项""查找此邮件的相关记录"来查找 ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> ) 。

有关邮件 ID 详细信息，请参阅本文前面部分的消息 ID 部分。

#### <a name="message-trace-details"></a>邮件跟踪详细信息

在摘要报告输出中，可以使用以下任一方法查看有关邮件的详细信息：

- Select the row (click anywhere in the row except the check box) .

- 选中该行的复选框，然后单击"更多 **选项** ![ "" ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **查看邮件详细信息"。**

   ![在安全与合规中心内双击摘要报告邮件跟踪结果中的&的详细信息](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

邮件跟踪详细信息包含摘要报告中未包含的以下附加信息：

- **邮件事件**：此部分包含分类，可帮助对服务对邮件采取的操作进行分类。 **您可能遇到的一些** 更有趣的事件是：

  - **接收**：邮件已由服务接收。

  - **发送**：邮件由服务发送。

  - **失败**：邮件无法传递。

  - **传递**：邮件已传递到邮箱。

  - **展开**：邮件已发送到已展开的通讯组。

  - **传输**：由于内容转换、邮件收件人限制或代理原因，收件人已移动到已进行收件人转换的邮件。

  - **延迟**：邮件传递延迟，稍后可能会重新尝试。

  - **已** 解决：邮件已基于 Active Directory 查找重定向到新的收件人地址。 当发生这种情况时，原始收件人地址会被列在邮件跟踪中的单独一行，包括邮件的最终传递状态。

  > [!NOTE]
  > 
  > - 成功传递的无事件邮件将在邮件 **跟踪** 中生成多个事件条目。
  > 
  > - 此列表并不详尽。 有关更多事件的说明，请参阅 [邮件跟踪日志中的事件类型](/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)。 请注意，此链接是Exchange Server (Exchange) 主题。

- **详细信息 ：** 此部分包含以下详细信息：

  - **邮件 ID：** 此值在本文前面的消息 [ID](#message-id) 部分中介绍。 例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。

  - **邮件大小**

  - **来自 IP：** 发送邮件的计算机的 IP 地址。 对于从 Exchange Online 发送的出站邮件，该值是空值。

  - **To IP**：服务尝试传递邮件的 IP 地址。 如果邮件有多个收件人，则显示这些收件人。 对于发送到 Exchange Online 的入站邮件，该值是空值。

### <a name="enhanced-summary-reports"></a>增强摘要报告

可在 (跟踪) **可下载** 报告"部分查看已完成的增强摘要报告。 报告中提供了以下信息：

- **origin_timestamp：** 服务最初使用配置的 UTC 时区接收邮件 <sup>*</sup> 的日期和时间。

- **sender_address：** 发件人的电子邮件地址 (*域名* @ *) 。*

- **Recipient_status：** 邮件送达收件人的状态。 如果邮件已发送给多个收件人，它将以以下格式显示所有收件人和每个收件人的相应状态 \<*email address*\> ## \<*status*\> ： 。 例如：

  - **##Receive，"** 发送"表示服务已接收邮件并发送到预期目标。

  - **##Receive，Fail** 表示服务已接收邮件，但发送到预期目标失败。

  - **##Receive，"** 传递"表示服务已接收邮件，并且已传递到收件人的邮箱。

- **message_subject**：邮件的 Subject 字段的前 256 **个字符。**

- **total_bytes：** 邮件的大小（以字节为单位，包括附件）。

- **message_id：** 此值在本文前面的消息 [ID](#message-id) 部分中介绍。 例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。

- **network_message_id：** 唯一的邮件 ID 值，因混淆或通讯组扩展而创建的邮件的所有副本中均保留。 示例值为 `1341ac7b13fb42ab4d4408cf7f55890f` 。

- **original_client_ip**：发件人客户端的 IP 地址。

- **方向** 性：指示邮件是 (1) 发送到组织的入站邮件，还是从组织 (2) 出站邮件。

- **connector_id**：源连接器或目标连接器的名称。 有关 Exchange Online 中的连接器详细信息，请参阅 [在 Office 365](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)中配置使用连接器的邮件流。

- **delivery_priority：** <sup>*</sup> 邮件是使用高、**低还是** 普通优先级 **发送**。

<sup>*</sup> 这些属性仅在增强摘要报告中可用。

### <a name="extended-reports"></a>扩展报告

Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace. 实际上，"增强摘要"报告中的所有信息都可用于扩展 (，origin_timestamp和 **delivery_priority) 。**  以下附加信息仅在扩展报告中可用：

- **client_ip**：提交邮件的电子邮件服务器或邮件客户端的 IP 地址。

- **client_hostname**：提交邮件的电子邮件服务器或邮件客户端的主机名或 FQDN。

- **server_ip**：源服务器或目标服务器的 IP 地址。

- **server_hostname**：目标服务器的主机名或 FQDN。

- **source_context：** 与源字段关联的 **额外** 信息。 例如：

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **source**：负责事件的 Exchange Online 组件。 例如：

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id：** 这些值对应于"查找此邮件的相关记录"部分中介绍的 **Message** [事件](#find-related-records-for-this-message) 值。

- **internal_message_id：** 由当前正在处理邮件的 Exchange Online 服务器分配的邮件标识符。

- **recipient_address：** 邮件收件人的电子邮件地址。 多个电子邮件地址通过分号字符 (;) 分隔。

- **recipient_count：** 邮件中的收件人总数。

- **related_recipient_address：** 与 、 和 事件一起用来显示与邮件关联的其他 `EXPAND` `REDIRECT` `RESOLVE` 收件人电子邮件地址。

- **参考**：此字段包含特定类型事件的其他信息。 例如：

  - **DSN：** 包含报告链接，如果 DSN 是在此事件之后生成的，则报告链接是关联的传递状态通知 (的 **message_id** 值，也称为 DSN、未送达报告、NDR 或退回邮件) 。 如果这是 DSN 邮件，则此字段message_id生成DSN 的原始邮件的默认值。

  - **EXPAND**：包含 **related_recipient_address** 邮件的默认值。

  - **RECEIVE：** 如果message_id由其他进程生成，则可能包含相关邮件的 (，例如收件箱规则) 。

  - **SEND**：包含 **internal_message_id** DSN 邮件的默认值。

  - **TRANSFER：****包含internal_message_id** 分叉的邮件的 (值，例如，按内容转换、邮件收件人限制或代理) 。

  - **MAILBOXRULE：****包含internal_message_id** 收件箱规则生成出站邮件的入站邮件的邮箱值。

    对于其他类型的事件，此字段通常为空。

- **return_path**：发送邮件的 **MAIL FROM** 命令指定的返回电子邮件地址。 尽管此字段从不为空，但它可以将空发件人地址值表示为 `<>` 。

- **message_info：** 有关邮件的其他信息。 例如：

  - 和 事件的邮件来源日期-时间 `DELIVER` `SEND` （UTC）。 起始日期-时间是邮件首次进入 Exchange Online 组织的时间。 UTC 日期-时间以 ISO 8601 日期-时间格式表示：，其中 = 年， = 月， = 天，表示时间部分的开始 `yyyy-mm-ddThh:mm:ss.fffZ` `yyyy` `mm` `dd` `T` `hh` ，= 小时， `mm` = 分钟， `ss` = 秒， `fff` = `Z` `Zulu` 秒的小数，并指示 ，这是表示 UTC 的另一种方式。

  - 身份验证错误。 例如，您可能会看到身份验证出错时所使用的值 `11a` 和身份验证类型。

- **tenant_id：** 表示 Exchange Online 组织的 GUID (例如 `39238e87-b5ab-4ef6-a559-af54c6b07b42` ，) 。

- **original_server_ip**：原始服务器的 IP 地址。

- **custom_data：** 包含与特定事件类型相关的数据。 有关详细信息，请参阅以下部分。

#### <a name="custom_data-values"></a>custom_data值

事件的 **custom_data** 字段由各种 Exchange Online 代理用于 `AGENTINFO` 记录邮件处理详细信息。 以下各节介绍了一些更有趣的代理。

#### <a name="spam-filter-agent"></a>垃圾邮件筛选器代理

以 **custom_data** 开头 `S:SFA` 的一个值来自垃圾邮件筛选器代理。 下表介绍了关键详细信息：

****

|值|说明|
|---|---|
|`SFV=NSPM`|邮件被标记为非垃圾邮件并发送给预期收件人。|
|`SFV=SPM`|邮件被反垃圾邮件筛选功能标记为垃圾邮件 (也称为内容筛选) 。|
|`SFV=BLK`|跳过筛选但阻止邮件，因为它是由已阻止发件人发送。|
|`SFV=SKS`|在反垃圾邮件筛选处理邮件之前，邮件被标记为垃圾邮件。 这包括符合以下邮件流程规则条件（也称为传输规则）的邮件：自动将邮件标记为垃圾邮件并规避其他所有筛选。|
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

例如 **custom_data** 垃圾邮件筛选的邮件的值，如下所示：

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>恶意软件筛选器代理

以 **custom_data** 的值 `S:AMA` 来自恶意软件筛选器代理。 下表介绍了关键详细信息：

****

|值|说明|
|---|---|
|`AMA=SUM|v=1|` 或 `AMA=EV|v=1`|已确定此邮件包含恶意软件。 `SUM` 指示恶意软件可能已被任意数目的引擎检测到。 `EV` 指示恶意软件被特定引擎检测到。 引擎检测到恶意软件后，将触发后续操作。|
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

包含 **custom_data** 邮件的默认值示例如下所示：

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>传输规则代理

一 **custom_data** 一个值来自邮件流规则的传输规则代理 (`S:TRA` 传输规则) 。 下表介绍了关键详细信息：

****

|值|说明|
|---|---|
|`ETR|ruleId=<guid>`|匹配的规则 ID。|
|`St=<datetime>`|规则匹配发生时的日期和时间（UTC）。|
|`Action=<ActionDefinition>`|应用的操作。 有关可用操作的列表，请参阅[Mail flow rule actions in Exchange Online。](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|`Mode=<Mode>`|规则模式。 有效值为：<ul><li>**强制**：将强制执行对规则执行的所有操作。</li><li>**使用策略提示进行测试：** 将发送任何策略提示操作，但不执行其他强制操作。</li><li>**不带策略提示的测试**：操作将列在日志文件，但不会以任何方式通知发件人，并且不会对强制操作采取行动。</li></ul>|
|

与 **custom_data** 规则条件匹配的邮件的示例值如下所示：

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`