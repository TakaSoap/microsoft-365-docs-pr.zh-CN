---
title: 查看 Defender for Office 365 报告
f1.keywords:
- CSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解如何查找和使用 Defender for Office 365门户中提供的报告Microsoft 365 Defender报告。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fbedc796fe257db700fa77f2d7b361ae188939ae
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476238"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a>在 Office 365 门户中查看 Defender for Microsoft 365 Defender 报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender for Office 365 organizations (for example， Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contains a variety of security-related reports. 如果您具有[必要的权限](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)，可以在管理门户中查看和下载Microsoft 365 Defender报告。

## <a name="view-and-download-reports"></a>查看和下载报告

### <a name="view-reports"></a>查看报告

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**. 若要直接转到电子邮件 **&协作报告页面** ，请使用 <https://security.microsoft.com/emailandcollabreport>。

1. 选择要查看的报告，然后选择" **查看详细信息"**。  

### <a name="download-reports"></a>下载报表

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to **ReportsEmail** >  **& collaboration** \> **Reports for download**. 若要直接转到" **报告"下载页面，** 请使用 <https://security.microsoft.com/ReportsForDownload?viewid=custom>。

:::image type="content" source="../../media/email-collaboration-download-reports.png" alt-text="&门户中的&quot;电子邮件Microsoft 365 Defender协作报告&quot;页" lightbox="../../media/email-collaboration-download-reports.png":::

