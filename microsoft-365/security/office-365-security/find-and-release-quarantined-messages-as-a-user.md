---
title: 以用户身份查找并释放隔离的邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 用户可在 Exchange Online Protection （EOP）中了解如何查看和管理应该已提供给他们的隔离邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 036aa164b8b77efd2365d56c07d26870eac243f5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274444"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a>在 EOP 中以用户身份查找和释放已隔离邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。 有关详细信息，请参阅 [EOP 的隔离功能](quarantine-email-messages.md)。

作为用户，你可以查看、释放和删除你是收件人的隔离邮件，这些邮件作为垃圾邮件或批量邮件被隔离。 从 2020 年 4 月起，你可以查看或删除你是收件人的被隔离（非高可信度钓鱼邮件）钓鱼邮件。 你可以在“安全与合规中心”或[最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)（如果管理员已对此进行了设置）中查看和管理隔离的邮件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开安全与合规中心，请转到 <https://protection.office.com>。 若要直接打开“隔离”页，请转到 <https://protection.office.com/quarantine>。

- 管理员可以配置邮件在永久删除前的隔离期限（反垃圾邮件策略）。 隔离到期的邮件不可恢复。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

- 此外，管理员还可以在反垃圾邮件策略中[启用最终用户垃圾邮件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)。 用户可以直接从这些通知释放隔离的垃圾邮件。 用户可以直接从这些通知查看隔离的网络仿冒邮件（不是高可信度网络仿冒邮件）。 有关详细信息，请参阅 [EOP 中的最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。

- 只有管理员才能访问因为是高可信度网络仿冒邮件、恶意软件或根据邮件流规则（亦称为“传输规则”）被隔离的邮件，用户看不到这些内容。 有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。

- 可以释放邮件，并将它报告为误报（非垃圾邮件），但只能执行一次。

## <a name="view-your-quarantined-messages"></a>查看已隔离邮件

1. 在安全与合规中心内，依次转到“威胁管理”\>“审阅”\>“隔离”。

2. 若要对结果进行排序，可以单击可用列标题。 单击“修改列”最多可显示七列。 默认值标有星号 (<sup>\*</sup>)：

   - **接收时间**<sup>\*</sup>
   - **发件人**<sup>\*</sup>
   - **主题**<sup>\*</sup>
   - **隔离原因**<sup>\*</sup>
   - **释放?**<sup>\*</sup>
   - **策略类型**<sup>\*</sup>
   - **到期时间**<sup>\*</sup>
   - **收件人**
   - **邮件 ID**
   - **策略名称**
   - **大小**
   - **方向**

   完成后，单击“保存”单击“设置为默认设置”。

3. 若要筛选结果，请单击“筛选器”。 以下筛选器可用：

   - **到期时间**：按邮件的隔离到期时间筛选：
     - **今天**
     - **未来 2 天**
     - **未来 7 天**
     - **自定义**：输入“开始日期”和“结束日期”。

   - **接收时间**：输入“开始日期”和“结束日期”。

   - **隔离原因**：
     - **大量邮件**
     - **垃圾邮件**
     - **网络钓鱼**

   - **策略类型**：按策略类型筛选邮件：
     - **反网络钓鱼策略**
     - **托管内容筛选器策略**（反垃圾邮件策略）

   若要清除筛选器，请单击“清除”。 若要隐藏筛选器浮出控件，请再次单击“筛选器”。

4. 使用“结果排序依据”（默认为“邮件 ID”按钮）和相应值查找特定邮件。 不支持通配符。 可以按下面的值搜索：

   - **邮件 ID**：邮件的全局唯一标识符。 在你选择列表中的邮件后，“详细信息”浮出控件窗格随即显示，其中包含“邮件 ID”值。 管理员可以使用[邮件跟踪](message-trace-scc.md)来查找邮件及其相应“邮件 ID”值。

   - **发件人电子邮件地址**：单个发件人的电子邮件地址。

   - **策略名称**：使用邮件的完整策略名称。 搜索不区分大小写。

   - **收件人电子邮件地址**：单个收件人的电子邮件地址。

   - **主题**：使用邮件的整个主题。 搜索不区分大小写。

   输入搜索条件后，单击“刷新” ![“刷新”按钮](../../media/scc-quarantine-refresh.png) 来筛选结果。

找到特定的已隔离邮件后，选择此邮件即可查看它的详细信息，并对它执行操作（例如，查看、释放、下载或删除邮件）。

### <a name="export-message-results"></a>导出邮件结果

1. 选择你有意访问的邮件，然后单击“导出结果”。

2. 在警告你不要关闭浏览器窗口的确认消息中，单击“是”。

3. 在导出结果准备就绪后，可以为 .csv 文件命令并选择下载位置。

### <a name="view-quarantined-message-details"></a>查看已隔离邮件的详细信息

选择列表中的电子邮件后，可以在“详细信息”浮出控件窗格中看到以下邮件详细信息：

- **邮件 ID**：邮件的全局唯一标识符。

- **发件人地址**

- **接收时间**：收到邮件的日期/时间。

- **主题**

- **隔离原因**：显示邮件是否被标识为“**垃圾邮件**”，“**批量邮件**”或“**钓鱼邮件**”。

- **收件人**：如果邮件有多个收件人，需要单击“预览邮件”或“查看邮件头”，以查看完整的收件人列表。

- **到期时间**：邮件自动从隔离中永久删除的日期/时间。

- **已释放到的位置**：邮件已释放到的所有电子邮件地址（若有）。

- **尚未释放到的位置**：邮件尚未释放到的所有电子邮件地址（若有）。

### <a name="take-action-on-quarantined-email"></a>对已隔离电子邮件执行操作

选择电子邮件后，可以在“详细信息”浮出控件窗格中选择要对邮件执行的操作：

- **释放邮件**：在显示的浮出控件窗格中，选择是否选中“将邮件报告给 Microsoft 进行分析”。 此选项默认处于选中状态，并将已错误隔离的邮件作为误报报告给 Microsoft。

  完成后，单击“释放邮件”。

- **查看邮件头**：选择此链接可查看邮件头文本。 若要深入分析邮件头字段和值，请将邮件头文本复制到剪贴板，然后选择“Microsoft 邮件头分析器”，即可转到远程连接分析器（如果希望在不离开 Microsoft 365 的情况下完成这项任务，请右键单击并选择“在新标签页中打开”）。 将邮件头粘贴到页面上的“邮件头分析器”部分中，然后选择“分析邮件头”：

- **预览邮件**：在显示的浮出控件窗格中，选择以下选项之一：
  - **源视图**：显示禁用所有链接的 HTML 版邮件正文。
  - **文本视图**：以纯文本格式显示邮件正文。

- **从隔离中删除**：当你在显示的警告中单击“是”后，邮件会立即删除。

- **阻止发件人**：将发件人添加到邮箱上的"阻止发件人"列表中。 有关详细信息，请参阅 [阻止邮件发件人](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。

将发件人添加到邮箱上的"阻止发件人"列表中。 有关详细信息，请参阅 [阻止邮件发件人](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。

完成后，单击“关闭”。

如果你没有释放或删除邮件，它会在默认隔离保持期到期后删除。

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>对多封已隔离电子邮件执行操作

在你选择列表中的多封已隔离邮件（最多 100 封）后，“批量操作”浮出控件窗格随即显示，你可以在其中执行以下操作：

- **释放邮件**：除了无法选择“将邮件释放给特定收件人”之外，可以选择的选项与释放一封邮件时相同，即只能选择“将邮件释放给所有收件人”或“将邮件释放给其他用户”。

- **删除邮件**：当你在显示的警告中单击“是”后，邮件会立即删除，而不会发送给原始收件人。

完成后，单击“关闭”。
