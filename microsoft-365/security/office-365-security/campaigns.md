---
title: Office 365 ATP 中的 Campaigns Views
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 了解 Office 365 高级威胁防护中的 Campaigns Views。
ms.openlocfilehash: 2d43b73a613ad6399a151a6bda39f236c7c913e8
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT + HT Review
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962757"
---
# <a name="campaign-views-in-office-365-atp"></a>Office 365 ATP 中的 Campaign Views

> [!NOTE]
> 本主题中所述的功能目前处于预览阶段，可能会发生更改。

Campaign Views 是 Office 365 安全与合规中心的高级威胁防护 (ATP) 中的一项功能，可以对服务中的钓鱼攻击进行识别和分类。 Campaign Views 可以帮助你：

- 高效调查和应对钓鱼攻击。

- 更好地了解攻击范围。

- 向决策者展示价值。

借助 Campaign Views，可以让你比任何人都更快获得有关攻击的更全面概览。

## <a name="what-is-a-campaign"></a>什么是活动 (campaign)？

活动是针对一个或多个组织的协同式电子邮件攻击。 当今，窃取凭据和公司数据的电子邮件攻击是有利可图的大生意。 随着旨在阻止攻击的技术不断发展，攻击者为了确保获得持续的成功，已具备改进方法的丰富经验。

Microsoft 利用在整个 Office 365 服务领域中积累的广泛的反钓鱼、反垃圾邮件和反恶意软件数据和经验，以识别活动。 根据若干因素对攻击信息进行分析和分类。 例如：

- **攻击来源**：源 IP 地址和发件人电子邮件域名。

- **攻击邮件属性**：攻击邮件的内容、样式和语气。

- **攻击收件人**：收件人域名、收件人工作职能（管理员、高管等）、公司类型（大型、小型、公共、私有等）和行业。

- **攻击有效负载**：恶意链接、附件或其他有效负载。

## <a name="campaign-views-the-office-365-security--compliance-center"></a>Campaign Views Office 365 安全与合规中心

在[安全与合规中心](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)中的以下位置可获取 Campaign Views：

- **威胁管理** \> **资源管理器** \> **查看** \> **钓鱼** \> **排名首位的活动（预览）**

- **威胁管理** \> **资源管理器** \> **查看** \> **所有电子邮件** \> **排名首位的活动（预览）**

![安全和合规中心中的活动概述](../media/campaigns-overview.png)

> [!TIP]
> 目前，唯一可用的筛选是日期范围。 如果看不到任何活动数据，请尝试更改日期范围。

“概述”页面显示有关该活动的以下信息：

- **名称**

- **示例主题**：活动中某封邮件的主题行。 请注意，并非活动中的_所有_邮件都具有此相同的主题行。

- **类型**：当前，该值将始终是**钓鱼**。

- **子类型**：此活动中作为钓鱼对象的品牌。 如果检测由 ATP 技术驱动，则会将前缀 **ATP** 添加到子类型值。

- **收件人**：此活动所面向的用户数。

- **递送数量**：在收件箱中收到此活动发送的邮件的用户数量。

- **ID**：活动的唯一标识符。

单击活动的名称时，活动详细信息将显示在浮出控件中。

## <a name="campaign-details"></a>活动详细信息

“活动详细信息”视图中提供了有关活动的大量信息：

- 活动信息：

  - **ID**：“概述”屏幕中活动的相同唯一标识符。

  - **开始时间**和**结束时间**：你选择的日期范围筛选器。

  - **影响**：你所选择的日期范围发送的邮件数量、收件箱中的邮件数量（即递送到收件箱的数量），以及单击钓鱼邮件中 URL 有效负载的用户数量。

  - 活动的时间线：活动的开始时间和结束时间以及随时间推移的邮件数量。

### <a name="campaign-flow"></a>活动流

关于活动的重要详细信息显示在**流程**部分中的水平流程图表（称为 _Sankey_ 图表）中。 这些详细信息将帮助你了解活动的元素和组织中的潜在影响。

