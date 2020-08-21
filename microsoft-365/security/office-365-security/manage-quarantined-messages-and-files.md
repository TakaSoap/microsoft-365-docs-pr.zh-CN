---
title: 以管理员身份管理隔离的邮件和文件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何查看和管理所有用户的已在 Exchange Online Protection 邮箱运行 () 。 组织中使用 Office 365 高级威胁防护 (Office 365 ATP) 的管理员也可以管理 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中的隔离文件。
ms.openlocfilehash: 5da67f15a933694c1aef059ff18945122e3ee2e8
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827059"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>在 EOP 中以管理员身份管理已隔离邮件和文件

无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。 有关详细信息，请参阅 [EOP 中隔离的电子邮件](quarantine-email-messages.md)。

管理员可以查看、释放和删除所有用户的所有类型的隔离邮件。 只有管理员可以管理被隔离为恶意软件或高可信度钓鱼的邮件，或者当邮件流规则或也称为传输规则 () 而产生的邮件。 管理员还可以向 Microsoft 报告误报。

组织中使用 Office 365 预防威胁防护 (Office 365 ATP) 的管理员还可以在 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中查看、下载和删除已隔离的文件。

您可以在安全 & 合规中心或在具有 Exchange Online 邮箱的 Microsoft 365 组织的 PowerShell (Exchange Online PowerShell 中查看和管理隔离的邮件;没有 Exchange Online 邮箱策略的组织独立的 EOP) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开安全与合规中心，请转到 <https://protection.office.com>。 若要直接打开“隔离”页，请转到 <https://protection.office.com/quarantine>。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 你需要授予权限，才能以管理员身份管理隔离邮箱。这些权限由安全与合规中心 **内的** 隔离&角色控制。 默认情况下，会在安全与合规中心 (**组织**管理) **Quarantine Administrator** (全局管理员委派委派、隔离管理员**Security Administrator**&安全管理员角色组分配此角色。 有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

- 隔离的邮件在被自动删除之前会默认保留一段时间：

  - 反垃圾邮件策略隔离的邮件会 (垃圾邮件、网络钓鱼和批量电子邮件功能) ： 30 天。 此为默认值和最大值。 要配置此值，请参阅["配置反垃圾邮件策略"。](configure-your-spam-filter-policies.md)

  - 包含恶意软件的邮件：15 天。

  当邮件从隔离到期时，您无法恢复它。

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>使用安全&与合规中心管理隔离的电子邮件

### <a name="view-quarantined-email"></a>查看隔离电子邮件

1. 在安全与合规中心内，依次转到“威胁管理”****\>“审阅”****\>“隔离”****。

2. 验证 **是否将"查看隔离"** 设置为默认值 **电子邮件**。

3. 若要对结果进行排序，可以单击可用列标题。 单击“修改列”**** 最多可显示七列。 默认值标有星号 (<sup>\*</sup>)：

   - **接收时间**<sup>\*</sup>

   - **发件人**<sup>\*</sup>

   - **主题**<sup>\*</sup>

   - **隔离原因**<sup>\*</sup>

   - **释放?**<sup>\*</sup>

   - **策略类型**<sup>\*</sup>

   - **收件人**

   - **邮件 ID**

   - **策略名称**

   - **大小**

   - **方向**

   完成后，单击“保存”**** 单击“设置为默认设置”****。

4. 若要筛选结果，请单击“筛选器”****。 以下筛选器可用：

   - **到期时间**：按邮件的隔离到期时间筛选：

     - **今天**

     - **未来 2 天**

     - **未来 7 天**

     - **自定义**：输入“开始日期”**** 和“结束日期”****。

   - **接收时间**：输入“开始日期”**** 和“结束日期”****。

   - **隔离原因**：

     - **策略**：该邮件符合邮件流规则条件， (也称为传输规则) 。

     - **大量邮件**

     - **网络钓鱼**

     - **恶意软件**

     - **垃圾邮件**

     - **高可信度钓鱼邮件**

   - **电子邮件收件人**：所有用户或仅发送给您的邮件。 最终用户只能管理发送给他们的隔离邮件。

   若要清除筛选器，请单击“清除”****。 若要隐藏筛选器浮出控件，请再次单击“筛选器”****。

