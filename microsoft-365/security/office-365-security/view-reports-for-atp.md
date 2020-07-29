---
title: 查看高级威胁防护报告
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: 在安全合规中心中查找和使用适用于 Office 365 高级威胁防护的报告 &amp; 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4210ea30457215f9adc2984f24f161dc94985873
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434074"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>查看 Office 365 高级威胁防护报告

Office 365 高级威胁防护（ATP）组织（例如，Microsoft 365 E5 订阅或 ATP 计划1或 ATP 计划2加载项）包含各种与安全相关的报告。 如果您具有[必要的权限](#what-permissions-are-needed-to-view-the-atp-reports)，则可以转到 "**报告**" \> **仪表板**，在安全 & 合规中心中查看这些报告。 若要直接转到 "报表" 仪表板，请打开 <https://protection.office.com/insightdashboard> 。

![安全 & 合规中心中的 "报告" 仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a>高级威胁防护文件类型报告

**高级威胁防护文件类型报告**报告显示通过[ATP 安全附件](atp-safe-attachments.md)检测为恶意的文件类型。

 报告的聚合视图允许在筛选过程中90天，而详细信息视图仅允许10天的筛选。

若要查看报告，请打开 "[安全 & 合规中心](https://protection.office.com)"，转到 "**报告**" \> **仪表板**，然后选择 " **Office ATP 文件类型**"。 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ATPFileReport> 。

!["报表" 仪表板中的 Office ATP 文件类型小组件](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> [高级威胁防护邮件处置报告](#advanced-threat-protection-message-disposition-report)中也提供了此报告中的信息。

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a>高级威胁防护文件类型报告的报告视图

可以使用以下视图：

- **数据查看依据：文件**：图表包含以下信息：

  - **恶意 Excel 附件**
  - **恶意 Flash 附件**
  - **恶意 PDF 附件**
  - **恶意 PowerPoint 附件**
  - **恶意 Url**
  - **恶意 Word 附件**
  - **恶意可执行附件**
  - **其他**

  当您将鼠标指针悬停在特定的某一天（数据点）时，您可以看到由 EOP 中的[ATP 安全附件](atp-safe-attachments.md)和[反恶意软件保护](anti-malware-protection.md)检测到的恶意文件的类型细目。

  ![ATP 文件类型报告中的文件视图](../../media/atp-file-types-report-file-view.png)

  如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期**和**结束日期**
  - 图表中显示的相同文件类型值。

- **数据查看依据：消息**：图表包含以下信息：

  - **阻止访问**
  - **邮件已替换**
  - **监视的邮件**
  - **替换为动态电子邮件传递**：有关详细信息，请参阅[使用 ATP 安全附件进行动态传递和预览](dynamic-delivery-and-previewing.md)。

  ![ATP 文件类型报告中的邮件视图](../../media/atp-file-types-report-message-view.png)

  如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期**和**结束日期**
  - 图表中可用的相同邮件处置值，以及传递的其他**邮件**值。

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a>高级威胁防护文件类型报告的详细信息表格视图

如果单击 "**查看详细信息表**"，则报告将提供最近10天内组织内发生的所有点击的近实时视图。 显示的信息取决于您所查看的图表：

- **数据查看依据：文件**：

  - **Date**
  - **收件人地址**
  - **发件人地址**
  - **邮件 id**：在邮件头的**邮件 id**标头字段中可用，并且应是唯一的。 示例值为 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` （请注意尖括号）。
  - **File**

  如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期**和**结束日期**
  - 图表中显示的相同文件类型值。

- **数据查看依据：消息**：

  - **Date**
  - **收件人地址**
  - **发件人地址**
  - **邮件 ID**
  - **File**
  - **主题**

  如果单击 "**筛选器**"，则可以使用以下筛选器修改结果：

  - **开始日期**和**结束日期**
  - 图表中可用的相同邮件处置值，以及传递的其他**邮件**值。

若要返回到 "报告" 视图，请单击 "**查看报告**"。

## <a name="advanced-threat-protection-message-disposition-report"></a>高级威胁防护邮件处置报告

**ATP 邮件处置**报告将向您显示检测为包含恶意内容的电子邮件所采取的操作。

若要查看报告，请打开 "[安全 & 合规中心](https://protection.office.com)"，转到 "**报告**" \> **仪表板**，然后选择 " **Office ATP 邮件处置**"。 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ATPMessageReport> 。

!["报告" 仪表板中的 Office 365 ATP 邮件处置小部件](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> [高级威胁防护文件类型报告](#advanced-threat-protection-file-types-report)中也提供了此报告中的信息。

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a>高级威胁防护邮件处置报告的报告视图

可以使用以下视图：

- **数据查看依据：消息**：图表包含以下信息：

  - **阻止访问**
  - **邮件已替换**
  - **监视的邮件**
  - **替换为动态电子邮件传递**：有关详细信息，请参阅[使用 ATP 安全附件进行动态传递和预览](dynamic-delivery-and-previewing.md)。

  ![ATP 文件类型报告中的邮件视图](../../media/atp-file-types-report-message-view.png)

  如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期**和**结束日期**
  - 图表中可用的相同邮件处置值，以及传递的其他**邮件**值。

- **数据查看依据：文件**：图表包含以下信息：

  - **恶意 Excel 附件**
  - **恶意 Flash 附件**
  - **恶意 PDF 附件**
  - **恶意 PowerPoint 附件**
  - **恶意 Url**
  - **恶意 Word 附件**
  - **恶意可执行附件**
  - **其他**

  当您将鼠标指针悬停在特定的某一天（数据点）时，您可以看到由 EOP 中的[ATP 安全附件](atp-safe-attachments.md)和[反恶意软件保护](anti-malware-protection.md)检测到的恶意文件的类型细目。

  ![ATP 文件类型报告中的文件视图](../../media/atp-file-types-report-file-view.png)

  如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期**和**结束日期**
  - 图表中显示的相同文件类型值。

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a>高级威胁防护邮件处置报告的详细信息表格视图

如果单击 "**查看详细信息表**"，则报告将提供最近10天内组织内发生的所有点击的近实时视图。 显示的信息取决于您所查看的图表：

- **数据查看依据：消息**：

  - **Date**
  - **收件人地址**
  - **发件人地址**
  - **邮件 ID**
  - **File**
  - **主题**

  如果单击 "**筛选器**"，则可以使用以下筛选器修改结果：

  - **开始日期**和**结束日期**
  - 图表中可用的相同邮件处置值，以及传递的其他**邮件**值。

- **数据查看依据：文件**：

  - **Date**
  - **收件人地址**
  - **发件人地址**
  - **邮件 ID**
  - **File**

  如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期**和**结束日期**
  - 图表中显示的相同文件类型值。

若要返回到 "报告" 视图，请单击 "**查看报告**"。

## <a name="threat-protection-status-report"></a>威胁防护状态报告

**威胁防护状态**报告是一个视图，它将有关检测到的恶意内容和恶意电子邮件的信息，以及[Exchange Online protection](exchange-online-protection-overview.md) （EOP）和 Office 365 ATP （）和 Office ATP 结合在一起。 有关详细信息，请参阅[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。

## <a name="url-threat-protection-report"></a>URL 威胁防护报告

**Url 威胁防护报告**提供了检测到的威胁的汇总和趋势视图，以及对 URL 单击执行的操作作为[ATP 安全链接](atp-safe-links.md)的一部分。 此报告将不会从用户处单击 "数据"，即应用了 "安全链接策略" 的用户已选中 "不**跟踪用户点击**" 选项。

若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 " **URL 保护报告**"。 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=URLProtectionActionReport> 。

!["报告" 仪表板中的 URL 保护报告小部件](../../media/url-protection-report-widget.png)

> [!NOTE]
> 这是一个 "*保护趋势" 报告*，即数据表示较大数据集中的趋势。 因此，在这里，聚合视图中的数据不是实时提供的，但详细信息表视图中的数据是，因此在这两种视图之间可能会出现细微差异。

### <a name="report-view-for-the-url-threat-protection-report"></a>URL 威胁防护报告的报告视图

**URL 威胁防护**报告包含两个聚合视图，每四个小时刷新一次，显示最近90天的数据：

- **URL 单击 "保护操作**"：显示组织中的用户单击的 url 的数量以及单击的结果：

  - **阻止**
  - **阻止并单击**
  - **在扫描过程中单击**

  单击指示用户已通过阻止页面单击到恶意网站（管理员可以禁用 "在安全链接策略中单击"）。

  如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期**和**结束日期**
  - 可用的单击保护操作，以及**允许**查看所有 URL 单击的信息的值（不只是阻止单击）。

  ![URL 单击 URL 威胁防护报告中的 "保护操作" 视图](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **URL 单击应用程序**：显示支持 OFFICE 365 ATP 安全链接的应用程序的 url 单击次数：

  - **电子邮件客户端**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **其他**

  如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期**和**结束日期**
  - 可用的应用程序。

### <a name="details-table-view-for-the-url-threat-protection-report"></a>URL 威胁防护报告的详细信息表格视图

如果单击 "**查看详细信息表**"，则报告将提供最近7天内在组织内发生的所有点击的近实时视图，并提供以下详细信息：

- **单击 "时间"**
- **用户**
- **URL**
- **Action**
- **App**

如果单击 "详细信息表" 视图中的 "**筛选器**"，则可以按与报表视图中相同的条件进行筛选，也可以按逗号分隔的**域**或**收件人**进行筛选。

若要返回到 "报告" 视图，请单击 "**查看报告**"。

## <a name="additional-reports-to-view"></a>要查看的其他报告

除了本主题中所述的 ATP 报告之外，还有几个其他报告可供使用，如下表所述：

|报告|主题|
|---|---|
|**资源管理器**（atp 计划2）或**实时检测**（atp 计划1）|[威胁资源管理器（和实时检测）](threat-explorer.md)|
|**电子邮件安全报告**，如主要发件人和收件人报告、欺骗邮件报告和垃圾邮件检测报告。|[查看安全与合规中心内的电子邮件安全报告](view-email-security-reports.md)|
|**邮件流报告**，例如转发报告、邮件流状态报告和主要发件人和收件人报告。|[查看安全 & 合规性中心中的邮件流报告](view-mail-flow-reports.md)|
|**ATP 安全链接的 URL 跟踪**（仅限 PowerShell）。 此 cmdlet 的输出显示在过去七天内 ATP 安全链接操作的结果。|[UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**EOP 和 ATP 的邮件流量结果**（仅限 PowerShell）。 此 cmdlet 的输出包含有关域、日期、事件类型、方向、操作和邮件计数的信息。|[MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport) <br/><br/> |
|**EOP 和 ATP 检测的邮件详细信息报告**（仅限 PowerShell）。 此 cmdlet 的输出包含有关恶意文件或 Url、网络钓鱼企图、模拟以及电子邮件或文件中的其他潜在威胁的详细信息。|[MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>查看 ATP 报告所需的权限是什么？

为了查看和使用本主题中所述的报告，**必须为安全 &amp; 合规中心和 Exchange 管理中心分配适当的角色**。

- 对于 "安全 & 合规中心"，您必须具有以下分配的角色之一：

  - 组织管理
  - 安全管理员（可在 Azure Active Directory 管理中心中分配（ [https://aad.portal.azure.com](https://aad.portal.azure.com) ））
  - 安全操作员（可在 Azure Active Directory 管理中心中分配（ [https://aad.portal.azure.com](https://aad.portal.azure.com) ））
  - 安全读取者

- 对于 Exchange Online，必须在 Exchange 管理中心（）或 PowerShell cmdlet 中分配以下角色之一 [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) （请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)）：

  - 组织管理
  - 仅限查看组织管理
  - “仅供查看收件人”角色
  - 合规性管理

若要了解详细信息，请参阅以下资源：

- [安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online 中的功能权限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a>如果报告不显示数据，该怎么办？

如果您未在 ATP 报告中看到数据，请仔细检查您的策略设置是否正确。 您的组织必须定义[Atp 安全链接策略](set-up-atp-safe-links-policies.md)和[atp 安全附件策略](set-up-atp-safe-attachments-policies.md)，以便将 ATP 保护设置到位。 另请参阅[Office 365 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。

## <a name="related-topics"></a>相关主题

[安全与合规中心内的智能报告和见解](reports-and-insights-in-security-and-compliance.md)
  
[角色权限（Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