![不包含用户 URL 单击次数的活动详细信息](../media/campaign-details-no-recipient-actions.png)

如果将鼠标悬停在图表中的水平带区上，则将看到相关邮件的数目（例如来自特定来源 IP 的邮件，使用指定发件人域名的来自来源 IP 的邮件等）。

此图表包含以下信息：

- **发件人 IP**

- **发件人域名**

- **筛选器裁定**：此处的值与[反垃圾邮件标头](anti-spam-message-headers.md)中所述的可用反钓鱼和反垃圾邮件筛选器裁定相关。 有意思的是值 **Tenant Allow**，该值表示组织中已配置的设置允许该服务中阻止的邮件（例如，Allowed Senders 列表中的域名）。

  - **Tenant Block**：该值指示组织中的设置（例如 [Blocked Senders 列表](create-block-sender-lists-in-office-365.md)中的域名条目）已检测到邮件并确定其来源。 对于未隔离的邮件，请查看阻止的发件人设置，以确定邮件送达的原因。

  - **已检测**

  - **Tenant Allow**

- **送达位置**：你希望调查发送到收件人的邮件（发送到收件箱或垃圾邮件文件夹），即使用户未单击邮件中的有效负载 URL。 此外，还可以将已隔离的邮件从[ Office 365 中的隔离电子邮件](quarantine-email-messages.md)中删除。

  - **垃圾邮件文件夹**

  - **隔离**

  - **收件箱**

#### <a name="url-clicks"></a>URL 单击次数

发送到收件人收件箱或垃圾邮件文件夹的邮件总有可能被用户执行操作（即用户将单击邮件中的恶意 URL）。 如果用户没有单击，则表明成功率低，虽然你当然需要首先确定这些恶意邮件为什么会发送到他们的邮箱。

如果用户单击了恶意 URL，则操作将显示在图表的 **URL 单击次数**区域。

![包含用户 URL 单击次数的活动详细信息](../media/campaign-details-with-recipient-actions.png)

- **Safe Links Block**：此值指示收件人单击了邮件上的有效负载 URL，但被组织中的 [ATP 安全链接](atp-safe-links.md)策略阻止。

- **Safe Links Block Override**：此值还指示收件人单击了邮件中的有效负载 URL，ATP 安全链接尝试阻止，但这些 URL 被允许替代阻止。 你需要调查[安全链接策略](set-up-atp-safe-links-policies.md)，了解为什么用户被允许替代安全链接裁定并单击恶意 URL。

### <a name="tabs"></a>选项卡

“活动详细信息”视图中有多个选项卡，可用于进一步调查活动。

- **URL 单击次数**：如果钓鱼邮件中的有效负载 URL 未被单击，则该部分为空。 如果用户能够单击 URL，则

  - **用户**<sup>\*</sup>

  - **URL**<sup>\*</sup>

  - **单击时间**

  - **单击操作**

- **发件人 IP**

  - **发件人 IP**<sup>\*</sup>

  - **总计数**

  - **收件箱邮件计数**

  - **阻止的计数**

  - **已通过 SPF**

- **发件人**

  - **发件人**

  - **总计数**

  - **收件箱邮件计数**

  - **阻止的计数**

  - **已通过 DKIM**

  - **已通过 DMARC**

- **有效负载**

  - **URL**<sup>\*</sup>

  - **总计数**

<sup>\*</sup> 单击此值将打开一个新浮出控件，其中包含有关“活动详细信息”视图顶部的指定项（用户、URL 等）的详细信息。 若要返回到“活动详细信息”视图，请单击新浮出控件中的“**完成**”。

### <a name="buttons"></a>按钮

通过“活动详细信息”视图中的按钮，可使用威胁资源管理器的强大功能进一步调查活动。

- **探索活动**：打开新的威胁资源管理器搜索选项卡，将**活动 ID** 值用作搜索筛选器。

- **浏览收件箱邮件**：打开新的威胁资源管理器搜索选项卡，将**活动 ID **和**送达位置：收件箱**用作搜索筛选器。
