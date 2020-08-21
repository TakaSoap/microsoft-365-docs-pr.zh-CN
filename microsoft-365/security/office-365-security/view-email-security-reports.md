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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 了解如何查找和使用组织的电子邮件安全报表。 电子邮件安全报告位于安全与&合规中心内。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b714d9dc4e3ca143d2cb2d7164f8c3c737d1928
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826501"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>查看安全与合规中心内的电子邮件安全报告

安全 & 合规中心提供各种 [报告，](https://protection.office.com) 有助于查看 Microsoft 365 中的电子邮件安全功能（如 Microsoft 365 中的反垃圾邮件、反恶意软件和加密功能）如何保护你的组织。 如果你具有必要 [的权限，](#what-permissions-are-needed-to-view-these-reports)可通过转到"报表仪表板"在安全&合规性中心查看 **这些** \> **报告**。 若要直接转到"报表"仪表板，请打开 <https://protection.office.com/insightdashboard> 。

![安全与合规中心中的&仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>被已被证明的用户报告

> [!NOTE]
> 此报告在具有 Exchange Online 邮箱的 Microsoft 365 组织中可用。 在独立的 Exchange Online Protection 和 EOP () 不可用。

受 **到入入禁的用户** 报告显示过去 7 天内标记为 **"可** 疑"或"受 **限** "的用户帐户的数量。 这两种状态的帐户均有问题，甚至受到了入保护。 通过使用频繁使用，你可以使用报告来发现可疑帐户或受限帐户中的峰值，甚至是趋势。 有关被入入入安全的用户的详细信息，请参阅["答复被入解的电子邮件帐户"。](responding-to-a-compromised-email-account.md)

!["报表"仪表板中的"已受到入禁升级的用户"小部件](../../media/compromised-users-report-widget.png)

聚合视图显示最近 90 天的数据，详细信息视图显示最近 30 天的数据。

若要查看报告，请打开[安全&合规中心](https://protection.office.com)，转到 **"报告** \> **仪表板"，** 然后选择 **"已被入入威用户"。** 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=CompromisedUsers> 。

通过单击"筛选器"，然后选择下面的一个或多个值可同时**Filters**筛选图表和详细信息表：

- **开始日期** 和 **结束日期**

- **可疑：用户帐户已**发送可疑电子邮件，有风险即被限制发送电子邮件。

- **受**限：因高度可疑的模式，用户帐户被限制发送电子邮件。

![被入入禁，用户报告中的报表视图](../../media/compromised-users-report-activity-view.png)

如果单击" **查看详细信息表**"，可以看到以下详细信息：

- **创建时间**
- **用户 ID**
- **操作**

要返回到数据库报表视图，请单击"**查看报告"。**

## <a name="encryption-report"></a>加密报告

在 **没有 Exchange** Online 邮箱的情况下，在未 (EXCHANGE Online 的邮箱的 EOP 订阅中，或独立 EOP 中，无法) 。 组织的安全团队可以使用此报告中的信息来识别模式，并主动应用或调整敏感电子邮件的策略。 例如：

- 如果您看到大量用户加密的电子邮件，您可能希望添加加密策略以针对某些用例自动进行加密。 有关详细信息，请参阅" [定义邮件流规则"，用于加密 Microsoft 365 中的电子邮件](../../compliance/define-mail-flow-rules-to-encrypt-email.md)。

- 如果有大量可用的加密模板，但没有人使用它们，则可能了解用户是否需要功能培训。

聚合视图允许筛选过去 90 天，而详细信息视图允许筛选 10 天。

若要查看报告，请打开安全[&合规中心](https://protection.office.com)，转到"**报告** \> **仪表板"，** 然后选择"**加密报告"。** 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=EncryptionReport> 。

若要了解有关加密的详细信息，请参阅 [Microsoft 365 中的电子邮件加密](../../compliance/email-encryption.md)。

### <a name="report-view-for-the-encryption-report"></a>加密报告的报告视图

可以在图表上使用以下筛选器：

- **查看数据：邮件加密报告和****按加密方式进行分解**：加密方法：以下加密方法可用：

  - **用户加密**
  - **按策略加密**

  如果单击 **"筛选器**"，则可以使用以下筛选器修改图表：

  - **开始日期** 和 **结束日期**
  - 加密方法。
  - 加密模板。

- **查看数据：邮件加密报告和****按以下问题进行分解：加密模板**：有以下加密方法可用：

  - **不要转发**
  - **仅加密**
  - **OME 之前**
  - **自定义**

  如果单击 **"筛选器**"，则可以使用以下筛选器修改图表：

  - **开始日期** 和 **结束日期**
  - 加密方法
  - 加密模板

- **查看数据：顶部 5 个收件人域**：此视图显示最上面 5 个收件人域已发送邮件计数的饼图。

  如果单击"**筛选器"，** 可以选择开始**日期和结束****日期**。

### <a name="details-table-view-for-the-encryption-report"></a>加密报表的详细信息表视图

如果您单击 **"查看详细信息**表"，显示的信息取决于您正在查看的图表：

- **按以下详细信息进行分****解：加密方法或细分：加密模板**：以下信息如下所示：

  - **Date**
  - **发件人地址**
  - **加密模板**
  - **加密方法**
  - **收件人地址**
  - **主题**

- **查看数据是：前 5 个收件人域**：

  - **Date**
  - **收件人域**
  - **邮件计数**
  
如果单击 **详细信息表** 视图中的"筛选器"，则可以使用以下筛选器修改结果：

- **开始日期** 和 **结束日期**
- 加密方法
- 加密模板

要返回到数据库报表视图，请单击"**查看报告"。**

## <a name="mailflow-status-report"></a>邮件流状态报告

邮件流 **状态报告包含** 关于恶意软件、垃圾邮件、网络钓鱼和边缘阻止邮件的信息。 有关详细信息，请参阅邮件流 [状态报告](view-mail-flow-reports.md#mailflow-status-report)。

## <a name="malware-detections-in-email-report"></a>电子邮件报告中的恶意软件检测

电子邮件 **报告中的恶意软件检测显示** Exchange Online Protection 或 EOP 用户检测到的恶意软件时，传入和传出的电子邮件的 (恶意软件) 。 若要详细了解 EOP 中的恶意软件保护，请参阅 [EOP 中的反恶意软件保护](anti-malware-protection.md)。

 聚合视图筛选器允许 90 天，而详细信息表筛选仅允许 10 天。

要查看报告，请打开[安全&合规中心](https://protection.office.com)，转到 **"** \> **报告仪表板"，** 然后选择**电子邮件中的"恶意软件检测"。** 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=MalwareDetections> 。

!["报告"仪表板中电子邮件小部件的恶意软件检测](../../media/malware-detections-widget.png)

通过单击"筛选器"并选择，可同时 **筛选图表** 和详细信息表：

- **开始日期** 和 **结束日期**
- **入站**
- **出站**

![电子邮件报告中恶意软件检测中的报告视图](../../media/malware-detections-report-view.png)

如果单击" **查看详细信息表**"，可以看到以下详细信息：

- **Date**
- **发件人地址**
- **收件人地址**
- **邮件 ID：** 在邮件头 **中的"邮件 ID** 头"字段中可用，并且应是唯一的。 例如，为 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (括号) 。
- **主题**
- **Filename**
- **恶意软件名称**

要返回到数据库报表视图，请单击"**查看报告"。**

## <a name="sent-and-received-email-report"></a>已发送和已接收电子邮件报告

" **已发送和已接收的** 电子邮件报告"包含有关恶意软件、垃圾邮件、邮件流规则 (在电子邮件进入服务后的恶意软件、) 和高级恶意软件检测的信息。 有关详细信息，请参阅"发送 [和接收的电子邮件"报告](view-mail-flow-reports.md#sent-and-received-email-report)。

## <a name="spam-detections-report"></a>垃圾邮件检测报告

**垃圾邮件检测报告**显示被 EOP 阻止的垃圾邮件。 邮件计数单独计数，而不是每个收件人。 例如，如果向组织中的 100 个收件人发送了同一垃圾邮件，则这会计数为一封邮件。

聚合视图允许进行 90 天筛选，而详细信息表允许进行 10 天筛选。

若要查看报告，请打开[安全&合规中心](https://protection.office.com)，转到 **"** \> **报告仪表板"，** 然后选择 **"垃圾邮件检测"。** 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SpamDetections> 。

!["报告"仪表板中的垃圾邮件检测小部件](../../media/spam-detections-report-widget.png)

有关反垃圾邮件保护的详细信息，请参阅 EOP [中的反垃圾邮件保护](anti-spam-protection.md)。

### <a name="report-view-for-the-spam-detections-report"></a>垃圾邮件检测报告的报告视图

下面的图表提供了报表视图：

- **按以下分解：** 操作：显示以下事件类型：

  - **已筛选的垃圾邮件内容**
  - **垃圾邮件 IP 阻止**
  - **垃圾邮件信封阻止**
  - **垃圾邮件 DBEB 筛选器**：基于目录的边缘 (DBEB) 

  当您将鼠标悬停在一天 (的数据点) 图表中时，可以看到阻止该天的项目数以及这些项目的分类方式。

  ![垃圾邮件检测报告中的操作视图](../../media/spam-detections-report-action-view.png)

- **Break down by：Direction：** The following directions are shown：

  - **入站**
  - **出站**

  ![垃圾邮件检测报告中的方向视图](../../media/spam-detections-report-direction-view.png)

如果单击 **文件** 中的报表视图筛选器，可以用以下筛选器修改结果：

- **开始日期** 和 **结束日期**
- 方向值
- 事件类型值

### <a name="details-table-view-for-the-spam-detections-report"></a>垃圾邮件检测报告的详细表视图

如果单击任何 **页面的** "查看详细信息报表视图，会显示以下信息：

- **Date**
- **发件人地址**
- **收件人地址**
- **事件类型**
- **操作**
- **主题**

如果单击 **详细信息** 表中的"筛选器"，则可以使用以下筛选器修改结果：

- **开始日期** 和 **结束日期**
- 方向值
- 事件类型值

要返回到数据库报表视图，请单击"**查看报告"。**

## <a name="spoof-detections-report"></a>欺骗检测报告

欺 **骗性检测报告** 显示检测到的欺骗邮件数以及被视为视为"良好"的欺骗邮件（出于合法 (理由) ）。 有关欺骗的详细信息，请参阅 EOP [中的防欺骗保护](anti-spoofing-protection.md)。

报告的聚合视图允许 90 天进行筛选，而详细信息视图仅支持 10 天的筛选。

若要查看报表，请打开 [安全与&中心](https://protection.office.com)，转到 **"** \> **报表仪表板"，** 然后选择 **"欺骗"检测**。 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SpoofMailReport> 。

!["报告"仪表板中的欺骗检测小部件](../../media/spoof-detections-widget.png)

当您将鼠标悬停在某个 (数据) 数据点时，你可以看到有多少欺骗邮件传输。

通过单击"筛选器"，然后选择下面的一个或多个值可同时**Filters**筛选图表和详细信息表：

- **开始日期** 和 **结束日期**

- **正常邮件**

- **Caught as spam**

![欺骗检测报告中的报告视图](../../media/spoof-detections-report-view.png)

如果单击" **查看详细信息表**"，可以看到以下详细信息：

- **Date**
- **伪的发件人**
- **真正的发件人**
- **发件人 IP**
- **操作**
- **邮件计数**

要返回到数据库报表视图，请单击"**查看报告"。**

## <a name="threat-protection-status-report"></a>威胁防护状态报告

威 **胁防护状态** 报告在 EOP 和 Office 365 ATP 中均可用;但是，报表中包含其他数据。 例如，EOP 客户可查看电子邮件中检测到的恶意软件信息，但不查看 [在 SharePoint Online、OneDrive](atp-for-spo-odb-and-teams.md)或 Microsoft Teams 中检测到的恶意文件的信息。

该报告提供包含恶意内容的唯一电子邮件的聚合计数，例如 (但) 被反恶意软件引擎阻止的文件或网站地址 (、零时差[自动清除 (ZAP) ），](zero-hour-auto-purge.md)以及 ATP 功能（[如 ATP 安全链接](atp-safe-links.md)[、ATP 安全](atp-safe-attachments.md)附件和[ATP 防钓鱼](set-up-anti-phishing-policies.md)）。 可以使用此信息来确定趋势或确定组织策略是否需要调整。

若要查看报告，请打开安全 [&合规中心，](https://protection.office.com)转到"报表 **仪表板** \> **"，** 然后选择"威 **胁防护"状态**。 若要直接转到报告，请打开以下 URL 之一：

- Office 365 <https://protection.office.com/reportv2?id=ATPV2AggregateReport> ATP：
- EOP： <https://protection.office.com/reportv2?id=ATPAggregateLightReport>

!["报表"仪表板中的威胁防护状态小部件](../../media/threat-protection-status-report-widget.png)

默认情况下，该图表显示过去 7 天的数据。 如果单击 **"筛选器"，** 可以选择试用订阅 (90 天日期范围，此日期范围不可为 30) 。 详细信息表视图允许筛选 30 天。

### <a name="report-view-for-the-threat-protection-status-report"></a>威胁防护状态报告的报告视图

提供了以下视图：

- **查看数据：概述**：显示以下检测信息：

  - **电子邮件恶意软件**
  - **电子邮件钓鱼邮件**
  - **内容恶意软件**

  ![威胁防护状态报告中的概述视图](../../media/threat-protection-status-report-overview-view.png)

- **通过"内容"查看数据 \> 恶意软件**<sup>1：</sup>以下是 Office 365 ATP 组织显示的信息：

  - **反恶意软件引擎**
  - **文件销销**

  ![威胁防护状态报告中的内容恶意软件视图](../../media/threat-protection-status-report-content-malware-view.png)

- **细分：检测技术和查看****数据：电子邮件 \> 网络钓鱼**：显示以下信息：

  - **ATP 生成的 URL 信誉**<sup>1</sup>
  - **高级钓鱼筛选器**
  - **反欺骗：DMARC 失败**
  - **反欺骗：组织内**
  - **反欺骗：外部域**
  - **品牌模拟**
  - **域模拟**<sup>1</sup>
  - **EOP URL 信誉**
  - **常规钓鱼筛选器**
  - **其他**
  - **网络钓鱼邮件 ZAP**<sup>2</sup>
  - **URL 表示形式**<sup>1</sup>
  - **用户模拟**<sup>1</sup>

  ![威胁防护状态报告中网络钓鱼电子邮件的检测技术视图](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **"分解条件"：检测技术和****"查看数据"： \> 电子邮件恶意软件**：显示以下信息：

  - **ATP 生成的文件信誉**<sup>1</sup>
  - **反恶意软件引擎**<sup>1</sup>
  - **反恶意软件策略文件类型阻止**
  - **文件销销**<sup>1</sup>
  - **恶意文件信誉**
  - **恶意软件 ZAP**<sup>2</sup>
  - **其他**

  ![威胁防护状态报告中恶意软件的检测技术视图](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **按以下方式分解：策略****类型和查看数据： \> 电子邮件网络钓鱼或****查看数据： \> 电子邮件恶意软件**：显示以下信息：

  - **反恶意软件**
  - **安全附件**<sup>1</sup>
  - **反钓鱼邮件**
  - **反垃圾邮件**
  - **邮件流规则** (也称为传输规则) 
  - **其他**

  ![威胁防护状态报告中网络钓鱼电子邮件的策略类型视图](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **按以下方式分解：传递**状态**和查看数据： \> 电子邮件网络钓鱼或****查看数据：电子邮件 \> 恶意软件**：显示以下信息：

  - **传递失败**
  - **Dropped**
  - **Forwarded**
  - **托管邮箱：自定义文件夹**
  - **托管邮箱：已删除邮件**
  - **托管邮箱：收件箱**
  - **托管邮箱：垃圾邮件**
  - **本地服务器：已送达**
  - **隔离**

  ![威胁防护状态报告中网络钓鱼电子邮件的传递状态视图](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>仅</sup> 限 Office 365 ATP

<sup>2</sup> 个零时差自动清除 (ZAP) 在独立 EOP (仅适用于 Exchange Online 邮箱) 。

如果单击 **"筛选器**"，则可以使用以下筛选器修改报告：

- **开始日期** 和 **结束日期**
- 检测值
- **仅由 Office** (365 ATP 保护 **) ：ATP**或**EOP。** 请注意，以下可筛选属性在"查看数据"中**不可用，通过"内容恶意软件 \> "。**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>威胁防护状态报告的详细信息表视图

如果您单击 **"查看详细信息**表"，显示的信息取决于您正在查看的图表：

- **通过"内容"查看数据 \> 恶意软件**：

  - **Date**
  - **位置**
  - **定向者**
  - **恶意软件名称**

- **查看数据，概述：** 无 **查看详细信息表** 按钮可用。

- 所有其他图表：

  - **Date**
  - **主题**
  - **发件人**
  - **Recipients**
  - **检测者**
  - **传递状态**
  - **数据被证明**

如果单击 **"筛选器**"，则可以使用以下筛选器修改报告：

- **开始日期** 和 **结束日期**
- 检测值
- **仅由 Office** (365 ATP 保护 **) ：ATP**或**EOP。** 请注意，以下可筛选属性在"查看数据"中**不可用，通过"内容恶意软件 \> "。**

## <a name="top-malware-report"></a>主要恶意软件报告

**主要的**恶意软件报告显示了 EOP 中的反恶意软件保护所[检测到的各种类型的恶意软件](anti-malware-protection.md)。

若要查看报告，请打开安全[&合规中心](https://protection.office.com)，转到报告**仪表板** \> **，然后选择**"主要**恶意软件"。** 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=TopMalware> 。

!["报表"仪表板中的"主要恶意软件"小部件](../../media/top-malware-report-widget.png)

将鼠标悬停在饼图中的 Wedge 上时，可以看到一种恶意软件的名称和检测为具有该恶意软件的邮件数量。

![主要的恶意软件报表视图](../../media/top-malware-report-view.png)

如果单击" **查看详细信息表**"，可以看到以下详细信息：

- **主要恶意软件**
- **Count**

如果在表 **视图中单击"筛选器** "报表视图 或详细信息表视图中的"筛选器"，可以指定具有开始日期和结束 **日期** 的 **日期范围**。

## <a name="url-threat-protection-report"></a>URL 威胁防护报告

Office 365 **高级威** 胁防护报告位于 Office 365 高级威胁防 (报告) 。 有关详细信息，请参阅 [URL 威胁防护报告](view-reports-for-atp.md#url-threat-protection-report)。

## <a name="user-reported-messages-report"></a>用户报告的邮件报告

**用户报告报告通过使用"** 报告邮件"外接程序显示有关用户已报告为垃圾邮件、网络钓鱼或邮件[的电子邮件相关信息](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)。

每封邮件都提供了详细信息，包括传递原因，如为组织配置的垃圾邮件策略异常或邮件流规则。 若要查看详细信息，请选择用户报告列表中的项目，然后在"摘要"和"**详细信息"****选项卡上查看**信息。

![用户报告报告显示标记为垃圾邮件、非垃圾邮件或钓鱼的邮件。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

若要查看此报告，请在 [安全与&合规](https://protection.office.com)中心内执行以下操作之一：

- 转到威**胁管理** \> **Dashboard** \> **仪表板用户报告的邮件**。

- 转到威 **胁管理** \> **审** \> **阅用户报告的邮件**。

![在安全与合规 &中心内，选择'威胁管理 \> 审阅 \> '用户报告的邮件'](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> 为了使用户报告正常工作，必须 **为** 您的 Office 365 环境启用审核日志记录。 这通常由在 Exchange Online 中分配了审核日志角色的人员执行。 有关详细信息，请参阅["启用或禁用 Microsoft 365 审核日志"。](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

## <a name="what-permissions-are-needed-to-view-these-reports"></a>查看这些报表需要哪些权限？

若要查看和使用这些报告，你必须是安全 & 合规中心和 Exchange Online **中指定角色** 组的成员。

- 在安全&合规中心内，你必须是以下角色组之一的成员：

  -组织管理 -安全 (也可以在 Azure Active Directory 管理中心 [-Security](https://aad.portal.azure.com) Reader 中执行此操作

  有关详细信息，请参阅[安全与合规中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。

- 在 Exchange Online 中，你必须是以下角色组之一的成员：

  -Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management

有关详细信息，请参阅 Exchange [Online 中的权限和](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo)[管理 Exchange Online 中的角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

## <a name="what-if-the-reports-arent-showing-data"></a>如果报告未显示数据，该怎什么情况？

如果无法在报告中看到数据，请仔细检查是否正确设置了你的策略。 若要了解详细信息，请参阅["防止威胁"。](protect-against-threats.md)

## <a name="related-topics"></a>相关主题

[EOP 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)

[安全与合规中心内的智能报告和见解](reports-and-insights-in-security-and-compliance.md)

[查看安全与合规中心&邮件流报告](view-mail-flow-reports.md)

[查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)
