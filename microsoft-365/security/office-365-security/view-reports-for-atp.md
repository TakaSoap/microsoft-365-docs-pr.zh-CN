---
title: 在报告仪表板中查看适用于 Office 365 的 Defender 报告
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 在安全 & 合规中心中查找和使用 Microsoft Defender for Office 365 的报告。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a237049c9ebbccf1c01feeb21129496e16d437b2
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572485"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a>在安全 & 合规中心的 "报告" 仪表板中查看 Office 365 的 Defender for the reports

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Microsoft Defender for Office 365 组织 (例如，Microsoft 365 E5 订阅或 Microsoft Defender for office 365 Plan 1 或 Microsoft defender for Office 365 Plan 2 加载项) 包含各种与安全相关的报告。 如果您具有 [必要的权限](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)，则可以转到 " **报告**" \> **仪表板**，在安全 & 合规中心中查看这些报告。 若要直接转到 "报表" 仪表板，请打开 <https://protection.office.com/insightdashboard> 。

![安全 & 合规中心中的 "报告" 仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a>适用于 Office 365 的 Defender 文件类型报告

" **适用于 Office 的 Defender 365 文件类型报告** " 报告显示了通过 [安全附件](atp-safe-attachments.md)检测为恶意的文件类型。

 报告的聚合视图允许在筛选过程中90天，而详细信息视图仅允许10天的筛选。

若要查看报告，请打开 " [安全 & 合规中心](https://protection.office.com)"，转到 " **报告**" \> **仪表板** ，然后选择 " **适用于 Office 365 的 Defender" 文件类型**。 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ATPFileReport> 。

!["报告" 仪表板中的 "Office 365 的 Defender" 文件类型小组件](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> 此报告中的信息也适用于 Office 365 中的 " [Defender For Office 邮件处置" 报告](#defender-for-office-365-message-disposition-report)。

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a>适用于 Office 365 的 "Defender for Office" 文件类型的报告视图

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

  将鼠标悬停在特定日期 (数据点) 上时，可以查看 EOP 中 [安全附件](atp-safe-attachments.md) 和 [反恶意软件保护](anti-malware-protection.md)检测到的恶意文件的类型细目。

  ![Defender for Office 365 文件类型报告中的文件视图](../../media/atp-file-types-report-file-view.png)

  如果单击 " **筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期** 和 **结束日期**
  - 图表中显示的相同文件类型值。

- **数据查看依据：消息**：图表包含以下信息：

  - **阻止访问**
  - **邮件已替换**
  - **监视的邮件**
  - **替换为动态电子邮件传递**：有关详细信息，请参阅 [在安全附件策略中动态传递](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。

  ![Defender for Office 365 文件类型报告中的邮件视图](../../media/atp-file-types-report-message-view.png)

  如果单击 " **筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期** 和 **结束日期**
  - 图表中可用的相同邮件处置值，以及传递的其他 **邮件** 值。

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a>适用于 Office 365 的 Defender 文件类型报告的详细信息表格视图

如果单击 " **查看详细信息表**"，则报告将提供最近10天内组织内发生的所有点击的近实时视图。 显示的信息取决于您所查看的图表：

- **数据查看依据：文件**：

  - **Date**
  - **收件人地址**
  - **发件人地址**
  - **邮件 id**：在邮件头的 **邮件 id** 标头字段中可用，并且应是唯一的。  (的示例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 记下尖括号) 。
  - **File**

  如果单击 " **筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期** 和 **结束日期**
  - 图表中显示的相同文件类型值。

- **数据查看依据：消息**：

  - **Date**
  - **收件人地址**
  - **发件人地址**
  - **邮件 ID**
  - **File**
  - **Subject**

  如果单击 " **筛选器**"，则可以使用以下筛选器修改结果：

  - **开始日期** 和 **结束日期**
  - 图表中可用的相同邮件处置值，以及传递的其他 **邮件** 值。

若要返回到 "报告" 视图，请单击 " **查看报告**"。

## <a name="defender-for-office-365-message-disposition-report"></a>适用于 Office 365 的 Defender 邮件处置报告

**ATP 邮件处置** 报告将向您显示检测为包含恶意内容的电子邮件所采取的操作。

若要查看报告，请打开 [安全 & 合规中心](https://protection.office.com)，转到 " **报告**" \> **仪表板** ，然后选择 " **用于 Office 365 的 Defender for Office 邮件处置**"。 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ATPMessageReport> 。

!["报告" 仪表板中的 "用于 Office 365 的 Defender" 邮件处置小组件](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> 此报告中的信息也适用于 " [Defender For Office 365 文件类型" 报告](#defender-for-office-365-file-types-report)。

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a>用于 Office 365 的 "Defender for Office" 邮件处置报告的报告视图

可以使用以下视图：

- **数据查看依据：消息**：图表包含以下信息：

  - **阻止访问**
  - **邮件已替换**
  - **监视的邮件**
  - **替换为动态电子邮件传递**：有关详细信息，请参阅 [在安全附件策略中动态传递](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。

  ![Defender for Office 365 文件类型报告中的邮件视图](../../media/atp-file-types-report-message-view.png)

  如果单击 " **筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期** 和 **结束日期**
  - 图表中可用的相同邮件处置值，以及传递的其他 **邮件** 值。

- **数据查看依据：文件**：图表包含以下信息：

  - **恶意 Excel 附件**
  - **恶意 Flash 附件**
  - **恶意 PDF 附件**
  - **恶意 PowerPoint 附件**
  - **恶意 Url**
  - **恶意 Word 附件**
  - **恶意可执行附件**
  - **其他**

  将鼠标悬停在特定日期 (数据点) 上时，可以查看 EOP 中 [安全附件](atp-safe-attachments.md) 和 [反恶意软件保护](anti-malware-protection.md)检测到的恶意文件的类型细目。

  ![Defender for Office 365 文件类型报告中的文件视图](../../media/atp-file-types-report-file-view.png)

  如果单击 " **筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期** 和 **结束日期**
  - 图表中显示的相同文件类型值。

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a>适用于 Office 365 的 "Defender for Office" 邮件处置报告的详细信息表视图

如果单击 " **查看详细信息表**"，则报告将提供最近10天内组织内发生的所有点击的近实时视图。 显示的信息取决于您所查看的图表：

- **数据查看依据：消息**：

  - **Date**
  - **收件人地址**
  - **发件人地址**
  - **邮件 ID**
  - **File**
  - **Subject**

  如果单击 " **筛选器**"，则可以使用以下筛选器修改结果：

  - **开始日期** 和 **结束日期**
  - 图表中可用的相同邮件处置值，以及传递的其他 **邮件** 值。

- **数据查看依据：文件**：

  - **Date**
  - **收件人地址**
  - **发件人地址**
  - **邮件 ID**
  - **File**

  如果单击 " **筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期** 和 **结束日期**
  - 图表中显示的相同文件类型值。

若要返回到 "报告" 视图，请单击 " **查看报告**"。

## <a name="mail-latency-report"></a>邮件延迟报告

**邮件延迟报告** 显示组织中的邮件传递和沙箱延迟的聚合视图。 服务中的邮件传递时间受多种因素的影响，并且以秒为单位的绝对传递时间通常不是成功或问题的最佳指示器。 一天中的传递时间较慢可能会被视为另一天的平均传递时间，反之亦然。 **邮件延迟报告** 尝试根据有关对其他邮件的观察传递时间的统计数据来限定邮件传递：

- 第 **50 个百分点** 值：这是邮件传递时间的中间部分。 您可以将此值视为平均传递时间。
- **90 百分点**：这表示邮件传递的延迟较长。 只有10% 的邮件花费超过此值传递时间。
- **99th 百分点**：这表示邮件传递的最长延迟。

不包括客户端和网络延迟。

若要查看报告，请打开 [安全性 & 合规性中心](https://protection.office.com)，转到 " **报告**" \> **仪表板** ，然后选择 " **邮件延迟报告**"。 若要直接转到报表，请打开 <https://protection.office.com/mailLatencyReport?viewid=P50> 。

!["报告" 仪表板中的邮件延迟报告构件](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a>邮件延迟报告的报告视图

在打开报表时，默认情况下将选中第50个 " **百分点值** " 选项卡。

默认情况下，此视图包含一个使用以下筛选器配置的图表：

- **日期**：最近7天
- **邮件视图**：
  - 触发邮件

此图显示了按以下类别组织的邮件：

- **邮件传递延迟**
- **沙箱延迟**

当您将鼠标悬停在图表中的某个类别上时，您可以查看每个类别中的延迟的细目。

![邮件延迟报告](../../media/mail-latency-report.png)

如果您在报告视图中单击 " **筛选器** "，则可以使用以下筛选器修改结果：

- 所有邮件
- 包含附件或 Url 的邮件

如果单击 " **90 百分点值** " 选项卡或 " **99th 百分点值** " 选项卡，则将使用第 **50 个百分点值** 视图中的相同默认筛选器。

### <a name="details-table-view-for-the-mail-latency-report"></a>邮件延迟报告的详细信息表格视图

"详细信息" 表视图中显示以下信息：

- **Date**
- **百分点值**
- **邮件计数**
- **整体延迟**

![邮件延迟报告详细信息](../../media/mail-latency-report-details.png)

上面显示了11月14日，所有传递的邮件和触发的平均延迟为 **108.033** 秒。

详细信息表包含每个选项卡上的相同信息。

## <a name="threat-protection-status-report"></a>威胁防护状态报告

**威胁防护状态** 报告是一个视图，它将有关检测到的恶意内容和恶意电子邮件的信息，以及通过 [Exchange ONLINE protection](exchange-online-protection-overview.md) (EOP) 和 Microsoft Defender for Office 365 进行了检测和阻止。 有关详细信息，请参阅 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。

## <a name="url-threat-protection-report"></a>URL 威胁防护报告

**Url 威胁防护报告** 提供了检测到的威胁的摘要和趋势视图，以及 [安全链接](atp-safe-links.md)的一部分对 URL 单击执行的操作。 此报告将不会从用户处单击 "数据"，即应用了 "安全链接策略" 的用户已选中 "不 **跟踪用户点击** " 选项。

若要查看报告，请打开 [安全性 & 合规性中心](https://protection.office.com)，转到 " **报告**" \> **仪表板** ，然后选择 " **URL 保护报告**"。 若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=URLProtectionActionReport> 。

!["报告" 仪表板中的 URL 保护报告小部件](../../media/url-protection-report-widget.png)

> [!NOTE]
> 这是一个 " *保护趋势" 报告*，即数据表示较大数据集中的趋势。 因此，在这里，聚合视图中的数据不是实时提供的，但详细信息表视图中的数据是，因此在这两种视图之间可能会出现细微差异。

### <a name="report-view-for-the-url-threat-protection-report"></a>URL 威胁防护报告的报告视图

**URL 威胁防护** 报告包含两个聚合视图，每四个小时刷新一次，显示最近90天的数据：

- **URL 单击 "保护操作**"：显示组织中的用户单击的 url 的数量以及单击的结果：

  - **阻止 (阻止** 用户导航到 URL) 
  - **阻止并单击**
  - **在扫描过程中单击**

  单击指示用户已通过阻止页面单击了恶意网站， (管理员可以禁用 "安全链接策略") 中的 "单击"。

  如果单击 " **筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期** 和 **结束日期**
  - 可用的单击保护操作加上 (**允许** 用户导航到 URL) 的值。

  ![URL 单击 URL 威胁防护报告中的 "保护操作" 视图](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **URL 单击应用程序**：显示支持安全链接的应用程序的 url 单击次数：

  - **电子邮件客户端**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **其他**

  如果单击 " **筛选器**"，则可以使用以下筛选器修改报表：

  - **开始日期** 和 **结束日期**
  - 可用的应用程序。

### <a name="details-table-view-for-the-url-threat-protection-report"></a>URL 威胁防护报告的详细信息表格视图

如果单击 " **查看详细信息表**"，则报告将提供最近7天内在组织内发生的所有点击的近实时视图，并提供以下详细信息：

- **单击 "时间"**
- **用户**
- **URL**
- **操作**
- **App**

如果单击 "详细信息表" 视图中的 " **筛选器** "，则可以按与报表视图中相同的条件进行筛选，也可以按逗号分隔的 **域** 或 **收件人** 进行筛选。

若要返回到 "报告" 视图，请单击 " **查看报告**"。

## <a name="additional-reports-to-view"></a>要查看的其他报告

除了本主题中所述的报告之外，还有几个其他报告可供使用，如下表所述：

****

|报告|主题|
|---|---|
|**Explorer** (microsoft Defender for Office 365 plan 2) 或 **实时检测** (microsoft Defender for office 365 计划 1) |[威胁资源管理器（和实时检测）](threat-explorer.md)|
|**电子邮件安全报告**，如主要发件人和收件人报告、欺骗邮件报告和垃圾邮件检测报告。|[查看安全与合规中心内的电子邮件安全报告](view-email-security-reports.md)|
|**邮件流报告**，例如转发报告、邮件流状态报告和主要发件人和收件人报告。|[查看安全 & 合规性中心中的邮件流报告](view-mail-flow-reports.md)|
|**安全链接的 URL 跟踪** 仅 (PowerShell) 。 此 cmdlet 的输出显示在过去七天内安全链接操作的结果。|[UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**EOP 和 Microsoft Defender For Office 365 的邮件流量结果** 仅)  (PowerShell。 此 cmdlet 的输出包含有关域、日期、事件类型、方向、操作和邮件计数的信息。|[MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|**EOP 和 Defender For Office 365 检测的邮件详细信息报告** 仅 (PowerShell) 。 此 cmdlet 的输出包含有关恶意文件或 Url、网络钓鱼企图、模拟以及电子邮件或文件中的其他潜在威胁的详细信息。|[MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>查看适用于 Office 的 Defender 365 报告所需的权限是什么？

若要查看和使用本主题中所述的报告，您必须是安全 & 合规性中心中下列角色组之一的成员：

- **组织管理**
- **安全管理员**
- **安全读者**
- **全局读者**

有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

**注意**：将用户添加到 microsoft 365 管理中心中对应的 Azure Active Directory 角色，用户可为用户提供安全 & 合规性中心中的必需权限 _以及_ Microsoft 365 中其他功能的权限。 有关详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="what-if-the-reports-arent-showing-data"></a>如果报告不显示数据，该怎么办？

如果您在您的 Defender for Office 365 报告中看不到数据，请仔细检查您的策略设置是否正确。 您的组织必须已定义 [安全链接策略](set-up-atp-safe-links-policies.md) 和 [安全附件策略](set-up-atp-safe-attachments-policies.md) ，以便将 Office 365 防护功能设置为就地使用。 另请参阅 [反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。

## <a name="related-topics"></a>相关主题

[安全与合规中心内的智能报告和见解](reports-and-insights-in-security-and-compliance.md)
  
[Azure Active Directory (角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
