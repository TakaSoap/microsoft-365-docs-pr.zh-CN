---
title: 以管理员身份管理隔离的邮件和文件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: 管理员可以了解如何在 EOP 管理中心中查看和管理所有用户Exchange Online Protection () 。 使用 Microsoft Defender for Office 365 的组织的管理员还可以在 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中管理隔离Microsoft Teams。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 508866fd66e4cbd00f559446d4ce52a4be063c94
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539103"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>在 EOP 中以管理员身份管理已隔离邮件和文件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。 有关详细信息，请参阅 [EOP 中的隔离电子邮件](quarantine-email-messages.md)。

管理员可以查看、释放和删除所有用户的所有类型的隔离邮件。 只有管理员才能管理被隔离为恶意软件、高可信度网络钓鱼的邮件，或由于邮件流规则 (也称为传输规则) 。 管理员还可以向 Microsoft 报告误报。

使用 Microsoft Defender for Office 365 的组织的管理员还可以在 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中查看、下载和删除隔离Microsoft Teams。

在安全与合规中心或 PowerShell & PowerShell 中查看和管理隔离邮件， (Exchange Online Microsoft 365邮箱位于 Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开安全与合规中心，请转到 <https://protection.office.com>。 若要直接打开“隔离”页，请转到 <https://protection.office.com/quarantine>。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：
  - 若要对所有用户的隔离邮件采取措施，你需要是组织管理、安全管理员或隔离管理员 **角色** <sup>\*</sup> 组的成员。
  - 若要对所有用户的隔离邮件进行只读访问，你需要是全局读者或安全读者 **角色组的成员**。 

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  **注意**：

  - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。
  - <sup>\*</sup>隔离管理员 **角色** 组的成员还需要是 Exchange Online 中清洁管理角色组的成员，才能在 [](/Exchange/permissions-exo/permissions-exo#role-groups)PowerShell 中执行Exchange Online过程。

- 隔离邮件在被自动删除之前将保留一段默认时间：
  - 30 天内，由反垃圾邮件策略隔离的邮件 (垃圾邮件、网络钓鱼和批量电子邮件) 。 这是默认值和最大值。 若要配置 (此值) ，请参阅配置 [反垃圾邮件策略](configure-your-spam-filter-policies.md)。
  - 包含恶意软件的邮件的 15 天。
  - 对于在 Defender for 保险箱 中由 SharePoint、OneDrive 和 Microsoft Teams 附件隔离Microsoft Teams 15 Office 365。

  当邮件从隔离区过期时，你无法恢复它。

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>使用安全&中心管理隔离的电子邮件

### <a name="view-quarantined-email"></a>查看隔离电子邮件

1. 在安全与&中心，转到"**威胁管理** \> **""审阅隔离** \> **"。**

2. 验证“**查看隔离项目**”是否设置为默认值“**电子邮件**”。

3. 若要对结果进行排序，可以单击可用列标题。 单击“修改列”最多可显示七列。 默认值标有星号 (<sup>\*</sup>)：

   - **接收时间**<sup>\*</sup>
   - **发件人**<sup>\*</sup>
   - **主题**<sup>\*</sup>
   - **隔离原因**<sup>\*</sup>
   - **释放?**<sup>\*</sup>
   - **策略类型**<sup>\*</sup>
   - **Expires**
   - **收件人**
   - **邮件 ID**
   - **策略名称**
   - **大小**
   - **方向**

   完成后，单击“保存”单击“设置为默认设置”。

4. 若要筛选结果，请单击“筛选器”。 以下筛选器可用：

   - **到期时间**：按邮件的隔离到期时间筛选：
     - **今天**
     - **未来 2 天**
     - **未来 7 天**
     - **自定义**：输入“开始日期”和“结束日期”。

   - **接收时间**：输入“开始日期”和“结束日期”。

   - **隔离原因**：
     - **策略**：邮件与邮件流规则条件匹配 (也称为传输规则) 。
     - **大量邮件**
     - **网络钓鱼**：垃圾邮件筛选器 **裁定是钓鱼** 电子邮件或防钓鱼保护隔离了邮件 ([欺骗](set-up-anti-phishing-policies.md#spoof-settings)[设置或模拟](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)保护) 。
     - **恶意软件**
     - **垃圾邮件**
     - **高可信度钓鱼邮件**

   - **策略类型**：按策略类型筛选邮件：
     - **反恶意软件策略**
     - **保险箱附件策略**
     - **反网络钓鱼策略**
     - **托管内容筛选器策略**（反垃圾邮件策略）
     - **传输规则**

   - **电子邮件收件人**：所有用户或仅发送给你的邮件。 最终用户只能管理发送给他们的隔离邮件。

   若要清除筛选器，请单击“清除”。 若要隐藏筛选器浮出控件，请再次单击“筛选器”。

5. 使用“结果排序依据”（默认为“邮件 ID”按钮）和相应值查找特定邮件。 不支持通配符。 可以按下面的值搜索：

   - **邮件 ID**：邮件的全局唯一标识符。

     例如 [，使用邮件](message-trace-scc.md) 跟踪查找已发送给组织中用户的邮件，并确定邮件是隔离的而不是传递的。 请务必包括完整的邮件 ID 值，该值可能包含尖括号 \<\> () 。 例如：`<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。

   - **发件人电子邮件地址**：单个发件人的电子邮件地址。

   - **策略名称**：使用邮件的完整策略名称。 搜索不区分大小写。

   - **收件人电子邮件地址**：单个收件人的电子邮件地址。

   - **主题**：使用邮件的整个主题。 搜索不区分大小写。

   - **策略** 名称：负责隔离邮件的策略的名称。

   输入搜索条件后，单击“刷新” ![“刷新”按钮](../../media/scc-quarantine-refresh.png) 来筛选结果。

找到特定的已隔离邮件后，选择此邮件即可查看它的详细信息，并对它执行操作（例如，查看、释放、下载或删除邮件）。

#### <a name="view-quarantined-message-details"></a>查看已隔离邮件的详细信息

选择列表中的电子邮件后，可以在“详细信息”浮出控件窗格中看到以下邮件详细信息：

- **邮件 ID**：邮件的全局唯一标识符。

- **发件人地址**

- **接收时间**：收到邮件的日期/时间。

- **主题**

- **隔离原因**：显示邮件被标识为垃圾邮件、批量邮件、网络钓鱼邮件、匹配邮件流规则 (**传输** 规则) 或标识为包含恶意软件 **。**

- **收件人计数**

- **收件人**：如果邮件有多个收件人，需要单击“预览邮件”或“查看邮件头”，以查看完整的收件人列表。

- **到期时间**：邮件自动从隔离中永久删除的日期/时间。

- **已释放到的位置**：邮件已释放到的所有电子邮件地址（若有）。

- **尚未释放到的位置**：邮件尚未释放到的所有电子邮件地址（若有）。

### <a name="take-action-on-quarantined-email"></a>对已隔离电子邮件执行操作

选择邮件后，在"详细信息"飞出窗格中，您可以选择对邮件执行哪些操作： 

- **释放邮件**：在出现的飞出窗格中，选择以下选项：

  - **将邮件报告给 Microsoft 进行分析**：默认情况下选中此选项，将错误隔离的邮件报告给 Microsoft 作为误报。 如果邮件被隔离为垃圾邮件、批量邮件、网络钓鱼邮件或包含恶意软件，则还会将邮件报告给 Microsoft 垃圾邮件分析团队。 根据分析，可能会调整服务范围内的垃圾邮件筛选规则以允许邮件通过。

  - 选择下列选项之一：
    - **将邮件释放给所有收件人**
    - **将邮件释放给特定收件人**
    - **将邮件释放给其他人**：请注意，不支持将恶意软件邮件释放给原始收件人外的其他人员。

  完成后，单击“释放邮件”。

  有关释放邮件的注意事项：

  - 不能将邮件释放给同一收件人多次。
  - 只有尚未收到邮件的收件人将显示在潜在收件人列表中。

- **查看邮件头**：选择此链接可查看邮件头文本。 若要深入分析邮件头字段和值，请将邮件头文本复制到剪贴板，然后选择“Microsoft 邮件头分析器”，即可转到远程连接分析器（如果希望在不离开 Microsoft 365 的情况下完成这项任务，请右键单击并选择“在新标签页中打开”）。 将邮件头粘贴到页面上的“邮件头分析器”部分中，然后选择“分析邮件头”：

- **预览邮件**：在显示的浮出控件窗格中，选择以下选项之一：
  - **源视图**：显示禁用所有链接的 HTML 版邮件正文。
  - **文本视图**：以纯文本格式显示邮件正文。

- **从隔离** 区删除：在出现的警告中单击"是"后，邮件将立即删除，而不会发送给原始收件人。

- **下载邮件**：在显示的浮出控件窗格中，选择“我了解下载此邮件所面临的风险”，以使用 .eml 格式保存邮件的本地副本。

- **阻止发件人**：将发件人添加到邮箱上的"阻止发件人"列表中。 有关详细信息，请参阅 [阻止邮件发件人](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。

- **提交邮件**：在出现的飞出窗格中，选择以下选项：

  - **对象类型**： **电子邮件** (默认 **) 、URL** 或 **附件**。

  - 提交 **格式**：网络消息 ID (默认为，"网络消息 **ID"** 框中的相应值为) 或 **file** (浏览到本地 .eml 或 .msg) 。  请注意，如果您选择" **文件"，** 然后选择" **网络消息 ID"，** 初始值将消失。

  - **收件人：** 在租用邮件的原始收件人时键入 ，或单击"全 **选** "以标识所有收件人。 也可以单击"全 **选"，** 然后有选择地删除各个收件人。

  - **提交原因****：不应被** 阻止 (默认) **或应该已被阻止**。

  完成后，单击"提交 **"。**

如果你没有释放或删除邮件，它会在默认隔离保持期到期后删除。

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>对多封已隔离电子邮件执行操作

在你选择列表中的多封已隔离邮件（最多 100 封）后，“批量操作”浮出控件窗格随即显示，你可以在其中执行以下操作：

- **释放邮件**：除了无法选择“将邮件释放给特定收件人”之外，可以选择的选项与释放一封邮件时相同，即只能选择“将邮件释放给所有收件人”或“将邮件释放给其他用户”。

  > [!NOTE]
  > 请考虑以下方案：john@gmail.com 向用户发送 faith@contoso.com john@subsidiary.contoso.com。 Gmail 将此邮件分为两个副本，这两个副本在 Microsoft 中都作为网络钓鱼路由到隔离邮箱。 管理员将这两条消息释放到 admin@contoso.com。 将传递到达管理员邮箱的第一个释放的邮件。 第二个释放的邮件被标识为重复传递并跳过。 如果邮件具有相同的邮件 ID 和接收时间，则邮件被标识为重复项。

- **删除邮件**：在 **出现的警告中** 单击"是"后，将立即删除这些邮件，而不发送给原始收件人。

完成后，单击“关闭”。

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>仅适用于 Office 365 的 Microsoft Defender：使用安全&安全与合规中心管理隔离的文件

> [!NOTE]
> 本部分中隔离文件的过程仅适用于 Microsoft Defender for Office 365计划 1 和计划 2 订阅者。

在具有 Defender for Office 365 的组织中，管理员可以在 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中管理隔离Microsoft Teams。 若要启用对这些文件的保护，请参阅打开保险箱[附件SharePoint、OneDrive和Microsoft Teams。](turn-on-mdo-for-spo-odb-and-teams.md)

### <a name="view-quarantined-files"></a>查看隔离文件

1. 在安全与&中心，转到"**威胁管理** \> **""审阅隔离** \> **"。**

2. 将 **隔离视图更改为** 值 **文件**。 可以通过单击可用列标题对字段进行排序。

3. 若要对结果进行排序，可以单击可用列标题。 单击“修改列”最多可显示七列。 默认列标有星号 <sup>\*</sup> () ：

   - **用户**<sup>\*</sup>
   - **位置**<sup>\*</sup>
   - **文件名**<sup>\*</sup>
   - **文件 URL**<sup>\*</sup>
   - **文件大小**<sup>\*</sup>
   - **到期时间**<sup>\*</sup>
   - **释放?**<sup>\*</sup>
   - **检测者**
   - **按时间修改**

4. 若要筛选结果，请单击“筛选器”。 以下筛选器可用：

   - **到期时间**：按邮件的隔离到期时间筛选：
     - **今天**
     - **未来 2 天**
     - **未来 7 天**
     - 自定义日期/时间范围。
   - **接收时间**
   - **隔离原因**：唯一可用的值为 **Malware**。
   - **策略类型**

找到特定的隔离文件后，选择该文件以查看其详细信息， (例如查看、释放、下载或删除邮件) 。

#### <a name="view-quarantined-file-details"></a>查看隔离文件详细信息

在列表中选择文件时，"详细信息"飞出窗格中会显示 **以下文件详细信息** ：

- **文件名**
- **文件 URL：** 用于定义文件位置的 URL (例如，在 SharePoint Online) 。
- **检测到的恶意内容** 文件的隔离日期/时间。
- **Expires**：从隔离区删除文件的日期。
- **检测者**：defender Office 365或 Microsoft 的反恶意软件引擎。
- **释放?**
- **恶意软件名称**
- **文档 ID：** 文档的唯一标识符。
- **文件大小：** 以 KB 为单位 (KB) 。
- **组织** 组织的唯一 ID。
- **上次修改时间**
- **修改者**：上次修改文件的用户。
- 安全哈希 **算法 256 位 (SHA-256) 值**：可以使用此哈希值在其他信誉存储或环境中的其他位置标识文件。

### <a name="take-action-on-quarantined-files"></a>对隔离文件采取措施

在列表中选择文件时，可以在"详细信息"飞出窗格中对文件执行以下操作： 

- **发布文件**： (默认) 将报告文件取消选中 **到 Microsoft** 进行分析，然后单击"发布 **文件"。**
- **下载文件**
- **从隔离区中删除文件**

如果不释放或删除文件，将在默认隔离保留期过期后删除这些文件。

#### <a name="actions-on-multiple-quarantined-files"></a>对多个隔离文件的操作

在列表中选择多个隔离文件 (最多 100) 时，将显示"批量操作"飞出窗格，您可以在其中执行以下操作：

- **发布文件**
- **删除文件**：在 **出现的警告中** 单击"是"后，将立即删除文件。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 查看和管理隔离的邮件和文件

用于查看和管理隔离邮件和文件的 cmdlet 包括：

- [Delete-QuarantineMessage](/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage：](/powershell/module/exchange/preview-quarantinemessage)请注意，此 cmdlet 仅适用于邮件，而不是来自 保险箱 Attachments for SharePoint、OneDrive 和 Microsoft Teams 的隔离Microsoft Teams。

- [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
