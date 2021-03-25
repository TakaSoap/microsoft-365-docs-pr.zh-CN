---
title: 查看安全与合规中心内的电子邮件安全报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 了解如何查找和使用组织的电子邮件安全报告。 安全与合规中心提供&报告。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5d9f6d12fef8a2ef6241fbbd5e0e2a980284e9cc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203767"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>查看安全与合规中心内的电子邮件安全报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

安全与合规中心提供了各种报告 [&，](https://protection.office.com) 可帮助你查看电子邮件安全功能（如 Microsoft 365 中的反垃圾邮件、反恶意软件和加密功能）如何保护你的组织。 如果您具有 [必要的权限](#what-permissions-are-needed-to-view-these-reports)，可以在安全与合规中心内查看这些报告&"报告仪表板 \> **"。** 若要直接转到"报表"仪表板，请打开 <https://protection.office.com/insightdashboard> 。

![安全与合规中心&仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>遭到入侵的用户报告

> [!NOTE]
> 此报告适用于具有 Exchange Online 邮箱的 Microsoft 365 组织。 它不适用于独立 Exchange Online Protection (EOP) 组织。

"**遭到入侵的用户**"报告显示过去 7 天内标记为"可疑"或"受限"的用户帐户数量。 其中任一状态的帐户存在问题，甚至受到威胁。 通过频繁使用，可以使用报告来发现可疑或受限帐户的峰值甚至趋势。 有关遭到入侵的用户详细信息，请参阅响应遭到入侵 [的电子邮件帐户](responding-to-a-compromised-email-account.md)。

!["报告"仪表板中的"遭到入侵的用户"小组件](../../media/compromised-users-report-widget.png)

聚合视图显示过去 90 天的数据，而详细信息视图显示最近 30 天的数据。

若要查看报告，请打开安全与合规 [&，转到](https://protection.office.com)**报告仪表板** \> 并选择 **泄露的用户**。 若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=CompromisedUsers> 。

通过单击"筛选器"并选择以下一个或多个值，可以筛选图表和详细信息表：

- **开始日期和****结束日期**

- **可疑**：用户帐户已发送可疑电子邮件，并且存在被限制发送电子邮件的风险。

- **受限**：由于高度可疑的模式，已限制用户帐户发送电子邮件。

!["泄露的用户"报告中的报告视图](../../media/compromised-users-report-activity-view.png)

如果单击 **"查看详细信息表"，** 可以看到以下详细信息：

- **创建时间**
- **用户 ID**
- **操作**

若要返回到报告报表视图，请单击"查看 **报告"。**

## <a name="encryption-report"></a>加密报告

加密 **报告** 适用于在 Exchange Online (没有 Exchange Online 邮箱的独立 EOP 中的邮箱的 EOP) 。 组织的安全团队可以使用此报告中的信息来识别模式，并主动应用或调整敏感电子邮件的策略。 例如：

- 如果您看到大量由用户加密的电子邮件，您可能需要添加加密策略以自动加密某些用例。 有关详细信息，请参阅在 [Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md)中定义用于加密电子邮件的邮件流规则。

- 如果您具有许多可用的加密模板，但没有人使用它们，您可能会探索用户是否需要功能培训。

聚合视图允许筛选过去 90 天，而详细信息视图允许筛选 10 天。

若要查看报告，请打开安全与&[中心，](https://protection.office.com)**转到报告** 仪表板 \> ，然后选择加密 **报告**。 若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=EncryptionReport> 。

若要详细了解加密，请参阅 [Microsoft 365 中的电子邮件加密](../../compliance/email-encryption.md)。

### <a name="report-view-for-the-encryption-report"></a>加密报告的报告视图

可以在图表上使用以下筛选器：

- **按以下方式查看数据：邮件加密报告** 并按以下方式进行分解 **：加密** 方法：可以使用以下加密方法：

  - **按用户加密**
  - **按策略加密**

  如果单击 **"筛选器"，** 可以使用以下筛选器修改图表：

  - **开始日期和****结束日期**
  - 加密方法。
  - 加密模板。

- **按以下方式查看数据：邮件加密报告** 并按： **加密** 模板进行分解：可以使用以下加密方法：

  - **不要转发**
  - **仅加密**
  - **OME 上一个**
  - **自定义**

  如果单击 **"筛选器"，** 可以使用以下筛选器修改图表：

  - **开始日期和****结束日期**
  - 加密方法
  - 加密模板

- **查看数据者：前 5 个** 收件人域：此视图显示包含前 5 个收件人域的已发送邮件计数的饼图。

  如果单击 **"筛选器"，** 可以选择"**开始日期"和**"**结束日期"。**

### <a name="details-table-view-for-the-encryption-report"></a>加密报告的详细信息表视图

如果单击 **"查看详细信息表**"，显示的信息取决于您所查看的图表：

- **分解方式：加密方法** 或按： **加密** 模板进行分解：显示以下信息：

  - "日期"
  - **发件人地址**
  - **加密模板**
  - **加密方法**
  - **收件人地址**
  - **主题**

- **查看数据者：前 5 个收件人域**：

  - "日期"
  - **收件人域**
  - **邮件计数**

如果在详细信息 **表** 视图中单击"筛选器"，可以使用以下筛选器修改结果：

- **开始日期和****结束日期**
- 加密方法
- 加密模板

若要返回到报告报表视图，请单击"查看 **报告"。**

## <a name="mailflow-status-report"></a>邮件流状态报告

邮件 **流状态报告** 包含有关恶意软件、垃圾邮件、网络钓鱼和边缘阻止邮件的信息。 有关详细信息，请参阅邮件 [流状态报告](view-mail-flow-reports.md#mailflow-status-report)。

## <a name="malware-detections-in-email-report"></a>电子邮件报告中的恶意软件检测

电子邮件 **报告中的恶意软件** 检测显示有关传入和传出电子邮件中的恶意软件检测 (Exchange Online Protection 或 EOP) 。 有关 EOP 中的恶意软件保护详细信息，请参阅 [EOP 中的反恶意软件保护](anti-malware-protection.md)。

 聚合视图筛选器允许 90 天，而详细信息表筛选器仅允许 10 天。

若要查看报告，请打开安全与&中心，转到报告 [仪表板](https://protection.office.com) \> ，然后选择 **电子邮件中的恶意软件检测**。 若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=MalwareDetections> 。

!["报告"仪表板中电子邮件小部件中的恶意软件检测](../../media/malware-detections-widget.png)

通过单击"筛选器"并选择以下选项，可以筛选图表 **和详细信息** 表：

- **开始日期和****结束日期**
- **入站**
- **出站**

![电子邮件报告中的恶意软件检测中的报告视图](../../media/malware-detections-report-view.png)

如果单击 **"查看详细信息表"，** 可以看到以下详细信息：

- "日期"
- **发件人地址**
- **收件人地址**
- **邮件 ID：** 在邮件 **头的 Message-ID** 头字段中可用，并且应该是唯一的。 示例值是 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (尖括号) 。
- **主题**
- **Filename**
- **恶意软件名称**

若要返回到报告报表视图，请单击"查看 **报告"。**

## <a name="mail-latency-report"></a>邮件延迟报告

邮件 **延迟报告** 包含有关组织中遇到的邮件传递和触发延迟的信息。 有关详细信息，请参阅邮件 [延迟报告](view-reports-for-mdo.md#mail-latency-report)。

## <a name="sent-and-received-email-report"></a>已发送和已接收电子邮件报告

" **已发送和** 已接收电子邮件"报告包含有关恶意软件、垃圾邮件、邮件流规则 (也称为传输规则) ，以及电子邮件进入服务后的高级恶意软件检测。 有关详细信息，请参阅已 [发送和已接收电子邮件报告](view-mail-flow-reports.md#sent-and-received-email-report)。

## <a name="spam-detections-report"></a>垃圾邮件检测报告

垃圾邮件 **检测报告显示** EOP 阻止的垃圾邮件。 邮件单独计数，而不是按收件人计数。 例如，如果将同一垃圾邮件发送给您组织的 100 个收件人，则它算作一封邮件。

聚合视图允许筛选 90 天，而详细信息表允许筛选 10 天。

若要查看报告，请打开安全与&中心 **，转到报告**[仪表板](https://protection.office.com) \> ，然后选择垃圾邮件 **检测**。 若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=SpamDetections> 。

!["报告"仪表板中的"垃圾邮件检测"小组件](../../media/spam-detections-report-widget.png)

有关反垃圾邮件保护的信息，请参阅 [EOP 中的反垃圾邮件保护](anti-spam-protection.md)。

### <a name="report-view-for-the-spam-detections-report"></a>垃圾邮件检测报告的报告视图

下表中提供了以下报表视图：

- **Break down by： Action**： The following event types are shown：

  - **已筛选的垃圾邮件内容**
  - **垃圾邮件 IP 阻止**
  - **垃圾邮件信封阻止**
  - **垃圾邮件 DBEB 筛选器**：基于目录的边缘阻止 (DBEB) 

  当您将鼠标悬停在图表中 (数据点) 时，可以看到当天阻止的项目数以及如何对这些项目进行分类。

  ![垃圾邮件检测报告中的操作视图](../../media/spam-detections-report-action-view.png)

- **中断时间：方向**：显示以下方向：

  - **入站**
  - **出站**

  ![垃圾邮件检测报告中的方向视图](../../media/spam-detections-report-direction-view.png)

如果 **单击筛选器** 中的报表视图，可以使用以下筛选器修改结果：

- **开始日期和****结束日期**
- 方向值
- 事件类型值

### <a name="details-table-view-for-the-spam-detections-report"></a>垃圾邮件检测报告的详细信息表视图

如果在任 **一视图中单击** "查看详细信息报表视图，将显示以下信息：

- "日期"
- **发件人地址**
- **收件人地址**
- **事件类型**
- **操作**
- **主题**

如果单击 **详细信息表中的** "筛选器"，可以使用以下筛选器修改结果：

- **开始日期和****结束日期**
- 方向值
- 事件类型值

若要返回到报告报表视图，请单击"查看 **报告"。**

## <a name="spoof-detections-report"></a>欺骗检测报告

欺骗 **检测** 报告显示检测到的欺骗邮件数，以及出于合法业务原因 (欺骗邮件被视为"良好"的邮件) 。 有关欺骗功能详细信息，请参阅 [EOP 中的反欺骗保护](anti-spoofing-protection.md)。

报告聚合视图允许筛选 90 天，而详细信息视图仅允许筛选 10 天。

若要查看报告，请打开安全与&中心，**转到报告**[仪表板](https://protection.office.com) \> 并选择 **欺骗检测**。 若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=SpoofMailReport> 。

![报告仪表板中的欺骗检测小组件](../../media/spoof-detections-widget.png)

当您将鼠标悬停在 (中) 的数据点时，可以看到经过多少封欺骗邮件。

通过单击"筛选器"并选择以下一个或多个值，可以筛选图表和详细信息表：

- **开始日期和****结束日期**

- **良好的邮件**

- **捕获为垃圾邮件**

![欺骗检测报告中的报告视图](../../media/spoof-detections-report-view.png)

如果单击 **"查看详细信息表"，** 可以看到以下详细信息：

- "日期"
- **欺骗发件人**
- **真正的发件人**
- **发件人 IP**
- **操作**
- **邮件计数**

若要返回到报告报表视图，请单击"查看 **报告"。**

## <a name="threat-protection-status-report"></a>威胁防护状态报告

威胁 **防护状态报告** 在 EOP 和 Microsoft Defender for Office 365 中均可用;但是，报告包含不同的数据。 例如，EOP 客户可以查看有关电子邮件中检测到的恶意软件的信息，但不能查看有关 [SharePoint、OneDrive](mdo-for-spo-odb-and-teams.md)和 Microsoft Teams 的安全附件检测到的恶意文件的信息。

该报告提供包含恶意内容的电子邮件（如反恶意软件引擎阻止的文件或网站地址 (URL) 、零时差自动清除[ (ZAP) ](zero-hour-auto-purge.md)和 Defender for Office 365 功能（如安全链接、安全附件和[防](set-up-anti-phishing-policies.md)钓鱼）的计数。 [](safe-links.md) [](safe-attachments.md) 您可以使用此信息来确定趋势或确定组织策略是否需要调整。

**注意**：如果邮件发送给五个收件人，则我们将邮件计为五个不同的邮件，而不是一封邮件，了解这一点很重要。

若要查看报告，请打开安全与&中心，**转到报告**[仪表板](https://protection.office.com) \> ，然后选择 **威胁防护状态**。 若要直接转到报告，请打开以下 URL 之一：

- Microsoft Defender for Office 365： <https://protection.office.com/reportv2?id=TPSAggregateReportATP>
- EOP： <https://protection.office.com/reportv2?id=TPSAggregateReport>

![报告仪表板中的威胁防护状态小组件](../../media/threat-protection-status-report-widget.png)

默认情况下，图表显示过去 7 天的数据。 如果单击 **"筛选器**"，可以选择 90 天的日期范围 (试用版订阅可能限制为 30) 。 详细信息表视图允许筛选 30 天。

### <a name="report-view-for-the-threat-protection-status-report"></a>威胁防护状态报告的报告视图

以下视图可用：

- **查看数据者：概述**：显示以下检测信息：

  - **电子邮件恶意软件**
  - **电子邮件钓鱼邮件**
  - **内容恶意软件**

  ![威胁防护状态报告中的概述视图](../../media/threat-protection-status-report-overview-view.png)

- **查看数据者：内容 \> 恶意软件**<sup>1：</sup>显示了适用于 Office 365 组织的 Microsoft Defender 的以下信息：

  - **反恶意软件引擎**：Microsoft [365](virus-detection-in-spo.md)中的内置病毒检测在 Sharepoint、OneDrive 和 Microsoft Teams 中检测到的恶意文件。
  - **文件触发**[：SharePoint、OneDrive](mdo-for-spo-odb-and-teams.md)和 Microsoft Teams 的安全附件检测到的恶意文件。

  ![威胁防护状态报告中的内容恶意软件视图](../../media/threat-protection-status-report-content-malware-view.png)

- **查看数据者：消息替代**：显示以下替代原因信息：

  - **本地跳过**
  - **IP 允许**
  - **邮件流规则**
  - **发件人允许**
  - **域允许**
  - **ZAP 未启用**
  - **未启用垃圾邮件文件夹**
  - **用户安全发件人**
  - **用户安全域**

  ![威胁防护状态报告中的邮件替代视图](../../media/threat-protection-status-report-message-override-view.png)

- **按以下条件进行分解：检测** 技术和 **查看数据者： \> 电子邮件** 钓鱼邮件：显示以下信息：

  - **ATP 生成的 URL 信誉**<sup>1：</sup>其他 Microsoft 365 客户的 Defender for Office 365 触发生成的恶意 URL 信誉。
  - **高级钓鱼筛选器**：基于机器学习的网络钓鱼信号。
  - **反欺骗 - DMARC 失败**：邮件上的 DMARC 身份验证失败。
  - **反欺骗 - 组织内部**：发件人正在尝试欺骗收件人域。
  - **反欺骗 - 外部域**：发件人正在尝试欺骗其他一些域。
  - **品牌模拟**：模拟基于发件人的已知品牌。
  - **域模拟**<sup>1：</sup>模拟客户拥有或定义的域。
  - **EOP URL 信誉**：恶意 URL 信誉。
  - **常规网络钓鱼筛选器**：基于分析员规则的网络钓鱼信号。
  - **其他**
  - **网络钓鱼 ZAP**<sup>2：</sup>零时差自动清除网络钓鱼邮件。
  - **URL 触发**<sup>1</sup>
  - **用户模拟**<sup>1：</sup>模拟管理员定义或通过邮箱智能学习的用户。

  ![威胁防护状态报告中的网络钓鱼电子邮件的检测技术视图](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **按以下条件进行分解：检测** 技术和 **查看数据者： \> 电子邮件** 恶意软件：显示以下信息：

  - **ATP 生成的文件信誉**<sup>1：Defender</sup>for Office 365 触发生成的所有恶意文件信誉。
  - **反恶意软件引擎**<sup>1：</sup>来自反恶意软件引擎的检测。
  - **反恶意软件策略文件类型阻止**：这些是由于邮件中标识的恶意文件类型而筛选掉的电子邮件。
  - **文件触发**<sup>1：</sup>安全附件检测。
  - **恶意文件信誉**
  - **恶意软件 ZAP**<sup>2</sup>
  - **其他**

  ![威胁防护状态报告中恶意软件的检测技术视图](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **按以下条件进行分解：策略** 类型和 **查看数据者：电子邮件 \> 钓鱼** 或查看数据 **者： \>** 电子邮件恶意软件：显示以下信息：

  - **反恶意软件**
  - **安全附件**<sup>1</sup>
  - **防钓鱼**
  - **反垃圾邮件**
  - **邮件流规则** (也称为传输规则) 
  - **其他**

  ![威胁防护状态报告中的网络钓鱼电子邮件的策略类型视图](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **按以下条件进行分解：传递** 状态和 **查看数据者：电子邮件 \> 钓鱼** 邮件或查看数据 **者： \>** 电子邮件恶意软件：显示以下信息：

  - **传递失败**
  - **已丢弃**
  - **转发**
  - **托管邮箱：自定义文件夹**
  - **托管邮箱：已删除项目**
  - **托管邮箱：收件箱**
  - **托管邮箱：垃圾邮件**
  - **本地服务器：已传递**
  - **隔离**

  ![威胁防护状态报告中网络钓鱼电子邮件的传递状态视图](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>仅 1</sup> 个 Defender for Office 365

<sup>2"</sup> 零时差自动清除" (ZAP) 在独立 EOP 中 (它仅适用于 Exchange Online 邮箱) 。

如果单击 **"筛选器**"，可用的筛选器取决于您所查看的图表：

- For **View data by： Content \> Malware**， you can modify the report by **Start date** and End **date**， and the **Detection** value.

- 对于 **View data by： Message Override**，您可以使用以下筛选器修改报告：

  - **开始日期和****结束日期**
  - **替代原因**
  - **Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。 有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。
  - **域**

- 对于所有其他视图，您可以使用以下筛选器修改报告：

  - **开始日期和****结束日期**
  - **检测**
  - **受保护****：ATP** 或 **EOP**
  - **Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。 有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。
  - **域**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>威胁防护状态报告的详细信息表视图

如果单击 **"查看详细信息表**"，显示的信息取决于您所查看的图表：

- **查看数据者：概述**：没有 **"查看详细信息表"** 按钮可用。

- **查看数据者：内容 \> 恶意软件**：

  - "日期"
  - **位置**
  - **定向者**
  - **恶意软件名称**

  如果在此 **视图中** 单击"筛选器"，可以按"开始日期"和"结束日期"以及 **"检测"** 值修改报告。

- **查看数据者：邮件替代**：

  - "日期"
  - **主题**
  - **发件人**
  - **Recipients**
  - **检测者**
  - **替代原因**
  - **泄露来源**
  - **Tags**

  如果单击 **此视图中** 的"筛选器"，可以使用以下筛选器修改报告：

  - **开始日期和****结束日期**
  - **替代原因**
  - **Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。 有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。
  - **域**
  - **收件人 (** 请注意，此可筛选属性仅适用于详细信息表视图) 

- 所有其他图表：

  - "日期"
  - **主题**
  - **发件人**
  - **Recipients**
  - **检测者**
  - **传递状态**
  - **泄露来源**
  - **Tags**

  如果单击 **"筛选器"，** 可以使用以下筛选器修改报告：

  - **开始日期和****结束日期**
  - **检测**
  - **受保护：** **Defender for Office 365** 或 **EOP**
  - **Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。 有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。
  - **域**
  - **收件人 (** 请注意，此可筛选属性仅适用于详细信息表视图) 

## <a name="top-malware-report"></a>热门恶意软件报告

" **热门恶意软件** "报告显示 [EOP](anti-malware-protection.md)中的反恶意软件保护检测到的各种恶意软件。

若要查看报告，请打开安全与&中心，**转到报告**[仪表板](https://protection.office.com) \> ，然后选择 **热门恶意软件**。 若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=TopMalware> 。

![报告仪表板中的热门恶意软件小组件](../../media/top-malware-report-widget.png)

当您将鼠标悬停在饼图中的一个浮点上时，可以看到某种恶意软件的名称，以及检测到具有该恶意软件的邮件数。

![热门恶意软件报表视图](../../media/top-malware-report-view.png)

如果单击 **"查看详细信息表"，** 可以看到以下详细信息：

- **热门恶意软件**
- **Count**

如果在 **视图或详细信息** 表视图中报表视图筛选器，可以指定开始日期和 **结束日期的日期范围**。 

## <a name="url-threat-protection-report"></a>URL 威胁防护报告

适用于 Office 365 的 Microsoft Defender 中提供了 **URL** 威胁防护报告。 有关详细信息，请参阅 [URL 威胁防护报告](view-reports-for-mdo.md#url-threat-protection-report)。

## <a name="user-reported-messages-report"></a>用户报告的邮件报告

用户 **报告** 的邮件报告显示有关用户使用报告邮件外接程序或报告网络钓鱼外接程序报告为垃圾邮件、网络钓鱼尝试或良好邮件 [的电子邮件的信息](enable-the-report-phish-add-in.md)。 [](enable-the-report-message-add-in.md)

每封邮件的详细信息可用，包括传递原因，例如为组织配置的垃圾邮件策略例外或邮件流规则。 若要查看详细信息，请选择用户报告列表中的某个项目，然后查看"摘要"和"详细信息"选项卡 **上** 的信息。 

![The User-Reported Messages report shows messages users labeled as junk， not junk， or phishing attempts.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

若要查看此报告，在安全与 [&，](https://protection.office.com)请执行下列操作之一：

- 转到"**威胁管理** \> **""仪表板** \> **""用户报告的邮件"。**

- 转到"**威胁管理** \> **""** \> **查看用户报告的邮件"。**

![在安全与&中心，选择"威胁管理 \> ""查看 \> 用户报告的邮件"](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> 为了使用户报告的邮件报告正常工作，必须为 Office 365 环境启用审核日志记录。  通常是由在 Exchange Online 中分配为审核日志的角色执行。 有关详细信息，请参阅打开或关闭 [Microsoft 365 审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="what-permissions-are-needed-to-view-these-reports"></a>查看这些报告需要哪些权限？

若要查看和使用本文中所述的报告，你需要是安全与合规中心内以下角色&之一：

- **组织管理**
- **安全管理员**
- **安全读者**
- **全局读者**

有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

注意：将用户添加到 Microsoft 365 管理中心的相应 Azure Active Directory 角色会为用户提供安全 & 合规中心所需的权限以及Microsoft 365 中其他功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="what-if-the-reports-arent-showing-data"></a>如果报告未显示数据，该做什么？

如果报告中未显示数据，请仔细检查策略是否正确设置。 若要了解更多信息，请参阅 [防范威胁](protect-against-threats.md)。

## <a name="related-topics"></a>相关主题

[EOP 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)

[安全与合规中心内的智能报告和见解](reports-and-insights-in-security-and-compliance.md)

[在安全与合规中心内查看&流报告](view-mail-flow-reports.md)

[查看适用于 Office 365 的 Defender 报告](view-reports-for-mdo.md)
