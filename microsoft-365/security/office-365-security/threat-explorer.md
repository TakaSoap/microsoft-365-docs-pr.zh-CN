---
title: 威胁资源管理器和实时检测
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 使用安全合规中心中的资源管理器和实时 &amp; 检测来有效调查和响应威胁。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3c07ea4a44eb965ab6df834260c9dcef6e79c02a
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142321"
---
# <a name="threat-explorer-and-real-time-detections"></a>威胁资源管理器和实时检测


**适用于**
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

如果你的组织拥有 [适用于 Office 365](office-365-atp.md)的 Microsoft Defender，并且你拥有必要的权限，你拥有资源管理器或实时 **检测 (以前的** 实时报告 *—* 查看新增功能 [！) 。](#new-features-in-threat-explorer-and-real-time-detections) [](#required-licenses-and-permissions) 在安全&合规中心，转到 **"威胁** 管理"，然后选择 **"资源管理器**"_或_**"实时检测"。**


|借助 Microsoft Defender for Office 365 计划 2，可以看到：|借助 Microsoft Defender for Office 365 计划 1，可以看到：|
|---|---|
|![威胁资源管理器](../../media/threatmgmt-explorer.png)|![实时检测](../../media/threatmgmt-realtimedetections.png)|
|

资源管理器或实时检测可帮助安全运营团队有效调查和响应威胁。 报表类似于下图：

![转到威胁管理 \> 资源管理器](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

通过此报告，您可以：

- [查看 Microsoft 365 安全功能检测到的恶意软件](#see-malware-detected-in-email-by-technology)
- [查看网络钓鱼 URL 和单击裁定数据](#view-phishing-url-and-click-verdict-data)
- [仅从资源管理器中的](#start-automated-investigation-and-response) 视图启动自动调查和响应 (Defender for Office 365 计划 2) 
- [调查恶意电子邮件等](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a>威胁资源管理器和实时检测的改进

### <a name="tags-in-threat-explorer"></a>威胁资源管理器中的标记

> [!NOTE]
> 用户标记功能在 *预览版* 中，并非对所有人都可用，并且可能会更改。 有关发布计划的信息，请查看 Microsoft 365 路线图。

用户标记标识 Microsoft Defender for Office 365 中的特定用户组。 有关标记（包括许可和配置）详细信息，请参阅 [用户标记](user-tags.md)。

在威胁资源管理器中，可以在以下体验中查看有关用户标记的信息。

#### <a name="email-grid-view"></a>电子邮件网格视图

电子邮件 **网格** 中的"标记"列包含已应用于发件人或收件人邮箱的所有标记。 默认情况下，优先帐户等系统标记将首先显示。

> [!div class="mx-imgBorder"]
> ![电子邮件网格视图中的筛选器标记](../../media/tags-grid.png)

#### <a name="filtering"></a>筛选

可以使用标记作为筛选器。 仅跨优先级帐户或特定用户标记方案进行智能寻线。 还可以排除具有特定标记的结果。 将此功能与其他筛选器相结合，以缩小调查范围。

[![筛选器标记](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![非筛选器标记](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>电子邮件详细信息飞出
若要查看发件人和收件人的单个标记，请选择主题以打开邮件详细信息飞出。 在 **"摘要"** 选项卡上，如果电子邮件存在发件人和收件人标记，则分别显示它们。
有关发件人和收件人的单个标记的信息还扩展到导出的 CSV 数据，您可以在两个单独的列中查看这些详细信息。

> [!div class="mx-imgBorder"]
> ![电子邮件详细信息标记](../../media/tags-flyout.png)

标记信息也显示在 URL 单击飞出中。 若要查看它，请转到"网络钓鱼"或"所有电子邮件"视图，然后转到 **"URL"或****"URL** 单击"选项卡。选择单个 URL 飞出以查看有关该 URL 的单击的其他详细信息，包括与该单击关联的标记。

> [!div class="mx-imgBorder"]
> ![URL 标记](../../media/tags-urls.png)

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a>威胁搜寻体验的改进 (即将推出的) 

### <a name="updated-threat-information-for-emails"></a>更新了电子邮件的威胁信息

我们专注于平台和数据质量改进，以提高电子邮件记录的数据准确性和一致性。 改进包括将传递前和传递后信息（如作为 ZAP 过程的一部分对电子邮件执行的操作）合并到单个记录中。 还包括垃圾邮件裁定、实体级别威胁 (例如，哪个 URL 是恶意) ，以及最新的传递位置。

这些更新后，无论影响邮件的不同传递后事件如何，你将看到每封邮件的单个条目。 操作可能包括 ZAP、手动修正 (这意味着管理员操作) 、动态传递等。

除了显示恶意软件和网络钓鱼威胁外，您还可以看到与电子邮件关联的垃圾邮件裁定。 在电子邮件中，查看与电子邮件关联的所有威胁以及相应的检测技术。 电子邮件可以具有零个威胁、一个威胁或多个威胁。 你将在电子邮件飞出"详细信息"部分看到当前威胁。 对于恶意软件 (网络钓鱼) ，检测技术字段显示威胁检测映射，这是识别威胁的检测技术。

检测技术集现在包括新的检测方法以及垃圾邮件检测技术。 您可以使用同一组检测技术筛选恶意软件、网络钓鱼、所有电子邮件 (不同电子邮件) 。

> [!NOTE]
> 裁定分析不一定与实体关联。 例如，电子邮件可能分类为网络钓鱼或垃圾邮件，但没有标记有网络钓鱼/垃圾邮件裁定的 URL。 这是因为在分配裁定之前，筛选器还会评估电子邮件的内容和其他详细信息。

#### <a name="threats-in-urls"></a>URL 中的威胁

现在，可以在"电子邮件飞出详细信息"选项卡上看到 URL **的特定威胁**。威胁可以是 *恶意软件*、*网络钓鱼*、*垃圾邮件* 或无 *.)*

> [!div class="mx-imgBorder"]
> ![URL 威胁](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>更新了 (视图) 

> [!div class="mx-imgBorder"]
> ![更新的日程表视图](../../media/Email_Timeline.png)

时间线视图标识所有传递和传递后事件。 它包括有关在这些事件的子集时标识的威胁的信息。 时间线视图还提供了有关已执行 (操作（如 ZAP 或手动修正) ）的信息，以及该操作的结果。 日程表视图信息包括：

- **源：** 事件的源。 它可以是管理员/系统/用户。
- **事件：** 包括顶级事件，如原始传递、手动修正、ZAP、提交和动态传递。
- **操作：** 作为 ZAP 或管理员操作一部分执行的特定 (例如，软删除) 。
- **威胁：** 涵盖 (时标识) 恶意软件、网络钓鱼、垃圾邮件等威胁。
- **结果/详细信息：** 有关操作结果（例如是否作为 ZAP/管理员操作一部分执行）详细信息。

### <a name="original-and-latest-delivery-location"></a>原始和最新的送达位置

目前，我们在电子邮件网格和电子邮件浮出控件中显示传递位置。 传递 **位置字段** 被重命名为原始 **_传递位置_*_。我们正在介绍另一个字段 _*_最新送达位置_**。

**原始送达** 位置将提供有关电子邮件最初送达位置的更多信息。 **最新的送达位置** 将说明电子邮件在系统操作（如 *ZAP）* 或管理员操作（如 *移动到已删除项目）之后登录的位置*。 最新送达位置旨在告知管理员邮件传递后的最新已知位置或任何系统/管理员操作。 它不包含对电子邮件的任何最终用户操作。 例如，如果用户删除了邮件或将邮件移动到存档/pst，邮件"传递"位置将不会更新。 但是，如果系统操作更新了位置 (例如，ZAP 导致电子邮件移动到隔离邮箱) ，则最新送达位置将显示为"隔离"。

> [!div class="mx-imgBorder"]
> ![更新的传递位置](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> 在某些情况下，传递位置 **和****传递操作** 可能显示为"未知"：
>
> - 如果邮件已送达，您可能会将传递位置视为"已送达"，而"传递位置"为"未知"，但收件箱规则将邮件移动到默认文件夹 (例如"草稿"或"存档") ，而不是"收件箱"或"垃圾邮件"文件夹。
>
> - **如果尝试执行** 管理/系统操作（如 ZAP (，但未找到邮件) ，则最新的传递位置可能未知。 通常，该操作发生在用户移动或删除邮件之后。 在这种情况下，请验证 **日程表视图中的结果/** 详细信息列。 查找"用户移动或删除的邮件"语句。

> [!div class="mx-imgBorder"]
> ![时间线的传递位置](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>其他操作

*在电子邮件* 传递后应用了其他操作。 它们可以包括 *ZAP、* 由管理员 (手动修正操作（如软删除 *) 、* 动态传递和重新处理 (）以用于被反向检测为良好的) 。  

> [!NOTE]
> - 作为挂起更改的一部分，当前在传递操作筛选器中显示"ZAP 删除"值将消失。 你将可以通过其他操作通过 ZAP 尝试搜索 **所有电子邮件**。
>
> - 检测技术和其他操作将具有新的字段 **和值**， (ZAP 方案) 。 您需要评估现有保存的查询和跟踪的查询，以确保它们使用新值。

> [!div class="mx-imgBorder"]

> ![资源管理器中的其他操作](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>系统替代

*系统覆盖* 使您能够对邮件的预定传递位置进行例外。 根据筛选堆栈标识的威胁和其他检测，覆盖系统提供的传递位置。 可以通过租户或用户策略设置系统覆盖，以根据策略的建议传递邮件。 替代可以标识由于配置差异（如用户设置过宽的安全发件人策略）而无意传递恶意邮件。 这些替代值可以是：

- 用户策略允许：用户在邮箱级别创建策略以允许域或发件人。
- 被用户策略阻止：用户在邮件框级别创建策略以阻止域或发件人。
- 组织策略允许：组织的安全团队设置策略或 Exchange 邮件流规则 (也称为传输规则) ，以允许组织中的用户使用发件人和域。 这适用于一组用户或整个组织。
- 被组织策略阻止：组织的安全团队设置策略或邮件流规则，以阻止组织中的用户的发件人、域、邮件语言或源 IP。 这可应用于一组用户或整个组织。
- 组织策略阻止的文件扩展名：组织的安全团队通过反恶意软件策略设置阻止文件扩展名。 这些值现在将显示在电子邮件详细信息中，以帮助进行调查。 Secops 团队还可使用丰富的筛选功能筛选阻止的文件扩展名。

[![资源管理器中的系统覆盖](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![资源管理器中的系统覆盖网格](../../media/System_Overrides_Grid.png)

### <a name="improvements-for-the-url-and-clicks-experience"></a>URL 和单击体验的改进

这些改进包括：

- 显示完整单击的 URL (包括作为 URL 链接的一) **单击部分的任何** 查询参数。 目前，URL 域和路径显示在标题栏中。 我们将扩展该信息以显示完整 URL。

- 跨 URL 筛选器 (*URL* 域与 *URL* 域和路径的修复) ：更新会影响对包含 URL/单击裁定的邮件的搜索。 我们启用了协议不可知搜索支持，因此无需使用即可搜索 `http` URL。 默认情况下，除非明确指定了其他值，否则 URL 搜索将映射到 http。 例如：

   -  在 URL、URL 域和 URL 域和路径筛选器字段中使用和不带 `http://` 前缀 **进行** 搜索。   搜索应显示相同的结果。

   -  在 `https://` **URL** 中搜索前缀。 如果未指定任何值， `http://` 则假定前缀。

   - `/` 在 URL 路径 **、URL** 域 **、URL** 域和路径字段的开头和结尾 **被忽略** 。 `/` 将忽略 **URL** 字段的末尾。

### <a name="phish-confidence-level"></a>网络钓鱼可信度

网络钓鱼可信度有助于确定电子邮件被分类为"网络钓鱼"的可信度。 两个可能的值是 *高和**普通*。 在初始阶段，此筛选器仅在威胁资源管理器的网络钓鱼视图中可用。

[![资源管理器中的网络钓鱼可信度](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>ZAP URL 信号

ZAP URL 信号通常用于 ZAP 网络钓鱼警报方案，其中电子邮件被标识为网络钓鱼，且在传递后被删除。 此信号将警报与资源管理器中的相应结果连接在一起。 它是警报的 IIC 之一。

为了改进搜寻过程，我们更新了威胁资源管理器和实时检测，使搜寻体验更加一致。 此处概述了这些更改：

- [时区改进](#timezone-improvements)
- [刷新过程中的更新](#update-in-the-refresh-process)
- [要添加到筛选器的图表向下钻取](#chart-drilldown-to-add-to-filters)
- [在产品信息更新中](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>按用户标记筛选

现在，你可以对系统或自定义用户标记进行排序和筛选，以快速了解威胁的范围。 若要了解更多信息，请参阅 [用户标记](user-tags.md)。

> [!IMPORTANT]
> 按用户标记进行筛选和排序目前处于公共预览阶段。 在商业发布之前，可能会对此功能进行重大修改。 Microsoft 对提供的信息不做出明示或暗示的担保。

![资源管理器中的"标记"列](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>时区改进

你将在门户中以及导出的数据中查看电子邮件记录的时区。 它将在电子邮件网格、详细信息飞出控件、电子邮件时间线和类似电子邮件等体验中可见，因此邮件结果集清晰。

> [!div class="mx-imgBorder"]
> ![在资源管理器中查看时区](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>刷新过程中的更新

例如，一些用户评论了与自动刷新 (混淆，例如，一旦更改日期，页面就会) 其他筛选器 (刷新) 。 同样，删除筛选器会导致自动刷新。 修改查询时更改筛选器可能会导致搜索体验不一致。 为了解决这些问题，我们将迁移到手动筛选机制。

从体验的角度来看，用户可以应用和删除筛选器集和日期 (中不同的筛选器范围) 并选择刷新按钮，以在定义查询后筛选结果。 此时，屏幕上也强调刷新按钮。 我们还更新了相关工具提示和产品内文档。

> [!div class="mx-imgBorder"]
> ![选择"刷新"筛选结果](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>要添加到筛选器的图表向下钻取

现在，你可以绘制图例值图表以将它们添加为筛选器。 选择 **"刷新** "按钮以筛选结果。

> [!div class="mx-imgBorder"]
> ![向下钻取图表以筛选](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>产品内信息更新

产品内现已提供其他详细信息，例如网格内搜索结果总数 (请参阅下面的) 。 我们改进了标签、错误消息和工具提示，以提供有关筛选器、搜索体验和搜索结果集。

> [!div class="mx-imgBorder"]
> ![查看产品内信息](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>威胁资源管理器中的扩展功能

### <a name="top-targeted-users"></a>主要目标用户

现在，我们在电子邮件的"恶意软件"视图中的"主要恶意软件系列"部分公开了主要目标 **用户** 的列表。 我们还将在"网络钓鱼"和"所有电子邮件"视图中扩展此视图。 你将能够看到前五个目标用户，以及每个用户针对相应视图的尝试次数。 例如，对于网络钓鱼视图，你将看到网络钓鱼尝试次数。

你将能够导出目标用户的列表（最多为 3，000 个）以及每个电子邮件视图的脱机分析尝试次数。 此外，选择尝试次数（例如 (，) 下面的图像中的 13 次尝试将在威胁资源管理器中打开筛选视图，以便你可以查看针对该用户的电子邮件和威胁的更多详细信息。

> [!div class="mx-imgBorder"]
> ![主要目标用户](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Exchange 传输规则

作为数据扩充的一部分，你将能够看到应用于邮件的所有不同 Exchange (ETR) 规则。 此信息将在电子邮件网格视图中提供。 若要查看它，请选择网格 **中的** 列选项，然后 **从列** 选项中添加 Exchange 传输规则。 它还将在电子邮件 **的"详细信息** "飞出上可见。

您将能够查看应用于邮件的传输规则的 GUID 和名称。 您可以使用传输规则的名称搜索邮件。 这是一个"包含"搜索，这意味着您也可以执行部分搜索。

#### <a name="important-note"></a>重要说明：

ETR 搜索和名称可用性取决于分配给您的特定角色。 你需要具有以下角色/权限之一才能查看 ETR 名称和搜索。 如果未分配任何这些角色，则看不到传输规则的名称，也看不到使用 ETR 名称搜索邮件。 但是，您可以在电子邮件详细信息中查看 ETR 标签和 GUID 信息。 电子邮件网格、电子邮件飞出、筛选器和导出中的其他记录查看体验不受影响。

- 仅 EXO - 数据丢失防护：全部
- 仅 EXO - O365SupportViewConfig：全部
- Microsoft Azure Active Directory 或 EXO - 安全管理员：全部
- AAD 或 EXO - 安全读取器：全部
- 仅 EXO - 传输规则：全部
- 仅 EXO - View-Only配置：全部

在电子邮件网格、详细信息飞出和导出的 CSV 中，ETR 将显示一个名称/GUID，如下所示。

> [!div class="mx-imgBorder"]
> ![Exchange 传输规则](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>入站连接器

连接器是一组说明，用于自定义电子邮件在 Microsoft 365 或 Office 365 组织之间流动和流出。 它们使您能够应用任何安全限制或控件。 在威胁资源管理器中，你现在可以查看与电子邮件相关的连接器，然后使用连接器名称搜索电子邮件。

连接器搜索本质上是"包含"的，这意味着部分关键字搜索也应正常工作。 在主网格视图、"详细信息"飞出控件和导出的 CSV 中，连接器以名称/GUID 格式显示，如下所示：

> [!div class="mx-imgBorder"]
> ![连接器详细信息](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>威胁资源管理器中的新功能和实时检测

威胁资源管理器和实时检测中提供了三项新功能：

- [预览电子邮件头并下载电子邮件正文](#preview-email-header-and-download-email-body)
- [电子邮件时间线](#email-timeline)
- [导出 URL 单击数据](#export-url-click-data)

下面概述了这些新功能。

### <a name="preview-email-header-and-download-email-body"></a>预览电子邮件头并下载电子邮件正文

现在，你可以预览电子邮件头，并下载威胁资源管理器中的电子邮件正文。管理员可以分析下载的邮件头/电子邮件中的威胁。 因为下载电子邮件可能会暴露信息的风险，所以此过程由基于角色的访问控制控制， (RBAC) 。 必须将新角色 *Preview* 添加到另一个角色组 (如安全操作或安全管理员) ，以授予在全部电子邮件视图中下载邮件和预览邮件头的能力。

资源管理器和实时检测还将获取新字段，这些字段可提供电子邮件到达位置的更完整图片。 这些更改使搜寻安全操作变得更简单。 但主要结果是，您可以一目了然地了解问题电子邮件的位置。

如何完成此操作？ 传递状态现在分为两列：

- **传递操作** - 电子邮件的状态。
- **传递位置** - 电子邮件的路由位置。

*传递* 操作是对现有策略或检测对电子邮件采取的操作。 以下是电子邮件的可能操作：

|已传递|垃圾邮件|Blocked|已替换|
|---|---|---|---|
|电子邮件已传递到用户的收件箱或文件夹，用户可以访问它。|电子邮件已发送到用户的"垃圾邮件"或"已删除邮件"文件夹，用户可以访问它。|隔离、失败或已丢弃的电子邮件。 用户无法访问这些邮件。|电子邮件有恶意附件替换为 .txt 文件，指出附件是恶意附件。|

下面是用户可以看到和看不到的：

|最终用户可访问|最终用户无法访问|
|---|---|
|已传递|Blocked|
|垃圾邮件|已替换|

**传递** 位置显示运行传递后的策略和检测的结果。 它链接到传递 **_操作_**。 以下为可能的值：

- *收件箱或文件夹*：电子邮件位于收件箱或文件夹中 (根据您的电子邮件规则) 。
- *本地或外部*：邮箱在云中不存在，但位于本地。
- *垃圾邮件* 文件夹：电子邮件位于用户的"垃圾邮件"文件夹中。
- *"已删除邮件"文件夹*：用户的"已删除邮件"文件夹中的电子邮件。
- *隔离*：电子邮件被隔离，不在用户的邮箱中。
- *失败*：电子邮件无法到达邮箱。
- *已* 丢弃：电子邮件在邮件流中的某位置丢失。

### <a name="email-timeline"></a>电子邮件时间线

电子邮件 **时间线** 是一种新的资源管理器功能，可改进管理员的搜寻体验。 它减少检查不同位置以尝试了解事件所花的时间。 当在电子邮件到达的同一时间或接近同一时间发生多个事件时，这些事件将显示在日程表视图中。 在"特殊操作"列中捕获在电子邮件传递后发生的一 **些** 事件。 管理员可以将时间线的信息与对邮件传递后采取的特殊操作相结合，以深入了解其策略如何工作、邮件最终路由在何处，在某些情况下，了解最终评估内容。

有关详细信息，请参阅 [调查和修正在 Office 365 中传递的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)。

### <a name="export-url-click-data"></a>导出 URL 单击数据

现在可以将 URL 单击报告导出到 Microsoft Excel 以查看其网络消息 **ID** 和单击裁定，这有助于说明 URL 单击流量的来源。 工作原理如下：在 Office 365 快速启动栏上的威胁管理中，按照以下链操作：

**资源管理器** \>**查看网络钓鱼** \>**单击** \>**顶部 URL 或** **URL 单击** \> 次数顶部选择任意记录以打开 URL 飞出。

When you select a URL in the list， you'll see a new **Export** button on the fly-out panel. 使用此按钮将数据移动到 Excel 电子表格，以便更轻松地报告。

按照此路径到达实时检测报告中的相同位置：

**资源管理器** \>**实时检测** \>**查看网络钓鱼** \>**URL** \>**顶部 URL** 或 **顶部单击** \> 选择任意记录以打开 URL 飞出控件 \> ，导航到 **"单击"** 选项卡。

> [!TIP]
> 当您通过资源管理器或关联的第三方工具搜索 ID 时，网络消息 ID 将单击映射回特定邮件。 此类搜索可标识与单击结果关联的电子邮件。 通过关联网络消息 ID，可以更快、更强大的分析。

> [!div class="mx-imgBorder"]
> ![资源管理器中的"单击"选项卡](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>查看通过技术在电子邮件中检测到的恶意软件

假设你想要查看在按 Microsoft 365 技术排序的电子邮件中检测到的恶意软件。 为此，请使用资源管理器>或[](threat-explorer-views.md#email--malware)实时检测的"电子邮件 (恶意软件"视图) 。

1. 在安全&中心 () ，选择威胁管理资源管理器 (或实时检测 <https://protection.office.com>  \> ) 。   (此示例使用 Explorer.) 

2. 在"**视图"** 菜单中，选择 **"电子邮件** \> **恶意软件"。**

   > [!div class="mx-imgBorder"]
   > ![资源管理器的视图菜单](../../media/ExplorerViewEmailMalwareMenu.png)

3. 单击 **"** 发件人"，然后选择 **"基本** \> **检测技术"。**

   你的检测技术现在用作报告的筛选器。

   > [!div class="mx-imgBorder"]
   > ![恶意软件检测技术](../../media/ExplorerEmailMalwareDetectionTech.png)

4. 选择一个选项。 然后选择" **刷新"** 按钮以应用该筛选器。

   > [!div class="mx-imgBorder"]
   > ![选定的检测技术](../../media/ExplorerEmailMalwareDetectionTechATP.png)

报告将刷新，以使用所选的技术选项显示电子邮件中检测到的恶意软件的结果。 在这里，你可以执行进一步的分析。

## <a name="view-phishing-url-and-click-verdict-data"></a>查看网络钓鱼 URL 和单击裁定数据

假设您希望查看通过电子邮件中的 URL（包括允许、阻止和覆盖的 URL 列表）的网络钓鱼尝试。 若要标识单击的 URL， [必须](atp-safe-links.md) 配置安全链接。 确保为安全 [链接](set-up-atp-safe-links-policies.md) 的单击保护和单击裁定日志记录设置了安全链接策略。

若要查看邮件中的网络钓鱼 URL 并单击网络钓鱼邮件中的 URL，请使用 Explorer[  >  ](threat-explorer-views.md#email--phish)的电子邮件网络钓鱼视图或实时检测。

1. 在安全&中心 () ，选择威胁管理资源管理器 (或实时检测 <https://protection.office.com>  \> ) 。   (此示例使用 Explorer.) 

2. 在"**视图"** 菜单中，选择 **"电子邮件** \> **钓鱼"。**

   > [!div class="mx-imgBorder"]
   > ![网络钓鱼上下文中资源管理器的"查看"菜单](../../media/ExplorerViewEmailPhishMenu.png)

3. 单击 **"** 发件人"，然后选择 **"URL 单击** \> **"裁定**。

4. 选择一个或多个选项，如"阻止"和"阻止覆盖"，然后选择与应用该筛选器的选项位于同一行上的"刷新"按钮。   (不刷新浏览器窗口。) 

   > [!div class="mx-imgBorder"]
   > ![URL 和单击裁定](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   报告刷新以显示报告下的"URL"选项卡上的两个不同的 URL 表：

   - **顶部 URL** 是筛选到的邮件中的 URL，以及每个 URL 的电子邮件传递操作计数。 在网络钓鱼电子邮件视图中，此列表通常包含合法 URL。 攻击者在邮件中混入好 URL 和坏 URL 以尝试传递这些 URL，但它们让恶意链接看起来更有趣。 URL 表按总电子邮件计数排序，但隐藏此列可简化视图。

   - **点击** 量居前的是单击的安全链接包装 URL，按总点击次数排序。 此列也不显示，以简化视图。 按列的总计数指示每个单击的 URL 的安全链接单击裁定计数。 在网络钓鱼电子邮件视图中，这些 URL 通常是可疑或恶意的 URL。 但视图可能包括不是威胁但包含钓鱼邮件的 URL。 此处不会显示单击未包链接的 URL。

   这两个 URL 表按传递操作和位置显示网络钓鱼电子邮件中的顶部 URL。 这些表显示了在出现警告时被阻止或访问的 URL 单击，因此你可以看到向用户显示哪些潜在的错误链接以及用户点击了哪些链接。 在这里，你可以执行进一步的分析。 例如，在图表下方，你可以看到在组织环境中被阻止的电子邮件中的顶部 URL。

   > [!div class="mx-imgBorder"]
   > ![阻止的浏览器 URL](../../media/ExplorerPhishClickVerdictURLs.png)

   选择 URL 以查看更多详细信息。

   > [!NOTE]
   > 在"URL"弹出对话框中，删除对电子邮件的筛选以显示环境中 URL 曝光的完整视图。 这允许你在资源管理器中筛选你关注的电子邮件，查找潜在威胁的特定 URL，然后通过 URL 详细信息对话框 (扩展你了解环境中 URL 的曝光) 而无需将 URL 筛选器添加到资源管理器视图本身。

### <a name="interpretation-of-click-verdicts"></a>单击裁定的解释

在"电子邮件"或"URL"飞出、"点击量"以及筛选体验内，你将看到不同的单击裁定值：

- **无：** 无法捕获 URL 裁定。 用户可能已经单击了 URL。
- **允许：** 允许用户导航到 URL。
- **已阻止：** 阻止用户导航到 URL。
- **待定裁定：** 用户被呈现了等待触发的页面。
- **阻止重写：** 阻止用户直接导航到 URL。 但是，用户会接管该块以导航到 URL。
- **已绕过待定裁定：** 向用户显示触发页面。 但用户会过度更改邮件以访问 URL。
- **错误：** 用户收到错误页，或捕获裁定时出错。
- **失败：** 捕获裁定时发生未知异常。 用户可能已经单击了 URL。

## <a name="review-email-messages-reported-by-users"></a>查看用户报告的电子邮件

假设您希望查看组织中用户通过报告邮件外接程序或报告网络钓鱼外接程序报告为垃圾邮件、非垃圾邮件或网络钓鱼[的电子邮件](enable-the-report-phish-add-in.md)。 [](enable-the-report-message-add-in.md) 若要查看它们，请使用资源管理器中的[  >  "电子邮件](threat-explorer-views.md#email--submissions)提交" (或实时检测) 。

1. 在安全&中心 () ，选择威胁管理资源管理器 (或实时检测 <https://protection.office.com>  \> ) 。   (此示例使用 Explorer.) 

2. 在"**视图"** 菜单中，选择 **"** \> **电子邮件提交"。**

   > [!div class="mx-imgBorder"]
   > ![适用于电子邮件资源管理器的"查看"菜单](../../media/explorer-view-menu-email-user-reported.png)

3. 单击 **"** 发件人"，然后选择 **"基本** \> **报告类型"。**

4. 选择一个选项，如 **钓鱼** 邮件，然后选择" **刷新"** 按钮。

   > [!div class="mx-imgBorder"]
   > ![用户报告的网络钓鱼](../../media/EmailUserReportedReportType.png)

报告将刷新以显示有关组织中人员报告为网络钓鱼尝试的电子邮件的数据。 可以使用此信息进行进一步分析，如有必要，在 [Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)中调整防钓鱼策略。

## <a name="start-automated-investigation-and-response"></a>启动自动调查和响应

> [!NOTE]
> Microsoft Defender for *Office 365* 计划 2 和 *Office 365 E5* 中提供了自动调查和响应功能。

[自动调查和响应](automated-investigation-response-office.md) 可以节省安全运营团队在调查和缓解网络攻击上花费的时间和精力。 除了配置可触发安全手册的警报外，还可以从资源管理器中的视图启动自动调查和响应过程。 有关详细信息，请参阅 [示例：安全管理员从资源管理器触发调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a>更多使用资源管理器和实时检测的方法

除了本文中概述的方案之外，资源管理器或实时检测功能中 (更多报告) 。 另请参阅以下文章：

- [查找和调查投递的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)
- [查看在 SharePoint Online、OneDrive 和 Microsoft Teams 中检测到的恶意文件](malicious-files-detected-in-spo-odb-or-teams.md)
- [大致了解威胁资源管理器中的 (和实时检测) ](threat-explorer-views.md)
- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft 威胁防护中的自动调查和响应](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

必须具有适用于 [Office 365 的 Microsoft Defender，](office-365-atp.md) 以使用资源管理器或实时检测。

- 资源管理器包含在 Defender for Office 365 计划 2 中。
- 实时检测报告包含在 Defender for Office 365 计划 1 中。
- 计划为应受 Office 365 Defender 保护的所有用户分配许可证。 资源管理器和实时检测显示许可用户的检测数据。

若要查看和使用资源管理器或实时检测，您必须具有适当的权限，例如授予安全管理员或安全读者的权限。

- 对于安全&合规中心，必须分配有以下角色之一：

  - 组织管理
  - 安全 (可以在 Azure Active Directory 管理中心 () <https://aad.portal.azure.com>
  - 安全读取者

- 对于 Exchange Online，必须在 Exchange 管理中心或 Exchange Online PowerShell 中分配 <https://admin.protection.outlook.com/ecp/> () 角色 [之一](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)：

  - 组织管理
  - 仅查看组织管理
  - 仅查看收件人
  - 合规性管理

若要详细了解角色和权限，请参阅以下资源：

- [安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)
- [Exchange Online 中的功能权限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>威胁资源管理器和实时检测之间的差异

- *实时检测报告在* Defender for Office 365 计划 1 中提供。 *威胁资源管理器* 在 Office 365 计划 2 的 Defender 中可用。
- 实时检测报告允许你实时查看检测。 威胁资源管理器也这样做，但它还提供给定攻击的其他详细信息。
- " *所有电子邮件* "视图在威胁资源管理器中可用，但在实时检测报告中不可用。
- 威胁资源管理器中包含更多筛选功能和可用操作。 有关详细信息，请参阅 [Microsoft Defender for Office 365 服务说明：跨 Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)计划的 Defender 的功能可用性。