5. 使用“结果排序依据”****（默认为“邮件 ID”**** 按钮）和相应值查找特定邮件。 不支持通配符。 可以按下面的值搜索：

   - **邮件 ID**：邮件的全局唯一标识符。

     例如，您使用 [邮件](message-trace-scc.md) 跟踪来查找发送给组织内用户的邮件，且您确定邮件已隔离而不是传递。 请务必包含完整邮件 ID 值，该值可能包含包含用于发送此 \<\> () 。 例如：`<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。

   - **发件人电子邮件地址**：单个发件人的电子邮件地址。

   - **收件人电子邮件地址**：单个收件人的电子邮件地址。

   - **主题**：使用邮件的整个主题。 搜索不区分大小写。

   输入搜索条件后，单击“刷新”**** ![“刷新”按钮](../../media/scc-quarantine-refresh.png) 来筛选结果。

找到特定的已隔离邮件后，选择此邮件即可查看它的详细信息，并对它执行操作（例如，查看、释放、下载或删除邮件）。

#### <a name="export-message-results"></a>导出邮件结果

1. 选择你有意访问的邮件，然后单击“导出结果”****。

2. 在警告你不要关闭浏览器窗口的确认消息中，单击“是”****。

3. 在导出结果准备就绪后，可以为 .csv 文件命令并选择下载位置。

#### <a name="view-quarantined-message-details"></a>查看已隔离邮件的详细信息

选择列表中的电子邮件后，可以在“详细信息”**** 浮出控件窗格中看到以下邮件详细信息：

- **邮件 ID**：邮件的全局唯一标识符。

- **发件人地址**

- **接收时间**：收到邮件的日期/时间。

- **主题**

- **隔离原因：** 显示邮件是被标识**为垃圾邮件、** 批量、网络**钓**鱼邮件、匹配**Bulk**邮件流规则 (**传输规则**) 还是被标识为包含"恶意软件 **"。**

- **收件人**：如果邮件有多个收件人，需要单击“预览邮件”**** 或“查看邮件头”****，以查看完整的收件人列表。

- **到期时间**：邮件自动从隔离中永久删除的日期/时间。

- **已释放到的位置**：邮件已释放到的所有电子邮件地址（若有）。

- **尚未释放到的位置**：邮件尚未释放到的所有电子邮件地址（若有）。

### <a name="take-action-on-quarantined-email"></a>对已隔离电子邮件执行操作

选择邮件后，"详细信息"浮出控件窗格中有几个 **操作适用于这些** 邮件的选项：

- **释放**邮件：在显示的浮出控件窗格中，选择以下选项：

  - **向 Microsoft 报告邮件以供**分析：默认情况下该选项处于选中状态，并将已错误隔离的邮件作为误报报告给 Microsoft。 如果邮件被隔离为垃圾邮件、批量、网络钓鱼或包含恶意软件，则也会向 Microsoft 垃圾邮件分析团队报告该邮件。 根据具体分析，可能会调整服务范围内垃圾邮件筛选规则，以允许发送该邮件。

  - 选择下列选项之一：

    - **将邮件释放给所有收件人**

    - **将邮件释放给特定收件人**

    - **向其他用户发布邮件**

  完成后，单击“释放邮件”****。

  关于发行邮件的注释：

  - 您不能将邮件释放多次，您不能将邮件释放到同一收件人。

  - 只有未收到此邮件的收件人会显示在潜在收件人列表中。

- **查看邮件头**：选择此链接可查看邮件头文本。 若要深入分析邮件头字段和值，请将邮件头文本复制到剪贴板，然后选择“Microsoft 邮件头分析器”****，即可转到远程连接分析器（如果希望在不离开 Microsoft 365 的情况下完成这项任务，请右键单击并选择“在新标签页中打开”****）。 将邮件头粘贴到页面上的“邮件头分析器”部分中，然后选择“分析邮件头”****：

- **预览邮件**：在显示的浮出控件窗格中，选择以下选项之一：

  - **源视图**：显示禁用所有链接的 HTML 版邮件正文。
  
  - **文本视图**：以纯文本格式显示邮件正文。

- **从隔离中删除：** 在出现的警告 **中单击"是** "后，系统会立即删除邮件，而不会发送给原始收件人。

- **下载邮件**：在显示的浮出控件窗格中，选择“我了解下载此邮件所面临的风险”****，以使用 .eml 格式保存邮件的本地副本。

- **提交邮件**：在显示的浮出控件窗格中，选择以下选项：

  - **对象类型****：电子邮件** (默认) **URL**或**附件**。

  - **提交格式**：**默认情况下，" (ID"** 框中具有相应值) **Network Message ID****或者"** 文件" (浏览到本地 .eml 或 .msg 文件) 。 请注意，如果您选择" **文件"** 并选择" **网络消息 ID"，** 则初始值将会不存在。

  - **收件人**：在邮件的一个原始收件人处键入，或单击" **选择全部收件人** "以识别所有收件人。 也可以单击" **选择全部"，** 然后选择性地删除各个收件人。

  - **提交原因：****不应在默认设置** (阻止) ，**或已被阻止**。

  完成后，请单击"提交 **"。**

如果你没有释放或删除邮件，它会在默认隔离保持期到期后删除。

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>对多封已隔离电子邮件执行操作

在你选择列表中的多封已隔离邮件（最多 100 封）后，“批量操作”**** 浮出控件窗格随即显示，你可以在其中执行以下操作：

- **释放邮件**：除了无法选择“将邮件释放给特定收件人”**** 之外，可以选择的选项与释放一封邮件时相同，即只能选择“将邮件释放给所有收件人”**** 或“将邮件释放给其他用户”****。

  > [!NOTE]
  > 假设应用场景如下：john@gmail.com向当前情况faith@contoso.comjohn@subsidiary.contoso.com。 Gmail 会将此邮件放入两个副本中，这些副本都在 Microsoft 都路由到隔离的网络钓鱼中。 管理员将这两种消息均发布以admin@contoso.com。 第一封达到管理员邮箱的已发布邮件将送达。 第二封已释放的邮件标识为重复传递，并跳过。 如果邮件 ID 和接收时间相同，则邮件被标识为重复项。

- **删除邮件**：当你在显示的警告中单击“是”**** 后，邮件会立即删除，而不会发送给原始收件人。

完成后，单击“关闭”****。

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>仅 ATP：& 使用安全与合规中心管理隔离的文件

> [!NOTE]
> 本节中隔离文件的过程仅适用于 ATP 计划 1 和计划 2 订阅者。

在具有 ATP 的组织中，管理员可以管理 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中的隔离文件。

### <a name="view-quarantined-files"></a>查看隔离的文件

1. 在安全与合规中心内，依次转到“威胁管理”****\>“审阅”****\>“隔离”****。

2. **将隔离的视图**更改为默认值**文件**。 通过单击可用列标题，可以对字段排序。

3. 若要对结果进行排序，可以单击可用列标题。 单击“修改列”**** 最多可显示七列。 默认列用星号标记为 <sup>\*</sup> () ：

   - **用户**<sup>\*</sup>

   - **位置**<sup>\*</sup>

   - **文件名**<sup>\*</sup>

   - **文件 URL**<sup>\*</sup>

   - **文件大小**<sup>\*</sup>

   - **到期时间**<sup>\*</sup>

   - **释放?**<sup>\*</sup>

   - **检测者**

   - **按时间修改**

4. 若要筛选结果，请单击“筛选器”****。 以下筛选器可用：

   - **到期时间**：按邮件的隔离到期时间筛选：

     - **今天**

     - **未来 2 天**

     - **未来 7 天**

     - 自定义日期/时间范围。

   - **接收时间**

   - **隔离原因：唯一**可用的值为**Malware。**

找到特定的隔离文件后，选择该文件以查看它的详细信息，并对其执行操作 (例如，查看、释放、下载或删除邮件) 。

#### <a name="export-file-results"></a>导出文件结果

1. 选择你有兴趣的文件，并单击"导出**结果"。**

2. 在警告你不要关闭浏览器窗口的确认消息中，单击“是”****。

3. 在导出结果准备就绪后，可以为 .csv 文件命令并选择下载位置。

#### <a name="view-quarantined-file-details"></a>查看隔离文件详细信息

选择列表中的文件后，"详细信息"浮出控件窗格 **会显示** 以下文件详细信息：

- **文件名**

- **文件 URL：** 定义文件位置的 URL (SharePoint Online 站点) 。

- **检测到的恶意内容** 文件隔离的日期/时间。

- **过期**：从隔离区删除文件的日期。

- **ErP 检测到**：ATP (安全) Microsoft 的反恶意软件引擎。

- **释放?**

- **恶意软件名称**

- **文档 ID：** 文档的唯一标识符。

- **文件大小**：KB (以) 。

- **组织** 组织的唯一 ID。

- **上次修改时间**

- **修改人**：上次修改文件的用户。

- **安全哈希算法 256 位 (SHA-256) 值**： 可以使用此哈希值标识其他信誉存储区或环境中其他位置的文件。

### <a name="take-action-on-quarantined-files"></a>对已隔离文件执行操作

当你选择列表中的文件时，可以对"详细信息"浮出控件 **窗格中的文件** 执行以下操作：

- **释放文件**： 选择 (默认) 向**Microsoft 取消选择报告文件以进行分析，** 然后单击"发布**文件"。**

- **下载文件**

- **从隔离区中删除文件**

如果不释放或删除文件，它们将在默认隔离保留期到期后删除。

#### <a name="actions-on-multiple-quarantined-files"></a>对多个隔离文件执行的操作

在列表中选择多个隔离的文件后 (最多 100 **) ，"批量** 操作"窗格将出现，你可以在其中执行以下操作：

- **发布文件**

- **删除文件**：在出现 **的警告** 中单击"是"后，文件将立即删除。

1. 使用在组织中拥有全局管理员权限 (或适当的安全& 合规中心角色) 的工作或学校帐户登录并转到 [安全&合规中心](../../compliance/go-to-the-securitycompliance-center.md)。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 查看和管理隔离邮件和文件

您用于查看和管理隔离的邮件和文件的 cmdlet 是：

- [Delete-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage：](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)请注意，此 cmdlet 仅适用于邮件，不适用于来自 SharePoint Online、OneDrive for Business 或 Teams 的 ATP 的恶意软件文件。

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