> [!NOTE]
>
> 在安全门户中查看电子邮件安全报告Office 365 Defender [for Microsoft 365 Defender报告。](view-email-security-reports.md)
>
> 与邮件流相关的报告现在位于 EAC Exchange 管理 () 。 有关这些报告详细信息，请参阅新管理中心中的Exchange[报告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。

## <a name="safe-attachments-file-types-report"></a>保险箱附件文件类型报告

> [!NOTE]
> 此报告已被弃用。 威胁防护状态报告中提供了 [相同的信息](#threat-protection-status-report)。

## <a name="safe-attachments-message-disposition-report"></a>保险箱附件邮件处置报告

> [!NOTE]
> 此报告已被弃用。 威胁防护状态报告中提供了 [相同的信息](#threat-protection-status-report)。

## <a name="mail-latency-report"></a>邮件延迟报告

邮件 **延迟报告显示** 组织中遇到的邮件传递和触发延迟的聚合视图。 服务中的邮件传递时间受多种因素影响，绝对传递时间（以秒表示）通常不是成功或出现问题的良好指标。 一天的较慢的送达时间可能被视为另一天的平均送达时间，反之亦然。 这将尝试根据有关其他邮件的观察到送达时间的统计数据来限定邮件传递。

不包括客户端和网络延迟。

若要查看报告，请打开 Microsoft 365 Defender 门户 ，<https://security.microsoft.com>**转到报告** \> **电子邮件&协作** \> **电子邮件&报告**。 若要直接转到电子邮件 **&协作报告页面** ，请使用 <https://security.microsoft.com/emailandcollabreport>。

在" **电子邮件&协作** 报告"页上，找到 **"邮件延迟** 报告"，然后单击" **查看详细信息"**。 若要直接转到报告，请使用 <https://security.microsoft.com/mailLatencyReport>。


:::image type="content" source="../../media/mail-latency-report-widget.png" alt-text="&quot;电子邮件和协作报告&quot;页上的&quot;邮件延迟&小组件" lightbox="../../media/mail-latency-report-widget.png":::

在" **邮件延迟报告"** 页上，"邮件延迟报告"页上提供了 **以下** 选项卡：

- **第 50 个** 百分点值：这是邮件传递时间中间值。 可以将此值视为平均送达时间。 默认情况下，此选项卡为选中状态。
- **第 90** 个百分点值：这表示邮件传递延迟较高。 仅 10% 的邮件传递时间超过此值。
- **第 99 个** 百分点值：这表示邮件传递的延迟最高。

无论选择哪个选项卡，图表都会显示按以下类别组织的邮件：

- **总体**
- **触发**

将鼠标悬停在图表中的类别上时，可以看到每个类别中延迟的细分。

:::image type="content" source="../../media/mail-latency-report-50th-percentile-view.png" alt-text="邮件延迟报告的第 50 个百分点值视图" lightbox="../../media/mail-latency-report-50th-percentile-view.png":::

如果单击 **"筛选器**"，可以按以下值筛选图表和详细信息表：

- **UTC (utc)****：开始日期** 和 **结束日期**
- **消息视图**：下列值之一：
  - **所有邮件**
  - **触发的邮件**：下列值之一：
    - **内联触发**：包括传递前经过全面测试的邮件。
    - **异步触发**

配置完筛选器后，请单击"应用"**、"****取消**"或"清除 **筛选器"**。

在图表下面的详细信息表中，提供了以下信息：

- **UTC (日期)**
- **延迟**
- **邮件计数**
- **第 50 个百分点值**
- **第 90 个百分点值**
- **第 99 个百分点值**

在主报告页面上，"导出 !["图标。](../../media/m365-cc-sc-download-icon.png) **["](view-email-security-reports.md#export-report)** 导出"按钮可用。

## <a name="threat-protection-status-report"></a>威胁防护状态报告

威胁 **防护状态** 报告是一个单一视图，将有关 [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) 和 Microsoft Defender for Office 365 检测并阻止的恶意内容和恶意电子邮件的信息汇集在一起。 有关详细信息，请参阅 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。

## <a name="top-senders-and-recipients-report"></a>首要发件人和收件人报告

The **Top senders and recipients** report show the top recipients for EOP and Defender for Office 365 protection features. 有关详细信息，请参阅 Top [senders and recipients report](view-email-security-reports.md#top-senders-and-recipients-report)。

## <a name="url-protection-report"></a>URL 保护报告

URL **保护报告提供** 检测到的威胁的摘要和趋势视图，以及作为链接的一部分对 URL 单击 [保险箱视图](safe-links.md)。 此报告不会包含应用了"链接"策略保险箱"不跟踪用户单击"选项的用户的 **单击** 数据。

若要查看报告，请打开 Microsoft 365 Defender [门户](https://security.microsoft.com)，\>转到报告 **电子邮件&协作** \> **电子邮件&协作报告**。 在" **电子邮件&协作报告** "页上，找到 **"URL 保护"页** ，然后单击" **查看详细信息"**。 若要直接转到报告，请打开 <https://security.microsoft.com/reports/URLProtectionActionReport>。

:::image type="content" source="../../media/url-protection-report-widget.png" alt-text="&quot;电子邮件和协作报告&quot;页上的&quot;URL &小组件" lightbox="../../media/url-protection-report-widget.png":::

以下各节介绍了 **URL 保护** 报告页面上的可用视图。

> [!NOTE]
> 这是一个 *保护趋势报告*，这意味着数据表示较大数据集中的趋势。 因此，此处无法实时获得图表中的数据，但详细信息表中的数据是，因此您可能会发现这两者稍有不同。 图表每四小时刷新一次，并包含过去 90 天的数据。

### <a name="view-data-by-url-click-protection-action"></a>按 URL 查看数据单击保护操作

:::image type="content" source="../../media/url-threat-protection-report-url-click-protection-action-view.png" alt-text="URL 保护报告中的视图名称为 URL 单击保护操作" lightbox="../../media/url-threat-protection-report-url-click-protection-action-view.png":::

" **按 URL 查看数据"单击** 保护操作视图显示组织中用户单击的 URL 数以及单击结果：

- **允许**：允许单击。
- **租户管理员允许：** 链接策略中保险箱单击。
- **已阻止**：单击"已阻止"。
- **被租户管理员阻止**：单击链接保险箱阻止。
- **被阻止并单击通过**：阻止的单击，其中用户单击到阻止的 URL。
- **被租户管理员阻止且点击通过**：管理员已阻止链接，但用户点击通过。
- **在扫描过程中单击完成**：单击用户单击到 URL 的挂起扫描页面。
- **挂起扫描**：单击等待扫描裁定的 URL。

单击指示用户已单击通过阻止页面访问恶意网站 (管理员可以在"链接策略"保险箱禁用) 。

如果单击 **"筛选器**"，则可以通过在出现的飞出内容中选择以下一个或多个值来修改报表和详细信息表：

- **UTC (utc)****：开始日期** 和 **结束日期**
- **操作**：
  - **Allowed**
  - **阻止**
  - **租户管理员允许**
  - **阻止和单击**
  - **被租户管理员阻止并点击通过**
  - **在扫描过程中单击浏览**
  - **挂起扫描**
- **域**：报告结果中列出的 URL 域。
- **收件人**

配置完筛选器后，请单击"应用"**、"****取消**"或"清除 **筛选器"**。

图表下面的详细信息表提供了最近 7 天内组织中发生的所有单击的以下近实时视图：

- **单击时间**
- **用户**
- **URL**
- **操作**
- **应用**

在主报告页面上，创建 ![计划图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](view-email-security-reports.md#schedule-report)**、请求 ![报告图标。](../../media/m365-cc-sc-download-icon.png) **["请求报告](view-email-security-reports.md#request-report)**"和" ![导出"图标。](../../media/m365-cc-sc-download-icon.png) **["](view-email-security-reports.md#export-report)** 导出"按钮可用。

### <a name="view-data-by-url-click-by-application"></a>按 URL 单击应用程序查看数据

:::image type="content" source="../../media/url-threat-protection-report-url-click-by-application-view.png" alt-text="URL 保护报告中的 URL 单击保护操作视图" lightbox="../../media/url-threat-protection-report-url-click-by-application-view.png":::

"**按 URL 单击应用程序** 查看数据"视图显示支持"链接"保险箱单击数：

- **电子邮件客户端**
- **Office文档**
- **Teams**

如果单击 **"筛选器**"，则可以通过在出现的飞出内容中选择以下一个或多个值来修改报表和详细信息表：

- **UTC (utc)****：开始日期** 和 **结束日期**
- **检测**：图表中可用的应用。
- **域**：报告结果中列出的 URL 域。
- **收件人**

配置完筛选器后，请单击"应用"**、"****取消**"或"清除 **筛选器"**。

图表下面的详细信息表提供了最近 7 天内组织中发生的所有单击的以下近实时视图：

- **单击时间**
- **用户**
- **URL**
- **操作**
- **应用**

在主报告页面上，创建 ![计划图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](view-email-security-reports.md#schedule-report)**、请求 ![报告图标。](../../media/m365-cc-sc-download-icon.png) **["请求报告](view-email-security-reports.md#request-report)**"和" ![导出"图标。](../../media/m365-cc-sc-download-icon.png) **["](view-email-security-reports.md#export-report)** 导出"按钮可用。

## <a name="additional-reports-to-view"></a>要查看的其他报告

除了本文中所述的报告之外，还有其他一些报告可用，如下表所述：

|报告|主题|
|---|---|
|**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1) |[威胁资源管理器（和实时检测）](threat-explorer.md)|
|不需要 Defender for Office 365|[在电子邮件门户中查看Microsoft 365 Defender报告](view-email-security-reports.md)|
|EAC 管理中心Exchange中的 (流) |[新管理中心中的Exchange报告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|

PowerShell 报告 cmdlet：

|报告|主题|
|---|---|
|主要发件人和收件人|[Get-MailTrafficTopReport](/powershell/module/exchange/get-mailtraffictopreport) <p> [Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|热门恶意软件|[Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|邮件通信|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <p> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|安全链接|[Get-SafeLinksAggregateReport](/powershell/module/exchange/get-safelinksaggregatereport) <p> [Get-SafeLinksDetailReport](/powershell/module/exchange/get-safelinksdetailreport)|
|遭到入侵的用户|[Get-CompromisedUserAggregateReport](/powershell/module/exchange/get-compromiseduseraggregatereport) <p> [Get-CompromisedUserDetailReport](/powershell/module/exchange/get-compromiseduserdetailreport)|
|邮件流状态|[Get-MailflowStatusReport](/powershell/module/exchange/get-mailflowstatusreport)|
|欺骗用户|[Get-SpoofMailReport](/powershell/module/exchange/get-spoofmailreport)|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>查看 Defender for Office 365报告需要哪些权限？

若要查看和使用本文中所述的报告，您需要是该门户中以下角色组之一Microsoft 365 Defender成员：

- **组织管理**
- **安全管理员**
- **安全读者**
- **全局读取者**

有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。

**注意**：将用户添加到 Microsoft 365 管理中心 中的相应 Azure Active Directory 角色会为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能Microsoft 365。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="what-if-the-reports-arent-showing-data"></a>如果报告未显示数据，该做什么？

如果你在 Defender for Office 365报告中看不到数据，请仔细检查策略是否正确设置。 你的组织必须保险箱[链接](set-up-safe-links-policies.md)策略保险箱[附件](set-up-safe-attachments-policies.md)策略，以便 Defender Office 365保护就位。 另请参阅 [反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。

## <a name="related-topics"></a>相关主题

[智能报表和 Microsoft 365 Defender见解](reports-and-insights-in-security-and-compliance.md)

[Azure AD内置角色](/azure/active-directory/roles/permissions-reference)
