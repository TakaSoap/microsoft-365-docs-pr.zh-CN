---
title: Microsoft Defender for Office 365 威胁资源管理器中的威胁搜寻
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 使用威胁资源管理器或 Microsoft 365 Defender门户中的实时检测来高效地调查和响应威胁。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b6662a3268fa6ab83c103eb84cd1d77ab06d37d
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476392"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 威胁资源管理器中的威胁搜寻

本文内容：

- [威胁资源管理器演练](#threat-explorer-walk-through)
- [电子邮件调查](#email-investigation)
- [电子邮件修正](#email-remediation)
- [威胁搜寻体验改进](#improvements-to-threat-hunting-experience)

> [!NOTE]
> 这是威胁资源管理器 **(资源管理器)**、电子邮件安全性、资源管理器和实时 **检测 (（** 如工具之间的差异以及操作它们所需的权限）) 的 **3** 篇文章系列中的一部分。 本系列中的其他两篇文章 [是使用威胁](email-security-in-microsoft-defender.md) 资源管理器和威胁资源管理器的电子邮件安全性 [以及实时检测](real-time-detections.md)。


**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

如果你的组织拥有适用于 Office 365 的 [Microsoft Defender](defender-for-office-365.md)，并且你拥有这些权限，可以使用资源管理器或实时检测来检测和修正威胁。[](#required-licenses-and-permissions)

In the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to **Email & collaboration**， and then choose **Explorer** or **Real-time detections**. 若要直接转到页面，请使用 或 <https://security.microsoft.com/threatexplorer> <https://security.microsoft.com/realtimereports>。

使用这些工具，你可以：

- 查看由安全Microsoft 365检测到的恶意软件
- 查看网络钓鱼 URL 并单击裁定数据
- 从资源管理器中的视图启动自动调查和响应过程
- 调查恶意电子邮件等

有关详细信息，请参阅使用 [威胁资源管理器的电子邮件安全性](email-security-in-microsoft-defender.md)。

## <a name="threat-explorer-walk-through"></a>威胁资源管理器演练

在 Microsoft Defender for Office 365，有两个订阅计划：计划 1 和计划 2。 手动操作的威胁搜寻工具存在于两个计划中，名称不同，功能不同。

Defender for Office 365 Plan *1 使用实时* 检测，它是威胁 *资源管理器 (（* 在计划 2 中也称为 *资源管理器) 搜寻* 工具）的子集。 在本系列文章中，大多数示例都是使用完整的威胁资源管理器创建的。 管理员应在实时检测中测试任何步骤，以查看其应用位置。

转到 **资源管理器后，** 默认情况下，你将到达恶意软件页面，但使用视图下拉列表来熟悉你的选项。 如果你搜寻网络钓鱼，或进入威胁活动，请选择这些视图。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/view-drop-down.png" alt-text="威胁资源管理器中的&quot;视图&quot;下拉列表" lightbox="../../media/view-drop-down.png":::

一旦安全操作 (Sec Ops) 人员选择要查看的数据，无论范围是较窄的视图（如用户提交）还是较宽的视图（如"所有电子邮件"），他们都可以使用"发件人"按钮进一步筛选。 请记住，选择"刷新"以完成筛选操作。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/sender-drop-down.png" alt-text="威胁资源管理器中的&quot;发件人&quot;按钮" lightbox="../../media/sender-drop-down.png":::


可以在层中考虑在资源管理器中精简焦点或实时检测。 第 **一个视图**。 第二个可视为已 *筛选焦点*。 例如，可以通过记录类似以下的决策来重新跟踪查找威胁时所执行的步骤：为了在资源管理器中查找问题，我选择了"具有收件人筛选器焦点的 **恶意软件视图"**。 这样一来，可以更轻松地重新跟踪步骤。

> [!TIP]
> 如果 Sec Ops 使用 **标记** 来标记他们认为高价值目标的帐户，他们可以做出选择，如具有标记筛选器焦点的网络钓鱼 (包括日期范围（ *如果使用*) ）。 这会显示在一个时间范围内针对其高价值用户目标的任何网络钓鱼 (例如，当某些网络钓鱼攻击针对其行业组织发生很多事件时) 。

可以使用日期范围控件对日期范围进行精简。 你可以在此处查看"恶意软件"视图中 **的** 资源管理器，具有 **检测技术** 筛选器焦点。 但高级筛选器按钮可让  Sec Ops 团队深入了解。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/advanced-filter.png" alt-text="威胁资源管理器中的高级筛选器" lightbox="../../media/advanced-filter.png":::

单击 **"高级** "筛选器将弹出一个面板，该面板允许 Sec Ops 执行者自己生成查询，允许他们包含或排除他们需要查看的信息。 资源管理器页面上的图表和表格都将反映其结果。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-chart-table.png" alt-text="查询的结果" lightbox="../../media/threat-explorer-chart-table.png":::

使用 **"列** 选项"按钮获取有关最有帮助的表的信息类型：

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-column-options.png" alt-text="突出显示的&quot;列选项&quot;按钮" lightbox="../../media/threat-explorer-column-options.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/column-options.png" alt-text="列中的可用选项" lightbox="../../media/column-options.png":::

在同一方面，请确保测试你的显示选项。 不同的访问群体将很好地响应相同数据的不同演示文稿。 对于一些查看者，电子邮件来源地图可以显示威胁是普遍出现还是比它旁边的"宣传活动显示"选项更快速。 Sec 操作可充分利用这些显示，以最好地突出安全性和保护需求，或用于稍后比较，以演示其操作的有效性。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-email-origin-map.png" alt-text="电子邮件来源映射" lightbox="../../media/threat-explorer-email-origin-map.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-campaign-display.png" alt-text="市场活动显示选项" lightbox="../../media/threat-explorer-campaign-display.png":::

### <a name="email-investigation"></a>电子邮件调查

当看到可疑电子邮件时，单击该名称以展开右侧飞出。 此处提供了允许 Sec Ops 查看 [电子邮件实体页面的](mdo-email-entity-page.md) 横幅。

电子邮件实体页面将可以在详细信息、附件、设备下找到的内容汇集在一起，但包含组织更有序的数据。 这包括 DMARC 结果、带有复制选项的电子邮件头的纯文本显示、安全触发的附件裁定信息以及丢弃 (的文件等内容，包括已联系的 IP 地址以及页面或文件) 的屏幕截图。 还将列出 URL 及其裁定，并报告类似的详细信息。

当您进入此阶段时，电子邮件实体页面将对于最后一步（修正）*至关重要*。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-email-entity-page.png" alt-text="电子邮件实体页面" lightbox="../../media/threat-explorer-email-entity-page.png":::

> [!TIP]
> 若要了解有关以下"分析"选项卡)  (的丰富电子邮件实体页面的详细信息，包括触发的附件的结果、包含的 URL 的结果和安全电子邮件预览，[请单击此处。](mdo-email-entity-page.md)

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-analysis-tab.png" alt-text="电子邮件实体页面的&quot;分析&quot;选项卡" lightbox="../../media/threat-explorer-analysis-tab.png":::

### <a name="email-remediation"></a>电子邮件修正

Sec Ops 人员确定电子邮件是威胁后，下一个资源管理器或实时检测步骤将处理威胁并修正它。 为此，可以返回到威胁资源管理器，选中问题电子邮件的复选框，然后使用"操作 **"按钮。**

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-email-actions-button.png" alt-text="威胁资源管理器中的&quot;操作&quot;按钮" lightbox="../../media/threat-explorer-email-actions-button.png":::

在此，分析员可以执行将邮件报告为"垃圾邮件"、网络钓鱼或恶意软件、联系收件人等操作，或执行进一步调查，包括触发自动调查和响应 (或 AIR) playbook (（如果你有计划 2) ）。 或者，也可以将邮件报告为干净。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-email-actions-drop-down.png" alt-text="&quot;操作&quot;下拉列表" lightbox="../../media/threat-explorer-email-actions-drop-down.png":::

## <a name="improvements-to-threat-hunting-experience"></a>威胁搜寻体验改进

### <a name="alert-id"></a>警报 ID

从警报导航到威胁资源管理器时， **视图** 将按警报 **ID 进行筛选**。 这同样适用于实时检测。 与特定警报相关的邮件，以及 (显示) 总数。 你将能够查看邮件是否属于警报，以及从该邮件导航到相关警报。

最后，警报 ID 包含在 URL 中，例如： `https://https://security.microsoft.com/viewalerts`

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/AlertID-Filter.png" alt-text="警报 ID 筛选器" lightbox="../../media/AlertID-Filter.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/AlertID-DetailsFlyout.png" alt-text="详细信息中的警报 ID 飞出" lightbox="../../media/AlertID-DetailsFlyout.png":::

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a>扩展资源管理器 (和实时检测) 试用租户的数据保留和搜索限制

作为此更改的一部分，分析员将能够搜索和筛选 (在威胁资源管理器中为) 增加的 30 天内的电子邮件数据，以及针对 Office P1 和 P2 试用租户的 Defender 实时检测。 这不会影响 P1 和 P2 E5 客户的任何生产租户，其中保留默认值已是 30 天。

### <a name="updated-export-limit"></a>已更新的导出限制

现在，可以从威胁资源管理器导出的电子邮件记录数为 200，000， (9990) 。 可导出的列集保持不变。

### <a name="tags-in-threat-explorer"></a>威胁资源管理器中的标记

> [!NOTE]
> 用户标记功能在预览版中，可能并非对所有人都可用。 此外，预览可能会更改。 有关发布计划的信息，请查看Microsoft 365路线图。

用户标记标识 Microsoft Defender for Office 365 中的特定用户组。 有关标记（包括许可和配置）详细信息，请参阅 [用户标记](user-tags.md)。

在威胁资源管理器中，可以在以下体验中查看有关用户标记的信息。

#### <a name="email-grid-view"></a>电子邮件网格视图

当分析员查看电子邮件网格的 **"** 标签"列时，他们将看到已应用于发件人或收件人邮箱的所有标记。 默认情况下，优先显示优先 *帐户等* 系统标记。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-grid.png" alt-text="电子邮件网格视图中的 Filter 标记" lightbox="../../media/tags-grid.png":::

#### <a name="filtering"></a>筛选

标记可以用作筛选器。 仅在优先级帐户之间搜寻，或采用这种方式使用特定用户标记方案。 还可以排除具有特定标记的结果。 将标记与其他筛选器和日期范围相结合，以缩小调查范围。

[![筛选器标记。](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-filter-not.png" alt-text="尚未筛选的标记" lightbox="../../media/tags-filter-not.png":::

#### <a name="email-detail-flyout"></a>电子邮件详细信息飞出

若要查看发件人和收件人的单个标记，请选择一封电子邮件以打开邮件详细信息飞出。 在 **"摘要"选项卡** 上，发件人和收件人标记将单独显示。 有关发件人和收件人的单个标记的信息可以导出为 CSV 数据。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-flyout.png" alt-text="&quot;电子邮件详细信息&quot;标记" lightbox="../../media/tags-flyout.png":::

URL 单击飞出也显示标记信息。 若要查看，请转到"网络钓鱼"或"所有电子邮件"视图> **URL** 或 **URL** 单击"选项卡。选择单个 URL 飞出以查看有关该 URL 的单击的其他详细信息，包括与该单击关联的任何标记。

### <a name="updated-timeline-view"></a>更新的时间线视图

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-urls.png" alt-text="URL 标记" lightbox="../../media/tags-urls.png":::
>
观看[此视频](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4)了解更多信息。

## <a name="extended-capabilities"></a>扩展功能

### <a name="top-targeted-users"></a>主要目标用户

主要恶意软件系列在 **"恶意软件"部分显示** 主要目标用户。 主要目标用户也将通过钓鱼和所有电子邮件视图进行扩展。 分析员将能够查看前五个目标用户，以及每个视图中每个用户的尝试次数。

安全操作 用户可以导出目标用户列表（最多 3，000 个）以及尝试次数，以便针对每个电子邮件视图进行脱机分析。 此外，选择尝试次数 (例如，在) 下的图像中尝试 13 次将在威胁资源管理器中打开筛选视图，以便你可以查看有关该用户的电子邮件和威胁的更多详细信息。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Top_Targeted_Users.png" alt-text="目标最多的用户" lightbox="../../media/Top_Targeted_Users.png":::

### <a name="exchange-transport-rules"></a>Exchange传输规则

安全操作团队将能够在"电子邮件"网格Exchange查看 (邮件流规则) 邮件流规则。 选择 **网格中的** 列选项，**然后Exchange添加** 传输规则。 the Exchange transport rules option is also visible on the **Details** flyout in the email.

将显示应用于邮件的传输规则的名称和 GUID。 分析员将能够使用传输规则的名称搜索邮件。 这是 CONTAINS 搜索，这意味着您也可以执行部分搜索。

> [!IMPORTANT]
> Exchange规则搜索和名称可用性取决于分配给您的特定角色。 您需要具有以下角色或权限之一才能查看传输规则名称和搜索。 但是，即使没有以下角色或权限，分析员也可以查看电子邮件详细信息中的传输规则标签和 GUID 信息。 电子邮件网格、电子邮件飞出、筛选器和导出中的其他记录查看体验不受影响。
>
> - Exchange Online - 数据丢失防护：全部
> - Exchange Online - O365SupportViewConfig：全部
> - Microsoft Azure Active Directory或Exchange Online - 安全管理员：全部
> - Azure Active Directory或Exchange Online - 安全读者：全部
> - Exchange Online - 传输规则：全部
> - 仅Exchange Online - View-Only配置：全部
>
> 在电子邮件网格、"详细信息"飞出控件和导出的 CSV 中，ETR 将显示一个名称/GUID，如下所示。
>
> > [!div class="mx-imgBorder"]
> > :::image type="content" source="../../media/ETR_Details.png" alt-text="传输Exchange规则" lightbox="../../media/ETR_Details.png":::

### <a name="inbound-connectors"></a>入站连接器

连接器是一组说明，用于自定义电子邮件在组织或组织Microsoft 365 Office 365流。 它们使您能够应用任何安全限制或控件。 在威胁资源管理器中，可以查看与电子邮件相关的连接器，然后使用连接器名称搜索电子邮件。

搜索连接器是 CONTAINS 查询，这意味着部分关键字搜索可以正常工作：

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Connector_Details.png" alt-text="连接器详细信息" lightbox="../../media/Connector_Details.png":::

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

你必须拥有 [Microsoft Defender Office 365](defender-for-office-365.md)使用资源管理器或实时检测。

- 资源管理器包含在计划 2 Office 365 Defender 中。
- 实时检测报告包含在计划 1 的 Defender Office 365中。
- 计划为应受 Defender for Office 365 保护的所有用户分配Office 365。 资源管理器和实时检测显示许可用户的检测数据。

若要查看和使用资源管理器或实时检测，您必须具有以下权限：

- 在 Microsoft 365 Defender门户中：
  - 组织管理
  - 安全 (可以在管理中心Azure Active Directory分配<https://aad.portal.azure.com> () 
  - 安全信息读取者
- 在Exchange Online：
  - 组织管理
  - 仅查看组织管理
  - 仅查看收件人
  - 合规性管理

若要详细了解角色和权限，请参阅以下资源：

- [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)
- [Exchange Online 中的权限](/exchange/permissions-exo/permissions-exo)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>详细信息

- [查找和调查投递的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)
- [查看在 SharePoint Online、OneDrive 和 Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [大致了解威胁资源管理器中的视图 (实时检测) ](threat-explorer-views.md)
- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft 威胁防护中的自动调查和响应](automated-investigation-response-office.md)
- [使用"电子邮件实体"页调查电子邮件](mdo-email-entity-page.md)
